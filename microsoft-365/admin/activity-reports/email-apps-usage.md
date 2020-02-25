---
title: 'Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico'
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Obtenga información sobre cómo obtener el informe de uso de aplicaciones de correo electrónico para conocer las aplicaciones de correo electrónico que se conectan a Exchange Online y la versión de Outlook que usan los usuarios.
ms.openlocfilehash: 3fc0d0ce29e38bc2b7f30b6bf15909f9a736de30
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245398"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de correo electrónico, puede ver cuántas aplicaciones de correo electrónico se conectan a Exchange Online. También puede ver la información de la versión de las aplicaciones de Outlook que usan los usuarios, lo que le permitirá realizar un seguimiento con los usuarios que usan versiones no admitidas para instalar las versiones compatibles de Outlook.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint o Skype empresarial para ver los informes. 
 
## <a name="how-to-get-to-the-email-apps-report"></a>Cómo obtener el informe de aplicaciones de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione uso de la **aplicación de correo electrónico**de **Exchange** \> .
  
## <a name="interpret-the-email-apps-report"></a>Interpretar el informe de aplicaciones de correo electrónico

Puede obtener una vista de la actividad de las aplicaciones de correo electrónico consultando los gráficos **usuarios** y **clientes** . 
  
![Clientes de correo electrónico usados](../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |El informe de **uso de aplicaciones de correo electrónico** puede visualizarse para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Usuarios** muestra el número de usuarios únicos que se han conectado a Exchange Online mediante cualquier aplicación de correo electrónico.  <br/> |
|4.  <br/> |La vista **Aplicaciones** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado.  <br/> |
|5.  <br/> |La vista **versiones** muestra el número de usuarios únicos para cada versión de Outlook en Windows.  <br/> |
|6.  <br/> | En el gráfico **Usuarios**, el eje Y es el recuento total de usuarios únicos que se han conectado a una aplicación en cualquier día del período de informe.  <br/>  En el gráfico **Usuarios**, el eje X es el número de usuarios únicos que han usado la aplicación durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje Y es el recuento total de usuarios únicos que han usado una aplicación específica durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje X es la lista de aplicaciones de su organización.  <br/>  En el gráfico **Versiones**, el eje Y es el recuento total de los usuarios únicos que utilizan una versión específica de escritorio de Outlook. Si el informe no puede concluir el número de versión de Outlook, el dato se mostrará como sin determinar.  <br/>  En el gráfico **Versiones**, el eje X es la lista de aplicaciones de su organización.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico mediante selectingan elemento de la leyenda. Por ejemplo, en el gráfico **usuarios** , seleccione **correo de Mac** o lista de clientes de correo electrónico de **Outlook** ![. Seleccione el cliente de correo electrónico para obtener más datos de informes en ese cliente.](../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) para ver solo la información relacionada con cada uno. Al cambiar esta selección, no se cambia la información de la tabla de cuadrícula. Mail de Mac, Outlook para Mac, Outlook móvil, Outlook de escritorio y Outlook en la web, son ejemplos de aplicaciones de correo electrónico que es posible que tenga en su organización.  <br/> |
|8.  <br/> | Es posible que no vea todos los elementos de las columnas en la lista siguiente hasta que los agregue.<br/> **Username** es el nombre del propietario de la aplicación de correo electrónico.  <br/> **Fecha de la última actividad** es la última fecha en la que el usuario leyó o envió un mensaje de correo electrónico.  <br/> **Mail de Mac**, **Outlook para Mac**, **Outlook**, **Outlook móvil** y **Outlook en la web**, son ejemplos de aplicaciones de correo electrónico que es posible que tenga en su organización.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Seleccione **administrar columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso de aplicaciones de correo electrónico: elegir columnas](../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

