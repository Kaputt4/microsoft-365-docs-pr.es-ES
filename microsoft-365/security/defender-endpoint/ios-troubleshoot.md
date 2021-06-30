---
title: Solucionar problemas y encontrar respuestas en preguntas frecuentes relacionadas con Microsoft Defender para endpoint en iOS
description: 'Solución de problemas y preguntas frecuentes: Microsoft Defender para endpoint en iOS'
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, troubleshoot, faq, how to
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194978"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Solucionar problemas y encontrar respuestas a preguntas frecuentes en Microsoft Defender para endpoint en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

En este tema se proporciona información de solución de problemas que le ayudará a solucionar los problemas que pueden surgir al usar Microsoft Defender para Endpoint en iOS.



> [!NOTE]
> Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Las aplicaciones no funcionan cuando la VPN está activada
Hay algunas aplicaciones que dejan de funcionar cuando se detecta una VPN activa. Puedes deshabilitar la VPN durante el tiempo que estás usando estas aplicaciones. 

De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web. [La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing. Defender para endpoint en iOS usa una VPN para proporcionar esta protección. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN. Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:

1. En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**
1. Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.
1. Desactiva la **Conectar a petición** para deshabilitar VPN.

    > [!div class="mx-imgBorder"]
    > ![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.

## <a name="co-existence-with-multiple-vpn-profiles"></a>Coexistencia con varios perfiles vpn

Apple iOS no admite varias VPN de todo **el** dispositivo para estar activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.

Microsoft Defender para endpoint VPN puede coexistir con otras VPN configuradas como *por aplicación* o *"Personal".*

## <a name="battery-consumption"></a>Consumo de batería

En la Configuración, iOS solo muestra el uso de batería de aplicaciones que son visibles para el usuario durante un período de tiempo específico. El uso de la batería por parte de las aplicaciones que se muestran en la pantalla es solo durante ese tiempo y lo calcula iOS en función de una gran variedad de factores, incluido el uso de la CPU y la red. Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas. Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente. El consumo real de batería de Microsoft Defender para Endpoint es mucho menor que lo que se muestra en la página Battery Configuración en el dispositivo.

En promedio, el uso de batería por día por parte de Microsoft Defender para endpoint que se ejecuta en segundo plano es aproximadamente el **8,81 %** de la batería total consumida en ese día. Apple informa de esta métrica en función del uso real de Microsoft Defender para Endpoint en dispositivos de usuario final y debido a los motivos mencionados anteriormente también se pueden tener en cuenta en otras aplicaciones que tienen actividad de red.

Además, la VPN usada es una VPN local y, a diferencia de una VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

## <a name="data-usage"></a>Uso de datos

Microsoft Defender para endpoint usa una VPN local/loopback para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas. Debido a este motivo, el uso de datos de Microsoft Defender para puntos de conexión puede tenerse en cuenta de forma inexacta. También hemos observado que si el dispositivo está solo en la red móvil, el uso de datos notificado por el proveedor de servicios es muy cercano al consumo real, mientras que en la aplicación Configuración, Apple muestra entre 1,5x y 2x de datos reales consumidos.

También tenemos observaciones similares con otros servicios VPN y hemos notificado esto a Apple.

Además, es fundamental que Microsoft Defender para Endpoint esté al día con nuestros servicios back-end para proporcionar una mejor protección. Sin embargo, estamos trabajando en optimizar el uso de datos por parte de Microsoft Defender para endpoint.

## <a name="report-unsafe-site"></a>Informe de sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visite la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red para informar de un sitio web que podría ser un sitio de suplantación de identidad.

## <a name="malicious-site-detected"></a>Sitio malintencionado detectado

Microsoft Defender para endpoint le protege contra la suplantación de identidad (phishing) u otros ataques basados en web. Si se detecta un sitio malintencionado, la conexión se bloquea y se envía una alerta al portal del Centro de seguridad de la organización. La alerta incluye el nombre de dominio de la conexión, la dirección IP remota y los detalles del dispositivo.

Además, se muestra una notificación en el dispositivo iOS. Al pulsar en la notificación se abre la siguiente pantalla para que el usuario revise los detalles.

> [!div class="mx-imgBorder"]
> ![Imagen del sitio notificado como notificación no segura](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Datos y privacidad

Para obtener más información acerca de los datos recopilados y la privacidad, consulte [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).

