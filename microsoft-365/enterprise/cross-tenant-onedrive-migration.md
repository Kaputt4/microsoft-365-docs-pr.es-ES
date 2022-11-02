---
title: Migración entre inquilinos de OneDrive
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Migración entre inquilinos de OneDrive
ms.openlocfilehash: 0088e7088dd67fd3a4d189eacdacde5362d0ff73
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68814107"
---
# <a name="cross-tenant-onedrive-migration"></a>Migración entre inquilinos de OneDrive

>[!Note]
> La información de este artículo hace referencia a la **migración entre inquilinos de OneDrive**. Para la migración de buzones de correo, consulte [Migración de buzones entre inquilinos](/microsoft-365/enterprise/cross-tenant-mailbox-migration).

## <a name="overview"></a>Información general

Durante las fusiones o desinversiones, normalmente se necesita la capacidad de mover cuentas de OneDrive de los usuarios a un nuevo inquilino de Microsoft 365. Con la migración entre inquilinos de OneDrive, los administradores de inquilinos pueden usar herramientas conocidas como *PowerShell de SharePoint Online* para realizar la transición de los usuarios a su nueva organización.

Los administradores de SharePoint de dos inquilinos independientes pueden usar el cmdlet *Set-SPOCrossTenantRelationship* para establecer una relación de organización y el comando *Start-SPOCrossTenantUserContentMove* para comenzar a mover OneDrive entre inquilinos.

Se pueden programar hasta 4000 cuentas de OneDrive para la migración de antemano en un momento dado. Una vez programadas, las migraciones se producen sin que los datos del usuario salgan de la nube de Microsoft 365 y con una interrupción mínima, lo que requiere solo unos minutos en los que OneDrive de un usuario será de solo lectura. Una vez completadas las migraciones, se coloca una redirección en la ubicación de OneDrive original del usuario, por lo que los vínculos a archivos y carpetas pueden seguir funcionando en la nueva ubicación. 

Esta característica no es compatible con los usuarios de la nube para administración pública, incluidos GCC, Consumidor, GCC High o DoD.

## <a name="licensing"></a>Licencias

**La migración de datos de usuario entre inquilinos** está disponible como complemento a los siguientes planes de suscripción de Microsoft 365 para Enterprise Agreement clientes. Las licencias de usuario son por migración (tarifa de una sola vez). Póngase en contacto con el equipo de su cuenta de Microsoft para obtener más información.
 
Microsoft 365 Empresa Básico/Business Standard/Business Premium/F1/F3/E3/A3/E5/A5; Office 365 F3/E1/A1/E3/A3/E5/A5; Exchange Online; SharePoint Online; OneDrive para la Empresa.


## <a name="prerequisites-and-settings"></a>Requisitos previos y configuración

- **Microsoft Office SharePoint Online PowerShell**. Confirme que tiene instalada la versión más reciente. [Descarga del Shell de administración de SharePoint Online desde el Centro de descarga oficial de Microsoft](/download/details.aspx?id=35588)

- **Desactive el cifrado del servicio con la clave de cliente habilitada.** Confirme que el inquilino de OneDrive de origen **no** tiene el cifrado de servicio con la clave de cliente de Microsoft Purview habilitada. Si está habilitado en el inquilino de origen, se producirá un error en la migración. [Más información sobre el cifrado de servicios con la clave de cliente de Microsoft Purview](/microsoft-365/compliance/customer-key-overview)

- Las cuentas de OneDrive de origen deben establecerse en Lectura y escritura. Si se establece en Solo lectura, se producirá un error.

## <a name="pre-create-target-accounts"></a>Creación previa de cuentas de destino

- Asegúrese de que todos los usuarios y grupos identificados para la migración se han creado previamente en el inquilino de destino.
- Asigne las licencias adecuadas a cada usuario del inquilino de destino.
- Se recomienda restringir la creación de sitios de OneDrive en el inquilino de destino para evitar que los usuarios creen sitios de OneDrive. Si ya existe un sitio de OneDrive para el usuario en el inquilino de destino, se producirá un error en la migración.  No se puede sobrescribir un sitio existente.

>[!Note]
>Para obtener más información sobre cómo restringir la creación de sitios de OneDrive, consulte [Deshabilitar la creación de OneDrive para algunos usuarios](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users).


## <a name="path-size-limits"></a>Límites de tamaño de ruta de acceso

Microsoft limita el número de caracteres de una ruta de acceso a no superar los 400 caracteres. Este es el límite de ruta de acceso completa, no solo el nombre de archivo. Al planear las migraciones, revise la longitud de los nombres de dirección URL de OneDrive en el inquilino de destino. El error suele producirse cuando los archivos o las rutas de acceso de carpeta del origen, combinados con la dirección URL de OneDrive en el destino superan el límite de ruta de acceso de 400 caracteres. 

Una migración detectará si ha superado el límite de caracteres. Trabaje con el propietario del sitio para actualizar la estructura de directorios de archivos o carpetas para reducir las longitudes de la ruta de acceso del archivo.

Se aceptará cualquier dirección URL legal al crear el mapa de identidades de origen a destino para las migraciones. En este momento, los nombres de usuario o direcciones URL que contienen un carácter apóstrofo ( **'** ) en un nombre de usuario o dirección URL producirán un error de "carácter no válido" al intentar la migración.

>[!Tip]
>Se recomienda mantener los nombres de dirección URL de OneDrive de destino cortos para evitar superar el límite de caracteres.

## <a name="onedrive-account-size-limits"></a>Límites de tamaño de cuenta de OneDrive
Cada cuenta de OneDrive puede tener un máximo de 2 TB de contenido o 1 millón de elementos.


## <a name="permissions"></a>Permisos

Todos los usuarios y grupos incluidos en el archivo de asignación de identidades que cargó en el inquilino de destino mantendrán permisos en el inquilino de destino relacionados con el sitio de OneDrive migrado.

## <a name="legal-holds"></a>Retenciones legales
Las cuentas de OneDrive con una directiva de suspensión aplicada se bloquearán de la migración.
Para migrar estas cuentas de OneDrive, quite la directiva de suspensión, migre y vuelva a aplicar la suspensión según sea necesario en el inquilino de destino.

## <a name="shared-files"></a>Archivos compartidos

Una vez migrada una cuenta de OneDrive, cualquier persona que haga clic en un vínculo compartido a la ubicación anterior se redirigirá a la nueva, siempre que todavía tenga acceso al destino. 

Esas redireccionamientos permanecen hasta que se desaprovisiona el inquilino de origen. El administrador también puede quitar de forma selectiva las redirecciones de sitio a sitio.

## <a name="how-does-it-work"></a>¿Cómo funciona?

- **Paso 1:** [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md).  
- **Paso 2:** [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- **Paso 3:** [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- **Paso 4:** [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- **Paso 5:** [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- **Paso 6:** [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- **Paso 7:** [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)

## <a name="step-1-connect-to-source-and-target-tenants"></a>Paso 1: [Conectarse a inquilinos de origen y de destino](cross-tenant-onedrive-migration-step1.md)