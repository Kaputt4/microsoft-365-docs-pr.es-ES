---
title: Microsoft 365 la integración con la guía de configuración de ServiceNow
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de configuración y instalación de aplicaciones certificadas con ámbito para ServiceNow.
ms.openlocfilehash: f21353aa54cfee3b85a6e9d846aa4fce37cc13f5
ms.sourcegitcommit: 8ef23d275d7209a705295e2b117d4382b20ad4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866738"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-guide"></a>Microsoft 365 la integración con la guía de configuración de ServiceNow

[Información general](#overview) 

[Dependencias de aplicaciones en entornos de ServiceNow](#application-dependencies-in-servicenow-environments)

[Instrucciones de configuración](#configuration-instructions)

[Quién puede configurar la Microsoft 365 la integración de soporte técnico?](#who-can-set-up-microsoft-365-support-integration)

[¿Qué características están disponibles en Microsoft 365 integración de compatibilidad?](#what-features-are-available-in-microsoft-365-support-integration) 

[Configurar la Microsoft 365 compatibilidad con la autenticación básica de ServiceNow](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)

[Configurar la Microsoft 365 la integración de soporte técnico con token de AAD OAuth](#set-up-microsoft-365-support-integration-with-aad-oauth-token)

[Configurar la Microsoft 365 de compatibilidad para Ideas SOLO](#set-up-microsoft-365-support-integration-for-insights-only) 

[Probar la configuración](#testing-the-configuration) 

[Solución de problemas](#troubleshooting) 

## <a name="overview"></a>Información general

Microsoft 365 la integración de soporte técnico le permite integrar Microsoft 365 ayuda, soporte técnico y estado del servicio con ServiceNow. Puede investigar problemas conocidos y notificados de Microsoft, resolver incidentes y completar tareas mediante soluciones recomendadas de Microsoft y, si es necesario, escalar a soporte técnico con ayuda humana de Microsoft.

## <a name="application-dependencies-in-servicenow-environments"></a>Dependencias de aplicaciones en entornos de ServiceNow

Permisos necesarios:

- entidad \_ oauth

- Perfil de \_ entidad de \_ oauth

Después Microsoft 365 se instaló la integración de compatibilidad, se crearon dos accesos entre ámbitos de aplicación. Si no se crean correctamente por cualquier motivo, creólos manualmente.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image1.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="configuration-instructions"></a>Instrucciones de configuración

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image2.png" alt-text="Descripción del diagrama generada automáticamente":::

Para configurar la Microsoft 365 la integración de soporte técnico:

- Registrar aplicaciones en Microsoft Azure Active Directory (AAD) para la autenticación de llamadas DE API salientes y entrantes.

- Cree entidades de ServiceNow con aplicaciones de Microsoft AAD para el flujo de datos entrante y saliente.

- Integre la instancia de ServiceNow con soporte técnico de Microsoft a través Administración de Microsoft 365 Portal.

## <a name="who-can-set-up-microsoft-365-support-integration"></a>Quién puede configurar la Microsoft 365 la integración?

- Cualquier persona con permisos para crear aplicaciones de AAD.

- Un administrador de ServiceNow.

- Un administrador del departamento de soporte técnico o un administrador de solicitudes de servicio Microsoft 365 inquilinos.

## <a name="what-features-are-available-in-microsoft-365-support-integration"></a>¿Qué características están disponibles en Microsoft 365 integración de compatibilidad?

Antes de configurar cualquier configuración para la Microsoft 365 la integración de soporte técnico, revise sus respuestas a estas preguntas:

**Preguntas #1** ¿El entorno de ServiceNow permite la autenticación básica (acceso con credenciales de usuario de ServiceNow) para las llamadas entrantes al servicio web?

**Preguntas #2** Si tiene varios inquilinos, ¿tiene previsto usar un único espacio empresarial integrado con el entorno de ServiceNow para Microsoft 365 integración de soporte técnico?

En función de las respuestas a las preguntas anteriores, esta tabla le indica qué características están disponibles y cómo configurar la integración Microsoft 365 compatibilidad. Para obtener una descripción de cada característica, [vea Microsoft 365 la integración de soporte técnico](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

|Pregunta #1 respuesta|Pregunta #2 respuesta|¿Qué características están disponibles?|Pasos de configuración|
|--- |--- |--- |--- |
|Sí|Sí|Incidentes de estado del servicio <br/>Soluciones recomendadas </br>Solicitud de servicio de Microsoft|[Configurar la Microsoft 365 compatibilidad con la autenticación básica de ServiceNow](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)|
|Sí|No|Incidentes de estado del servicio <br/>Soluciones recomendadas </br>Solicitud de servicio de Microsoft||
|No|Sí|Incidentes de estado del servicio <br/>Soluciones recomendadas </br>Solicitud de servicio de Microsoft|[Configurar la Microsoft 365 la integración de soporte técnico con token de AAD OAuth](#set-up-microsoft-365-support-integration-with-aad-oauth-token)|
|No|No|Incidentes de estado del servicio <br/>Soluciones recomendadas|[Configurar la Microsoft 365 de compatibilidad para Ideas SOLO](#set-up-microsoft-365-support-integration-for-insights-only) |

## <a name="set-up-microsoft-365-support-integration-with-servicenow-basic-authentication"></a>Configurar la Microsoft 365 compatibilidad con la autenticación básica de ServiceNow

### <a name="prerequisites-basic-authentication"></a>Requisitos previos (autenticación básica)

Algunos requisitos previos son necesarios para configurar la Microsoft 365 la integración de soporte técnico.

1. \[La persona que puede crear aplicaciones de AAD \] Crear aplicación de AAD en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) las Microsoft 365 de inquilino.

    1. Vaya a la página Registros de aplicaciones y cree una nueva aplicación.

        Seleccione **Cuentas solo en este directorio de la organización ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Agregar dirección URL de redireccionamiento: `https://{your-servicenow-instance}.service-now.com/oauth_redirect.do` .

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Obtener el identificador de cliente de la aplicación y crear un secreto de aplicación.

2. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider in ServiceNow.

    1. Si el ámbito no está establecido en **Global**, **abra Configuración**  >    >  **Developer Applications** para cambiar a **Global**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

    1. Vaya a **Registro de aplicaciones de OAuth** del  >  **sistema.**

    1. Cree una nueva aplicación con los valores siguientes **seleccionando Conectar a un proveedor de OAuth de terceros**.

    - Id. de cliente: el identificador de cliente de la aplicación creada en el paso \# 1

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en el paso \# 1

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: https://{service-now-instance-name}.service-now.com/auth_redirect.do

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

3. \[La persona que es administrador de ServiceNow \] Configure Inbound OAuth Provider.

    1. Si el ámbito no está establecido en **Global**, **abra Configuración**  >    >  **Developer Applications** para cambiar a **Global**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

    1. Vaya a **Registro de aplicaciones de OAuth** del  >  **sistema.**

    1. Para crear una aplicación nueva, seleccione **Crear un extremo de api de OAuth para clientes externos.** Asigne un nombre al proveedor de OAuth entrante y deje otros campos en sus valores predeterminados.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image7.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

4. \[La persona que es administrador de ServiceNow \] Crear usuarios de integración.

    Debe especificar un usuario de integración. Si no tiene un usuario de integración existente o si desea crear un usuario específico para esta integración, vaya a Usuarios de la organización  >   para crear un nuevo usuario.

    Si va a crear un nuevo usuario de integración, active la casilla Solo acceso **al servicio web**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image8.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[Opcional Permitir las IP del servicio de Microsoft 365 \] integración de compatibilidad

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de Microsoft 365 admitir la integración al permitir las direcciones IP siguientes para el acceso a la API entrante y saliente.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para Microsoft 365 integración de compatibilidad:`nslookup connector.rave.microsoft.com`

### <a name="set-up-microsoft-365-support-integration-application"></a>Configurar una Microsoft 365 de integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[La persona que es administrador de ServiceNow Cambie el ámbito a \] Microsoft 365 la integración de soporte técnico.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

2. \[La persona que es administrador de ServiceNow Vaya a Microsoft 365 \] soporte técnico > **instalación** para abrir el flujo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauth \_ entity' from scope 'x \_ mioms \_ m365 \_ assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación** Puede  >  **leer** están activados para la entidad oauth de \_ tabla.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image10.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

3. \[La persona que es administrador de ServiceNow \] Seleccione **Aceptar** aceptar el consentimiento

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

4. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider.

    Seleccione el perfil de OAuth para el proveedor de OAuth saliente creado en el paso 2 [requisitos previos (autenticación básica)](#prerequisites-basic-authentication) \# y seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

5. \[La persona que es administrador de ServiceNow \] Configure Inbound OAuth Provider.

- Desactive **Omitir el paso actual**.

- Desactive **Token de autenticación OIDC externo**.

- Seleccione Cliente de OAuth creado en [Requisitos previos (autenticación básica)](#prerequisites-basic-authentication) paso \# 3 y seleccione **Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image13.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

6. \[La persona que es administrador de ServiceNow \] Configure el usuario de integración de llamadas entrantes.

- Desactive **Omitir el paso actual**.

- Seleccione el usuario de integración creado en [requisitos previos (autenticación básica)](#prerequisites-basic-authentication) paso \# 4 y seleccione **Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image14.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

7. \[La persona que es administrador de ServiceNow \] Configure up Repository ID.

Especifique el identificador del repositorio y, a continuación, **seleccione Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

8. \[La persona que es administrador de ServiceNow \] Configurar la configuración de la aplicación.

Seleccione la siguiente configuración y, a continuación, **seleccione Siguiente**.

- SSO con Microsoft 365: compruebe si la instancia de ServiceNow está configurada como SSO con Microsoft 365 inquilinos, de lo contrario desactíquela.

- Microsoft 365 correo electrónico de administrador: el correo electrónico del Microsoft 365 de administrador al que se contacta cuando se Microsoft 365 casos de soporte técnico.

- Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

9. \[La persona que es administrador del departamento de soporte técnico o administrador de solicitudes de servicio en Microsoft 365 inquilinos \] completa la integración.

    1. Compruebe la información siguiente para asegurarse de que es correcta.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image17.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

    1. Vaya a Microsoft 365 [Portal de administración Configuración](https://admin.microsoft.com/)Configuración de la organización  >    >    >  **Perfiles de organización**.

    1. Configurar la configuración de integración de compatibilidad:

        1. En  la pestaña Información básica, seleccione la herramienta de soporte técnico interna **Service Now** y escriba Outbound **App ID** como el valor de Id. de aplicación en la página Step - 6 Complete, que se creó en [Prerequisites (Basic Authentication)](#prerequisites-basic-authentication) step \# 1.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

        1. En la pestaña **Repositorios,** seleccione **Agregar un** repositorio para crear un nuevo repositorio con la siguiente configuración:

        - Repositorio: valor **de id. de repositorio** de la página Paso - 6 Completar la integración.

        - Punto de conexión: el **valor** de extremo de la página Paso - 6 Completar la integración.

        - Tipo de autenticación: seleccione **Autenticación básica**.

        - Id. de cliente: **valor de id.** de cliente de la página Paso - 6 Completar la integración.

        - Secreto de cliente: el secreto del proveedor de OAuth entrante que se creó en el paso 3 [requisitos previos (autenticación](#prerequisites-basic-authentication) \# básica).

        - Expiración del token de actualización: 864000

        - Rest username: el **valor de Nombre** de usuario de la página Paso - 6 Completar la integración.

        - Contraseña de usuario de reposo: la contraseña del usuario de integración que se creó en el paso 4 [requisitos previos (autenticación](#prerequisites-basic-authentication) \# básica).

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image19.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generar automáticamente":::

        1. Vuelva atrás y seleccione el botón para guardar la integración.

    1. Seleccione **Siguiente** para completar la integración.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image20.png" alt-text="Interfaz gráfica de usuario, aplicación, descripción del sitio web generada automáticamente":::

10. \[La persona que es administrador de ServiceNow Habilitar Microsoft 365 \] la integración de soporte técnico para un usuario existente.

Microsoft 365 la integración de soporte técnico solo está habilitada para el usuario con uno de estos roles:

- x \_ mioms \_ m365 \_ assis.insights \_ user

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE]
> El usuario con el rol x \_ mioms \_ m365 assis.insights rol de usuario puede ver \_ Service Health \_ Incidents, Recommended Solutions. El usuario con el rol x \_ mioms \_ m365 assis.administrator también puede abrir un caso con Microsoft 365 \_ compatibilidad.

11. \[Opcional \] \[ El usuario con rol x_mioms_m365_assis.administrator \] Vincular Administración de Microsoft 365 cuenta.

Si algún usuario tiene el rol x \_ mioms \_ m365 assis.administrator y usa diferentes cuentas de Microsoft 365 para administrar un caso de soporte técnico de Microsoft 365 Microsoft 365, debe ir > la cuenta de vínculo de soporte técnico > para configurar su correo electrónico de administrador \_ de Microsoft 365.

 :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

## <a name="set-up-microsoft-365-support-integration-with-aad-oauth-token"></a>Configurar la Microsoft 365 la integración de soporte técnico con token de AAD OAuth

### <a name="prerequisites-aad-oauth-token"></a>Requisitos previos (token OAuth de AAD)

Estos pasos previos son necesarios para configurar la Microsoft 365 integración de soporte técnico:

1. \[La persona que puede crear aplicaciones de AAD Crear una aplicación de AAD para salida \] en su Microsoft 365 inquilino.

    1. Inicie sesión [en Azure Portal](https://portal.azure.com/) con Microsoft 365 de inquilino.

    1. Vaya a la **página Registros de aplicaciones** y cree una nueva aplicación.

        Seleccione **Cuentas solo en este directorio de la organización ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Agregar dirección URL de redireccionamiento: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Obtener el identificador de cliente de la aplicación y crear el secreto de aplicación.

2. \[La persona que puede crear aplicaciones de AAD Cree una API de aplicación de AAD para \] rest en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) las Microsoft 365 de inquilino.

    1. Vaya a **Registros de aplicaciones** y cree una nueva aplicación.

        Seleccione **Cuentas solo en este directorio de la organización ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image22.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Obtener el identificador de cliente de la aplicación y crear el secreto de aplicación.

3. \[La persona que puede crear aplicaciones de AAD Crear una aplicación de AAD para el usuario de reposo \] en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) las Microsoft 365 de inquilino.

    1. Vaya a la **página Registros de aplicaciones** y cree una nueva aplicación.
        
        Seleccione **Cuentas solo en este directorio de la organización ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Obtener el identificador de cliente de la aplicación y crear un secreto de aplicación.

4. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider in ServiceNow.

    1. Si el ámbito no está establecido en **Global**, **abra Configuración**  >    >  **Developer Applications** para cambiar a **Global**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

    1. Vaya a **Registro de aplicaciones de OAuth** del  >  **sistema.**

    1. Cree una nueva aplicación con los valores siguientes **seleccionando Conectar a un proveedor de OAuth de terceros**.

        - Id. de cliente: el identificador de cliente de la aplicación creada en el paso 1 de [Requisitos previos (token de OAuth de AAD).](#prerequisites-aad-oauth-token) \#

        - Secreto de cliente: el secreto de aplicación de la aplicación creada en [requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 1.

        - Tipo de concesión predeterminado: credenciales de cliente.

        - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - Dirección URL de redireccionamiento:

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

5. \[La persona que es administrador de ServiceNow \] Configure OIDC provider in ServiceNow, consulte la [documentación en línea](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html).

    1. Si el ámbito no está establecido en **Global**, **abra Configuración**  >    >  **Developer Applications** para cambiar a **Global**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

    1. Vaya a **Registro de aplicaciones de OAuth** del  >  **sistema.**

    1. Seleccione **Nuevo**  >  **Crear nuevo identificador abierto Conectar proveedor**.

    1. En Configuración del proveedor **OAuth OIDC,** seleccione Buscar y cree una nueva configuración de proveedor de OIDC en "oidc provider  \_ \_ configuration.list" con estos valores:

    - Proveedor de OIDC: Contoso Azure

    - Dirección URL de metadatos de OIDC: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appId**

    - Campo de usuario: **Id. de usuario**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image24.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

    1. Para crear una aplicación nueva, seleccione **Configurar un proveedor de OIDC para comprobar los tokens de id.** con estos valores:

    - Nombre: api \_ de entrada de aplicación \_ \_ contoso

    - Id. de cliente: el identificador de cliente de la aplicación creada en el paso 2 [requisitos previos (token de OAuth de AAD).](#prerequisites-aad-oauth-token) \#

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en [requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 2.

    - Configuración del proveedor de OAuth OIDC: el proveedor de OIDC creado en el último paso.

    - Dirección URL de redireccionamiento:  
        `https://{service-now-instance-name}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image25.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

6. \[La persona que es administrador de ServiceNow \] Crear usuarios de integración.

    Vaya a **Usuarios**  >  **de la** organización para crear un nuevo usuario si no hay ningún usuario de integración. El valor de **Id. de usuario** es el id. de cliente de la aplicación creado en el paso [Prerequisites (Token de AAD OAuth)](#prerequisites-aad-oauth-token) \# 3

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image26.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[Opcional Permitir las IP del servicio de Microsoft 365 \] integración de compatibilidad

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de Microsoft 365 admitir la integración al permitir estas direcciones IP para el acceso a la API entrante y saliente:

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para la Microsoft 365 de compatibilidad: *nslookup connector.rave.microsoft.com*

### <a name="set-up-microsoft-365-support-integration"></a>Configurar la Microsoft 365 la integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar a través del **programa de** instalación en la Microsoft 365 soporte técnico.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[La persona que es administrador de ServiceNow Cambie el ámbito a \] Microsoft 365 la integración de soporte técnico.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

2. \[La persona que es administrador de ServiceNow Vaya a Microsoft 365 \] soporte técnico > **instalación** para abrir el flujo de integración.

> [!NOTE]
> Si ve el error "Read operation against 'oauth \_ entity' from scope 'x \_ mioms \_ m365 \_ assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación** Puede  >  **leer** están activados para la entidad oauth de \_ tabla.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

3. \[La persona que es administrador de ServiceNow \] Seleccione **Aceptar** aceptar el consentimiento.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

4. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider.

Seleccione Perfil de OAuth para proveedor de OAuth saliente creado [en Requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 4 y **seleccione Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

5. \[La persona que es administrador de ServiceNow \] Configure Inbound OAuth Provider.

    1. Desactive **Omitir el paso actual**.

    1. Compruebe **Token de autenticación OIDC externo**.

    1. Seleccione el paso 5 del cliente de OAuth creado [en Requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image28.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

6. \[La persona que es administrador de ServiceNow \] Configurar el usuario de integración de llamadas entrantes.

    1. Desactive **Omitir el paso actual**.

    1. Introduzca el identificador de cliente de la aplicación que se creó en el paso 3 [requisitos previos (token de OAuth de AAD)](#prerequisites-aad-oauth-token) \# y seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image39.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

7. \[La persona que es administrador de ServiceNow \] Configure el id. de repositorio.

    Especifique el identificador del repositorio y seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

8. \[La persona que es administrador de ServiceNow \] Configure up Application Configuración.

    Seleccione esta configuración:

    1. SSO con Microsoft 365: active la casilla si la instancia de ServiceNow está configurando SSO con Microsoft 365 inquilinos; de lo contrario, desactíquelo.

    1. Microsoft 365 correo electrónico de administrador: el correo electrónico de Microsoft 365 usuario administrador al que se debe ponerse en contacto cuando se Microsoft 365 casos de soporte técnico.

    1. Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

    1. Seleccione **Siguiente**.

9. \[La persona que es administrador del departamento de soporte técnico o administrador de solicitudes de servicio en Microsoft 365 inquilinos \] completa la integración.

    1. Compruebe la siguiente información para asegurarse de que es correcta.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image40.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Vaya a Microsoft 365 [Portal de administración Configuración](https://admin.microsoft.com)Configuración de la organización  >    >    >  **Perfiles de organización**.

    1. Configurar la configuración de integración de compatibilidad.

        1. En  la pestaña información básica, seleccione **Servicio** ahora como herramienta de soporte técnico interna y escriba **Identificador** de aplicación saliente como el valor de Id. de aplicación en el paso - 6 Completar la página de integración, que se creó en [Requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 1.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. En la **pestaña Repositorios,** seleccione **Agregar un** repositorio para crear un nuevo repositorio con la siguiente información:

    - Repositorio: use el valor **id. de** repositorio de la página Paso - 6 Completar la integración.

    - Punto de conexión: **valor** de extremo de la página Paso - 6 Completar la integración.

    - Tipo de autenticación: seleccione **Autenticación de AAD**.

    - Id. de cliente: valor de **id.** de cliente en el paso - 6 Completar la página de integración, que es el identificador de cliente de la aplicación creada en [requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 2.

    - Rest username: el valor **de Nombre** de usuario en el paso - 6 Completar la página de integración, que es el **identificador** de cliente de la aplicación creada en [Prerequisites (Token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 3.

    - Contraseña de usuario de reposo: el secreto de aplicación de la aplicación creada en [requisitos previos (token de AAD OAuth)](#prerequisites-aad-oauth-token) paso \# 3.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image31.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

    1. Vuelva atrás y seleccione el botón para guardar la integración.

    1. Seleccione **Siguiente** para completar la integración.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image32.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

10. \[La persona que es administrador de ServiceNow Habilitar Microsoft 365 \] la integración de soporte técnico para un usuario existente.

Microsoft 365 la integración de soporte técnico solo está habilitada para usuarios con los siguientes roles:

- x \_ mioms \_ m365 \_ assis.insights \_ user

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE]
> El usuario con el rol x \_ mioms \_ m365 assis.insights el usuario puede ver \_ Service Health \_ Incidents, Recommended Solutions. El usuario con el rol x \_ mioms \_ m365 assis.administrator también puede abrir un caso con Microsoft 365 \_ compatibilidad.

11. **\[Opcional \] \[ El usuario con rol x_mioms_m365_assis.administrator \] Link Administración de Microsoft 365 cuenta**

Si algún usuario tiene el rol "x \_ mioms \_ m365 assis.administrator" y usa diferentes cuentas de Microsoft 365 para administrar los casos de soporte técnico de Microsoft, debe ir Microsoft 365 la cuenta de vínculo de soporte técnico > para configurar su correo electrónico de administrador de \_ Microsoft 365.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

## <a name="set-up-microsoft-365-support-integration-for-insights-only"></a>Configurar la Microsoft 365 de compatibilidad para Ideas SOLO

### <a name="prerequisites-insights-only"></a>Requisitos previos (Ideas SOLO)

Estos pasos previos son necesarios para configurar la Microsoft 365 integración de soporte técnico:

1. \[La persona que puede crear aplicaciones de AAD \] Crear aplicación de AAD en su Microsoft 365 inquilino.

    1. Inicie sesión en [Azure Portal con](https://portal.azure.com/) las Microsoft 365 de inquilino.

    1. Vaya a la **página Registros de aplicaciones** y cree una nueva aplicación.

        Seleccione **Cuentas solo en este directorio de la organización ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Agregar dirección URL de redireccionamiento: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Obtener el identificador de cliente de la aplicación y crear un secreto de aplicación.

1. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider in ServiceNow.

    1. Si el ámbito no está establecido en **Global**, **abra Configuración**  >    >  **Developer Applications** para cambiar a **Global**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

    1. Vaya a **Registro de aplicaciones de OAuth** del  >  **sistema.**

    1. Cree una nueva aplicación con los valores siguientes **seleccionando Conectar a un proveedor de OAuth de terceros**.

    - Id. de cliente: **el identificador de cliente** de la aplicación creada en [requisitos previos (Ideas SOLO)](#prerequisites-insights-only) \# paso 1

    - Secreto de cliente: el secreto de aplicación de la aplicación creada en [requisitos previos (Ideas SOLO)](#prerequisites-insights-only) \# paso 1

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{servicenow-instance-name}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

### <a name="set-up-microsoft-365-support-integration"></a>Configurar la Microsoft 365 la integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar a **través del programa de instalación** Microsoft 365 soporte técnico.

Los siguientes pasos son necesarios para configurar la integración entre la instancia de ServiceNow y el soporte técnico de Microsoft.

1. \[La persona que es administrador de ServiceNow Cambie el ámbito a \] Microsoft 365 la integración de soporte técnico.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

2. \[La persona que es administrador de ServiceNow Vaya a Microsoft 365 \] soporte técnico > **instalación** para abrir el flujo de integración.

> [!NOTE]
> Si ve el error "Read operation against 'oauth \_ entity' from scope 'x \_ mioms \_ m365 \_ assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación** Puede  >  **leer** están activados para la entidad oauth de \_ tabla.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

3. \[La persona que es administrador de ServiceNow \] Seleccione **Aceptar** aceptar el consentimiento.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

4. \[La persona que es administrador de ServiceNow \] Configure Outbound OAuth Provider.

Seleccione Perfil de OAuth para proveedor de OAuth saliente y seleccione **Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

5. \[La persona que es administrador de ServiceNow \] Omitir proveedor de OAuth entrante.

    Compruebe **Omitir paso actual** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image33.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

6. \[La persona que es administrador de ServiceNow \] Omitir usuario de integración.

    Compruebe **Omitir paso actual** y seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image34.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

7. \[La persona que es administrador de ServiceNow \] Configure up Repository ID.

Especifique el identificador del repositorio y seleccione **Siguiente**.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

8. \[La persona que es administrador de ServiceNow \] Configure up Application Configuración.

    Seleccione la configuración correcta y seleccione **Siguiente**.

    - SSO con Microsoft 365: compruebe si la instancia de ServiceNow está configurada como SSO con Microsoft 365 inquilinos; de lo contrario, desactíquelo.

    - Administración de Microsoft 365 Correo electrónico: el correo electrónico Microsoft 365 usuario administrador al que se debe ponerse en contacto cuando se Microsoft 365 casos de soporte técnico.

    - Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

9. \[La persona que es administrador del departamento de soporte técnico o administrador de solicitudes de servicio en Microsoft 365 inquilinos \] completa la integración.

    1. Compruebe la información aquí para asegurarse de que es correcta.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image35.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Vaya a Microsoft 365 [Portal de administración Configuración](https://admin.microsoft.com)Configuración de la organización  >    >    >  **Perfiles de organización**.

        1. Configure la configuración de integración de soporte técnico con la información que se muestra en el flujo de configuración.

        1. En la **pestaña información básica,** seleccione **Servicio** ahora como herramienta de soporte técnico interna y escriba **Identificador** de aplicación saliente como id. de aplicación para emitir un token de OAuth.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

        1. En la **pestaña Repositorios,** seleccione **Agregar un** repositorio para crear un nuevo repositorio con la siguiente información:

        - Repositorio: el valor **id. de** repositorio de la página Paso - 6 Completar la integración.

        - Punto de conexión: **valor** de extremo de la página Paso - 6 Completar la integración.

        - Tipo de autenticación: seleccione **Autenticación de AAD**.

        - Id. de cliente: un valor aleatorio, como **omitido**.

        - Rest username: un valor aleatorio, como **ignored**.

        - Rest user password: A random value, such as **ignored**.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image36.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

        1. Vuelva atrás y seleccione el botón para guardar la integración.

    1. Seleccione **Siguiente** para completar la integración.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image37.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

10. \[La persona que es administrador de ServiceNow Habilitar Microsoft 365 \] la integración de soporte técnico para un usuario existente.

Microsoft 365 la integración de compatibilidad solo está habilitada para estos roles de usuario:

- x \_ mioms \_ m365 \_ assis.insights \_ user

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE] 
> El usuario con el rol x_mioms_m365_assis.insights_user puede ver Service Health Incidents, Recommended Solutions. El usuario con el rol x_mioms_m365_assis.administrator también puede abrir un caso con Microsoft 365 compatibilidad. Con Ideas SOLO, no se debe asignar a nadie el rol x_mioms_m365_assis.administrator.

## <a name="testing-the-configuration"></a>Probar la configuración

Si la aplicación requiere una comunicación correcta con sistemas externos, esboza cómo probar la conexión para garantizar una configuración correcta.

Estos son los pasos para probar la configuración de la Microsoft 365 la integración de soporte técnico:

1. Inicie sesión en el portal de ServiceNow como administrador.

2. Abra cualquier incidente.

3. **Céntrate en Microsoft 365 de** soporte técnico y selecciona **Microsoft 365 Ideas** para determinar si las soluciones recomendadas se recuperaron correctamente.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image38.png" alt-text="Interfaz gráfica de usuario, aplicación, descripción del sitio web generada automáticamente":::

##  <a name="troubleshooting"></a>Solución de problemas

|#|Problema|Acción diagnóstico|
|--- |--- |--- |
|1|No se puede ver la **Microsoft 365 de soporte** técnico|Compruebe la vista actual y **los registros del** sistema todos  >  **con** x_mioms_m365_assit|
|2|Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen los pasos de configuración de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|3|Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen el paso de configuración final de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|4 |Escriba el problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|5 |Escriba problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|6 |Selecciona Póngase en contacto con el soporte técnico de **Microsoft,** pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|7 |Selecciona Póngase en contacto con el soporte técnico de **Microsoft,** pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|8 |Seleccione **Póngase en contacto con** el soporte técnico de Microsoft pero obtenga el error "{EmailAddress} no es una cuenta de administrador Microsoft 365 válida. Necesita privilegios Microsoft 365 administrador para abrir una solicitud de servicio. En la aplicación, vincula la cuenta de administrador".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|9 |Seleccionar **soluciones recomendadas de Microsoft,** pero no aparece nada|Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com|
|10|Seleccione **Soluciones recomendadas de Microsoft pero** obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|11 |Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft,** pero no aparece nada|Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com|
|12 |Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".|Compruebe el mensaje de error en la parte superior del formulario y **registros del** sistema  >  **todos con** filtro x_mioms_m365_assit|
|13|El usuario selecciona **Póngase en contacto con el soporte técnico de Microsoft,** pero no ocurre nada|Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com|
|14 |No se puede ver la solución recomendada por Microsoft después de volver a abrir el incidente|Comprobar **Registros del sistema**  >  **Todo** con filtros x_mioms_m365_assit|
|15 |No se pueden ver casos de Microsoft al volver a abrir el incidente que se transfirió al soporte técnico de Microsoft|Comprobar **Registros del sistema**  >  **Todo** con filtros x_mioms_m365_assit|
|16 |No se pueden guardar los detalles del vale, recibe el error "No se pueden guardar los detalles del vale. Póngase en contacto con el soporte técnico de la aplicación".|Comprobar el mensaje de error en la parte superior del formulario|
