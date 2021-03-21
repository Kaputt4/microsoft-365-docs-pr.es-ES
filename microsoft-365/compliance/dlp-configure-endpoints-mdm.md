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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917996"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles

**Se aplica a:**

- [Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)

Puedes usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos. Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.


## <a name="before-you-begin"></a>Antes de empezar
Si usas Microsoft Intune, debes tener el dispositivo MDM inscrito. De lo contrario, la configuración no se aplicará correctamente. 

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulta [Inscripción de dispositivos (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporación de dispositivos con Microsoft Intune

Siga las instrucciones de [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - La **directiva Estado de mantenimiento para dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard y supervisar dispositivos con herramientas de administración de dispositivos móviles

Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtenga el paquete de offboarding del [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).

2. En el panel de navegación, seleccione **Configuración**  >  **La incorporación de**  >  **dispositivos fuera del panel de navegación**.

3. En el **campo Método de** implementación, seleccione Administración de **dispositivos móviles / Microsoft Intune**.
    
4. Haga **clic en Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Use la directiva de configuración personalizada de Microsoft Intune para implementar la siguiente configuración de OMA-URI compatible.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo de fecha: String      
      Valor: [Copiar y pegar el valor del contenido del archivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Para obtener más información sobre la configuración de directivas de Microsoft Intune, vea Configuración de directivas de [Windows 10 en Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> La **directiva Estado de mantenimiento para dispositivos fuera deborde** usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 con la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)