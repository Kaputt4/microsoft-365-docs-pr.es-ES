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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Obtenga información sobre cómo obtener un informe de actividad de correo electrónico mediante el panel informes de 365 de Microsoft en el centro de administración de Microsoft 365.
ms.openlocfilehash: 34cacd3a1c4682a53fdefd8f3fe26c38651676df
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353851"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, puede obtener una vista de alto nivel del tráfico de correo electrónico de su organización desde la página Informes. Luego, puede desplazarse al widget Actividad de correo electrónico para consultar las tendencias y los detalles de nivel de usuario de la actividad de correo electrónico de su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint o Skype empresarial para ver los informes. 

## <a name="how-to-get-to-the-email-activity-report"></a>Obtener acceso al informe de actividad de correo electrónico

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **** \> **actividad de correo electrónico**de Exchange.
  
## <a name="interpret-the-email-activity-report"></a>Interpretar el informe de actividad de correo electrónico

Puede obtener una vista de la actividad de correo electrónico de su usuario consultando los gráficos **Actividad** y **Usuarios**. 
  
![Informe de actividad de correo electrónico](../../media/21c1e082-317e-4b5e-b736-661ca5744def.png)
  
|||
|:-----|:-----|
|1.  <br/> |El informe **Actividad de correo electrónico** se puede visualizar para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |El gráfico **Actividad** le permite consultar la tendencia de la actividad de correo electrónico presente en su organización. Puede analizar la división de las actividades de envío, lectura o recepción de correo electrónico.  <br/> |
|4.  <br/> |El gráfico **Usuario** le permite consultar la tendencia de la cantidad de usuarios únicos que generan las actividades de correo electrónico. Puede consultar la tendencia de los usuarios que llevan a cabo actividades de envío, lectura o recepción de correo electrónico.  <br/> |
|5.  <br/> | En el gráfico **Actividad**, el eje Y es el número de actividades de los tipos de correo electrónico enviado, recibido y leído.  <br/>  En el gráfico de actividad **Usuarios**, el eje Y es la actividad que lleva a cabo el usuario de los tipos de correo electrónico enviado, recibido y leído.  <br/>  En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **actividad** , seleccione gráficos de filtro de **envío**, **recepción**o **lectura** ![para datos](../../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) relacionados específicos para ver solo la información relacionada con cada uno de ellos. Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> |
|7.  <br/> | En la tabla se muestra un desglose de las actividades de correo electrónico en el nivel de usuario. Se muestran todos los usuarios que tienen asignado un producto de Exchange y sus actividades de correo electrónico. <br/> <br/> **Nombre de usuario** es la dirección de correo electrónico de los usuarios.  <br/> **Nombre para mostrar** es el nombre completo del usuario.  <br/> **Eliminado** se refiere al usuario cuyo actual estado se ha eliminado, pero que estaba activo durante parte del período de informes del informe.  <br/> **Fecha de eliminación** es la fecha en que se eliminó el usuario.  <br/> **Fecha de última actividad** hace referencia a la última vez que el usuario realizó una actividad de lectura o envío de correo electrónico.  <br/> **Acciones de envío** es el número de veces que se registra una acción de envío de correo electrónico para el usuario.  <br/> **Acciones de recepción** es el número de veces que se registra una acción de recepción de correo electrónico para el usuario.  <br/> **Acciones de lectura** es el número de veces que se registra una acción de lectura de correo electrónico para el usuario.  <br/> **Producto asignado** son los productos que se asignan a este usuario.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello **** ![, seleccione el](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) vínculo exportar botón exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
Nota: el informe de actividad de correo electrónico solo está disponible para los buzones que están asociados a usuarios que tienen licencias.
