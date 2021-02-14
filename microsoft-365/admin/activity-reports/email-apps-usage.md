---
title: 'Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones de correo electrónico'
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Obtenga información sobre cómo obtener un informe de uso de aplicaciones de correo electrónico para conocer las aplicaciones de correo electrónico que se conectan a Exchange Online y la versión de Outlook que usan los usuarios.
ms.openlocfilehash: c6ee72390f0b9e9ead0f07c41d64bf5b7264fc1b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948249"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones de correo electrónico

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de correo electrónico, puede ver cuántas aplicaciones de correo electrónico se conectan a Exchange Online. También puede ver la información de versión de las aplicaciones de Outlook que usan los usuarios, lo que le permitirá realizar un seguimiento de aquellos que usan versiones no compatibles para instalar versiones compatibles de Outlook.
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Cómo obtener acceso al informe de aplicaciones de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Uso de la aplicación Correo electrónico de **Exchange.** \> 
  
## <a name="interpret-the-email-apps-report"></a>Interpretar el informe de aplicaciones de correo electrónico

Puede obtener una vista de la actividad de las aplicaciones de correo electrónico consultando los **gráficos** usuarios **y** clientes. 
  
![Clientes de correo electrónico usados](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|Elemento|Description|
|:-----|:-----|
|1.  <br/> |El **informe de uso de** aplicaciones de correo electrónico se puede ver para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Usuarios** muestra el número de usuarios únicos que se han conectado a Exchange Online mediante cualquier aplicación de correo electrónico.  <br/> |
|4.  <br/> |La vista **Aplicaciones** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado.  <br/> |
|5.  <br/> |La **vista** Versiones muestra el número de usuarios únicos para cada versión de Outlook en Windows.  <br/> |
|6.  <br/> | En el gráfico **Usuarios**, el eje Y es el recuento total de usuarios únicos que se han conectado a una aplicación en cualquier día del período de informe.  <br/>  En el gráfico **Usuarios**, el eje X es el número de usuarios únicos que han usado la aplicación durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje Y es el recuento total de usuarios únicos que han usado una aplicación específica durante el período de informe.  <br/>  En el gráfico **Aplicaciones**, el eje X es la lista de aplicaciones de su organización.  <br/>  En el gráfico **Versiones**, el eje Y es el recuento total de los usuarios únicos que utilizan una versión específica de escritorio de Outlook. Si el informe no puede resolver el número de versión de Outlook, la cantidad se mostrará como **Undetermined**.  <br/>  En el gráfico **Versiones**, el eje X es la lista de aplicaciones de su organización.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **Usuarios,** seleccione Correo **mac** o **Lista de outlook** de clientes de correo ![ electrónico. Seleccione el cliente de correo electrónico para obtener más datos de informes sobre ese cliente.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) para ver solo la información relacionada con cada uno. Al cambiar esta selección, no se cambia la información de la tabla de cuadrícula. Mail de Mac, Outlook para Mac, Outlook móvil, Outlook de escritorio y Outlook en la web, son ejemplos de aplicaciones de correo electrónico que es posible que tenga en su organización.  <br/> |
|8.  <br/> | Es posible que no vea todos los elementos de las columnas en la lista siguiente hasta que los agregue.<br/> **El** nombre de usuario es el nombre del propietario de la aplicación de correo electrónico.  <br/> **La fecha de la última** actividad es la última fecha en la que el usuario leyó o envió un mensaje de correo electrónico.  <br/> **Mail de Mac**, **Outlook para Mac**, **Outlook**, **Outlook móvil** y **Outlook en la web**, son ejemplos de aplicaciones de correo electrónico que es posible que tenga en su organización.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo se ocultan los** detalles del nivel de usuario? en los informes de actividades del Centro de administración [de Microsoft 365.](activity-reports.md)  <br/> |
|9.  <br/> |Seleccione **Administrar columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso de aplicaciones de correo electrónico: elegir columnas](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
