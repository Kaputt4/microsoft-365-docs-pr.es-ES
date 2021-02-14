---
title: 'Informes de Microsoft 365 en el Centro de administración: actividad de SharePoint'
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: Obtenga el informe de uso de actividad de SharePoint para conocer la actividad de cada usuario de SharePoint, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: b0c628300647e83889e273268bef7abd9e337ed4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948873"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de SharePoint

Como administrador de Microsoft 365, el panel **informes** muestra la información general sobre la actividad en varios productos de la organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Consulte los informes de actividades en el Centro de administración de [Microsoft 365.](activity-reports.md)
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar SharePoint consultando su interacción con los archivos. También le ayuda a entender el nivel de colaboración actual consultando el número de archivos compartidos.
  
> [!NOTE]
> Algunas funciones se irán introduciendo gradualmente. Esto significa que es posible que todavía no pueda ver esta característica o que la vea con un aspecto diferente a como se describe en los artículos de ayuda. Pero no se preocupe: si aún no la ve, estará disponible próximamente. 
  
Si quiere ver cuál es la actividad que tiene lugar en cada sitio de SharePoint, así como el uso de almacenamiento, vea el [informe de uso del sitio de SharePoint](sharepoint-site-usage.md).
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>¿Cómo puedo obtener acceso al informe de actividad de SharePoint?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Actividad de **SharePoint** \> .
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Interpretar el informe de actividad de SharePoint

Puede obtener una vista de la actividad de SharePoint consultando las vistas **Archivos** y **Usuarios**.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|Elemento|Description|
|:-----|:-----|
|1.  <br/> |Puede visualizar el **informe de actividad de SharePoint** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Archivos** le ayuda a entender el número de usuarios con licencia que llevan a cabo interacciones de archivo con archivos almacenados en los sitios de SharePoint.  <br/> |
|4.  <br/> |La vista **Páginas** muestra el número de páginas únicas visitadas por usuarios.  <br/> |
|5.  <br/> |La vista **Usuarios** le ayuda a comprender la tendencia en el número de usuarios activos. Un usuario se considera activo si ha ejecutado una actividad de archivo (guardar, sincronizar, modificar o compartir) o ha visitado una página dentro del período de tiempo especificado.  <br/> NOTA: Una actividad de archivo puede producirse varias veces para un único archivo, pero solo se contará como un archivo activo. Por ejemplo, puede guardar y sincronizar el mismo archivo varias veces durante un período de tiempo especificado, pero solo contará como un único archivo activo y como un único archivo sincronizado en los datos.           |
|6.  <br/> | En el gráfico **Archivos**, el eje Y es el recuento de archivos únicos que guardó, sincronizó, modificó o compartió un usuario.  <br/>  En el gráfico **Usuarios**, el eje Y es el número de usuarios únicos que ejecutaron una interacción de archivo (guardar, sincronizar, modificar o compartir) en un sitio.  <br/>  En el gráfico **Páginas**, el eje X es el número de páginas únicas visitadas por los usuarios.  <br/>  En todos los gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo,  en el gráfico Archivos, seleccione **Vista** o edición, Sincronizado **,** Compartido internamente o Compartido externamente para ver solo la información relacionada con cada uno.  Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> |
|8.  <br/> | En la tabla se muestra un desglose de las actividades en el nivel de cada sitio.  <br/>  <br/> **Nombre** de usuario es la dirección de correo electrónico del usuario que realizó la actividad en el sitio de SharePoint.  <br/> La **fecha de la última actividad (UTC)** es la última fecha en que se ha llevado a cabo una actividad de archivo o se ha visitado una página para el intervalo de fechas seleccionado. Para ver las actividades efectuadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> ![Seleccionar una fecha específica en el gráfico](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.  <br/>  **Archivos vistos o editados** es el número de archivos que el usuario cargó, descargó, modificó o visualizó.  <br/>  **Los archivos sincronizados** es el número de archivos que se han sincronizado desde el dispositivo local de un usuario al sitio de SharePoint.  <br/>  **Los archivos compartidos internamente** es el recuento de archivos que se han compartido con usuarios de la organización o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/>  **Compartidos de forma externa** es el número de archivos que se han compartido con usuarios fuera de la organización.  <br/>  **Las páginas visitadas** son las visitas a páginas únicas por el usuario.  <br/>  **Eliminados** indica que se ha quitado la licencia del usuario.  <br/>  **NOTA:** La actividad de un usuario eliminado se seguirá visualizando en el informe siempre que se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna Eliminado puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> **fecha eliminado** es la fecha en la que se quitó la licencia del usuario.  <br/>  **El producto asignado** son los productos de Microsoft 365 con licencia para el usuario.  <br/> |
|9.  <br/> |Seleccione el **icono Administrar columnas** administrar columnas para agregar o quitar columnas del ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) informe.  <br/> |
|10.  <br/> |También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

