---
title: Incorporación de dispositivos Windows a Defender para punto de conexión mediante Intune
description: Use Microsoft Intune para implementar el paquete de configuración en los dispositivos de modo que se incorporen al servicio Defender para punto de conexión.
keywords: incorporación de dispositivos mediante mdm, administración de dispositivos, incorporación de dispositivos Microsoft Defender para punto de conexión, mdm
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 16da44ee7df41d3a239055360e71f320346a097d
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180283"
---
# <a name="onboard-windows-devices-to-defender-for-endpoint-using-intune"></a>Incorporación de dispositivos Windows a Defender para punto de conexión mediante Intune 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Puede usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos Windows 10. Defender para punto de conexión admite MDM proporcionando OMA-URIs para crear directivas para administrar dispositivos.

Para obtener más información sobre el uso de CSP de Defender para punto de conexión, vea [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) y [el archivo DDF WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos deben inscribirse con Intune como solución mobile Administración de dispositivos (MDM).

Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulte [Inscripción de dispositivos (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Incorporación de dispositivos mediante Microsoft Intune

Consulte el [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) o [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para punto de conexión.

Siga las instrucciones de [Intune](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune).


Para obtener más información sobre el uso de CSP de Defender para punto de conexión, vea [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) y [el archivo DDF WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).

> [!NOTE]
>
> - La directiva **Estado de mantenimiento para dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.
> - La configuración de la frecuencia de informes de datos de diagnóstico solo está disponible para los dispositivos en Windows 10, versión 1703.
> - La incorporación a Defender para punto de conexión incorporará el dispositivo a [la prevención de pérdida de datos (DLP),](../../compliance/endpoint-dlp-learn-about.md) que también forma parte del cumplimiento de Microsoft 365.


## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecución de una prueba de detección para comprobar la incorporación
Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).


## <a name="offboard-devices-using-mobile-device-management-tools"></a>Dispositivos fuera del panel con herramientas de mobile Administración de dispositivos

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:

   1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** \> Administración **de** \> **dispositivos Offboarding**.

   1. Seleccione Windows 10 o Windows 11 como sistema operativo.

   1. En el campo **Método de implementación**, seleccione **Mobile Administración de dispositivos/Microsoft Intune**.

   1. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.

3. Use la Microsoft Intune directiva de configuración personalizada para implementar la siguiente configuración de OMA-URI compatible.
   - OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - Tipo de fecha: String
   - Valor: [Copie y pegue el valor del contenido del archivo WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Para obtener más información sobre Microsoft Intune configuración de directivas, consulte [configuración de directivas de Windows 10 en Microsoft Intune](/mem/intune/configuration/custom-settings-windows-10).

> [!NOTE]
> La directiva **Estado de mantenimiento para dispositivos no incorporados** usa propiedades de solo lectura y no se puede corregir.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
