---
title: Ver los detalles y los resultados de una investigación automatizada
description: Durante y después de una investigación automatizada, puede ver los resultados y los resultados clave
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 8ecf39090d368427c103c7ec78e22bc13f7c339f
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591773"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Ver los detalles y los resultados de una investigación automatizada

**Se aplica a:**
- Microsoft Defender para punto de conexión

Con Microsoft Defender para [](automated-investigations.md) endpoint, cuando se ejecuta una investigación automatizada, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado. Si tiene los permisos necesarios, puede ver esos detalles en la vista de detalles de la investigación. La vista de detalles de la investigación ofrece un estado actualizado y la capacidad de aprobar las acciones pendientes. 

## <a name="new-unified-investigation-page"></a>(¡NUEVO!) Página de investigación unificada

La página de investigación se actualizó recientemente para incluir información en los dispositivos, el correo electrónico y el contenido de colaboración. La nueva página de investigación unificada define un idioma común y proporciona una experiencia unificada para las investigaciones automáticas en [Microsoft Defender](microsoft-defender-endpoint.md)  para Endpoint y Microsoft Defender para [Office 365](/microsoft-365/security/office-365-security/office-365-atp). 

> [!TIP]
> Para obtener más información sobre lo que está cambiando, vea [(¡NUEVO!) Página de investigación unificada](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Abrir la vista de detalles de la investigación

Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:
- [Seleccionar un elemento en el centro de actividades](#select-an-item-in-the-action-center)
- [Seleccionar una investigación en una página de detalles de un incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Seleccionar un elemento en el centro de actividades

El Centro [de acción mejorado](auto-investigation-action-center.md) reúne acciones de [corrección](manage-auto-investigation.md#remediation-actions) en todos los dispositivos, correo & contenido de colaboración e identidades. Las acciones enumeradas incluyen acciones de corrección que se realizaron de forma automática o manual. En el Centro de acciones, puede ver las acciones que están esperando la aprobación y las acciones que ya se aprobaron o completaron. También puede navegar a más detalles, como una página de investigación.

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

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 
2. En el panel de navegación, elija **Incidentes &**  >  **alertas incidentes**. 
3. Seleccione un elemento de la lista y, a continuación, elija **Abrir página de incidentes**.
4. Seleccione la **pestaña Investigaciones** y, a continuación, seleccione una investigación en la lista. Se abre el panel desplegable.
5. Seleccione **Abrir página de investigación**. 

## <a name="investigation-details"></a>Detalles de la investigación

Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación. La vista de detalles de la investigación es similar a la siguiente imagen:

En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.

> [!NOTE]
> Las pestañas específicas que se ven en una página de detalles de investigación dependen de lo que incluya la suscripción. Por ejemplo, si su suscripción no incluye Microsoft Defender para Office 365 Plan 2, no verá una pestaña **Buzones.**

| Pestaña | Descripción |
|:--------|:--------|
| **Gráfico de investigación**   | Proporciona una representación visual de la investigación. Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.<br/>Puede seleccionar un elemento en el gráfico para ver más detalles. Por ejemplo, al seleccionar el icono  **Evidencia,** te llevará a la pestaña Evidencia, donde puedes ver las entidades detectadas y sus veredictos. |
| **Alertas**    | Muestra las alertas relacionadas con la investigación. Las alertas pueden venir de características de protección contra amenazas en el dispositivo de un usuario, en aplicaciones de Office, Cloud App Security y otras características de Microsoft 365 Defender.|
| **Dispositivos** | Enumera los dispositivos incluidos en la investigación junto con su nivel de corrección. (Los niveles de corrección corresponden al [nivel de automatización de los grupos de dispositivos](automation-levels.md)).) |
| **Buzones** |Enumera los buzones que se verán afectados por las amenazas detectadas.  |
| **Usuarios**  | Enumera las cuentas de usuario afectadas por las amenazas detectadas. |
| **Evidencia** | Enumera partes de evidencias generadas por alertas/investigaciones. Incluye veredictos ( Malintencionado , *Sospechoso* o *No se encontraron* amenazas ) y estado de corrección. |
| **Entities**  | Proporciona detalles sobre cada entidad analizada, incluido un veredicto para cada tipo de entidad ( Malintencionada , *Sospechosa* o *Sin amenazas encontradas*).|
|**Log**    | Proporciona una vista cronológica y detallada de todas las acciones de investigación realizadas después de desencadenar una alerta.|
| **Acciones pendientes** | Muestra los elementos que necesitan aprobación para continuar. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) para aprobar acciones pendientes. |

## <a name="see-also"></a>Vea también

- [Revisar acciones de corrección tras una investigación automatizada](manage-auto-investigation.md)
- [Ver y organizar la cola de Microsoft Defender para incidentes de extremo](view-incidents-queue.md)