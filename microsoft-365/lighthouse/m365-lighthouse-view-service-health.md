---
title: Ver el estado del servicio de inquilino
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver el estado del servicio de inquilino.
ms.openlocfilehash: b7361865e0ad3f070e128207a92669f3515e9969
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62466158"
---
# <a name="view-tenant-service-health"></a>Ver el estado del servicio de inquilino

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplan los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, consulte [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Puede ver el estado del servicio para los inquilinos que administra en Microsoft 365 Lighthouse. El estado del servicio incluye incidentes y avisos para varios servicios, incluidos Microsoft Intune, servicios de identidad de Azure Active Directory (Azure AD) y servicios en la nube de administración de dispositivos móviles (MDM). También puede ver cuántos de los inquilinos administrados se ven afectados por incidentes. Por ejemplo, si uno de los inquilinos tiene problemas, puede comprobar la página Estado del servicio para determinar si se trata de un problema conocido con una resolución en curso o si un cambio reciente puede afectarles. Esto podría ahorrar tiempo para solucionar problemas y reducir las llamadas de soporte técnico.

Si no puede iniciar sesión en Lighthouse, puede usar la página de estado de estado del servicio de [Microsoft 365](https://status.office365.com/) para comprobar si hay problemas conocidos que le impidan iniciar sesión en el espacio empresarial asociado. Además, regístrate [para seguir @MSFT365status](https://twitter.com/MSFT365Status) twitter para ver información sobre incidentes de servicio específicos.

## <a name="before-you-begin"></a>Antes de empezar

Para ver el estado del servicio, necesitará un rol Azure AD en el inquilino asociado con el siguiente conjunto de propiedades: **microsoft.office365.serviceHealth/allEntities/allTasks**. Para obtener una lista de Azure AD funciones, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

## <a name="view-service-health-status-for-all-tenants"></a>Ver el estado del servicio para todos los inquilinos

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Estado del servicio**.

2. En la **página Estado del** servicio, revise el estado actual del servicio, incluidos:

   -   Número total de incidentes
   -   Número total de avisos que afectan a cualquiera de los inquilinos administrados
   -   Número de servicios con incidentes activos.

3. En la **pestaña Todos los servicios** , revise los problemas por servicio.

4. En la **pestaña Todos los problemas** , revise todos los problemas actuales.

## <a name="review-issue-details"></a>Revisar detalles de problemas

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Estado del servicio**.

2. En la **página Estado del** servicio, seleccione la **pestaña Todos los servicios** o **Todos los problemas** .

3. Seleccione un problema de la lista.

4. En el panel de detalles del problema, revise información detallada, incluido el tipo de problema, los inquilinos afectados, el impacto del usuario y el historial de problemas.

En la pestaña **Inquilinos** afectados, puede exportar una lista de inquilinos afectados a un archivo de valores separados comunes (.cvs) para que pueda compartirlo con los equipos de soporte técnico.

## <a name="related-content"></a>Contenido relacionado
[Cómo comprobar el estado Microsoft 365 servicio](/microsoft-365/enterprise/view-service-health) (artículo)
