---
title: Microsoft 365 la integración de soporte técnico para incidentes de mantenimiento del servicio y soluciones recomendadas solamente
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
ms.openlocfilehash: bbe0f34a4252418cd3f989b871507df721a779a1
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62294875"
---
# <a name="microsoft-365-support-integration-for-service-health-incidents-and-recommended-solutions-only"></a>Microsoft 365 la integración de soporte técnico para incidentes de mantenimiento del servicio y soluciones recomendadas solamente

Esta configuración no permite crear un caso con soporte técnico de Microsoft a través de la instancia de ServiceNow. Esta opción solo proporciona la información sobre incidentes de mantenimiento del servicio y las soluciones de recomendación disponibles a través de la instancia de ServiceNow.

## <a name="prerequisites-service-health-incidents-and-recommended-solutions-only"></a>Requisitos previos (Solo incidentes de mantenimiento del servicio y soluciones recomendadas)

Estos requisitos previos son necesarios para configurar la Microsoft 365 **la integración de soporte técnico**.

1. \[AAD administrador\] Cree Azure AD de salida en su Microsoft 365 inquilino.

    1. Inicie sesión en Azure Portal con las Microsoft 365 de inquilino y cree una nueva aplicación en la [página Registros de aplicaciones](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade).

    2. Seleccione **Cuentas solo en este directorio de la organización ({Microsoft-365-tenant-name} only – Single tenant)** y, a continuación, **seleccione Registrar**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y **seleccione Agregar una plataforma**. Seleccione la **opción Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[Administrador de ServiceNow\] Configure el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, vaya a **Configuración &gt; Developer &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/Servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/Servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Cree una nueva aplicación mediante el Conectar a una opción proveedor **de OAuth** de terceros y especificando estos valores:

    - Id. de cliente: este es el identificador de cliente de la aplicación creada en requisitos previos (Ideas SOLO) paso \#1.

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en requisitos previos (Ideas SOLO) paso \#1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configurar la aplicación Microsoft 365 integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[Administrador de ServiceNow\] Cambie el ámbito a **Microsoft 365 la integración de soporte técnico**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[Administrador de ServiceNow\] Vaya **a Microsoft 365 configuración de soporte &gt; técnico para** abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauthentity\_' from scope 'xmiomsm365assis\_\_\_' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación &gt; Puede leer** se comprueban para la oauthentity\_ de la tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Seleccione **Aceptar** continuar.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure el proveedor de OAuth saliente.

    Seleccione el perfil de OAuth para el proveedor de OAuth saliente y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Omitir el proveedor de OAuth entrante.

    Compruebe **Omitir paso actual** y, a continuación, **seleccione Siguiente**.

1. \[Administrador de ServiceNow\] Omitir el usuario de integración de llamadas entrantes.

    Compruebe **Omitir paso actual** y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image34.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image34.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure el id. de repositorio.

    Especifique el identificador del repositorio y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Configurar la aplicación Configuración.

    Seleccione esta configuración y, a continuación, **seleccione Siguiente**:

    - SSO con Microsoft 365: compruebe si la instancia de ServiceNow está configurada como SSO con Microsoft 365 inquilinos, de lo contrario desactíquela.

    - Microsoft 365 correo electrónico de administrador: el correo electrónico del Microsoft 365 de administrador al que se contacta cuando se Microsoft 365 casos de soporte técnico.

    - Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Microsoft 365 de inquilinos\] Complete la integración.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image35.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image35.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Administración de Microsoft 365 Portal Configuración &gt; &gt; Configuración de la organización Perfiles &gt; de organización**.

1. Configure las opciones de integración de compatibilidad:

    Seleccione la **pestaña Información básica >** **Herramienta** >  de soporte técnico **internoServiceNow** y escriba el valor **de Identificador** de aplicación saliente en el id. de aplicación para emitir el **campo Token de** autenticación. Este identificador de aplicación saliente se encuentra en el paso 6: completar la integración, que se creó en el paso 1 requisitos previos [(Ideas solo\#).](#prerequisites-service-health-incidents-and-recommended-solutions-only)

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. En la **pestaña Repositorios** , **seleccione Nuevo repositorio y** actualícelo con la siguiente configuración:

    - Repositorio: el valor **de id. de** repositorio del paso 6: completar la integración.

    - Punto de conexión: **el valor** de extremo del paso 6: completar la integración.

    - Tipo de autenticación: **seleccione AAD Auth**.

    - Id. de cliente: valor aleatorio (ejemplo: omitido).

    - Rest username: un valor aleatorio (por ejemplo: omitido).

    - Rest user password: A random value (example: ignored).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image36.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image36.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. Vuelva a ServiceNow.

1. Seleccione **Siguiente** para completar la integración.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image37.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image37.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Habilite la integración de soporte técnico de Microsoft para un usuario existente.

    Microsoft 365 la integración de soporte técnico está habilitada para el usuario con uno de estos roles:

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

    > [!NOTE]
    > El usuario con el rol xmiomsm365assis.insightsuser\_\_\_\_ puede ver Service Health Incidents, Recommended Solutions. El usuario con el rol xmiomsm365assis.administrator\_\_\_ también puede abrir un caso con Microsoft 365 compatibilidad. Con Ideas SOLO, no se debe asignar a nadie el rol xmiomsm365assis.administrator\_\_\_.
