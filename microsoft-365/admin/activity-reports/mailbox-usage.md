---
title: Centro de administración de Microsoft 365 informes de uso del buzón
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Obtenga información sobre cómo obtener el informe de uso del buzón para averiguar los niveles de actividad de los usuarios con un buzón de usuario, así como información de almacenamiento y cuota para cada uno.
ms.openlocfilehash: c30cb6e9cc593aba14902d81904f3e765faa4231
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663050"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso del buzón

El **informe de uso del buzón de correo** proporciona información sobre los usuarios con un buzón de usuario y el nivel de actividad de cada uno en función del envío, lectura, creación de citas, envío de reunión, aceptación de reunión, rechazo de reunión y cancelación de la actividad de reunión. También proporciona información sobre cuánto almacenamiento ha consumido cada buzón de usuario y cuántos de ellos se acercan a las cuotas de almacenamiento. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Cómo obtener el informe de uso del buzón

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. Seleccione **Ver más** en **Actividad de correo electrónico**. 
3. En la lista desplegable **Actividad de correo electrónico**, seleccione **Uso del buzón de** **Exchange**\>.

## <a name="interpret-the-mailbox-usage-report"></a>Interpretar el informe de uso del buzón

Para obtener una vista del **Uso del buzón** de la organización, consulte los gráficos **Buzón**, **Almacenamiento** y **Cuota**.
  
:::image type="content" alt-text="Informe de uso del buzón de correo." source="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png" lightbox="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png":::

Puede visualizar el informe **Uso del buzón** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe). Los datos de cada informe suelen cubrir hasta las últimas 24 a 48 horas.

El gráfico **Buzón de correo** muestra el número total de buzones de usuario de su organización y el número total que están activos en cualquier día determinado del período de informes. Un buzón de usuario se considera activo si tenía un correo electrónico de envío, lectura, creación de citas, envío de reunión, aceptación de reunión, rechazo de reunión y cancelación de la actividad de reunión.

El gráfico **Almacenamiento** muestra la cantidad de almacenamiento usado en su organización. El gráfico de almacenamiento no incluye buzones de archivo. Para obtener más información sobre el archivado de expansión automática, consulte [Introducción al archivado de expansión automática en Microsoft 365](../../compliance/autoexpanding-archiving.md).

El gráfico **Cuota** muestra el número de buzones de usuario en cada categoría de cuota. Hay cuatro categorías de cuota: 
- Bueno: el número de usuarios cuyo almacenamiento usado está por debajo de la cuota de "advertencia de problema".
- Advertencia: el número de usuarios cuyo almacenamiento usado está en o por encima de la cuota de "advertencia de problema", pero por debajo de la cuota "prohibir envío".
- No se puede enviar: el número de usuarios cuyo almacenamiento usado está en o por encima de la cuota de prohibición de envío, pero por debajo de la cuota de prohibición de envío y recepción.
- No se puede enviar o recibir: el número de usuarios cuyo almacenamiento usado está en la cuota "prohibir envío/recepción" o superior.

En el gráfico Buzón, el eje Y es el número de buzones de usuario. 

En el gráfico Almacenamiento, el eje Y es la cantidad de almacenamiento que usan los buzones de usuario de la organización.

El eje X de los gráficos Buzón y Almacenamiento es el intervalo de fechas seleccionado para este informe específico.

En el gráfico Cuota, el eje Y es el número de buzones de usuario en cada cuota de almacenamiento. Y el eje X es la categoría de cuota.

Puede filtrar los gráficos que ve seleccionando un elemento en la leyenda.

En la tabla se muestra un desglose del uso del buzón en el nivel de usuario. Puede agregar columnas adicionales a la tabla. 

|Item|Descripción|
|:-----|:-----|
|Nombre de usuario |La dirección de correo electrónico del usuario. |
|Nombre para mostrar  |Nombre completo del usuario. |
|Deleted |Buzón cuyo estado actual se elimina, pero que estaba activo durante alguna parte del período de informes del informe.|
|Fecha de eliminación |La fecha en que se eliminó el buzón. |
|Fecha de creación | La fecha en que se creó el buzón.  |
|Fecha de la última actividad | La fecha en que el buzón tenía por última vez una actividad de envío o lectura de correo electrónico.   |
|Número de elementos|Número total de elementos en el buzón de correo. |
|Almacenamiento usado (MB)|Almacenamiento total usado. |
|Recuento del elemento eliminado|Número total de elementos eliminados en el buzón de correo. |
|Tamaño del elemento eliminado (MB)|Tamaño total de todos los elementos eliminados en el buzón. |
|Cuota de advertencia de problema (MB)|Límite de almacenamiento cuando el propietario del buzón recibirá una advertencia de que está a punto de alcanzar la cuota de almacenamiento.  |
|Prohibir cuota de envío (MB)|Límite de almacenamiento cuando el buzón ya no puede enviar correos electrónicos. |
|Prohibir la cuota de recepción de envío (MB)|Límite de almacenamiento cuando el buzón ya no puede enviar ni recibir correos electrónicos. |
|Cuota de elementos recuperables (MB)|Límite de almacenamiento para los elementos recuperables (eliminados) del buzón cuando el buzón ya no puede eliminar correos electrónicos. |
|Tiene archivo|Muestra si el buzón tiene habilitado un archivo en línea. |


Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Ocultar los detalles del usuario en la sección de informes** de [Informes de actividad en el Centro de administración de Microsoft 365](activity-reports.md.

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> :::image type="content" alt-text="Informe de uso del buzón: elija columnas." source="../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png":::

También puede exportar los datos del informe a un archivo .csv de Excel; para ello, seleccione el vínculo **Exportar** . 