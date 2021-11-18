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
ms.openlocfilehash: b2676c05a4ee7767b40356852d32398f2d2c04a3
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071431"
---
# <a name="microsoft-365-support-integration-for-service-health-incidents-and-recommended-solutions-only"></a>Microsoft 365 la integración de soporte técnico para incidentes de mantenimiento del servicio y soluciones recomendadas solamente

Esta configuración no permite crear un caso con soporte técnico de Microsoft a través de la instancia de ServiceNow. Esta opción solo proporciona la información sobre incidentes de mantenimiento del servicio y las soluciones de recomendación disponibles a través de la instancia de ServiceNow.

## <a name="prerequisites-service-health-incidents-and-recommended-solutions-only"></a>Requisitos previos (Solo incidentes de mantenimiento del servicio y soluciones recomendadas)

Estos requisitos previos son necesarios para configurar la **Microsoft 365 integración de compatibilidad**.

1. \[AAD administrador \] Cree AAD de salida en el espacio empresarial Microsoft 365 cliente.

    1. Inicie sesión en Azure Portal con las Microsoft 365 de inquilino y cree una nueva aplicación en la [página Registros de aplicaciones.](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)

    2. Seleccione Cuentas solo en este directorio de la organización **({Microsoft-365-tenant-name} only – Single tenant)** y, a continuación, **seleccione Registrar**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a **Autenticación** y **seleccione Agregar una plataforma.** Seleccione la **opción Web** y escriba la dirección URL de redireccionamiento: `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Obtenga el identificador de cliente de aplicación y cree un secreto de cliente y obtenga ese valor.

1. \[Administrador de ServiceNow \] Configure el proveedor de OAuth saliente en ServiceNow.

    Si el ámbito no está establecido en **Global**, vaya a **Configuración Developer &gt; &gt; Applications** y cambie a **Global**.

    :::image type="content" source="../../media/ServiceNow-guide/Servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/Servicenow-guide-image5.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, chat o mensaje de texto Descripción generada automáticamente":::

1. Vaya a **Registro de aplicaciones de OAuth del &gt; sistema.**

1. Cree una nueva aplicación mediante el Conectar a una opción proveedor **de OAuth** de terceros y especificando estos valores:

    - Id. de cliente: este es el identificador de cliente de la aplicación creada en el paso 1 de requisitos previos (Ideas \# solo).

    - Secreto de cliente: este es el valor secreto de cliente de la aplicación creada en requisitos previos (Ideas SOLO) paso \# 1.

    - Tipo de concesión predeterminado: credenciales de cliente

    - Dirección URL del token: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Dirección URL de redireccionamiento: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Interfaz gráfica de usuario, descripción de la aplicación generada automáticamente":::

## <a name="configure-the-microsoft-365-support-integration-application"></a>Configurar la aplicación Microsoft 365 integración de soporte técnico

La Microsoft 365 de integración de soporte técnico se puede configurar en Microsoft 365 compatibilidad.

Estos pasos son necesarios para configurar la integración entre la instancia de ServiceNow y Microsoft 365 compatibilidad.

1. \[Administrador de ServiceNow \] Cambie el ámbito a Microsoft 365 **integración de soporte técnico**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Interfaz gráfica de usuario, descripción de tabla generada automáticamente":::

1. \[Administrador de ServiceNow \] Vaya Microsoft 365 configuración de soporte técnico **&gt; para** abrir el flujo de trabajo de integración.

    > [!NOTE]
    > Si ve el error "Read operation against 'oauth \_ entity' from scope 'x \_ mioms \_ m365 \_ assis' has been refused due to the table's cross-scope access policy", it was caused by your table access policy. Debe asegurarse de que **todos los ámbitos de aplicación &gt; Puede leer** están activados para la entidad oauth de \_ tabla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Seleccione **Aceptar** continuar.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el proveedor de OAuth saliente.

    Seleccione el perfil de OAuth para el proveedor de OAuth saliente y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. \[Administrador de ServiceNow \] Omitir el proveedor de OAuth entrante.

    Compruebe **Omitir paso actual** y, a continuación, seleccione **Siguiente**.

1. \[Administrador de ServiceNow \] Omitir el usuario de integración de llamadas entrantes.

    Compruebe **Omitir paso actual** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image34.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image34.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Configure el id. de repositorio.

    Especifique el identificador del repositorio y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Administrador de ServiceNow \] Configurar la aplicación Configuración.

    Seleccione esta configuración y, a continuación, **seleccione Siguiente**:

    - SSO con Microsoft 365: compruebe si la instancia de ServiceNow está configurada como SSO con Microsoft 365 inquilinos, de lo contrario desactíquela.

    - Microsoft 365 correo electrónico de administrador: el correo electrónico del Microsoft 365 de administrador al que se contacta cuando se Microsoft 365 casos de soporte técnico.

    - Entorno de prueba: active la casilla para indicar una fase de prueba para evitar que los agentes de soporte técnico de Microsoft se pondrán en contacto con usted para solucionar el problema. Si está listo para avanzar oficialmente con la integración Microsoft 365 compatibilidad, desactive la casilla.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="Interfaz gráfica de usuario, texto, descripción de la aplicación generada automáticamente":::

1. \[Microsoft 365 de inquilinos \] Complete la integración.

    Compruebe que la información siguiente es correcta. NO seleccione **Siguiente** en este momento.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image35.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image35.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. Vaya a Administración de Microsoft 365 Portal Configuración Configuración de la organización **&gt; &gt; &gt; Perfiles de organización**.

1. Configure las opciones de integración de compatibilidad:

    Seleccione la **pestaña Información básica >** **Herramienta** de soporte técnico interna ServiceNow y escriba el valor De id. de aplicación saliente en el id. de aplicación para emitir el  >  campo token de **OAuth.**  Este identificador de aplicación saliente se encuentra en el paso 6: Completar la integración, que se creó en El requisito [previo (Ideas solo) \# paso 1](#prerequisites-service-health-incidents-and-recommended-solutions-only).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Interfaz gráfica de usuario, texto, aplicación, descripción de correo electrónico generada automáticamente":::

1. En la **pestaña Repositorios,** **seleccione Nuevo repositorio y** actualícelo con la siguiente configuración:

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

1. \[Administrador de ServiceNow \] Habilite la integración de soporte técnico de Microsoft para un usuario existente.

    Microsoft 365 la integración de soporte técnico está habilitada para el usuario con uno de estos roles:

    - x \_ mioms \_ m365 \_ assis.insights \_ user

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > El usuario con el rol x \_ mioms \_ m365 assis.insights el usuario puede ver \_ Service Health \_ Incidents, Recommended Solutions. El usuario con el rol x \_ mioms \_ m365 assis.administrator también puede abrir un caso con Microsoft 365 \_ compatibilidad. Con Ideas SOLO, no se debe asignar a nadie el rol x \_ mioms \_ m365 \_ assis.administrator.
