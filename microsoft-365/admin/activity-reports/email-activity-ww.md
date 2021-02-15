---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico'
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
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Obtenga información sobre cómo obtener un informe de actividad de correo electrónico mediante el panel informes de Microsoft 365 en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 65ef74ccd05aa4b55fc127985c03a490bb109b4b
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921992"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, puede obtener una vista de alto nivel del tráfico de correo electrónico de su organización desde la página Informes. Luego, puede desplazarse al widget Actividad de correo electrónico para consultar las tendencias y los detalles de nivel de usuario de la actividad de correo electrónico de su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes. 

## <a name="how-to-get-to-the-email-activity-report"></a>Obtener acceso al informe de actividad de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. Seleccione **Ver más en** Actividad de correo **electrónico.** 
3. En la **lista desplegable Actividad** de correo electrónico, seleccione Actividad de correo electrónico de **Exchange.** \> 
  
## <a name="interpret-the-email-activity-report"></a>Interpretar el informe de actividad de correo electrónico

Puede obtener una vista de la actividad de correo electrónico de su usuario consultando los gráficos **Actividad** y **Usuarios**. 
  
![Informe de actividad de correo electrónico](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|Elemento|Description|
|:-----|:-----|
|1.  <br/> |El informe **Actividad de correo electrónico** se puede visualizar para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |El gráfico **Actividad** le permite consultar la tendencia de la actividad de correo electrónico presente en su organización. Puede comprender la división de las actividades de envío de correo electrónico, lectura de correo electrónico, correo electrónico recibido, reunión creada o reunión interaccionada.  <br/> |
|4.  <br/> |El gráfico **Usuario** le permite consultar la tendencia de la cantidad de usuarios únicos que generan las actividades de correo electrónico. Puede ver la tendencia de los usuarios que realizan envíos de correo electrónico, lectura de correo electrónico, recepción de correo electrónico, creación de reuniones o actividades de interacción de reuniones.  <br/> |
|5.  <br/> | En el **gráfico Actividad,** el eje Y es el recuento de actividad del tipo de correo electrónico enviado, correo electrónico recibido, lectura de correo electrónico, reunión creada e interacción de la reunión.  <br/>  En el **gráfico de** actividad Usuarios, el eje Y es la actividad que realiza el usuario del tipo de correo electrónico enviado, correo electrónico recibido, lectura de correo electrónico, reunión creada o reunión interactuada.  <br/>  En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda.  <br/> |
|7.  <br/> | En la tabla se muestra un desglose de las actividades de correo electrónico en el nivel de usuario. Se muestran todos los usuarios que tienen asignado un producto de Exchange y sus actividades de correo electrónico. <br/> <br/> **Nombre de usuario** es la dirección de correo electrónico de los usuarios.  <br/> **El nombre para** mostrar es el nombre completo si el usuario.  <br/> **Eliminado** se refiere al usuario cuyo actual estado se ha eliminado, pero que estaba activo durante parte del período de informes del informe.  <br/> **Fecha de eliminación** es la fecha en que se eliminó el usuario.  <br/> **Fecha de última actividad** hace referencia a la última vez que el usuario realizó una actividad de lectura o envío de correo electrónico.  <br/> **Acciones de envío** es el número de veces que se registra una acción de envío de correo electrónico para el usuario.  <br/> **Acciones de recepción** es el número de veces que se registra una acción de recepción de correo electrónico para el usuario.  <br/> **Acciones de lectura** es el número de veces que se registra una acción de lectura de correo electrónico para el usuario.  <br/> **Las acciones creadas por** la reunión son el número de veces que se registró una acción de envío de una solicitud de reunión para el usuario.  <br/> **Las acciones de reunión interaccionadas** son el número de veces que se registró una acción de aceptación, provisional, rechazo o cancelación de una reunión para el usuario.  <br/> **El producto asignado** es los productos que se asignan a este usuario.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo se ocultan los** detalles del nivel de usuario? en los informes de actividades del Centro de administración [de Microsoft 365.](activity-reports.md)  <br/> |
|8.  <br/> |Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de correo electrónico: elegir columnas](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
> [!NOTE]
> El informe de actividad de correo electrónico solo está disponible para los buzones asociados con usuarios con licencias.
