---
title: Informes de Microsoft 365 en el Centro de administración - Actividad de OneDrive para la Empresa
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
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Obtenga el informe de uso de OneDrive para su organización y conozca la actividad de cada usuario de OneDrive, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: dd5ac1c52d2226b12c75dc92c3407012251a90da
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948933"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Informes de Microsoft 365 en el Centro de administración - Actividad de OneDrive para la Empresa

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar OneDrive consultando su interacción con los archivos en OneDrive. También le ayuda a entender el nivel de colaboración actual observando el número de archivos compartidos.
  
> [!NOTE]
> Parte de las funciones se introducen gradualmente. Esto significa que es posible que todavía no pueda ver esta característica o que la vea con un aspecto diferente a como se describe en los artículos de ayuda. Pero no se preocupe, estará disponible próximamente. 
  
Si quiere conocer la cantidad de actividad que tiene lugar en cada cuenta de OneDrive y el uso de almacenamiento, puede consultar el [informe de uso de OneDrive](onedrive-for-business-usage.md).
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>¿Cómo puedo tener acceso al informe de actividades de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Actividad de **OneDrive.** \> 
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar el informe de actividades de OneDrive para la Empresa

Puede obtener una vista de la actividad de OneDrive para la Empresa consultando las vistas **Archivos** y **Usuarios**. 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|Elemento|Description|
|:-----|:-----|
|1.  <br/> |Puede visualizar el informe de **actividad de OneDrive para la Empresa** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 o 48 horas. <br/>|
|3.  <br/> |La vista **Archivos** le ayuda a entender el número de usuarios con licencia que realizan interacciones de archivo con cualquier cuenta de OneDrive.  <br/> |
|4.  <br/> |La vista **Usuarios** le ayuda a comprender la tendencia en el número de usuarios activos de OneDrive. Un usuario se considera activo si ha ejecutado una actividad de archivo (guardar, sincronizar, modificar o compartir) dentro del período de tiempo especificado.  <br/> NOTA: Una actividad de archivo puede producirse varias veces para un único archivo, pero solo se contará como un archivo activo. Por ejemplo, puede guardar y sincronizar el mismo archivo varias veces durante un período de tiempo especificado, pero solo contará como un único archivo activo y como un único archivo sincronizado en los datos.           |
|5.  <br/> | En el gráfico **Archivos**, el eje Y es el número de archivos únicos que cualquier usuario guardó, sincronizó, modificó o compartió.  <br/>  En el gráfico **Usuarios**, el eje Y es el número de usuarios únicos que ejecutaron interacciones de archivo (guardar, sincronizar, modificar o compartir) en cualquier cuenta de OneDrive.  <br/>  En todos los gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **Archivos,** seleccione **Ver, editar** o **Sincronizar** para ver solo la información relacionada con cada uno de ellos. El hecho de cambiar esta selección no cambia la información de la tabla de cuadrícula.  <br/> |
|7.  <br/> | En la tabla, se muestra un desglose de los datos en el nivel de usuario. Puede agregar o quitar columnas de la tabla.   <br/>  **Nombre** de usuario es el nombre de usuario del propietario de la cuenta de OneDrive.  <br/> **Fecha de la última actividad (UTC)** es la última fecha en que se ha realizado una actividad de archivo en la cuenta de OneDrive para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> ![Seleccionar una fecha específica en el gráfico](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.  <br/> **Archivos vistos o editados** es el número de archivos que el usuario cargó, descargó, modificó o visualizó.  <br/> **Archivos sincronizados** es el número de archivos que se han sincronizado desde el dispositivo local de un usuario a la cuenta de OneDrive.  <br/> **Los archivos compartidos** internamente es el número de archivos que se han compartido con usuarios de la organización o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> **Compartidos de forma externa** es el número de archivos que se han compartido con usuarios fuera de la organización.  <br/> **Eliminados** indica que se ha quitado la licencia del usuario.  <br/> NOTA: La actividad de un usuario eliminado seguirá a la vista en un informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna **Eliminado** puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.<br/>**fecha eliminado** es la fecha en la que se quitó la licencia del usuario.  <br/> **Los productos asignados** son los productos de Microsoft 365 con licencia para el usuario.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo ocultar los** detalles del nivel de usuario? en los informes de actividad en el Centro de administración de Microsoft [365.](activity-reports.md)  <br/> |
|8.  <br/> |Seleccione el **icono Administrar columnas** administrar columnas para agregar o quitar columnas del ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) informe.  <br/> |
|9.  <br/> |También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

