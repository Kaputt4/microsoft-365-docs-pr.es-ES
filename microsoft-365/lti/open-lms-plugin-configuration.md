---
title: Configuración y configuración del complemento Moodle para Open LMS
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
description: Prepárese para integrar One LMS y Microsoft Teams configurando y configurando el complemento Moodle.
ms.openlocfilehash: e59d9298d61060f4d898e773cc5800d32e86bebf
ms.sourcegitcommit: f181e110cdb983788a86f30d5bb018e53c83e64d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057754"
---
# <a name="set-up-and-configure-the-moodle-plugin"></a>Configuración y configuración del complemento Moodle

En este artículo, aprenderá a instalar y configurar el complemento Moodle para incorporar Microsoft Teams con su experiencia de Open LMS.

## <a name="prerequisites"></a>Requisitos previos

Estos son los requisitos previos para instalar el complemento Moodle:

* Credenciales de administrador de Moodle.
* credenciales de administrador de Microsoft Azure Active Directory (Azure AD).
* Una suscripción de Azure en la que puede crear nuevos recursos.

## <a name="1-install-the-microsoft-365-moodle-plugin"></a>1. Instale el complemento Microsoft 365 Moodle

La integración de Open LMS en Microsoft Teams funciona con el [conjunto de complementos código abierto Microsoft 365 Moodle](https://moodle.org/plugins/browse.php?list=set&id=72).

### <a name="requisite-applications-and-plugins"></a>Aplicaciones y complementos necesarios

Instale y descargue los siguientes elementos antes de continuar con la instalación del complemento de Moodle Microsoft 365:

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
3. Tras la detección de nuevos complementos que se instalarán, Moodle debería redirigirle a la página instalar nuevos complementos. Si esto no ocurre, en la página **Administración del sitio** , seleccione **Notificaciones** en la pestaña **General** , ya que esto debería desencadenar la instalación de los complementos.

    > [!IMPORTANT]
    >
    > * Mantenga abierta la página de configuración de los complementos de Moodle Microsoft 365 en una pestaña independiente del explorador, ya que debe volver a este conjunto de páginas a lo largo del proceso.  
    >
    > * Si no tiene un sitio de Moodle existente, vaya al repositorio [de Moodle en Azure](https://github.com/azure/moodle) e implemente rápidamente una instancia de Moodle y personalícela según sus necesidades.

#### <a name="enable-the-openid-connect-authentication-plugin"></a>Habilitación del complemento de autenticación Conectar OpenID

1. Vaya a **Autenticación** **de complementos** >  de **administración** >  del sitio y seleccione **Administrar autenticación**.
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
> Para obtener más información sobre cómo registrar manualmente la instancia de Moodle, consulte Registro de la [instancia de Moodle como aplicación](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration).

### <a name="teams-for-open-lms-setup-process"></a>Teams para el proceso de instalación de Open LMS

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

1. Vuelva a la página de administración de complementos, **OpenID** de **autenticación** > **de complementos** >  de administración  > **del sitio Conectar**.

1. Pegue el `AppID` valor en el cuadro **Id. de** aplicación y el `Key` valor en el cuadro **Clave** y, a continuación, seleccione **Guardar cambios**.

1. Vaya a **Complementos** > **locales** de **administración** >  del sitio y seleccione **Microsoft 365 Integración**.

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

        ✔ Cree cuentas en Open LMS para los usuarios de Azure AD.

        ✔ Actualice todas las cuentas de Open LMS para los usuarios de Azure AD.

    1. En la sección **Restricción de creación** de usuarios, puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizan con Open LMS.
    1. En la sección **Sincronización de cursos**, puede seleccionar la opción **de personalización Sincronización** de cursos para habilitar la creación automática de grupos y Teams para algunos o todos los cursos de Open LMS existentes.

1. Para validar las tareas [cron](https://docs.moodle.org/400/en/Cron) y ejecutarlas manualmente por primera vez, vaya a Tareas **programadas** del **servidor** > **de** >  **administración** >  del sitio.

    1. Desplácese hacia abajo y busque la tarea **Sincronizar usuarios con Azure AD** y seleccione **Ejecutar ahora**.
        1. Este proceso sincronizará el usuario de Azure AD con el sitio de Open LMS.
    1. A continuación, busque los **cursos de Sync Moodle para Microsoft Teams** tarea y seleccione **Ejecutar ahora**.
        1. Esta tarea creará grupos y Teams si se encuentra un propietario.
        1. Si el usuario tiene `local/o365:teamowner` capacidad en el contexto del curso, el usuario es propietario del equipo. Si el usuario tiene `local/o365:teammember` funcionalidad en el contexto del curso, el usuario es miembro del equipo.  
        1. El rol *maestro* predeterminado tiene la `local/o365:teamowner` funcionalidad y el rol *student* predeterminado tiene la `local/o365:teammember` funcionalidad .

    > [!NOTE]
    > Moodle [Cron](https://docs.moodle.org/400/en/Scheduled_tasks) se ejecuta según la programación de tareas. La programación predeterminada es una vez al día a la 1:00 AM en la zona horaria local del servidor. Sin embargo, el cron debe ejecutarse con más frecuencia para mantener todo sincronizado.

1. Vaya a **Complementos** > **locales** >  de **administración** >  del sitio **Microsoft 365 pestaña Integración** >  **Teams Configuración**.

1. Seleccione el botón **Comprobar configuración de Moodle** para actualizar todas las configuraciones necesarias para que la integración Teams funcione.

Una vez instalados y configurados los complementos, puede hacer lo siguiente:

* [Implementación del bot de Moodle Assistant en Azure](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
* [Agregue pestañas de Moodle a las clases de Teams](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
* [Agregue Teams clases y reuniones a Open LMS](open-lms-teams-classes-and-meetings.md).

## <a name="extra-moodle-plugin-documentation"></a>Documentación adicional del complemento Moodle

Si desea revisar las guías de integración Microsoft 365 de Open LMS y las notas de la versión, consulte estos recursos:

* [Microsoft 365 documentación de integración en Moodle Docs](https://docs.moodle.org/400/en/Microsoft_365).
