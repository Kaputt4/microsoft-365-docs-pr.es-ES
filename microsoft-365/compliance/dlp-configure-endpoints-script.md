---
title: Incorporar dispositivos Windows 10 mediante un script local
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
description: Usa un script local para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769516"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Incorporar dispositivos Windows 10 mediante un script local

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

También puede incorporar manualmente dispositivos individuales a la prevención de pérdida de datos del punto de conexión de Microsoft 365. Es posible que quieras hacerlo primero al probar el servicio antes de confirmar la incorporación de todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta 10 dispositivos.
>
> Para implementar a escala, use [otras opciones de implementación.](dlp-configure-endpoints.md) Por ejemplo, puedes implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en incorporar dispositivos [Windows 10](dlp-configure-endpoints-gp.md)mediante la directiva de grupo.

## <a name="onboard-devices"></a>Incorporar dispositivos
 
1.  Abre el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargaste desde el Asistente para la incorporación de servicios. También puede obtener el paquete desde el Centro [de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, selecciona **Configuración de** incorporación  >  **de dispositivos.**

3. En el **campo Método de** implementación, seleccione Script **local**.

4. Haz **clic en Descargar paquete** y guarda el archivo .zip.
  
5. Extrae el contenido del paquete de configuración en una ubicación del dispositivo que quieras incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *DeviceOnboardingScript.cmd*.

6.  Abre un símbolo de la línea de comandos con privilegios elevados en el dispositivo y ejecuta el script:

7.  Vaya a **Inicio** y escriba **cmd**.

8.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si has copiado el archivo en el escritorio, escribe: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Presione la **tecla Entrar** o haga clic en **Aceptar.**

Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulta Solucionar problemas de incorporación de Protección contra amenazas avanzada [de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

## <a name="offboard-devices-using-a-local-script"></a>Quitar dispositivos con un script local
Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de baja expirados enviados a un dispositivo. Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones impredecibles.

1. Obtener el paquete de descarga del Centro [de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione **Configuración**  >  **de la baja del dispositivo.**

3. En el **campo Método de** implementación, seleccione Script **local**.

4. Haz **clic en Descargar paquete** y guarda el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los dispositivos. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6.  Abre un símbolo de la línea de comandos con privilegios elevados en el dispositivo y ejecuta el script:

7.  Vaya a **Inicio** y escriba **cmd**.

8.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Presione la **tecla Entrar** o haga clic en **Aceptar.**

> [!IMPORTANT]
> La baja hace que el dispositivo deje de enviar datos del sensor al portal.


## <a name="monitor-device-configuration"></a>Supervisar la configuración de dispositivos
Puede seguir los distintos pasos de comprobación en [Solucionar problemas de incorporación](( para comprobar que el script se completó correctamente y https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las diferentes herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos mediante el portal
1. Vaya al [Centro de cumplimiento de Microsoft 365.](https://compliance.microsoft.com)

2. Elija **Configuración**  >  **dispositivos de incorporación de**  >  **dispositivos.**

3. Comprueba que los dispositivos aparezcan.


## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo atp de Microsoft Defender recién incorporado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
