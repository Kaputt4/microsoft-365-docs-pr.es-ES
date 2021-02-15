---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de Voz del cliente de Dynamics 365'
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
description: Obtenga información sobre cómo obtener un informe de actividad de Voz de cliente de Microsoft Dynamics 365 mediante el panel informes de Microsoft 365 en el Centro de administración de Microsoft 365.
ms.openlocfilehash: de03067197c80634f02318b35a79eb84e33c4b86
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988557"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de Voz del cliente de Dynamics 365

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).
  
Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar Microsoft Dynamics 365 Customer Voice observando sus interacciones con Dynamics 365 Customer Voice. También le ayuda a comprender el nivel de colaboración que va a seguir observando el número de encuestas pro creadas y las encuestas profesionales a las que respondieron los usuarios. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Cómo obtener acceso al informe de actividad de Forms Pro

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable Seleccionar** un informe, seleccione Actividad de Voz del cliente de Dynamics **365.** \> 

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretar el informe de actividad de Voz del cliente de Dynamics 365

Puede obtener una vista de la actividad de Dynamics 365 Customer Voice de su usuario consultando los gráficos **Actividad** **y** Usuarios. 

![Informe de actividad de formularios](../../media/formsproactivity.png)

|Elemento|Description|
|:-----|:-----|
|1.  <br/> |El informe de actividad de Voz del cliente de **Dynamics 365** se puede ver para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).   <br/> |
|2.  <br/> |Los datos de cada informe suelen ser tan recientes como en las últimas 48 horas.  <br/> |
|3.  <br/> |La **vista** Usuarios le ayuda a comprender la tendencia en el número de usuarios activos de Dynamics 365 Customer Voice. Un usuario se considera activo si ha ejecutado una actividad en torno a una encuesta profesional (crear, editar, ver, etc.) dentro del período de tiempo específico.  <br/> |
|4.  <br/> |La **vista** Actividad le ayuda a comprender la tendencia en el número de usuarios activos. Un usuario se considera activo si ha ejecutado una actividad de archivo (guardar, sincronizar, modificar o compartir) o ha visitado una página dentro del período de tiempo especificado.<br/> NOTA: Una actividad puede producirse varias veces para una sola encuesta, pero solo se contará como una encuesta activa. Por ejemplo, puede crear una encuesta pro y seguir editando la misma encuesta varias veces durante un período de tiempo especificado, solo se contará como una sola encuesta. <br>|
|5.<br/>|En el **gráfico Usuarios,** el eje Y es el número de usuarios únicos. El eje X es la fecha en la que los usuarios únicos están activos. Las leyendas son:<br/><br/>**Diseñadores** significa que el usuario ha creado o editado una encuesta de voz del cliente de Dynamics 365.<br><br>En el **gráfico Actividad,** el eje Y es el recuento de respuestas de Voz del cliente de Dynamics 365 por encuesta. El eje X es la fecha en la que se produjo la actividad encuesta o respuesta. Las leyendas son:<br/><br/>**Encuestas creadas** es el recuento de encuestas únicas de Dynamics 365 Customer Voice que los usuarios han creado<br>**Las respuestas** son el recuento de respuestas anónimas o no anónimas que han enviado los usuarios que recibieron la encuesta. |
|6.<br/>|Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico Usuarios, seleccione diseñadores, respondedores o usuarios totales para ver solo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de cuadrícula debajo de ella.|
|7.<br/>|En la tabla se muestra un desglose de las actividades en el nivel por usuario. Las leyendas son:<br/><br/>**Username** es la dirección de correo electrónico del usuario que realizó la actividad en Microsoft Forms.<br/>La fecha de la última actividad **(UTC)** es la última fecha en que el usuario realizó una actividad de formulario para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/>Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.<br/><br/>**El número de encuestas creadas** es el número de encuestas que creó el usuario.<br/> **El número de respuestas a la** encuesta es el número de respuestas de los respondedores a los que se distribuyó la encuesta.|
|8.<br/>|Seleccione el **icono Administrar columnas** para agregar o quitar columnas del informe.|
|9.<br/>|También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Esto exporta datos para todos los usuarios y permite realizar agregaciones sencillas, ordenar y filtrar para un análisis posterior. Si tiene menos de 100 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 100 usuarios, para filtrar y ordenar, tendrá que exportar los datos.|