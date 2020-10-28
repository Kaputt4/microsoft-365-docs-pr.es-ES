---
title: Dispositivos de Windows 10 incorporados que usan un script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use un script local para implementar el paquete de configuración en dispositivos para que estén integrados en el servicio.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769516"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Dispositivos de Windows 10 incorporados que usan un script local

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

También puede incorporar dispositivos individuales de forma manual a la prevención de pérdida de datos de extremos de Microsoft 365. Es posible que desee hacerlo primero al probar el servicio antes de comprometerse a incorporar todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en un máximo de 10 dispositivos.
>
> Para implementar a escala, use [otras opciones de implementación](dlp-configure-endpoints.md). Por ejemplo, puede implementar un script de incorporación a más de 10 dispositivos en producción con el script disponible en dispositivos de [Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md).

## <a name="onboard-devices"></a>Dispositivos integrados
 
1.  Abra el archivo package. zip de configuración de GP ( *DeviceComplianceOnboardingPackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios. También puede obtener el paquete del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione incorporación de dispositivos de **configuración**  >  **Device onboarding** .

3. En el campo **método de implementación** , seleccione **script local** .

4. Haga clic en **Descargar paquete** y guarde el archivo. zip.
  
5. Extraiga el contenido del paquete de configuración en una ubicación del dispositivo que desee incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *DeviceOnboardingScript. cmd* .

6.  Abra un mensaje de la línea de comandos con privilegios elevados en el dispositivo y ejecute el script:

7.  Vaya a **Inicio** y escriba **cmd** .

8.  Haga clic con el botón secundario en **símbolo del sistema** y seleccione **Ejecutar como administrador** .

![Menú de inicio de ventana que apunta a ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Presione la tecla **entrar** o haga clic en **Aceptar** .

Para obtener información sobre cómo validar manualmente que el dispositivo es compatible y notifica correctamente los datos de los sensores, consulte [solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos desincorpora con un script local
Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó. Los paquetes de retirada expirados enviados a un dispositivo se rechazarán. Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.

1. Obtener el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione **configuración**  >  **dispositivo de descarga** .

3. En el campo **método de implementación** , seleccione **script local** .

4. Haga clic en **Descargar paquete** y guarde el archivo. zip.

5. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

6.  Abra un mensaje de la línea de comandos con privilegios elevados en el dispositivo y ejecute el script:

7.  Vaya a **Inicio** y escriba **cmd** .

8.  Haga clic con el botón secundario en **símbolo del sistema** y seleccione **Ejecutar como administrador** .

![Menú de inicio de ventana que apunta a ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*

10.  Presione la tecla **entrar** o haga clic en **Aceptar** .

> [!IMPORTANT]
> La descarga hace que el dispositivo deje de enviar datos del sensor al portal.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Puede seguir los diferentes pasos de comprobación de [solucionar problemas de incorporación] ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) para comprobar que el script se completó correctamente y que el agente se está ejecutando.

La supervisión también puede realizarse directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya al [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).

2. Elija los dispositivos de incorporación de dispositivos de **configuración**  >  **Device onboarding**  >  **Devices** .

3. Compruebe que aparecen dispositivos.


## <a name="related-topics"></a>Temas relacionados
- [Dispositivos de Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint](dlp-configure-endpoints-sccm.md)
- [Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo ATP de Microsoft defender recién integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
