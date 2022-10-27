---
title: Centro de administración de Microsoft 365 informes de actividad de correo electrónico
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
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
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Obtenga información sobre cómo obtener un informe de actividad de correo electrónico y comprender las tendencias de correo electrónico del usuario mediante el panel Informes de Microsoft 365 de la Centro de administración de Microsoft 365.
ms.openlocfilehash: 94ae5e27e6ce95b28be587834731642f24c3b182
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68724933"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de Email

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, puede obtener una vista de alto nivel del tráfico de correo electrónico de su organización desde la página Informes. Luego, puede desplazarse al widget Actividad de correo electrónico para consultar las tendencias y los detalles de nivel de usuario de la actividad de correo electrónico de su organización.

## <a name="how-to-get-to-the-email-activity-report"></a>Obtener acceso al informe de actividad de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. Seleccione **Ver más** en **Email actividad**. 
3. En la lista desplegable **Email actividad**, seleccione **Exchange** \> **Email actividad**.
  
## <a name="interpret-the-email-activity-report"></a>Interpretar el informe de actividad de correo electrónico

Puede obtener una vista de la actividad de correo electrónico de su usuario consultando los gráficos **Actividad** y **Usuarios**. 
  
![Email informe de actividad.](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)

El informe **Actividad de correo electrónico** se puede visualizar para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe). Los datos de cada informe suelen cubrir hasta las últimas 24 a 48 horas.

El gráfico **Actividad** le permite consultar la tendencia de la actividad de correo electrónico presente en su organización. Puede comprender la división de las actividades de envío de correo electrónico, lectura de correo electrónico, correo electrónico recibido, reunión creada o reunión interactuada. 

El gráfico **Usuario** permite comprender la tendencia del número de usuarios únicos que generan las actividades de correo electrónico. Puede ver la tendencia de los usuarios que realizan el envío de correo electrónico, la lectura de correo electrónico, la recepción de correo electrónico, la creación de reuniones o las actividades de interacción de reuniones. 

En el gráfico Actividad, el eje Y es el recuento de actividad del tipo de correo electrónico enviado, correo electrónico recibido, lectura de correo electrónico, reunión creada e interacción con la reunión. 

En el gráfico actividad Usuarios, el eje Y es la actividad que realiza el usuario del tipo de correo electrónico enviado, correo electrónico recibido, lectura de correo electrónico, reunión creada o reunión interactuada. 

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 

Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda.

 En la tabla se muestra un desglose de las actividades de correo electrónico en el nivel de usuario. Se muestran todos los usuarios que tienen asignado un producto de Exchange y sus actividades de correo electrónico.

  
|Elemento|Descripción|
|:-----|:-----|
|Nombre de usuario  |La dirección de correo electrónico del usuario. |
|Nombre para mostrar |Nombre completo del usuario. |
|Deleted |Hace referencia al usuario cuyo estado actual se elimina, pero que estuvo activo durante alguna parte del período de informes del informe. |
|Fecha de eliminación |La fecha en que se eliminó el usuario. |
|Fecha de la última actividad  | La última vez que el usuario realizó una actividad de lectura o envío de correo electrónico. |
|Acciones de envío |El número de veces que se registró una acción de envío de correo electrónico para el usuario.  |
|Acciones de recepción  |El número de veces que se registró una acción de recepción de correo electrónico para el usuario. |
|Acciones de lectura |El número de veces que se registró una acción de lectura de correo electrónico para el usuario. |
|Acciones creadas para reuniones  |El número de veces que se registró una acción de envío de una convocatoria de reunión para el usuario. |
|Reuniones de acciones interactuadas |El número de veces que se registró una acción de aceptación, tentativa, declinación o cancelación de una convocatoria de reunión para el usuario. |
|Producto asignado  |Productos asignados a este usuario.  |


Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Cómo ocultar los detalles de nivel de usuario** en informes [de actividad de la Centro de administración de Microsoft 365](activity-reports.md).

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  

![Email informe de actividad: elija columnas.](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)

También puede exportar los datos del informe a un archivo .csv de Excel; para ello, seleccione el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. 
   
> [!NOTE]
> El informe de actividad de Email solo está disponible para los buzones asociados a usuarios que tienen licencias.
