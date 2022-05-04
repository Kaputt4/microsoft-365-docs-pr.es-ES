---
title: Visualización del estado del servicio de inquilino en Microsoft 365 Lighthouse
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
ms.openlocfilehash: 8ad96c77f14148fefd6d00cd51af093cd081d857
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187830"
---
# <a name="view-tenant-service-health-in-microsoft-365-lighthouse"></a>Visualización del estado del servicio de inquilino en Microsoft 365 Lighthouse

Puede ver el estado del servicio de los inquilinos que administra en Microsoft 365 Lighthouse. Estado del servicio incluye incidentes y avisos para varios servicios, incluidos Microsoft Intune, servicios de identidad de Azure Active Directory (Azure AD) y servicios en la nube de administración de dispositivos móviles (MDM). También puede ver cuántos de los inquilinos administrados se ven afectados por incidentes. Por ejemplo, si uno de los inquilinos tiene problemas, puede comprobar la página de Estado del servicio para determinar si se trata de un problema conocido con una resolución en curso o si un cambio reciente puede afectar a ellos. Esto podría ahorrarle tiempo para solucionar problemas y reducir las llamadas de soporte técnico.

Si no puede iniciar sesión en Lighthouse, puede usar la [página Microsoft 365 estado de mantenimiento del servicio](https://status.office365.com/) para comprobar si hay problemas conocidos que le impidan iniciar sesión en el inquilino del asociado. Además, regístrese para seguir [@MSFT365status](https://twitter.com/MSFT365Status) en Twitter para ver información sobre incidentes de servicio específicos.

## <a name="before-you-begin"></a>Antes de empezar

Para ver el estado del servicio, necesitará un rol de Azure AD en el inquilino del asociado con el siguiente conjunto de propiedades: **microsoft.office365.serviceHealth/allEntities/allTasks**. Para obtener una lista de Azure AD roles, consulte [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

## <a name="view-service-health-status-for-all-tenants"></a>Visualización del estado de mantenimiento del servicio para todos los inquilinos

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Estado del servicio**.

2. En la página **Estado del servicio**, revise el estado de mantenimiento del servicio actual, incluido:

   - Número total de incidentes
   - Número total de avisos que afectan a cualquiera de los inquilinos administrados
   - Número de servicios con incidentes activos.

3. En la pestaña **Todos los servicios** , revise los problemas por servicio.

4. En la pestaña **Todos los problemas** , revise todos los problemas actuales.

## <a name="review-issue-details"></a>Revisión de los detalles del problema

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Estado del servicio**.

2. En la página **Estado del servicio**, seleccione la pestaña **Todos los servicios** o **Todos los problemas**.

3. Seleccione un problema de la lista.

4. En el panel de detalles del problema, revise la información detallada, incluido el tipo de problema, los inquilinos afectados, el impacto del usuario y el historial de problemas.

En la pestaña **Inquilinos afectados** , puede exportar una lista de inquilinos afectados a un archivo de valores separados por comas (.csv) para que pueda compartirlo con los equipos de soporte técnico.

## <a name="related-content"></a>Contenido relacionado

[Cómo comprobar Microsoft 365 estado del servicio](/microsoft-365/enterprise/view-service-health) (artículo)\
[Problemas conocidos con Microsoft 365 Lighthouse](m365-lighthouse-known-issues.md) (artículo)\
[Ver los roles de Azure Active Directory en Microsoft 365 Lighthouse](m365-lighthouse-view-your-roles.md) (artículo)
