---
title: Incorporación de dispositivos a Microsoft Defender para empresas
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 58cb84f082bf290e870f545c0bb48503143aa837
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375803"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos a Microsoft Defender para empresas

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Con Microsoft Defender para empresas, tienes varias opciones entre las que elegir para incorporar los dispositivos de tu empresa. En este artículo se le guía por las opciones e incluye información general sobre cómo funciona la incorporación.

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los métodos de](#types-of-onboarding-methods)incorporación y determine si usa la incorporación automática o la incorporación manual.

2. Realice una de las acciones siguientes:

   - Si usa la incorporación automática, vaya al [Paso 5: Configurar](mdb-configure-security-settings.md)las directivas y la configuración de seguridad en Microsoft Defender para empresas .
   - Si estás incorporando dispositivos manualmente, ve a Incorporación de un dispositivo mediante [un script local en Microsoft 365 Defender](#onboard-a-device-using-a-local-script-in-defender-for-business).
   - Si ya estás usando Microsoft Intune, ve a Incorporación de [dispositivos con Microsoft Intune](#onboard-devices-using-microsoft-intune).

3. [Ejecute una prueba de detección](#run-a-detection-test) para dispositivos recién incorporados.

4. [Vea los pasos siguientes](#next-steps). 

En este artículo también se incluye información [sobre cómo salir de un dispositivo](#what-if-i-want-to-offboard-a-device).

## <a name="types-of-onboarding-methods"></a>Tipos de métodos de incorporación

En la tabla siguiente se describen los tipos de métodos de incorporación que se admiten en Defender para empresas durante la versión preliminar. 
<br/><br/>

| Método de incorporación  | Descripción  |
|---------|---------|
| **Incorporación automática**<br/>(*disponible para clientes que ya usan Microsoft Endpoint Manager*) | Si ya usaste Microsoft Endpoint Manager obtener Defender para empresas, Defender for Business lo detectará. Se te preguntará si quieres usar el proceso de incorporación automática para dispositivos que se incorporaron anteriormente a Microsoft Endpoint Manager. La incorporación automática configura una conexión entre Defender para empresas y Microsoft Endpoint Manager y, a continuación, incorpora dispositivos a Defender para empresas. Esta opción te permite incorporar dispositivos a Defender para empresas de forma rápida y eficaz.<br/><br/>Si elige el proceso de incorporación *automática,* todos los dispositivos que estén inscritos en Microsoft Endpoint Manager se incorporarán a Defender for Endpoint. <br/><br/>Si desea usar la incorporación automática, omita los procedimientos descritos en este artículo y vaya al Paso [5: Configurar](mdb-configure-security-settings.md)la configuración de seguridad y las directivas en Microsoft Defender para empresas .  |
| **Script local**<br/>(*recomendado durante la vista previa; útil para incorporar algunos dispositivos a la vez*)  | Durante la vista previa, puedes incorporar dispositivos en Defender para empresas mediante un script local. Microsoft Defender para empresas hospeda un script descargable que puedes usar en Windows 10 o 11 dispositivos. La ejecución del script en un dispositivo crea una confianza con Azure Active Directory (Azure AD) e inscribe el dispositivo con Microsoft Intune.<br/><br/>Si quieres usar este método, ve a Incorporación de un dispositivo [mediante un script local en Microsoft 365 Defender](#onboard-a-device-using-a-local-script-in-defender-for-business). |
| **Microsoft Intune** <br/>(*disponible para clientes que ya usan Microsoft Intune*) | Si ya usaste Microsoft Intune obtener Defender para empresas, puedes usar Microsoft Intune para incorporar dispositivos. Durante la vista previa, por ejemplo, puedes incorporar dispositivos iOS, macOS, Linux y Android a Defender para empresas. <br/><br/>Si quieres usar este método, consulta [Inscripción de dispositivos en Intune](/mem/intune/enrollment/device-enrollment). |

> [!TIP]
> Si algo sale mal al incorporar dispositivos, consulta Solución de problemas de [Microsoft Defender para empresas.](mdb-troubleshooting.yml) 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>Incorporación de un dispositivo con un script local en Defender para empresas

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, **elija Configuración** endpoints y, a continuación, en  >  Administración **de dispositivos,** elija **Incorporación**.

3. Seleccione **Windows 10 y 11** y, **a** continuación,  en Incorporación de un dispositivo , en la sección Método de implementación, elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. En cada dispositivo, siga estos pasos: 

   1. Copie el `WindowsDefenderATPOnboardingPackage.zip` archivo que descargó en un dispositivo y extraiga su contenido. Puedes extraer el contenido en la carpeta Escritorio **del** dispositivo.
   
   2. Abra el símbolo del sistema como administrador.
   
   3. En la ventana Símbolo del sistema, escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta **Escritorio,** escriba y, a `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd` continuación, presione la tecla Entrar.

6. Continúe con [Ejecutar una prueba de detección](#run-a-detection-test).

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, consulta Solución de problemas de [Microsoft Defender para empresas.](mdb-troubleshooting.yml)

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporar dispositivos con Microsoft Intune

Si ya usaste Microsoft Intune obtener Defender para empresas, puedes usar Microsoft Intune para incorporar dispositivos. Para obtener ayuda con esto, consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Después de incorporar un dispositivo manualmente, puedes ejecutar una prueba de detección para asegurarte de que todo funciona correctamente con Defender para empresas.

1. En el dispositivo, cree una carpeta: `C:\test-MDATP-test` .

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender para el dispositivo recién incorporado en unos 10 minutos.

## <a name="what-if-i-want-to-offboard-a-device"></a>¿Qué sucede si quiero salir de un dispositivo?

Si quieres salir de un dispositivo, sigue estos pasos:

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, **elija Configuración** y, a continuación, elija **Extremos**.

3. En **Administración de dispositivos,** **elija Offboarding**.

4. Seleccione **Windows 10 y 11** y, a continuación, en **Offboard a device**, en la sección **Método** de implementación, elija **Script local**. 

5. En la pantalla de confirmación, revise la información y, a continuación, elija **Descargar** para continuar.

6. Guarde la carpeta comprimida en una ubicación, como una unidad extraíble.

7. En cada dispositivo, siga estos pasos: 

   1. Copie el paquete de configuración ( `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD` ) que descargó en el dispositivo y extraiga su contenido. Puedes extraer el contenido en la carpeta Escritorio **del** dispositivo. ( `YYYY-MM-DD` hace referencia a la fecha de expiración del paquete).

   2. Abra el símbolo del sistema como administrador.

   3. En la ventana Símbolo del sistema, escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta **Escritorio,** escriba y, a `%userprofile%\Desktop\WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.cmd` continuación, presione la tecla Entrar.

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 5: Configurar la configuración de seguridad y las directivas en Microsoft Defender para empresas](mdb-configure-security-settings.md)

- [Introducción al uso de Microsoft Defender para empresas](mdb-get-started.md) 