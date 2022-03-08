---
title: Revisar y administrar acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Obtenga información sobre las acciones de corrección en las capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 35e9293fa83b86fb80c1c907fbf3a0769e323503
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318625"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar y administrar acciones de corrección en Office 365

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

A medida que las investigaciones automatizadas en el & contenido de colaboración resultan en veredictos, como malintencionados o sospechosos *, se* crean determinadas acciones de corrección. En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:

- Eliminación de mensajes de correo electrónico o clústeres
- Desactivar el reenvío de correo externo

Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe. Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna. En algunos casos, puede reconsiderar las acciones enviadas.  Debe formar parte del rol de purga & de búsqueda antes de realizar cualquier acción.

## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes

Hay cuatro formas diferentes de buscar y realizar acciones de investigación automática:

- [Cola de incidentes](https://security.microsoft.com/incidents)
- Investigación en sí (a la que se accede a través de un incidente o desde una alerta)
- [Centro de actividades](https://security.microsoft.com/action-center/pending)
- [Cola de investigaciones de investigación y corrección](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Cola de incidentes

1. En el portal Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página Incidentes  en **Incidentes & alertas incidentes**\>. Para ir directamente a la **página Incidentes** , use <https://security.microsoft.com/incidents>.
2. En la **página Incidentes** , seleccione un nombre de incidente para abrir su página de resumen.
3. Seleccione la **pestaña Evidencia y** respuesta.
4. Seleccione un elemento de la lista. Se abre su panel lateral.
5. En el panel lateral, lleve a cabo acciones de aprobación o rechazo.

## <a name="action-center"></a>Centro de actividades

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Centro de** acciones seleccionando **Centro de acciones**. Para ir directamente a la **página Centro de acciones** , use <https://security.microsoft.com/action-center/pending>.
2. En la **página Centro de** acciones, compruebe que la **pestaña Pendiente está** seleccionada y, a continuación, revise la lista de acciones que están a la espera de su aprobación.
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.

## <a name="investigation-and-remediation-investigations-queue"></a>Cola de investigaciones de investigación y corrección

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Investigación de amenazas** en **Email & collaboration** \> **Investigations**. Para ir directamente a la **página Investigación de amenazas** , use <https://security.microsoft.com/airinvestigation>.
2. En la **página Investigación de** amenazas, busque y un elemento de la lista cuyo estado es **Acción pendiente**.
3. Haga clic ![en Abrir en el icono de nueva ventana.](../../media/m365-cc-sc-open-icon.png) **Abra en la nueva ventana** de la hora de lista (entre **ID** y **Status**).
4. En la página que se abre, lleve a cabo acciones de aprobación o rechazo.

## <a name="change-or-undo-one-remediation-action"></a>Cambiar o deshacer una acción de corrección

Hay dos formas diferentes de reconsiderar las acciones enviadas:

- A través del [centro de acciones unificado](https://security.microsoft.com/action-center).
- Aunque el [centro Office acción](https://security.microsoft.com/threatincidents).

## <a name="change-or-undo-through-the-unified-action-center"></a>Cambiar o deshacer a través del centro de acciones unificado

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya al centro de acciones unificado seleccionando **Centro de acciones**. Para ir directamente al centro de acciones unificado, use <https://security.microsoft.com/action-center/>.
2. En la **página Centro de** acciones, **seleccione la pestaña** Historial y, a continuación, seleccione la acción que desea cambiar o deshacer.
3. En el panel de la parte derecha de la pantalla, seleccione la acción **adecuada (mover** a la bandeja de **entrada, pasar** a correo no **deseado, mover** a elementos eliminados **, eliminar** temporalmente o **eliminar de forma permanente**).

## <a name="change-or-undo-through-the-office-action-center"></a>Cambiar o deshacer a través del centro de Office acción

1. En el portal Microsoft 365 Defender en <https://security.microsoft.com>, vaya al Centro de Office acción en el Centro de & **de** colaboración **de** \> \> **colaboración**. Para ir directamente al centro de Office acción, use <https://security.microsoft.com/threatincidents>.
2. En la **página Centro de** acciones, seleccione la corrección adecuada.
3. En el panel lateral, haga clic en la entrada envíos de correo y espere a que se cargue la lista.
4. Espere a que el botón Acción de la parte superior habilite y seleccione el botón Acción para cambiar el tipo de acción.
5. Esto creará las acciones adecuadas.

## <a name="next-steps"></a>Pasos siguientes

- [Usar el Explorador de amenazas](threat-explorer.md)
- [Acciones de administrador /manual](remediate-malicious-email-delivered-office-365.md)
- [Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Vea también

- [Ver detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)
