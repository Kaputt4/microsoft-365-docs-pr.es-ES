---
title: Integración de Microsoft 365 con ServiceNow Virtual Agent
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Configure la integración de soporte técnico para probar y proporcionar comentarios al equipo de integración de soporte técnico de Microsoft 365.
ms.openlocfilehash: 25c18c562776e7e28a9f6596950f36d6396021b4
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68735647"
---
# <a name="integrate-microsoft-365-with-servicenow-virtual-agent"></a>Integración de Microsoft 365 con ServiceNow Virtual Agent

Al configurar la aplicación de integración de soporte técnico de Microsoft 365 para que funcione con ServiceNow Virtual Agent, accederá a la autoayuda creada por los equipos de productos de Microsoft 365 a través de dos experiencias de usuario diferentes:

- Soluciones paso a paso y paso a paso de Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Conclusiones rápidas.":::
    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2b.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-2b.png" alt-text="Conclusiones rápidas.":::

- Principales resultados de búsqueda web de artículos de Microsoft 365 knowledge base.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-1.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Resultados de búsqueda de artículos de Knowledge Base.":::

## <a name="before-you-begin"></a>Antes de empezar

- Habilite el agente virtual en ServiceNow. Para obtener más información, consulte [Activación del agente virtual](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/activate-virtual-agent.html).

- Instale y complete la configuración de la aplicación de integración de soporte técnico de Microsoft 365 desde la Tienda ServiceNow.

- Versión mínima de ServiceNow: Roma.

- Rol necesario: administrador de ServiceNow o virtual_agent_admin.

## <a name="configure-microsoft-365-support-integration-to-work-with-servicenow-virtual-agent"></a>Configuración de la integración de soporte técnico de Microsoft 365 para trabajar con ServiceNow Virtual Agent

### <a name="standalone-fallback-topic"></a>Tema de reserva independiente

Establezca Soporte técnico de Microsoft 365 como tema de reserva. Para obtener más información, consulte [Configuración de una experiencia de chat del agente virtual](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/configure-default-chat-experience.html).

:::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-3.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-3.png" alt-text="Establezca el tema de reserva de experiencia de chat predeterminado.":::

### <a name="topic-blocks"></a>Bloques de temas

Si no tiene ningún tema creado, puede usar el tema de reserva independiente como se mencionó anteriormente o [crear su propio tema de agente virtual](https://docs.servicenow.com/bundle/rome-now-intelligence/page/administer/virtual-agent/task/create-virtual-agent-topic.html).

Siga estos pasos para agregar el bloque de temas Soporte técnico de Microsoft 365:

1. En **Utilidades**, seleccione **Bloque de temas** y agréguelo al flujo.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-1.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-1.png" alt-text="Agregue un bloque de temas al flujo.":::

1. En **Propiedades del bloque de temas**, elija **Bloque de temas de soporte técnico de Microsoft 365**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-2.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-2.png" alt-text="Elija la propiedad Bloque de temas de soporte técnico.":::

1. Un bloque de temas de soporte técnico de Microsoft 365 tiene acceso al texto de entrada en este orden:

    a. Comprueba si hay variable de entrada. Si la variable de entrada no está vacía, captura los resultados de la variable de entrada.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-3.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-3.png" alt-text="Captura los resultados de la variable de entrada.":::

    b. Si la variable de entrada está vacía, comprueba el texto escrito por el usuario en la ventana de chat y captura los resultados del texto.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-4.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-4.png" alt-text="Comprueba si hay texto escrito en la ventana de chat.":::

    c. Si el usuario no ha especificado texto, pide al usuario que escriba texto para capturar los resultados.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-5.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-5.png" alt-text="Comprueba si hay texto escrito en la ventana de chat.":::

1. El bloque de temas de soporte técnico de Microsoft 365 proporciona una variable de salida, que es los comentarios del usuario para los resultados.

    a. Nombre de la variable de salida: m365_success b. Posibles valores de variable de salida: SÍ/NO

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-6.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-6.png" alt-text="Nombre y valores de la variable de salida.":::