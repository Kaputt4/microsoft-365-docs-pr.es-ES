---
title: Detalles y resultados de una investigación automatizada
description: Durante y después de una investigación automatizada, puede ver los resultados y los resultados clave
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 83a897438b9da88287574ff576fab9b2f6b30236
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430804"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Detalles y resultados de una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Cuando se produce una investigación automatizada en la Protección contra amenazas de Microsoft, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizada. Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en la vista de detalles de la investigación. La vista de detalles de la investigación ofrece un estado actualizado y la capacidad de aprobar las acciones pendientes. 

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Abrir la vista de detalles de la investigación

Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:
- [Seleccionar un elemento en el centro de actividades](#select-an-item-in-the-action-center)
- [Seleccionar una investigación en una página de detalles de un incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Seleccionar un elemento en el centro de actividades

Use el centro de actividades para ver las acciones que estén pendientes de aprobación (en la pestaña **pendiente**) o que ya se hayan aprobado (en la pestaña **historial**). 

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En la pestaña **pendiente** o **historial**, seleccione un elemento. Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede aprobar (o rechazar) acciones pendientes.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Abrir una investigación desde una página de detalles de un incidente

Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **incidentes**. 

3. Seleccione un elemento de la lista para abrir la vista detalles del incidente.<br/>![Detalles del incidente](../../media/mtp-incidentdetails-tabs.png)

4. En la pestaña **investigaciones**, seleccione una investigación en la lista.

## <a name="investigation-details"></a>Detalles de la investigación

Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación. La vista de detalles de la investigación es similar a la siguiente imagen:

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.

|Pestaña    |Descripción |
|--------|--------|
|Gráfico de investigación    |Proporciona una representación visual de la investigación. Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.<br/>Puede hacer clic en un elemento del gráfico para ver más detalles. Por ejemplo, al hacer clic en el icono **amenazas detectadas** le llevará a la pestaña **resultados clave**. |
|Alertas |Muestra las alertas relacionadas con la investigación. Las alertas pueden provenir de características de protección contra amenazas en el equipo de un usuario, en las aplicaciones de Office, Cloud App Security y otras características de Protección contra amenazas de Microsoft 365.|
|Dispositivos|Muestra los equipos incluidos en la investigación junto con el nivel de corrección.|
|Resultados clave   |Muestra los resultados de la investigación junto con el estado y las acciones tomadas o pendientes. Puede aprobar acciones pendientes para dispositivos e identidades en esta pestaña.|
|Entidades   |Muestra las actividades del usuario, archivos, procesos, servicios, controladores, direcciones IP y métodos de persistencia asociados con la investigación, junto con el estado y las acciones tomadas.|
|Registro    |Ofrece una vista detallada de todos los pasos realizados durante la investigación, junto con el estado.|
|Acciones pendientes    |Muestra los elementos que necesitan aprobación para continuar.|

## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas](mtp-autoir-actions.md)

