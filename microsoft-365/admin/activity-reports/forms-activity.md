---
title: 'Informes de Microsoft 365 en el Centro de administración: actividad de formularios'
ms.author: sirkkuw
author: sirkkuw
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
description: Obtenga información sobre cómo obtener un informe de actividad de Microsoft Forms mediante el panel informes de Microsoft 365 en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 843548e77067c7598cfa78ba6fac985237f6f62c
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841118"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de formularios

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).
  
Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar Microsoft Forms al ver su interacción con los formularios. También le ayuda a comprender el nivel de colaboración que se está creando al ver el número de formularios creados y los formularios a los que respondió el usuario.
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Cómo obtener acceso al informe de actividad de formularios

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Actividad de  \> **formularios.**

## <a name="interpret-the-forms-activity-report"></a>Interpretar el informe de actividad de formularios

Puede obtener una vista de la actividad de formularios del usuario consultando los gráficos **Actividad** **y** Usuarios. 

![Informe de actividad de formularios](../../media/adminformsactivity.png)

|Elemento|Description|
|:-----|:-----|
|1.  <br/> |El **informe de actividad** de formularios se puede ver para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La **vista** Usuarios le ayuda a comprender la tendencia en el número de usuarios de formularios activos. Un usuario se considera activo si ha ejecutado una actividad alrededor de un formulario (crear, editar, ver, etc.) o ha respondido a un formulario dentro del período de tiempo específico.  <br/> |
|4.  <br/> |La **vista** Actividad le ayuda a comprender la tendencia en el número de usuarios activos. Un usuario se considera activo si ha ejecutado una actividad de archivo (guardar, sincronizar, modificar o compartir) o ha visitado una página dentro del período de tiempo especificado.<br/> NOTA: Una actividad puede producirse varias veces para un único formulario, pero solo se contará como un formulario activo. Por ejemplo, puede crear un formulario y seguir editando el mismo formulario varias veces durante un período de tiempo especificado, pero solo contará como un único formulario. Sin embargo, si un usuario envió varias respuestas para el mismo formulario, cada respuesta seguiría siendo una respuesta individual y, por lo tanto, se contaría varias veces. <br/> |
|5.<br/>|En el **gráfico Usuarios,** el eje Y es el número de usuarios únicos. El eje X es la fecha en la que los usuarios únicos están activos. Las leyendas son:<br/><br/>**Diseñadores** significa que el usuario ha creado o editado un formulario.<br/>**Respondedores** significa que el usuario ha enviado respuestas a un formulario.<br/> **El número total** de usuarios significa cualquier persona de la empresa que haya sido diseñador o respondedor.<br/><br/> En el **gráfico Actividad,** el eje Y es el recuento de formularios o respuestas únicos. El eje X es la fecha en la que se produjo la actividad de formulario o respuesta. Las leyendas son:<br/><br/>**Los formularios** creados son el recuento de formularios únicos que los usuarios han creado.<br/> **Respuestas firmadas** el recuento de respuestas con sesión que han recibido los usuarios de la organización.<br/> **Las respuestas anónimas** son el recuento de respuestas anónimas que han recibido los usuarios de la organización.<br/><br/>|
|6.<br/>|Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico Usuarios, seleccione diseñadores, respondedores o usuarios totales para ver solo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de cuadrícula debajo de ella.|
|7.<br/>|En la tabla se muestra un desglose de las actividades en el nivel por usuario. Las leyendas son:<br/><br/>**Username** es la dirección de correo electrónico del usuario que realizó la actividad en Microsoft Forms.<br/>La fecha de la última actividad **(UTC)** es la última fecha en que el usuario realizó una actividad de formulario para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/><br/>Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.<br/><br/>**El número de formularios creados** es el número de formularios que creó el usuario.<br/> **El número de formularios a** los que se ha respondido es el número de formularios a los que el usuario ha enviado respuestas.|
|8.<br/>|Seleccione el **icono Administrar columnas** para agregar o quitar columnas del informe.|
|9.<br/>|También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Esto exporta datos para todos los usuarios y permite realizar agregaciones sencillas, ordenar y filtrar para un análisis posterior. Si tiene menos de 100 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 100 usuarios, para filtrar y ordenar, tendrá que exportar los datos.|