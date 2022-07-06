---
title: Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles
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
description: Use las herramientas de Mobile Administración de dispositivos para implementar el paquete de configuración en los dispositivos de modo que se incorporen al servicio.
ms.openlocfilehash: d5c03c80c9a38d34ab27f888084604372874a64a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624209"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-mobile-device-management-tools"></a>Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

Puede usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos. La protección de la información de Microsoft 365 admite MDM proporcionando OMA-URIs para crear directivas para administrar dispositivos.


## <a name="before-you-begin"></a>Antes de empezar
Si usa Microsoft Intune, debe tener el dispositivo MDM inscrito. De lo contrario, la configuración no se aplicará correctamente. 

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulte [Inscripción de dispositivos (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporación de dispositivos mediante Microsoft Intune

Siga las instrucciones de [Intune](/mem/intune/protect/advanced-threat-protection-configure).
 
> [!NOTE]
> - La directiva **Estado de mantenimiento para dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard and monitor devices using Mobile Administración de dispositivos tools

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>.

2. En el panel de navegación, seleccione Configuración Device onboarding Offboarding (**Configuración:** > **incorporación de** >  dispositivos **fuera del panel de navegación**).

3. En el campo **Método de implementación**, seleccione **Mobile Administración de dispositivos/Microsoft Intune**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Use la Microsoft Intune directiva de configuración personalizada para implementar la siguiente configuración de OMA-URI compatible.

    ```text
    OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
    Date type: String
    Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]
    ```
> [!NOTE]
> Si Microsoft Defender para punto de conexión ya está configurado, puede **activar la incorporación de dispositivos** y ya no se requiere el paso 6.

> [!NOTE]
> La directiva **Estado de mantenimiento para dispositivos no incorporados** usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 mediante directiva de grupo](device-onboarding-gp.md)
- [Incorporación de dispositivos Windows 10 mediante Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](device-onboarding-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md)
- [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
