---
title: Incorporar los dispositivos de la organización a Microsoft Defender für Unternehmen
description: Incorporar los dispositivos de la organización a Microsoft Defender für Unternehmen
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: e9810b453136025e094ef8a0e88bff526f2c5a51
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634787"
---
# <a name="onboard-managed-devices-to-microsoft-defender-for-business"></a>Incorporar dispositivos administrados para Microsoft Defender für Unternehmen

Incorpore dispositivos Microsoft Defender für Unternehmen protegerlos con protección de última generación (antivirus, antimalware y protección entregada en la nube), protección de firewall, filtrado de contenido web y mucho más. 

Para incorporar dispositivos, puedes elegir entre varias opciones:

- [Usar la incorporación automática para Windows dispositivos que ya están inscritos en Microsoft Endpoint Manager](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager)

- [Usar un script local para incorporar dispositivos Windows y macOS](#use-a-local-script-to-onboard-windows-and-macos-devices)

- [Usa Endpoint Manager para inscribir](#use-microsoft-endpoint-manager-to-enroll-devices) dispositivos (Windows, macOS, iOS y Android) y, a continuación, aplicar directivas de Defender para empresas a esos dispositivos

En este artículo también se incluyen:

- [Cómo ejecutar una prueba de detección en un Windows dispositivo](#run-a-detection-test-on-a-windows-device)

- [Cómo incorporar dispositivos gradualmente](#onboard-devices-gradually)

- [Cómo salir de un dispositivo si](#offboard-a-device) se reemplaza un dispositivo o si alguien abandona la organización

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, [consulte Microsoft Defender für Unternehmen solución de problemas](../security/defender-business/mdb-troubleshooting.yml).

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager"></a>Usar la incorporación automática para Windows dispositivos que ya están inscritos en Microsoft Endpoint Manager

La opción de incorporación automática solo se aplica Windows dispositivos. La incorporación automática está disponible si tu organización ya usaba Microsoft Endpoint Manager, Microsoft Intune o Mobile Administración de dispositivos (MDM) en Microsoft Intune antes de obtener Defender para empresas y ya tienes Windows dispositivos inscritos en Endpoint Manager. 

Si Windows dispositivos ya están inscritos en Endpoint Manager, Defender para empresas detectará esos dispositivos mientras se está configurando y configurando Defender para empresas. Se te preguntará si quieres usar la incorporación automática para todos o algunos de tus Windows dispositivos. Puedes incorporar todos los Windows a la vez, o seleccionar dispositivos específicos para empezar y, a continuación, agregar más dispositivos más adelante.

Para obtener más información sobre la incorporación automática, vea el paso 2 en [Usar el asistente para configurar](../security/defender-business/mdb-use-wizard.md) Microsoft Defender für Unternehmen.

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices"></a>Usar un script local para incorporar dispositivos Windows y macOS

Puedes usar un script local para incorporar dispositivos Windows y macOS. Cuando ejecutas el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza aún no existe), inscribe el dispositivo en Microsoft Endpoint Manager (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender para empresas. 

Puedes incorporar hasta 10 dispositivos a la vez con este método.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en Incorporación **de** un dispositivo, en la sección Método  de implementación, elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. Siga las instrucciones de los artículos siguientes:

   - Windows: [incorporar Windows dispositivos con un script local](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)

   - dispositivos macOS: [implementación manual para Pertahanan Microsoft untuk Titik Akhir en macOS](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-microsoft-endpoint-manager-to-enroll-devices"></a>Usar Microsoft Endpoint Manager para inscribir dispositivos

Si ya estaba usando Endpoint Manager (que incluye Microsoft Intune y Mobile Administración de dispositivos), antes de obtener Defender para empresas, puede seguir usando Endpoint Manager para incorporar los dispositivos de la organización. Con Endpoint Manager, puedes incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

Si tu organización usa dispositivos Android, usa este método.

Consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).


## <a name="run-a-detection-test-on-a-windows-device"></a>Ejecutar una prueba de detección en un Windows dispositivo

Después de incorporar Windows dispositivos a Defender para empresas, puedes ejecutar una prueba de detección en un dispositivo Windows para asegurarte de que todo funciona correctamente.

1. En el Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="onboard-devices-gradually"></a>Incorporar dispositivos gradualmente

Si prefieres incorporar dispositivos en fases, a los que llamamos *incorporación gradual* de dispositivos, sigue estos pasos: 

1. Identificar un conjunto de dispositivos que se incorporarán.

2. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

3. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

4. Seleccione un sistema operativo (como **Windows 10 y 11)** y, a continuación, elija un método de incorporación (como **script local**). Siga las instrucciones proporcionadas para el método seleccionado.

5. Repita este proceso para cada conjunto de dispositivos que desee incorporar. 

> [!TIP]
> No tienes que usar el mismo paquete de incorporación cada vez que incorpores dispositivos. Por ejemplo, puedes usar un script local para incorporar algunos dispositivos y, más adelante, puedes elegir otro método para incorporar más dispositivos.

## <a name="offboard-a-device"></a>Fuera de un dispositivo

Si quieres salir de un dispositivo, sigue estos pasos:

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, **elija Configuración** y, a continuación, elija **Extremos**.

3. En **Administración de dispositivos**, elija **Offboarding**.

4. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Offboard a device**, en la sección **Método** de implementación, elija **Script local**. 

5. En la pantalla de confirmación, revise la información y, a continuación, elija **Descargar** para continuar.

6. Seleccione **Descargar paquete de offboarding**. Se recomienda guardar el paquete de offboarding en una unidad extraíble.

7. Ejecuta el script en cada dispositivo que quieras desactivar. ¿Necesita ayuda con esta tarea? Vea los siguientes recursos:   

   - Windows: [offboard Windows dispositivos con un script local](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   
   - dispositivos macOS: [desinstalación en macOS](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> La salida de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes del offboarding se conservan durante un máximo de seis (6) meses.

## <a name="next-steps"></a>Siguientes pasos

[Revisar acciones de corrección en Microsoft 365 Business Premium](m365bp-review-remediation-actions-devices.md)