---
title: Configuración de la integración de compatibilidad de Microsoft 365 con el token de autenticación de Azure AD
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
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de instalación y configuración de aplicaciones con ámbito certificado para ServiceNow.
ms.openlocfilehash: 6502e3301dab653c14980acb4e91f2dd8ed2a589
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68173135"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>Configuración de la integración de compatibilidad de Microsoft 365 con el token de autenticación de Azure AD

## <a name="prerequisites-azure-ad-auth-token"></a>Requisitos previos (token de autenticación de Azure AD)

Estos requisitos previos son necesarios para configurar la integración de soporte técnico de Microsoft 365.

1. \[AAD Administración\] Creación de una aplicación de Azure AD para salientes en el inquilino de Microsoft 365.

    1. Inicie sesión en Azure Portal con sus credenciales de inquilino de Microsoft 365 y vaya a la [página Registros de aplicaciones](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) para crear una nueva aplicación.

    2. Seleccione **Solo cuentas en este directorio organizativo ({Microsoft-365-tenant-name} - Solo inquilino único)** y seleccione **Registrar**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y seleccione **Agregar una plataforma**. Seleccione la opción **Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación, cree un secreto de cliente y obtenga ese valor.

1. \[AAD Administración\] Creación de una aplicación de Azure AD para rest API en el inquilino de Microsoft 365.

    1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con sus credenciales de inquilino de Microsoft 365 y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Solo cuentas en este directorio organizativo {(Microsoft-365-tenant-name}: inquilino único).**

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación, cree un secreto de cliente y obtenga ese valor.

1. \[AAD Administración\] Creación de una aplicación de Azure AD para el usuario rest en el inquilino de Microsoft 365.

    1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con sus credenciales de inquilino de Microsoft 365 y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Solo cuentas en este directorio organizativo {(Microsoft-365-tenant-name}: inquilino único).**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación, cree un secreto de cliente y obtenga ese valor.

1. \[ServiceNow Administración\] Configurar el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, para ello, vaya a **Configuración &gt; Aplicaciones para desarrolladores &gt;** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Cree una nueva aplicación con la opción **Conectarse a un proveedor de OAuth de terceros** y escriba estos valores:

    - Id. de cliente: este es el identificador de cliente de la aplicación creada en el paso \#1 de Requisitos previos (token de autenticación de Azure AD).

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en requisitos previos (token de autenticación de Azure AD) paso \#1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[ServiceNow Administración\] Para configurar el proveedor OIDC en ServiceNow, consulte la [documentación en línea](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html).

    Si el ámbito no está establecido en **Global**, vaya a **Configuración &gt; Aplicaciones para desarrolladores &gt;** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Seleccione **Nuevo** y, a continuación, **seleccione Crear nuevo proveedor de Open ID Connect**.

1. En **Configuración del proveedor OIDC de OAuth**, seleccione **Buscar** y cree una nueva configuración de proveedor OIDC en **oidc\_provider\_configuration.list** con estos valores:

    - Proveedor OIDC: **{Nombre de inquilino\_} Azure** (por ejemplo: Contoso Azure)

    - Dirección URL de metadatos de OIDC: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appid**

    - UserField: **Id. de usuario**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. Para crear una aplicación, seleccione **Configurar un proveedor OIDC para comprobar los tokens de identificador** con estos valores:

    - Nombre: **{Nombre del inquilino\_}\_API de entrada\_de la aplicación\_** (por ejemplo: api de entrada\_de aplicación\_contoso\_)

    - Id. de cliente: el identificador de cliente de la aplicación creada en el paso \#3 de Requisitos previos (token de autenticación de Azure AD).

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en requisitos previos (token de autenticación de Azure AD) paso \#3.

    - Configuración del proveedor OIDC de OAuth: el proveedor OIDC creado en el paso anterior

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[ServiceNow Administración\] Crear usuarios de integración.

    Debe especificar un usuario de integración. Si no tiene un usuario de integración existente o si desea crear uno específicamente para esta integración, vaya a Usuarios de **la organización &gt;** para crear un nuevo usuario. El valor del **identificador de usuario** es el identificador de cliente de la aplicación creado en [Requisitos previos (token de autenticación de Azure AD).](#prerequisites-azure-ad-auth-token)

    Si va a crear un nuevo usuario de integración, active la opción **Solo acceso al servicio web** . También debe conceder a este usuario el rol **de administrador de incidentes\_**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPCIONAL\] Permitir la integración de la compatibilidad con las direcciones IP del servicio en Microsoft 365

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de integración de soporte técnico de Microsoft 365 al permitir las direcciones IP siguientes para el acceso de API entrante y saliente.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para la integración de soporte técnico de Microsoft 365: `nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configuración de la aplicación de integración de soporte técnico de Microsoft 365

La aplicación de integración de soporte técnico de Microsoft 365 se puede configurar en soporte técnico de Microsoft 365.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y la compatibilidad con Microsoft 365.

1. \[ServiceNow Administración\] Cambie el ámbito a **la integración de soporte técnico de Microsoft 365**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[ServiceNow Administración\] Vaya al **programa de instalación de soporte técnico &gt; de Microsoft 365** para abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauth\_entity' from scope 'x\_mioms\_m365\_assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación que se pueden leer estén comprobados &gt;** para la entidad oauth\_de la tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] Seleccione **Aceptar** la solicitud de consentimiento para continuar.

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] Configurar el entorno y el tipo de instalación.
    Si esta instalación está en un entorno de prueba, seleccione la opción Este es un entorno de prueba. Podrá deshabilitar rápidamente esta opción después de la instalación y de que todas las pruebas se completen más adelante.
    Si la instancia permite la autenticación básica para las conexiones entrantes, seleccione Sí y consulte el [proceso de configuración de autenticación básica](servicenow-basic-authentication.md). De lo contrario, seleccione **No** y haga clic en **Iniciar configuración**. 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] Escriba su dominio de inquilino de Microsoft 365.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] configurar el proveedor de OAuth saliente.
    1. Configure el proveedor de OAuth de salida.
    1. Después de completar las instrucciones de la sección de requisitos previos, haga clic en Listo. De lo contrario, siga las instrucciones del asistente para crear el registro de aplicación necesario en AAD.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Registre la aplicación OAuth de ServiceNow.
    1. Después de completar las instrucciones de la sección de requisitos previos, seleccione el registro de aplicaciones de OAuth recién creado y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo registro de aplicación.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] Configurar opciones de entrada.
    1. Configure la aplicación de AAD entrante.
    1. Después de completar las instrucciones de la sección de requisitos previos, haga clic en Listo para ir al paso siguiente. De lo contrario, siga las instrucciones para crear el registro de aplicaciones de AAD para la conectividad entrante.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configure el proveedor de OpenID Connect externo de ServiceNow (proveedor OIDC).
    1. Después de completar las instrucciones de la sección de requisitos previos, seleccione la entidad recién creada y haga clic en Listo. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo registro de la aplicación Proveedor OIDC externo.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configure el registro de aplicaciones de AAD para el usuario de integración entrante.
    1. Después de completar las instrucciones de la sección de requisitos previos, haga clic en Listo para ir al paso siguiente. De lo contrario, siga las instrucciones para crear el registro de aplicaciones de AAD para el usuario REST entrante (usuario de integración).
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    1. Configure el usuario de integración.
    1. Después de completar las instrucciones de la sección de requisitos previos, seleccione la entidad recién creada y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear el usuario de integración en ServiceNow y, a continuación, seleccione la entidad.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Inquilino de Microsoft 365 Administración\] Completar la integración.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Vaya a **Administración de Microsoft 365 Configuración del portal &gt; Configuración &gt; de &gt; la organización Perfiles de organización**.

    1. Configure las opciones de integración de soporte técnico:

    Seleccione la pestaña **Información básica** > herramienta  >  de **soporte técnico interno****ServiceNow** y escriba el valor **de Id. de aplicación saliente** en el campo **Id. de aplicación para emitir el token de autenticación**. Este identificador de aplicación saliente se encuentra en el paso 6: completar la integración, que se creó en [Requisitos previos (token de autenticación de Azure AD).](#prerequisites-azure-ad-auth-token)

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. En la pestaña **Repositorios** , seleccione **Nuevo repositorio** y actualícelo con la siguiente configuración:

    - Repositorio: valor del **identificador de repositorio** del "Paso 6: Completar la integración".

    - Punto de conexión: valor del punto de **conexión** del "Paso 6: Completar la integración".

    - Tipo de autenticación: seleccione **Autenticación de AAD**.

    - Id. de cliente: valor del id. de **cliente** del paso 6: completar la integración.

    - Secreto de cliente: el secreto del proveedor de OAuth entrante que se creó en requisitos previos (token de autenticación de Azure AD) paso \#2.

    - Nombre de usuario rest: valor de **Nombre de usuario** del paso 6: completar la integración, que es el **identificador de cliente** de la aplicación creada en requisitos previos (token de autenticación de Azure AD) paso \#3.

    - Contraseña de usuario rest: el secreto de aplicación de la aplicación que se creó en requisitos previos (token de autenticación de Azure AD) paso \#3.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

    1. Volver a ServiceNow.

    1. Seleccione **Siguiente** para completar la integración.

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    La aplicación de integración de soporte técnico de Microsoft 365 ejecutará pruebas para asegurarse de que la integración funciona. Si hay un problema con la configuración, un mensaje de error explicará lo que se debe corregir. De lo contrario, la aplicación está lista.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[ServiceNow Administración\] Habilitar la integración de soporte técnico de Microsoft para un usuario existente.

    La integración de soporte técnico de Microsoft 365 está habilitada para el usuario con uno de estos roles:

    - x\_mioms\_m365\_assis.insights\_user

    - x\_mioms\_m365\_assis.administrator

1. \[OPCIONAL\] \[El usuario con el rol x\_mioms\_m365\_assis.administrator link\] Vincular cuenta de administrador de Microsoft 365.

    Si algún usuario tiene el rol x\_mioms\_m365\_assis.administrator y usa diferentes cuentas de Microsoft 365 para administrar un caso de soporte técnico de Microsoft 365, debe ir a La cuenta de vínculo de soporte técnico &gt; de Microsoft 365 para configurar su correo electrónico de administrador de Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::
