---
title: Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de instalación y configuración de aplicaciones con ámbito certificado para ServiceNow.
ms.openlocfilehash: cb36dfa2f0c27eee6112e7512a3dbc474c1dcf32
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68735713"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Información general de configuración de compatibilidad de Microsoft 365 con ServiceNow

El siguiente contenido se aplica a la aplicación de integración de soporte técnico de Microsoft 365 con una versión mínima de **1.0.7**.

La **integración de soporte técnico de Microsoft 365** le permite integrar la ayuda, el soporte técnico y el estado del servicio de Microsoft 365 con las instancias de ServiceNow. Puede investigar problemas conocidos y notificados de Microsoft, resolver incidentes, completar tareas mediante soluciones recomendadas por Microsoft y, si es necesario, escalar al soporte técnico asistido por personas de Microsoft.

Para la aplicación de **integración de soporte técnico de Microsoft 365** desde la tienda ServiceNow, vaya a [ServiceNow Store](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

## <a name="key-features"></a>Características principales

Estas son las características clave que obtendrá con la aplicación de integración de soporte técnico de Microsoft 365 en la instancia de ServiceNow:

- Incidentes de mantenimiento del servicio: información sobre incidentes conocidos de mantenimiento del servicio de Microsoft, incluidos el impacto del usuario, el ámbito, el estado actual y la próxima actualización esperada. Con el aprendizaje automático, los incidentes de ServiceNow coinciden con los incidentes de mantenimiento del servicio de Microsoft en función del campo de descripción breve.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow_service_health_incidents.png" lightbox="../../media/ServiceNow-guide/servicenow_service_health_incidents.png" alt-text="Campo de descripción de incidentes de mantenimiento del servicio.":::

- Soluciones recomendadas: se usan descripciones de tareas e incidentes para recomendar soluciones específicas y artículos pertinentes de Microsoft con tecnología de aprendizaje automático. También puede usar Buscar para buscar otras soluciones, si es necesario.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow_recommended_articles.png" lightbox="../../media/ServiceNow-guide/servicenow_recommended_articles.png" alt-text="Campo de descripción de soluciones recomendadas.":::

- Solicitud de servicio de Microsoft: escale los problemas a los agentes de soporte técnico de Microsoft y reciba actualizaciones de estado para su solicitud. Con un flujo de trabajo actualizado, ahora puede crear una solicitud de servicio agregando su título, descripción e información de contacto preferidas similares a las que se encuentran en el portal de administración de Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/SNOW_escalation.png" lightbox="../../media/ServiceNow-guide/SNOW_escalation.png" alt-text="Captura de pantalla que muestra el campo de descripción de soluciones recomendadas.":::

    :::image type="content" source="../../media/ServiceNow-guide/SNOW_escalation2.png" lightbox="../../media/ServiceNow-guide/SNOW_escalation2.png" alt-text="Captura de pantalla que muestra el campo de descripción de soluciones recomendadas.":::

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

## <a name="set-up-the-integration"></a>Configuración de la integración

Después de descargar la aplicación, vaya al Asistente para la instalación de Microsoft 365 en el entorno de SNOW para completar el proceso de instalación.

:::image type="content" source="../../media/ServiceNow-guide/Agree.png" lightbox="../../media/ServiceNow-guide/Agree.png" alt-text="Captura de pantalla que muestra el campo de descripción de soluciones recomendadas.":::

Para obtener más información sobre los pasos, visite las páginas siguientes:
- Si desea empezar a trabajar sin configurar la aplicación de integración de soporte técnico de Microsoft 365, puede seleccionar la opción **Continuar sin ninguna configuración** . Esta opción seguirá proporcionando soluciones recomendadas básicas.

    :::image type="content" source="../../media/ServiceNow-guide/No_setup.png" lightbox="../../media/ServiceNow-guide/No_setup.png" alt-text="Campo de descripción de soluciones recomendadas.":::
    
- Si el entorno de ServiceNow permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas de servicio web entrantes, siga las instrucciones de Configuración de la [integración de soporte técnico de Microsoft 365 con la autenticación básica de ServiceNow](servicenow-basic-authentication.md).
- Si el entorno de ServiceNow NO permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas de servicio web entrantes, siga las instrucciones de Configuración de la [integración de soporte técnico de Microsoft 365 con el token de autenticación de Azure AD](servicenow-aad-oauth-token.md).
  - Esta configuración requerirá un inquilino de SSO para que el token de autenticación de AAD funcione correctamente.

Para comprender cada característica, consulte [Integración de soporte técnico de Microsoft 365](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

> [!NOTE]
> Esta aplicación no se admite en entornos regulados o restringidos.

> [!IMPORTANT]
> En ocasiones, la aplicación de integración de soporte técnico de Microsoft 365 solicitará a los usuarios comentarios sobre la aplicación. Si no desea que se le pidan comentarios a los usuarios, desactive esta funcionalidad en la configuración de la aplicación. Para obtener más información sobre las directivas de comentarios de Microsoft, consulte [Información sobre los comentarios de Microsoft para su organización](/microsoft-365/admin/misc/feedback-user-control). Para cambiar la configuración de comentarios, siga los pasos del proceso de instalación.
