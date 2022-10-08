---
title: Integración de LTI de Microsoft OneDrive con Desire2Learn Brightspace
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
ms.collection: m365initiative-edu
ms.localizationpriority: medium
description: Crear y calificar asignaciones, compilar y mantener contenido del curso, y colaborar en archivos en tiempo real con la nueva interoperabilidad de herramientas de aprendizaje de Microsoft OneDrive para Desire2Learn Brightspace.
ms.openlocfilehash: 9c03ee2f46e77d8d24f7c731ac2e32b1dfc9cef2
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363022"
---
# <a name="integrate-microsoft-onedrive-lti-with-desire2learn-brightspace"></a>Integración de LTI de Microsoft OneDrive con Desire2Learn Brightspace

En esta guía se proporcionan los pasos de los administradores de TI para registrar la aplicación LTI de OneDrive para Desire2Learn (D2L) Brightspace LMS.

Para obtener información general sobre Microsoft LTI, consulte [Integración de productos de Microsoft con el sistema de administración de aprendizaje (LMS).](index.md)

Los pasos para agregar la aplicación LTI de OneDrive son:

1. [Paso 1: Agregar la nueva aplicación LTI de Microsoft OneDrive](#step-1-add-the-new-microsoft-onedrive-lti-app).
1. [Paso 2: Implementar la aplicación LTI en la experiencia de Brightspace de los usuarios](#step-2-deploy-the-lti-app-in-users-brightspace-experience).
1. [Paso 3: Active la nueva aplicación LTI de OneDrive en la barra de actividad de Quicklinks](#step-3-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar).

> [!NOTE]
> La persona que realiza esta integración debe ser administrador de Brightspace y administrador del inquilino de Microsoft 365.
>
> La documentación de origen de la configuración de LTI 1.3 se encuentra en la [Guía de LTI Advantage - Administrator](https://community.brightspace.com/s/article/LTI-Advantage-Administrator-Guide).

## <a name="step-1-add-the-new-microsoft-onedrive-lti-app"></a>Paso 1: Agregar la nueva aplicación LTI de Microsoft OneDrive

### <a name="register-a-new-microsoft-onedrive-lti-app"></a>Registro de una nueva aplicación LTI de Microsoft OneDrive

1. Inicie sesión en el [Portal de registro de LTI de Microsoft OneDrive](https://onedrivelti.microsoft.com/admin).
1. Seleccione el botón **Administración Consentimiento** y acepte los permisos.
   >[!IMPORTANT]
   >Si no **se acepta Administración consentimiento**, el siguiente paso le dará un error y tendrá que esperar una hora para poder continuar.
1. Seleccione el botón **Crear nuevo inquilino de LTI** .
1. En la lista **Plataforma de consumidores de LTI** , seleccione **D2L Brightspace**.
1. En el campo **D2L Brightspace Base URL (DIRECCIÓN URL base de Brightspace D2L** ), escriba la dirección URL base de Brightspace, como `https://myschool.brightspace.com`.
1. Seleccione el botón **Siguiente**. Se cargará la página **Registrar aplicación LTI 1.3** . \
   Mantenga esta página abierta en su propia pestaña al completar el siguiente conjunto de pasos. Los valores necesarios se generarán en los pasos siguientes.

### <a name="add-microsoft-lti-app-to-brightspace"></a>Adición de una aplicación de Microsoft LTI a Brightspace

1. En una nueva pestaña del explorador, inicie sesión en brightspace LMS con una cuenta *de administrador* o *superadministrador* para las organizaciones a las que desea agregar la aplicación LTI de OneDrive.
1. Seleccione el icono de engranaje en la parte superior derecha para acceder a **Administración Tools**.
1. En la categoría **Relacionada con la organización** , busque **Administrar extensibilidad**. \
   La dirección URL debe tener un aspecto similar al de este ejemplo: `https://<yourbrightspacedomain>/d2l/le/ltiadvantage/registrations/home`.
1. Seleccione la pestaña **Ventaja de LTI** en la parte superior y, a continuación, seleccione **Registrar una herramienta**.
1. Seleccione el botón de radio **Estándar** para el **tipo de registro de herramientas**.
1. Escriba un nombre para la aplicación, como `Microsoft OneDrive LTI App`.
1. En el campo **Dominio** , escriba `https://onedrivelti.microsoft.com`.
1. Vaya a la pestaña del explorador con el Portal de registro de LTI de Microsoft OneDrive para copiar los demás valores necesarios:
    1. Pegue el `ToolOIDCLaunchRedirectUri` valor en el campo **Direcciones URL de redireccionamiento** .  
       >[!IMPORTANT] 
       >Usará este valor de **dirección URL de redireccionamiento** en pasos posteriores.
    1. Pegue el valor ''OIDCLoginInitiationUri' en el campo **Url de inicio de sesión de OpenID Connect** .
    1. Pegue el `ToolPublicJwksUri` valor en el campo **Url del conjunto de claves** .
1. En **Extensiones**, seleccione la casilla **Vinculación profunda** .
1. Seleccione el botón **Registrar** en la parte inferior de la página. \
   Se mostrarán los detalles del registro de aplicaciones de Brightspace. Mantenga esta página abierta en su propia pestaña mientras completa el siguiente conjunto de pasos.

### <a name="add-brightspace-lti-platform-registration-details-to-the-microsoft-onedrive-lti-registration-portal"></a>Adición de detalles de registro de la plataforma LTI de Brightspace al portal de registro de LTI de Microsoft OneDrive

Una vez registrada la aplicación en Brightspace, copiará los valores del portal de registro de Brightspace en el Portal de registro de LTI de Microsoft.

1. Vuelva a la pestaña abrir el explorador de la página Del portal de registro de LTI de OneDrive de Microsoft.
1. Copie la página de detalles de registro de la aplicación Brightspace necesaria y péguela en el Portal de registro de LTI de Microsoft.
    1. Pegue el valor **issuer** de Brightspace en el campo **Emisor de LTI** de Microsoft.
    2. Pegue el valor del punto de **conexión de autenticación de OpenID Connect de Brightspace** en el campo **Dirección URL de autorización de LTI** de Microsoft.
    3. Pegue el valor de **LA URL del conjunto de claves de Brightspace** en el campo **Url de jwks públicos de LTI** de Microsoft.
    4. Pegue el valor de **Brightspace OAuth2 Access Token URL (DIRECCIÓN URL del token de acceso de Brightspace OAuth2** ) en el campo **Url del token de acceso LTI de** Microsoft.
    5. Pegue el valor de Id. de **cliente** de Brightspace en el campo Id. de **cliente LTI** de Microsoft.
1. Seleccione **Siguiente** > **guardar**. \
   Aparecerá un mensaje que indica que *el consumidor LTI se creó correctamente.* \
   Opcional: puede revisar los detalles del registro seleccionando el botón **Ver inquilinos LTI** en la página principal.

## <a name="step-2-deploy-the-lti-app-in-users-brightspace-experience"></a>Paso 2: Implementación de la aplicación LTI en la experiencia de Brightspace de los usuarios

Una vez conectados Microsoft OneDrive LTI y Brightspace, debe implementar la aplicación LTI de OneDrive en la experiencia de Brightspace de los usuarios.

1. En la pestaña con la experiencia de administrador de Brightspace, vaya a **Administración Tools** > **Manage Extensibility** > **LTI Advantage** para ver la lista de aplicaciones de LTI Advantage.
1. Seleccione el nombre de la aplicación LTI Advantage que creó en el paso anterior.
1. Desplácese hasta la parte inferior de la página y seleccione el vínculo **Ver implementaciones** . \
   La dirección URL debe tener un aspecto similar al de este ejemplo: `https://<yourbrightspacedomain>/d2l/le/ltiadvantage/deployments/home`
1. Seleccione **Nueva implementación**.
1. Seleccione la aplicación por el nombre que especificó al crear el registro de aplicación de Brightspace, como `Microsoft OneDrive LTI App`.
1. Escriba un nombre de implementación para esta implementación, como `Microsoft OneDrive Deployment`.
1. En la sección **Extensiones** , seleccione **Vínculo profundo**.
1. Seleccione todas las casillas de configuración de seguridad excepto **Classlist** y **Anonymous**.
1. No seleccione ninguna configuración, parámetros de sustitución ni parámetros de cliente.
1. Seleccione **Agregar unidades de organización** y elija las unidades de organización que desea usar la nueva aplicación LTI.  \
   También puede seleccionar:
   - La **organización raíz** junto con la opción **Todos los descendientes** para incluir a todos.
   - Unidades de organización individuales para incluir solo esas unidades.
   - **Todas las unidades descendientes** que usan los botones de radio de la columna **Opciones** .
1. Seleccione **Crear implementación**. \
   La nueva implementación se mostrará en la lista. Deje esta opción de pestaña y continúe con los pasos siguientes.

### <a name="create-links-to-the-onedrive-lti-app-in-brightspace"></a>Creación de vínculos a la aplicación LTI de OneDrive en Brightspace

En este paso se agrega la aplicación LTI de OneDrive a los menús de Brightspace LMS, donde los usuarios seleccionan insertar archivos de OneDrive.

1. En la pestaña con la experiencia de administrador de Brightspace, vaya a **Administración Tools** > **Manage Extensibility** > **LTI Advantage** para ver la lista de aplicaciones de LTI Advantage.
1. Seleccione el nombre de la aplicación LTI Advantage que creó.
1. Desplácese hasta la parte inferior de la página y seleccione el vínculo **Ver implementaciones** .
1. Seleccione el nombre de la implementación que creó en el paso anterior.
1. Desplácese hasta la parte inferior de la página y seleccione **Ver vínculos**.

#### <a name="create-a-deep-linking-quicklink-for-the-app-that-will-appear-in-the-quicklinks-menu"></a>Crear un **vínculo rápido de vinculación profunda** para la aplicación que aparecerá en el menú **Vínculos rápidos**

1. En la página **Ver vínculos** , seleccione **Nuevo vínculo**.
1. Escriba un nombre para el vínculo, como `Microsoft OneDrive`. \
   Este nombre será visible para los usuarios en su experiencia de Brightspace.
1. Pegue la **dirección URL de redireccionamiento** en el campo **URL** . \
   Esta es la misma **dirección URL de redireccionamiento** usada en los pasos anteriores, que se muestra en el `ToolOIDCLaunchRedirectUri` Portal de registro de LTI de OneDrive de Microsoft.
1. Establezca **Tipo** en **Vínculo rápido de vinculación profunda**.
1. Seleccione **+Agregar parámetro de cliente** y escriba `launchType` para el campo **Nombre** y `linkSelection` para el campo **Valor** .
1. Seleccione el botón **Guardar y cerrar** .

#### <a name="create-a-deep-linking-insert-stuff-link-for-the-app-that-will-appear-in-the-insert-stuff-menu"></a>Crear un vínculo **de inserción de vínculos profundos** para la aplicación que aparecerá en el menú **Insertar material**

1. En la página **Ver vínculos** , seleccione **Nuevo vínculo**.
1. Escriba un nombre para el vínculo, como `Microsoft OneDrive`. \
   Este nombre será visible para los usuarios en su experiencia de Brightspace.
1. Pegue la **dirección URL de redireccionamiento** en el campo **URL** . \
   Esta es la misma **dirección URL de redireccionamiento** usada en los pasos anteriores, que se muestra en el `ToolOIDCLaunchRedirectUri` Portal de registro de LTI de OneDrive de Microsoft.
1. Establezca **tipo** en **Material de inserción de vinculación profunda**.
1. Seleccione el botón **Guardar y cerrar** .

## <a name="step-3-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar"></a>Paso 3: Activar la nueva aplicación LTI de OneDrive en la barra de actividad de Quicklinks

La aplicación LTI de OneDrive ya está disponible para los usuarios, pero la aplicación de OneDrive anterior ahora debe estar desactivada.

1. Inicie sesión en el portal de administración de Brightspace.
1. Vaya a **Administración** >  **Config Variable Browser**
1. Busque la variable denominada **d2l.3rdParty.OneDrive.EnableOneDrivePicker** y establezca el valor en **off**.

Para agregar la aplicación LTI de OneDrive a la barra de actividad de Brightspace para obtener acceso rápido, deberá establecer una **variable de configuración** de unidad organizativa en el identificador de vínculo de la aplicación LTI.

> [!NOTE]
> Tendrá que repetir estos pasos para cada identificador de organización (o identificador de organización principal) en el que quiera que la aplicación LTI de OneDrive aparezca en la barra de actividad.

### <a name="collect-the-link-id"></a>Recopilación del identificador de vínculo

1. Inicie sesión en Brightspace como administrador o superadministrador.
1. Vaya a **herramientas de Administración** seleccionando el icono de engranaje en la parte superior derecha.
1. Seleccione **Administrar extensibilidad** para ver la lista **Implementaciones de LTI Advantage** .
1. Seleccione el nombre de la aplicación LTI Advantage que creó.
1. Desplácese hasta la parte inferior de la página y seleccione **Ver implementaciones**.
1. Seleccione el nombre de la implementación de la aplicación que creó.
1. Desplácese hacia abajo hasta la parte inferior de la página y seleccione **Ver vínculos**.
1. Seleccione el nombre del vínculo con el tipo **vínculo rápido de vinculación profunda** .
1. Mueva el mouse a la barra de direcciones URL del explorador.
1. Copie los dígitos numéricos después del final `/` en la dirección URL. \
   Por ejemplo, si la dirección URL del vínculo es `https://example.desire2learn.com/d2l/le/ltiadvantage/deployments/3bfcc0b7-2fb6-4ffe-b353-95b520d4bae6/links/details/259`, copie el `259` valor numérico.

### <a name="update-the-config-variables"></a>Actualización de las variables de configuración

1. En el portal de administración de Brightspace, vaya a **herramientas de Administración** seleccionando el icono de engranaje superior derecho.
1. Seleccione **Config Variable Browser (Explorador de variables de configuración**).
1. En el menú **Todas las variables** de la izquierda, vaya a **3rdParty** > **Microsoft** > y seleccione **OneDriveLTI**. \
   Debería ver el nombre `3rdparty.microsoft.onedriveLTI.linkId` de la variable en el panel derecho.
1. Seleccione el nombre de la **variable LinkId** .
1. En la pantalla **de configuración LinkId** , seleccione **Agregar valor** para seleccionar una **unidad organizativa** y pegue el valor numérico id. de **vínculo** que recopiló anteriormente.  \
   Tendrá que repetirlo para cada unidad organizativa que quiera usar en la **barra de actividad de vínculos rápidos**.
1. Para que esta configuración se aplique a los tipos de organización descendientes de los que ha agregado, puede editar los **tipos de unidad organizativa en cascada** y seleccionar qué tipos y en qué orden se aplicará la configuración.

La aplicación LTI de OneDrive ahora se mostrará en los menús **Agregar contenido existente**, **Vínculos rápidos** e **Insertar material** en Brightspace.

Los usuarios verán un icono de vínculo genérico en lugar de un icono de nube de OneDrive. El nombre que se muestra en el menú será el nombre proporcionado en la configuración del vínculo LTI de la aplicación.  

Estos vínculos se pueden desactivar y activar según lo deseado y dirigirse a organizaciones y personas fallecidas específicas por configuración.

Para obtener más información sobre cómo configurar aplicaciones en Brightspace, visite [la Ayuda de Brightspace](https://documentation.brightspace.com).

## <a name="common-questions-concerning-the-onedrive-lti-app"></a>Preguntas comunes sobre la aplicación LTI de OneDrive

### <a name="does-the-new-onedrive-lti-filepicker-support-personal-accounts"></a>¿El nuevo OneDrive LTI FilePicker admite cuentas personales?

Sí, las cuentas personales pueden abrir OneDrive para cargar los archivos. Hay una casilla en la aplicación en el Portal de registro de LTI de OneDrive para permitir varias cuentas o no. Si está activada, se permiten cuentas personales.

### <a name="does-the-filepicker-support-multiple-languages"></a>¿FilePicker admite varios idiomas?

El Objeto FilePicker de LTI de OneDrive examina el parámetro de configuración de idioma LTI pasado del LMS y (como copia de seguridad) la configuración del explorador (ya que la primera es una notificación opcional) para determinar el idioma que se va a usar.
