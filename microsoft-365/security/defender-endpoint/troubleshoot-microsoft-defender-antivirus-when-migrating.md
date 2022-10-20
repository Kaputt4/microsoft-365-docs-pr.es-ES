---
title: Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros
description: Solución de errores comunes al migrar a Microsoft Defender Antivirus
keywords: evento, código de error, registro, solución de problemas, antivirus de Microsoft Defender, antivirus de Windows Defender, migración, antivirus de Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: martyav
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier1
search.appverid: met150
ms.openlocfilehash: 3b8f1779eb78df07e5379a4aa56aeb3acd19abc6
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637362"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Antivirus de Microsoft Defender](https://www.microsoft.com/windows/comprehensive-security)

**Plataformas**
- Windows

Puede encontrar ayuda aquí si encuentra problemas al migrar desde una solución de seguridad de terceros a Microsoft Defender Antivirus.

## <a name="review-event-logs"></a>Revisión de registros de eventos

1. Abra la aplicación Visor de eventos seleccionando el icono **Buscar** en la barra de tareas y buscando *visor de eventos*.

    Puede encontrar información sobre Microsoft Defender Antivirus en **Registros de aplicaciones y servicios** \> de **Microsoft** \> **Windows** \> **Windows डिफेन्डर**.

1. Desde allí, seleccione **Abrir** debajo **de Operativo**.

    Al seleccionar un evento en el panel de detalles, se mostrará más información sobre un evento en el panel inferior, en las pestañas **General** y **Detalles** .

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus no se iniciará

Este problema se puede manifestar en forma de varios identificadores de evento diferentes, todos los cuales tienen la misma causa subyacente.

### <a name="associated-event-ids"></a>Identificadores de eventos asociados

Id. de evento|Nombre de registro|Descripción|Origen
---|---|---|---
15 |Application|Se ha actualizado Windows डिफेन्डर estado correctamente para SECURITY_PRODUCT_STATE_OFF.|Security Center
5007|Microsoft-Windows-Windows डिफेन्डर/Operational|Microsoft Defender ha cambiado la configuración del antivirus. Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware. <p> **Valor anterior:** Default\IsServiceRunning = 0x0 <p> **Nuevo valor:** HKLM\SOFTWARE\Microsoft\Windows डिफेन्डर\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows डिफेन्डर/Operational|Microsoft Defender El antivirus está deshabilitado para detectar spyware y otro software potencialmente no deseado.|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Cómo saber si Microsoft Defender Antivirus no se iniciará porque está instalado un antivirus de terceros

En un dispositivo Windows 10 o Windows 11, si no usa Microsoft Defender para punto de conexión y tiene instalado un antivirus de terceros, Microsoft Defender Antivirus se desactivará automáticamente. Si usa Microsoft Defender para punto de conexión con un antivirus de terceros instalado, Microsoft Defender Antivirus se iniciará en modo pasivo, con una funcionalidad reducida.

> [!TIP]
> El escenario que se acaba de describir solo se aplica a Windows 10 y Windows 11. Otras versiones de Windows tienen [respuestas diferentes](microsoft-defender-antivirus-compatibility.md) a Microsoft Defender Antivirus que se ejecuta junto con software de seguridad de terceros.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Uso de la aplicación Servicios para comprobar si Microsoft Defender Antivirus está desactivado

Para abrir la aplicación Servicios, seleccione el icono **Buscar** de la barra de tareas y busque *servicios*. También puede abrir la aplicación desde la línea de comandos escribiendo *services.msc*.

La información sobre Microsoft Defender Antivirus se mostrará en la aplicación Servicios en **Windows डिफेन्डर** \> **Operativo**. El nombre del servicio antivirus es *Microsoft Defender Antivirus Service*.

Al comprobar la aplicación, es posible que vea que *Microsoft Defender servicio antivirus* está establecido en manual, pero cuando intenta iniciar este servicio manualmente, recibe una advertencia que indica que *el servicio antivirus de Microsoft Defender en el equipo local se inició y, a continuación, se detuvo. Algunos servicios se detienen automáticamente si no están en uso por otros servicios o programas.*

Esto indica que Microsoft Defender Antivirus se ha desactivado automáticamente para conservar la compatibilidad con un antivirus de terceros.

#### <a name="generate-a-detailed-report"></a>Generación de un informe detallado

Para generar un informe detallado sobre las directivas de grupo actualmente activas, abra un símbolo del sistema en el modo **Ejecutar como administrador** y escriba el siguiente comando:

```console
GPresult.exe /h gpresult.html
```

Esto generará un informe ubicado en *./gpresult.html*. Abra este archivo y es posible que vea los siguientes resultados, en función de cómo Microsoft Defender Antivirus se haya desactivado.

##### <a name="group-policy-results"></a>Resultados de la directiva de grupo

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Si la configuración de seguridad se implementa a través de la directiva de grupo (GPO) en el nivel de dominio o local, o a través de System Center Configuration Manager (SCCM)

En el informe GPResults, en el encabezado *Componentes de Windows/Antivirus de Microsoft Defender*, puede ver algo parecido a la siguiente entrada, que indica que Microsoft Defender Antivirus está desactivado.

Policy|Setting|GPO ganador
---|---|---
Desactivar Microsoft Defender Antivirus|Habilitado|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Si la configuración de seguridad se implementa a través de la preferencia de directiva de grupo (GPP)

En el encabezado , *Elemento del Registro (Ruta de acceso de clave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nombre del valor: DisableAntiSpyware)*, es posible que vea algo parecido a la siguiente entrada, lo que indica que Microsoft Defender Antivirus está desactivado.

DisableAntiSpyware|-
---|---
GPO ganador|Win10-Workstations
Resultado: Correcto|
**General**|
Acción|Actualizar
**Propiedades**|
Hive|HKEY_LOCAL_MACHINE
Ruta de acceso de clave|SOFTWARE\Policies\Microsoft\Windows डिफेन्डर
Nombre del valor|DisableAntiSpyware
Tipo de valor|REG_DWORD
Datos del valor|0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Si la configuración de seguridad se implementa a través de la clave del Registro

El informe puede contener el texto siguiente, que indica que Microsoft Defender Antivirus está desactivado:

> Registro (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hexadecimal)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Si la configuración de seguridad se establece en Windows o en la imagen de Windows Server

Es posible que el administrador de creación de imágenes haya establecido la directiva de seguridad **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** localmente a través *deGPEdit.exe*, *LGPO.exe* o modificando el registro en su secuencia de tareas. Puede [configurar un identificador de imagen de confianza](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) para Microsoft Defender Antivirus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Volver a activar Microsoft Defender Antivirus

Microsoft Defender Antivirus se activará automáticamente si no hay ningún otro antivirus activo actualmente. Tendrá que desactivar completamente el antivirus de terceros para asegurarse de que Microsoft Defender Antivirus pueda ejecutarse con funcionalidad completa.

> [!WARNING]
> Las soluciones que sugieren que edite los valores de inicio *de Windows डिफेन्डर* para *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* y *windefend* en HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services no son compatibles y pueden forzarle a volver a crear imágenes del sistema.

El modo pasivo está disponible si empieza a usar Microsoft Defender para punto de conexión y un antivirus de terceros junto con Microsoft Defender Antivirus. El modo pasivo permite Microsoft Defender Antivirus examinar archivos y actualizarse, pero no corregirá las amenazas. Además, la supervisión del comportamiento a través de [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) no está disponible en modo pasivo, a menos que se implemente la [prevención de pérdida de datos de punto de conexión (DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)

Otra característica, conocida como [examen periódico limitado](limited-periodic-scanning-microsoft-defender-antivirus.md), está disponible para los usuarios finales cuando Microsoft Defender Antivirus está configurado para desactivarse automáticamente. Esta característica permite Microsoft Defender Antivirus examinar archivos periódicamente junto con un antivirus de terceros, utilizando un número limitado de detecciones.

> [!IMPORTANT]
> No se recomienda el examen periódico limitado en entornos empresariales. Las funcionalidades de detección, administración e informes disponibles al ejecutar Microsoft Defender Antivirus en este modo se reducen en comparación con el modo activo.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)


### <a name="see-also"></a>Vea también

- [compatibilidad con Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md)
- [Microsoft Defender Antivirus en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md)
