---
title: Protección de la configuración de seguridad de macOS con protección contra alteraciones
description: Use la protección contra alteraciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad importante de macOS.
keywords: macos, protección contra alteraciones, configuración de seguridad, malware
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d27272464938b4dc3a5a53bc447fcb227614f345
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689394"
---
# <a name="protect-macos-security-settings-with-tamper-protection"></a>Protección de la configuración de seguridad de macOS con protección contra alteraciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]


La protección contra alteraciones en macOS ayuda a evitar que los usuarios no autorizados realicen cambios no deseados en la configuración de seguridad. La protección contra alteraciones ayuda a evitar la eliminación no autorizada de Microsoft Defender para punto de conexión en macOS. Esta funcionalidad también ayuda a que los archivos de seguridad, los procesos y los valores de configuración importantes no se manipulen.

Puede establecer la protección contra alteraciones en los modos siguientes:

|Tema|Descripción|
|---|---|
|Deshabilitada|La protección contra alteraciones está completamente desactivada (este es el modo predeterminado después de la instalación)|
|Auditoría|Las operaciones de manipulación se registran, pero no se bloquean|
|Bloquear|La protección contra alteraciones está activada, las operaciones de manipulación están bloqueadas|

Cuando la protección contra alteraciones se establece en modo de auditoría o bloqueo, puede esperar los siguientes resultados:

**Modo de auditoría**:

- Las acciones para desinstalar el agente de Defender para punto de conexión se registran (auditadas)
- La edición o modificación de archivos de Defender para punto de conexión se registra (auditada)
- Se registra la creación de nuevos archivos en la ubicación de Defender para punto de conexión (auditada)
- La eliminación de archivos de Defender para punto de conexión se registra (auditada)
- Se registra el cambio de nombre de los archivos de Defender para punto de conexión (auditado)

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
> - El cambio de modo se aplicará inmediatamente.
> - Si usó JAMF durante la configuración inicial, también tendrá que actualizar la configuración mediante JAMF.

## <a name="before-you-begin"></a>Antes de empezar

- Versiones de macOS compatibles: Monterey (12), Big Sur (11), Catalina (10.15+).
- Versión mínima necesaria para Defender para punto de conexión: 101.70.19.
- Debe estar en un canal de actualización que no sea de producción ([versión preliminar o beta](/deployoffice/office-insider/deploy/microsoft-autoupdate)), mientras que la característica Protección contra alteraciones está en versión preliminar. Si está en el canal de producción, se omitirá el modo de protección contra alteraciones configurado.

**Configuración muy recomendada:**

- Protección de integridad del sistema (SIP) habilitada. Para obtener más información, consulte [Deshabilitación y habilitación de la protección de integridad del sistema](https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection).
- Use una herramienta de administración de dispositivos móviles (MDM) para configurar Microsoft Defender para punto de conexión.

## <a name="configure-tamper-protection-on-macos-devices"></a>Configuración de la protección contra alteraciones en dispositivos macOS

Hay varias maneras de configurar la protección contra alteraciones:

- [Configuración manual](#manual-configuration)
- [JAMF](#jamf)
- [Intune](#intune)

### <a name="before-you-begin"></a>Antes de empezar

Compruebe que "tamper_protection" está establecido en "disabled" o "audit" para observar el cambio de estado.
Además, asegúrese de que "release_ring" no notifica "Producción".

```bash
mdatp health
```

```console
healthy                                     : true
health_issues                               : []
licensed                                    : true
engine_version                              : "1.1.19300.3"
app_version                                 : "101.70.19"
org_id                                      : "..."
log_level                                   : "info"
machine_guid                                : "..."
release_ring                                : "InsiderFast"
product_expiration                          : Dec 29, 2022 at 09:48:37 PM
cloud_enabled                               : true
cloud_automatic_sample_submission_consent   : "safe"
cloud_diagnostic_enabled                    : false
passive_mode_enabled                        : false
real_time_protection_enabled                : true
real_time_protection_available              : true
real_time_protection_subsystem              : "endpoint_security_extension"
network_events_subsystem                    : "network_filter_extension"
device_control_enforcement_level            : "audit"
tamper_protection                           : "audit"
automatic_definition_update_enabled         : true
definitions_updated                         : Jul 06, 2022 at 01:57:03 PM
definitions_updated_minutes_ago             : 5
definitions_version                         : "1.369.896.0"
definitions_status                          : "up_to_date"
edr_early_preview_enabled                   : "disabled"
edr_device_tags                             : []
edr_group_ids                               : ""
edr_configuration_version                   : "20.199999.main.2022.07.05.02-ac10b0623fd381e28133debe14b39bb2dc5b61af"
edr_machine_id                              : "..."
conflicting_applications                    : []
network_protection_status                   : "stopped"
data_loss_prevention_status                 : "disabled"
full_disk_access_enabled                    : true
```

### <a name="manual-configuration"></a>Configuración manual

1. Use el siguiente comando:

   ```console
   sudo mdatp config tamper-protection enforcement-level --value block
   ```

   ![Imagen del comando de configuración manual](images/manual-config-cmd.png)

   > [!NOTE]
   > Si usa la configuración manual para habilitar la protección contra alteraciones, también puede deshabilitar la protección contra alteraciones manualmente en cualquier momento. Por ejemplo, puede revocar el acceso completo al disco desde Defender en Preferencias del sistema manualmente. Debe usar MDM en lugar de la configuración manual para evitar que un administrador local haga eso.

2. Compruebe el resultado.

  ```bash
  mdatp health
  ```

  ```console
  healthy                                     : true
  health_issues                               : []
  licensed                                    : true
  engine_version                              : "1.1.19300.3"
  app_version                                 : "101.70.19"
  org_id                                      : "..."
  log_level                                   : "info"
  machine_guid                                : "..."
  release_ring                                : "InsiderFast"
  product_expiration                          : Dec 29, 2022 at 09:48:37 PM
  cloud_enabled                               : true
  cloud_automatic_sample_submission_consent   : "safe"
  cloud_diagnostic_enabled                    : false
  passive_mode_enabled                        : false
  real_time_protection_enabled                : true
  real_time_protection_available              : true
  real_time_protection_subsystem              : "endpoint_security_extension"
  network_events_subsystem                    : "network_filter_extension"
  device_control_enforcement_level            : "audit"
  tamper_protection                           : "block"
  automatic_definition_update_enabled         : true
  definitions_updated                         : Jul 06, 2022 at 01:57:03 PM
  definitions_updated_minutes_ago             : 5
  definitions_version                         : "1.369.896.0"
  definitions_status                          : "up_to_date"
  edr_early_preview_enabled                   : "disabled"
  edr_device_tags                             : []
  edr_group_ids                               : ""
  edr_configuration_version                   : "20.199999.main.2022.07.05.02-ac10b0623fd381e28133debe14b39bb2dc5b61af"
  edr_machine_id                              : "..."
  conflicting_applications                    : []
  network_protection_status                   : "stopped"
  data_loss_prevention_status                 : "disabled"
  full_disk_access_enabled                    : true
  ```

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

También puede ejecutar full `mdatp health` y buscar el "tamper_protection" en la salida.

## <a name="verify-tamper-protection-preventive-capabilities"></a>Comprobación de las funcionalidades preventivas de protección contra alteraciones

Puede comprobar que la protección contra alteraciones está activada de varias maneras.

### <a name="verify-block-mode"></a>Comprobación del modo de bloque

La alerta de alteración se genera en el portal de Microsoft 365 Defender

![Imagen de la alerta de manipulación que se genera en el portal de Microsoft 365 Defender](images/tampering-sensor-portal.png)

### <a name="verify-block-mode-and-audit-modes"></a>Comprobación del modo de bloque y los modos de auditoría

- Con la búsqueda avanzada, verá que aparecen alertas de manipulación
- Los eventos de alteración se pueden encontrar en los registros de dispositivos locales: `sudo grep -F '[{tamperProtection}]' /Library/Logs/Microsoft/mdatp/microsoft_defender_core.log`

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
$ sudo grep -F '\[{tamperProtection}\]: Feature state:' /Library/Logs/Microsoft/mdatp/microsoft_defender_core.log | tail -n 1


```

El modo debe ser "block" (o "audit"). Si no es así, no ha establecido el modo de protección contra alteraciones mediante `mdatp config` el comando o a través de Intune.
