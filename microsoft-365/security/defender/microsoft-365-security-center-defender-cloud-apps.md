---
title: Microsoft Defender for Cloud Apps en Microsoft 365 Defender (versión preliminar)
description: Obtenga información sobre los cambios de la Microsoft Defender for Cloud Apps a Microsoft 365 Defender
keywords: Introducción a Microsoft 365 Defender, Microsoft Defender for Cloud Apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 05/03/2022
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 9113e3f06ba0f9c8cbec0da6d738cc170a215771
ms.sourcegitcommit: 44ece87e3e0c0c851dfc1e77211ac3e5e4a5b973
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66998378"
---
# <a name="microsoft-defender-for-cloud-apps-in-microsoft-365-defender-preview"></a>Microsoft Defender for Cloud Apps en Microsoft 365 Defender (versión preliminar)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Cloud Apps](/defender-cloud-apps/)

Microsoft Defender for Cloud Apps ahora forma parte de Microsoft 365 Defender. El portal de Microsoft 365 Defender permite a los administradores de seguridad realizar sus tareas de seguridad en una ubicación. Esto simplificará los flujos de trabajo y agregará la funcionalidad de los demás servicios de Microsoft 365 Defender. Microsoft 365 Defender será el hogar para supervisar y administrar la seguridad en las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura de Microsoft.

Los analistas de SOC podrán evaluar, investigar y buscar todas las cargas de trabajo Microsoft 365 Defender, incluidas las aplicaciones en la nube.
Las alertas de Defender for Cloud Apps seguirán apareciendo en la cola de incidentes y en la cola de alertas de Microsoft 365 Defender, pero ahora con contenido relevante dentro de las páginas de alertas disponibles en el portal de Microsoft 365 Defender, en un formato unificado con las adaptaciones adecuadas a cada tipo de alerta.

Eche un vistazo a Microsoft 365 Defender en <https://security.microsoft.com>.

Más información sobre las ventajas: [Información general de Microsoft 365 Defender](microsoft-365-defender.md).

## <a name="quick-reference"></a>Referencia rápida

La imagen y la tabla siguiente muestran los cambios en la navegación entre Microsoft Defender for Cloud Apps y Microsoft 365 Defender.

> [!NOTE]
> Algunas páginas aún no se han migrado y se debe acceder a ellas desde el portal de Defender for Cloud Apps.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender.png" alt-text="Nuevas ubicaciones en el portal de Microsoft 365 Defender" lightbox="../../media/defender-cloud-apps-m365-defender.png":::

| Defender for Cloud Apps | Microsoft 365 Defender |
|---------|---------|
| Panel de detección en la nube | Aplicaciones en la nube:> cloud discovery |
| Aplicaciones detectadas | pestaña de la página Cloud Discovery |
| Recursos detectados | pestaña de la página Cloud Discovery |
| Direcciones IP | pestaña de la página Cloud Discovery |
| Usuarios | pestaña de la página Cloud Discovery |
| Dispositivos | pestaña de la página Cloud Discovery |
| Catálogo de aplicaciones en la nube |  Aplicaciones en la nube: catálogo de aplicaciones en la nube > |
| Creación de un informe de instantáneas de Cloud Discovery | En la página Cloud Discovery, en Acciones |
| Registro de actividad | Aplicaciones en la nube: registro de actividad de > |
| Archivos | restante en el portal de Defender for Cloud Apps |
| Usuarios y cuentas | Recursos -> identidades |
| Configuración de seguridad | restante en el portal de Defender for Cloud Apps |
| Posición de seguridad de identidad | [Evaluaciones de la postura de posición de seguridad de identidad de Microsoft Defender for Identity](/defender-for-identity/isp-overview) |
| Aplicaciones OAuth | Aplicaciones en la nube:> aplicaciones de OAuth |
| Aplicaciones conectadas | restante en el portal de Defender for Cloud Apps |

> [!NOTE]
> La nueva experiencia de Defender for Cloud Apps en el portal de Microsoft 365 Defender está disponible actualmente para todos los usuarios detallados en [Administración del acceso de administrador](/defender-cloud-apps/manage-admins), excepto para:
> * **Administrador de aplicaciones o instancias**, **administrador de grupos** de usuarios, **administrador global de Cloud Discovery** y **administrador de informes de Cloud Discovery**, tal como se define [en Roles de administrador integrados en Defender for Cloud Apps](/defender-cloud-apps/manage-admins#built-in-admin-roles-in-defender-for-cloud-apps).
> * Grupos de privacidad de usuario definidos en [Privacidad de la actividad](/defender-cloud-apps/activity-privacy)

## <a name="whats-changed"></a>Modificaciones

Obtenga información sobre los cambios que se han producido con la integración de Defender for Cloud Apps y Microsoft 365 Defender.

### <a name="global-search"></a>Búsqueda global

La búsqueda global en Microsoft 365 Defender (con la barra de búsqueda de la parte superior de la página) ahora incluye una entidad de búsqueda adicional: permite buscar aplicaciones conectadas en Defender for Cloud Apps.

:::image type="content" source="../../media/global-search-apps.png" alt-text="Busque aplicaciones conectadas.":::

### <a name="assets-and-identities"></a>Recursos e identidades

Como parte de la creación de una sección **recursos** dedicados que abarca toda la experiencia de Microsoft 365 Defender, la sección **Usuarios y cuentas** de Defender for Cloud Apps se cambia de nombre como la sección **Identidades**. No se espera ningún cambio en la funcionalidad.

## <a name="related-information"></a>Información relacionada

- [Microsoft 365 Defender](microsoft-365-defender.md)
