---
title: Configurar Microsoft 365 de compatibilidad con Azure AD token de autenticación
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
description: Guía de configuración y instalación de aplicaciones certificadas con ámbito para ServiceNow.
ms.openlocfilehash: 9f9985e07989f168f9b27dde1c1d574813c3f349
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320905"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>Configurar Microsoft 365 de compatibilidad con Azure AD token de autenticación

## <a name="prerequisites-azure-ad-auth-token"></a>Requisitos previos (Azure AD token de autenticación)

Estos requisitos previos son necesarios para configurar la Microsoft 365 la integración de compatibilidad.

1. \[AAD administrador\] Cree Azure AD de salida en el espacio empresarial Microsoft 365 cliente.

    1. Inicie sesión en Azure Portal con las Microsoft 365 de inquilino y vaya a la página Registros [de](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) aplicaciones para crear una nueva aplicación.

    2. Seleccione **Cuentas solo en este directorio de la organización ({Microsoft-365-tenant-name} only – Single tenant)** y seleccione **Registrar**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y **seleccione Agregar una plataforma**. Seleccione la **opción Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[AAD administrador\] Cree una API Azure AD Application for Rest en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) sus Microsoft 365 de inquilino y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Cuentas en este directorio de la organización solo {(Microsoft-365-tenant-name} only – Single tenant)**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[AAD administrador\] Cree una aplicación Azure AD para el usuario de reposo en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) sus Microsoft 365 de inquilino y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Cuentas en este directorio de la organización solo {(Microsoft-365-tenant-name} only – Single tenant)**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[Administrador de ServiceNow\] Configure el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, para ello, vaya a **Configuración &gt; Aplicaciones &gt;** para desarrolladores y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Cree una nueva aplicación mediante la Conectar a una opción proveedor **de OAuth** de terceros y escriba estos valores:

    - Identificador de cliente: este es el identificador de cliente de la aplicación creada en requisitos previos (Azure AD token de autenticación) paso \#1.

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en requisitos previos (Azure AD token de autenticación) paso \#1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Para configurar el proveedor de OIDC en ServiceNow, consulte la [documentación en línea](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html).

    Si el ámbito no está establecido en **Global**, vaya a **Configuración &gt; Developer &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Seleccione **Nuevo** y, a continuación, **seleccione Crear nuevo proveedor de Conectar de identificación abierta**.

1. En **Configuración del proveedor OAuth OIDC**, seleccione **Buscar** y cree una nueva configuración de proveedor de OIDC en **oidcproviderconfiguration.list\_\_** con estos valores:

    - Proveedor de OIDC: **{TenantName\_} Azure** (ejemplo: Contoso Azure)

    - Dirección URL de metadatos de OIDC: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appid**

    - UserField: **Id. de usuario**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. Para crear una aplicación nueva, seleccione **Configurar un proveedor de OIDC para comprobar los tokens de id** . con estos valores:

    - Nombre: **{TenantName\_}\_applicationinboundapi\_\_** (ejemplo: contosoapplicationinboundapi\_\_\_)

    - Id. de cliente: el identificador de cliente de la aplicación creada en el paso 2 Azure AD de autenticación (token de \#autenticación).

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en requisitos previos (Azure AD token de autenticación) paso \#2.

    - Configuración del proveedor OAuth OIDC: el proveedor de OIDC creado en el paso anterior

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Crear usuarios de integración.

    Debe especificar un usuario de integración. Si no tiene un usuario de integración existente o si desea crear uno específicamente para esta integración, **&gt;** vaya a Usuarios de la organización para crear un nuevo usuario. El valor del **identificador de usuario** es el identificador de cliente de la aplicación creado en [Requisitos previos (Azure AD token de autenticación).](#prerequisites-azure-ad-auth-token).

    Si va a crear un nuevo usuario de integración, compruebe la opción **Solo acceso al servicio** web. También debe conceder a este usuario el rol **incidentmanager\_**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPCIONAL\] Permitir que las direcciones IP del servicio Microsoft 365 la integración de soporte técnico

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de integración de soporte técnico de Microsoft 365 al permitir las direcciones IP siguientes para el acceso a la API entrante y saliente.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para Microsoft 365 integración de soporte técnico:`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configurar la aplicación Microsoft 365 integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en la Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[Administrador de ServiceNow\] Cambie el ámbito a **Microsoft 365 la integración de soporte técnico**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[Administrador de ServiceNow\] Vaya **Microsoft 365 configuración de soporte &gt; técnico** para abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauthentity\_' from scope 'xmiomsm365assis\_\_\_' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación &gt; Puede leer** se comprueban para la oauthentity\_ de la tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Seleccione **Aceptar** el aviso de consentimiento para continuar.

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure el entorno y el tipo de configuración.
    Si esta instalación se encuentra en un entorno de prueba, seleccione la opción Este es un entorno de prueba. Podrás deshabilitar rápidamente esta opción después de la configuración y de que todas las pruebas se completen más adelante.
    Si la instancia permite la autenticación básica para las conexiones entrantes, seleccione Sí y consulte el proceso de configuración [de autenticación básica](servicenow-basic-authentication.md). De lo contrario, **seleccione No** y haga clic **en Iniciar configuración**. 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Escriba su Microsoft 365 inquilino.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configurar el proveedor de OAuth saliente.
    1. Configurar el proveedor de OAuth saliente.
    1. Después de completar las instrucciones de la sección requisitos previos, haga clic en Listo. De lo contrario, siga las instrucciones del asistente para crear el registro de aplicación necesario en AAD.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Registrar la aplicación OAuth de ServiceNow.
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione el registro de la aplicación OAuth recién creada y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo registro de la aplicación.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure Inbound settings.
    1. Configurar la aplicación AAD entrante.
    1. Después de completar las instrucciones de la sección requisitos previos, haga clic en Listo para ir al paso siguiente. De lo contrario, siga las instrucciones para crear el registro AAD aplicación para la conectividad entrante.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configurar el proveedor de Conectar openid externo de ServiceNow (proveedor de OIDC).
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione la entidad recién creada y haga clic en Listo. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo registro de la aplicación Proveedor externo de OIDC.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configure el registro AAD aplicación para el usuario de integración entrante.
    1. Después de completar las instrucciones de la sección requisitos previos, haga clic en Listo para ir al paso siguiente. De lo contrario, siga las instrucciones para crear el registro AAD aplicación para el usuario REST entrante (usuario de integración).
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configure el usuario de integración.
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione la entidad recién creada y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear el usuario de integración en ServiceNow y, a continuación, seleccione la entidad.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Microsoft 365 de inquilinos\] Complete la integración.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Vaya a **Administración de Microsoft 365 Configuración Configuración &gt; &gt; organización perfiles &gt; de organización**.

    1. Configure las opciones de integración de compatibilidad:

    Seleccione la **pestaña Información básica >** **Herramienta** >  de soporte **internoServiceNow** y escriba el valor **de Identificador** de aplicación saliente en el id. de aplicación para emitir el **campo Token de autenticación**. Este identificador de aplicación saliente se encuentra en el paso 6: completar la integración, que se creó en [Requisitos previos (Azure AD token de autenticación).](#prerequisites-azure-ad-auth-token).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. En la **pestaña Repositorios** , **seleccione Nuevo repositorio y** actualícelo con la siguiente configuración:

    - Repositorio: el valor **del id. de** repositorio del "Paso 6: completar la integración".

    - Punto de conexión: **el valor** del extremo de "Paso 6: completar la integración".

    - Tipo de autenticación: **seleccione AAD Auth**.

    - Id. de cliente: **valor de id.** de cliente del paso 6: completar la integración.

    - Secreto de cliente: el secreto del proveedor de OAuth entrante que se creó en requisitos previos (Azure AD token de autenticación) paso \#2.

    - Rest username: el valor **de Nombre** de usuario del paso 6: Completar la integración, que es el **identificador** de cliente de la aplicación creada en Prerequisites (Azure AD Auth Token) paso \#3.

    - Contraseña de usuario de reposo: el secreto de aplicación de la aplicación que se creó en requisitos previos (Azure AD token de autenticación) paso \#3.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

    1. Vuelva a ServiceNow.

    1. Seleccione **Siguiente** para completar la integración.

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    La Microsoft 365 de integración de soporte técnico ejecutará pruebas para garantizar que la integración funciona. Si hay un problema con la configuración, un mensaje de error explicará lo que debe solucionarse. De lo contrario, la aplicación está lista.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Habilite la integración de soporte técnico de Microsoft para un usuario existente.

    Microsoft 365 la integración de soporte técnico está habilitada para el usuario con uno de estos roles:

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[OPCIONAL\] \[El usuario con el rol xmiomsm365assis.administrator\_\_\_ vínculo\] Vínculo Microsoft 365 cuenta de administrador.

    Si algún usuario tiene el rol xmiomsm365assis.administrator\_\_\_ y usa diferentes cuentas de Microsoft 365 para administrar un caso de soporte técnico de Microsoft 365, debe ir Microsoft 365 la cuenta de vínculo de soporte técnico para &gt; configurar su correo electrónico de administrador Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::
