---
title: Iniciar el portal mediante el programador de inicio del portal
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
description: En este artículo se describe cómo puede iniciar el portal mediante el programador de inicio del portal
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123588"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar el portal mediante el programador de inicio del portal

Un portal es un sitio de SharePoint en la intranet que tiene un gran número de visores de sitio que emplean el contenido en el sitio. El inicio del portal en ondas es una parte importante de la garantía de que los usuarios tienen una experiencia sin problemas y de forma eficaz para obtener acceso a un nuevo portal de SharePoint Online. 

El lanzamiento en ondas es una forma clave de implementar el portal, como se detalla en [planear el plan de implementación de lanzamiento de portal en SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). El programador de inicio del portal está diseñado para ayudarle a seguir un enfoque de lanzamiento en fases o oleada administrando las redirecciones para el nuevo portal. Durante cada una de las ondas, puede recopilar los comentarios de los usuarios y supervisar el rendimiento durante cada una de las ondas de implementación. Esto tiene la ventaja de presentar lentamente el portal, lo que le ofrece la posibilidad de pausar y resolver problemas antes de continuar con la siguiente ola y, en última instancia, garantizar una experiencia positiva para los usuarios. 

Hay dos tipos de redirección: 
- bidireccional: iniciar un nuevo portal moderno de SharePoint Online para reemplazar un portal clásico o moderno de SharePoint existente 
- redirección de página temporal: iniciar un nuevo portal moderno de SharePoint Online sin SharePoint Portal existente

El programador de inicio del portal solo está disponible para iniciar portales modernos de SharePoint Online, como sitios de comunicación y sitios de grupo modernos. Los lanzamientos deben programarse al menos 7 días antes. El número de ondas necesario se determina según el número de usuarios previsto. Antes de programar un inicio del portal, debe ejecutarse la [herramienta diagnósticos de página para SharePoint](https://aka.ms/perftool) para comprobar que la Página principal del portal está en buen estado. Al final del inicio del portal, todos los usuarios con permisos para el sitio podrán tener acceso al nuevo sitio. 

Para obtener más información acerca de cómo iniciar correctamente un portal, siga los principios básicos, prácticas y recomendaciones detalladas para [crear, iniciar y mantener un portal saludable](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Esta característica no está disponible para los planes de Office 365 Germany, Office 365 operado por 21Vianet (China) o Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuración de aplicaciones y conexión a SharePoint Online
1. [Descargue el Shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a Agregar o quitar programas y desinstale "Shell de administración de SharePoint Online".<br>En la página Centro de descarga, seleccione su idioma y haga clic en el botón Descargar. Se le pedirá que elija entre descargar un archivo .msi x64 y x86. Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits. Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system) Después de descargar el archivo, ejecútelo y siga los pasos del Asistente de configuración.

2. Conéctese a SharePoint como un [administrador global o como un administrador de SharePoint](/sharepoint/sharepoint-admin-role) en Microsoft 365. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Ver las configuraciones de inicio del portal existentes

Para ver si hay configuraciones de inicio del portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Programar un inicio del portal en el sitio

El número de ondas necesarias depende del tamaño de inicio previsto. 
- Menos de 10.000 usuarios: 1 ola
- de 10 k a 30K: 3 ondas 
- 30K + a 100 a 100 usuarios: 5 ondas
- Más de 100 k usuarios: 5 ondas y póngase en contacto con el equipo de la cuenta de Microsoft

### <a name="steps-for-bi-directional-redirection"></a>Pasos para la redirección bidireccional

La redirección bidireccional consiste en iniciar un nuevo portal moderno de SharePoint Online para reemplazar un portal clásico o moderno de SharePoint existente. Los usuarios de ondas activas se redirigirán al nuevo sitio independientemente de si navegan hasta el sitio antiguo o el nuevo. Los usuarios de una onda no iniciada que intenten obtener acceso al nuevo sitio se redirigirán de vuelta al sitio antiguo hasta que se inicie la onda. Si tiene administradores o propietarios que necesitan tener acceso a los sitios antiguos y nuevos sin redirigirse, asegúrese de que aparecen en la lista mediante el `WaveOverrideUsers` parámetro. 

Para migrar los usuarios de un sitio de SharePoint existente a un nuevo sitio de SharePoint de forma escalonada:

1. Ejecute el siguiente comando para designar las ondas de lanzamiento del portal.
   
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

2. Validación completa. El redireccionamiento puede tardar 5-10 minutos en completarse para completar su configuración en el servicio. 

### <a name="steps-for-redirection-to-temporary-page"></a>Pasos para redirigir a la página temporal

La redirección de página temporal debe usarse cuando no exista portal de SharePoint existente. Los usuarios se dirigen a un nuevo portal moderno de SharePoint Online de forma escalonada. Si un usuario está en una onda que no se ha iniciado, se le redirigirá a una página temporal (cualquier dirección URL). 

1. Ejecute el siguiente comando para designar las ondas de lanzamiento del portal.
   
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

2. Validación completa. El redireccionamiento puede tardar 5-10 minutos en completarse para completar su configuración en el servicio. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar o reiniciar el inicio de un portal en el sitio

1. Para pausar un inicio del portal en curso y evitar temporalmente los próximos progresos de onda, ejecute el siguiente comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Compruebe que todos los usuarios se redirigen al sitio anterior. 

3. Para reiniciar un inicio del portal que se ha pausado, ejecute el siguiente comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valida que la redirección ya se haya restaurado. 

## <a name="delete-a-portal-launch-on-the-site"></a>Eliminar un inicio del portal en el sitio
1. Cree una onda de lanzamiento de portal.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Ejecute el siguiente comando para eliminar un inicio del portal programado o en curso para un sitio.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Validar que no se produzca ninguna redirección para todos los usuarios.

## <a name="learn-more"></a>Más información
[Planeación del lanzamiento del portal del plan de implementación en SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
