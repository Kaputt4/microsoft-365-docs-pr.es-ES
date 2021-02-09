---
title: Revisar y administrar acciones correctivas en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142698"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar y administrar acciones de corrección en Office 365

A medida que las investigaciones automatizadas en el correo & contenido de colaboración resultan en veredictos, como *malintencionados* o *sospechosos,* se crean determinadas acciones de corrección. En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:
- Bloqueo de una dirección URL (tiempo de clic)
- Eliminación de mensajes de correo electrónico o clústeres de forma flexible
- Quarantining email or email attachments
- Desactivar el reenvío de correo externo

Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe y hasta que el equipo de operaciones de seguridad las apruebe. Se recomienda revisar y aprobar las acciones pendientes lo antes posible para que las investigaciones automatizadas se completen de forma oportuna. En algunos casos, puede deshacer una acción de corrección.

## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes

1. Vaya al Centro de seguridad de Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones.**
3. En la **pestaña** Pendiente, revisa la lista de acciones que están a la espera de su aprobación.
4. Seleccione un elemento de la lista. Se abre el panel desplegable. 
5. Revise la información del panel desplegable y, a continuación, siga uno de estos pasos:
   - Seleccione **abrir la página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.

## <a name="undo-one-remediation-action"></a>Deshacer una acción de corrección

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.
2. En la **pestaña** Historial, seleccione una acción que desee deshacer.
3. En el panel del lado derecho de la pantalla, seleccione **Deshacer**.

## <a name="undo-multiple-remediation-actions"></a>Deshacer varias acciones de corrección

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.
2. En la **pestaña** Historial, seleccione las acciones que desea deshacer. Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción. Se abre un panel desplegable.
3. En el panel desplegable, seleccione Deshacer.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.
2. En la **pestaña** Historial, seleccione un archivo que tenga el tipo de acción **Quarantine file**.
3. En el panel del lado derecho de la pantalla, seleccione Aplicar a **X más** instancias de este archivo y, a continuación, **seleccione Deshacer**.

## <a name="next-steps"></a>Siguientes pasos

- [Usar el Explorador de amenazas](threat-explorer.md)
- [Cómo notificar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Recursos adicionales

- [Ver detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)
