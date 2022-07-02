---
title: Incorporar los dispositivos de su organización a Microsoft Defender para Empresas
description: Incorporar los dispositivos de su organización a Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 70be4a5b7991d038dd1e34c00778de6bb3a67b84
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66573977"
---
# <a name="onboard-enrolled-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos inscritos a Microsoft Defender para empresas

Microsoft 365 Empresa Premium incluye Microsoft Defender para Empresas, una solución de seguridad de punto de conexión para pequeñas y medianas empresas. Defender para empresas proporciona protección de próxima generación (antivirus, antimalware y protección de entrega en la nube), protección de firewall, filtrado de contenido web y mucho más para los dispositivos de su empresa. La protección se aplica al incorporar dispositivos. 

Para incorporar dispositivos, puede elegir entre varias opciones:

- [Incorporación automática para dispositivos Windows inscritos en Microsoft Intune](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune)
- [Un script local para incorporar dispositivos Windows y macOS a Defender para empresas](#use-a-local-script-to-onboard-windows-and-macos-devices-to-defender-for-business)
- [Intune para inscribir dispositivos, incluidos los dispositivos móviles](#use-intune-to-enroll-devices) (Windows, macOS, iOS y Android) y, a continuación, aplicar directivas de Defender para empresas a esos dispositivos

En este artículo también se incluyen:

- [Cómo ejecutar una prueba de detección en un dispositivo Windows](#run-a-detection-test-on-a-windows-device)
- [Cómo incorporar dispositivos gradualmente](#onboard-devices-gradually)
- [Cómo desincorporar un dispositivo](#offboard-a-device) si se reemplaza un dispositivo o alguien abandona la organización

> [!IMPORTANT]
> Si algo va mal y se produce un error en el proceso de incorporación, consulte [Solución de problemas de Microsoft Defender para empresas](../security/defender-business/mdb-troubleshooting.yml).

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune"></a>Uso de la incorporación automática para dispositivos Windows que ya están inscritos en Intune

Puede incorporar dispositivos Windows a Defender para empresas automáticamente si esos dispositivos ya están inscritos en Intune. Defender para empresas detecta los dispositivos cliente de Windows inscritos en Intune y le pide que elija si quiere incorporar esos dispositivos automáticamente. Las directivas de seguridad y la configuración de Defender para empresas se aplican a esos dispositivos. Este proceso se denomina *incorporación automática*. La opción de incorporación automática solo se aplica a dispositivos Windows. La incorporación automática está disponible si se cumplen las condiciones siguientes:

- Su organización ya usaba Microsoft Endpoint Manager, Microsoft Intune o Mobile Administración de dispositivos (MDM) en Microsoft Intune antes de obtener Defender para empresas (los clientes de Microsoft 365 Empresa Premium ya tienen Microsoft Intune).
- Ya tiene dispositivos Windows inscritos en Intune.

> [!TIP]
> Cuando se le pida que use la incorporación automática, se recomienda seleccionar los "todos los dispositivos inscritos". Opción. De este modo, cuando los dispositivos Windows se inscriban en Intune posteriormente, se incorporarán automáticamente a Defender para empresas.

Para obtener más información sobre la incorporación automática, consulte el paso 2 de [Use el asistente para configurar Microsoft Defender para Empresas](../security/defender-business/mdb-use-wizard.md).

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices-to-defender-for-business"></a>Usar un script local para incorporar dispositivos Windows y macOS a Defender para empresas

Puede usar un script local para incorporar dispositivos Windows y Mac. Al ejecutar el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza aún no existe), inscribe el dispositivo en Intune (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender para empresas. Puede incorporar hasta 10 dispositivos a la vez mediante el script local.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** o **macOS**, y, a continuación, en la sección **Método de implementación**, elija **Script local**. 

4. Seleccione **Descargar el paquete de incorporación** Se recomienda guardar el paquete de incorporación en una unidad extraíble. (Si seleccionó **macOS**, seleccione también **Descargue el paquete de instalación** y guárdelo en el dispositivo extraíble).

5. Use las siguientes instrucciones:

   - Dispositivos Windows: [Abordar dispositivos Windows mediante un script local](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)
   - dispositivos macOS: [ Implementación manual para Microsoft Defender para punto de conexión en macOS](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-intune-to-enroll-devices"></a>Uso de Intune para inscribir dispositivos

Para inscribir un dispositivo, inscríbase usted mismo o haga que los usuarios inicien sesión en el portal de empresa e inscriban e instalen las aplicaciones necesarias. 

Si ya usaba Intune o Mobile Administración de dispositivos antes de obtener Defender para empresas, puede seguir usando Intune para incorporar los dispositivos de su organización. Con Intune, puede incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

Consultar [Habilitar la inscripción en Microsoft Intune](/mem/intune/enrollment/device-enrollment). 

## <a name="run-a-detection-test-on-a-windows-device"></a>Ejecutar una prueba de detección en un dispositivo Windows

Después de incorporar dispositivos Windows a Defender para empresas, puedes ejecutar una prueba de detección en un dispositivo Windows para asegurarte de que todo funciona correctamente.

1. En el dispositivo Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra una ventana de Símbolo de sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cierra automáticamente. Si se realiza correctamente, la prueba de detección se marca como completada y aparece una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos diez minutos.

## <a name="onboard-devices-gradually"></a>Incorporar dispositivos gradualmente

Si prefiere incorporar dispositivos en fases, que llamamos *a incorporación de dispositivos degradada*, siga estos pasos: 

1. Identifique un conjunto de dispositivos para incorporar.

2. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

3. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

4. Seleccione un sistema operativo (como **Windows 10 y 11)** y, a continuación, elija un método de incorporación (como **Script local**). Siga las instrucciones proporcionadas para el método seleccionado.

5. Repita este proceso para cada conjunto de dispositivos que quiera incorporar. 

> [!TIP]
> No tiene que usar el mismo paquete de incorporación cada vez que incorpore dispositivos. Por ejemplo, puede usar un script local para incorporar algunos dispositivos y, más adelante, puede elegir otro método para incorporar más dispositivos.

## <a name="offboard-a-device"></a>Retirar un dispositivo

Si desea desconectar un dispositivo, use uno de los procedimientos siguientes:

1. En el panel de navegación, elija **Configuración** y, a continuación, elija **Puntos de conexión**.

2. En **Administración de dispositivos**, elige **Desincorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Desincorporar un dispositivo**, en la sección **Método**, elige **Script local**. 

4. En la pantalla de confirmación, revise la información y elija **Descargar** para continuar.

5. Seleccione **Descargar paquete de retirada**. Se recomienda guardar el paquete de retirada en una unidad extraíble.

6. Ejecute el script en cada dispositivo que quiera desincorporar. ¿Necesita ayuda con esta tarea? Vea los siguientes recursos:   

   - Dispositivos Windows: [Desincorporar dispositivos Windows mediante un script local](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script) 
   - Dispositivos macOS: [Desinstalación en macOS](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> La desincorporación de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes de la desincorporación se conservan durante un máximo de seis (6) meses.

## <a name="next-objective"></a>Siguiente objetivo

[Configurar la protección para los dispositivos Windows](m365bp-protection-settings-for-windows-10-devices.md).
