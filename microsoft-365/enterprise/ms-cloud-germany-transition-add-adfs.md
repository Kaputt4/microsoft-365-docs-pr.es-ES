---
title: Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: pasos de migración de Servicios de federación de Active Directory (AD FS) para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727472"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland

Este cambio de configuración se puede aplicar en cualquier momento antes de que se inicie la fase 4.
Una vez completada la fase 2, el cambio de configuración funcionará y podrá iniciar sesión en puntos de conexión globales de Office 365, como `https://portal.office.com` . Si va a implementar el cambio de configuración antes de la fase  2, los extremos globales de Office 365 aún no funcionarán, pero la nueva confianza de usuario de confianza sigue formando parte de la configuración de servicios de federación de Active Directory (AD FS).

Para migrar la granja de AD FS desde Microsoft Cloud Deutschland:

1. Haga una copia de seguridad de la configuración de AD FS, incluida la información de confianza de FF con [estos pasos](#backup). Asigne un nombre a **la copia de seguridad de Microsoft Cloud Deutschland_Only** para indicar que solo tiene la información del inquilino de Microsoft Cloud Deutschland.
2. Pruebe la restauración con la copia de seguridad de Microsoft Cloud Deutschland_Only, la granja de servidores de AD FS debe seguir funcionando como Microsoft Cloud Deutschland solamente.

Una vez completada y probada la copia de seguridad de AD FS, siga estos pasos para agregar una nueva confianza de usuario de confianza a la configuración de ADFS:

1. Abrir la consola de administración de AD FS
2. En el panel izquierdo de la consola de administración de **ADFS, expanda ADFS**, luego **Relaciones** de confianza y, a continuación, **Confianzas de usuario de confianza**
3. En el panel derecho, seleccione **Agregar confianza de usuario de confianza...**
4. Seleccione **Siguiente** en la **página de** bienvenida del Asistente para agregar confianza de usuario de confianza.
5. En la **página Seleccionar origen de** datos, seleccione Importar datos sobre el usuario de confianza publicado en línea o en una red **local**. El **valor de dirección de metadatos de** federación (nombre de host o dirección URL) debe establecerse en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Luego, haga clic en **Siguiente**.
6. En la **página Seleccionar origen de** datos, escriba el nombre para mostrar como Microsoft Office **365 Identity Platform WorldWide**. Luego, haga clic en **Siguiente**.
7. En la página del asistente **Configure Multi-factor Authentication Now?,** seleccione la opción adecuada según sus requisitos de autenticación. Si sigue con el valor predeterminado, seleccione No quiero configurar la configuración de autenticación **multifactor** para esta confianza de usuario de confianza en este momento . Puede cambiar esta configuración más adelante si lo desea.
8. En elegir reglas **de autorización de emisión,** mantenga permitir que todos los usuarios **accedan** a este usuario de confianza seleccionado haga clic en **Siguiente**
9. Haga **clic en** Siguiente en la página Listo para agregar **confianza** para completar el asistente.
10. Haga **clic en** Cerrar en la **página** Finalizar.

Al cerrar el asistente, se establece la confianza de usuario de confianza con los servicios globales de Office 365. Sin embargo, aún no se han configurado reglas de transformación de emisión.

Puedes usar la [Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas. Las reglas de notificación generadas creadas con la Ayuda de AD FS se pueden agregar manualmente a través de la consola de administración de AD FS o con PowerShell. La Ayuda de AD FS generará los scripts de PowerShell necesarios que deben ejecutarse.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Ejecute **la ayuda Generar notificaciones** en AD FS y  copie el script de transformación de notificaciones de PowerShell con la opción Copiar en la esquina superior derecha del script.
2. Abra el editor de texto que prefiera y pegue el script de PowerShell en una nueva ventana de texto.
3. Agregue las siguientes líneas de PowerShell al final del script pegada del paso 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. A salvo y ejecute el script de PowerShell.
5. Compruebe que hay dos confianzas de usuario de confianza presentes; uno para Microsoft Cloud Deutschland y otro para el servicio global de Office 365.
6. Haga una copia de seguridad de sus confianzas [con estos pasos](#backup). Guárdelo con el **nombre FFAndWorldwide**.
7. Complete la migración back-end y compruebe que AD FS todavía funciona durante el proceso de migración.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperación ante desastres de AD FS (base de datos WID)

Para restaurar la granja de servidores de AD FS en una herramienta de restauración rápida de [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres, debe aprovecharse. Por lo tanto, la herramienta debe descargarse y antes del inicio de la migración se debe crear una copia de seguridad y almacenarla de forma segura. En este ejemplo (entornos TAT), se han ejecutado los siguientes comandos para realizar una copia de seguridad de la granja de servidores:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Copia de seguridad de una granja de servidores de AD FS

1. Instale la herramienta de restauración rápida de AD FS en el servidor principal de AD FS.
2. Importe el módulo en una sesión de PowerShell con este comando.
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. Ejecute el comando de copia de seguridad:
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. Almacene la copia de seguridad de forma segura en un destino deseado.

### <a name="restore-an-ad-fs-farm"></a>Restaurar una granja de servidores de AD FS

Si la granja de servidores ha fallado por completo y no hay ninguna forma de volver a la granja de servidores antigua, haga lo siguiente. 

1. Mueva la copia de seguridad generada y almacenada anteriormente al nuevo servidor principal de AD FS.
2. Ejecute el siguiente `Restore-ADFS` comando de PowerShell. Si es necesario, importe el certificado SSL de AD FS de antemano.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Apunte los nuevos registros DNS o el equilibrador de carga a los nuevos servidores de AD FS.

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
