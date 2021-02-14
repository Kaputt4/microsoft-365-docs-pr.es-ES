---
title: 'Informes de Microsoft 365 en el Centro de administración: uso de OneDrive para la Empresa'
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Obtenga información sobre el informe de uso de OneDrive para la Empresa sobre el número total de archivos y almacenamiento usados en toda la organización. '
ms.openlocfilehash: e08dff4e763479afa197377d37e474384492c012
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948930"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso de OneDrive para la Empresa

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, la tarjeta de OneDrive en el panel le ofrece una vista general del valor que obtiene de OneDrive para la Empresa en cuanto al número total de archivos y almacenamiento que se usa en su organización. Después, puede explorarlo en profundidad para comprender las tendencias de las cuentas activas de OneDrive, con cuántos archivos interactúan los usuarios, así como el almacenamiento usado. También le ofrece los detalles de cada usuario de OneDrive.
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de OneDrive?

1. En el centro de administración, vaya a **Uso** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">de informes.</a>

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Uso de **OneDrive.** \>  
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretar el informe de uso de OneDrive

Puede obtener una vista del uso de OneDrive para la Empresa consultando las vistas **Cuentas**, **Archivos** y **Almacenamiento**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Elemento|Description|
|:-----|:-----|
|1.  <br/> |Consulte el informe **Uso de OneDrive** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas. <br/>|
|3.  <br/> |La vista **Cuentas** muestra la tendencia en el número de cuentas de OneDrive totales y activas. Las "Cuentas activas" son las que los usuarios usan para ver, modificar, cargar, descargar, compartir o sincronizar archivos.  <br/> |
|4.  <br/> |La **vista** Archivos muestra el número de archivos totales y activos. Un archivo se considera activo si se ha guardado, sincronizado, modificado o compartido en un período de tiempo específico.  <br/> NOTA: Una actividad de archivo puede producirse varias veces para un único archivo, pero solo se contará como un archivo activo. Por ejemplo, puede guardar y sincronizar el mismo archivo varias veces durante un período de tiempo especificado, pero solo contará como un único archivo activo y como un único archivo sincronizado en los datos.           |
|5.  <br/> |La vista **Almacenamiento** muestra la tendencia de la cantidad de almacenamiento que esté usando en OneDrive. Si desea comprobar los límites de almacenamiento, consulte Comprobar si un usuario tiene el límite de almacenamiento predeterminado [o un límite específico.](https://docs.microsoft.com/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit)  <br/> NOTA: El tamaño incluye cualquier versión y metadatos asociados con los archivos.           |
|6.  <br/> | En el gráfico **Cuentas**, el eje Y es el número de cuentas de OneDrive.  <br/>  En el gráfico **Archivos**, el eje Y es el número de archivos almacenados en OneDrive.  <br/>  En el gráfico **Almacenamiento**, el eje Y es la cantidad de almacenamiento que se usa para las cuentas de OneDrive.  <br/>  En todos los gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **Archivos,** seleccione **Archivos totales** o **Archivos activos.** En el **gráfico Cuentas,** seleccione **Cuentas totales** o **Cuentas activas.** O bien, **en el gráfico** Almacenamiento, seleccione Almacenamiento **usado.** Si cambia su selección, no se modificará la información de la tabla.  <br/> |
|8.  <br/> | En la tabla se muestra un desglose de los datos de cada OneDrive de usuario. Para que un usuario aparezca en la tabla, debe tener asignada una licencia de producto que incluya OneDrive y la opción SharePoint Online activada. El usuario también debe haber iniciado sesión con en cliente de sincronización de OneDrive o haber consultado su OneDrive con un explorador web.  <br/>  Si la cuenta de OneDrive ha tenido actividad de archivos, tendrá la última fecha en la que se ha realizado la actividad de archivos. Las filas de la tabla se ordenan por el valor **Fecha de última actividad** para que las OneDrive con la actividad de archivos más reciente se muestran en la parte superior de la lista.  <br/>  Puede agregar o quitar columnas de la tabla.  <br/> ![Opciones de columna](../../media/onedriveusage-columns.png)  <br/> **La** dirección URL es la dirección web del OneDrive del usuario.  <br/> **Eliminada** es el estado de eliminación de la OneDrive. Pueden pasar al menos 7 días hasta que las cuentas se marquen como eliminadas.  <br/> **Propietario** es el nombre de usuario del administrador principal del OneDrive.  <br/> **El nombre principal del** propietario es la dirección de correo electrónico del propietario de OneDrive.  <br/> **Fecha de última actividad (UTC)** es la última fecha en que se ha realizado una actividad de archivos en la OneDrive. Si la OneDrive no ha tenido actividad de archivos, el valor se mostrará en blanco.  <br/> **Archivos** es el número de archivos que hay en el OneDrive.  <br/> **Archivos activos** es el número de archivos activos que hay en el período de tiempo.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en OneDrive. Los usuarios eliminados seguirán apareciendo en los informes durante 180 días.<br/>**Almacenamiento usado (MB)** es la cantidad de almacenamiento que el OneDrive usa en MB. <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo se ocultan los** detalles del nivel de usuario? en los informes de actividades del Centro de administración [de Microsoft 365.](activity-reports.md)  <br/> |
|9.  <br/> |Seleccione el **icono Administrar columnas** administrar columnas para agregar o quitar columnas del ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) informe.  <br/> |
|10.  <br/> |También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los OneDrive y podrá efectuar una ordenación y un filtrado sencillos para llevar a cabo análisis posteriores. Si tiene menos de 2000 OneDrive de usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 OneDrive de usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> NOTA: Cuando los datos se exportan a un archivo de Excel, la  fecha en que se generó el informe de contenido se refleja en el archivo de la columna Datos.  <br/> |
|||
   
