---
title: Configurar Microsoft Defender para punto de conexión en las características de iOS
description: Describe cómo implementar Microsoft Defender para punto de conexión en características de iOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, configure, features, ios
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
ms.openlocfilehash: 8defbb5d1a72afd13110d3c76a4770e40ac1c469
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089315"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Configurar Microsoft Defender para punto de conexión en las características de iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Defender para punto de conexión en iOS usaría una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Acceso condicional con Defender para punto de conexión en iOS

Microsoft Defender para punto de conexión en iOS junto con Microsoft Intune y Azure Active Directory permite aplicar las directivas de cumplimiento de dispositivos y acceso condicional en función de la puntuación de riesgo del dispositivo. Defender para punto de conexión es una solución de Mobile Threat Defense (MTD) que puede implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información sobre cómo configurar el acceso condicional con Defender para punto de conexión en iOS, consulte [Defender para punto de conexión y Intune](/mem/intune/protect/advanced-threat-protection).

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Detección de jailbreak por Microsoft Defender para punto de conexión

Microsoft Defender para punto de conexión tiene la capacidad de detectar dispositivos administrados y no administrados que están liberados. Si se detecta que un dispositivo está liberado, se notificará una alerta de **alto** riesgo al portal de Microsoft 365 Defender y, si se configura el acceso condicional en función de la puntuación de riesgo del dispositivo, se bloqueará el acceso al dispositivo de los datos corporativos.

## <a name="web-protection-and-vpn"></a>Protección web y VPN

De forma predeterminada, Defender para punto de conexión en iOS incluye y habilita la característica de protección web. La [protección web](web-protection-overview.md) ayuda a proteger los dispositivos frente a las amenazas web y a los usuarios frente a ataques de suplantación de identidad. Tenga en cuenta que los indicadores personalizados y anti-phishing (direcciones URL y IP) se admiten como parte de La protección web. El filtrado de contenido web no se admite actualmente en iOS.

Defender para punto de conexión en iOS usa una VPN para proporcionar esta funcionalidad. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran que deshabilite la VPN. Por ejemplo, quiere ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puede optar por deshabilitar la VPN de la aplicación en el dispositivo siguiendo estos pasos:

1. En el dispositivo iOS, abra la aplicación **Configuración**, haga clic o pulse **general** y, a continuación, **VPN**.

2. Haga clic o pulse el botón "i" para Microsoft Defender para punto de conexión.

3. Desactive **Conectar a petición** para deshabilitar la VPN. 

   :::image type="content" source="images/ios-vpn-config.png" alt-text="Botón de alternancia de la opción de configuración de VPN Conectar a petición" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar La protección web, abra la aplicación Microsoft Defender para punto de conexión en el dispositivo y haga clic o pulse **iniciar VPN**.

## <a name="configure-network-protection"></a>Configuración de la protección de red
>[!NOTE] 
>La protección de red en Microsoft Defender para punto de conexión está ahora en versión preliminar pública. La siguiente información se relaciona con la versión preliminar del producto que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

La protección de red en Microsoft Defender para punto de conexión está habilitada de forma predeterminada. Los administradores pueden usar los pasos siguientes para configurar la compatibilidad de MAM con la protección de red en dispositivos iOS.

1. En Microsoft Endpoint Manager Administración, vaya a Aplicaciones > Directivas de configuración de aplicaciones. Cree una nueva directiva de configuración de aplicaciones.
   :::image type="content" source="images/addiosconfig.png" alt-text="Agregue la directiva de configuración." lightbox="images/addiosconfig.png":::
   
2. Proporcione un nombre y una descripción para identificar de forma única la directiva. A continuación, haga clic en "Seleccionar aplicaciones públicas" y elija "Microsoft Defender" para Platform iOS/IPadOS :::image type="content" source="images/nameiosconfig.png" alt-text="Nombre de la configuración." lightbox="images/nameiosconfig.png":::
   
3. En Configuración página, agregue "DefenderNetworkProtectionEnable" como clave y valor como "false" para deshabilitar La protección de red. (La protección de red está habilitada de forma predeterminada) :::image type="content" source="images/addiosconfigvalue.png" alt-text="Agregue el valor de configuración." lightbox="images/addiosconfigvalue.png":::
   
4. Para otras configuraciones relacionadas con la protección de red, agregue las siguientes claves y el valor correspondiente correspondiente.

    |Key | Valor predeterminado (true-enable, false-disable)|Descripción|
    |---|---|---|
    |DefenderEndUserTrustFlowEnable| false | Permitir que los usuarios confíen en redes y certificados|
    |DefenderNetworkProtectionAutoRemediation| true |El administrador de TI usa esta configuración para habilitar o deshabilitar las alertas de corrección que se envían cuando un usuario realiza actividades de corrección, como cambiar a puntos de acceso WIFI más seguros o eliminar certificados sospechosos detectados por Defender.|
    |DefenderNetworkProtectionPrivacy| true |Esta configuración la administra el administrador de TI para habilitar o deshabilitar la privacidad en la protección de red.|
  
5. En la sección Asignaciones, el administrador puede elegir grupos de usuarios para incluir y excluir de la directiva.
   :::image type="content" source="images/assigniosconfig.png" alt-text="Asignar configuración." lightbox="images/assigniosconfig.png":::
   
6. Revise y cree la directiva de configuración.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Coexistencia de varios perfiles de VPN

Apple iOS no admite varias VPN de todo el dispositivo para que estén activas simultáneamente. Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Configuración de Microsoft Defender para punto de conexión señal de riesgo en la directiva de protección de aplicaciones (MAM)

Microsoft Defender para punto de conexión se puede configurar para enviar señales de amenaza que se usarán en directivas de protección de aplicaciones (APP, también conocidas como MAM) en iOS/iPadOS. Con esta funcionalidad, también puede usar Microsoft Defender para punto de conexión para proteger el acceso a datos corporativos de dispositivos no inscritos.

A continuación se indican los pasos para configurar directivas de protección de aplicaciones con Microsoft Defender para punto de conexión:

1. Configure la conexión desde el inquilino de Microsoft Endpoint Manager a Microsoft Defender para punto de conexión. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Conectores y tokens** \> de administración \> de **inquilinos** **Microsoft Defender para punto de conexión** (en Multiplataforma) o **Endpoint Security** \> **Microsoft Defender para punto de conexión**  (en Configuración) y activa los alternadores en Directiva de protección de aplicaciones **Configuración para iOS**.

2. Seleccione Guardar. Debería ver **que el estado de la conexión** ahora está establecido en **Habilitado**.

3. Crear directiva de protección de aplicaciones: una vez completada la configuración del conector de Microsoft Defender para punto de conexión, vaya a **Aplicaciones** \> **Protección de aplicaciones directivas** (en Directiva) para crear una nueva directiva o actualizar una existente.

4. Seleccione la plataforma, **Aplicaciones, Protección de datos,** Configuración de requisitos de acceso que su organización requiere para la directiva.

5. En **Condiciones del dispositivo** de **inicio** \> condicional, encontrará la configuración **Nivel máximo de amenaza de dispositivo permitido**. Esto tendrá que configurarse en Baja, Media, Alta o Protegida. Las acciones disponibles serán **Bloquear el acceso** o **Borrar datos**. Es posible que vea un cuadro de diálogo informativo para asegurarse de que tiene el conector configurado antes de que esta configuración surta efecto. Si el conector ya está configurado, puede omitir este cuadro de diálogo.

6. Termine con Asignaciones y guarde la directiva.

Para obtener más información sobre mam o directiva de protección de aplicaciones, consulte [iOS configuración de directivas de protección de aplicaciones](/mem/intune/apps/app-protection-policy-settings-ios).

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementación de Microsoft Defender para punto de conexión para MAM o en dispositivos no inscritos

Microsoft Defender para punto de conexión en iOS habilita el escenario directiva de protección de aplicaciones y está disponible en la Tienda de aplicaciones de Apple. Los usuarios finales deben instalar la versión más reciente de la aplicación directamente desde la tienda de aplicaciones de Apple.

## <a name="privacy-controls"></a>Controles de privacidad

> [!IMPORTANT]
> Los controles de privacidad para Microsoft Defender para punto de conexión en iOS están en versión preliminar. La siguiente información se refiere al producto preliminar que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

### <a name="configure-privacy-in-phish-alert-report"></a>Configuración de la privacidad en el informe de alertas de phish

Los clientes ahora pueden habilitar el control de privacidad para el informe de phish enviado por Microsoft Defender para punto de conexión en iOS. Esto garantizará que el nombre de dominio no se envíe como parte de la alerta de phish cada vez que Microsoft Defender para punto de conexión detecte y bloquee un sitio web de phish.

Siga estos pasos para habilitar la privacidad y no recopilar el nombre de dominio como parte del informe de alertas de phish.

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.

2. Asigne un nombre a la directiva, **Platform > iOS/iPadOS**, seleccione el tipo de perfil.

3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

4. En Configuración página, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeURLInReport** como tipo de clave y valor como **booleano**.

   - Para habilitar la privacidad y no recopilar el nombre de dominio, escriba el valor como `true` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `false`.

   - Para los usuarios con un conjunto de claves como `true`, la alerta de phish no contendrá la información del nombre de dominio cada vez que Defender para punto de conexión detecte y bloquee un sitio malintencionado.

5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configuración de la directiva de cumplimiento en dispositivos con jailbreak

Para proteger el acceso a los datos corporativos en dispositivos de iOS liberados, se recomienda configurar la siguiente directiva de cumplimiento en Intune.

> [!NOTE]
> La detección de jailbreak es una funcionalidad proporcionada por Microsoft Defender para punto de conexión en iOS. Sin embargo, se recomienda configurar esta directiva como una capa adicional de defensa frente a escenarios de jailbreak.

Siga los pasos siguientes para crear una directiva de cumplimiento en dispositivos con jailbreak.

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas****de cumplimiento** ->  de dispositivos  -> **Crear directiva**. Seleccione "iOS/iPadOS" como plataforma y haga clic en **Crear**.

   :::image type="content" source="images/ios-jb-policy.png" alt-text="Pestaña Crear directiva" lightbox="images/ios-jb-policy.png":::

1. Especifique un nombre de la directiva, por ejemplo, "Directiva de cumplimiento para Jailbreak".

1. En la página configuración de cumplimiento, haga clic para expandir la sección **Estado del dispositivo** y haga clic en **el campo Bloquear** para **dispositivos jailbreak** .

   :::image type="content" source="images/ios-jb-settings.png" alt-text="Pestaña Configuración de cumplimiento" lightbox="images/ios-jb-settings.png":::

1. En la sección **Acciones para no cumplimiento** , seleccione las acciones según sus requisitos y seleccione **Siguiente**.

   :::image type="content" source="images/ios-jb-actions.png" alt-text="Pestaña Acciones para no cumplimiento" lightbox="images/ios-jb-actions.png":::

1. En la sección **Asignaciones** , seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, seleccione **Siguiente**.

1. En la sección **Revisar y crear** , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

## <a name="configure-custom-indicators"></a>Configuración de indicadores personalizados

Defender para punto de conexión en iOS permite a los administradores configurar indicadores personalizados en iOS dispositivos también. Para obtener más información sobre cómo configurar indicadores personalizados, consulte [Administración de indicadores](/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> Defender para punto de conexión en iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL o dominios.

## <a name="configure-option-to-send-in-app-feedback"></a>Configuración de la opción para enviar comentarios desde la aplicación 

Los clientes ahora tienen la opción de configurar la capacidad de enviar datos de comentarios a Microsoft dentro de la aplicación Defender para punto de conexión. Los datos de comentarios ayudan a Microsoft a mejorar los productos y a solucionar problemas.

> [!NOTE]
> Para los clientes de la nube del Gobierno de EE. UU., la recopilación de datos de comentarios está **deshabilitada** de forma predeterminada. 

Siga estos pasos para configurar la opción para enviar datos de comentarios a Microsoft:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.

1. Asigne un nombre a la directiva, **Platform > iOS/iPadOS**, seleccione el tipo de perfil.

1. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

1. En Configuración página, seleccione **Usar diseñador de configuración** y agregue **DefenderSendFeedback** como tipo de clave y valor como **booleano**.
   
   - Para quitar la capacidad de los usuarios finales de proporcionar comentarios, establezca el valor como `false` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `true`. Para los clientes del Gobierno de EE. UU., el valor predeterminado se establece en "false".
   
   - Para los usuarios con el conjunto de claves como `true`, habrá una opción para enviar datos de comentarios a Microsoft dentro de la aplicación (Menú > Ayuda & Comentarios > Enviar comentarios a Microsoft)

1. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

## <a name="report-unsafe-site"></a>Informe de un sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visite la página [Proporcionar comentarios sobre la protección de red](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) si desea informar de un sitio web que podría ser un sitio de suplantación de identidad (phishing).
