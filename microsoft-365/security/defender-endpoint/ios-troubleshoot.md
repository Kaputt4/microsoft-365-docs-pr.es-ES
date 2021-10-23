---
title: Solucionar problemas y encontrar respuestas en preguntas frecuentes relacionadas con Microsoft Defender para endpoint en iOS
description: 'Solución de problemas y preguntas frecuentes: Microsoft Defender para endpoint en iOS'
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, troubleshoot, faq, how to
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fab35b6e40d03239d57329128505a31737904a64
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555805"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Solucionar problemas y encontrar respuestas a preguntas más frecuentes sobre Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se proporciona información de solución de problemas que le ayudará a solucionar los problemas que pueden surgir al usar Microsoft Defender para Endpoint en iOS.



> [!NOTE]
> Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Las aplicaciones no funcionan cuando la VPN está activada
Hay algunas aplicaciones que dejan de funcionar cuando se detecta una VPN activa. Puedes deshabilitar la VPN durante el tiempo que estás usando estas aplicaciones. 

De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web. [La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing. Defender para endpoint en iOS usa una VPN para proporcionar esta protección. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN. Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puedes optar por deshabilitar la VPN directamente desde la aplicación Defender for Endpoint o mediante los siguientes pasos:

1. En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**
1. Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.
1. Desactiva la **Conectar a petición** para deshabilitar VPN.

    > [!div class="mx-imgBorder"]
    > ![Los config de VPN se conectan a petición.](images/ios-vpn-config.png)

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar Web Protection, abra la aplicación Microsoft Defender para Endpoint en el dispositivo y Habilite La protección web.

## <a name="issues-with-device-health-card"></a>Problemas con la tarjeta de estado del dispositivo

Hay un problema conocido con la tarjeta de mantenimiento del dispositivo que puede provocar una notificación incorrecta para actualizar la versión de iOS aunque el usuario esté en la versión más reciente. Se recomienda a los usuarios que ignoren la notificación de Defender para endpoint. No hay ningún impacto en el cumplimiento del dispositivo debido a esto. Estamos trabajando para resolver este problema y actualizaremos este lugar una vez que disponen de una resolución.

## <a name="coexistence-with-multiple-vpn-profiles"></a>Coexistencia con varios perfiles vpn

Apple iOS no admite varias VPN de todo **el** dispositivo para estar activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez. Si necesitas usar otra VPN en el dispositivo, puedes deshabilitar Defender for Endpoint VPN mientras usas la otra VPN.

## <a name="battery-consumption"></a>Consumo de batería

Para proporcionar protección continua contra amenazas basadas en web, Microsoft Defender for Endpoint debe ejecutarse en segundo plano en todo momento. Esto puede provocar un aumento menor en el consumo de batería general del dispositivo.

Además, en la Configuración, iOS solo muestra el uso de batería de aplicaciones que son visibles para el usuario durante un período de tiempo específico. El uso de la batería por parte de las aplicaciones mostradas en la pantalla solo es durante ese tiempo y lo calcula iOS en función de una gran variedad de factores, incluido el uso de la CPU y la red. Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas. Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente. El consumo real de batería de Microsoft Defender para Endpoint es menor que lo que se muestra en la página De Configuración batería en el dispositivo.

En promedio, el uso de batería por día por parte de Microsoft Defender para endpoint que se ejecuta en segundo plano es aproximadamente el **8,81 %** de la batería total consumida en ese día. Apple informa de esta métrica en función del uso real de Microsoft Defender para Endpoint en dispositivos de usuario final y debido a los motivos mencionados anteriormente también se pueden tener en cuenta en otras aplicaciones que tienen actividad de red.

Además, la VPN usada es una VPN local y, a diferencia de una VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

## <a name="data-usage"></a>Uso de datos

Microsoft Defender para endpoint usa una VPN local/loopback para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas. Debido a este motivo, el uso de datos de Microsoft Defender para puntos de conexión puede tenerse en cuenta de forma inexacta. También hemos observado que si el dispositivo está solo en la red móvil, el uso de datos notificado por el proveedor de servicios es muy cercano al consumo real, mientras que en la aplicación Configuración, Apple muestra entre 1,5x y 2x de datos reales consumidos.

También tenemos observaciones similares con otros servicios VPN y hemos notificado esto a Apple.

Además, es fundamental que Microsoft Defender para Endpoint esté al día con nuestros servicios back-end para proporcionar una mejor protección. Sin embargo, estamos trabajando en optimizar el uso de datos por parte de Microsoft Defender para endpoint.

## <a name="report-unsafe-site"></a>Informe de sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza para obtener su información personal o financiera. Visite la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/support/report-unsafe-site) red para informar de un sitio web que podría ser un sitio de suplantación de identidad.

## <a name="malicious-site-detected"></a>Sitio malintencionado detectado

Microsoft Defender para endpoint le protege contra la suplantación de identidad (phishing) u otros ataques basados en web. Si se detecta un sitio malintencionado, la conexión se bloquea y se envía una alerta al portal del Centro de seguridad de la organización. La alerta incluye el nombre de dominio de la conexión, la dirección IP remota y los detalles del dispositivo.

Además, se muestra una notificación en el dispositivo iOS. Al pulsar en la notificación se abre la siguiente pantalla para que el usuario revise los detalles.

> [!div class="mx-imgBorder"]
> ![Imagen del sitio notificado como notificación no segura.](images/ios-phish-alert.png)

## <a name="device-not-seen-on-the-defender-for-endpoint-console-after-onboarding"></a>El dispositivo no se ve en la consola de Defender for Endpoint después de la incorporación.

Después de la incorporación, el dispositivo tarda unas horas en aparecer en el inventario de dispositivos en la consola de seguridad de Defender para endpoints. Además, asegúrate de que el dispositivo esté registrado correctamente con Azure Active Directory dispositivo tenga conectividad a Internet. Para una incorporación correcta, el dispositivo debe registrarse a través de Microsoft Authenticator o Portal de empresa de Intune y el usuario debe iniciar sesión con la misma cuenta con la que el dispositivo está registrado con Azure AD.

> [!NOTE]
> A veces, el nombre del dispositivo no es coherente con el de Microsoft Endpoint Manager (Intune). El nombre del dispositivo en la consola defender para endpoint tiene el formato <username_iPhone/iPad modelo>. También puedes usar el Azure AD de dispositivo para identificar el dispositivo en la consola de Defender para endpoint.

## <a name="data-and-privacy"></a>Datos y privacidad

Para obtener más información acerca de los datos recopilados y la privacidad, consulte [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).

## <a name="issues-on-supervised-devices-with-content-filter-profile-installed"></a>Problemas en dispositivos supervisados con el perfil de filtro de contenido instalado

Hay un problema en dispositivos supervisados con el filtro de contenido de Defender for Endpoint instalado. Si observa lentitud o latencia en la conectividad a Internet en estos dispositivos, desinstale o elimine el perfil de filtro de contenido del dispositivo. Estamos trabajando para resolver este problema y actualizaremos este lugar una vez que disponen de una resolución. 

## <a name="issues-during-app-updates-from-the-app-store"></a>Problemas durante las actualizaciones de aplicaciones de la tienda de aplicaciones

Si observas problemas cuando la aplicación se actualiza a través de la tienda de aplicaciones (ya sea actualizaciones automáticas o actualizaciones manuales), es posible que deba reiniciar el dispositivo. Si eso no resuelve el problema, puedes deshabilitar la VPN de Defender y realizar la actualización de la aplicación. También puedes proporcionar comentarios desde la aplicación para informar de este problema.

## <a name="send-in-app-feedback"></a>Enviar comentarios desde la aplicación

Si un usuario se enfrenta a un problema que aún no se ha tratado en las secciones anteriores o no puede resolver con los pasos enumerados, el usuario puede proporcionar comentarios desde la aplicación junto con los datos de diagnóstico. A continuación, nuestro equipo investigará los registros para proporcionar la solución adecuada. Los usuarios pueden usar los siguientes pasos para enviar comentarios:

  - Abre la aplicación MSDefender en el dispositivo iOS/iPadOS.
  - Pulsa en Menú (icono de perfil) en la esquina superior izquierda.
  - Pulsa **Enviar comentarios**.
  - Elija entre las opciones dadas. Para informar de un problema, seleccione **No me gusta nada**.
  - Proporcione detalles del problema al que se enfrenta y compruebe **Enviar datos de diagnóstico**. Le recomendamos que incluya su dirección de correo electrónico para que el equipo pueda ponerse en contacto con usted para obtener una solución o un seguimiento.
  - Pulsa **Enviar** para enviar correctamente los comentarios.



