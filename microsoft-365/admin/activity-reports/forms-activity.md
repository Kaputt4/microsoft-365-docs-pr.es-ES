---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de formularios'
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
description: Obtenga información sobre cómo obtener un informe de actividad de Microsoft Forms mediante el panel informes de Microsoft 365 en el centro de administración de Microsoft 365.
ms.openlocfilehash: 78b09edfbfeb83c056af16787085b7c4cfe93fc6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949209"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de formularios

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).
  
Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar Microsoft Forms examinando su interacción con los formularios. También le ayuda a comprender el nivel de colaboración en el que se encuentra al mirar el número de formularios creados y los formularios a los que respondió el usuario.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Obtener acceso al informe de actividad de formularios

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **Forms** \> **actividad**de formularios.

## <a name="interpret-the-forms-activity-report"></a>Interpretar el informe de actividad de formularios

Puede obtener una vista de la actividad de los formularios del usuario consultando los gráficos **actividad** y **usuarios** . 

![Informe de actividad de formularios](../../media/adminformsactivity.png)

|Item|Descripción|
|:-----|:-----|
|1.  <br/> |El informe de **actividad de formularios** puede visualizarse para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **usuarios** le ayuda a comprender la tendencia en el número de usuarios de formularios activos. Un usuario se considera activo si ha ejecutado una actividad alrededor de un formulario (crear, editar, ver, etc.) o respondió a un formulario dentro del período de tiempo específico.  <br/> |
|4.  <br/> |La vista de **actividad** le ayuda a comprender la tendencia en el número de usuarios activos. Un usuario se considera activo si ha ejecutado una actividad de archivo (guardar, sincronizar, modificar o compartir) o ha visitado una página dentro del período de tiempo especificado.<br/> Nota: una actividad puede producirse varias veces para un solo formulario, pero solo se contará como un formulario activo. Por ejemplo, puede crear un formulario y continuar modificando el mismo formulario varias veces durante un período de tiempo especificado, pero solo se contará como un formulario único. Sin embargo, si un usuario envió varias respuestas para el mismo formulario, cada respuesta seguiría siendo una respuesta individual y, por lo tanto, se contará varias veces. <br/> |
|5.<br/>|En el gráfico **usuarios** , el eje Y es el número de usuarios únicos. Eje X es la fecha en la que los usuarios únicos están activos. Las leyendas son:<br/><br/>**Diseñadores** significa que el usuario ha creado o editado un formulario.<br/>**Respondedores** significa que el usuario ha enviado respuestas a un formulario.<br/> **Total de usuarios significa a** cualquier persona de la compañía que ha sido un diseñador o respondedor.<br/><br/> En el gráfico **actividad** , el eje Y es el recuento de formularios o respuestas únicos. Eje X es la fecha en que se produjo el formulario o la actividad de respuesta. Las leyendas son:<br/><br/>**Formularios creados** es el recuento de los formularios únicos que han creado los usuarios.<br/> **Respuestas con sesión iniciada** el número de respuestas iniciadas por los usuarios de la organización que han recibido.<br/> **Respuestas anónimas** es el número de respuestas anónimas que han recibido los usuarios de la organización.<br/><br/>|
|6.<br/>|Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico usuarios, seleccione diseñadores, respondedores o total de usuarios para ver solo la información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla de cuadrícula que hay debajo de ella.|
|7.<br/>|En la tabla se muestra un desglose de las actividades en el nivel por usuario. Las leyendas son:<br/><br/>**Username** es la dirección de correo electrónico del usuario que realizó la actividad en Microsoft Forms.<br/>**Fecha de última actividad (UTC)** es la última fecha en que el usuario ha realizado una actividad de formulario para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/><br/>Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.<br/><br/>**Número de formularios creados** es el número de formularios que ha creado el usuario.<br/> **Número de formularios respondidos** es el número de formularios a los que el usuario ha enviado respuestas.|
|8.<br/>|Seleccione el icono **administrar columnas** para agregar o quitar columnas del informe.|
|9.<br/>|También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Esto exporta datos para todos los usuarios y le permite realizar una agregación, ordenación y filtrado sencillos para un análisis más avanzado. Si tiene menos de 100 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 100 usuarios, con el fin de filtrar y ordenar, tendrá que exportar los datos.|