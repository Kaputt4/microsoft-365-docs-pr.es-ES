---
title: Implementar actualizaciones para ATP de Microsoft Defender para Mac
description: Controle las actualizaciones de ATP de Microsoft Defender para Mac en entornos empresariales.
keywords: microsoft, defender, atp, mac, actualizaciones, implementar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074344"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a>Implementar actualizaciones para Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para endpoint para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.

Para actualizar Microsoft Defender para Endpoint para Mac, se usa un programa denominado Microsoft AutoUpdate (MAU). De forma predeterminada, MAU comprueba automáticamente las actualizaciones diariamente, pero puede cambiarla a semanal, mensual o manual.

![Captura de pantalla mau](images/MDATP-34-MAU.png)

Si decide implementar actualizaciones mediante las herramientas de distribución de software, debe configurar MAU para comprobar manualmente si hay actualizaciones de software. Puede implementar preferencias para configurar cómo y cuándo MAU busca actualizaciones para los Mac de su organización.

## <a name="use-msupdate"></a>Usar msupdate

MAU incluye una herramienta de línea de comandos, denominada *msupdate*, que está diseñada para los administradores de TI para que tengan un control más preciso sobre cuándo se aplican las actualizaciones. Las instrucciones para usar esta herramienta se pueden encontrar en [Update Office para Mac mediante msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).

En MAU, el identificador de aplicación de Microsoft Defender para Endpoint para Mac es *WDAV00*. Para descargar e instalar las actualizaciones más recientes de Microsoft Defender para Endpoint para Mac, ejecute el siguiente comando desde una ventana de Terminal:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Establecer preferencias para Microsoft AutoUpdate

En esta sección se describen las preferencias más comunes que se pueden usar para configurar MAU. Esta configuración se puede implementar como un perfil de configuración a través de la consola de administración que usa su empresa. En las secciones siguientes se muestra un ejemplo de un perfil de configuración.

### <a name="set-the-channel-name"></a>Establecer el nombre del canal

El canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen a través de MAU. Los `Beta` dispositivos pueden probar nuevas características antes de que los dispositivos `Preview` en `Current` y . 

El `Current` canal contiene la versión más estable del producto.

>[!IMPORTANT]
> Antes de Microsoft AutoUpdate versión 4.29, los canales tenían nombres diferentes: 
> 
> - `Beta` se `InsiderFast` denominaba (Insider Fast)
> - `Preview` se `External` denominaba (Insider Slow)
> - `Current` se nombraba `Production`

>[!TIP]
>Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa en `Beta` o `Preview` .

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | ChannelName |
| **Tipo de datos** | Cadena |
| **Posibles valores** | Beta <br/> Preview <br/> Current |
|||

>[!WARNING]
>Esta configuración cambia el canal de todas las aplicaciones que se actualizan a través de Microsoft AutoUpdate. Para cambiar el canal solo para Microsoft Defender para Endpoint para Mac, ejecute el siguiente comando después de reemplazar `[channel-name]` por el canal deseado:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Establecer frecuencia de comprobación de actualización

Cambiar la frecuencia con la que MAU busca actualizaciones.

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | UpdateCheckFrequency |
| **Tipo de datos** | Entero |
| **Valor predeterminado** | 720 (minutos) |
| **Comment** | Este valor se establece en minutos. |
|||

### <a name="change-how-mau-interacts-with-updates"></a>Cambiar la forma en que MAU interactúa con las actualizaciones

Cambiar la forma en que MAU busca actualizaciones.

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | HowToCheck |
| **Tipo de datos** | Cadena |
| **Posibles valores** | Manual <br/> AutomaticCheck <br/> AutomaticDownload |
| **Comment** |  Ten en cuenta que AutomaticDownload realizará una descarga e instalará silenciosamente si es posible. |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Cambiar si el botón "Buscar actualizaciones" está habilitado

Cambie si los usuarios locales podrán hacer clic en la opción "Buscar actualizaciones" en la interfaz de usuario de Microsoft AutoUpdate.

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | EnableCheckForUpdatesButton |
| **Tipo de datos** | Booleano |
| **Posibles valores** | True (predeterminado) <br/> False |
|||

### <a name="disable-insider-checkbox"></a>Casilla Deshabilitar Insider

Se establece en true para que el "Join the Office Insider Program..." casilla no disponible / grised hacia fuera para los usuarios.

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | DisableInsiderCheckbox |
| **Tipo de datos** | Booleano |
| **Posibles valores** | False (predeterminado) <br/> Verdadero |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Limitar la telemetría que se envía desde MAU

Se establece en false para enviar datos de latido mínimos, sin uso de aplicaciones y sin detalles del entorno.

|||
|:--|:--|
| **Dominio** | com.microsoft.autoupdate2 |
| **Clave** | SendAllTelemetryEnabled |
| **Tipo de datos** | Booleano |
| **Posibles valores** | True (predeterminado) <br/> False |
|||

## <a name="example-configuration-profile"></a>Perfil de configuración de ejemplo

El siguiente perfil de configuración se usa para:
- Colocar el dispositivo en el canal beta
- Descargar e instalar actualizaciones automáticamente
- Habilitar el botón "Buscar actualizaciones" en la interfaz de usuario
- Permitir que los usuarios del dispositivo se inscriban en los canales de Insider

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Para configurar MAU, puede implementar este perfil de configuración desde la herramienta de administración que usa su empresa:
- Desde JAMF, cargue este perfil de configuración y establezca el dominio de preferencia en *com.microsoft.autoupdate2*.
- Desde Intune, cargue este perfil de configuración y establezca el nombre del perfil de configuración personalizado en *com.microsoft.autoupdate2*.

## <a name="resources"></a>Recursos

- [referencia de msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
