---
title: Configurar Microsoft Defender para endpoint en características de iOS
description: Describe cómo implementar Microsoft Defender para endpoint en características de iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: 834ce13917237dd822bdfbb7b88967dcac4bc0f8
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929018"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Configurar Microsoft Defender para endpoint en características de iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Acceso condicional con Defender para endpoint en iOS  
Microsoft Defender para endpoint en iOS junto con Microsoft Intune y Azure Active Directory permite aplicar directivas de cumplimiento de dispositivos y acceso condicional en función de los niveles de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información acerca de cómo configurar el acceso condicional con Defender para endpoint en iOS, vea [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="web-protection-and-vpn"></a>Protección web y VPN

De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web. [La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing. Defender para endpoint en iOS usa una VPN para proporcionar esta protección. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN. Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:

1. En el dispositivo iOS, abre la aplicación **Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**
1. Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.
1. Desactiva **Conectar a petición para** deshabilitar VPN.

    > [!div class="mx-imgBorder"]
    > ![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Coexistencia de varios perfiles vpn

Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configurar la directiva de cumplimiento en dispositivos con jailbreak

Para proteger los datos corporativos de acceso en dispositivos iOS con jailbreak, le recomendamos que configure la siguiente directiva de cumplimiento en Intune.

> [!NOTE]
> En este momento, Microsoft Defender para Endpoint en iOS no proporciona protección contra escenarios de jailbreak. Si se usa en un dispositivo con jailbreak, en escenarios específicos, los datos que usa la aplicación como el identificador de correo electrónico corporativo y la imagen de perfil corporativo (si está disponible) se pueden exponer localmente

Siga los pasos siguientes para crear una directiva de cumplimiento contra dispositivos con jailbreak.

1. En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Directivas **de** cumplimiento  ->  **de dispositivos** Crear  ->  **directiva**. Seleccione "iOS/iPadOS" como plataforma y haga clic **en Crear**.

    > [!div class="mx-imgBorder"]
    > ![Crear directiva](images/ios-jb-policy.png)

2. Especifique un nombre de la directiva, por ejemplo, "Compliance Policy for Jailbreak".
3. En la página Configuración de cumplimiento, haga clic para expandir **la sección Estado del** dispositivo y haga clic en **Bloquear** para el **campo Dispositivos con jailbreak.**

    > [!div class="mx-imgBorder"]
    > ![Configuración de directiva](images/ios-jb-settings.png)

4. En la *sección Acción por* incumplimiento, seleccione las acciones según sus requisitos y seleccione **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Acciones de directiva](images/ios-jb-actions.png)

5. En la *sección Asignaciones,* seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, **seleccione Siguiente**.
6. En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados

Defender para endpoint en iOS permite a los administradores configurar indicadores personalizados en dispositivos iOS también. Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> Defender para endpoint en iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL/dominios.

## <a name="report-unsafe-site"></a>Informe de sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>Problemas de consumo de batería en iOS cuando se instala Microsoft Defender para endpoint

Apple calcula el uso de la batería por parte de una aplicación en función de una gran variedad de factores, como el uso de la CPU y la red. Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas. Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente. Esto da una impresión falsa al usuario. El consumo real de batería de Microsoft Defender para Endpoint es menor que lo que se muestra en la página Configuración de la batería en el dispositivo. Esto se basa en pruebas realizadas en la aplicación Microsoft Defender para Endpoint para comprender el consumo de batería.

Además, la VPN usada es una VPN local y, a diferencia de las VPN tradicionales, el tráfico de red no se envía fuera del dispositivo.
