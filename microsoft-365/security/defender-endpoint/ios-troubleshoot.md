---
title: Solución de problemas y búsqueda de respuestas en preguntas más frecuentes relacionadas con Microsoft Defender para punto de conexión en iOS
description: 'Solución de problemas y preguntas más frecuentes: Microsoft Defender para punto de conexión en iOS'
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, troubleshooting, faq, how to
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
ms.openlocfilehash: ae6e65d99a82bdf4a9c0adbb740c6e5b969f4b68
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016336"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Solucionar problemas y encontrar respuestas a preguntas más frecuentes sobre Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se proporciona información para solucionar problemas que pueden surgir al usar Microsoft Defender para punto de conexión en iOS.

> [!NOTE]
> Defender para punto de conexión en iOS usaría una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Las aplicaciones no funcionan cuando la VPN está activada
Hay algunas aplicaciones que dejan de funcionar cuando se detecta una VPN activa. Puede deshabilitar la VPN durante el tiempo que usa dichas aplicaciones.

De forma predeterminada, Defender para punto de conexión en iOS incluye y habilita la característica de protección web. La [protección web](web-protection-overview.md) ayuda a proteger los dispositivos frente a las amenazas web y a los usuarios frente a ataques de suplantación de identidad. Defender para punto de conexión en iOS usa una VPN para proporcionar esta protección. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran que deshabilite la VPN. Por ejemplo, quiere ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puede optar por deshabilitar la VPN directamente desde la aplicación Defender para punto de conexión o mediante los pasos siguientes:

1. En el dispositivo iOS, abra la aplicación **Configuración**, haga clic o pulse **general** y, a continuación, **VPN**.
1. Haga clic o pulse el botón "i" para Microsoft Defender para punto de conexión.
1. Desactive **Conectar a petición** para deshabilitar la VPN.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-vpn-config.png" alt-text="Opción Conectar a petición" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar La protección web, abra la aplicación Microsoft Defender para punto de conexión en el dispositivo y Habilite La protección web.

## <a name="coexistence-with-multiple-vpn-profiles"></a>Coexistencia con varios perfiles de VPN

Apple iOS no admite que varias VPN de todo el **dispositivo** estén activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez. Si necesita usar otra VPN en el dispositivo, puede deshabilitar la VPN de Defender para punto de conexión mientras usa la otra VPN.

## <a name="battery-consumption"></a>Consumo de batería

Para proporcionar protección en todo momento frente a amenazas basadas en web, Microsoft Defender para punto de conexión debe ejecutarse en segundo plano en todo momento. Esto podría dar lugar a un pequeño aumento en el consumo general de batería del dispositivo. En caso de que vea un drenaje significativo de la batería, [envíenos sus comentarios](ios-troubleshoot.md#send-in-app-feedback) e investigaremos.

Además, en la aplicación Configuración, iOS solo muestra el uso de batería de las aplicaciones que son visibles para el usuario durante un período de tiempo específico. El uso de la batería por parte de las aplicaciones que se muestra en la pantalla es solo durante ese tiempo y se calcula iOS en función de una gran variedad de factores, como el uso de CPU y red. Microsoft Defender para punto de conexión usa una VPN local o de bucle atrás en segundo plano para comprobar el tráfico web en busca de sitios web malintencionados o conexiones. Los paquetes de red de cualquier aplicación pasan por esta comprobación y esto hace que el uso de la batería de Microsoft Defender para punto de conexión se calcule inexactamente. El consumo real de batería de Microsoft Defender para punto de conexión es menor que lo que se muestra en la página De batería Configuración del dispositivo.

Tenga en cuenta que la VPN usada es una VPN local y, a diferencia de una VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

## <a name="data-usage"></a>Uso de datos

Microsoft Defender para punto de conexión usa una VPN local o de bucle invertido para comprobar el tráfico web de sitios web malintencionados o conexiones. Debido a esta razón, Microsoft Defender para punto de conexión uso de datos se puede tener en cuenta inexactamente. También hemos observado que si el dispositivo está solo en la red de telefonía móvil, el uso de datos notificado por el proveedor de servicios es muy cercano al consumo real, mientras que en la aplicación Configuración, los números pueden ser inexactos.

También tenemos observaciones similares con otros servicios VPN.

Además, es fundamental que Microsoft Defender para punto de conexión estén actualizados con nuestros servicios back-end para proporcionar una mejor protección.

## <a name="report-unsafe-site"></a>Informe de un sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza para obtener su información personal o financiera. Visite la página [Proporcionar comentarios sobre la protección de red](https://www.microsoft.com/wdsi/support/report-unsafe-site) para informar de un sitio web que podría ser un sitio de suplantación de identidad (phishing).

## <a name="malicious-site-detected"></a>Sitio malintencionado detectado

Microsoft Defender para punto de conexión le protege contra suplantación de identidad (phishing) u otros ataques basados en la web. Si se detecta un sitio malintencionado, la conexión se bloquea y se envía una alerta al portal de Microsoft 365 Defender de la organización. La alerta incluye el nombre de dominio de la conexión, la dirección IP remota y los detalles del dispositivo.

Además, se muestra una notificación en el dispositivo iOS. Al pulsar en la notificación, se abre la siguiente pantalla para que el usuario revise los detalles.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/ios-phish-alert.png" alt-text="El sitio notificado como notificación no segura" lightbox="images/ios-phish-alert.png":::

## <a name="device-not-seen-on-the-defender-for-endpoint-console-after-onboarding"></a>Dispositivo no visto en la consola de Defender para punto de conexión después de la incorporación

Después de la incorporación, el dispositivo tarda unas horas en aparecer en el inventario de dispositivos en la consola de seguridad de Defender para punto de conexión. Además, asegúrese de que el dispositivo está registrado correctamente con Azure Active Directory y que el dispositivo tiene conectividad a Internet. Para una incorporación correcta, el dispositivo debe registrarse a través de Microsoft Authenticator o Portal de empresa de Intune y el usuario debe iniciar sesión con la misma cuenta con la que el dispositivo está registrado con Azure AD.

> [!NOTE]
> A veces, el nombre del dispositivo no es coherente con el de Microsoft Endpoint Manager consola (Intune). El nombre del dispositivo en la consola de Defender para punto de conexión tiene el formato <username_iPhone o modelo de iPad>. También puede usar el identificador de dispositivo de Azure AD para identificar el dispositivo en la consola de Defender para punto de conexión.

## <a name="data-and-privacy"></a>Datos y privacidad

Para obtener más información sobre los datos recopilados y la privacidad, consulte [Información de privacidad: Microsoft Defender para punto de conexión en iOS](ios-privacy.md).

## <a name="connectivity-issue-on-cellular-network"></a>Problema de conectividad en la red de telefonía móvil

Si tiene problemas de conectividad a Internet en la red de telefonía móvil, compruebe si Microsoft Defender para punto de conexión tiene los datos móviles habilitados: Abra Configuración aplicación > MS Defender > asegúrese de que "Datos de telefonía móvil" está habilitado para MS Defender.

Si sigue teniendo problemas de conectividad, compruebe si activar o desactivar el modo avión ayuda a resolver el problema. Si el problema persiste, [envíenos registros](ios-troubleshoot.md#send-in-app-feedback).

## <a name="issues-on-supervised-devices-with-content-filter-profile-installed"></a>Problemas en dispositivos supervisados con el perfil de filtro de contenido instalado

Hay un problema en los dispositivos supervisados con el filtro de contenido de Defender para punto de conexión instalado. Si observa lentitud o latencia en la conectividad a Internet en estos dispositivos, desinstale o elimine el perfil de filtro de contenido del dispositivo. Estamos trabajando para resolver este problema y actualizaremos este lugar una vez que tengamos una resolución. 

## <a name="issues-during-app-updates-from-the-app-store"></a>Problemas durante las actualizaciones de la aplicación desde la tienda de aplicaciones

Si observas problemas cuando la aplicación se actualiza a través de la tienda de aplicaciones (actualizaciones automáticas o actualizaciones manuales), es posible que tengas que reiniciar el dispositivo. Si eso no resuelve el problema, puede deshabilitar la VPN de Defender y realizar la actualización de la aplicación. También puede proporcionar comentarios desde la aplicación para informar de este problema.

## <a name="send-in-app-feedback"></a>Enviar comentarios desde la aplicación

Si un usuario se enfrenta a un problema que aún no se ha solucionado en las secciones anteriores o no puede resolverse mediante los pasos enumerados, el usuario puede proporcionar comentarios desde la aplicación junto con datos de diagnóstico. A continuación, nuestro equipo investigará los registros para proporcionar la solución adecuada. Los usuarios pueden usar los pasos siguientes para enviar comentarios:

- Abra la aplicación MSDefender en el dispositivo iOS/iPadOS.
- Pulse en Menú (icono de perfil) en la esquina superior izquierda.
- Pulse **Enviar comentarios**.
- Elija entre las opciones especificadas. Para informar de un problema, seleccione **No me gusta algo**.
- Proporcione los detalles del problema al que se enfrenta y active **Enviar datos de diagnóstico**. Le recomendamos que incluya su dirección de correo electrónico para que el equipo pueda ponerse en contacto con usted para obtener una solución o un seguimiento.
- Pulse **Enviar** para enviar correctamente los comentarios.
