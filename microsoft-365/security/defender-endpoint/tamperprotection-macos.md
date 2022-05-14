---
title: Protección de macOS configuración de seguridad con protección contra alteraciones
description: Use la protección contra alteraciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad macOS importante.
keywords: macos, protección contra alteraciones, configuración de seguridad, malware
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e99ed2f93156cb92f031528e71d51cebafc3088f
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417017"
---
# <a name="protect-macos-security-settings-with-tamper-protection"></a>Protección de macOS configuración de seguridad con protección contra alteraciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

La protección contra alteraciones en macOS ayuda a evitar que los usuarios no autorizados realicen cambios no deseados en la configuración de seguridad. La protección contra alteraciones ayuda a evitar la eliminación no autorizada de Microsoft Defender para punto de conexión en macOS. Esta funcionalidad también ayuda a que los archivos de seguridad, los procesos y los valores de configuración importantes no se manipulen.

Puede establecer la protección contra alteraciones en los modos siguientes:

|Tema|Descripción|
|---|---|
|Deshabilitado|La protección contra alteraciones está completamente desactivada (este es el modo predeterminado después de la instalación)|
|Auditoría|Las operaciones de manipulación se registran, pero no se bloquean|
|Bloquear|La protección contra alteraciones está activada, las operaciones de manipulación están bloqueadas|

Cuando la protección contra alteraciones se establece en modo de auditoría o bloqueo, puede esperar los siguientes resultados:

**Modo de auditoría**:

- Las acciones para desinstalar el agente de Defender para punto de conexión se registran (auditadas)
- La edición o modificación de archivos de Defender para punto de conexión se registra (auditada)
- Se registra la creación de nuevos archivos en la ubicación de Defender para punto de conexión (auditada)
- La eliminación de archivos de Defender para punto de conexión se registra (auditada)
- Se registra el cambio de nombre de los archivos de Defender para punto de conexión (auditado)
- Error en los comandos para detener el agente

**Modo de bloque**:

- Las acciones para desinstalar el agente de Defender para punto de conexión están bloqueadas
- Se bloquea la edición o modificación de archivos de Defender para punto de conexión
- Se bloquea la creación de nuevos archivos en la ubicación de Defender para punto de conexión
- Se bloquea la eliminación de archivos de Defender para punto de conexión
- Se bloquea el cambio de nombre de los archivos de Defender para punto de conexión
- Error en los comandos para detener el agente

Este es un ejemplo de un mensaje del sistema en respuesta a una acción bloqueada:

![Imagen de la operación bloqueada](images/operation-blocked.png)

Puede configurar el modo de protección contra alteraciones proporcionando el nombre del modo como nivel de cumplimiento.

> [!NOTE]
>
> - El cambio de modo se aplicará inmediatamente. No es necesario cambiar la marca de características ni reiniciar Microsoft Defender para punto de conexión.
> - Si usó JAMF durante la configuración inicial, también tendrá que actualizar la configuración mediante JAMF.

## <a name="before-you-begin"></a>Antes de empezar

- Versiones de macOS compatibles: Monterey (12), Big Sur (11), Catalina (10.15+)
- Versión mínima necesaria para Defender para punto de conexión: 101.49.25

**Configuración muy recomendada:**

1. Protección de integridad del sistema (SIP) habilitada. Para obtener más información, consulte [Deshabilitación y habilitación de la protección de integridad del sistema](https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection).
1. Use una herramienta de administración de dispositivos móviles (MDM) para configurar Microsoft Defender para punto de conexión.

## <a name="configure-tamper-protection-on-macos-devices"></a>Configuración de la protección contra alteraciones en dispositivos macOS

Hay varias maneras de configurar la protección contra alteraciones:

- [Configuración manual](#manual-configuration)
- [JAMF](#jamf)
- [Intune](#intune)

### <a name="before-you-begin"></a>Antes de empezar

Compruebe que "tamper_protection" está establecido en "deshabilitado".

![Imagen de la línea de comandos con protección contra alteraciones en modo de deshabilitación](images/verify-tp.png)

### <a name="manual-configuration"></a>Configuración manual

1. Use el siguiente comando:

   ```console
   sudo mdatp config tamper-protection enforcement-level --value block
   ```

   ![Imagen del comando de configuración manual](images/manual-config-cmd.png)

   > [!NOTE]
   > Si usa la configuración manual para habilitar la protección contra alteraciones, también puede deshabilitar la protección contra alteraciones manualmente en cualquier momento. Por ejemplo, puede revocar el acceso completo al disco desde Defender en Preferencias del sistema manualmente. Debe usar MDM en lugar de la configuración manual para evitar que un administrador local haga eso.

2. Compruebe el resultado.

    ![Imagen del resultado del comando de configuración manual](images/result-manual-config.png)

Observe que el "tamper_protection" ahora está establecido en "block".

### <a name="jamf"></a>JAMF

Para configurar el modo de protección contra alteraciones en Microsoft Defender para punto de conexión [perfil de configuración](mac-jamfpro-policies.md), agregue los valores siguientes:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>tamperProtection</key>
    <dict>
      <key>enforcementLevel</key>
      <string>block</string>
    </dict>
  </dict>
</plist>
```

> [!NOTE]
> Si ya tiene un perfil de configuración para Microsoft Defender para punto de conexión, debe *agregarle* la configuración. No es necesario crear un segundo perfil de configuración.

### <a name="intune"></a>Intune

Siga el ejemplo de perfil de Intune documentado para configurar la protección contra alteraciones a través de Intune. Para obtener más información, consulte [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md).

Agregue la siguiente configuración en el perfil de Intune:

> [!NOTE]
> Para Intune configuración, puede crear un nuevo archivo de configuración de perfil para agregar la configuración de protección contra alteraciones, o bien puede agregar estos parámetros al existente.

```xml
?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>tamperProtection</key>
                <dict>
                             <key>enforcementLevel</key>
                             <string>block</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Para comprobar el estado de la protección contra alteraciones, ejecute el siguiente comando:

`mdatp health --field tamper_protection`

El resultado mostrará "bloquear" si la protección contra alteraciones está activada:

![Imagen de la protección contra alteraciones en modo de bloque](images/tp-block-mode.png)

También puede ejecutar full `mdatp health` y buscar el "tamper_protection" en la salida:

![Imagen de la protección contra alteraciones cuando está en modo de bloque](images/health-tp-audit.png)

## <a name="verify-tamper-protection-preventive-capabilities"></a>Comprobación de las funcionalidades preventivas de protección contra alteraciones

Puede comprobar que la protección contra alteraciones está activada de varias maneras.

### <a name="verify-block-mode"></a>Comprobación del modo de bloque

La alerta de alteración se genera en el portal de Microsoft 365 Defender

![Imagen de la alerta de manipulación que se genera en el portal de Microsoft 365 Defender](images/tampering-sensor-portal.png)

### <a name="verify-block-mode-and-audit-modes"></a>Comprobación del modo de bloque y los modos de auditoría

- Con la búsqueda avanzada, verá que aparecen alertas de manipulación
- Los eventos de alteración se pueden encontrar en los registros de dispositivos locales: `sudo grep -F '\[{tamperProtection}\]' /Library/Logs/Microsoft/mdatp/microsoft_defender_core.log`

![Imagen del registro de protección contra alteraciones](images/tamper-protection-log.png)

### <a name="diy-scenarios"></a>Escenarios de bricolaje

- Con la protección contra alteraciones establecida en "bloquear", intente diferentes métodos para desinstalar Defender para punto de conexión. Por ejemplo, arrastre el icono de la aplicación a la papelera o desinstale la protección contra alteraciones mediante la línea de comandos.
- Intente detener el proceso de Defender para punto de conexión (eliminación).
- Intente eliminar, cambiar el nombre, modificar y mover archivos de Defender para punto de conexión (de forma similar a lo que haría un usuario malintencionado), por ejemplo:

  - /Applications/Microsoft Defender ATP.app/
  - /Library/LaunchDaemons/com.microsoft.fresno.plist
  - /Library/LaunchDaemons/com.microsoft.fresno.uninstall.plist
  - /Library/LaunchAgents/com.microsoft.wdav.tray.plist
  - /Library/Managed Preferences/com.microsoft.wdav.ext.plist
  - /Library/Managed Preferences/mdatp_managed.json
  - /Library/Managed Preferences/com.microsoft.wdav.atp.plist
  - /Library/Managed Preferences/com.microsoft.wdav.atp.offboarding.plist
  - /usr/local/bin/mdatp

## <a name="turning-off-tamper-protection"></a>Desactivar la protección contra alteraciones

Puede desactivar la protección contra alteraciones mediante cualquiera de los métodos siguientes.

### <a name="manual-configuration"></a>Configuración manual

Use el siguiente comando:

```console
sudo mdatp config tamper-protection enforcement-level - -value disabled
```

## <a name="jamf"></a>JAMF
Cambie el `enforcementLevel` valor a "disabled" en el perfil de configuración e insérelo en la máquina:

```console
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>tamperProtection</key>
    <dict>
      <key>enforcementLevel</key>
      <string>disabled</string>
    </dict>
  </dict>
</plist>

```

### <a name="intune"></a>Intune
Agregue la siguiente configuración en el perfil de Intune:

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>tamperProtection</key>
                <dict>
                             <key>enforcementLevel</key>
                             <string>disabled</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="troubleshooting-configuration-issues"></a>Solución de problemas de configuración

### <a name="issue-tamper-protection-is-reported-as-disabled"></a>Problema: la protección contra alteraciones se notifica como deshabilitada

Si al ejecutar el comando `mdatp health` se informa de que la protección contra alteraciones está deshabilitada, incluso si la ha habilitado y ha transcurrido más de una hora desde la incorporación, puede comprobar si tiene la configuración correcta mediante la ejecución del siguiente comando:

```console
$ sudo grep -F '\[{tamperProtection}\]: Feature state:' /Library/Logs/Microsoftmdatpmicrosoft_defender_core.log \| tail -n 1

\[85246\]\[2021-12-08 15:45:34.184781 UTC\]\[info\]: \[{tamperProtection}\]: Feature state: enabledmode: "block"
```

El modo debe ser "block" (o "audit"). Si no es así, no ha establecido el modo de protección contra alteraciones mediante `mdatp config` el comando o a través de Intune.
