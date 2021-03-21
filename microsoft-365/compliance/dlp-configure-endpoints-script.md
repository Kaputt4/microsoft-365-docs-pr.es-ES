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
description: Use un script local para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917976"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Incorporar dispositivos Windows 10 mediante un script local

**Se aplica a:**

- [Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)

También puede incorporar manualmente dispositivos individuales a la prevención de pérdida de datos de puntos de conexión de Microsoft 365. Es posible que quieras hacerlo primero al probar el servicio antes de comprometerte a incorporar todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta 10 dispositivos.
>
> Para implementar a escala, use [otras opciones de implementación.](dlp-configure-endpoints.md) Por ejemplo, puedes implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en Incorporar dispositivos [Windows 10 mediante](dlp-configure-endpoints-gp.md)la directiva de grupo .

## <a name="onboard-devices"></a>Dispositivos integrados
 
1.  Abra el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione **Configuración Incorporación**  >  **de dispositivos**.

3. En el **campo Método de** implementación, seleccione Script **local**.

4. Haga **clic en Descargar paquete** y guarde el archivo .zip.
  
5. Extrae el contenido del paquete de configuración en una ubicación en el dispositivo que quieras incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *DeviceOnboardingScript.cmd*.

6.  Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

7.  Vaya a **Inicio** y escriba **cmd**.

8.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Presione la **tecla Entrar** o haga clic en **Aceptar**.

Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte Solucionar problemas de incorporación de Protección contra amenazas avanzada de [Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos offboard con un script local
Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtener el paquete de offboarding desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione **Configuración**  >  **Desaborde dispositivo**.

3. En el **campo Método de** implementación, seleccione Script **local**.

4. Haga **clic en Descargar paquete** y guarde el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6.  Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

7.  Vaya a **Inicio** y escriba **cmd**.

8.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Presione la **tecla Entrar** o haga clic en **Aceptar**.

> [!IMPORTANT]
> El offboarding hace que el dispositivo deje de enviar datos del sensor al portal.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Puede seguir los diferentes pasos de comprobación en [Solucionar problemas de incorporación](( para comprobar que el script se completó correctamente https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) y que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya al [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).

2. Elija **Configuración**  >  **Dispositivos de incorporación de**  >  **dispositivos**.

3. Compruebe que aparecen dispositivos.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 con la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo ATP de Microsoft Defender recién incorporado](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)