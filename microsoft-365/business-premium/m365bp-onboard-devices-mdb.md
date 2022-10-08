---
title: Incorporar los dispositivos de su organización a Microsoft Defender para Empresas
description: Incorporar los dispositivos de su organización a Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.openlocfilehash: d358c456bea558bae4b5c17f7d0ea52e8a5803a9
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097103"
---
# <a name="onboard-enrolled-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos inscritos a Microsoft Defender para Empresas

Microsoft 365 Empresa Premium incluye [Microsoft Defender para Empresas](../security/defender-business/mdb-overview.md), una solución de seguridad de punto de conexión para pequeñas y medianas empresas. Defender para empresas proporciona protección de próxima generación (antivirus, antimalware y protección de entrega en la nube), protección de firewall, filtrado de contenido web y mucho más para los dispositivos de su empresa. La protección se aplica al incorporar dispositivos y aplicar directivas de seguridad a dichos dispositivos.

Para incorporar dispositivos a Defender para Empresas, puede elegir entre varias opciones:

- [Incorporación automática para dispositivos Windows ya inscritos en Microsoft Intune](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune)
- [Un script local para incorporar dispositivos Windows y Mac a Defender para Empresas](#use-a-local-script-to-onboard-windows-and-mac-devices-to-defender-for-business) (para dispositivos que aún no están inscritos en Intune)
- [Intune para inscribir dispositivos, incluidos los dispositivos móviles](#use-intune-to-enroll-devices) (Windows, Mac, iOS y Android) y, luego, aplicar directivas de Defender para Empresas a dichos dispositivos

En este artículo también se incluyen:

- [¿Qué ocurre con los servidores?](#what-about-servers) (NUEVO)
- [Cómo ejecutar una prueba de detección en un dispositivo Windows](#run-a-detection-test-on-a-windows-device)
- [Cómo incorporar dispositivos gradualmente](#onboard-devices-gradually)
- [Cómo desincorporar un dispositivo](#offboard-a-device) si se reemplaza un dispositivo o alguien abandona la organización

> [!IMPORTANT]
> Si algo va mal y se produce un error en el proceso de incorporación, consulte [Solución de problemas de Microsoft Defender para empresas](../security/defender-business/mdb-troubleshooting.yml).

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune"></a>Uso de la incorporación automática para dispositivos Windows que ya están inscritos en Intune

Puede incorporar dispositivos cliente Windows a Defender para Empresas automáticamente si los dispositivos ya están inscritos en Intune. Defender para Empresas detecta los dispositivos cliente Windows inscritos en Intune y le pide que elija si prefiere incorporarlos automáticamente. Las directivas de seguridad y la configuración de Defender para empresas se aplican a esos dispositivos. Este proceso se denomina *incorporación automática*. 

La incorporación automática ayuda a proteger los dispositivos prácticamente de inmediato. Tenga en cuenta que la opción de incorporación automática solo se aplica a los dispositivos cliente Windows y solo si se cumplen las condiciones siguientes:

- Su organización ya usaba Intune o Administración de dispositivos móviles (MDM) en Intune antes de obtener Defender para Empresas (los clientes de Microsoft 365 Empresa Premium ya tienen Microsoft Intune y MDM).
- Ya tiene dispositivos cliente Windows inscritos en Intune.

> [!TIP]
> Si se le pide que use la incorporación automática, se recomienda seleccionar la opción "todos los dispositivos inscritos". De este modo, cuando los dispositivos Windows se inscriban en Intune posteriormente, se incorporarán automáticamente a Defender para empresas.

Para obtener más información sobre la incorporación automática, consulte el paso 2 de [Use el asistente para configurar Microsoft Defender para Empresas](../security/defender-business/mdb-use-wizard.md).

## <a name="use-a-local-script-to-onboard-windows-and-mac-devices-to-defender-for-business"></a>Usar un script local para incorporar dispositivos Windows y Mac a Defender para Empresas

Puede usar un script local para incorporar dispositivos Windows y Mac. Al ejecutar el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza aún no existe), inscribe el dispositivo en Intune (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender para empresas. Puede incorporar hasta 10 dispositivos a la vez mediante el script local.

Consulte [Incorporar dispositivos a Microsoft Defender para Empresas](../security/defender-business/mdb-onboard-devices.md) para obtener instrucciones detalladas.

## <a name="use-intune-to-enroll-devices"></a>Uso de Intune para inscribir dispositivos

Para inscribir un dispositivo, puede hacerlo usted mismo o pedir a los usuarios que inicien sesión en la aplicación del portal de empresa, inscriban sus dispositivos y, luego, instalen las aplicaciones necesarias. 

Si ya usaba Intune o Mobile Administración de dispositivos antes de obtener Defender para empresas, puede seguir usando Intune para incorporar los dispositivos de su organización. Con Intune, puede incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

Consultar [Habilitar la inscripción en Microsoft Intune](/mem/intune/enrollment/device-enrollment). 

## <a name="what-about-servers"></a>¿Qué ocurre con los servidores?

De forma predeterminada, los servidores no se admiten en Microsoft 365 Empresa Premium ni en la versión independiente de Defender para Empresas. Sin embargo, **la capacidad de incorporar un servidor, como un punto de conexión que ejecuta Windows Server o Linux Server, ya está en versión preliminar**. 

Consulta [Cómo obtener servidores de Microsoft Defender para Empresas (versión preliminar).](../security/defender-business/get-defender-business-servers.md)

## <a name="run-a-detection-test-on-a-windows-device"></a>Ejecutar una prueba de detección en un dispositivo Windows

Después de incorporar dispositivos Windows a Defender para empresas, puedes ejecutar una prueba de detección en un dispositivo Windows para asegurarte de que todo funciona correctamente.

1. En el dispositivo Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra una ventana de Símbolo de sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

After the command has run, the Command Prompt window closes automatically. If successful, the detection test is marked as completed, and a new alert appears in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) for the newly-onboarded device in about ten minutes.

## <a name="onboard-devices-gradually"></a>Incorporar dispositivos gradualmente

Si prefiere incorporar dispositivos en fases, que llamamos *a incorporación de dispositivos degradada*, siga estos pasos: 

1. Identifique un conjunto de dispositivos para incorporar.

2. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

3. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

4. Select an operating system (such as **Windows 10 and 11)**, and then choose an onboarding method (such as **Local script**). Follow the guidance provided for the method you selected.

5. Repita este proceso para cada conjunto de dispositivos que quiera incorporar. 

> [!TIP]
> No tiene que usar el mismo paquete de incorporación cada vez que incorpore dispositivos. Por ejemplo, puede usar un script local para incorporar algunos dispositivos y, más adelante, puede elegir otro método para incorporar más dispositivos.

## <a name="offboard-a-device"></a>Retirar un dispositivo

Si desea desconectar un dispositivo, use uno de los procedimientos siguientes:

1. En el panel de navegación, elija **Configuración** y, a continuación, elija **Puntos de conexión**.

2. En **Administración de dispositivos**, elige **Desincorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Desincorporar un dispositivo**, en la sección **Método**, elige **Script local**. 

4. En la pantalla de confirmación, revise la información y elija **Descargar** para continuar.

5. Seleccione **Descargar paquete de desincorporación**. Se recomienda guardar el paquete de retirada en una unidad extraíble.

6. Ejecute el script en cada dispositivo que quiera desincorporar. ¿Necesita ayuda con esta tarea? Vea los siguientes recursos:   

   - Dispositivos Windows: [Desincorporar dispositivos Windows mediante un script local](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script) 
   - Mac: [Desinstalar en Mac](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> La desincorporación de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes de la desincorporación se conservan durante un máximo de seis (6) meses.

## <a name="next-objective"></a>Siguiente objetivo

[Configurar la protección para los dispositivos Windows](m365bp-protection-settings-for-windows-10-devices.md).
