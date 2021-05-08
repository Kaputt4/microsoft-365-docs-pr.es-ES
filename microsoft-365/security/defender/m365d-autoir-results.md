---
title: Detalles y resultados de una investigación automatizada
description: Ver los resultados y los resultados clave de la investigación automatizada en Microsoft 365 Defender
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: b26574c85e498209f8d0233495d3fe0e44733909
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245881"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Detalles y resultados de una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Con Microsoft 365 Defender, cuando se ejecuta una [investigación](m365d-autoir.md) automatizada, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado. Si tiene los [permisos necesarios](m365d-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en la vista de detalles de la investigación. La vista de detalles de la investigación ofrece un estado actualizado y la capacidad de aprobar las acciones pendientes. 

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a>(¡NUEVO!) Página de investigación unificada

La página de investigación se actualizó recientemente para incluir información en los dispositivos, el correo electrónico y el contenido de colaboración. La nueva página de investigación unificada define un idioma común y proporciona una experiencia unificada para las investigaciones automáticas en [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para endpoint y Microsoft Defender [para Office 365](../office-365-security/defender-for-office-365.md). Para acceder a la página de investigación unificada, seleccione el vínculo en el banner amarillo que verá en:
- Cualquier página de investigación en el Centro Office 365 seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) )
- Cualquier página de investigación del Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
- Cualquier incidente o experiencia del Centro de acción en el centro de Microsoft 365 de seguridad mejorado ( [https://security.microsoft.com](https://security.microsoft.com) )

## <a name="open-the-investigation-details-view"></a>Abrir la vista de detalles de la investigación

Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:
- [Seleccionar un elemento en el centro de actividades](#select-an-item-in-the-action-center)
- [Seleccionar una investigación en una página de detalles de un incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Seleccionar un elemento en el centro de actividades

El Centro [de acción](m365d-action-center.md) mejorado ( ) reúne acciones de corrección en todos los dispositivos, correo electrónico & contenido de colaboración e [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) [](m365d-remediation-actions.md) identidades. Las acciones enumeradas incluyen acciones de corrección que se realizaron de forma automática o manual. En el Centro de acciones, puede ver las acciones que están esperando la aprobación y las acciones que ya se aprobaron o completaron. También puede navegar a más detalles, como una página de investigación.

> [!TIP]
> Debe tener [ciertos permisos para](m365d-action-center.md#required-permissions-for-action-center-tasks) aprobar, rechazar o deshacer acciones.

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En la pestaña **pendiente** o **historial**, seleccione un elemento. Se abre el panel desplegable.

4. Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.
   - Seleccione **Ir a la búsqueda** para ir a Búsqueda [avanzada.](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>Abrir una investigación desde una página de detalles de un incidente

Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.

![Detalles del incidente](../../media/mtp-incidentdetails-tabs.png)

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Incidentes &**  >  **alertas incidentes**. 

3. Seleccione un elemento de la lista y, a continuación, elija **Abrir página de incidentes**.

4. Seleccione la **pestaña Investigaciones** y, a continuación, seleccione una investigación en la lista. Se abre el panel desplegable.

5. Seleccione **Abrir página de investigación**. 

## <a name="investigation-details"></a>Detalles de la investigación

Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación. La vista de detalles de la investigación es similar a la siguiente imagen:

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.

> [!NOTE]
> Las pestañas específicas que se ven en una página de detalles de investigación dependen de lo que incluya la suscripción. Por ejemplo, si su suscripción no incluye Microsoft Defender para Office 365 plan 2, no verá una pestaña **Buzones.**

| Pestaña | Descripción |
|:--------|:--------|
| **Gráfico de investigación**   | Proporciona una representación visual de la investigación. Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.<br/>Puede seleccionar un elemento en el gráfico para ver más detalles. Por ejemplo, al seleccionar el icono  **Evidencia,** te llevará a la pestaña Evidencia, donde puedes ver las entidades detectadas y sus veredictos. |
| **Alertas**    | Muestra las alertas relacionadas con la investigación. Las alertas pueden venir de características de protección contra amenazas en el dispositivo de un usuario, en Office aplicaciones, Cloud App Security y otras características de Microsoft 365 Defender.|
| **Dispositivos** | Enumera los dispositivos incluidos en la investigación junto con su nivel de corrección. (Los niveles de corrección corresponden [al nivel de automatización de los grupos de dispositivos](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)).) |
| **Buzones** |Enumera los buzones que se verán afectados por las amenazas detectadas.  |
| **Users**  | Enumera las cuentas de usuario afectadas por las amenazas detectadas. |
| **Evidencia** | Enumera partes de evidencias generadas por alertas/investigaciones. Incluye veredictos ( Malintencionado , *Sospechoso* o *No se encontraron* amenazas ) y estado de corrección. |
| **Entities**  | Proporciona detalles sobre cada entidad analizada, incluido un veredicto para cada tipo de entidad ( Malintencionada , *Sospechosa* o *Sin amenazas encontradas*).|
|**Log**    | Proporciona una vista cronológica y detallada de todas las acciones de investigación realizadas después de desencadenar una alerta.|
| **Acciones pendientes** | Muestra los elementos que necesitan aprobación para continuar. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) para aprobar acciones pendientes. |

## <a name="next-steps"></a>Pasos siguientes

- [Aprobar o rechazar acciones de corrección tras una investigación automatizada](m365d-autoir-actions.md)
- [Más información sobre las acciones de corrección](m365d-remediation-actions.md)
