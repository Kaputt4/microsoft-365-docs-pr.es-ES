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
ms.openlocfilehash: 28b156cc9f9062863868550f2aac216b8d92a403
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754204"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow

**Microsoft 365 la integración** de soporte técnico le permite integrar Microsoft 365 ayuda, soporte técnico y estado del servicio con las instancias de ServiceNow. Puede investigar problemas conocidos y notificados de Microsoft, resolver incidentes, completar tareas mediante soluciones recomendadas de Microsoft y, si es necesario, escalar a soporte técnico con ayuda humana de Microsoft.

Para obtener **Microsoft 365 la aplicación de integración** de soporte técnico de la tienda ServiceNow, vaya a la Tienda [ServiceNow](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

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

- Azure Active Directory administrador (AAD) que puede crear AAD aplicaciones

- Administrador de ServiceNow

- Microsoft 365 de inquilinos

### <a name="configuration-highlights"></a>Aspectos destacados de la configuración

Para configurar la **Microsoft 365 la integración de soporte técnico:**

- Registrar aplicaciones en Microsoft Azure Active Directory (AAD) para la autenticación de llamadas DE API salientes y entrantes.

- Cree entidades de ServiceNow con Microsoft AAD aplicación para el flujo de datos entrante y saliente.

- Integre la instancia de ServiceNow con el soporte técnico de Microsoft a través Microsoft 365 de administración.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="Diagrama de integración de ServiceNow.":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>Dependencias de aplicaciones en los entornos de ServiceNow

Permisos necesarios:

- entidad \_ oauth

- Perfil de \_ entidad de \_ oauth

Después de Microsoft 365 se haya instalado la aplicación de integración de soporte técnico, se crean dos accesos entre ámbitos de aplicación. Si no se crean correctamente, creó manualmente.

## <a name="what-features-will-work-for-your-organization-based-on-your-configuration"></a>¿Qué características funcionarán para la organización en función de la configuración?

Antes de configurar cualquier configuración para la Microsoft 365 la integración de soporte técnico, revise sus respuestas a estas preguntas:

**Pregunta \# 1:**¿El entorno de ServiceNow permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas entrantes al servicio web?

**Pregunta \# 2:** Si tiene varios inquilinos, ¿tiene previsto usar un único espacio empresarial integrado con el entorno de ServiceNow para Microsoft 365 integración de soporte técnico?

En función de las respuestas a las preguntas anteriores, esta tabla le indica qué características están disponibles y cómo configurar la integración Microsoft 365 compatibilidad. Para obtener una descripción de cada característica, [vea Microsoft 365 la integración de soporte técnico](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

| Respuesta \# de la pregunta 1 | Respuesta \# de la pregunta 2 | ¿Qué características están disponibles? | Pasos de la configuración  |
|---------------------|---------------------|-----------|----------------|
| Sí                 | Sí/No              | Service Health Incidents Recommended Solutions Microsoft service request | [Configurar la Microsoft 365 compatibilidad con la autenticación básica de ServiceNow](servicenow-basic-authentication.md) |
| No                  | Sí                 | Service Health Incidents Recommended Solutions Microsoft service request | [Configurar la Microsoft 365 la integración con AAD token de OAuth](servicenow-aad-oauth-token.md)                 |
| No                  | No                  | Soluciones recomendadas para incidentes de mantenimiento de servicio                           | [Configurar la Microsoft 365 de compatibilidad para Ideas SOLO](servicenow-service-health-incidents-solutions-only.md)                    |
