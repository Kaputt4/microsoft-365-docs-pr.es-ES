---
title: Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles
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
description: Use las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en dispositivos para que estén integrados en el servicio.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769518"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

Puede usar las soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos. La prevención de pérdida de datos de extremos de Microsoft 365 admite MDMs proporcionando OMA-URIs para crear directivas para administrar dispositivos.


## <a name="before-you-begin"></a>Antes de empezar
Si está usando Microsoft Intune, debe estar inscrito en MDM del dispositivo. De lo contrario, la configuración no se aplicará correctamente. 

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulte [Device Enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Dispositivos integrados con Microsoft Intune

Siga las instrucciones de [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

> [!NOTE]
> - El **Estado de mantenimiento de la Directiva de dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Desincorpora y supervisión de dispositivos con herramientas de administración de dispositivos móviles

Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó. Los paquetes de retirada expirados enviados a un dispositivo se rechazarán. Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.

1. Obtenga el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).

2. En el panel de navegación, seleccione **configuración** de la  >  **incorporación de dispositivos** de configuración  >  **Offboarding** .

3. En el campo **método de implementación** , seleccione Administración de **dispositivos móviles/Microsoft Intune** .
    
4. Haga clic en **Descargar paquete** y guarde el archivo. zip.

5. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que van a implementar el paquete. Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-mm-dd. de descarga* .

6. Use la Directiva de configuración personalizada de Microsoft Intune para implementar la siguiente configuración de OMA-URI admitida.

      OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo de datos: String      
      Valor: [copie y pegue el valor del contenido del archivo DeviceCompliance_valid_until_YYYY-MM-DD. de descarga]

Para obtener más información sobre la configuración de directiva de Microsoft Intune, consulte [configuración de la Directiva de Windows 10 en Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> El **Estado de mantenimiento de la Directiva de dispositivos de offboarded** usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a cualquier alerta que haya tenido, se conservará durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Dispositivos de Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint](dlp-configure-endpoints-sccm.md)
- [Dispositivos de Windows 10 incorporados que usan un script local](dlp-configure-endpoints-script.md)
- [Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
