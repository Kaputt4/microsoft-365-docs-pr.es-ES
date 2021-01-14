---
title: Iniciar el portal mediante el Programador de inicio del portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: En este artículo se describe cómo iniciar el portal mediante el Programador de inicio del portal
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864881"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar el portal mediante el Programador de inicio del portal

Un portal es un sitio de SharePoint en la intranet que tiene un gran número de visores de sitio que emplean el contenido en el sitio. El inicio del portal en oleadas es una parte importante de garantizar que los usuarios tengan una experiencia fluida y de rendimiento al obtener acceso a un nuevo portal de SharePoint Online. 

Iniciar en oleadas es una forma clave de lanzar el portal, como se detalla en la planeación del plan de lanzamiento de lanzamiento del [portal en SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) El Programador de inicio del portal está diseñado para ayudarle a seguir un enfoque de implementación por fases o oleadas mediante la administración de redireccionamientos para el nuevo portal. Durante cada una de las oleadas, puedes recopilar comentarios de los usuarios y supervisar el rendimiento durante cada oleada de implementación. Esto tiene la ventaja de introducir lentamente el portal, darle la opción de pausar y resolver problemas antes de continuar con la siguiente oleada y, en última instancia, garantizar una experiencia positiva para los usuarios. 

Hay dos tipos de redirección: 
- bidireccional: inicie un nuevo portal de SharePoint Online moderno para reemplazar un portal moderno o clásico de SharePoint existente 
- redirección de página temporal: inicie un nuevo portal de SharePoint Online moderno sin ningún portal de SharePoint existente

El programador de inicio del portal solo está disponible para iniciar portales modernos de SharePoint Online (es decir, sitios de comunicación). Los inicios deben programarse con al menos 7 días de antelación. El número de oleadas requerido está determinado por el número esperado de usuarios. Antes de programar el inicio de un portal, debe ejecutarse la herramienta Diagnóstico de páginas para [SharePoint](https://aka.ms/perftool) para comprobar que la página principal del portal está en buen estado. Al final del inicio del portal, todos los usuarios con permisos para el sitio podrán acceder al nuevo sitio. 

Para obtener más información sobre cómo iniciar un portal correcto, siga los principios, prácticas y recomendaciones básicos detallados en Crear, iniciar y mantener [un portal en buen estado.](https://docs.microsoft.com/sharepoint/portal-health) 

> [!NOTE]
> Esta característica no está disponible para los planes de Office 365 Germany, Office 365 operado por 21Vianet (China) o Microsoft 365 Us Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuración de la aplicación y conexión a SharePoint Online
1. [Descargue el Shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a Agregar o quitar programas y desinstale "Shell de administración de SharePoint Online".<br>En la página Centro de descarga, seleccione su idioma y haga clic en el botón Descargar. Se le pedirá que elija entre descargar un archivo .msi x64 y x86. Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits. Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system) Después de descargar el archivo, ejecútelo y siga los pasos del Asistente de configuración.

2. Conéctese a SharePoint como un [administrador global o como un administrador de SharePoint](/sharepoint/sharepoint-admin-role) en Microsoft 365. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Ver las configuraciones de inicio del portal existentes

Para ver si hay configuraciones de inicio de portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Programar el inicio de un portal en el sitio

El número de oleadas necesarias depende del tamaño de inicio esperado. 
- Menos de 10.000 usuarios: 1 oleada
- De 10.000 a 30.000 usuarios: 3 oleadas 
- De 30.000 a 100.000 usuarios: 5 oleadas
- Más de 100.000 usuarios: 5 oleadas y póngase en contacto con su equipo de cuentas de Microsoft

### <a name="steps-for-bidirectional-redirection"></a>Pasos para el redireccionamiento bidireccional

La redirección bidireccional implica el inicio de un nuevo portal de SharePoint Online moderno para reemplazar un portal moderno o clásico de SharePoint existente. Los usuarios de las oleadas activas serán redirigidos al nuevo sitio independientemente de si navegan al sitio antiguo o nuevo. Los usuarios de una oleada no iniciada que intenten obtener acceso al nuevo sitio serán redirigidos de nuevo al sitio antiguo hasta que se inicia su oleada. 

Solo se admite el redireccionamiento entre la página principal predeterminada del sitio antiguo y la página principal predeterminada en el nuevo sitio. Si tiene administradores o propietarios que necesitan tener acceso a los sitios antiguos y nuevos sin ser redirigidos, asegúrese de que aparecen con el `WaveOverrideUsers` parámetro.

Para migrar usuarios de un sitio de SharePoint existente a un nuevo sitio de SharePoint de forma por fases:

1. Ejecute el siguiente comando para designar las oleadas de inicio del portal.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Ejemplo:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validación completa. El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio. 

### <a name="steps-for-redirection-to-temporary-page"></a>Pasos para la redirección a la página temporal

El redireccionamiento temporal de páginas debe usarse cuando no exista ningún portal de SharePoint existente. Los usuarios se dirigen a un nuevo portal de SharePoint Online moderno de forma por fases. Si un usuario está en una oleada que no se ha iniciado, se le redirigirá a una página temporal (cualquier dirección URL). 

1. Ejecute el siguiente comando para designar las oleadas de inicio del portal.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Ejemplo:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validación completa. El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar o reiniciar el inicio de un portal en el sitio

1. Para pausar el inicio de un portal en curso y evitar temporalmente que se produzcan las próximas progresión de oleadas, ejecute el siguiente comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Valide que todos los usuarios sean redirigidos al sitio antiguo. 

3. Para reiniciar un inicio de portal que se ha pausado, ejecute el siguiente comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valide que el redireccionamiento ya está restaurado. 

## <a name="delete-a-portal-launch-on-the-site"></a>Eliminar un inicio de portal en el sitio

1. Ejecute el siguiente comando para eliminar un inicio del portal programado o en curso para un sitio.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valide que no se produce ningún redireccionamiento para todos los usuarios.

## <a name="learn-more"></a>Más información
[Planeación del plan de implementación del lanzamiento del portal en SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
