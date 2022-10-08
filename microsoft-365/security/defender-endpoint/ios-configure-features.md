---
title: Configurar Microsoft Defender para punto de conexión en las características de iOS
description: Describe cómo implementar Microsoft Defender para punto de conexión en características de iOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, configure, features, ios
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: c1d909699cdcbf993351a5232f2b12cbf84b5ca1
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222922"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Configurar Microsoft Defender para punto de conexión en las características de iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Defender para punto de conexión en iOS usaría una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Acceso condicional con Defender para punto de conexión en iOS

Microsoft Defender para punto de conexión en iOS, junto con Microsoft Intune y Azure Active Directory, permite aplicar las directivas de cumplimiento de dispositivos y acceso condicional en función de la puntuación de riesgo del dispositivo. Defender para punto de conexión es una solución de Mobile Threat Defense (MTD) que puede implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información sobre cómo configurar el acceso condicional con Defender para punto de conexión en iOS, consulte [Defender para punto de conexión y Intune](/mem/intune/protect/advanced-threat-protection).

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Detección de jailbreak por Microsoft Defender para punto de conexión

Microsoft Defender para punto de conexión tiene la capacidad de detectar dispositivos administrados y no administrados que están liberados. Si se detecta que un dispositivo está liberado, se notificará una alerta de **alto** riesgo al portal de Microsoft 365 Defender y, si el acceso condicional está configurado en función de la puntuación de riesgo del dispositivo, se bloqueará el acceso al dispositivo de los datos corporativos.

## <a name="web-protection-and-vpn"></a>Protección web y VPN

De forma predeterminada, Defender para punto de conexión en iOS incluye y habilita la característica de protección web. La [protección web](web-protection-overview.md) ayuda a proteger los dispositivos frente a las amenazas web y a los usuarios frente a ataques de suplantación de identidad. Tenga en cuenta que los indicadores personalizados y anti-phishing (direcciones URL y IP) se admiten como parte de La protección web. Actualmente, el filtrado de contenido web no se admite en plataformas móviles.

Defender para punto de conexión en iOS usa una VPN para proporcionar esta funcionalidad. Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.

Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran que deshabilite la VPN. Por ejemplo, quiere ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN. En tales casos, puede optar por deshabilitar la VPN de la aplicación en el dispositivo siguiendo estos pasos:

1. En el dispositivo iOS, abra la aplicación **Configuración** , haga clic o pulse en **General** y, a continuación, **vpn**.

2. Haga clic o pulse el botón "i" para Microsoft Defender para punto de conexión.

3. Desactive **Conectar a petición** para deshabilitar vpn. 

   :::image type="content" source="images/ios-vpn-config.png" alt-text="Botón de alternancia de la opción Conectar a petición de configuración de VPN" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> La protección web no estará disponible cuando la VPN esté deshabilitada. Para volver a habilitar La protección web, abra la aplicación Microsoft Defender para punto de conexión en el dispositivo y haga clic o pulse **iniciar VPN**.

## <a name="disable-web-protection"></a>Deshabilitar la protección web

Web Protection es una de las características clave de Defender para punto de conexión y requiere una VPN para proporcionar esa funcionalidad. La VPN usada es una VPN local o de bucle invertido y no una VPN tradicional, pero hay varias razones por las que es posible que los clientes no prefieran la VPN. Los clientes que no quieren configurar una VPN, hay una opción para deshabilitar **La protección web** e implementar Defender para punto de conexión sin esa característica. Otras características de Defender para punto de conexión seguirán funcionando.

Esta configuración está disponible tanto para los dispositivos inscritos (MDM) como para los dispositivos no inscritos (MAM). Para los clientes con MDM, los administradores pueden configurar la **protección web** a través de dispositivos administrados en app config. Para los clientes sin inscripción, mediante MAM, los administradores pueden configurar la **protección web** mediante aplicaciones administradas en app config.

### <a name="configure-web-protection"></a>Configuración de La protección web

1. **Deshabilitar protección web (MDM)** Siga estos pasos para deshabilitar **La protección web** para dispositivos inscritos.

    - En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.
    - Asigne un nombre a la directiva, **Platform > iOS/iPadOS**.
    - Seleccione Microsoft Defender para punto de conexión como la aplicación de destino.
    - En la página Configuración, seleccione Usar diseñador de configuración y agregue **WebProtection** como tipo de clave y valor como **booleano**.
        - De forma predeterminada, **WebProtection= true**.
        - Administración debe hacer **webProtection = false** para desactivar la protección web.
        - Defender enviará el latido al portal de Microsoft 365 Defender cada vez que el usuario abra la aplicación.
        - Haga clic en Siguiente y asigne este perfil a los dispositivos o usuarios de destino.

1. **Deshabilitar protección web (MAM)** Siga estos pasos para deshabilitar **La protección web** para dispositivos no inscritos.

    - En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **aplicaciones administradas**.
    - Asignar a la directiva un nombre.
    - En Seleccionar aplicaciones públicas, elija Microsoft Defender para punto de conexión como aplicación de destino.
    - En la página Configuración, en Configuración general, agregue **WebProtection** como la clave y el valor como **false**.
        - De forma predeterminada, **WebProtection= true**.
        - Administración debe hacer **webProtection = false** para desactivar la protección web.
        - Defender enviará el latido al portal de Microsoft 365 Defender cada vez que el usuario abra la aplicación.
        - Haga clic en Siguiente y asigne este perfil a los dispositivos o usuarios de destino.

## <a name="configure-network-protection"></a>Configuración de la protección de red

>[!NOTE]
>La protección de red en Microsoft Defender para punto de conexión está ahora en versión preliminar pública. La siguiente información se relaciona con la versión preliminar del producto que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

La protección de red en Microsoft Defender para el punto de conexión está habilitada de forma predeterminada. Los administradores pueden usar los pasos siguientes para configurar la compatibilidad de MAM con la protección de red en dispositivos iOS.

1. En Microsoft Endpoint Manager Administración, vaya a Aplicaciones > Directivas de configuración de aplicaciones. Cree una nueva directiva de configuración de aplicaciones.
   :::image type="content" source="images/addiosconfig.png" alt-text="Agregue la directiva de configuración." lightbox="images/addiosconfig.png":::

2. Proporcione un nombre y una descripción para identificar de forma única la directiva. A continuación, haga clic en "Seleccionar aplicaciones públicas" y elija "Microsoft Defender" para Platform iOS/IPadOS :::image type="content" source="images/nameiosconfig.png" alt-text="Name the configuration (Nombre de iOS/IPadOS de la plataforma)." lightbox="images/nameiosconfig.png":::

3. En la página Configuración, agregue "DefenderNetworkProtectionEnable" como clave y valor como "false" para deshabilitar La protección de red. (La protección de red está habilitada de forma predeterminada) :::image type="content" source="images/addiosconfigvalue.png" alt-text="Agregue el valor de configuración." lightbox="images/addiosconfigvalue.png":::

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

1. Configure la conexión desde el inquilino de Microsoft Endpoint Manager a Microsoft Defender para punto de conexión. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Conectores y tokens** \> de administración \> de **inquilinos** **Microsoft Defender para punto de conexión** (en Multiplataforma) o **Endpoint Security** \> **Microsoft Defender para punto de conexión**  (en Configuración) y activa los alternadores en Configuración de directivas **de Protección de aplicaciones para iOS**.

2. Seleccione Guardar. Debería ver **que el estado de la conexión** ahora está establecido en **Habilitado**.

3. Crear directiva de protección de aplicaciones: una vez completada la configuración del conector de Microsoft Defender para punto de conexión, vaya a **Aplicaciones** \> **Protección de aplicaciones directivas** (en Directiva) para crear una nueva directiva o actualizar una existente.

4. Seleccione la plataforma, **Aplicaciones, Protección de datos,** Configuración de requisitos de acceso que su organización requiere para la directiva.

5. En **Condiciones del dispositivo** de **inicio** \> condicional, encontrará la configuración **Nivel máximo de amenaza de dispositivo permitido**. Esto tendrá que configurarse en Baja, Media, Alta o Protegida. Las acciones disponibles serán **Bloquear el acceso** o **Borrar datos**. Es posible que vea un cuadro de diálogo informativo para asegurarse de que tiene el conector configurado antes de que esta configuración surta efecto. Si el conector ya está configurado, puede omitir este cuadro de diálogo.

6. Termine con Asignaciones y guarde la directiva.

Para obtener más información sobre mam o directiva de protección de aplicaciones, consulte configuración de directivas de [protección de aplicaciones de iOS](/mem/intune/apps/app-protection-policy-settings-ios).

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementación de Microsoft Defender para punto de conexión para MAM o en dispositivos no inscritos

Microsoft Defender para punto de conexión en iOS habilita el escenario de directiva de protección de aplicaciones y está disponible en la tienda de aplicaciones de Apple. Los usuarios finales deben instalar la versión más reciente de la aplicación directamente desde la tienda de aplicaciones de Apple.

## <a name="privacy-controls"></a>Controles de privacidad

Microsoft Defender para punto de conexión en iOS habilita los controles de privacidad tanto para los administradores como para los usuarios finales. Esto incluye los controles para dispositivos inscritos (MDM) y no inscritos (MAM).
Para los clientes con MDM, los administradores pueden configurar los controles de privacidad a través de dispositivos administrados en la configuración de la aplicación. En el caso de los clientes sin inscripción, con MAM, los administradores pueden configurar los controles de privacidad a través de aplicaciones administradas en la configuración de la aplicación. Los usuarios finales también tendrán la capacidad de configurar la configuración de privacidad desde la configuración de la aplicación Defender.

### <a name="configure-privacy-in-phish-alert-report"></a>Configuración de la privacidad en el informe de alertas de phish

Los clientes ahora pueden habilitar el control de privacidad para el informe de phish enviado por Microsoft Defender para punto de conexión en iOS. Esto garantizará que el nombre de dominio no se envíe como parte de la alerta de phish cada vez que Microsoft Defender para punto de conexión detecte y bloquee un sitio web de phish.

1. **Administración Controles de privacidad (MDM)** Siga estos pasos para habilitar la privacidad y no recopilar el nombre de dominio como parte del informe de alertas de phish para dispositivos inscritos.

    - En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.

    - Asigne un nombre a la directiva, **Platform > iOS/iPadOS**, seleccione el tipo de perfil.

    - Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

    - En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeURLInReport** como tipo de clave y valor como **booleano**.

      - Para habilitar la privacidad y no recopilar el nombre de dominio, escriba el valor como `true` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `false`.

      - Para los usuarios con un conjunto de claves como `true`, la alerta de phish no contendrá la información del nombre de dominio cada vez que Defender para punto de conexión detecte y bloquee un sitio malintencionado.

    - Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

1. **Administración Controles de privacidad (MAM)** Siga estos pasos para habilitar la privacidad y no recopilar el nombre de dominio como parte del informe de alertas de phish para dispositivos no inscritos.

    - En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **aplicaciones administradas**.

    - Asignar a la directiva un nombre.

    - En Seleccionar aplicaciones públicas, elija **Microsoft Defender para punto de conexión** como la aplicación de destino.

    - En la página Configuración, en  **Configuración general** , agregue **DefenderExcludeURLInReport** como clave y valor como **true**.

      - Para habilitar la privacidad y no recopilar el nombre de dominio, escriba el valor como `true` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `false`.

      - Para los usuarios con un conjunto de claves como `true`, la alerta de phish no contendrá la información del nombre de dominio cada vez que Defender para punto de conexión detecte y bloquee un sitio malintencionado.

    - Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

1. **Controles de privacidad del usuario final** Estos controles ayudan al usuario final a configurar la información compartida con su organización.
    - En el caso de los dispositivos supervisados, los controles de usuario final no estarán visibles. Administración decidirá y controlará la configuración.
    - Sin embargo, en el caso de los dispositivos no supervisados, el control se mostrará en **Configuración > Privacidad**.
        - Los usuarios verán un botón de alternancia para **Información de sitio no segura**.
        - Este botón de alternancia solo es visible si Administración ha establecido **DefenderExcludeURLInReport = true**
        - Si se habilita mediante Administración, los usuarios pueden decidir si quieren enviar la información del sitio no seguro a su organización o no.
        - De forma predeterminada, se `true`enviará la información de sitio no segura.
        - Si el usuario lo cambia a `false`, no se enviarán los detalles del sitio no seguro.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="optional-permissions"></a>Permisos opcionales

Microsoft Defender para punto de conexión en iOS habilita **permisos opcionales** en el flujo de incorporación. Actualmente, los permisos necesarios para Defender para punto de conexión son obligatorios en el flujo de incorporación. Con esta característica, los administradores pueden implementar Defender para punto de conexión en dispositivos BYOD sin aplicar el **permiso DE VPN** obligatorio durante la incorporación. Los usuarios finales pueden incorporar la aplicación sin los permisos obligatorios y pueden revisarlos más adelante. Esta característica solo está presente actualmente para dispositivos inscritos (MDM).

### <a name="configure-optional-permission"></a>Configurar permiso opcional

1. **flujo de Administración (MDM)** Siga estos pasos para habilitar el permiso **VPN opcional** para los dispositivos inscritos.

    - En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.

    - Asigne un nombre a la directiva y seleccione **Platform > iOS/iPadOS**.

    - Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

    - En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderOptionalVPN** como tipo de clave y valor como **booleano**.

      - Para habilitar el permiso VPN opcional, escriba el valor como `true` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `false`.
      - Para los usuarios con un conjunto de claves como `true`, los usuarios podrán incorporar la aplicación sin conceder permiso de VPN.

    - Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.
1. **Flujo de usuario final** : el usuario instalará y abrirá la aplicación para iniciar la incorporación.
    - Si el administrador tiene la configuración Permisos opcionales, el usuario puede **omitir** el permiso VPN y completar la incorporación.
    - Incluso si el usuario ha omitido la VPN, el dispositivo podrá incorporarse y se enviará el latido.
    - Puesto que `VPN` está deshabilitado, `Web Protection` no estará activo.
    - Más adelante, el usuario puede habilitar desde `Web Protection` dentro de la aplicación. Esto instalará la configuración de VPN en el dispositivo.

> [!NOTE]
>**El permiso opcional** es diferente de **Deshabilitar protección web**. El permiso VPN opcional solo ayuda a omitir el permiso durante la incorporación, pero está disponible para que el usuario final lo revise y lo habilite más adelante. Mientras **que Deshabilitar Protección web** permite a los usuarios incorporar la aplicación Defender para punto de conexión sin La protección web. No se puede habilitar más adelante.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configuración de la directiva de cumplimiento en dispositivos con jailbreak

Para proteger el acceso a los datos corporativos en dispositivos iOS con jailbreak, se recomienda configurar la siguiente directiva de cumplimiento en Intune.

> [!NOTE]
> La detección de jailbreak es una funcionalidad proporcionada por Microsoft Defender para punto de conexión en iOS. Sin embargo, se recomienda configurar esta directiva como una capa adicional de defensa frente a escenarios de jailbreak.

Siga los pasos siguientes para crear una directiva de cumplimiento en dispositivos con jailbreak.

1. En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Directivas****de cumplimiento** >  de dispositivos  > **Crear directiva**. Seleccione "iOS/iPadOS" como plataforma y haga clic en **Crear**.

   :::image type="content" source="images/ios-jb-policy.png" alt-text="Pestaña Crear directiva" lightbox="images/ios-jb-policy.png":::

1. Especifique un nombre de la directiva, por ejemplo, "Directiva de cumplimiento para Jailbreak".

1. En la página configuración de cumplimiento, haga clic para expandir la sección **Estado del dispositivo** y haga clic en **el campo Bloquear** para **dispositivos jailbreak** .

   :::image type="content" source="images/ios-jb-settings.png" alt-text="Pestaña Configuración de cumplimiento" lightbox="images/ios-jb-settings.png":::

1. En la sección **Acciones para no cumplimiento** , seleccione las acciones según sus requisitos y seleccione **Siguiente**.

   :::image type="content" source="images/ios-jb-actions.png" alt-text="Pestaña Acciones para no cumplimiento" lightbox="images/ios-jb-actions.png":::

1. En la sección **Asignaciones** , seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, seleccione **Siguiente**.

1. En la sección **Revisar y crear** , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

## <a name="configure-custom-indicators"></a>Configuración de indicadores personalizados

Defender para punto de conexión en iOS permite a los administradores configurar indicadores personalizados también en dispositivos iOS. Para obtener más información sobre cómo configurar indicadores personalizados, consulte [Administración de indicadores](/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> Defender para punto de conexión en iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL o dominios.

## <a name="configure-vulnerability-assessment-of-apps"></a>Configuración de la evaluación de vulnerabilidades de las aplicaciones

>[!Note]
>La evaluación de vulnerabilidades de las aplicaciones en Microsoft Defender para punto de conexión para iOS está ahora en versión preliminar pública. La siguiente información se refiere a la versión preliminar del producto que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona. Si está interesado en participar en la versión preliminar, comparta su nombre de inquilino e id. con nosotros en **mdatpmobile@microsoft.com**.

Defender para punto de conexión en iOS admite evaluaciones de vulnerabilidades de aplicaciones solo para dispositivos inscritos (MDM).

Los administradores pueden usar los pasos siguientes para configurar la evaluación de vulnerabilidades de las aplicaciones.

### <a name="on-a-supervised-device"></a>En un dispositivo supervisado

1. Asegúrese de que el dispositivo está configurado en [modo supervisado](ios-install.md#complete-deployment-for-supervised-devices).
1. Para habilitar la característica en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Seguridad** >  de punto de conexión **Microsoft Defender para punto de conexión** >  **Incronizar aplicaciones para dispositivos iOS/iPadOS**.

     :::image type="content" source="images/tvm-app-sync-toggle.png" alt-text="Alternancia de sincronización de aplicacionesSup" lightbox="images/tvm-app-sync-toggle.png":::

### <a name="on-an-unsupervised-device"></a>En un dispositivo sin supervisión

1. Para habilitar la característica en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Seguridad** >  de punto de conexión **Microsoft Defender para punto de conexión** >  **Incronizar aplicaciones para dispositivos iOS/iPadOS**.

   :::image type="content" source="images/tvm-app-sync-toggle.png" alt-text="Alternancia de sincronización de aplicaciones" lightbox="images/tvm-app-sync-toggle.png":::

1. Para obtener la lista de todas las aplicaciones, incluidas las aplicaciones no administradas, habilite el botón de alternancia **Enviar datos de inventario de aplicaciones completos en dispositivos del sistema operativo iOS/iPad de propiedad personal**.

    :::image type="content" source="images/tvm-full-app-data.png" alt-text="Datos completos de la aplicación" lightbox="images/tvm-full-app-data.png":::

1. Siga estos pasos para configurar la configuración de privacidad.
    - Vaya a **Aplicaciones Directivas** > **de configuración de aplicaciones** > **Agregar** > **dispositivos administrados**.
    - Asigne un nombre a la directiva, **Platform** > **iOS/iPadOS**.
    - Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
    - En la página Configuración, seleccione Usar diseñador de configuración y agregue **DefenderTVMPrivacyMode** como tipo de clave y valor como **Cadena**.
        - Para deshabilitar la privacidad y recopilar la lista de aplicaciones instaladas, escriba el valor como `False` y asigne esta directiva a los usuarios. 
        - De forma predeterminada, este valor se establece en `True` para dispositivos sin supervisión.
        - Para los usuarios con el conjunto de claves como `False`, Defender para punto de conexión enviará la lista de aplicaciones instaladas en el dispositivo para la evaluación de vulnerabilidades.
    - Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.
    - Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.
1. Una vez aplicada la configuración, el usuario final tendrá que abrir la aplicación para **aprobar** la configuración de privacidad.
    - La pantalla de aprobación de privacidad solo vendrá para dispositivos no supervisados.
    - Solo si el usuario final aprueba la privacidad, la información de la aplicación se enviará a la consola de Defender para punto de conexión.

        :::image type="content" source="images/tvm-user-privacy.png" alt-text="Privacidad de TVM" lightbox="images/tvm-user-privacy.png":::

Una vez implementadas las versiones de cliente para dispositivos iOS de destino, se iniciará el procesamiento. Las vulnerabilidades encontradas en esos dispositivos comenzarán a aparecer en el panel de Administración de vulnerabilidades de Defender. El procesamiento puede tardar algunas horas (máximo 24 horas) en completarse. Especialmente para que toda la lista de aplicaciones aparezca en el inventario de software.

## <a name="configure-option-to-send-in-app-feedback"></a>Configuración de la opción para enviar comentarios desde la aplicación

Los clientes ahora tienen la opción de configurar la capacidad de enviar datos de comentarios a Microsoft dentro de la aplicación Defender para punto de conexión. Los datos de comentarios ayudan a Microsoft a mejorar los productos y a solucionar problemas.

> [!NOTE]
> Para los clientes de la nube del Gobierno de EE. UU., la recopilación de datos de comentarios está **deshabilitada** de forma predeterminada.

Siga estos pasos para configurar la opción para enviar datos de comentarios a Microsoft:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.

1. Asigne un nombre a la directiva, **Platform > iOS/iPadOS**, seleccione el tipo de perfil.

1. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

1. En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderSendFeedback** como tipo de clave y valor como **booleano**.

   - Para quitar la capacidad de los usuarios finales de proporcionar comentarios, establezca el valor como `false` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `true`. Para los clientes del Gobierno de EE. UU., el valor predeterminado se establece en "false".

   - Para los usuarios con el conjunto de claves como `true`, habrá una opción para enviar datos de comentarios a Microsoft dentro de la aplicación (Menú > Ayuda & Comentarios > Enviar comentarios a Microsoft)

1. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

## <a name="report-unsafe-site"></a>Informe de un sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visite la página [Proporcionar comentarios sobre la protección de red](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) si desea informar de un sitio web que podría ser un sitio de suplantación de identidad (phishing).
