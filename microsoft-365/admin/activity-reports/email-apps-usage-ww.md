---
title: 'Microsoft 365 Informes en el Centro de administración: uso de aplicaciones de correo electrónico'
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
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Obtén información sobre cómo obtener el informe de uso de aplicaciones de correo electrónico para saber acerca de las aplicaciones de correo electrónico que se conectan a Exchange Online y la Outlook versión que usan los usuarios.
ms.openlocfilehash: 9da0900723928fe091e7415482ba2cb50ff4f5f1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553297"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365 Informes en el Centro de administración: uso de aplicaciones de correo electrónico

El panel Microsoft 365 **informes le** muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de correo electrónico, puedes ver cuántas aplicaciones de correo electrónico se conectan a Exchange Online. También puedes ver la información de versión de las aplicaciones de Outlook que usan los usuarios, lo que te permitirá realizar un seguimiento de los usuarios que usan versiones no admitidas para instalar versiones compatibles de Outlook.
  
## <a name="how-to-get-to-the-email-apps-report"></a>Cómo llegar al informe de aplicaciones de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. Seleccione **Ver más en** Actividad de correo **electrónico**. 
3. En la **lista desplegable Actividad** de correo electrónico, seleccione **Exchange** Uso de aplicaciones de \> **correo electrónico**.
  
## <a name="interpret-the-email-apps-report"></a>Interpretar el informe de aplicaciones de correo electrónico

Para obtener una vista de la actividad de las aplicaciones de correo electrónico, consulte los gráficos **usuarios** **y** clientes. 
  
![Clientes de correo electrónico usados.](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|Item|Descripción|
|:-----|:-----|
|1.  <br/> |El **informe de uso de aplicaciones** de correo electrónico se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Usuarios** muestra el número de usuarios únicos que se han conectado a Exchange Online mediante cualquier aplicación de correo electrónico.  <br/> |
|4.  <br/> |La vista **Aplicaciones** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado.  <br/> |
|5.  <br/> |La **vista** Versiones muestra el número de usuarios únicos para cada versión de Outlook en Windows.  <br/> |
|6.  <br/> | En el gráfico **Usuarios**, el eje Y es el recuento total de usuarios únicos que se han conectado a una aplicación en cualquier día del período de informe.  <br/>  En el gráfico **Usuarios**, el eje X es el número de usuarios únicos que han usado la aplicación durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje Y es el recuento total de usuarios únicos que han usado una aplicación específica durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje X es la lista de aplicaciones de su organización.  <br/>  En el gráfico **Versiones**, el eje Y es el recuento total de los usuarios únicos que utilizan una versión específica de escritorio de Outlook. Si el informe no puede resolver el número de versión de Outlook, la cantidad se mostrará como **Undetermined**.  <br/>  En el gráfico **Versiones**, el eje X es la lista de aplicaciones de su organización.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento en la leyenda.  <br/> |
|8.  <br/> | Es posible que no vea todos los elementos de las columnas en la lista siguiente hasta que los agregue.<br/> **Username** es el nombre del propietario de la aplicación de correo electrónico.  <br/> **La última fecha de actividad** es la última fecha en la que el usuario leyó o envió un mensaje de correo electrónico.  <br/> **Mail de Mac**, **Outlook para Mac**, **Outlook**, **Outlook móvil** y **Outlook en la web**, son ejemplos de aplicaciones de correo electrónico que es posible que tenga en su organización.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo se ocultan los detalles** del nivel de usuario? en los informes de actividad [de la Centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso de aplicaciones de correo electrónico: elija columnas.](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |También puede exportar los datos del informe a un Excel .csv, seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
