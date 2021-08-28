---
title: Configurar Microsoft Defender para endpoint en características de iOS
description: Describe cómo implementar Microsoft Defender para endpoint en características de iOS.
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
ms.openlocfilehash: 3916217467892a46fd8a2534a7852b928d2b5215
ms.sourcegitcommit: d016e3bd30c0dd73c4cd3d804c0b6941b5eb3e87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2021
ms.locfileid: "58684093"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Configurar Microsoft Defender para endpoint en características de iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Acceso condicional con Defender para endpoint en iOS

Microsoft Defender para endpoint en iOS junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de la puntuación de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información acerca de cómo configurar el acceso condicional con Defender para endpoint en iOS, vea [Defender for Endpoint e Intune](/mem/intune/protect/advanced-threat-protection).

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Detección de jailbreak por Microsoft Defender para endpoint

Microsoft Defender para endpoint tiene la capacidad de detectar dispositivos administrados y no administrados que están liberados. Si se detecta que un dispositivo está liberado, se notifica una alerta de alto riesgo al Centro de seguridad y si el acceso condicional se configura en función de la puntuación de riesgo del dispositivo, se bloqueará el acceso al dispositivo a los datos corporativos.

## <a name="web-protection-and-vpn"></a>Protección web y VPN

De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web. [La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing. Defender para endpoint en iOS usa una VPN para proporcionar esta protección. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN. Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:

1. En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**
1. Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.
1. Desactiva la **Conectar a petición** para deshabilitar VPN.

    > [!div class="mx-imgBorder"]
    > ![Los config de VPN se conectan a petición.](images/ios-vpn-config.png)

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Coexistencia de varios perfiles vpn

Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Configurar Microsoft Defender para la señal de riesgo de extremo en la directiva de protección de aplicaciones (MAM)

Microsoft Defender para endpoint se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocidas como MAM) en iOS/iPadOS. Con esta funcionalidad, también puedes usar Microsoft Defender para Endpoint para proteger el acceso a datos corporativos desde dispositivos no inscritos.

Los pasos para configurar directivas de protección de aplicaciones con Microsoft Defender para endpoint son los siguientes:

1. Configure la conexión desde el espacio empresarial Microsoft Endpoint Manager a Microsoft Defender para Endpoint. En el Centro de administración  de [Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Conectores de administración de inquilinos y tokens de Microsoft Defender para Endpoint (en Plataforma cruzada) o Endpoint Security Microsoft Defender para Endpoint \>  \>   \>  (en Configuración) y active los alternancias en Directiva de protección de **aplicaciones Configuración para iOS**.
1. Seleccione Guardar. Debería ver que **el estado de** conexión ahora está establecido en **Habilitado**.
1. Crear directiva de protección de aplicaciones: una vez completada la configuración del conector de Microsoft Defender para puntos de conexión, vaya a **Directivas** de protección de aplicaciones \>  (en Directiva) para crear una nueva directiva o actualizar una existente.
1. Seleccione la plataforma, **Aplicaciones, Protección de datos, Configuración** de requisitos de Acceso que su organización requiere para la directiva.
1. En **Condiciones del** dispositivo de inicio \> **condicional,** encontrarás la configuración Nivel máximo de amenaza del dispositivo **permitido.** Esto tendrá que configurarse en Low, Medium, High o Secured. Las acciones disponibles serán Bloquear acceso **o** **Borrar datos**. Es posible que vea un cuadro de diálogo informativo para asegurarse de que el conector está configurado antes de que esta configuración suba a efecto. Si el conector ya está configurado, puede omitir este cuadro de diálogo.
1. Termina con Asignaciones y guarda la directiva.

Para obtener más información sobre mam o directiva de protección de aplicaciones, consulta configuración de la directiva de protección de aplicaciones [de iOS](/mem/intune/apps/app-protection-policy-settings-ios).

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementación de Microsoft Defender para endpoint para MAM o en dispositivos no inscritos

Microsoft Defender para endpoint en iOS habilita el escenario de directiva de protección de aplicaciones y está disponible en la Tienda de aplicaciones de Apple.

Los usuarios finales deben instalar la versión más reciente de la aplicación directamente desde la Tienda de aplicaciones de Apple.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configurar la directiva de cumplimiento en dispositivos con jailbreak

Para proteger los datos corporativos de acceso en dispositivos iOS con jailbreak, le recomendamos que configure la siguiente directiva de cumplimiento en Intune.

> [!NOTE]
> La detección de jailbreak es una funcionalidad proporcionada por Microsoft Defender para Endpoint en iOS. Sin embargo, se recomienda configurar esta directiva como una capa adicional de defensa frente a escenarios de jailbreak.

Siga los pasos siguientes para crear una directiva de cumplimiento contra dispositivos con jailbreak.

1. En [Microsoft Endpoint Manager de administración,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Directivas de** cumplimiento de  ->  **dispositivos** Crear  ->  **directiva**. Seleccione "iOS/iPadOS" como plataforma y haga clic **en Crear**.

    > [!div class="mx-imgBorder"]
    > ![Crear directiva.](images/ios-jb-policy.png)

2. Especifique un nombre de la directiva, por ejemplo, "Compliance Policy for Jailbreak".
3. En la página Configuración de cumplimiento, haga clic para expandir **la sección Estado del** dispositivo y haga clic en **Bloquear** para el **campo Dispositivos con jailbreak.**

    > [!div class="mx-imgBorder"]
    > ![Directiva Configuración.](images/ios-jb-settings.png)

4. En la **sección Acción por** incumplimiento, seleccione las acciones según sus requisitos y seleccione **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Acciones de directiva.](images/ios-jb-actions.png)

5. En la **sección Asignaciones,** seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, **seleccione Siguiente**.
6. En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados

Defender para endpoint en iOS permite a los administradores configurar indicadores personalizados en dispositivos iOS también. Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> Defender para endpoint en iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL/dominios.

## <a name="report-unsafe-site"></a>Informe de sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.
