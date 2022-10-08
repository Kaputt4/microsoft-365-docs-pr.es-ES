---
title: Habilitación de la integración de soporte técnico de Microsoft 365 para ServiceNow Virtual Agent
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
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Configure la característica experimental de integración de soporte técnico para probar y proporcionar comentarios al equipo de integración de soporte técnico de Microsoft 365.
ms.openlocfilehash: 48a49b1e4a19039c40db278adf398f9a0ccd3831
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68172959"
---
# <a name="enable-microsoft-365-support-integration-for-servicenow-virtual-agent"></a>Habilitación de la integración de soporte técnico de Microsoft 365 para ServiceNow Virtual Agent

> [!IMPORTANT]
> La integración de soporte técnico para ServiceNow Virtual Agent es una característica experimental que se está implementando para que los usuarios prueben y proporcionen comentarios al equipo de integración de soporte técnico de Microsoft 365.

Al configurar la aplicación de integración de soporte técnico de Microsoft 365 para que funcione con ServiceNow Virtual Agent, obtendrá acceso a **soluciones recomendadas** a través de dos experiencias de usuario diferentes:

- **Conclusiones rápidas** Similar a lo que aparece en la página Incidentes, el agente virtual de ServiceNow muestra **artículos recomendados** y **soluciones recomendadas** en función del texto escrito.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-1.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Conclusiones rápidas.":::

- **Experiencia de bifurcación** La bifurcación se integra con la característica de búsqueda y asistente para guiar a los usuarios a través de un flujo de solución de problemas que devuelve respuestas basadas en el texto escrito.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-2.png" alt-text="Experiencia de bifurcación.":::

## <a name="before-you-begin"></a>Antes de empezar

- Habilite el agente virtual en ServiceNow. Para obtener más información, consulte [Activación del agente virtual](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/activate-virtual-agent.html).

- Descargue y complete la configuración de la aplicación de integración de soporte técnico de Microsoft 365 desde la Tienda ServiceNow.

- Versión mínima de la integración de compatibilidad con Microsoft 365: v1.0.10.

- Versión mínima de ServiceNow: Quebec.

- Rol necesario: Administración.

## <a name="configure-microsoft-365-support-integration-to-work-with-servicenow-virtual-agent"></a>Configuración de la integración de soporte técnico de Microsoft 365 para trabajar con ServiceNow Virtual Agent

- Establezca Soporte técnico de Microsoft 365 como tema de reserva. Para obtener más información, consulte [Configuración de una experiencia de chat del agente virtual](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/configure-default-chat-experience.html).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-3.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-3.png" alt-text="Establezca el tema de reserva de experiencia de chat predeterminado.":::