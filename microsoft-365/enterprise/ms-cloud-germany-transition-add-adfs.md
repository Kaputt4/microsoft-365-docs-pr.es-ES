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
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838418"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland

Este cambio de configuración debe aplicarse en cualquier momento antes de que se inicie la fase 2.
Una vez completada la fase 2, el cambio de configuración funcionará y podrá iniciar sesión a través de puntos de conexión globales de Office 365, como `https://portal.office.com` . Si va a implementar el cambio de configuración antes de la fase  2, los extremos globales de Office 365 aún no funcionarán, pero la nueva confianza de usuario de confianza sigue formando parte de la configuración de servicios de federación de Active Directory (AD FS).

Los clientes que usan la autenticación federada con Servicios de federación de Active Directory (AD FS) no deben realizar cambios en los URI del emisor que se usan para todas las autenticaciones con servicios de dominio de Active Directory (AD DS) locales durante la migración. Cambiar los URI del emisor provocará errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD  FS o cuando un dominio se convierte de administrado a _federado_ y viceversa. Se recomienda no agregar, quitar ni convertir un dominio federado en el inquilino de Azure AD que se ha migrado. Los URI del emisor se pueden cambiar una vez completada la migración.

Para preparar la granja de AD FS para la migración desde Microsoft Cloud Deutschland, siga estos pasos:

1. Haga una copia de seguridad de la configuración de AD FS, incluida la confianza existente del usuario de confianza de Microsoft Cloud Deutschland, con [estos pasos](#backup). Asigne un nombre a **la copia de seguridad MicrosoftCloudDeutschlandOnly** para indicar que solo tiene la información del inquilino de Microsoft Cloud Deutschland.

   > [!NOTE]
   > La copia de seguridad no solo contendrá la confianza de usuario de confianza de Office 365 existente para Microsoft Cloud Deutschland, sino también todas las demás confianzas de usuario de confianza presentes en la granja de servidores de AD FS correspondiente.

2. Probar la restauración con la copia de seguridad de MicrosoftCloudDeutschlandOnly, la granja de servidores de AD FS debe seguir funcionando como Microsoft Cloud Deutschland solamente.

Una vez completada y probada la copia de seguridad de AD FS, siga estos pasos para agregar una nueva confianza de usuario de confianza a la configuración de ADFS:

1. Abra la consola de administración de AD FS.

2. En el panel izquierdo de la consola de administración de ADFS, vaya al menú **Confianzas de usuario de** confianza.

3. En el panel derecho, seleccione **Agregar confianza de usuario de confianza...**

4. Seleccione **Inicio en** la página **de** bienvenida del Asistente para agregar confianza de usuario de confianza.

5. En la **página Seleccionar origen de** datos, seleccione Importar datos sobre el usuario de confianza publicado en línea o en una red **local**. El **valor de dirección de metadatos de** federación (nombre de host o dirección URL) debe establecerse en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Haga clic en **Siguiente**.

6. En la **página Especificar nombre para** mostrar, escriba el nombre para mostrar como Microsoft Office **365 Identity Platform WorldWide**. Haga clic en **Siguiente**.

7. Si estás usando ADFS en Windows Server 2012, en la página del asistente Configurar la autenticación **multifactor ahora?**, selecciona la opción adecuada según tus requisitos de autenticación. Si sigue con el valor predeterminado, seleccione No quiero configurar la configuración de autenticación **multifactor** para esta confianza de usuario de confianza en este momento . Puede cambiar esta configuración más adelante si lo desea.

8. For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep Permit all users to access this **relying party** selected and click **Next**.

8. Para AD FS 2016 y AD FS 2019: en la página Elegir directiva de control de acceso, seleccione la directiva de **control** de acceso adecuada y haga clic en **Siguiente**. Si no se elige ninguno, la confianza de usuario de confianza **no funcionará.**

9. Haga **clic en** Siguiente en la página Listo para agregar **confianza** para completar el asistente.

10. Haga **clic en** Cerrar en la **página** Finalizar.

Al cerrar el asistente, se establece la confianza de usuario de confianza con el servicio global de Office 365. Sin embargo, aún no se han configurado reglas de transformación de emisión.

Puedes usar la [Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas. Las reglas de notificación generadas creadas con la Ayuda de AD FS se pueden agregar manualmente a través de la consola de administración de AD FS o con PowerShell. La Ayuda de AD FS generará los scripts de PowerShell necesarios que deben ejecutarse.  

> [!NOTE]
> [La Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generará las reglas de transformación de emisión estándar que se envían con el producto. Sin embargo, si las reglas de transformación de emisión personalizadas se aplican en la confianza de usuario de confianza de usuario de confianza de Microsoft Cloud Deutschland (por ejemplo, URI de emisor personalizado, IDs inmutables no estándar o cualquier otra personalización), las reglas generadas por la ayuda de AD FS deben modificarse de forma que se ajusten a la lógica personalizada que se aplica actualmente para la confianza de usuario de confianza de Microsoft Cloud Deutschland. Si estas personalizaciones no están integradas en las reglas generadas a través de la Ayuda  de [AD FS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)la autenticación **en Microsoft Office 365 Identity Platform WorldWide** probablemente no funcionará para las identidades federadas.

1. Ejecute **Generar notificaciones** en la Ayuda de AD [FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) y copie el script de PowerShell con la **opción Copiar** en la esquina superior derecha del script.

2. Siga los pasos descritos en la Ayuda [de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) sobre cómo ejecutar el script de PowerShell en la granja de servidores de AD FS para generar la confianza global de usuario de confianza.

3. Compruebe que hay dos confianzas de usuario de confianza; uno para Microsoft Cloud Deutschland y otro para el servicio global de Office 365. El siguiente comando se puede aprovechar para la comprobación. Debe devolver dos filas y los nombres e identificadores respectivos.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Haga una copia de seguridad de la configuración de migración completa, incluidas ambas confianzas de usuario de confianza, mediante [estos pasos](#backup). Guárdelo con el nombre **MicrosoftCloudDeutschlandAndWorldwide**.

5. Mientras el inquilino está en migración, compruebe periódicamente que la autenticación de AD FS funciona con Microsoft Cloud Deutschland y la nube global de Microsoft en los distintos pasos de migración admitidos.


## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperación ante desastres de AD FS (base de datos WID)

Para restaurar la granja de servidores de AD FS en una herramienta de restauración rápida de [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres, debe aprovecharse. Por lo tanto, la herramienta debe descargarse y antes del inicio de la migración se debe crear una copia de seguridad y almacenarla de forma segura. En este ejemplo, se han ejecutado los siguientes comandos para realizar una copia de seguridad de una granja de servidores que se ejecuta en una base de datos WID:

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
