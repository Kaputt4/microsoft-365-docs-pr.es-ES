---
title: Configuración y configuración de los complementos de Moodle LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Prepárese para integrar Moodle y Microsoft Teams mediante la configuración y configuración de los complementos de Moodle LMS.
ms.openlocfilehash: 854a4d261f0848d3a33040b9bf9b90d6bafd09b7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68177618"
---
# <a name="set-up-the-moodle-lms-plugins"></a>Configuración de los complementos de Moodle LMS

En este artículo, aprenderá a instalar y configurar los complementos de Moodle LMS para incorporar Microsoft Teams con su experiencia de Moodle.

## <a name="prerequisites"></a>Requisitos previos

Estos son los requisitos previos para configurar una instancia de Moodle instalada para que funcione con Microsoft Teams:

- Credenciales de administrador de Moodle.
- Credenciales de administrador de Azure AD.
- Una suscripción de Azure en la que puede crear nuevos recursos.

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Instalar los complementos de Microsoft 365 Moodle

La integración de Moodle con Microsoft Teams cuenta con la tecnología código abierto [conjunto de complementos de Microsoft 365 Moodle](https://moodle.org/plugins/browse.php?list=set&id=72).

### <a name="requisite-applications-and-plugins"></a>Aplicaciones y complementos necesarios

Descargue e instale los siguientes elementos:

1. Una [versión estable actual de Moodle](https://download.moodle.org/releases/latest/).

    > [!IMPORTANT]
    > Si no tiene un sitio de Moodle existente, vaya al repositorio [de Moodle en Azure](https://github.com/azure/moodle) e implemente rápidamente una instancia de Moodle y personalícela según sus necesidades.

1. Descargue y guarde moodle [OpenID Connect](https://moodle.org/plugins/auth_oidc) y los complementos de [integración de Microsoft 365](https://moodle.org/plugins/local_o365) en el equipo local.

    > [!NOTE]
    > Para la integración de Teams, es necesario instalar los complementos OpenID Connect y Microsoft 365 Integration.
    >
    > Además, se recomienda instalar el complemento [tema de Microsoft 365 Teams](https://moodle.org/plugins/theme_boost_o365teams) .

### <a name="install-plugins"></a>Instalación de complementos

1. Descargue los complementos, extráigalos y cárguelos en sus carpetas correspondientes.
    - Extraiga el complemento OpenID Connect (auth_oidc) en una carpeta denominada **oidc** y cárguelo en la carpeta **de autenticación** de la raíz del documento de Moodle.
    - Extraiga el complemento de integración de Microsoft 365 (local_o365) en una carpeta denominada **o365** y cárguelo en la carpeta **local** de la raíz del documento de Moodle.
1. Inicie sesión en el sitio de Moodle como administrador y seleccione **Administración del sitio**.
1. Tras la detección de nuevos complementos que se instalarán, Moodle debería redirigirle a la página instalar nuevos complementos. Si esto no ocurre, en la página **Administración del sitio** , seleccione **Notificaciones** en la pestaña **General** , esta acción debe desencadenar la instalación de los complementos.
1. Una vez instalados los nuevos complementos, Moodle le mostrará una página con todas las nuevas configuraciones de los complementos instalados. Puede omitir esta página de forma segura aplicando la configuración predeterminada. Los complementos se configurarán en los pasos siguientes.

## <a name="2-enable-the-openid-connect-authentication-plugin"></a>2. Habilitar el complemento de autenticación de OpenID Connect

Para que los complementos de Moodle se comuniquen con los servicios de Microsoft, el complemento de autenticación OpenID Connect debe estar activado y configurado.

1. Vaya a **Autenticación** **de complementos** >  de **administración** >  del sitio y seleccione **Administrar autenticación**.
1. Busque el complemento de autenticación **OpenID Connect** y seleccione el *icono de ojo* para activarlo.
1. Seleccione **Configuración** para que el complemento compruebe los puntos de conexión **de autorización** y **token** .
    1. Los valores predeterminados deben ser:
        1. Punto de conexión de autorización: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Punto de conexión de token: ``https://login.microsoftonline.com/common/oauth2/token``.
1. Registre el **URI de redireccionamiento** para su uso posterior.

    > [!NOTE]
    > No es necesario que todos los usuarios de Moodle accedan al complemento de autenticación OpenID Connect como método de autenticación; sin embargo, si usan otros métodos de autenticación, sus cuentas de Moodle deben *estar conectadas* a sus cuentas de Microsoft correspondientes para poder usar ciertas características en la integración de Teams, como la sincronización de la propiedad y la pertenencia de Teams.

## <a name="3-configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>3. Configurar la conexión entre los complementos de Microsoft 365 y los servicios de Microsoft

Debe configurar la conexión entre los complementos de Microsoft 365 y los servicios de Microsoft para que puedan trabajar juntos.

> [!NOTE]
> Al configurar la integración, mantenga la página de configuración de Microsoft 365 Moodle Integration abierta en una pestaña independiente del explorador, ya que debe volver a este conjunto de páginas a lo largo del proceso.

### <a name="create-azure-app"></a>Creación de una aplicación de Azure

1. Vaya a **Complementos** de **administración** >  del sitio **Complementos** >  locales y seleccione **Integración de Microsoft 365**. Se abrirá la página configuración de integración de Microsoft 365.

1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración** .

1. Seleccione el botón **Descargar script de PowerShell** y guárdelo como una carpeta ZIP en el equipo local.

    > [!NOTE]
    > Al ejecutar el script, se crea una nueva aplicación de Azure AD en el inquilino de Microsoft 365, que configura las direcciones URL de respuesta y los permisos necesarios, proporciona los permisos necesarios y devuelve y `AppID` `Key`.
    >
    > El script de PowerShell solo funciona en sistemas operativos Windows.

1. Prepare el script de PowerShell desde el archivo ZIP de la siguiente manera:
    1. Descargue y extraiga el `Moodle-AzureAD-Powershell.zip` archivo.
    1. Abra la carpeta extraída.
    1. Haga clic con el botón derecho en el `Moodle-AzureAD-Script.ps1` archivo y seleccione **Propiedades**.
    1. En la pestaña **General** del ventana Propiedades, active la `Unblock` casilla situada junto al atributo **Seguridad** situado en la parte inferior de la ventana.
    1. Seleccione **Aceptar**.
    1. Copie la ruta de acceso del directorio a la carpeta extraída.

1. Ejecute PowerShell como administrador:
    1. En Windows, seleccione **Iniciar**.
    1. Tipo `PowerShell`.
    1. Haga clic con el botón derecho en **Windows PowerShell**.
    1. Seleccione **Ejecutar como administrador**.

1. Vaya al directorio descomprimido; para ello, escriba `cd .../.../Moodle-AzureAD-Powershell` dónde `.../...` es la ruta de acceso al directorio.

1. Ejecute el script de PowerShell:
    1. Escriba `./Moodle-AzureAD-Script.ps1`.
    1. Cuando se le pregunte, inicie sesión en su cuenta de administrador de Microsoft 365 en la ventana emergente.
    1. Cuando se le pregunte, escriba el nombre de la aplicación de Azure AD, por ejemplo, complementos de Moodle o Moodle.
    1. Cuando se le pregunte, escriba la dirección URL del servidor de Moodle.
    1. Cuando se le pregunte, escriba la dirección URL de respuesta copiada de la página de configuración del complemento de autenticación openID Connect. Esta es esencialmente la dirección URL del sitio de Moodle, seguida de `\auth\oidc\`.
    1. Es posible que se le pida que vuelva a iniciar sesión en su cuenta de Microsoft 365 en una ventana emergente del proceso. Esto es para proporcionar el consentimiento del administrador a los permisos agregados a la aplicación para su organización.
    1. Cuando el script termine de ejecutarse, copie el **identificador de aplicación (`AppID`)** y **la clave de aplicación (`Key`)** generados por el script y guárdelos.

### <a name="set-azure-app-details-in-moodle"></a>Establecimiento de los detalles de la aplicación de Azure en Moodle

1. Vuelva a la página de configuración del complemento de autenticación de OpenID Connect.
1. Pegue el `AppID` valor en el cuadro **Id. de** aplicación y el `Key` valor en el cuadro **Clave** y, a continuación, seleccione **Guardar cambios**.

### <a name="configure-connection-between-microsoft-plugins-and-microsoft-services"></a>Configuración de la conexión entre los complementos de Microsoft y los servicios de Microsoft

1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración** .
1. En **Elegir método de conexión**, seleccione **Acceso a la aplicación** y, a continuación, seleccione **Guardar cambios** de nuevo.
1. Una vez actualizada la página, puede ver otra nueva sección **Administración consentimiento & información adicional**.
    1. Seleccione **Proporcionar Administración vínculo consentimiento**, escriba sus credenciales de administrador global de Microsoft 365 y, a continuación, **Acepte** para conceder los permisos.
    1. Junto al campo **Inquilino de Azure AD** , seleccione el botón **Detectar** .
    1. Junto a la **dirección URL de OneDrive para la Empresa**, seleccione el botón **Detectar**.
    1. Después de rellenar los campos, vuelva a seleccionar el botón **Guardar cambios** .
1. Seleccione el botón **Actualizar** para comprobar la instalación. Si no se notifica ningún error en esta fase, significa que los complementos de Microsoft pueden comunicarse con Microsoft Server a través de las API de Microsoft Graph.

### <a name="configure-user-and-course-synchronization"></a>Configuración de la sincronización de usuarios y cursos

1. Sincronice los usuarios entre el servidor de Moodle y Azure AD. En función del entorno, puede seleccionar diferentes opciones durante esta fase. Para empezar:
    1. En la página Configuración de integración de Microsoft 365, seleccione la pestaña **Configuración de sincronización** .

    1. En la configuración **Sincronizar usuarios con Azure AD** , active las casillas que se aplican a su entorno. Debe seleccionar las siguientes opciones:  
        ✔ Cree cuentas en Moodle para los usuarios de Azure AD.
       ✔ Actualice todas las cuentas de Moodle para los usuarios de Azure AD.

    1. En la sección **Restricción de creación** de usuarios, puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizan con Moodle.

    > [!NOTE]
    > No es necesario activar la sincronización del usuario; sin embargo, facilitará mucho la conexión de usuarios de Moodle con cuentas de Microsoft 365.
    >
    > La sincronización de usuarios se realiza mediante la ejecución de la tarea **sincronización de usuarios con Azure AD** programada.

1. En la sección **Sincronización de cursos** , puede seleccionar la opción **de personalización Sincronización** de cursos para activar la creación automática de Teams para algunos o todos los cursos de Moodle existentes.

    > [!NOTE]
    > La sincronización del curso se realiza mediante la **ejecución de los cursos de Sync Moodle en** la tarea programada de Microsoft Teams.

1. Guarde los cambios.

1. Para validar la configuración de sincronización, tendrá que ejecutar las tareas programadas manualmente por primera vez, vaya a Tareas **programadas** del **servidor** > **de** >  **administración** >  del sitio.

    1. Desplácese hacia abajo y busque la tarea **Sincronizar usuarios con Azure AD** y seleccione **Ejecutar ahora**.
        1. Esto sincronizará a los usuarios de Azure AD con el sitio de Moodle según las opciones de sincronización de usuarios.
    1. A continuación, busque la tarea **Sincronizar cursos de Moodle con Microsoft Teams** y seleccione **Ejecutar ahora**.
        1. Esta tarea creará grupos para todos los cursos de Moodle con la opción de sincronización activada, y también Teams si se puede encontrar un **propietario de equipo** en el curso.
        1. La tarea también sincronizará a los usuarios de Moodle inscritos en el curso con Teams como propietarios o miembros.
            1. Un **propietario del** equipo es un usuario de Moodle que
                1. está conectado a una cuenta de Microsoft 365, Y
                2. está inscrito en el curso, Y
                3. tiene la `local/o365:teamowner` funcionalidad en el contexto del curso.
            1. Del mismo modo, un **miembro** del equipo es un usuario de Moodle que
                1. está conectado a una cuenta de Microsoft 365, Y
                2. está inscrito en el curso, Y
                3. tiene la `local/o365:teamember` funcionalidad en el contexto del curso.
            1. El rol *maestro* predeterminado tiene la `local/o365:teamowner` funcionalidad y el rol *student* predeterminado tiene la `local/o365:teammember` funcionalidad .

> [!NOTE]
> [Moodle Cron](https://docs.moodle.org/400/en/Cron) desencadena las tareas programadas, que deben configurarse para que se ejecuten con frecuencia. Cada tarea programada puede tener una programación predeterminada, que se puede personalizar.
>
> - La programación predeterminada de la tarea **Sincronizar usuarios con Azure AD** es cada minuto.
> - La programación predeterminada de la tarea **Sincronizar cursos de Moodle con Microsoft Teams** es diaria a la 1:00 en la zona horaria predeterminada del servidor de Moodle.

Una vez instalados y configurados los complementos, puede hacer lo siguiente:

- [Implementación del bot de Moodle Assistant en Azure](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
- [Agregue pestañas de Moodle a las clases de Teams](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
- [Agregue clases y reuniones de Teams a Moodle LMS](teams-classes-meetings-with-moodle.md).

## <a name="extra-moodle-plugin-documentation"></a>Documentación adicional del complemento Moodle

Si desea revisar las guías de integración de Moodle de Microsoft 365 y las notas de la versión, consulte estos recursos:

- [Documentación de integración de Microsoft 365 sobre Moodle Docs](https://docs.moodle.org/400/en/Microsoft_365).
