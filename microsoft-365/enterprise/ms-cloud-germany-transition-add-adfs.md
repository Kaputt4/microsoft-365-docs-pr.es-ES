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
description: 'Resumen: pasos de migración de los Servicios de federación de Active Directory (AD FS) para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688670"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland

Para migrar la granja de servicios de federación de Active Directory (AD FS) desde Microsoft Cloud Deutschland:

1. Haga una copia de seguridad de la configuración de AD FS, incluida la información de confianza de [FF, con estos pasos.](#backup) Asigne un nombre a la copia de seguridad **de Microsoft Cloud Deutschland_Only** para indicar que solo tiene la información del espacio empresarial de Microsoft Cloud Deutschland.
2. Pruebe la restauración con la copia de seguridad de Microsoft Cloud Deutschland_Only, la granja de AD FS debe seguir funcionando solo como Microsoft Cloud Deutschland.
3. Cree una nueva confianza de usuario de confianza de **AD FS > servicios de Office 365.**
4. En **Confianzas de usuario de confianza en la** consola de administración de AD FS, seleccione Agregar confianza para usuario de **confianza.**
5. Seleccione **Siguiente en** la página **principal** del Asistente para agregar confianza de usuario de confianza.
6. En la **página Seleccionar origen de** datos, seleccione Importar datos sobre el usuario de confianza publicado en línea o en una red **local.** El valor de dirección de metadatos de federación **(nombre de host o dirección URL)** se establece en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Haga clic en **Siguiente**.
7. En la **página Seleccionar origen de** datos, escriba el nombre para mostrar. Microsoft recomienda **Microsoft Office 365 Identity Platform WorldWide**. Haga clic en **Siguiente**.
8. Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and Ready to **Add Trust** pages.
9. Haga **clic en** Cerrar en la **página** Finalizar.

Al cerrar el asistente, se establece la confianza de usuario de confianza para los servicios de Office 365 eSTS. Sin embargo, no se establecen reglas de transformación de emisión.

Puedes usar la [Ayuda de AD FS para](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generar las reglas de transformación de emisión correctas. Las reglas de notificación generadas creadas con la Ayuda de AD FS se pueden agregar manualmente a través de la consola de administración de AD FS o con PowerShell. La Ayuda de AD FS generará los scripts de PowerShell necesarios que deben ejecutarse.  

1. Ejecute **la ayuda de Generar** notificaciones en AD FS  y copie el script de transformación de notificaciones de PowerShell con la opción Copiar en la esquina superior derecha del script.
2. Pegue el PowerShell generado en lo siguiente:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Ejecute el script completado.
4.  Compruebe que hay dos confianzas de usuario de confianza presentes; uno para todo el mundo y otro para BF.
5.  Haga una copia de seguridad de sus confianzas [con estos pasos.](#backup) Guárdelo con el nombre **FFAndWorldwide**.
6.  Complete la migración de back-end y compruebe que AD FS aún funciona durante el proceso de migración.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperación ante desastres de AD FS (base de datos WID)

Para restaurar la granja de AD FS en una herramienta de restauración rápida de [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres, debe aprovecharse. Por lo tanto, la herramienta debe descargarse y antes del inicio de la migración, se debe crear una copia de seguridad y almacenarla de forma segura. En este ejemplo (entornos DEA) se han ejecutado los siguientes comandos para realizar una copia de seguridad de la granja de servidores:

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

4. Almacene la copia de seguridad de forma segura en el destino deseado. 

### <a name="restore-an-ad-fs-farm"></a>Restauración de una granja de servidores de AD FS

Si se ha fallado completamente la granja de servidores y no hay ninguna forma de volver a la granja de servidores antigua, haga lo siguiente. 

1. Mueva la copia de seguridad generada y almacenada anteriormente al nuevo servidor principal de AD FS.
2. Ejecute el siguiente `Restore-ADFS` comando de PowerShell. Si es necesario, importe el certificado SSL de AD FS de antemano.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Apunte los nuevos registros DNS o el equilibrador de carga a los nuevos servidores de AD FS.

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
