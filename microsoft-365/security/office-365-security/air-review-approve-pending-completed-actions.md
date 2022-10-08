---
title: Revisar y administrar las acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender para punto de conexión, automatizado, investigación, respuesta, corrección, amenazas, avanzado, amenaza, protección
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
- m365-security
- m365initiative-defender-office365
ms.custom: ''
description: Obtenga información sobre las acciones de corrección en las funcionalidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 plan 2.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.date: 06/10/2021
ms.openlocfilehash: 0342ad8b4319d82205889785cd243b0a6aa5d9e2
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086055"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar y administrar las acciones de corrección en Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

A medida que las investigaciones automatizadas sobre el correo electrónico & contenido de colaboración dan lugar a veredictos, como *malintencionados* o *sospechosos*, se crean determinadas acciones de corrección. En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:

- Eliminación temporal de mensajes de correo electrónico o clústeres
- Desactivar el reenvío de correo externo

Estas acciones de corrección no se realizan a menos que y hasta que el equipo de operaciones de seguridad las apruebe. Se recomienda revisar y aprobar las acciones pendientes lo antes posible para que las investigaciones automatizadas se completen de forma oportuna. En algunos casos, puede reconsiderar las acciones enviadas.  Debe formar parte del rol De búsqueda & purgar antes de realizar cualquier acción.

## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes

Hay cuatro maneras diferentes de buscar y realizar acciones de investigación automática:

- [Cola de incidentes](https://security.microsoft.com/incidents)
- Investigación en sí (a la que se accede a través de incidente o desde una alerta)
- [Centro de acciones](https://security.microsoft.com/action-center/pending)
- [Cola de investigaciones de investigación y corrección](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Cola de incidentes

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Incidentes** en **Incidentes & alertas** \> **Incidentes**. Para ir directamente a la página **Incidentes** , use <https://security.microsoft.com/incidents>.
2. En la página **Incidentes** , seleccione un nombre de incidente para abrir su página de resumen.
3. Seleccione la pestaña **Evidencia y respuesta** .
4. Seleccione un elemento de la lista. Se abre el panel lateral.
5. En el panel lateral, realice acciones de aprobación o rechazo.

## <a name="action-center"></a>Centro de actividades

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Centro** de acciones; para ello, seleccione **Centro de acciones**. Para ir directamente a la página **Centro de acciones** , use <https://security.microsoft.com/action-center/pending>.
2. En la página **Centro** de acciones, compruebe que la pestaña **Pendiente** está seleccionada y, a continuación, revise la lista de acciones que están en espera de aprobación.
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se realice una acción pendiente.

## <a name="investigation-and-remediation-investigations-queue"></a>Cola de investigaciones de investigación y corrección

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Investigación de amenazas** en Email & **Investigaciones de** **colaboración**\>. Para ir directamente a la página **Investigación de amenazas** , use <https://security.microsoft.com/airinvestigation>.
2. En la página **Investigación de amenazas** , busque y un elemento de la lista cuyo estado sea **La acción Pendiente**.
3. Haga clic en ![Abrir en el icono de ventana nueva.](../../media/m365-cc-sc-open-icon.png) **Abra en una nueva ventana** en la hora de la lista (entre **id.** y **Estado**).
4. En la página que se abre, realice acciones de aprobación o rechazo.

## <a name="change-or-undo-one-remediation-action"></a>Cambiar o deshacer una acción de corrección

Hay dos maneras diferentes de reconsiderar las acciones enviadas:

- A través del [centro de acciones unificado](https://security.microsoft.com/action-center).
- Aunque el [centro de acciones de Office](https://security.microsoft.com/threatincidents).

## <a name="change-or-undo-through-the-unified-action-center"></a>Cambiar o deshacer a través del centro de acciones unificado

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya al centro de acciones unificado; para ello, seleccione **Centro de acciones**. Para ir directamente al centro de acciones unificado, use <https://security.microsoft.com/action-center/>.
2. En la página **Centro de acciones** , seleccione la pestaña **Historial** y, a continuación, seleccione la acción que desea cambiar o deshacer.
3. En el panel del lado derecho de la pantalla, seleccione la acción adecuada (**mover a la bandeja de entrada**, **moverse a correo no deseado**, **moverse a elementos eliminados**, **eliminar temporalmente** o **eliminar de forma rígida**).

## <a name="change-or-undo-through-the-office-action-center"></a>Cambiar o deshacer a través del centro de acciones de Office

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya al centro de acciones de Office en Email & **centro de acciones** de **revisión** \> de **colaboración**\>. Para ir directamente al centro de acciones de Office, use <https://security.microsoft.com/threatincidents>.
2. En la página **Centro de acciones** , seleccione la corrección adecuada.
3. En el panel lateral, haga clic en la entrada envíos de correo y espere a que se cargue la lista.
4. Espere a que el botón Acción de la parte superior se habilite y seleccione el botón Acción para cambiar el tipo de acción.
5. Esto creará las acciones adecuadas.

## <a name="next-steps"></a>Pasos siguientes

- [Uso del Explorador de amenazas](threat-explorer.md)
- [Administración /Acciones manuales](remediate-malicious-email-delivered-office-365.md)
- [Cómo notificar falsos positivos o negativos en funcionalidades automatizadas de investigación y respuesta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Vea también

- [Ver detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)
