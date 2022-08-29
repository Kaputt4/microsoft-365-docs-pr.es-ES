---
title: Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Guía de instalación y configuración de aplicaciones con ámbito certificado para ServiceNow.
ms.openlocfilehash: 898b6a8f15d67fbf3530f6db269f47d5031f3676
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359239"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow

El siguiente contenido se aplica a la aplicación de integración de soporte técnico de Microsoft 365 con una versión mínima de **1.0.7**.

La **integración de soporte técnico de Microsoft 365** le permite integrar la ayuda, el soporte técnico y el estado del servicio de Microsoft 365 con las instancias de ServiceNow. Puede investigar problemas conocidos y notificados de Microsoft, resolver incidentes, completar tareas mediante soluciones recomendadas por Microsoft y, si es necesario, escalar al soporte técnico asistido por personas de Microsoft.

Para la aplicación de **integración de soporte técnico de Microsoft 365** desde la tienda ServiceNow, vaya a [ServiceNow Store](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

## <a name="key-features"></a>Características principales

Estas son las características clave que obtendrá con la aplicación de integración de soporte técnico de Microsoft 365 en la instancia de ServiceNow:

- Incidentes de mantenimiento del servicio: información sobre incidentes conocidos de mantenimiento del servicio de Microsoft, incluidos el impacto del usuario, el ámbito, el estado actual y la próxima actualización esperada. Con el aprendizaje automático, los incidentes de ServiceNow coinciden con los incidentes de mantenimiento del servicio de Microsoft en función del campo de descripción breve.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="Campo de descripción de incidentes de mantenimiento del servicio.":::

- Soluciones recomendadas: se usan descripciones de tareas e incidentes para recomendar soluciones específicas y artículos pertinentes de Microsoft con tecnología de aprendizaje automático. También puede usar Buscar para buscar otras soluciones, si es necesario.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="Campo de descripción de soluciones recomendadas.":::

- Solicitud de servicio de Microsoft: escale los problemas a los agentes de soporte técnico de Microsoft y reciba actualizaciones de estado para su caso.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="Formulario de solicitud de servicio.":::

## <a name="prerequisites"></a>Requisitos previos

### <a name="permissions-requirements"></a>Requisitos de permisos

Para continuar con esta guía, asegúrese de que los siguientes permisos están disponibles y configurados para los entornos durante todo el proceso:

- Administrador de Azure Active Directory (AAD) que puede crear aplicaciones de Azure AD

- Administrador de ServiceNow

- Administrador de inquilinos de Microsoft 365

### <a name="configuration-highlights"></a>Resaltados de configuración

Para configurar la **integración de soporte técnico de Microsoft 365**:

- Registre aplicaciones en Microsoft Azure Active Directory (AAD) para la autenticación de llamadas API salientes y entrantes.

- Cree entidades de ServiceNow con Microsoft Azure AD Application para el flujo de datos saliente y entrante.

- Integre la instancia de ServiceNow con soporte técnico de Microsoft a través del portal de administración de Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="Diagrama de integración de ServiceNow.":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>Dependencias de la aplicación en los entornos de ServiceNow

Permisos necesarios:

- entidad oauth\_

- Perfil de entidad\_de oauth\_

Una vez instalada la aplicación de integración de soporte técnico de Microsoft 365, se crean dos accesos entre ámbitos de aplicación. Si no se crean correctamente, créelas manualmente.

## <a name="setup-the-integration"></a>Configuración de la integración

Después de descargar la aplicación, vaya al Asistente para la instalación de Microsoft 365 en el entorno de SNOW para completar el proceso de instalación.
:::image type="content" source="../../media/154124985-76e13e7d-b32e-4741-830b-bbb110d3ecbf.png" alt-text="Asistente para instalación de nieve":::

Para obtener más información sobre los pasos, visite las páginas siguientes:
- Si el entorno de ServiceNow permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas de servicio web entrantes, siga las instrucciones de Configuración de la [integración de soporte técnico de Microsoft 365 con la autenticación básica de ServiceNow](servicenow-basic-authentication.md).
- Si el entorno de ServiceNow NO permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas de servicio web entrantes, siga las instrucciones de Configuración de la [integración de soporte técnico de Microsoft 365 con el token de autenticación de Azure AD](servicenow-aad-oauth-token.md).
  - Esta configuración requerirá un inquilino de SSO para que el token de autenticación de AAD funcione correctamente.

Para comprender cada característica, consulte [Integración de soporte técnico de Microsoft 365](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

> [!NOTE]
> Esta aplicación no se admite en entornos regulados o restringidos.

> [!IMPORTANT]
> En ocasiones, la aplicación de integración de soporte técnico de Microsoft 365 solicitará a los usuarios comentarios sobre la aplicación. Si no desea que se le pidan comentarios a los usuarios, desactive esta funcionalidad en la configuración de la aplicación. Para obtener más información sobre las directivas de comentarios de Microsoft, consulte [Información sobre los comentarios de Microsoft para su organización](/microsoft-365/admin/misc/feedback-user-control). Para cambiar la configuración de comentarios, siga los pasos del proceso de instalación.
