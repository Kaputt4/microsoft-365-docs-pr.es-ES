---
title: Revisar y administrar acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección en las capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028936"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar y administrar acciones de corrección en Office 365

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

A medida que las investigaciones automatizadas en el &  contenido de colaboración resultan en veredictos, como malintencionados o sospechosos, se crean determinadas acciones de corrección. En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:

- Eliminación de mensajes de correo electrónico o clústeres
- Desactivar el reenvío de correo externo

Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe. Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna. En algunos casos, puede reconsiderar las acciones enviadas.  Debe formar parte de la función de & de depuración antes de realizar cualquier acción.


## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes
Hay cuatro formas diferentes de buscar y realizar acciones de investigación automática:

- [Cola de incidentes](https://security.microsoft.com/incidents)
- [Centro de actividades](https://security.microsoft.com/action-center/pending)
- Investigación en sí (a la que se accede a través de un incidente o desde una alerta)
- [Cola de investigaciones de investigación y corrección](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Cola de incidentes
1. Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.
2. En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.
3. Seleccione un nombre de incidente para abrir su página de resumen.
4. Seleccione la **pestaña Evidencia y** respuesta.
5. Seleccione un elemento de la lista. Se abre su panel lateral.
6. En el panel lateral, lleve a cabo acciones de aprobación o rechazo.

## <a name="investigation-queue"></a>Cola de investigación 
1. Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.
2. Navegue desde la página alertas/incidentes. 
3. En la página Investigación, vaya a la **pestaña Acciones pendientes.** 
4. Seleccione un elemento de la lista. Se abre su panel lateral.  
5. En el panel lateral, lleve a cabo acciones de aprobación o rechazo.

## <a name="action-center"></a>Centro de actividades
1. Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En la **pestaña** Pendiente, revise la lista de acciones que están a la espera de su aprobación.
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.

## <a name="investigation-and-remediation-investigations-queue"></a>Cola de investigaciones de investigación y corrección
1. Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.
2. Abrir investigaciones pendientes. 
3. En la página Investigación, vaya a la **pestaña Acciones pendientes.**
4. Seleccione un elemento de la lista. Se abre su panel lateral.  
5. En el panel lateral, lleve a cabo acciones de aprobación o rechazo.

## <a name="change-or-undo-one-remediation-action"></a>Cambiar o deshacer una acción de corrección

Hay dos formas diferentes de reconsiderar las acciones enviadas:
   - A través del [centro de acciones unificado](https://security.microsoft.com/action-center).
   - Aunque el [Office de acción](https://security.microsoft.com/threatincidents).
   
## <a name="change-or-undo-through-the-unified-action-center"></a>Cambiar o deshacer a través del centro de acciones unificado
1. Vaya al centro [de acciones unificado](https://security.microsoft.com/action-center) e inicie sesión.
2. En la **pestaña** Historial, seleccione una acción que desee cambiar o deshacer.
3. En el panel de la parte derecha de la pantalla, seleccione la acción adecuada **(** mover a la bandeja de **entrada,** mover a correo no **deseado,** mover a elementos eliminados , **eliminación temporal" o eliminar de forma **permanente**).

 ## <a name="change-or-undo-through-the-office-action-center"></a>Cambiar o deshacer a través del centro de Office acción 
1. Vaya al centro [de Office acción e](https://security.microsoft.com/threatincidents) inicie sesión.
2. Seleccione la corrección adecuada.
3. En el panel lateral, haga clic en la entrada envíos de correo y espere a que se cargue la lista. 
4. Espere a que el botón Acción de la parte superior habilite y seleccione el botón Acción para cambiar el tipo de acción. 
5. Esto creará las acciones adecuadas.

## <a name="next-steps"></a>Pasos siguientes

- [Usar el Explorador de amenazas](threat-explorer.md) 
- [Acciones de administrador /manual](remediate-malicious-email-delivered-office-365.md)
- [Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Vea también

- [Ver detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)
