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
description: Usa las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en los dispositivos de modo que se incorpore al servicio.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769518"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

Puedes usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos. La prevención de pérdida de datos de puntos de conexión de Microsoft 365 admite MDM al OMA-URIs crear directivas para administrar dispositivos.


## <a name="before-you-begin"></a>Antes de empezar
Si usas Microsoft Intune, debes tener el dispositivo inscrito en MDM. De lo contrario, la configuración no se aplicará correctamente. 

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulta [Inscripción de dispositivos (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporar dispositivos con Microsoft Intune

Siga las instrucciones de [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)

> [!NOTE]
> - La **directiva Estado de mantenimiento de los dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Quitar y supervisar dispositivos con herramientas de administración de dispositivos móviles

Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de baja expirados enviados a un dispositivo. Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones impredecibles.

1. Obtenga el paquete de descarga del Centro [de cumplimiento de Microsoft.](https://compliance.microsoft.com/)

2. En el panel de navegación, selecciona **Configuración**  >  **de la incorporación de dispositivos.**  >  

3. En el **campo Método de** implementación, seleccione Administración de **dispositivos móviles / Microsoft Intune**.
    
4. Haga **clic en Descargar** paquete y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Usa la directiva de configuración personalizada de Microsoft Intune para implementar la siguiente configuración de OMA-URI compatible.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo de fecha: String      
      Valor: [Copiar y pegar el valor del contenido del archivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Para obtener más información sobre la configuración de directiva de Microsoft Intune, consulta la configuración de directiva de [Windows 10 en Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> La **directiva Estado de mantenimiento de los dispositivos** desactivados usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> La baja hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
