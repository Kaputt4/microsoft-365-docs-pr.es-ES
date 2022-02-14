---
title: Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de configuración y instalación de aplicaciones certificadas con ámbito para ServiceNow.
ms.openlocfilehash: 0629b322a52702ef293ff1f73661359b410f2d69
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806017"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow

**Microsoft 365 la integración** de soporte técnico le permite integrar Microsoft 365 ayuda, soporte técnico y estado del servicio con las instancias de ServiceNow. Puede investigar problemas conocidos y notificados de Microsoft, resolver incidentes, completar tareas mediante soluciones recomendadas de Microsoft y, si es necesario, escalar a soporte técnico con ayuda humana de Microsoft.

Para obtener **Microsoft 365 la aplicación de integración** de soporte técnico de la tienda ServiceNow, vaya a [la Tienda ServiceNow](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

## <a name="key-features"></a>Características principales

Estas son las características clave que se obtienen con la aplicación Microsoft 365 de integración de soporte técnico en la instancia de ServiceNow:

- Incidentes de estado del servicio: información sobre los incidentes de mantenimiento del servicio de Microsoft conocidos, incluidos el impacto del usuario, el ámbito, el estado actual y la próxima actualización esperada. Con el aprendizaje automático, los incidentes de ServiceNow coinciden con los incidentes de estado del servicio de Microsoft en función del campo de descripción breve.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="Campo Descripción de incidentes de estado del servicio.":::

- Soluciones recomendadas: las descripciones de tareas e incidentes se usan para recomendar soluciones específicas y artículos relevantes de Microsoft con tecnología de aprendizaje automático. También puede usar la búsqueda para buscar otras soluciones, si es necesario.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="Campo de descripción de soluciones recomendado.":::

- Solicitud de servicio de Microsoft: Escala los problemas a los agentes de soporte técnico de Microsoft y recibe actualizaciones de estado para tu caso.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="Formulario de solicitud de servicio.":::

## <a name="prerequisites"></a>Requisitos previos

### <a name="permissions-requirements"></a>Requisitos de permisos

Para continuar con esta guía, asegúrese de que los siguientes permisos están disponibles y configurados para los entornos durante todo el proceso:

- Azure Active Directory administrador (AAD) que puede crear aplicaciones Azure AD web

- Administrador de ServiceNow

- Microsoft 365 de inquilinos

### <a name="configuration-highlights"></a>Aspectos destacados de la configuración

Para configurar la **Microsoft 365 la integración de soporte técnico**:

- Registrar aplicaciones en Microsoft Azure Active Directory (AAD) para la autenticación de llamadas DE API salientes y entrantes.

- Cree entidades de ServiceNow con Microsoft Azure AD aplicación para el flujo de datos salientes y entrantes.

- Integre la instancia de ServiceNow con el soporte técnico de Microsoft a través Microsoft 365 de administración.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="Diagrama de integración de ServiceNow.":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>Dependencias de aplicaciones en los entornos de ServiceNow

Permisos necesarios:

- oauthentity\_

- oauthentityprofile\_\_

Después de Microsoft 365 se haya instalado la aplicación de integración de soporte técnico, se crean dos accesos entre ámbitos de aplicación. Si no se crean correctamente, creó manualmente.

## <a name="what-configuration-is-right-for-your-organization"></a>¿Qué configuración es adecuada para su organización?

Antes de configurar cualquier configuración para la Microsoft 365 la integración de soporte técnico, comprenda cómo se configura el entorno de ServiceNow.

- Si el entorno de ServiceNow permite la autenticación básica (acceso con la credencial de usuario de ServiceNow) para las llamadas entrantes al servicio web, siga las instrucciones de Configurar Microsoft 365 la integración de soporte técnico con la autenticación básica de [ServiceNow](servicenow-basic-authentication.md).
- Si el entorno servicenow no permite la autenticación básica (acceso con la credencial de usuario de ServiceNow) para las llamadas entrantes al servicio web, siga las instrucciones en Configurar Microsoft 365 la integración de compatibilidad con Azure AD [token](servicenow-aad-oauth-token.md) de autenticación.
  - Esta configuración requerirá un inquilino de SSO para que AAD token de autenticación funcione correctamente.

Para comprender cada característica, consulte [Microsoft 365 la integración de soporte técnico](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).
