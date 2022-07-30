---
title: Configuración y configuración de los complementos de Moodle LMS para Open LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Prepárese para integrar Open LMS y Microsoft Teams mediante la configuración y configuración de los complementos de Moodle LMS.
ms.openlocfilehash: dbc85e8643159552e3e9bf340deef1856b542aab
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085979"
---
# <a name="set-up-and-configure-the-moodle-lms-plugins-for-open-lms"></a>Configuración y configuración de los complementos de Moodle LMS para Open LMS

En este artículo, aprenderá a instalar y configurar los complementos de Moodle LMS para integrar Microsoft Teams con su experiencia de Open LMS.

## <a name="prerequisites"></a>Requisitos previos

Para configurar y configurar un Open LMS instalado para que funcione con Microsoft Teams:

- Compruebe que [Moodle OpenID Connect](https://moodle.org/plugins/auth_oidc) y los complementos de [integración de Microsoft 365](https://moodle.org/plugins/local_o365) están activos.

## <a name="configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>Configuración de la conexión entre los complementos de Microsoft 365 y los servicios de Microsoft

Debe configurar la conexión entre los complementos de Microsoft 365 y los servicios de Microsoft para que puedan trabajar juntos.

> [!NOTE]
> Al configurar la integración, mantenga la página de configuración de integración de Microsoft 365 abierta en una pestaña independiente del explorador, ya que tendrá que volver a estas páginas a lo largo del proceso.

### <a name="enable-the-openid-connect-authentication-plugin"></a>Habilitación del complemento de autenticación de OpenID Connect

Para que los complementos de Moodle se comuniquen con los servicios de Microsoft, el complemento de autenticación OpenID Connect debe estar activado y configurado.

1. Vaya a **Autenticación** **de complementos** >  de **administración** >  del sitio y seleccione **Administrar autenticación**.
1. Busque el complemento de autenticación **OpenID Connect** y seleccione el *icono de ojo* para activarlo.
1. Seleccione **Configuración** para que el complemento compruebe los puntos de conexión **de autorización** y **token** .
    1. Los valores predeterminados deben ser:
        1. Punto de conexión de autorización: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Punto de conexión de token: ``https://login.microsoftonline.com/common/oauth2/token``.
1. Registre el **URI de redireccionamiento** para su uso posterior.

> [!NOTE]
> No es necesario que todos los usuarios de Open LMS usen el complemento de autenticación OpenID Connect como método de autenticación; sin embargo, si usan otros métodos de autenticación, sus cuentas de Open LMS deben *estar conectadas* a sus cuentas de Microsoft correspondientes para poder usar ciertas características en la integración de Teams, como la sincronización de la propiedad y la pertenencia de Teams.

### <a name="requisites"></a>Requisitos

Registre Open LMS como una aplicación en Azure AD mediante el script de PowerShell. El script aprovisiona los siguientes elementos:

- Una nueva aplicación de Azure AD para el inquilino de Microsoft 365, que usan los complementos de Microsoft 365 Moodle.
- La aplicación para el inquilino de Microsoft 365 configura las direcciones URL de respuesta y los permisos necesarios para la aplicación aprovisionada y devuelve y `AppID` `Key`.
- En sistemas operativos que no son Windows, solo debe seguir el proceso manual para registrar la instancia de Open LMS en Azure. Consulte la sección *Alerta importante* a continuación para obtener más información.

> [!IMPORTANT]
> Para obtener más información sobre cómo registrar manualmente la instancia de Open LMS, consulte Registro de la [instancia de Open LMS como aplicación](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration).
>
> Una vez que registre la aplicación, compruebe que se aplican todos los permisos de aplicación de Azure. Para obtener más información, consulte [Permisos de aplicaciones de Azure](https://docs.moodle.org/400/en/Microsoft_365#Azure_app_permissions).

### <a name="register-application-in-azure-using-powershell"></a>Registro de una aplicación en Azure mediante PowerShell

#### <a name="step-1-create-azure-app"></a>Paso 1: Creación de una aplicación de Azure

1. Vaya a **Complementos** de **administración** >  del sitio **Complementos** >  locales y seleccione **Integración de Microsoft 365**. Se abrirá la página configuración de integración de Microsoft 365.

1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración** .

1. Seleccione el botón **Descargar script de PowerShell** y guárdelo como una carpeta ZIP en el equipo local.

    > [!NOTE]
    > Al ejecutar el script, se crea una nueva aplicación de Azure AD en el inquilino de Microsoft 365, que configura las direcciones URL de respuesta y los permisos necesarios, proporciona los permisos necesarios y devuelve y `AppID` `Key`.
    >
    > El script no funciona en PowerShell en sistemas operativos que no son Windows.

1. Prepare el script de PowerShell desde el archivo ZIP de la siguiente manera:
    1. Descargue y extraiga el `Moodle-AzureAD-Powershell.zip` archivo.
    1. Abra la carpeta extraída.
    1. Haga clic con el botón derecho en el `Moodle-AzureAD-Script.ps1` archivo y seleccione **Propiedades**.
    1. En la pestaña **General** del ventana Propiedades, active la `Unblock` casilla situada junto al atributo **Seguridad** situado en la parte inferior de la ventana.
    1. Seleccione **Aceptar**.
    1. Copie la ruta de acceso del directorio a la carpeta extraída.

1. Ejecute PowerShell como administrador:
    1. En Windows, abra el menú Inicio.
    1. Tipo `PowerShell`.
    1. Haga clic con el botón derecho en **Windows PowerShell**.
    1. Seleccione **Ejecutar como administrador**.

1. Vaya al directorio descomprimido; para ello, escriba `cd .../.../Moodle-AzureAD-Powershell` dónde `.../...` es la ruta de acceso al directorio.

1. Ejecute el script de PowerShell:
    1. Escriba `./Moodle-AzureAD-Script.ps1`.
    1. Cuando se le pregunte, inicie sesión en su cuenta de administrador de Microsoft 365 en la ventana emergente.
    1. Cuando se le solicite, escriba el nombre de la aplicación de Azure AD. Por ejemplo, complementos de Open LMS, Moodle o Moodle.
    1. Cuando se le pregunte, escriba la dirección URL del servidor Open LMS.
    1. Cuando se le pregunte, escriba la dirección URL de respuesta copiada de la página de configuración del complemento de autenticación openID Connect. Esta es la dirección URL del sitio de Open LMS seguida de `\auth\oidc\`.
    1. Es posible que se le pida que vuelva a iniciar sesión en su cuenta de Microsoft 365 en una ventana emergente del proceso. Esto es para proporcionar el consentimiento del administrador a los permisos agregados a la aplicación para su organización.
    1. Cuando el script termine de ejecutarse, copie el **identificador de aplicación (`AppID`)** y **la clave de aplicación (`Key`)** generados por el script y guárdelos.

#### <a name="step-2-set-azure-app-details-in-openid-connect"></a>Paso 2: Establecer los detalles de la aplicación de Azure en OpenID Connect

1. Vuelva a la página de configuración del complemento de autenticación de OpenID Connect.
1. Pegue el `AppID` valor en el cuadro **Id. de** aplicación y el `Key` valor en el cuadro **Clave** y, a continuación, seleccione **Guardar cambios**.

#### <a name="step-3-configure-connection-between-microsoft-plugins-and-microsoft-services"></a>Paso 3: Configurar la conexión entre los complementos de Microsoft y los servicios de Microsoft

1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración** .
1. En **Elegir método de conexión**, seleccione **Acceso a la aplicación** y, a continuación, seleccione **Guardar cambios** de nuevo.
1. Una vez actualizada la página, puede ver otra nueva sección **Administración consentimiento & información adicional**.
    1. Seleccione **Proporcionar Administración vínculo consentimiento**, escriba sus credenciales de administrador global de Microsoft 365 y, a continuación, **Acepte** para conceder los permisos.
    1. Junto al campo **Inquilino de Azure AD** , seleccione el botón **Detectar** .
    1. Junto a la **dirección URL de OneDrive para la Empresa**, seleccione el botón **Detectar**.
    1. Después de rellenar los campos, vuelva a seleccionar el botón **Guardar cambios** .
1. Seleccione el botón **Actualizar** para comprobar la instalación. Si no se notifica ningún error en esta fase, significa que los complementos de Microsoft pueden comunicarse con Microsoft Server a través de las API de Microsoft Graph.

#### <a name="step-4-configure-user-and-course-synchronization"></a>Paso 4: Configuración de la sincronización de usuarios y cursos

1. Sincronice los usuarios entre el servidor Open LMS y Azure AD. En función del entorno, puede seleccionar diferentes opciones durante esta fase. Para empezar:

    1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración de sincronización** .

    1. En la configuración **Sincronizar usuarios con Azure AD** , active las casillas que se aplican a su entorno. Debe seleccionar las siguientes opciones:  
        ✔ Cree cuentas en Open LMS para los usuarios de Azure AD.
       ✔ Actualice todas las cuentas de Open LMS para los usuarios de Azure AD.

    1. En la sección **Restricción de creación** de usuarios, puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizan con Open LMS.

        > [!NOTE]
        > No es absolutamente necesario habilitar la sincronización del usuario; sin embargo, facilitará mucho la conexión de usuarios de Open LMS con cuentas de Microsoft 365.
        >
        > La sincronización de usuarios se realiza mediante la ejecución de la tarea **sincronización de usuarios con Azure AD** programada.

1. En la sección **Sincronización de cursos** , puede seleccionar la opción **de personalización Sincronización** de cursos para habilitar la creación automática de Teams para algunos o todos los cursos de Open LMS existentes.

    > [!NOTE]
    > La sincronización del curso se realiza mediante la **ejecución de los cursos de Sync Moodle en** la tarea programada de Microsoft Teams.

1. Guarde los cambios.

1. Para validar la configuración de sincronización, tendrá que ejecutar las tareas programadas manualmente por primera vez. Vaya a Tareas **programadas** del **servidor** > **de** >  **administración** >  del sitio.

    1. Desplácese hacia abajo y busque la tarea **Sincronizar usuarios con Azure AD** y seleccione **Ejecutar ahora**.
        1. Esto sincronizará los usuarios de Azure AD con el sitio de Open LMS según las opciones de sincronización de usuarios.
    1. A continuación, busque la tarea **Sincronizar cursos de Moodle con Microsoft Teams** y seleccione **Ejecutar ahora**.
        1. Esta tarea creará grupos para todos los cursos de Open LMS con la opción de sincronización activada, y también Teams si se puede encontrar un **propietario de equipo** en el curso.
        1. Esta tarea también sincronizará a los usuarios de Open LMS inscritos en el curso con Teams como propietarios o miembros.
            1. El **propietario** de un equipo es un usuario de Open LMS que cumple todos los criterios siguientes:
                1. está conectado a una cuenta de Microsoft 365.
                2. está inscrito en el curso.
                3. tiene la `local/o365:teamowner` funcionalidad en el contexto del curso.
            1. Del mismo modo, un **miembro** del equipo es un usuario de Open LMS que cumple todos los criterios siguientes:
                1. está conectado a una cuenta de Microsoft 365.
                2. está inscrito en el curso.
                3. tiene la `local/o365:teamember` funcionalidad en el contexto del curso.
            1. El rol *maestro* predeterminado tiene la `local/o365:teamowner` funcionalidad y el rol *student* predeterminado tiene la `local/o365:teammember` funcionalidad .

> [!NOTE]
> [Moodle Cron](https://docs.moodle.org/400/en/Cron) desencadena las tareas programadas, que deben configurarse para que se ejecuten con frecuencia. Cada tarea programada puede tener una programación predeterminada y se puede personalizar.
>
> - La programación predeterminada de la tarea **Sincronizar usuarios con Azure AD** es cada minuto.
> - La programación predeterminada de la tarea **Sincronizar cursos de Moodle con Microsoft Teams** es diaria a la 1 a. m. en la zona horaria predeterminada del servidor Open LMS.

Una vez instalados y configurados los complementos, puede hacer lo siguiente:

- [Agregue clases y reuniones de Teams a Open LMS](open-lms-teams-classes-and-meetings.md).
- [Implementación del bot de Moodle Assistant en Azure](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
- [Agregue pestañas de Moodle a las clases de Teams](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).

## <a name="extra-moodle-plugin-documentation"></a>Documentación adicional del complemento Moodle

Si desea revisar las guías de integración y las notas de la versión de Microsoft 365 de Open LMS, consulte estos recursos:

- [Documentación de integración de Microsoft 365 sobre Moodle Docs](https://docs.moodle.org/400/en/Microsoft_365).
