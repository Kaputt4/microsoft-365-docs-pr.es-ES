---
title: Paso 5 de migración de datos de usuarios entre inquilinos de OneDrive
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Paso 5 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 5e8706b88b255132bb4db36cd6010668b36b3f26
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807681"
---
# <a name="step-5-identity-mapping"></a>Paso 5: Asignación de identidades

Este es el paso 5 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)
- Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- **Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)**
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)

## <a name="create-the-identity-mapping-file"></a>Creación del archivo de asignación de identidades 

En este paso del proceso de migración entre inquilinos, va a crear un único archivo CSV (valores separados por comas) que contiene la asignación de los usuarios y grupos del inquilino de origen a sus usuarios y grupos correspondientes en el inquilino de destino.

Se recomienda tomarse el tiempo necesario para comprobar las asignaciones, asegurándose de que sean precisas antes de iniciar las migraciones al inquilino de destino.

Hay una relación uno a uno en el archivo de asignación de identidades.  No se puede asignar el mismo usuario a varios usuarios en el inquilino de destino. Por ejemplo, si tiene instancias en las que el administrador es el propietario de varias cuentas de OneDrive, se debe cambiar la propiedad para que coincida con el usuario correspondiente que desea migrar de Origen a Destino.  Si no lo hace, esos archivos de cuenta no se migrarán.

**Ejemplo:** En este ejemplo, el administrador posee varias cuentas de OneDrive.

|Propietario del inquilino de origen |Usuario de inquilino de destino|
|:-----|:-----|
|admin@source.com  |new.userA@target.com|
|admin@source.com |new.userB@target.com|
|admin@source.com |new.userC@target.com|


La migración entre inquilinos admite este escenario:

**Ejemplo**

|Propietario del inquilino de origen|Usuario de inquilino de destino|
|:-----|:-----|
|userA@source.com|new.userA@target.com|
|userB@source.com|new.userB@target.com|
|userC@source.com|new.userC@target.com|


### <a name="create-the-csv-file"></a>Creación del archivo CSV

Hay seis columnas necesarias en el archivo CSV. Los tres primeros son los valores de origen, cada uno de los cuales proporciona detalles sobre dónde se encuentran los datos actualmente. Las tres columnas restantes son la información correspondiente en el inquilino de destino. Las seis columnas deben tenerse en cuenta en el archivo. Cree el archivo en Excel y guárdelo como un archivo .csv. 

Los usuarios y grupos se incluyen en el mismo archivo. En función de si es un usuario o grupo, lo que escriba en la columna es diferente. En cada una de las columnas, escriba valores como se muestra en los ejemplos.  **NO incluya encabezados de columna.**

|Column|User|Grupo|
|:-----|:-----|:-----|
|1|User|Grupo|
|2|SourceTenantCompanyID|SourceTenantCompanyID|
|3|SourceUserUpn|SourceGroupObjectID|
|4|TargetUserUpn|TargetGroupObjectID|
|5|TargetUserEmail|GroupName|
|6|UserType|GroupType|


>[!Important]
>NO incluya encabezados de columna en el archivo CSV.  En los ejemplos siguientes se incluyen solo con fines ilustrativos. 

Usuarios Escriba los valores como se muestra en este ejemplo para invitados:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-columns.png" alt-text="formato que se va a usar para asignar usuarios":::

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-example.png" alt-text="ejemplo de csv para los usuarios":::

**Grupos**. Escriba los valores como se muestra en este ejemplo para invitados:
</br>
:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-groups-columns.png" alt-text="formato del archivo csv para grupos":::
</br>

*Ejemplo*:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-group-example.png" alt-text="ejemplo de adición de grupos a un archivo csv":::


**Usuarios invitados**. Puede asignar cuentas de invitado del inquilino de origen a cuentas miembro del inquilino de destino. También puede asignar una cuenta de invitado del origen a una cuenta de invitado en el destino si el invitado se ha creado anteriormente. Escriba los valores como se muestra en este ejemplo para invitados:
</br>

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-guests.png" alt-text="ejemplo csv al asignar un invitado a un miembro":::

*Ejemplo de varios usuarios en un archivo CSV:* </br>

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-migration-csv-users-groups.png" alt-text="ejemplo de usuarios y grupos en el archivo de asignación":::

## <a name="obtain-the-source-tenant-company-id"></a>Obtener el identificador de empresa del inquilino de origen
Para obtener el identificador de empresa del inquilino de origen:

1. Inicie sesión como Administración en el [Azure Portal](https://ms.portal.azure.com/)
2. Seleccione o busque **Azure Active Directory**.
3. Desplácese hacia abajo en el panel izquierdo y seleccione **Propiedades**.
4. Busque el **campo Id**. de inquilino. El identificador de inquilino necesario estará en ese cuadro.

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-azure-tenant-id.png" alt-text="obtención del identificador de inquilino de origen":::



## <a name="to-obtain-source-group-object-id"></a>Para obtener el identificador de objeto de grupo de origen:

1. Inicie sesión en el inquilino de origen como Administración en [grupos de Azure](https://ms.portal.azure.com).
2. Busque los grupos necesarios.
3. Seleccione la instancia de Group necesaria y, a continuación, **Copie en el Portapapeles**.  Pegue este valor en la columna sourceGroupObjectId del archivo CSV de asignación.
4. Si tiene varios grupos que asignar, repita estos pasos para cada grupo.

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-source-group-objectid.png" alt-text="obtención del identificador de objeto de grupo de origen":::

### <a name="to-obtain-target-group-object-id"></a>Para obtener el identificador de objeto de grupo de destino:

1. Inicio de sesión en el inquilino de destino como Administración en [grupos de Azure](https://ms.portal.azure.com)
2. Busque los grupos necesarios.
3. Seleccione la instancia de grupo necesaria y, a continuación, **Copie en el Portapapeles**. Pegue este valor en la columna targetGroupObjectId del archivo CSV de asignación.
4. Si tiene varios grupos que asignar, repita el proceso anterior para obtener esos targetGroupObjectId específicos.
5. Para GroupName, use el mismo identificador que *targetGroupObjectId* que obtuvo.
 
:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-target-group-objectid.png" alt-text="cómo obtener el identificador de objeto de destino":::

## <a name="upload-the-identity-map"></a>Carga del mapa de identidades

Una vez preparado el archivo de asignación de identidades, el administrador de SharePoint en el inquilino de destino carga el archivo en SharePoint. Esto permitirá que la asignación de identidades se produzca automáticamente como parte de la migración entre inquilinos.

>[!Important]
>Antes de ejecutar el comando *Add-SPOTenantIdentityMap –IdentityMapPath* , guarde y cierre el archivo de identitymap.csv en el escritorio, OneDrive o SharePoint. Si el archivo permanece abierto, recibirá el siguiente error.
>
>*Add-SPOTenantIdentityMap: el proceso no puede acceder al archivo "C:\Users\myuser\Test-Identity-Map.csv" porque lo usa otro proceso.*


1. Para cargar la identidad Map en el inquilino de destino, ejecute el siguiente comando.  Para *-IdentityMapPath*, proporcione la ruta de acceso completa y el nombre de archivo del archivo CSV de asignación de identidades.


```powershell
Add-SPOTenantIdentityMap –IdentityMapPath <identitymap.csv>  

```



>[!Important]
>Si realiza o necesita realizar cambios en el mapa de identidades durante el ciclo de vida de la migración, debe ejecutar el comando *Add-SPOTenantIdentityMap –IdentityMapPath <identitymap.csv>* **cada vez** que se realice un cambio para asegurarse de que esos cambios se aplican a la migración.

La carga de cualquier nuevo mapa de identidad sobrescribirá el actual. Asegúrese de que cualquier revisión o adición incluya TODOS los usuarios y grupos para la migración completa. El mapa de identidades siempre debe incluir a todos los usuarios que quiera migrar.

Para ver las entradas de asignación en el archivo de asignación de identidades de un usuario determinado, use el comando *Get-SPOTenantIdentityMappingUser* con Field como *SourceUserKey* y Value como el UPN del usuario que va a mover. 

**Ejemplo:**

```powershell

get-spoTenantIdentityMappingUser -Field SourceUserKey -Value usera@Contoso.onmicrosoft.com 
```

## <a name="verify-cross-tenant-compatibility-status"></a>Comprobación del estado de compatibilidad entre inquilinos

Antes de iniciar las migraciones entre inquilinos, asegúrese de que ambos esquemas de base de datos de SharePoint estén actualizados y sean compatibles entre el origen y el destino.

Para realizar esta comprobación, ejecute el siguiente cmdlet en el inquilino de origen.

```Powershell

Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL [Target tenant hostname]

Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL https://m365x12395529-my.sharepoint.com
```

- Si los inquilinos son compatibles, puede continuar con el siguiente paso para iniciar migraciones entre inquilinos.  
- Si los inquilinos no son compatibles, los inquilinos tendrán que ser revisados o actualizados para garantizar la compatibilidad.

>[!Note]
>Se recomienda esperar un período de 24 horas. Si los inquilinos siguen informando como *incompatibles*, póngase en contacto con el soporte técnico. 

>[!Note]
>Se recomienda realizar la comprobación del estado de compatibilidad con frecuencia y antes de iniciar CUALQUIER instancia de migraciones entre inquilinos. Si los inquilinos no son compatibles, esto puede dar lugar a errores en las migraciones entre inquilinos.


## <a name="step-6-start-a-onedrive-cross-tenant-migration"></a>Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)