---
title: Pasos de migración de AD FS para la migración desde la nube de Microsoft Alemania
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
description: 'Resumen: pasos para la migración de los servicios de Federación de Active Directory (AD FS) para la migración desde la nube de Microsoft Alemania.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688670"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Pasos de migración de AD FS para la migración desde la nube de Microsoft Alemania

Para migrar la granja de servidores de servicios de Federación de Active Directory (AD FS) desde la nube de Microsoft Alemania:

1. Realice una copia de seguridad de la configuración de AD FS, incluida la información de confianza FF, con [estos pasos](#backup). Denomine a la copia de seguridad de la **nube de microsoft Deutschland_Only** para indicar que solo tiene la información de inquilino Alemania de la nube de Microsoft.
2. Probar la restauración mediante la copia de seguridad de Microsoft Cloud Deutschland_Only, la granja de AD FS debe seguir funcionando solo como Alemania de nube de Microsoft.
3. Cree una nueva relación de confianza para usuario autenticado de **AD FS > servicios de Office 365**.
4. En **relaciones de confianza para usuario autenticado** en la consola de administración de AD FS, seleccione **Agregar relación de confianza para usuario autenticado**.
5. Seleccione **siguiente** en la página de **bienvenida** del Asistente para agregar relaciones de confianza para usuario autenticado.
6. En la página **Seleccionar origen de datos** , seleccione **importar datos sobre el usuario de confianza publicado en línea o en una red local**. El valor de la **dirección de metadatos de Federación (nombre de host o dirección URL)** se establece en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Haga clic en **Siguiente**.
7. En la página **Seleccionar origen de datos** , escriba el nombre para mostrar. Microsoft recomienda la **plataforma de identidad de Microsoft Office 365 en todo el mundo**. Haga clic en **Siguiente**.
8. Haga clic en **siguiente** en la página **¿configurar la autenticación multifactor ahora?**, **Elija reglas de autorización de emisión** y **listas para agregar páginas de confianza** .
9. Haga clic en **cerrar** en la página **Finalizar** .

Al cerrar el asistente, se establece la relación de confianza para usuario autenticado con los servicios de Office 365 eSTS. Sin embargo, no se establecen reglas de transformación de emisión.

Puede usar la [ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas. Las reglas de notificaciones generadas creadas con la ayuda de AD FS pueden agregarse manualmente a través de la consola de administración de AD FS o con PowerShell. La ayuda de AD FS generará los scripts de PowerShell necesarios que se deben ejecutar.  

1. Ejecute **generar notificaciones** en la ayuda de AD FS y copie el script de transformación de notificaciones de PowerShell con la opción de **copia** situada en la esquina superior derecha del script.
2. Pegue el PowerShell generado en lo siguiente:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Ejecute el script completado.
4.  Compruebe que hay dos relaciones de confianza para usuario autenticado presentes; uno para el mundo y otro para BF.
5.  Realice una copia de seguridad de las confianzas mediante [estos pasos](#backup). Guárdelo con el nombre **FFAndWorldwide**.
6.  Complete la migración del back-end y compruebe que AD FS sigue funcionando durante el proceso de migración.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperación ante desastres de AD FS (base de datos WID)

Para restaurar la granja de AD FS, es necesario aprovechar la [herramienta de restauración rápida de AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres. Por lo tanto, la herramienta debe descargarse y antes de iniciar la migración, se debe crear una copia de seguridad y almacenarla de forma segura. En este ejemplo (entornos TAT) se han ejecutado los siguientes comandos para hacer una copia de seguridad de la granja de servidores:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Copia de seguridad de una granja de AD FS

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

### <a name="restore-an-ad-fs-farm"></a>Restauración de una granja de AD FS

Si la granja de servidores falló completamente y no hay forma de volver a la granja de servidores anterior, haga lo siguiente. 

1. Mueva la copia de seguridad previamente generada y almacenada al nuevo servidor principal de AD FS.
2. Ejecute el siguiente `Restore-ADFS` comando de PowerShell. Si es necesario, importe de antemano el certificado SSL de AD FS.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Apunte sus nuevos registros DNS o un equilibrador de carga a los nuevos servidores de AD FS.

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
