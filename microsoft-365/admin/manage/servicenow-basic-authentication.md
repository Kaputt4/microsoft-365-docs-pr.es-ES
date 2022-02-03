---
title: 'Configurar la integración de soporte técnico con ServiceNow: autenticación básica'
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
ms.openlocfilehash: cf9b5149847b51d9d701a49e32624ada3f708a17
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321488"
---
# <a name="configure-support-integration-with-servicenow---basic-authentication"></a>Configurar la integración de soporte técnico con ServiceNow: autenticación básica

## <a name="prerequisites-basic-authentication"></a>Requisitos previos (autenticación básica)

Estos requisitos previos son necesarios para configurar la Microsoft 365 **la integración de soporte técnico**.

1. \[AAD administrador\] Cree Azure AD aplicación en su Microsoft 365 inquilino.

    1. Inicie sesión en Azure Portal con las Microsoft 365 de inquilino y vaya a la página Registros [de](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) aplicaciones para crear una nueva aplicación.

    1. Seleccione **Cuentas solo en este directorio de la organización ({Microsoft-365-tenant-name} only – Single tenant)** y seleccione **Registrar**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y **seleccione Agregar una plataforma**. Seleccione la **opción Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[Administrador de ServiceNow\] Configure el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, vaya a **Configuración &gt; Developer &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Cree una nueva aplicación mediante el Conectar a una opción proveedor **de OAuth** de terceros y especificando estos valores:

    - Id. de cliente: este es el identificador de cliente de la aplicación creada en el paso \#1.

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en el paso \#1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure el proveedor de OAuth entrante.

    Si el ámbito no está establecido en **Global**, **&gt; vaya a Configuración Developer &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya al **Registro de aplicaciones de OAuth &gt; del sistema**.

1. Cree una nueva aplicación mediante la opción Crear un punto de conexión **de la API de OAuth para clientes** externos. Asigne un nombre al proveedor de OAuth entrante y deje todos los demás campos con sus valores predeterminados.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow\] Cree un usuario de integración.

    Debe especificar un usuario de integración. Si no tiene un usuario de integración existente o si desea crear uno específicamente para esta integración, **&gt;** vaya a Usuarios de la organización para crear un nuevo usuario.

    Si va a crear un nuevo usuario de integración, compruebe la opción **Solo acceso al servicio** web. También debe conceder a este usuario el rol **incidentmanager\_**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPCIONAL\] Permitir que las direcciones IP del servicio se Microsoft 365 integración de soporte técnico

Si su empresa limita el acceso a Internet con sus propias directivas, habilite el acceso de red para el servicio de integración de soporte técnico de Microsoft 365 al permitir las direcciones IP siguientes para el acceso a la API entrante y saliente:

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Este comando de terminal enumera todas las direcciones IP activas del servicio para Microsoft 365 integración de compatibilidad:`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configurar la aplicación Microsoft 365 de integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[Administrador de ServiceNow\] Cambie el ámbito a **Microsoft 365 la integración de soporte técnico**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[Administrador de ServiceNow\] Vaya **a Microsoft 365 configuración de soporte &gt; técnico para** abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauthentity\_' from scope 'xmiomsm365assis\_\_\_' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación &gt; Puede leer** se comprueban para la oauthentity\_ de la tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Seleccione **Aceptar** continuar.

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-1.png" lightbox="../../media/ServiceNow-guide/snowbasic-1.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure el entorno y el tipo de configuración.

    Si esta instalación se encuentra en un entorno de prueba, seleccione la opción Este es un entorno de prueba. Podrás deshabilitar rápidamente esta opción después de la configuración y de que todas las pruebas se completen más adelante.
    Si la instancia permite la autenticación básica para las conexiones entrantes, seleccione Sí, de lo contrario, consulte la configuración [avanzada con AAD](servicenow-aad-oauth-token.md). :::image type="content" source="../../media/ServiceNow-guide/snowbasic-2.png" lightbox="../../media/ServiceNow-guide/snowbasic-2.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Escriba su Microsoft 365 inquilino.

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-3.png" lightbox="../../media/ServiceNow-guide/snowbasic-3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow Configurar\] las opciones de salida.
    1. Registrar la Azure Active Directory (AAD) App.
    1. Después de completar las instrucciones de la sección requisitos previos, haga clic en **Listo**. De lo contrario, siga las instrucciones del asistente para crear el registro de aplicación necesario en AAD.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-4.png" lightbox="../../media/ServiceNow-guide/snowbasic-4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Registrar la aplicación OAuth de ServiceNow.
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione el registro de la aplicación OAuth recién creada y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo registro de la aplicación.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-5.png" lightbox="../../media/ServiceNow-guide/snowbasic-5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow\] Configure Inbound settings.
    1. Configure el extremo de la API de OAuth entrante.
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione el registro de la aplicación OAuth recién creada y haga clic en Listo. De lo contrario, siga las instrucciones para crear la entidad y, a continuación, seleccione el nuevo registro de extremo REST.
     
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-6.png" lightbox="../../media/ServiceNow-guide/snowbasic-6.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

    1. Configure el usuario de integración.
    1. Después de completar las instrucciones de la sección requisitos previos, seleccione el usuario de integración recién creado y haga clic en Siguiente. De lo contrario, siga las instrucciones para crear la entidad en ServiceNow y, a continuación, seleccione el nuevo usuario de integración.
    
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-7.png" lightbox="../../media/ServiceNow-guide/snowbasic-7.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::


1. \[Microsoft 365 de inquilinos\] Complete la integración en el Administración de Microsoft 365 Portal.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. Vaya a **Administración de Microsoft 365 Portal Configuración &gt; &gt; Configuración de la organización Perfiles &gt; de organización**.

1. Configure las opciones de integración de compatibilidad:

    Seleccione la **pestaña Información básica >** **Herramienta** >  de soporte técnico **internoServiceNow** y escriba el valor **de Identificador** de aplicación saliente en el id. de aplicación para emitir el **campo Token de** autenticación. Este identificador de aplicación saliente se encuentra en el paso 6: completar la integración, que se creó en [el paso 1 de requisitos previos (autenticación básica\#](#prerequisites-basic-authentication)).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. En la **pestaña Repositorios** , **seleccione Nuevo repositorio y** actualícelo con la siguiente configuración:

    - Repositorio: el valor **de id. de** repositorio del paso 6: completar la integración.

    - Punto de conexión: **el valor** de extremo del paso 6: completar la integración.

    - Tipo de autenticación: seleccione **Autenticación básica**.

    - Id. de cliente: **valor de id.** de cliente del paso 6: completar la integración.

    - Secreto de cliente: el secreto del proveedor de OAuth entrante que se creó en el paso 3 requisitos previos (autenticación básica \#).

    - Expiración del token de actualización: 864000

    - Rest username: el **valor de Nombre** de usuario del paso 6 : Completar la integración.

    - Contraseña de usuario de reposo: la contraseña del usuario de integración que se creó en [el paso 4 requisitos previos (autenticación básica\#](#prerequisites-basic-authentication)).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generar automáticamente":::

1. Vuelva a ServiceNow.

1. Seleccione **Siguiente** para completar la integración.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="Interfaz gráfica de usuario, aplicación, descripción del sitio web generada automáticamente":::

1. \[ServiceNow Admin\] Probar la conexión Después de completar el paso anterior, haga clic en **Probar conexión**.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-8.png" lightbox="../../media/ServiceNow-guide/snowbasic-8.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::
    La Microsoft 365 de integración de soporte técnico ejecutará pruebas para garantizar que la integración funciona. Si hay un problema con la configuración, un mensaje de error explicará lo que debe solucionarse. De lo contrario, la aplicación está lista.
     :::image type="content" source="../../media/ServiceNow-guide/snowbasic-9.png" lightbox="../../media/ServiceNow-guide/snowbasic-9.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[OPTIONAL\] [El usuario con el vínculo role x_mioms_m365_assis.administrator] Vincular Administración de Microsoft 365 cuenta.
    Si algún usuario tiene el rol x_mioms_m365_assis.administrator y usa diferentes cuentas de Microsoft 365 para administrar un caso de soporte técnico de Microsoft 365, debe ir Microsoft 365 soporte técnico > Cuenta de vínculo para configurar su correo electrónico de administrador Microsoft 365.
    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::
