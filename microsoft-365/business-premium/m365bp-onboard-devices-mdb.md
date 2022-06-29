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
ms.openlocfilehash: 7d86b04b1c3883bc5b3da0e429dbbddd8275622f
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489522"
---
# <a name="onboard-enrolled-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos inscritos a Microsoft Defender para empresas

Ahora que ha inscrito los dispositivos, debe incorporarlos a Microsoft Defender para empresas para implementar la protección de próxima generación (antivirus, antimalware y protección de entrega en la nube), protección de firewall, filtrado de contenido web, etc. 

Para incorporar dispositivos, puede elegir entre varias opciones:

- [Use la incorporación automática para dispositivos Windows que ya están inscritos en Microsoft Endpoint Manager](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager)

- [Use un script local para incorporar dispositivos Windows y macOS](#use-a-local-script-to-onboard-windows-and-macos-devices)

- [Use Endpoint Manager para inscribir dispositivos](#use-microsoft-endpoint-manager-to-enroll-devices) (Windows, macOS, iOS y Android) y, a continuación, aplique directivas de Defender para empresas a esos dispositivos.

En este artículo también se incluyen:

- [Cómo ejecutar una prueba de detección en un dispositivo Windows](#run-a-detection-test-on-a-windows-device)

- [Cómo incorporar dispositivos gradualmente](#onboard-devices-gradually)

- [Cómo desincorporar un dispositivo](#offboard-a-device) si se reemplaza un dispositivo o alguien abandona la organización

> [!IMPORTANT]
> Si algo va mal y se produce un error en el proceso de incorporación, consulte [Solución de problemas de Microsoft Defender para empresas](../security/defender-business/mdb-troubleshooting.yml).

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager"></a>Usar la incorporación automática para dispositivos Windows que ya están inscritos en Microsoft Endpoint Manager

La opción de incorporación automática solo se aplica a dispositivos Windows. La incorporación automática está disponible si se cumplen las condiciones siguientes:

- Su organización ya usaba Microsoft Endpoint Manager, Microsoft Intune o Mobile Administración de dispositivos (MDM) en Microsoft Intune antes de obtener Defender para empresas (los clientes de Microsoft 365 Empresa Premium ya tienen Microsoft Intune).

- Ya tiene dispositivos Windows inscritos en Endpoint Manager.

Si los dispositivos Windows ya están inscritos en Endpoint Manager, Defender para empresas detecta esos dispositivos mientras se está configurando Defender para empresas. Se te preguntará si quieres usar la incorporación automática para todos los dispositivos Windows o para algunos de ellos. Puede incorporar todos los dispositivos Windows a la vez o seleccionar dispositivos específicos con los que empezar y, a continuación, agregar más dispositivos más adelante.

> [!TIP]
> Se recomienda seleccionar los "todos los dispositivos inscritos". Opción. De este modo, cuando los dispositivos Windows se inscriban en Endpoint Manager posteriormente, se incorporarán automáticamente a Defender para empresas.
Para obtener más información sobre la incorporación automática, consulte el paso 2 de [Use el asistente para configurar Microsoft Defender para empresas](../security/defender-business/mdb-use-wizard.md).

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices"></a>Uso de un script local para incorporar dispositivos Windows y macOS

Puede usar un script local para incorporar dispositivos Windows y Mac. Al ejecutar el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza aún no existe), inscribe el dispositivo en Microsoft Endpoint Manager (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender para empresas. Este método es útil para incorporar dispositivos en Defender para empresas. Puede incorporar hasta 10 dispositivos a la vez.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** o **macOS**, y, a continuación, en la sección **Método de implementación**, elija **Script local**. 

4. Seleccione **Descargar el paquete de incorporación** Se recomienda guardar el paquete de incorporación en una unidad extraíble. (Si seleccionó **macOS**, seleccione también **Descargue el paquete de instalación** y guárdelo en el dispositivo extraíble).

5. Use las siguientes instrucciones:

   - Dispositivos Windows: [Abordar dispositivos Windows mediante un script local](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)

   - dispositivos macOS: [ Implementación manual para Microsoft Defender para punto de conexión en macOS](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-microsoft-endpoint-manager-to-enroll-devices"></a>Usar Microsoft Endpoint Manager para inscribir los dispositivos.

Para inscribir un dispositivo, inscríbase usted mismo o haga que los usuarios inicien sesión en el portal de empresa e inscriban e instalen las aplicaciones necesarias. 

Si ya usaba Endpoint Manager (que incluye Microsoft Intune y Mobile Administración de dispositivos), antes de obtener Defender para empresas, puede seguir usando Endpoint Manager para incorporar los dispositivos de su organización. Con Endpoint Manager, puede incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

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

1. En **Administración de dispositivos**, elige **Desincorporación**.

1. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Desincorporar un dispositivo**, en la sección **Método**, elige **Script local**. 

1. En la pantalla de confirmación, revise la información y elija **Descargar** para continuar.

1. Seleccione **Descargar paquete de retirada**. Se recomienda guardar el paquete de retirada en una unidad extraíble.

1. Ejecute el script en cada dispositivo que quiera desincorporar. ¿Necesita ayuda con esta tarea? Vea los siguientes recursos:   

   - Dispositivos Windows: [Desincorporar dispositivos Windows mediante un script local](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   
   - Dispositivos macOS: [Desinstalación en macOS](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> La desincorporación de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes de la desincorporación se conservan durante un máximo de seis (6) meses.

## <a name="next-objective"></a>Siguiente objetivo

[Configurar la protección para los dispositivos Windows](m365bp-protection-settings-for-windows-10-devices.md).
