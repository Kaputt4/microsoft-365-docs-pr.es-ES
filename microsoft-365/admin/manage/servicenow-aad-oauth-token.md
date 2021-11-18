---
title: Configuración de la integración de compatibilidad de Microsoft 365 con el token de OAuth de AAD
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
ms.openlocfilehash: da241452f989ba5f682fd3219e3f3baabf623138
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071455"
---
# <a name="configure-microsoft-365-support-integration-with-aad-oauth-token"></a>Configuración de la integración de compatibilidad de Microsoft 365 con el token de OAuth de AAD

## <a name="prerequisites-aad-oauth-token"></a>Requisitos previos (AAD token de OAuth)

Estos requisitos previos son necesarios para configurar la Microsoft 365 la integración de soporte técnico.

1. \[AAD administrador \] Cree AAD de salida en el espacio empresarial Microsoft 365 cliente.

    1. Inicie sesión en Azure Portal con las Microsoft 365 de inquilino y vaya a la página Registros [de](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) aplicaciones para crear una nueva aplicación.

    2. Seleccione Cuentas solo en este directorio de la organización **({Microsoft-365-tenant-name} only – Single tenant)** y **seleccione Registrar**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y **seleccione Agregar una plataforma.** Seleccione la **opción Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[AAD administrador \] Cree una aplicación AAD para la API de Rest en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) sus Microsoft 365 de inquilino y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Cuentas en este directorio de la organización solo {(Microsoft-365-tenant-name} only – Single tenant)**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[AAD administrador \] Cree una aplicación AAD para el usuario de reposo en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) sus Microsoft 365 de inquilino y vaya a la página Registros de aplicaciones para crear una nueva aplicación.

    1. Seleccione **Cuentas en este directorio de la organización solo {(Microsoft-365-tenant-name} only – Single tenant)**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[Administrador de ServiceNow \] Configure el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, para ello, vaya a **Configuración &gt; &gt; Aplicaciones** para desarrolladores y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya a **Registro de aplicaciones de OAuth del &gt; sistema.**

1. Cree una nueva aplicación mediante la Conectar a una opción proveedor **de OAuth** de terceros e introduzca estos valores:

    - Id. de cliente: este es el identificador de cliente de la aplicación creada en requisitos previos (AAD token de OAuth) paso \# 1.

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en requisitos previos (AAD token de OAuth) paso \# 1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Para configurar el proveedor de OIDC en ServiceNow, consulte la documentación en [línea](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html).

    Si el ámbito no está establecido en **Global**, vaya a **Configuración Developer &gt; &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya a **Registro de aplicaciones de OAuth del &gt; sistema.**

1. Seleccione **Nuevo** y, a continuación, seleccione Crear nuevo identificador **de Conectar proveedor**.

1. En Configuración del proveedor **OAuth OIDC,** seleccione Buscar y cree una nueva configuración de proveedor de OIDC en **oidc \_ provider \_ configuration.list** con estos valores: 

    - Proveedor de OIDC: **{Tenant \_ Name} Azure** (ejemplo: Contoso Azure)

    - Dirección URL de metadatos de OIDC: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appId**

    - UserField: **Id. de usuario**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. Para crear una aplicación nueva, seleccione **Configurar un proveedor de OIDC para comprobar los tokens de id.** con estos valores:

    - Name: **{Tenant \_ Name} \_ application inbound \_ \_ api** (ejemplo: api \_ de entrada de aplicación \_ \_ contoso)

    - Id. de cliente: el identificador de cliente de la aplicación creada en requisitos previos (AAD token de OAuth) paso \# 2.

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en requisitos previos (AAD token de OAuth) paso \# 2.

    - Configuración del proveedor OAuth OIDC: el proveedor de OIDC creado en el paso anterior

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Crear usuarios de integración.

    Debe especificar un usuario de integración. Si no tiene un usuario de integración existente o si desea crear **uno &gt;** específicamente para esta integración, vaya a Usuarios de la organización para crear un nuevo usuario. El valor del **id. de usuario** es el id. de cliente de la aplicación creado en [requisitos previos (AAD token de OAuth) \# paso 3](#prerequisites-aad-oauth-token).

    Si va a crear un nuevo usuario de integración, compruebe la opción Solo acceso **al servicio** web. También debe conceder a este usuario el rol de administrador **\_ de** incidentes.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPCIONAL Permitir que las direcciones IP del servicio \] Microsoft 365 la integración de soporte técnico

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de Microsoft 365 admitir la integración al permitir las direcciones IP siguientes para el acceso a la API entrante y saliente.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para Microsoft 365 integración de compatibilidad:`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configurar la aplicación Microsoft 365 integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[Administrador de ServiceNow \] Cambie el ámbito a Microsoft 365 **integración de soporte técnico**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[Administrador de ServiceNow \] Vaya Microsoft 365 configuración de soporte técnico **&gt; para** abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauth \_ entity' from scope 'x \_ mioms \_ m365 \_ assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación &gt; Puede leer** están activados para la entidad oauth de \_ tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Seleccione **Aceptar** el aviso de consentimiento para continuar.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el proveedor de OAuth saliente.

    Seleccione el perfil de OAuth para el proveedor de OAuth saliente creado en [Requisitos previos (AAD Token de OAuth) paso \# 4](#prerequisites-aad-oauth-token)y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el proveedor de OAuth entrante.

    1. Desactive **Omitir el paso actual**.

    1. Compruebe **Token de autenticación OIDC externo**.

    1. Seleccione el paso 5 del cliente de OAuth creado en [Requisitos previos \# (AAD token de OAuth)](#prerequisites-aad-oauth-token)y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image28.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image28.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el usuario de integración de llamadas entrantes.

    1. Desactive **Omitir el paso actual**.

    1. Escriba el **identificador de cliente** de la aplicación que se creó en [requisitos previos (AAD token de OAuth) paso \# 3](#prerequisites-aad-oauth-token)y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image39.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image39.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el id. de repositorio.

    Especifique el identificador del repositorio y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Configurar la aplicación Configuración.

    Seleccione la siguiente configuración y, a continuación, **seleccione Siguiente**.

    - SSO con Microsoft 365: compruebe si la instancia de ServiceNow está configurada como SSO con Microsoft 365 inquilinos, de lo contrario desactíquela.

    - Microsoft 365 correo electrónico de administrador: el correo electrónico del Microsoft 365 de administrador al que se contacta cuando se Microsoft 365 casos de soporte técnico.

    - Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Microsoft 365 de inquilinos \] Complete la integración.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a Administración de Microsoft 365 Portal Configuración Configuración de la organización **&gt; &gt; &gt; Perfiles de organización**.

1. Configure las opciones de integración de compatibilidad:

    Seleccione la **pestaña Información básica >** **Herramienta** de soporte técnico interna ServiceNow y escriba el valor De id. de aplicación saliente en el id. de aplicación para emitir el  >  campo token de **OAuth.**  Este identificador de aplicación saliente se encuentra en el paso 6: completar la integración, que se creó en el paso 1 de requisitos previos [(AAD token de OAuth). \# ](#prerequisites-aad-oauth-token)

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. En la **pestaña Repositorios,** **seleccione Nuevo repositorio y** actualícelo con la siguiente configuración:

    - Repositorio: el valor **del id. de** repositorio del "Paso 6: completar la integración".

    - Punto de conexión: **el valor** del extremo de "Paso 6: completar la integración".

    - Tipo de autenticación: **seleccione AAD Auth**.

    - Id. de cliente: **valor de id.** de cliente del paso 6: completar la integración.

    - Secreto de cliente: el secreto del proveedor de OAuth entrante que se creó en requisitos previos (AAD token de OAuth) \# paso 2.

    - Rest username: el valor **de Nombre** de usuario del paso 6: Completar la integración, que es el **identificador** de cliente de la aplicación creada en Prerequisites (AAD Token de OAuth) paso \# 3.

    - Contraseña de usuario de reposo: el secreto de aplicación de la aplicación que se creó en requisitos previos (AAD token de OAuth) paso \# 3.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. Vuelva a ServiceNow.

1. Seleccione **Siguiente** para completar la integración.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image32.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image32.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Habilite la integración de soporte técnico de Microsoft para un usuario existente.

    Microsoft 365 la integración de soporte técnico está habilitada para el usuario con uno de estos roles:

    - x \_ mioms \_ m365 \_ assis.insights \_ user

    - x \_ mioms \_ m365 \_ assis.administrator

1. \[OPCIONAL \] \[ El usuario con el rol x \_ mioms \_ m365 \_ assis.administrator vínculo Vínculo Microsoft 365 \] cuenta de administrador.

    Si algún usuario tiene el rol x \_ mioms \_ m365 \_ assis.administrator y usa diferentes cuentas de Microsoft 365 para administrar un caso de soporte técnico de Microsoft 365, debe ir Microsoft 365 la cuenta de vínculo de soporte técnico para configurar su correo electrónico de administrador &gt; de Microsoft 365.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::
