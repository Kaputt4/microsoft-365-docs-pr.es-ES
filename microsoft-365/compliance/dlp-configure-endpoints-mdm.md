---
title: Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles
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
description: Usa las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: 7c5efde45558f41da4331c33937526f36b777abf
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754320"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles

**Se aplica a:**

- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)

Puedes usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos. Microsoft 365 La prevención de pérdida de datos de puntos de conexión admite MDM proporcionando OMA-URIs para crear directivas para administrar dispositivos.


## <a name="before-you-begin"></a>Antes de empezar
Si estás usando Microsoft Intune, debes tener el dispositivo MDM inscrito. De lo contrario, la configuración no se aplicará correctamente. 

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulta [Inscripción de dispositivos (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporar dispositivos con Microsoft Intune

Siga las instrucciones de [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - La **directiva Estado de mantenimiento para dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard y supervisar dispositivos con herramientas de administración de dispositivos móviles

Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtener el paquete de offboarding de la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>.

2. En el panel de navegación, **seleccione Configuración** Incorporación  >  **de**  >  **dispositivos offboarding**.

3. En el **campo Método de** implementación, seleccione Administración de **dispositivos móviles / Microsoft Intune**.

4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

5. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Use la Microsoft Intune de configuración personalizada para implementar la siguiente configuración de OMA-URI compatible.

    ```text
    OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
    Date type: String
    Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]
    ```

Para obtener más información sobre Microsoft Intune configuración de directiva, [consulte Windows 10 configuración de directiva en Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> La **directiva Estado de mantenimiento para dispositivos fuera deborde** usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Incorporación Windows 10 dispositivos con directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)