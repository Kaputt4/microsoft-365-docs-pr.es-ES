---
title: Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune
description: Describe cómo implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mde, android, installation, deploy, uninstallation,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: eda60083ff28188022ab0713ac4ec9d9fedcae44
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679095"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Obtenga información sobre cómo implementar Defender para punto de conexión en Android en Portal de empresa de Intune dispositivos inscritos. Para obtener más información sobre Intune inscripción de dispositivos, consulte [Inscripción del dispositivo](/mem/intune/user-help/enroll-device-android-company-portal).

> [!NOTE]
> **Defender para punto de conexión en Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Puede conectarse a Google Play desde Intune para implementar la aplicación Defender para punto de conexión en los modos de inscripción Administrador de dispositivos y Android Enterprise.
>
> Novedades a la aplicación son automáticas a través de Google Play.

## <a name="deploy-on-device-administrator-enrolled-devices"></a>Implementación en dispositivos inscritos por el administrador de dispositivos

Obtenga información sobre cómo implementar Defender para punto de conexión en Android en Portal de empresa de Intune: dispositivos inscritos por el administrador de dispositivos.

### <a name="add-as-android-store-app"></a>Agregar como aplicación de la Tienda Android

1. En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , vaya a **Aplicaciones** \> **Android Apps** \> **Agregar \> aplicación de la Tienda Android** y elija **Seleccionar**.

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="Panel Agregar aplicación de almacén de Android en el portal del Centro de Endpoint Manager Administración Microsoft"  lightbox="images/mda-addandroidstoreapp.png":::

2. En la página **Agregar aplicación** y en la sección *Información de la aplicación* , escriba:

   - **Nombre**
   - **Descripción**
   - **Publicador** como Microsoft.
   - **Dirección URL de la tienda de** aplicaciones como https://play.google.com/store/apps/details?id=com.microsoft.scmx (dirección URL de Google Play Store de la aplicación Defender para punto de conexión)

   Otros campos son opcionales. Seleccione **Siguiente**.

   :::image type="content" source="images/mda-addappinfo.png" alt-text="La página Agregar aplicación que muestra la información del publicador y la dirección URL de la aplicación en el portal del Centro de microsoft Endpoint Manager Administración" lightbox="images/mda-addappinfo.png":::

3. En la sección *Asignaciones* , vaya a la sección **Requerido** y seleccione **Agregar grupo.** A continuación, puede elegir los grupos de usuarios que desea que tengan como destino Defender para punto de conexión en la aplicación Android. Elija **Seleccionar** y, a continuación, **Siguiente**.

    > [!NOTE]
    > El grupo de usuarios seleccionado debe constar de Intune usuarios inscritos.
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="El panel Agregar grupo de la página Agregar aplicación en el portal del Centro de Endpoint Manager Administración De Microsoft" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. En la sección **Revisar y crear** , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

    En unos instantes, la aplicación Defender para punto de conexión se crearía correctamente y se mostraría una notificación en la esquina superior derecha de la página.

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="Panel de estado de la aplicación en el portal del Centro de microsoft Endpoint Manager Administración" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. En la página de información de la aplicación que se muestra, en la sección **Monitor** , seleccione **Estado de instalación** del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="Página Estado de instalación del dispositivo en el portal de Microsoft Defender 365" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>Incorporación completa y comprobación del estado

1. Una vez instalado Defender para punto de conexión en Android en el dispositivo, verá el icono de aplicación.

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="Icono de ATP de Microsoft Defender que aparece en el panel Búsqueda" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. Pulse el icono Microsoft Defender para punto de conexión aplicación y siga las instrucciones en pantalla para completar la incorporación de la aplicación. Los detalles incluyen la aceptación por parte del usuario final de los permisos de Android requeridos por Defender para punto de conexión en Android.

3. Tras la incorporación correcta, el dispositivo comenzará a aparecer en la lista Dispositivos del portal de Microsoft 365 Defender.

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Un dispositivo en el portal de Microsoft Defender para punto de conexión"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Implementación en dispositivos inscritos en Android Enterprise

Defender para punto de conexión en Android admite dispositivos inscritos en Android Enterprise.

Para obtener más información sobre las opciones de inscripción admitidas por Intune, consulte [Opciones de inscripción](/mem/intune/enrollment/android-enroll).

**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa son compatibles con la implementación.**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Adición de Microsoft Defender para punto de conexión en Android como una aplicación de Google Play administrada

Siga los pasos siguientes para agregar Microsoft Defender para punto de conexión aplicación a Google Play administrado.

1. En [el Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , vaya a **Aplicaciones** \> **Android Apps** \> **Agregar** y seleccione **Aplicación administrada de Google Play**.

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="Panel de adición de aplicaciones en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. En la página de Google Play administrada que se carga posteriormente, vaya al cuadro de búsqueda y escriba `Microsoft Defender`. La búsqueda debe mostrar la aplicación Microsoft Defender para punto de conexión en Google Play administrado. Haga clic en la aplicación Microsoft Defender para punto de conexión en el resultado de búsqueda aplicaciones.

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="Página google play administrada en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. En la página Descripción de la aplicación que aparece a continuación, debería poder ver los detalles de la aplicación en Defender para punto de conexión. Revise la información de la página y, a continuación, seleccione **Aprobar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="Página de Google Play administrado en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::

4. Se le presentarán los permisos que Defender para punto de conexión obtiene para que funcione. Revíselos y, a continuación, seleccione **Aprobar**.

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Página de aprobación de permisos en el portal de Microsoft Defender 365" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. Se le presentará la página Configuración de aprobación. La página confirma su preferencia por controlar los nuevos permisos de aplicación que Defender para punto de conexión en Android podría solicitar. Revise las opciones y seleccione la opción que prefiera. Seleccione **Listo**.

    De forma predeterminada, Google Play administrado selecciona **Mantener aprobado cuando la aplicación solicita nuevos permisos**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Página de finalización de la configuración de la configuración de aprobación en el portal de Microsoft Defender 365" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. Una vez realizada la selección de control de permisos, seleccione **Sincronizar** para sincronizar Microsoft Defender para punto de conexión con la lista de aplicaciones.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="Panel Sincronización del portal de Microsoft Defender 365" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. La sincronización se completará en unos minutos.

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="Panel de estado de sincronización de aplicaciones en la página Aplicaciones de Android en el portal de Microsoft Defender 365"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. Seleccione el botón **Actualizar** en la pantalla Aplicaciones de Android y Microsoft Defender para punto de conexión debe estar visible en la lista de aplicaciones.

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="Página que muestra la aplicación sincronizada" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint admite directivas de configuración de aplicaciones para dispositivos administrados a través de Intune. Esta funcionalidad se puede aprovechar para seleccionar diferentes configuraciones para Defender.

    1. En la página **Aplicaciones** , vaya a **Directiva > Directivas de configuración de aplicaciones > Agregar > dispositivos administrados**.

       :::image type="content" source="images/android-mem.png" alt-text="Panel Directivas de configuración de aplicaciones en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/android-mem.png":::

    1. En la página Crear directiva de **configuración de aplicaciones** , escriba los detalles siguientes:

        - Nombre: Microsoft Defender para punto de conexión.
        - Elija **Android Enterprise** como plataforma.
        - Elija **Perfil de trabajo solo** como Tipo de perfil.
        - Haga clic en **Seleccionar aplicación**, elija **ATP de Microsoft Defender**, seleccione **Aceptar** y, a continuación, **Siguiente**.

        :::image type="content" source="images/android-create-app.png" alt-text=" Captura de pantalla del panel de detalles de la aplicación asociada." lightbox="images/android-create-app.png":::
     
    1. Seleccione **Permisos > Agregar**. En la lista, seleccione los permisos de aplicación disponibles > **Aceptar**.
    2. Seleccione una opción para cada permiso que se conceda con esta directiva:

       - **Preguntar** : solicita al usuario que acepte o deniegue.
       - **Concesión automática** : se aprueba automáticamente sin notificar al usuario.
       - **Denegación automática** : deniega automáticamente sin notificar al usuario. 

    1. En la página **Configuración** , vaya a la sección **Configuración** y elija **"Usar diseñador de configuración"** en Formato de configuración. 

       :::image type="content" alt-text="Imagen de la directiva de configuración de la aplicación de creación de Android." source="images/configurationformat.png" lightbox="images/configurationformat.png":::

    1. Haga clic en **Agregar** para ver una lista de configuraciones admitidas. Seleccione la configuración necesaria y haga clic en **Aceptar**.

       :::image type="content" alt-text="Imagen de la selección de directivas de configuración para Android." source="images/selectconfigurations.png" lightbox="images/selectconfigurations.png":::

    1. Debería ver todas las configuraciones seleccionadas en la lista. Puede cambiar el valor de configuración según sea necesario y, a continuación, seleccionar **Siguiente**.

       :::image type="content" alt-text="Imagen de las directivas de configuración seleccionadas." source="images/listedconfigurations.png" lightbox="images/listedconfigurations.png":::

    1. En la página **Asignaciones** , seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones. Haga clic en **Seleccionar grupos para incluir** y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para punto de conexión aplicación Android.

       :::image type="content" source="images/android-select-group.png" alt-text="Panel Grupos seleccionados" lightbox="images/android-select-group.png":::

    1. En la página **Revisar y crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.

        La directiva de configuración de la aplicación para Defender para punto de conexión que autograna el permiso de almacenamiento ahora se asigna al grupo de usuarios seleccionado.

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="La pestaña Revisar y crear de la página Crear directiva de configuración de aplicaciones" lightbox="images/android-review-create.png":::

10. Seleccione la aplicación **ATP de Microsoft Defender** en la lista \> **Edición de asignaciones de** \> **propiedades**\>.

    :::image type="content" source="images/mda-properties.png" alt-text="La opción Editar de la página Propiedades" lightbox="images/mda-properties.png":::

11. Asigne la aplicación como una aplicación *requerida* a un grupo de usuarios. Se instala automáticamente en el *perfil de trabajo* durante la siguiente sincronización del dispositivo a través de Portal de empresa aplicación. Para realizar esta asignación, vaya a la sección \> *Requerido* **Agregar grupo,** seleccione el grupo de usuarios y haga clic en **Seleccionar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="Página Editar aplicación" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. En la página **Editar aplicación** , revise toda la información especificada anteriormente. A continuación, seleccione **Revisar y guardar** y, a continuación, **Guardar** de nuevo para comenzar la asignación.

### <a name="auto-setup-of-always-on-vpn"></a>Configuración automática de VPN always-on

Defender for Endpoint admite directivas de configuración de dispositivos para dispositivos administrados mediante Intune. Esta funcionalidad se puede aprovechar para configurar **automáticamente vpn always-on** en dispositivos inscritos en Android Enterprise, por lo que el usuario final no necesita configurar el servicio VPN durante la incorporación.

1. En **Dispositivos**, seleccione **Perfiles** \> de configuración Crear **plataforma** \> **de perfil** \> **Android Enterprise**

   Seleccione **Restricciones de** dispositivos en una de las siguientes opciones, en función del tipo de inscripción de dispositivo:
   - **Perfil de trabajo totalmente administrado, dedicado y Corporate-Owned**
   - **Perfil de trabajo de propiedad personal**

   Seleccione **Crear**.

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="Elemento de menú Perfiles de configuración en el panel Directiva" lightbox="images/1autosetupofvpn.png":::

2. **Configuración** Proporcione un **nombre** y una **descripción** para identificar de forma única el perfil de configuración.

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="Los campos Nombre y Descripción del perfil de configuración de dispositivos en el panel Aspectos básicos" lightbox="images/2autosetupofvpn.png":::

3. Seleccione **Conectividad** y configure VPN:

   - Habilitación **de VPN always-on**

     Configure un cliente VPN en el perfil de trabajo para conectarse y volver a conectarse automáticamente a la VPN siempre que sea posible. Solo se puede configurar un cliente VPN para vpn siempre activada en un dispositivo determinado, por lo que asegúrese de que no haya más de una directiva de VPN siempre activada implementada en un solo dispositivo.

   - Seleccione **Personalizado** en la lista desplegable cliente VPN.

     Vpn personalizada en este caso es LA VPN de Defender para punto de conexión que se usa para proporcionar la característica de protección web.

     > [!NOTE]
     > Microsoft Defender para punto de conexión aplicación debe instalarse en el dispositivo del usuario para poder funcionar con la configuración automática de esta VPN.

   - Escriba **el identificador de paquete** de la aplicación Microsoft Defender para punto de conexión en Google Play Store. Para la dirección URL <https://play.google.com/store/apps/details?id=com.microsoft.scmx>de la aplicación Defender, el identificador de paquete es **com.microsoft.scmx**.

   - **Modo de bloqueo** No configurado (valor predeterminado)

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="El panel Conectividad en la pestaña Configuración" lightbox="images/3autosetupofvpn.png":::

4. **Assignment**

   En la página **Asignaciones** , seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones. Elija **Seleccionar grupos** para incluir y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para punto de conexión aplicación Android.

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="Captura de pantalla del panel Asignación del perfil de configuración de dispositivos en Restricciones de dispositivos." lightbox="images/4autosetupofvpn.png":::

5. En la página **Revisar y crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.
El perfil de configuración del dispositivo ahora se asigna al grupo de usuarios seleccionado.

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="Aprovisionamiento de un perfil de configuración de dispositivos para Revisar y crear" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>Comprobar el estado y completar la incorporación

1. Confirme el estado de instalación de Microsoft Defender para punto de conexión en Android haciendo clic en Estado **de instalación del dispositivo**. Compruebe que el dispositivo se muestra aquí.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="Panel de estado de instalación del dispositivo" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. En el dispositivo, puede validar el estado de incorporación si va al **perfil de trabajo**. Confirme que Defender para punto de conexión está disponible y que está inscrito en los **dispositivos de propiedad personal con perfil de trabajo**. Si está inscrito en un dispositivo de **usuario corporativo totalmente administrado**, tendrá un único perfil en el dispositivo donde podrá confirmar que Defender para punto de conexión está disponible.

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="Panel de presentación de la aplicación" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. Cuando se instale la aplicación, abra la aplicación y acepte los permisos y, a continuación, la incorporación debe realizarse correctamente.

    :::image type="content" source="images/MDE_new.png" alt-text="Th display of a Microsoft Defender para punto de conexión application on a mobile device" lightbox="images/MDE_new.png":::

4. En esta fase, el dispositivo se incorpora correctamente a Defender para punto de conexión en Android. Para comprobarlo en el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a la página **Inventario** de dispositivos.

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="El portal de Microsoft Defender para punto de conexión" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="set-up-microsoft-defender-in-personal-profile-on-android-enterprise-in-byod-mode"></a>Configuración de Microsoft Defender en perfil personal en Android Enterprise en modo BYOD

### <a name="set-up-microsoft-defender-in-personal-profile"></a>Configuración de Microsoft Defender en perfil personal

Los administradores pueden ir al [Centro de administración de Microsoft Endpoint Management](https://endpoint.microsoft.com) para configurar y configurar la compatibilidad con Microsoft Defender en perfiles personales siguiendo estos pasos:

1. Vaya a **Aplicaciones> Directivas de configuración de aplicaciones** y haga clic en **Agregar**. Seleccione **Dispositivos administrados**.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la adición de la directiva de configuración de aplicaciones.](images/addpolicy.png)

1. Escriba **Name (Nombre** ) y **Description (Descripción** ) para identificar de forma única la directiva de configuración. Seleccione plataforma como **"Android Enterprise"**, Tipo de perfil como **"Solo perfil de trabajo de propiedad personal"** y Aplicación dirigida como **"Microsoft Defender"**.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la directiva de configuración de nomenclatura.](images/selectapp.png)

1. En la página de configuración, en **"Formato de configuración"**, seleccione **"Usar diseñador de configuración"** y haga clic en **Agregar**. En la lista de configuraciones que se muestran, seleccione **"Microsoft Defender en perfil personal"**.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la configuración del perfil personal.](images/addconfiguration.png)

1. Se mostrará la configuración seleccionada. Cambie el **valor de configuración a 1** para habilitar los perfiles personales de soporte técnico de Microsoft Defender. Aparecerá una notificación informando al administrador sobre lo mismo. Haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del cambio del valor de configuración.](images/changeconfigvalue.png)

1. **Asigne** la directiva de configuración a un grupo de usuarios. **Revise y cree** la directiva.

    > [!div class="mx-imgBorder"]
    > ![Imagen de revisión y creación de directivas.](images/savepolicy.png)

Los administradores también pueden configurar **controles de privacidad** desde el Centro de administración de Microsoft Endpoint Manager para controlar qué datos puede enviar el cliente móvil de Defender al portal de seguridad. Para obtener más información, consulte [configuración de controles de privacidad](android-configure.md).

Las organizaciones pueden comunicarse con sus usuarios para proteger el perfil personal con Microsoft Defender en sus dispositivos BYOD inscritos.

- Requisito previo: Microsoft Defender ya debe estar instalado y activo en el perfil de trabajo para habilitar Microsoft Defender en perfiles personales.

### <a name="to-complete-onboarding-a-device"></a>Para completar la incorporación de un dispositivo

1. Instale la aplicación de Microsoft Defender en un perfil personal con una cuenta personal de Google Play Store.
2. Instale la aplicación portal de empresa en el perfil personal. No se requiere ningún inicio de sesión.
3. Cuando un usuario inicie la aplicación, verá la pantalla de inicio de sesión. **Inicie sesión solo con una cuenta corporativa**.
4. En un inicio de sesión correcto, los usuarios verán las siguientes pantallas:
   1. **Pantalla EULA**: solo se presenta si el usuario no ha dado su consentimiento en el perfil de trabajo.
   2. **Pantalla de aviso**: los usuarios deben proporcionar consentimiento en esta pantalla para avanzar con la incorporación de la aplicación. Esto solo es necesario durante la primera ejecución de la aplicación.
5. Proporcione los permisos necesarios para completar la incorporación.

> [!NOTE]
> **Requisito previo:**
>
> 1. El portal de empresa debe estar habilitado en el perfil personal.
> 2. Microsoft Defender debe estar ya instalado y activo en el perfil de trabajo.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
