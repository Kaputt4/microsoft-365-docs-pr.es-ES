---
title: Incorporar dispositivos a Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/16/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 073478300e6b5a9d5a9fc10e634f6e3113897fb3
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879245"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>Incorporar dispositivos a Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

La experiencia de incorporación de dispositivos en Defender para empresas se basa en los mismos procesos de incorporación de dispositivos que se usan en Microsoft Defender para endpoint. Vea el siguiente vídeo para ver cómo funciona:<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Con Microsoft Defender para empresas (versión preliminar), tienes varias opciones entre las que elegir para incorporar los dispositivos de tu organización. En este artículo se le guía por las opciones e incluye información general sobre cómo funciona la incorporación.

> [!TIP]
> Para ver información más detallada sobre la incorporación de dispositivos en Defender para endpoint, consulta Incorporación de dispositivos y [configuración de Microsoft Defender para las capacidades de endpoint](../defender-endpoint/onboard-configure.md).

## <a name="what-to-do"></a>Qué hacer

1. Consulta las opciones para [los dispositivos de incorporación](#device-onboarding-methods).

2. Incorporar un dispositivo mediante uno de los métodos siguientes:
    - [Incorporación automática para Windows dispositivos inscritos en Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
    - [Un script local para Windows, macOS y dispositivos Linux](#onboard-devices-using-a-local-script-in-defender-for-business)
    - [Microsoft Endpoint Manager para equipos, tabletas y teléfonos](#onboard-devices-using-microsoft-endpoint-manager)
    - [Directiva de grupo para Windows dispositivos](#onboard-windows-devices-using-group-policy)
    - [Otro método que no aparece aquí](#onboard-devices-using-a-method-not-listed-here)

3. [Ejecute una prueba de detección](#run-a-detection-test) para dispositivos Windows recién incorporados.

4. [Consulta los pasos siguientes](#next-steps). 

En este artículo también se incluye información sobre [la offboarding de un dispositivo](#offboarding-a-device).

## <a name="device-onboarding-methods"></a>Métodos de incorporación de dispositivos

En la tabla siguiente se describen los métodos más usados para incorporar dispositivos a Defender para empresas. 

| Método de incorporación  | Descripción  |
|---------|---------|
| **Incorporación automática**<br/>(*disponible para clientes que ya usan Microsoft Endpoint Manager*) | La incorporación automática configura una conexión entre Defender para empresas (versión preliminar) y Microsoft Endpoint Manager y, a continuación, incorpora Windows dispositivos a Defender para empresas (versión preliminar). Los dispositivos ya deben estar inscritos en Endpoint Manager.<br/><br/>Para obtener más información, consulta [Usar la incorporación automática para los Windows inscritos en Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager). |
| **Script local**<br/>(*recomendado durante la vista previa; útil para incorporar algunos dispositivos a la vez*)  | Puedes incorporar equipos a Defender para empresas (versión preliminar) mediante un script que descargues y ejecutes en dispositivos Windows, macOS o Linux. El script configura una confianza con Azure Active Directory e inscribe el dispositivo.<br/><br/>Para usar este método, consulta [Incorporar dispositivos con un script local en Defender para empresas](#onboard-devices-using-a-local-script-in-defender-for-business). |
| **Microsoft Intune** o **Microsoft Endpoint Manager**<br/>(*disponible para clientes que ya usan Microsoft Intune o Endpoint Manager*) | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) [y administración de](/mem/intune/enrollment/device-enrollment) dispositivos móviles forman parte de Endpoint Manager. Si ya usaste Endpoint Manager antes de obtener Defender para empresas (versión preliminar), puedes optar por seguir usando Endpoint Manager para incorporar y administrar dispositivos<br/><br/>Para usar este método, consulte [Onboard devices using Microsoft Endpoint Manager](#onboard-devices-using-microsoft-endpoint-manager). |
| **Directiva de grupo** | Si su organización ya usa la directiva de grupo, puede crear GPO y aplicarlos a los dispositivos de su organización en Defender para empresas (versión preliminar).<br/><br/>Para obtener más información sobre este método, consulta [Incorporación Windows dispositivos con directiva de grupo](#onboard-windows-devices-using-group-policy). | 

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, consulta Solución de problemas de [Microsoft Defender para empresas](mdb-troubleshooting.yml).

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>Incorporación automática para Windows dispositivos inscritos en Microsoft Endpoint Manager

La opción de incorporación automática solo se aplica Windows dispositivos. Esta opción está disponible si tu organización ya usaba Microsoft Endpoint Manager, Microsoft Intune o Administración de dispositivos móviles (MDM) en Microsoft Intune antes de obtener Defender para empresas (versión preliminar) y ya tienes dispositivos Windows inscritos Endpoint Manager. 

Si Windows dispositivos ya están inscritos en Endpoint Manager, Defender para empresas detectará esos dispositivos mientras se está configurando y configurando Defender para empresas. Se te preguntará si quieres usar la incorporación automática para todos o algunos de tus Windows dispositivos. 

El proceso de incorporación automática configura una conexión entre Defender para empresas y Endpoint Manager y, a continuación, incorpora dispositivos a Defender para empresas. Puedes elegir incorporar todos los dispositivos Windows inscritos a la vez o seleccionar un conjunto de dispositivos Windows que incorporar.

Para obtener más información, consulta el paso 3 en [Usar el asistente para configurar Microsoft Defender para empresas (versión preliminar).](mdb-use-wizard.md)

## <a name="onboard-devices-using-a-local-script-in-defender-for-business"></a>Incorporar dispositivos con un script local en Defender para empresas

Puedes usar un script local para incorporar dispositivos Windows, macOS y Linux a Defender para empresas. Cuando ejecutas el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory, lo inscribe en Microsoft Endpoint Manager y lo incorpora a Defender para empresas. Este método es útil para incorporar dispositivos en Defender para empresas y para incorporar algunos dispositivos a la vez.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Incorporación de** un dispositivo, en la sección  Método de implementación, elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. Siga las instrucciones de los artículos siguientes:

   - Windows: [incorporar Windows dispositivos con un script local](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - dispositivos macOS: [implementación manual para Microsoft Defender para Endpoint en macOS](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Dispositivos Linux: [implementar Microsoft Defender para Endpoint en Linux manualmente](../defender-endpoint/linux-install-manually.md#client-configuration)

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, consulta Solución de problemas de [Microsoft Defender para empresas (versión preliminar](mdb-troubleshooting.yml)).

## <a name="onboard-devices-using-microsoft-endpoint-manager"></a>Incorporar dispositivos con Microsoft Endpoint Manager

Si ya usaste Microsoft Intune obtener Defender para empresas (versión preliminar), puedes seguir usando Microsoft Intune para incorporar dispositivos. Con Endpoint Manager, puede incorporar equipos, tabletas y teléfonos. 

Consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-windows-devices-using-group-policy"></a>Incorporar dispositivos Windows mediante directiva de grupo

[La directiva de](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) grupo es una infraestructura que permite especificar configuraciones administradas para usuarios y equipos mediante la configuración de directiva de grupo y las preferencias de directiva de grupo. Un objeto de directiva de grupo (GPO) es un objeto lógico compuesto por un contenedor de directiva de grupo y una plantilla de directiva de grupo. 

Si tu organización ya usa la directiva de grupo para administrar dispositivos, puedes usar la directiva de grupo para incorporar dispositivos a Defender para empresas. Si es completamente nuevo en la directiva de grupo, se recomienda usar otro método, como Endpoint Manager un script local en su lugar. 

Consulta [Incorporación Windows dispositivos con directiva de grupo](../defender-endpoint/configure-endpoints-gp.md).

## <a name="onboard-devices-using-a-method-not-listed-here"></a>Incorporar dispositivos con un método que no aparece aquí

Si quieres usar otro método que no aparece en este artículo para incorporar dispositivos, consulta [Opciones de herramientas de incorporación y configuración](../defender-endpoint/onboard-configure.md#onboarding-and-configuration-tool-options).

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Después de incorporar dispositivos Windows a Defender para empresas (versión preliminar), puedes ejecutar una prueba de detección en un dispositivo Windows para asegurarte de que todo funciona correctamente.

1. En el Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="gradual-device-onboarding"></a>Incorporación gradual de dispositivos

Si quieres incorporar los dispositivos de la organización en fases, sigue estos pasos:

1. Identificar un conjunto de dispositivos que se incorporarán.

2. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

3. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

4. Seleccione un sistema operativo (como **Windows 10 y 11)** y, a continuación, elija un método de incorporación (como **script local**). Siga las instrucciones proporcionadas para el método seleccionado.

5. Repita este proceso para cada conjunto de dispositivos que desee incorporar. 

> [!TIP]
> No tienes que usar el mismo paquete de incorporación cada vez que incorpores dispositivos. Por ejemplo, puedes usar un script local para incorporar algunos dispositivos y, más adelante, puedes elegir otro método para incorporar más dispositivos.

## <a name="offboarding-a-device"></a>Offboarding a device

Si quieres salir de un dispositivo, sigue estos pasos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, **elija Configuración** y, a continuación, elija **Extremos**.

3. En **Administración de dispositivos**, elija **Offboarding**.

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