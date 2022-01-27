---
title: Incorporar dispositivos a Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/23/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: a9aa664c7b7e6c2093817772f8f0bfaefdff3d9e
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244576"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>Incorporar dispositivos a Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Con Microsoft Defender para empresas (versión preliminar), tienes varias opciones entre las que elegir para incorporar los dispositivos de tu empresa. En este artículo se le guía por las opciones e incluye información general sobre cómo funciona la incorporación.

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los métodos de](#types-of-onboarding-methods)incorporación y determine si usa la incorporación automática o la incorporación manual.

2. Realiza una de las siguientes acciones:

   - Si usa la incorporación automática, vaya al [Paso 5: Configurar](mdb-configure-security-settings.md)las directivas y la configuración de seguridad en Microsoft Defender para empresas (versión preliminar).
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
| **Incorporación automática**<br/>(*disponible para clientes que ya usan Microsoft Endpoint Manager*) | Si ya usaste Microsoft Endpoint Manager obtener Defender para empresas (versión preliminar), Defender para empresas lo detectará. Se te preguntará si quieres usar el proceso de incorporación automática para dispositivos que se incorporaron anteriormente a Microsoft Endpoint Manager. <br/><br/>La incorporación automática configura una conexión entre Defender para empresas (versión preliminar) y Microsoft Endpoint Manager y, a continuación, incorpora dispositivos a Defender para empresas (versión preliminar). Esta opción te permite incorporar dispositivos a Defender para empresas (versión preliminar) de forma rápida y eficaz. Todos Windows dispositivos que están inscritos actualmente en Microsoft Endpoint Manager se incorporarán a Defender para empresas. <br/><br/>Si elige la incorporación automática, omita los procedimientos de este artículo y vaya al Paso 5: Configurar la configuración de seguridad y las directivas en Microsoft Defender para empresas [(versión preliminar).](mdb-configure-security-settings.md)  |
| **Script local**<br/>(*recomendado durante la vista previa; útil para incorporar algunos dispositivos a la vez*)  | Durante la vista previa, puedes incorporar dispositivos en Defender para empresas (versión preliminar) mediante un script que descargues y ejecutes en dispositivos macOS, Windows 10 o 11 y Linux. La ejecución del script en un dispositivo crea una confianza con Azure Active Directory (Azure AD) e inscribe el dispositivo con Microsoft Intune. El proceso es muy similar al de la incorporación de dispositivos [a Microsoft Defender para endpoint](../defender-endpoint/onboarding.md).<br/><br/>Para usar este método, vaya [a Incorporación de un dispositivo mediante un script local en Microsoft 365 Defender](#onboard-a-device-using-a-local-script-in-defender-for-business). |
| **Microsoft Intune** <br/>(*disponible para clientes que ya usan Microsoft Intune*) | Si ya [usaste](/mem/intune/fundamentals/what-is-intune) Microsoft Intune obtener Defender para empresas (versión preliminar), puedes usar Microsoft Intune para incorporar dispositivos. Durante la vista previa, puedes usar Microsoft Intune para incorporar dispositivos Windows, iOS, macOS, Linux y Android a Defender para empresas (versión preliminar). <br/><br/>Para usar este método, consulta [Inscripción de dispositivos en Intune](/mem/intune/enrollment/device-enrollment). |

> [!TIP]
> Si algo sale mal al incorporar dispositivos, consulta Solución de problemas de Microsoft Defender para empresas [(versión preliminar).](mdb-troubleshooting.yml) 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>Incorporación de un dispositivo con un script local en Defender para empresas

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, **elija Configuración** endpoints y, a continuación, en  >  Administración **de dispositivos,** elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Incorporación de** un dispositivo , en la sección Método de implementación, elija **Script local**.  

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. Siga las instrucciones de los artículos siguientes:

   - Windows: incorporar [Windows dispositivos con un script local](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - dispositivos macOS: [implementación manual para Microsoft Defender para Endpoint en macOS](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Dispositivos Linux: [implementar Microsoft Defender para Endpoint en Linux manualmente](../defender-endpoint/linux-install-manually.md#client-configuration)

6. Continúe con [Ejecutar una prueba de detección](#run-a-detection-test) para Windows dispositivos.

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, consulte Solución de problemas de Microsoft Defender para empresas [(versión preliminar).](mdb-troubleshooting.yml)

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporar dispositivos con Microsoft Intune

Si ya usaste Microsoft Intune obtener Defender para empresas (versión preliminar), puedes usar Microsoft Intune para incorporar dispositivos. Para obtener ayuda con esto, consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Después de incorporar un dispositivo Windows manualmente, puedes ejecutar una prueba de detección para asegurarte de que todo funciona correctamente con Defender para empresas (versión preliminar).

1. En el Windows, cree una carpeta: `C:\test-MDATP-test` .

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

4. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Offboard a device**, en la sección **Método** de implementación, elija **Script local**. 

5. En la pantalla de confirmación, revise la información y, a continuación, elija **Descargar** para continuar.

6. Seleccione **Descargar paquete de offboarding**. Se recomienda guardar el paquete de offboarding en una unidad extraíble.

7. Ejecuta el script en cada dispositivo que quieras desactivar. 

   ¿Necesita ayuda con esta tarea? Vea los siguientes recursos:   

   - Windows: [offboard Windows dispositivos con un script local](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - dispositivos macOS: [desinstalación en macOS](../defender-endpoint/mac-resources.md#uninstalling)
   - Dispositivos Linux: [desinstalación en Linux](../defender-endpoint/linux-resources.md#uninstall)

> [!IMPORTANT]
> La salida de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas (versión preliminar). Sin embargo, los datos recibidos antes del offboarding se conservan durante un máximo de seis (6) meses.

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 5: Configurar las directivas y las opciones de seguridad en Microsoft Defender para empresas (versión preliminar)](mdb-configure-security-settings.md)

- [Introducción al uso de Microsoft Defender para empresas (versión preliminar)](mdb-get-started.md) 