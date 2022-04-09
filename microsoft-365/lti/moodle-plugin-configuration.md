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
ms.openlocfilehash: efe1ebdb92cbb3367e54e99df89b75c853c48357
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747539"
---
# <a name="set-up-and-configure-the-moodle-plugin"></a>Configuración y configuración del complemento Moodle

En este artículo, aprenderá a instalar y configurar el complemento Moodle LMS para incorporar Microsoft Teams con su experiencia de Moodle.

## <a name="prerequisites"></a>Requisitos previos

Estos son los requisitos previos para instalar Moodle:

* Credenciales de administrador de Moodle.
* Azure AD credenciales de administrador.
* Una suscripción de Azure en la que puede crear nuevos recursos.

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Instalar los complementos de Moodle Microsoft 365

La integración de Moodle en Microsoft Teams se basa en el [conjunto de complementos código abierto Microsoft 365 Moodle](https://github.com/Microsoft/o365-moodle).

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

1. Inicie sesión en el servidor de Moodle y vaya a **Administración del sitio**.
1. Seleccione la pestaña **Complementos** y, a continuación, seleccione **Instalar complementos**.
1. En la sección **Instalar complementos desde un archivo ZIP** , seleccione **Elegir un archivo**.
1. Seleccione **Upload un archivo** en el panel de navegación izquierdo, busque el archivo que descargó y seleccione **Upload este archivo**.
1. Seleccione **Administración del sitio** en el panel de navegación izquierdo para volver al panel de administración.
1. Desplácese hacia abajo hasta **Complementos locales** y seleccione el vínculo **integración de Microsoft 365**.

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

## <a name="2-configure-the-connection-between-the-microsoft-365-plugins-and-azure-ad"></a>2. Configurar la conexión entre los complementos de Microsoft 365 y Azure AD

Debe configurar la conexión entre los complementos de Microsoft 365 y Azure AD.

### <a name="requisites"></a>Requisitos

Registre Moodle como una aplicación en el Azure AD mediante el script de PowerShell. El script aprovisiona los siguientes elementos:

* Una nueva aplicación de Azure AD para el inquilino de Microsoft 365, que usa la Microsoft 365 Complementos de Moodle.
* La aplicación para el inquilino de Microsoft 365 configura las direcciones URL de respuesta y los permisos necesarios para la aplicación aprovisionada y devuelve y `AppID` `Key`.

Use la página de configuración de complementos de Moodle generada `AppID` y `Key` en su Microsoft 365 para configurar el sitio del servidor de Moodle con Azure AD.

> [!IMPORTANT]
>
> * El script de PowerShell no se actualiza con los elementos de configuración más recientes, por lo que debe completar la configuración manualmente siguiendo los pasos descritos en la página de versión de Moodle [3.10.6 y 3.11.3](https://docs.moodle.org/311/en/Microsoft_365) .
>
> * Para obtener más información sobre cómo registrar manualmente la instancia de Moodle, consulte Registro de la [instancia de Moodle como aplicación](https://docs.moodle.org/311/en/Microsoft_365#Register_Application_in_Azure_manually).

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
    1. Escriba el nombre de la aplicación Azure AD, por ejemplo, complementos de Moodle o Moodle.
    1. Escriba la dirección URL del servidor de Moodle.
    1. Copie el **identificador de aplicación (`AppID`)** y **la clave de aplicación (`Key`)** generados por el script y guárdelos.

1. Vuelva a la página de administración de complementos, **Administración** >  del **sitioPluginsAuthenticationOpenID** >  >  **Conectar**.

1. Pegue el `AppID` valor en el cuadro **Id. de** aplicación y el `Key` valor en el cuadro **Clave** y, a continuación, seleccione **Guardar cambios**.

1. Vaya a **Administración** >  del **sitioPluginsLocal plugins (Complementos** >  **locales**) y seleccione **Microsoft 365 Integration (Integración de Microsoft 365**).

1. En **Elegir método de conexión**, seleccione **Acceso a la aplicación** y, a continuación, seleccione **Guardar cambios** de nuevo.

1. Después de actualizar la página, puede ver otra nueva sección **Consentimiento del administrador & información adicional**.
    1. Seleccione **El vínculo Proporcionar consentimiento del administrador**, escriba las credenciales de administrador global de Microsoft 365 y, a continuación, **Acepte** para conceder los permisos.
    1. Junto al campo **inquilino de Azure AD**, seleccione el botón **Detectar**.
    1. Junto a la **dirección URL de OneDrive para la Empresa**, seleccione el botón **Detectar**.
    1. Después de rellenar los campos, vuelva a seleccionar el botón **Guardar cambios** .

1. Seleccione el botón **Actualizar** para comprobar la instalación y, a continuación, seleccione **Guardar cambios**.

1. Sincronice los usuarios entre el servidor de Moodle y Azure AD. En función del entorno, puede seleccionar diferentes opciones durante esta fase. Para empezar:
    1. Cambie a la **pestaña Sincronizar Configuración**.

    1. En la sección **Sincronizar usuarios con Azure AD**, active las casillas que se aplican a su entorno. Debe seleccionar las siguientes opciones:  

        ✔ Cree cuentas en Moodle para los usuarios de Azure AD.
        
        ✔ Actualice todas las cuentas de Moodle para los usuarios de Azure AD.
        

    1. En la sección **Restricción de creación** de usuarios, puede configurar un filtro para limitar el Azure AD usuarios sincronizados con Moodle.
    1. En la sección **Sincronización de cursos**, puede seleccionar la opción **de personalización Sincronización** de cursos para habilitar la creación automática de grupos y Teams para algunos o todos los cursos de Moodle existentes.

1. Para validar las tareas [cron](https://docs.moodle.org/310/en/Cron) y ejecutarlas manualmente por primera vez, vaya a **Administración** >  del **sitioServerTasksNombres** >  **programados** > .

    1. Desplácese hacia abajo y busque la tarea **Sincronizar usuarios con Azure AD** y seleccione **Ejecutar ahora**.
        1. Esto sincronizará el usuario AAD con el sitio de Moodle.
    1. A continuación, busque los **cursos de Sync Moodle para Microsoft Teams** tarea y seleccione **Ejecutar ahora**.
        1. Esta tarea creará grupos y Teams si se encuentra un propietario.
        1. Si el usuario tiene `local/o365:teamowner` capacidad en el contexto del curso, el usuario es propietario del equipo. Si el usuario tiene `local/o365:teammember` funcionalidad en el contexto del curso, el usuario es miembro del equipo.  
        1. El rol *maestro* predeterminado tiene el `local/o365:teamowner" capability`y el rol *student* predeterminado tiene la `local/o365:teammember` funcionalidad .

    > [!NOTE]
    >
    > Moodle [Cron](https://docs.moodle.org/311/en/Scheduled_tasks) se ejecuta según la programación de tareas. La programación predeterminada es una vez al día a la 1:00 AM en la zona horaria local del servidor. Sin embargo, el cron debe ejecutarse con más frecuencia para mantener todo sincronizado.

1. Vuelva a la página de administración del sitio.

1. Configure los valores necesarios para habilitar la integración de la aplicación Teams.

    1. Para habilitar **OpenID Conectar**, vaya a **Administración** >  del **sitioPluginsAdministrar** >  **autenticación**.
        1. Busque **OpenID Conectar** y seleccione el icono de ojo si está atenuado. Guarde los cambios.
    1. Para habilitar la inserción de fotogramas, vaya a **Administración del sitio** y seleccione **Seguridad HTTP** en la sección **Seguridad** .
        1. Active la casilla situada junto a **Permitir incrustación de fotogramas**. Guarde los cambios.
    1. Para habilitar los servicios web, que habilitan las características de la API de Moodle, vaya a **Administración** >  del **sitioActerísticas avanzadas**.
        1. Asegúrese de que la casilla situada junto a **Habilitar servicios web** está seleccionada. Guarde los cambios.
    1. Para habilitar los servicios externos para Microsoft 365, vaya a **Administración** >  del **sitioPlugins** y seleccione **Servicios externos** en la sección **Servicios web**.

        ✔ En la sección **Servicios integrados**, busque **Moodle Microsoft 365 Webservices**.
        
        ✔ Seleccione **Editar** en la fila **Moodle Microsoft 365 Webservices**.
        
        ✔ Seleccione el icono de ojo si está atenuado. Guarde los cambios.
        

    1. Edite los permisos de usuario autenticados para permitirles crear tokens de servicio web.

        ✔ Vaya a **Administración del sitio**, pestaña **Usuarios** y busque **Definir roles** en la sección **Permisos** .
        
        ✔ En la pestaña **Administrar usuarios** , busque Rol **de usuario autenticado** y seleccione el icono de edición.
        
        ✔ Desplácese hacia abajo y busque la funcionalidad **Crear un token de servicio web** y active la casilla **Permitir** . Guarde los cambios.
        

Una vez instalados y configurados los complementos, puede hacer lo siguiente:

* [Agregue pestañas de Moodle a las clases de Teams](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
* [Agregue Teams clases y reuniones a Moodle LMS](teams-classes-meetings-with-moodle.md).

## <a name="extra-moodle-plugin-documentation"></a>Documentación adicional del complemento Moodle

Si desea revisar las guías de integración y las notas de la versión de Moodle Microsoft 365, consulte estos recursos:

* [Moodle y Microsoft 365 3.10.6](https://docs.moodle.org/310/en/Microsoft_365).
* [Moodle y Microsoft 365 3.11.3](https://docs.moodle.org/310/en/Microsoft_365).
