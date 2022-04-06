---
title: Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune
description: Describe cómo implementar Microsoft Defender para Endpoint en Android con Microsoft Intune
keywords: 'microsoft, defender, Microsoft Defender para endpoint, mde, android, instalación, implementación, desinstalación,'
ms.prod: m365-security
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
ms.technology: mde
---

# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aprende a implementar Defender for Endpoint en Android en Portal de empresa de Intune dispositivos inscritos. Para obtener más información acerca de la inscripción de dispositivos de Intune, consulta [Inscribir el dispositivo](/mem/intune/user-help/enroll-device-android-company-portal).

> [!NOTE]
> **Defender para endpoint en Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Puedes conectarte a Google Play desde Intune para implementar la aplicación Defender for Endpoint en los modos de inscripción administrador de dispositivos y Android Enterprise de inscripción.
>
> Las actualizaciones de la aplicación son automáticas a través de Google Play.

## <a name="deploy-on-device-administrator-enrolled-devices"></a>Implementar en dispositivos inscritos por el administrador de dispositivos

**Implementar Defender para endpoint en Android en Portal de empresa de Intune: dispositivos inscritos por el administrador de dispositivos**

Aprende a implementar Defender for Endpoint en Android en Portal de empresa de Intune: dispositivos inscritos por el administrador de dispositivos.

### <a name="add-as-android-store-app"></a>Agregar como aplicación de la Tienda Android

1. En [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), ve a **Aplicaciones** \> **Android Apps** \> **Agregar aplicación \> de la tienda Android** y elige **Seleccionar**.

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="El panel Agregar aplicación de la tienda Android en el portal Microsoft Endpoint Manager Centro de administración"  lightbox="images/mda-addandroidstoreapp.png":::

2. En la **página Agregar aplicación** y en la sección *Información de la* aplicación, escriba:

   - **Nombre**
   - **Descripción**
   - **Publisher** como Microsoft.
   - **Dirección URL de la Tienda de** aplicaciones como https://play.google.com/store/apps/details?id=com.microsoft.scmx (DIRECCIÓN URL de La aplicación Defender para endpoint de Google Play Store)

   Otros campos son opcionales. Seleccione **Siguiente**.

   :::image type="content" source="images/mda-addappinfo.png" alt-text="La página Agregar aplicación que muestra la información del editor y la dirección URL de la aplicación en el portal Microsoft Endpoint Manager Centro de administración" lightbox="images/mda-addappinfo.png":::

3. En la *sección Asignaciones* , vaya a la **sección Obligatorio** y seleccione **Agregar grupo.** A continuación, puedes elegir los grupos de usuarios a los que quieres dirigirte Defender para Endpoint en la aplicación Android. Elija **Seleccionar** y, a **continuación, Siguiente**.

    > [!NOTE]
    > El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="El panel Agregar grupo en la página Agregar aplicación en el portal Microsoft Endpoint Manager Centro de administración" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. En la **sección Review+Create** , compruebe que toda la información especificada es correcta y, a continuación, seleccione **Crear**.

    En unos instantes, la aplicación Defender for Endpoint se crearía correctamente y se mostraría una notificación en la esquina superior derecha de la página.

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="El panel de estado de la aplicación en el portal Microsoft Endpoint Manager centro de administración" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. En la página de información de la aplicación que se muestra, en la sección **Supervisar**, seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="La página Estado de instalación del dispositivo en el portal de Microsoft Defender 365" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>Completar la incorporación y comprobar el estado

1. Una vez que Defender para Endpoint en Android se haya instalado en el dispositivo, verás el icono de la aplicación.

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="El icono de ATP de Microsoft Defender que aparece en el panel Búsqueda" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. Pulsa el icono de la aplicación Microsoft Defender para endpoint y sigue las instrucciones que aparecen en pantalla para completar la incorporación de la aplicación. Los detalles incluyen la aceptación por parte del usuario final de los permisos de Android requeridos por Defender para Endpoint en Android.

3. Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos del portal Microsoft 365 Defender dispositivos.

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Un dispositivo en el portal de Microsoft Defender para endpoint"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Implementar en dispositivos Enterprise android inscritos

Defender para Endpoint en Android admite dispositivos Enterprise android inscritos.

Para obtener más información sobre las opciones de inscripción admitidas por Intune, consulta [Opciones de inscripción](/mem/intune/enrollment/android-enroll).

**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten para la implementación.**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Agregar Microsoft Defender para endpoint en Android como una aplicación administrada de Google Play

Sigue los pasos siguientes para agregar la aplicación Microsoft Defender para endpoint a tu Google Play administrado.

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), ve a **Aplicaciones** \> **Para agregar aplicaciones android** \> **y selecciona** **Aplicación administrada de Google Play**.

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="Panel de adición de aplicaciones en el portal Microsoft Endpoint Manager centro de administración" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. En la página administrada de Google Play que se carga posteriormente, vaya al cuadro de búsqueda y escriba `Microsoft Defender`. La búsqueda debe mostrar la aplicación Microsoft Defender para endpoint en tu Google Play administrado. Haz clic en la aplicación Microsoft Defender para endpoint desde el resultado de la búsqueda Aplicaciones.

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="La página De Google Play administrada en el portal Microsoft Endpoint Manager centro de administración" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. En la página Descripción de la aplicación que aparece a continuación, deberías poder ver los detalles de la aplicación en Defender para endpoint. Revise la información de la página y, a continuación, seleccione **Aprobar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="La página de Google Play administrado en el portal Microsoft Endpoint Manager centro de administración" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::
      

4. Se te mostrarán los permisos que Defender for Endpoint obtiene para que funcione. Repase y, a continuación, **seleccione Aprobar**.

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Página de aprobación de permisos en el portal de Microsoft Defender 365" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. Se le mostrará la página Configuración de aprobación. La página confirma tu preferencia para controlar los nuevos permisos de la aplicación que Defender for Endpoint en Android podría pedir. Revisa las opciones y selecciona la opción preferida. Seleccione **Listo**.

    De forma predeterminada, Google Play administrado selecciona **Mantener aprobado cuando la aplicación solicita nuevos permisos**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Página de finalización de la configuración de aprobación en el portal de Microsoft Defender 365" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. Después de realizar la selección de control de permisos, selecciona **Sincronizar** para sincronizar Microsoft Defender para Endpoint con la lista de aplicaciones.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="El panel Sincronización del portal de Microsoft Defender 365" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. La sincronización se completará en unos minutos.

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="El panel de estado de sincronización de aplicaciones de la página Aplicaciones de Android en el portal de Microsoft Defender 365"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. Selecciona el **botón** Actualizar en la pantalla aplicaciones de Android y Microsoft Defender para Endpoint debe estar visible en la lista de aplicaciones.

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="La página que muestra la aplicación sincronizada" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint admite directivas de configuración de aplicaciones para dispositivos administrados a través de Intune. Esta funcionalidad se puede aprovechar para aplicar automáticamente los permisos de Android aplicables, por lo que el usuario final no necesita aceptar estos permisos.

    1. En la **página Aplicaciones** , ve **a Directiva > directivas de configuración de aplicaciones > Agregar > dispositivos administrados**.

       :::image type="content" source="images/android-mem.png" alt-text="El panel Directivas de configuración de aplicaciones en el portal Microsoft Endpoint Manager centro de administración" lightbox="images/android-mem.png":::

    1. En la **página Crear directiva de configuración de aplicaciones** , escriba los siguientes detalles:

        - Nombre: Microsoft Defender para endpoint.
        - Elija **Android Enterprise** como plataforma.
        - Elija **Perfil de trabajo solo** como Tipo de perfil.
        - Haz **clic en Seleccionar aplicación**, **elige ATP de Microsoft Defender**, **selecciona Aceptar** y, a continuación, **Siguiente**.

        :::image type="content" source="images/android-create-app.png" alt-text=" Panel de detalles de la aplicación asociada" lightbox="images/android-create-app.png":::

    1. En la **Configuración**, vaya a la sección Permisos haga clic en Agregar para ver la lista de permisos admitidos. En la sección Agregar permisos, seleccione los siguientes permisos:

       - Almacenamiento externo (lectura)
       - Almacenamiento externo (escritura)

       A continuación, seleccione **Aceptar**.

       :::image type="content" source="images/android-create-app-config.png" alt-text="Panel Agregar permisos" lightbox="images/android-create-app-config.png":::

    1. Ahora debería ver los permisos enumerados y ahora puede autograntar eligiendo autogrant en la lista desplegable Estado de  permisos y, a continuación, **seleccione Siguiente**.

       :::image type="content" source="images/android-auto-grant.png" alt-text="El panel Estado de permisos" lightbox="images/android-auto-grant.png":::

    1. En la **página Asignaciones** , seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones. Haga **clic en Seleccionar grupos para** incluir y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.

       :::image type="content" source="images/android-select-group.png" alt-text="Panel Grupos seleccionados" lightbox="images/android-select-group.png":::

    1. En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, **seleccione Crear**.

        La directiva de configuración de la aplicación para Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="La pestaña Revisar y crear de la página Crear directiva de configuración de aplicaciones" lightbox="images/android-review-create.png":::

10. Selecciona **Aplicación ATP de Microsoft Defender** en la lista \> **Propiedades Asignaciones** \> **Editar**\>.

   :::image type="content" source="images/mda-properties.png" alt-text="La opción Editar de la página Propiedades" lightbox="images/mda-properties.png":::

11. Asigna la aplicación como *una aplicación* necesaria a un grupo de usuarios. Se instala automáticamente en el perfil de *trabajo durante la* siguiente sincronización del dispositivo mediante Portal de empresa aplicación. Esta asignación se puede realizar navegando a la *sección* \> Obligatorio Agregar grupo **,** seleccionando el grupo de usuarios y haciendo clic en **Seleccionar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="Página Editar aplicación" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. En la **página Editar aplicación** , revise toda la información especificada anteriormente. A continuación **, seleccione Revisar + Guardar** y, a continuación **, Vuelva a** guardar para iniciar la asignación.

### <a name="auto-setup-of-always-on-vpn"></a>Configuración automática de VPN always-on

Defender for Endpoint admite directivas de configuración de dispositivos para dispositivos administrados a través de Intune. Esta funcionalidad se puede aprovechar para la configuración  automática de VPN siempre en Android Enterprise los dispositivos inscritos, por lo que el usuario final no necesita configurar el servicio VPN durante la incorporación.

1. En **Dispositivos**, seleccione **Perfiles de configuración** \> **Crear plataforma de** \> **perfiles** \> **Android Enterprise**

   Selecciona **Restricciones de dispositivo en** una de las siguientes opciones, según el tipo de inscripción del dispositivo:
   - **Perfil de trabajo totalmente administrado, dedicado y Corporate-Owned trabajo**
   - **Perfil de trabajo de propiedad personal**

   Seleccione **Crear**.

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="El elemento de menú Perfiles de configuración en el panel Directiva" lightbox="images/1autosetupofvpn.png":::

2. **Configuración Configuración** proporcionar un **nombre** y una **descripción para** identificar de forma única el perfil de configuración.

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="Los campos Nombre y Descripción del perfil de configuración de dispositivos en el panel Conceptos básicos" lightbox="images/2autosetupofvpn.png":::

3. Seleccione **Conectividad** y configure VPN:

   - Habilitar **VPN siempre activa**

     Configure un cliente VPN en el perfil de trabajo para conectarse automáticamente y volver a conectarse a la VPN siempre que sea posible. Solo se puede configurar un cliente VPN para VPN siempre en un dispositivo determinado, por lo que asegúrate de que no se implemente más de una directiva VPN siempre en un solo dispositivo.

   - Select **Custom** in VPN client dropdown list

     Vpn personalizada en este caso es Defender for Endpoint VPN, que se usa para proporcionar la característica de protección web.

     > [!NOTE]
     > La aplicación Microsoft Defender para endpoint debe instalarse en el dispositivo del usuario para que funcione la configuración automática de esta VPN.

   - Escribe **El identificador del paquete** de la aplicación Microsoft Defender para endpoint en la Tienda Google Play. Para la dirección URL de la aplicación defender <https://play.google.com/store/apps/details?id=com.microsoft.scmx>, el identificador del paquete **es com.microsoft.scmx**

   - **Modo de bloqueo** No configurado (predeterminado)

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="Panel Conectividad de la pestaña Configuración" lightbox="images/3autosetupofvpn.png":::

4. **Assignment**

   En la **página Asignaciones** , seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones. Elija **Seleccionar grupos** para incluir y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="Panel Asignación del perfil de configuración de dispositivos en las restricciones de dispositivos" lightbox="images/4autosetupofvpn.png":::

5. En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, **seleccione Crear**.
El perfil de configuración del dispositivo ahora se asigna al grupo de usuarios seleccionado.

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="A devices configuration profile 's provision for Review + create" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>Comprobar el estado y completar la incorporación

1. Para confirmar el estado de instalación de Microsoft Defender para Endpoint en Android, haga clic en **El estado de instalación del dispositivo**. Comprueba que el dispositivo se muestra aquí.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="Panel de estado de instalación del dispositivo" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. En el dispositivo, puedes validar el estado de incorporación yendo al **perfil de trabajo**. Confirme que Defender para endpoint está disponible y que está inscrito en los dispositivos **de propiedad personal con perfil de trabajo**. Si estás inscrito en un dispositivo de usuario totalmente administrado de propiedad **corporativa, tienes** un solo perfil en el dispositivo donde puedes confirmar que Defender for Endpoint está disponible.

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="Panel para mostrar de la aplicación" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. Cuando la aplicación esté instalada, abre la aplicación y acepta los permisos y, a continuación, la incorporación debe ser correcta.

    :::image type="content" source="images/MDE_new.png" alt-text="Th display of a Microsoft Defender for Endpoint application on a mobile device" lightbox="images/MDE_new.png":::

4. En esta fase, el dispositivo se incorpora correctamente a Defender para Endpoint en Android. Para comprobar esto en el portal [de Microsoft 365 Defender,](https://security.microsoft.com) vaya a la página **Inventario de** dispositivos.

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Portal de Microsoft Defender para endpoint" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
