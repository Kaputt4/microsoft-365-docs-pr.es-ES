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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904133"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar y administrar acciones de corrección en Office 365

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

A medida que las investigaciones automatizadas en el &  contenido de colaboración resultan en veredictos, como malintencionados o sospechosos, se crean determinadas acciones de corrección. En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:

- Bloqueo de una dirección URL (hora de hacer clic)
- Eliminación de mensajes de correo electrónico o clústeres
- Quarantining email or email attachments
- Desactivar el reenvío de correo externo

Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe. Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna. En algunos casos, puede deshacer una acción de corrección.

## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes

1. Vaya al portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En la **pestaña** Pendiente, revise la lista de acciones que están a la espera de su aprobación.
4. Seleccione un elemento de la lista. Se abre el panel desplegable. 
5. Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.

## <a name="change-or-undo-one-remediation-action"></a>Cambiar o deshacer una acción de corrección

1. Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.
2. En la **pestaña** Historial, seleccione una acción que desee cambiar o deshacer.
3. En el panel de la parte derecha de la pantalla, seleccione **Deshacer**.

## <a name="change-or-undo-multiple-remediation-actions"></a>Cambiar o deshacer varias acciones de corrección

1. Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.
2. En la **pestaña** Historial, seleccione las acciones que desea cambiar o deshacer. Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción. Se abre un panel desplegable.
3. En el panel desplegable, seleccione Deshacer.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos

1. Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.
2. En la **pestaña** Historial, seleccione un archivo que tenga el tipo de acción **Archivo de cuarentena**.
3. En el panel de la parte derecha de la pantalla, seleccione **Aplicar a X más** instancias de este archivo y, a continuación, seleccione **Deshacer**.

## <a name="next-steps"></a>Siguientes pasos

- [Usar el Explorador de amenazas](threat-explorer.md)
- [Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Consulte también

- [Ver detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)
