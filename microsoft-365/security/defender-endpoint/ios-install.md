---
title: Implementación basada en aplicaciones para Microsoft Defender para punto de conexión en iOS
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para punto de conexión en iOS mediante una aplicación
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 53f21b5db99bb8d01e06f724f9fbc822ba2332e5
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67050994"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>Implementación de Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este tema se describe la implementación de Defender para punto de conexión en iOS en Portal de empresa de Intune dispositivos inscritos. Para obtener más información sobre Intune inscripción de dispositivos, consulte [Inscripción de dispositivos iOS/iPadOS en Intune](/mem/intune/enrollment/ios-enroll).

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que tiene acceso al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

- Asegúrese de que la inscripción de iOS se realiza para los usuarios. Los usuarios deben tener asignada una licencia de Defender para punto de conexión para poder usar Defender para punto de conexión en iOS. Consulte [Asignación de licencias a usuarios](/azure/active-directory/users-groups-roles/licensing-groups-assign) para obtener instrucciones sobre cómo asignar licencias.

> [!NOTE]
> Microsoft Defender para punto de conexión en iOS está disponible en apple [App Store](https://aka.ms/mdatpiosappstore).

## <a name="deployment-steps"></a>Pasos para la implementación

Implemente Defender para punto de conexión en iOS a través de Portal de empresa de Intune.

### <a name="add-ios-store-app"></a>Incorporación de una aplicación de la Tienda iOS

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Aplicaciones** -> **iOS/iPadOS** -> **Agregar** -> **aplicación de la tienda iOS** y haga clic en **Seleccionar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-1.png" alt-text="La pestaña Agregar aplicaciones en el Centro de Endpoint Manager Administración de Microsoft" lightbox="images/ios-deploy-1.png":::

1. En la página **Agregar aplicación**, haga clic en **Buscar en el App Store** y escriba **Microsoft Defender para punto de conexión** en la barra de búsqueda. En la sección de resultados de búsqueda, haga clic en *Microsoft Defender para punto de conexión* y haga clic en **Seleccionar**.

1. Seleccione **iOS 11.0** como sistema operativo mínimo. Revise el resto de la información sobre la aplicación y haga clic en **Siguiente**.

1. En la sección **Asignaciones** , vaya a la sección **Requerido** y seleccione **Agregar grupo**. A continuación, puede elegir los grupos de usuarios que desea que tengan como destino Defender para punto de conexión en la aplicación iOS. Haga clic en **Seleccionar** y, a continuación, **en Siguiente**.

    > [!NOTE]
    > El grupo de usuarios seleccionado debe constar de Intune usuarios inscritos.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-2.png" alt-text="Pestaña Agregar grupo en el Centro de Endpoint Manager Administración de Microsoft" lightbox="images/ios-deploy-2.png":::

1. En la sección *Revisar y crear* , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**. En unos instantes, la aplicación Defender para punto de conexión debe crearse correctamente y debe aparecer una notificación en la esquina superior derecha de la página.

1. En la página de información de la aplicación que se muestra, en la sección **Monitor** , seleccione **Estado de instalación** del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-3.png" alt-text="Página Estado de instalación del dispositivo" lightbox="images/ios-deploy-3.png":::

## <a name="complete-deployment-for-supervised-devices"></a>Implementación completa para dispositivos supervisados

La Microsoft Defender para punto de conexión en la aplicación iOS tiene una capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las mayores funcionalidades de administración que proporciona la plataforma en estos tipos de dispositivos. También puede proporcionar protección web **sin configurar una VPN local en el dispositivo**. Esto proporciona a los usuarios finales una experiencia sin problemas mientras siguen protegidos contra suplantación de identidad (phishing) y otros ataques basados en web.

### <a name="configure-supervised-mode-via-intune"></a>Configuración del modo supervisado mediante Intune

A continuación, configure el modo supervisado para la aplicación Defender para punto de conexión mediante una directiva de App Configuration.

   > [!NOTE]
   > Esta directiva de configuración de aplicaciones para dispositivos supervisados solo se aplica a los dispositivos administrados y debe tener como destino todos los dispositivos iOS administrados como procedimiento recomendado.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** \> de **configuración** \> de aplicaciones **Agregar**. Seleccione **Dispositivos administrados**.

    > [!div class="mx-imgBorder"]
    > ![Imagen de Microsoft Endpoint Manager Administración Center4.](images/ios-deploy-4.png)

1. En la página Crear directiva de *configuración de aplicaciones* , proporcione la siguiente información:
    - Nombre de directiva
    - Plataforma: seleccione iOS/iPadOS
    - Aplicación de destino: seleccione **Microsoft Defender para punto de conexión** de la lista

    > [!div class="mx-imgBorder"]
    > ![Imagen de Microsoft Endpoint Manager Administración Center5.](images/ios-deploy-5.png)

1. En la siguiente pantalla, seleccione **Usar diseñador de configuración** como formato. Especifique la siguiente propiedad:
    - Clave de configuración: issupervised
    - Tipo de valor: String
    - Valor de configuración: {{issupervised}}

    > [!div class="mx-imgBorder"]
    > ![Imagen de Microsoft Endpoint Manager Administración Center6.](images/ios-deploy-6.png)

1. Seleccione **Siguiente** para abrir la página **Etiquetas de ámbito**. Las etiquetas de ámbito son opcionales. Seleccione **Siguiente** para continuar.

1. En la página **Asignaciones**, seleccione los grupos que recibirán este perfil. En este escenario, se recomienda dirigirse a **Todos los dispositivos**. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](/mem/intune/configuration/device-profile-assign).

   Al implementar en grupos de usuarios, un usuario debe iniciar sesión en un dispositivo antes de que se aplique la directiva.

   Haga clic en **Siguiente**.

1. Cuando haya terminado, elija **Crear** en la página **Revisar y crear**. El nuevo perfil se muestra en la lista de perfiles de configuración.

1. A continuación, debe implementar un perfil personalizado en dispositivos iOS supervisados. Esto es para funcionalidades mejoradas de anti-phishing. Siga estos pasos:

    - Descargar el perfil de configuración desde [https://aka.ms/mdeiosprofilesupervised](https://aka.ms/mdeiosprofilesupervised)
    - Vaya a **Dispositivos perfiles** ->  de **configuración** ->  de **iOS/iPadOS** -> **Crear perfil**

    > [!div class="mx-imgBorder"]
    > ![Imagen de Microsoft Endpoint Manager Administración Center7.](images/ios-deploy-7.png)
    
    - Proporcione un nombre del perfil. Cuando se le pida que importe un archivo de perfil de configuración, seleccione el descargado del paso anterior.
    - En la sección **Asignación** , seleccione el grupo de dispositivos al que desea aplicar este perfil. Como procedimiento recomendado, esto debe aplicarse a todos los dispositivos iOS administrados. Seleccione **Siguiente**.
    - Cuando haya terminado, elija **Crear** en la página **Revisar y crear**. El nuevo perfil se muestra en la lista de perfiles de configuración.


## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>Incorporación automática del perfil de VPN (incorporación simplificada)

En el caso de los dispositivos sin supervisión, se usa una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.

>[!NOTE]
>En el caso de los dispositivos supervisados, una VPN no es necesaria para la funcionalidad de protección web y requiere que los administradores configuren un perfil de configuración en dispositivos supervisados. Para configurar para dispositivos supervisados, siga los pasos de la sección [Completar implementación para dispositivos supervisados](#complete-deployment-for-supervised-devices) .

Los administradores pueden configurar la configuración automática del perfil de VPN. Esto configurará automáticamente el perfil de VPN de Defender para punto de conexión sin que el usuario lo haga durante la incorporación. 

Este paso simplifica el proceso de incorporación mediante la configuración del perfil de VPN. Para obtener una experiencia de incorporación sin contacto o silenciosa, consulte la sección siguiente: [Incorporación de cero toques](#zero-touch-onboarding-of-microsoft-defender-for-endpoint).

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Dispositivos** -> **Perfiles** ->  de configuración **Crear perfil**.
1. Elija **Plataforma** como **iOS/iPadOS** y **Tipo de perfil** como **VPN**. Haga clic en **Crear**.
1. Escriba un nombre para el perfil y haga clic en **Siguiente**.
1. Seleccione **VPN personalizada** para Tipo de conexión y, en la sección **VPN base** , escriba lo siguiente:
    - Nombre de conexión = Microsoft Defender para punto de conexión
    - Dirección del servidor VPN = 127.0.0.1
    - Método de autenticación = "Nombre de usuario y contraseña"
    - Tunelización dividida = Deshabilitar
    - Identificador de VPN = com.microsoft.scmx
    - En los pares clave-valor, escriba la clave **AutoOnboard** y establezca el valor en **True**.
    - Tipo de VPN automática = VPN a petición
    - Seleccione **Agregar** para **reglas a petición** y seleccione **Quiero hacer lo siguiente = Conectar VPN**, **quiero restringir a = Todos los dominios**.

    :::image type="content" source="images/ios-deploy-8.png" alt-text="Pestaña Configuración del perfil de VPN" lightbox="images/ios-deploy-8.png":::
    - Para exigir que la VPN no se pueda deshabilitar en el dispositivo de usuarios, los administradores pueden seleccionar **Sí** en **Bloquear que los usuarios deshabiliten la VPN automática**. De forma predeterminada, no está configurada y los usuarios solo pueden deshabilitar la VPN en configuración.
    - Para permitir que los usuarios cambien la alternancia de VPN desde dentro de la aplicación, agregue **EnableVPNToggleInApp = TRUE** en los pares clave-valor. De forma predeterminada, los usuarios no pueden cambiar el botón de alternancia desde dentro de la aplicación.

1. Haga clic en Siguiente y asigne el perfil a los usuarios de destino.
1. En la sección *Revisar y crear* , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

## <a name="zero-touch-onboarding-of-microsoft-defender-for-endpoint"></a>Incorporación sin toque de Microsoft Defender para punto de conexión



> [!NOTE]
> No se puede configurar Sin intervención táctil en dispositivos iOS inscritos sin afinidad de usuario (dispositivos sin usuario o dispositivos compartidos).

Los administradores pueden configurar Microsoft Defender para punto de conexión para implementar y activar de forma silenciosa. En este flujo, el administrador crea un perfil de implementación y el usuario simplemente recibe una notificación de la instalación. Defender para punto de conexión se instala automáticamente sin necesidad de que el usuario abra la aplicación. Siga los pasos siguientes para configurar la implementación sin intervención o silenciosa de Defender para punto de conexión en dispositivos iOS inscritos:

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Dispositivos** > **Perfiles** >  de configuración **Crear perfil**.
1. Elija **Plataforma** como **iOS/iPadOS** y **Tipo de perfil** como **VPN**. Seleccione **Crear**.
1. Escriba un nombre para el perfil y seleccione **Siguiente**.
1. Seleccione **VPN personalizada** para Tipo de conexión y, en la sección **VPN base** , escriba lo siguiente:
    - Nombre de conexión = Microsoft Defender para punto de conexión
    - Dirección del servidor VPN = 127.0.0.1
    - Método de autenticación = "Nombre de usuario y contraseña"
    - Tunelización dividida = Deshabilitar
    - Identificador de VPN = com.microsoft.scmx
    - En los pares clave-valor, escriba la clave **SilentOnboard** y establezca el valor en **True**.
    - Tipo de VPN automática = VPN a petición
    - Seleccione **Agregar** para **reglas a petición** y seleccione **Quiero hacer lo siguiente = Conectar VPN**, **quiero restringir a = Todos los dominios**.

    :::image type="content" source="images/ios-deploy-9.png" alt-text="Página Configuración del perfil de VPN" lightbox="images/ios-deploy-9.png":::

    - Para exigir que la VPN no se pueda deshabilitar en el dispositivo de usuarios, los administradores pueden seleccionar **Sí** en **Bloquear que los usuarios deshabiliten la VPN automática**. De forma predeterminada, no está configurada y los usuarios solo pueden deshabilitar la VPN en configuración.
    - Para permitir que los usuarios cambien la alternancia de VPN desde dentro de la aplicación, agregue **EnableVPNToggleInApp = TRUE** en los pares clave-valor. De forma predeterminada, los usuarios no pueden cambiar el botón de alternancia desde dentro de la aplicación.

1. Seleccione **Siguiente** y asigne el perfil a los usuarios de destino.
1. En la sección *Revisar y crear* , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

Una vez realizada y sincronizada la configuración anterior con el dispositivo, se llevan a cabo las siguientes acciones en los dispositivos iOS de destino:
    - Microsoft Defender para punto de conexión se implementarán y incorporarán de forma silenciosa y el dispositivo se verá en el portal de Defender para punto de conexión.
    - Se enviará una notificación provisional al dispositivo de usuario.
    - Protección web y otras características se activarán.

   > [!NOTE]
   > En el caso de los dispositivos supervisados, aunque no se requiere un perfil de VPN, los administradores pueden configurar la incorporación de Zero-touch mediante la configuración del perfil de VPN de Defender para punto de conexión a través de Intune. El perfil de VPN se implementará en el dispositivo, pero solo estará presente en el dispositivo como perfil de paso a través y se puede eliminar después de la incorporación inicial.

## <a name="complete-onboarding-and-check-status"></a>Incorporación completa y comprobación del estado

1. Una vez instalado Defender para punto de conexión en iOS en el dispositivo, verá el icono de aplicación.

    :::image type="content" source="images/41627a709700c324849bf7e13510c516.png" alt-text="Una descripción del teléfono inteligente generada automáticamente" lightbox="images/41627a709700c324849bf7e13510c516.png":::

2. Pulse el icono de la aplicación Defender para punto de conexión (MSDefender) y siga las instrucciones en pantalla para completar los pasos de incorporación. Los detalles incluyen la aceptación por parte del usuario final de los permisos de iOS requeridos por Defender para punto de conexión en iOS.

3. Tras la incorporación correcta, el dispositivo comenzará a aparecer en la lista Dispositivos del portal de Microsoft 365 Defender.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/device-inventory-screen.png" alt-text="Página Inventario de dispositivos" lightbox="images/device-inventory-screen.png":::

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Configuración de Microsoft Defender para punto de conexión para el modo supervisado

La Microsoft Defender para punto de conexión en la aplicación iOS tiene una capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las mayores funcionalidades de administración que proporciona la plataforma en estos tipos de dispositivos. Para aprovechar estas funcionalidades, la aplicación Defender para punto de conexión debe saber si un dispositivo está en modo supervisado.

### <a name="configure-supervised-mode-via-intune"></a>Configuración del modo supervisado mediante Intune

Intune permite configurar la aplicación Defender para iOS mediante una directiva de App Configuration.

   > [!NOTE]
   > Esta directiva de configuración de aplicaciones para dispositivos supervisados solo se aplica a los dispositivos administrados y debe tener como destino todos los dispositivos iOS administrados como procedimiento recomendado.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** \> de **configuración** \> de aplicaciones **Agregar**. Haga clic en **Dispositivos administrados**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-4.png" alt-text="La opción Dispositivos administrados" lightbox="images/ios-deploy-4.png":::

1. En la página Crear directiva de *configuración de aplicaciones* , proporcione la siguiente información:
    - Nombre de directiva
    - Plataforma: seleccione iOS/iPadOS
    - Aplicación de destino: seleccione **Microsoft Defender para punto de conexión** de la lista

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-5.png" alt-text="Los campos básicos de la directiva de configuración de la aplicación" lightbox="images/ios-deploy-5.png":::

1. En la siguiente pantalla, seleccione **Usar diseñador de configuración** como formato. Especifique la siguiente propiedad:
    - Clave de configuración: issupervised
    - Tipo de valor: String
    - Valor de configuración: {{issupervised}}

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-6.png" alt-text="Página desde la que elegir el formato para la configuración de la directiva" lightbox="images/ios-deploy-6.png":::

1. Haga clic en **Siguiente** para abrir la página **Etiquetas de ámbito** . Las etiquetas de ámbito son opcionales. Haga clic en **Siguiente** para continuar.

1. En la página **Asignaciones**, seleccione los grupos que recibirán este perfil. En este escenario, se recomienda dirigirse a **Todos los dispositivos**. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](/mem/intune/configuration/device-profile-assign).

   Al implementar en grupos de usuarios, un usuario debe iniciar sesión en un dispositivo antes de que se aplique la directiva.

   Haga clic en **Siguiente**.

1. Cuando haya terminado, elija **Crear** en la página **Revisar y crear**. El nuevo perfil se muestra en la lista de perfiles de configuración.

## <a name="next-steps"></a>Pasos siguientes

- [Configuración de la directiva de protección de aplicaciones para incluir señales de riesgo de Defender para punto de conexión (MAM)](ios-install-unmanaged.md)
- [Configuración de Defender para punto de conexión en características de iOS](ios-configure-features.md)
