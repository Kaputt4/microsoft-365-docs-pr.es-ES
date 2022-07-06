---
title: Incorporar dispositivos Windows 10 y Windows 11 mediante un script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Use un script local para implementar el paquete de configuración en los dispositivos de modo que se incorporen al servicio.
ms.openlocfilehash: 840573794b447162f917fed162bb1f869585286e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634431"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-a-local-script"></a>Incorporar dispositivos Windows 10 y Windows 11 mediante un script local

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

También puede incorporar manualmente dispositivos individuales a Microsoft 365. Es posible que quiera hacerlo primero al probar el servicio antes de confirmar la incorporación de todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta 10 dispositivos.
>
> Para realizar la implementación a escala, use [otras opciones de implementación](device-onboarding-overview.md). Por ejemplo, puede implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en [Incorporación de dispositivos Windows 10 mediante directiva de grupo](device-onboarding-gp.md).

## <a name="onboard-devices"></a>Incorporar dispositivos
 
1. Obtenga el paquete del archivo de .zip del paquete de configuración (*DeviceComplianceOnboardingPackage.zip*) de [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com)

2. En el panel de navegación, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración Incorporación**</a> > **de dispositivos**.

3. En el campo **Método de implementación** , seleccione **Script local**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.
  
5. Extraiga el contenido del paquete de configuración en una ubicación del dispositivo que desea incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *DeviceOnboardingScript.cmd*.

6. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

7. Vaya a **Inicio** y escriba **cmd**.

8. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

    ![Menú Inicio de la ventana que apunta a Ejecutar como administrador.](../media/dlp-run-as-admin.png)

9. Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10. Presione la tecla **Entrar** o haga clic en **Aceptar**.

Para obtener información sobre cómo puede validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos fuera del panel con un script local

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>.

2. En el panel de navegación, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración Desactivación**</a> > **del dispositivo**.

3. En el campo **Método de implementación** , seleccione **Script local**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los dispositivos. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

7. Vaya a **Inicio** y escriba **cmd**.

8. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

    ![Menú Inicio de la ventana que apunta a Ejecutar como administrador.](../media/dlp-run-as-admin.png)

9. Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10. Presione la tecla **Entrar** o haga clic en **Aceptar**.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal.

## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo

Puede seguir los diferentes pasos de comprobación de [Solución de problemas de incorporación]((/windows/security/threat-protection/microsoft-defender-atp/troubleshooting-onboarding) para comprobar que el script se completó correctamente y que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisión de dispositivos mediante el portal

1. Ve a [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).

2. Elija **Configuración Dispositivos** > **de incorporación de** > **dispositivos**.

1. Vaya a portal de cumplimiento Microsoft Purview y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración Dispositivos**</a> > **de incorporación de** > **dispositivos**.

1. Compruebe que aparecen los dispositivos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 y Windows 11 mediante directiva de grupo](device-onboarding-gp.md)
- [Incorporación de dispositivos Windows 10 y Windows 11 mediante Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md)
- [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
