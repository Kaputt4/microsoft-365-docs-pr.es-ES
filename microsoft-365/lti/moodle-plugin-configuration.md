---
title: Configuración y configuración del complemento Moodle
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
description: Prepárese para integrar Moodle y Microsoft Teams mediante la configuración y configuración del complemento Moodle.
ms.openlocfilehash: c6c022ee2f567dc917a0be164daf4f39a74996b1
ms.sourcegitcommit: 4e7ff69f4d7d27c2d419f763cfcb069e3b0d0d9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65403215"
---
# <a name="set-up-and-configure-the-moodle-plugin"></a>Configuración y configuración del complemento Moodle

En este artículo, aprenderá a instalar y configurar el complemento Moodle LMS para incorporar Microsoft Teams con su experiencia de Moodle.

> [!NOTE]
> Actualmente, las integraciones de Moodle y Microsoft Teams LTI solo están disponibles en versión preliminar privada.
>
>Si desea participar en el programa de versión preliminar privada, [regístrese aquí](https://m365crmedu.powerappsportals.com/LMSSignup).

## <a name="prerequisites"></a>Requisitos previos

Estos son los requisitos previos para instalar Moodle:

* Credenciales de administrador de Moodle.
* Credenciales de administrador de Azure AD.
* Una suscripción de Azure en la que puede crear nuevos recursos.

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Instalar los complementos de Moodle Microsoft 365

La integración de Moodle en Microsoft Teams se basa en el [conjunto de complementos código abierto Microsoft 365 Moodle](https://moodle.org/plugins/browse.php?list=set&id=72).

### <a name="requisite-applications-and-plugins"></a>Aplicaciones y complementos necesarios

Instale y descargue los siguientes elementos antes de continuar con la instalación de complementos de Moodle Microsoft 365:

1. Una [versión estable actual de Moodle](https://download.moodle.org/releases/latest/).
1. Descargue y guarde la [Conectar Moodle OpenID](https://moodle.org/plugins/auth_oidc) y los complementos [de integración de Microsoft 365](https://moodle.org/plugins/local_o365) en el equipo local.

    > [!NOTE]
    > Para la integración de Teams, es necesario instalar los complementos Conectar y Microsoft 365 Integration de OpenID.
    >
    > Se recomienda el complemento [tema de Microsoft 365 Teams](https://moodle.org/plugins/theme_boost_o365teams).

### <a name="microsoft-365-moodle-plugins"></a>complementos de moodle de Microsoft 365

#### <a name="install-plugins"></a>Instalación de complementos

1. Descargue los complementos, extráigalos y cárguelos en sus carpetas correspondientes. Por ejemplo, extraiga el complemento openID Conectar (auth_oidc) en una carpeta denominada **oidc** y cárguelo en la carpeta **de autenticación** de la raíz del documento de Moodle.
2. Inicie sesión en el sitio de Moodle como administrador y seleccione **Administración del sitio**.
3. Tras la detección de nuevos complementos que se instalarán, Moodle debería redirigirle a la página instalar nuevos complementos. Si esto no ocurre, en la página **Administración del sitio** , seleccione **Notificaciones** en la pestaña **General** , esto debería desencadenar la instalación de los complementos.

    > [!IMPORTANT]
    >
    > * Mantenga abierta la página de configuración de los complementos de Moodle Microsoft 365 en una pestaña independiente del explorador, ya que debe volver a este conjunto de páginas a lo largo del proceso.  
    >
    > * Si no tiene un sitio de Moodle existente, vaya al repositorio [de Moodle en Azure](https://github.com/azure/moodle) e implemente rápidamente una instancia de Moodle y personalícela según sus necesidades.

#### <a name="enable-the-openid-connect-authentication-plugin"></a>Habilitación del complemento de autenticación Conectar OpenID

1. Vaya a **Administración del** >  **sitioPluginsAuthentication** >  y seleccione **Administrar autenticación**.
1. Busque el complemento de autenticación **openID Conectar** y seleccione el *icono de ojo* para habilitarlo.
1. Seleccione **Configuración** para que el complemento compruebe los puntos de conexión **de autorización** y **token**.
    1. Los valores predeterminados deben ser:
        1. Punto de conexión de autorización: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Punto de conexión de token: ``https://login.microsoftonline.com/common/oauth2/token``.
1. Registre el **URI de redireccionamiento** para su uso posterior.

## <a name="2-configure-the-connection-between-the-microsoft-365-plugins-and-azure-ad"></a>2. Configuración de la conexión entre los complementos de Microsoft 365 y Azure AD

Debe configurar la conexión entre los complementos de Microsoft 365 y Azure AD.

### <a name="requisites"></a>Requisitos

Registre Moodle como una aplicación en Azure AD mediante el script de PowerShell. El script aprovisiona los siguientes elementos:

* Una nueva aplicación de Azure AD para el inquilino de Microsoft 365, que usa la Microsoft 365 Complementos de Moodle.
* La aplicación para el inquilino de Microsoft 365 configura las direcciones URL de respuesta y los permisos necesarios para la aplicación aprovisionada y devuelve y `AppID` `Key`.

Use la página de configuración de complementos de Moodle generada `AppID` y `Key` en su Microsoft 365 para configurar el sitio de servidor de Moodle con Azure AD.

> [!IMPORTANT]
> * Para obtener más información sobre cómo registrar manualmente la instancia de Moodle, consulte Registro de la [instancia de Moodle como aplicación](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration).

### <a name="the-teams-for-moodle-set-up-process"></a>El proceso de configuración de Teams para Moodle

1. En la página complementos de integración de Microsoft 365, seleccione la pestaña **Configuración**.

1. Seleccione el botón **Descargar script de PowerShell** y guárdelo como una carpeta ZIP en el equipo local.

1. Prepare el script de PowerShell desde el archivo ZIP de la siguiente manera:

    1. Descargue y extraiga el `Moodle-AzureAD-Powershell.zip` archivo.
    1. Abra la carpeta extraída.
    1. Haga clic con el botón derecho en el `Moodle-AzureAD-Script.ps1` archivo y seleccione **Propiedades**.
    1. En la pestaña **General** del ventana Propiedades, active la `Unblock` casilla situada junto al atributo **Seguridad** situado en la parte inferior de la ventana.
    1. Seleccione **Aceptar**.
    1. Copie la ruta de acceso del directorio a la carpeta extraída.

1. Ejecute PowerShell como administrador:

    1. Seleccione Inicio.
    1. Escriba PowerShell.
    1. Haga clic con el botón derecho en **Windows PowerShell**.
    1. Seleccione **Ejecutar como administrador**.

1. Vaya al directorio descomprimido; para ello, escriba `cd .../.../Moodle-AzureAD-Powershell` dónde `.../...` es la ruta de acceso al directorio.

1. Ejecute el script de PowerShell:

    1. Escriba `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    1. Escriba `./Moodle-AzureAD-Script.ps1`.
    1. Inicie sesión en la cuenta de administrador de Microsoft 365 en la ventana emergente.
    1. Escriba el nombre de la aplicación de Azure AD, por ejemplo, complementos de Moodle o Moodle.
    1. Escriba la dirección URL del servidor de Moodle.
    1. Copie el **identificador de aplicación (`AppID`)** y **la clave de aplicación (`Key`)** generados por el script y guárdelos.

1. Vuelva a la página de administración de complementos, **Administración** >  del **sitioPluginsAuthenticationOpenID** >  >  **Conectar**.

1. Pegue el `AppID` valor en el cuadro **Id. de** aplicación y el `Key` valor en el cuadro **Clave** y, a continuación, seleccione **Guardar cambios**.

1. Vaya a **Administración** >  del **sitioPluginsLocal plugins (Complementos** >  **locales**) y seleccione **Microsoft 365 Integration (Integración de Microsoft 365**).

1. En **Elegir método de conexión**, seleccione **Acceso a la aplicación** y, a continuación, seleccione **Guardar cambios** de nuevo.

1. Después de actualizar la página, puede ver otra nueva sección **Consentimiento del administrador & información adicional**.
    1. Seleccione **El vínculo Proporcionar consentimiento del administrador**, escriba las credenciales de administrador global de Microsoft 365 y, a continuación, **Acepte** para conceder los permisos.
    1. Junto al campo **Inquilino de Azure AD** , seleccione el botón **Detectar** .
    1. Junto a la **dirección URL de OneDrive para la Empresa**, seleccione el botón **Detectar**.
    1. Después de rellenar los campos, vuelva a seleccionar el botón **Guardar cambios** .

1. Seleccione el botón **Actualizar** para comprobar la instalación y, a continuación, seleccione **Guardar cambios**.

1. Sincronice los usuarios entre el servidor de Moodle y Azure AD. En función del entorno, puede seleccionar diferentes opciones durante esta fase. Para empezar:
    1. Cambie a la **pestaña Sincronizar Configuración**.

    1. En la sección **Sincronizar usuarios con Azure AD** , active las casillas que se aplican a su entorno. Debe seleccionar las siguientes opciones:  

        ✔ Cree cuentas en Moodle para los usuarios de Azure AD.
        
        ✔ Actualice todas las cuentas de Moodle para los usuarios de Azure AD.
        

    1. En la sección **Restricción de creación** de usuarios, puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizan con Moodle.
    1. En la sección **Sincronización de cursos**, puede seleccionar la opción **de personalización Sincronización** de cursos para habilitar la creación automática de grupos y Teams para algunos o todos los cursos de Moodle existentes.

1. Para validar las tareas [cron](https://docs.moodle.org/400/en/Cron) y ejecutarlas manualmente por primera vez, vaya a **Administración** >  del **sitioServerTasksNombres** >  **programados** > .

    1. Desplácese hacia abajo y busque la tarea **Sincronizar usuarios con Azure AD** y seleccione **Ejecutar ahora**.
        1. Esto sincronizará el usuario de AAD con el sitio de Moodle.
    1. A continuación, busque los **cursos de Sync Moodle para Microsoft Teams** tarea y seleccione **Ejecutar ahora**.
        1. Esta tarea creará grupos y Teams si se encuentra un propietario.
        1. Si el usuario tiene `local/o365:teamowner` capacidad en el contexto del curso, el usuario es propietario del equipo. Si el usuario tiene `local/o365:teammember` funcionalidad en el contexto del curso, el usuario es miembro del equipo.  
        1. El rol *maestro* predeterminado tiene el `local/o365:teamowner" capability`y el rol *student* predeterminado tiene la `local/o365:teammember` funcionalidad .

    > [!NOTE]
    >
    > Moodle [Cron](https://docs.moodle.org/400/en/Scheduled_tasks) se ejecuta según la programación de tareas. La programación predeterminada es una vez al día a la 1:00 AM en la zona horaria local del servidor. Sin embargo, el cron debe ejecutarse con más frecuencia para mantener todo sincronizado.

1. Vaya a **Administración** >  del **sitioIns complementos** >  >  **locales** **Microsoft 365 pestaña Integración** >  **Teams Configuración**.

1. Haga clic en el botón **Comprobar configuración de Moodle** para actualizar todas las configuraciones necesarias para que la integración Teams funcione.
        

Una vez instalados y configurados los complementos, puede hacer lo siguiente:

* [Implementación del bot de Moodle Assistant en Azure](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
* [Agregue pestañas de Moodle a las clases de Teams](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
* [Agregue Teams clases y reuniones a Moodle LMS](teams-classes-meetings-with-moodle.md).

## <a name="extra-moodle-plugin-documentation"></a>Documentación adicional del complemento Moodle

Si desea revisar las guías de integración y las notas de la versión de Moodle Microsoft 365, consulte estos recursos:

* [Microsoft 365 documentación de integración en Moodle Docs](https://docs.moodle.org/400/en/Microsoft_365).
