---
title: Centro de administración de Microsoft 365 informes de uso de aplicaciones de correo electrónico
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
description: Obtenga información sobre cómo obtener un informe de uso de aplicaciones de correo electrónico para averiguar cuántas aplicaciones de correo electrónico se conectan a Exchange Online y qué versión de los usuarios de Outlook están usando.
ms.openlocfilehash: f0ac5a7dc862117784d3691cc616a70314d4f1f3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68197027"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones Email

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de correo electrónico, puede ver cuántas aplicaciones de correo electrónico se conectan a Exchange Online. También puede ver la información de versión de las aplicaciones de Outlook que usan los usuarios, lo que le permitirá realizar un seguimiento con aquellos que usan versiones no admitidas para instalar versiones compatibles de Outlook.
  
## <a name="how-to-get-to-the-email-apps-report"></a>Cómo llegar al informe de aplicaciones de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. Seleccione **Ver más** en **Email actividad**. 
3. En la lista desplegable **Email actividad**, seleccione **Exchange** \> **Email uso de aplicaciones**.
  
## <a name="interpret-the-email-apps-report"></a>Interpretación del informe de aplicaciones de correo electrónico

Puede obtener una vista de la actividad de las aplicaciones de correo electrónico examinando los gráficos **Usuarios** y **clientes** . 
  
![Email los clientes usados.](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)

El informe de **uso de Email aplicaciones** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe). Los datos de cada informe suelen cubrir hasta las últimas 24 a 48 horas.

La vista **Usuarios** muestra el número de usuarios únicos que se han conectado a Exchange Online mediante cualquier aplicación de correo electrónico. 

La vista **Aplicaciones** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado. 

La vista **Versiones** muestra el número de usuarios únicos para cada versión de Outlook en Windows. 

En el gráfico Usuarios, el eje Y es el recuento total de usuarios únicos que se han conectado a una aplicación en cualquier día del período de informe. Y el eje X es el número de usuarios únicos que usaron la aplicación para ese período de informes. 

En el gráfico Aplicaciones, el eje Y es el recuento total de usuarios únicos que han usado una aplicación específica durante el período de informe. Y el eje X es la lista de aplicaciones de su organización. 

En el gráfico Versiones, el eje Y es el recuento total de los usuarios únicos que utilizan una versión específica de escritorio de Outlook. Si el informe no puede resolver el número de versión de Outlook, la cantidad se mostrará como **Indeterminada**. Y el eje X es la lista de aplicaciones de su organización.

Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Es posible que no vea todos los elementos de las columnas en la lista siguiente hasta que los agregue.
 
|Elemento|Descripción|
|:-----|:-----|
|Nombre de usuario | Nombre del propietario de la aplicación de correo electrónico. |
|Fecha de la última actividad | La fecha más reciente en que el usuario leyó o envió un mensaje de correo electrónico. |
|Correo de Mac, Mac Outlook, Outlook, Outlook mobile y Outlook en la Web | Ejemplos de aplicaciones de correo electrónico que puede tener en su organización. |
   
Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Cómo ocultar los detalles de nivel de usuario** en informes [de actividad de la Centro de administración de Microsoft 365](activity-reports.md). 

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  

![Email informe de uso de aplicaciones: elija columnas.](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)

También puede exportar los datos del informe a un archivo .csv de Excel; para ello, seleccione el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. 