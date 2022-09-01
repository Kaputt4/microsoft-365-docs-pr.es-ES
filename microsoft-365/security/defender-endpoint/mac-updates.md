---
title: Implementación de actualizaciones para Microsoft Defender para punto de conexión en Mac
description: Controle las actualizaciones de Microsoft Defender para punto de conexión en Mac en entornos empresariales.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, actualizaciones, implementar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 3686ee0e4356091a0dd3d6b295fde72d8f2611e0
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519520"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación de actualizaciones para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.

Para actualizar Microsoft Defender para punto de conexión en macOS, se usa un programa denominado Microsoft AutoUpdate (MAU). De forma predeterminada, MAU comprueba automáticamente las actualizaciones diarias, pero puede cambiarlas a semanales, mensuales o manualmente.

:::image type="content" source="images/MDATP-34-MAU.png" alt-text="Mau" lightbox="images/MDATP-34-MAU.png":::

Si decide implementar actualizaciones mediante las herramientas de distribución de software, debe configurar MAU para comprobar manualmente si hay actualizaciones de software. Puede implementar preferencias para configurar cómo y cuándo MAU comprueba si hay actualizaciones para los Equipos Mac de su organización.

## <a name="use-msupdate"></a>Usar msupdate

MAU incluye una herramienta de línea de *comandos, denominada msupdate*, diseñada para los administradores de TI para que tengan un control más preciso sobre cuándo se aplican las actualizaciones. Las instrucciones para usar esta herramienta se pueden encontrar en [Update Office para Mac mediante msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).

En MAU, el identificador de aplicación para Microsoft Defender para punto de conexión en macOS es *WDAV00*. Para descargar e instalar las actualizaciones más recientes de Microsoft Defender para punto de conexión en macOS, ejecute el siguiente comando desde una ventana terminal:

```dos
cd /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app/Contents/MacOS
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Establecer preferencias para Microsoft AutoUpdate

En esta sección se describen las preferencias más comunes que se pueden usar para configurar MAU. Esta configuración se puede implementar como un perfil de configuración a través de la consola de administración que usa la empresa. En las secciones siguientes se muestra un ejemplo de un perfil de configuración.

### <a name="set-the-channel-name"></a>Establecer el nombre del canal

El canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen a través de MAU. Los dispositivos de `Beta` pueden probar nuevas características antes de que los dispositivos en `Preview` y `Current`.

El `Current` canal contiene la versión más estable del producto.

> [!IMPORTANT]
> Antes de la versión 4.29 de Microsoft AutoUpdate, los canales tenían nombres diferentes:
>
> - `Beta` se llamó `InsiderFast` (Insider Fast)
> - `Preview` se llamó `External` (Insider Slow)
> - `Current` se ha nombrado `Production`

> [!TIP]
> Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa en `Beta` o `Preview`.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|ChannelName|
|**Tipo de datos**|Cadena|
|**Posibles valores**|Beta <p> Preview <p> Current|
|||

> [!WARNING]
> Esta configuración cambia el canal de todas las aplicaciones que se actualizan a través de Microsoft AutoUpdate. Para cambiar el canal solo para Microsoft Defender para punto de conexión en macOS, ejecute el siguiente comando después de reemplazar por `[channel-name]` el canal deseado:
>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Establecer la frecuencia de comprobación de actualización

Cambie la frecuencia con la que MAU busca actualizaciones.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|UpdateCheckFrequency|
|**Tipo de datos**|Entero|
|**Valor predeterminado**|720 (minutos)|
|**Comment**|Este valor se establece en minutos.|
|||

### <a name="change-how-mau-interacts-with-updates"></a>Cambiar la interacción de MAU con las actualizaciones

Cambie la forma en que MAU busca actualizaciones.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|HowToCheck|
|**Tipo de datos**|Cadena|
|**Posibles valores**|Manual <p> AutomaticCheck <p> AutomaticDownload|
|**Comment**|Tenga en cuenta que AutomaticDownload realizará una descarga e instalación silenciosa si es posible.|
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Cambiar si el botón "Buscar Novedades" está habilitado

Cambie si los usuarios locales podrán hacer clic en la opción "Buscar Novedades" en la interfaz de usuario de Microsoft AutoUpdate.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|EnableCheckForUpdatesButton|
|**Tipo de datos**|Booleano|
|**Posibles valores**|True (valor predeterminado) <p> Falso|
|||

### <a name="disable-insider-checkbox"></a>Casilla Deshabilitar Insider

Establézcalo en true para que "Únase al programa Office Insider..." casilla no disponible o atenuada para los usuarios.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|DisableInsiderCheckbox|
|**Tipo de datos**|Booleano|
|**Posibles valores**|False (valor predeterminado) <p> Verdadero|
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Limitar la telemetría que se envía desde MAU

Establézcalo en false para enviar datos de latido mínimos, sin uso de la aplicación y sin detalles del entorno.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.autoupdate2`|
|**Clave**|SendAllTelemetryEnabled|
|**Tipo de datos**|Booleano|
|**Posibles valores**|True (valor predeterminado) <p> Falso|
|||

## <a name="example-configuration-profile"></a>Perfil de configuración de ejemplo

El siguiente perfil de configuración se usa para:

- Colocación del dispositivo en el canal de producción
- Descargar e instalar actualizaciones automáticamente
- Habilitar el botón "Buscar actualizaciones" en la interfaz de usuario
- Permitir que los usuarios del dispositivo se inscriban en los canales insider

> [!WARNING]
> La configuración siguiente es una configuración de ejemplo y no debe usarse en producción sin una revisión adecuada de la configuración y la adaptación de las configuraciones.

> [!TIP]
> Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa en `Beta` o `Preview`.

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
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
            <string>Production</string>
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

Para configurar MAU, puede implementar este perfil de configuración desde la herramienta de administración que usa la empresa:

- En JAMF, cargue este perfil de configuración y establezca el dominio de preferencia en *com.microsoft.autoupdate2*.
- En Intune, cargue este perfil de configuración y establezca el nombre del perfil de configuración personalizado en *com.microsoft.autoupdate2*.

## <a name="resources"></a>Recursos

- [Referencia de msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate)
