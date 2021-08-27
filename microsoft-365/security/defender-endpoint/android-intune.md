---
title: Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune
description: Describe cómo implementar Microsoft Defender para Endpoint en Android con Microsoft Intune
keywords: microsoft, defender, Microsoft Defender para endpoint, mde, android, instalación, implementación, desinstalación,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 807582e0eec56c42d03329802d72b38ca93ba1ac
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611091"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aprende a implementar Defender for Endpoint en Android en Portal de empresa de Intune dispositivos inscritos. Para obtener más información acerca de la inscripción de dispositivos de Intune, consulta  [Inscribir el dispositivo](/mem/intune/user-help/enroll-device-android-company-portal).

> [!NOTE]
> **Defender para endpoint en Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Puedes conectarte a Google Play desde Intune para implementar la aplicación Defender for Endpoint en los modos de inscripción administrador de dispositivos Enterprise Android.
>
> Las actualizaciones de la aplicación son automáticas a través de Google Play.

## <a name="deploy-on-device-administrator-enrolled-devices"></a>Implementar en dispositivos inscritos por el administrador de dispositivos

**Implementar Defender para endpoint en Android en Portal de empresa de Intune: dispositivos inscritos por el administrador de dispositivos**

Aprende a implementar Defender for Endpoint en Android en Portal de empresa de Intune: dispositivos inscritos por el administrador de dispositivos.

### <a name="add-as-android-store-app"></a>Agregar como aplicación de la Tienda Android

1. En [Microsoft Endpoint Manager centro de administración,](https://go.microsoft.com/fwlink/?linkid=2109431) ve a **Aplicaciones** Android Apps Agregar aplicación de la tienda \>  \> **\> Android** y elige **Seleccionar**.

   ![Imagen de Microsoft Endpoint Manager Centro de administración agregar aplicación de tienda android.](images/mda-addandroidstoreapp.png)

2. En la **página Agregar aplicación** y en la sección Información de *la* aplicación, escriba:

   - **Nombre**
   - **Descripción**
   - **Publisher** como Microsoft.
   - **Dirección URL de la Tienda de** aplicaciones como https://play.google.com/store/apps/details?id=com.microsoft.scmx (DIRECCIÓN URL de La aplicación Defender para endpoint de Google Play Store)

   Otros campos son opcionales. Seleccione **Siguiente**.

   ![Imagen de Microsoft Endpoint Manager Centro de administración agregar información de la aplicación.](images/mda-addappinfo.png)

3. En la *sección Asignaciones,* vaya a la **sección Obligatorio** y seleccione **Agregar grupo.** A continuación, puedes elegir los grupos de usuarios a los que quieres dirigirte Defender para Endpoint en la aplicación Android. Elija **Seleccionar** y, a **continuación, Siguiente**.

    > [!NOTE]
    > El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.

    > [!div class="mx-imgBorder"]

    > ![Imagen de los grupos de Microsoft Endpoint Manager de usuarios seleccionados del Centro de administración.](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.

    En unos instantes, la aplicación Defender for Endpoint se crearía correctamente y se mostraría una notificación en la esquina superior derecha de la página.

    ![Imagen de Microsoft Endpoint Manager notificación del Centro de administración de la aplicación de punto de conexión del defensor.](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. En la página de información de la aplicación  que se muestra, en la sección **Supervisar,** seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la Microsoft Endpoint Manager dispositivo del Centro de administración.](images/513cf5d59eaaef5d2b5bc122715b5844.png)

### <a name="complete-onboarding-and-check-status"></a>Completar la incorporación y comprobar el estado

1. Una vez que Defender para Endpoint en Android se haya instalado en el dispositivo, verás el icono de la aplicación.

    ![Icono en el dispositivo móvil.](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. Pulsa el icono de la aplicación Microsoft Defender para endpoint y sigue las instrucciones que aparecen en pantalla para completar la incorporación de la aplicación. Los detalles incluyen la aceptación por parte del usuario final de los permisos de Android requeridos por Defender para Endpoint en Android.

3. Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos de Centro de seguridad de Microsoft Defender.

    ![Imagen del dispositivo en defender para el portal de punto de conexión.](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Implementar en dispositivos Enterprise android inscritos

Defender para Endpoint en Android admite dispositivos Enterprise android inscritos.

Para obtener más información sobre las opciones de inscripción admitidas por Intune, vea [Opciones de inscripción](/mem/intune/enrollment/android-enroll).

**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten para la implementación.**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Agregar Microsoft Defender para endpoint en Android como una aplicación administrada de Google Play

Sigue los pasos siguientes para agregar la aplicación Microsoft Defender para endpoint a tu Google Play administrado.

1. En [Microsoft Endpoint Manager centro de administración,](https://go.microsoft.com/fwlink/?linkid=2109431) ve a **Aplicaciones** Para agregar \> **aplicaciones android** y selecciona Aplicación administrada de Google \>  **Play.**

    > [!div class="mx-imgBorder"]
    > ![Imagen de Microsoft Endpoint Manager centro de administración administrado google play.](images/579ff59f31f599414cedf63051628b2e.png)

2. En la página administrada de Google Play que se carga posteriormente, ve al cuadro de búsqueda y busca **Microsoft Defender.** La búsqueda debe mostrar la aplicación Microsoft Defender para endpoint en tu Google Play administrado. Haz clic en la aplicación Microsoft Defender para endpoint desde el resultado de la búsqueda Aplicaciones.

    ![Imagen de la Microsoft Endpoint Manager de aplicaciones del Centro de administración.](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. En la página Descripción de la aplicación que aparece a continuación, deberías poder ver los detalles de la aplicación en Defender para endpoint. Revise la información de la página y, a continuación, seleccione **Aprobar**.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de un Google Play administrado.](images/07e6d4119f265037e3b80a20a73b856f.png)

4. Se te mostrarán los permisos que Defender for Endpoint obtiene para que funcione. Repase y, a continuación, **seleccione Aprobar**.

    ![Una captura de pantalla de la aprobación de la aplicación defender para la vista previa del punto de conexión.](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. Se le mostrará la página Configuración de aprobación. La página confirma tu preferencia para controlar los nuevos permisos de la aplicación que Defender for Endpoint en Android podría pedir. Revisa las opciones y selecciona la opción preferida. Seleccione **Listo**.

    De forma predeterminada, Google Play administrado selecciona Mantener aprobado cuando *la aplicación solicita nuevos permisos*

    > [!div class="mx-imgBorder"]
    > ![Imagen de la pestaña notificaciones.](images/ffecfdda1c4df14148f1526c22cc0236.png)

6. Después de realizar la selección de control de permisos, selecciona **Sincronizar** para sincronizar Microsoft Defender para Endpoint con la lista de aplicaciones.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la página de sincronización.](images/34e6b9a0dae125d085c84593140180ed.png)

7. La sincronización se completará en unos minutos.

    ![Imagen de la aplicación Android.](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. Selecciona el **botón** Actualizar en la pantalla aplicaciones de Android y Microsoft Defender para Endpoint debe estar visible en la lista de aplicaciones.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la lista de aplicaciones de Android.](images/fa4ac18a6333335db3775630b8e6b353.png)

9. Defender for Endpoint admite directivas de configuración de aplicaciones para dispositivos administrados a través de Intune. Esta funcionalidad se puede aprovechar para aplicar automáticamente los permisos de Android aplicables, por lo que el usuario final no necesita aceptar estos permisos.

    1. En la **página Aplicaciones,** vaya a Directiva > de configuración de **aplicaciones > Agregar > dispositivos administrados.**

       ![Imagen de Microsoft Endpoint Manager dispositivos administrados android del Centro de administración.](images/android-mem.png)

    1. En la **página Crear directiva de configuración de aplicaciones,** escriba los siguientes detalles:

        - Nombre: Microsoft Defender para endpoint.
        - Elija **Android Enterprise** como plataforma.
        - Elija **Perfil de trabajo solo** como Tipo de perfil.
        - Haga **clic en Seleccionar aplicación,** elija ATP de Microsoft **Defender,** **seleccione Aceptar** y, a continuación, **Siguiente**.

        > [!div class="mx-imgBorder"]
        > ![Imagen de la página crear directiva de configuración de aplicaciones.](images/android-create-app.png)

    1. En la **Configuración,** vaya a la sección Permisos haga clic en Agregar para ver la lista de permisos admitidos. En la sección Agregar permisos, seleccione los siguientes permisos:

       - Almacenamiento externo (lectura)
       - Almacenamiento externo (escritura)

       A continuación, seleccione **Aceptar**.

       > [!div class="mx-imgBorder"]
      > ![Imagen de la directiva de configuración de la aplicación de creación de aplicaciones de Android.](images/android-create-app-config.png)

    1. Ahora debería ver los dos permisos enumerados y ahora puede autograntar  eligiendo autogrant en la lista desplegable Estado de permisos y, a continuación, **seleccione Siguiente**.

       > [!div class="mx-imgBorder"]
       > ![Imagen de la directiva de configuración de creación automática de aplicaciones de Android.](images/android-auto-grant.png)

    1. En la **página Asignaciones,** seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones. Haga **clic en Seleccionar grupos para** incluir y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.

       > [!div class="mx-imgBorder"]
       > ![Imagen de la directiva de configuración de la aplicación de creación.](images/android-select-group.png)

    1. En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.

        La directiva de configuración de la aplicación para Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.

        > [!div class="mx-imgBorder"]
        > ![Imagen de la revisión de Android crear directiva de configuración de aplicaciones.](images/android-review-create.png)

10. Selecciona **Aplicación ATP de Microsoft Defender** en la lista \> **Propiedades** \> **Asignaciones** \> **Editar**.

    ![Imagen de lista de aplicaciones.](images/mda-properties.png)

11. Asigna la aplicación como *una aplicación* necesaria a un grupo de usuarios. Se instala automáticamente en el perfil de trabajo *durante* la siguiente sincronización del dispositivo mediante Portal de empresa aplicación. Para realizar esta asignación, vaya a la *sección* Obligatorio Agregar \> **grupo,** seleccione el grupo de usuarios y haga clic en **Seleccionar**.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la página editar aplicación.](images/ea06643280075f16265a596fb9a96042.png)

12. En la **página Editar aplicación,** revise toda la información especificada anteriormente. A **continuación, seleccione Revisar + Guardar** y, a continuación, Vuelva **a** guardar para iniciar la asignación.

### <a name="auto-setup-of-always-on-vpn"></a>Configuración automática de VPN always-on

Defender for Endpoint admite directivas de configuración de dispositivos para dispositivos administrados a través de Intune. Esta funcionalidad se puede aprovechar para la configuración automática de **VPN** siempre en Android Enterprise los dispositivos inscritos, por lo que el usuario final no necesita configurar el servicio VPN durante la incorporación.

1. En **Dispositivos,** seleccione **Perfiles de configuración** Crear \> **plataforma** de \>  \> **perfiles Android Enterprise**

   Selecciona **Restricciones de dispositivo en** una de las siguientes opciones, según el tipo de inscripción del dispositivo:
   - **Perfil de trabajo totalmente administrado, dedicado y Corporate-Owned trabajo**
   - **Perfil de trabajo de propiedad personal**

   Seleccione **Crear**.

   > ![Imagen del perfil de configuración de dispositivos Crear.](images/1autosetupofvpn.png)

2. **Configuración Configuración** Proporcione un **nombre y** una **descripción para** identificar de forma única el perfil de configuración.

   > ![Imagen del perfil de configuración de dispositivos Nombre y descripción.](images/2autosetupofvpn.png)

3. Seleccione **Conectividad** y configure VPN:
   - Habilitar **VPN siempre activa**

   Configure un cliente VPN en el perfil de trabajo para conectarse automáticamente y volver a conectarse a la VPN siempre que sea posible. Solo se puede configurar un cliente VPN para VPN siempre en un dispositivo determinado, por lo que asegúrate de que no se implemente más de una directiva VPN siempre en un solo dispositivo.

   - Select **Custom** in VPN client dropdown list

   Vpn personalizada en este caso es Defender for Endpoint VPN, que se usa para proporcionar la característica de protección web.

   > [!NOTE]
   > La aplicación Microsoft Defender para endpoint debe instalarse en el dispositivo del usuario para que funcione la configuración automática de esta VPN.

   - Escribe **El identificador del paquete** de la aplicación Microsoft Defender para endpoint en la Tienda Google Play. Para la dirección URL de la aplicación <https://play.google.com/store/apps/details?id=com.microsoft.scmx> defender, el identificador del paquete **es com.microsoft.scmx**
   - **Modo de bloqueo** No configurado (predeterminado)

     ![La imagen del perfil de configuración de dispositivos habilita vpn siempre activa.](images/3autosetupofvpn.png)

4. **Assignment**

   En la **página Asignaciones,** seleccione el grupo de usuarios al que se asignaría esta directiva de   configuración de aplicaciones. Haga **clic en** Seleccionar grupos para incluir y seleccionar el grupo aplicable y, a continuación, haga clic en **Siguiente**. El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.

     ![Imagen del perfil de configuración de dispositivos Asignación.](images/4autosetupofvpn.png)

5. En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.
El perfil de configuración del dispositivo ahora se asigna al grupo de usuarios seleccionado.

    ![Imagen del perfil de configuración de dispositivos Revisar y crear.](images/5autosetupofvpn.png)

## <a name="check-status-and-complete-onboarding"></a>Comprobar el estado y completar la incorporación

1. Confirme el estado de instalación de Microsoft Defender para Endpoint en Android haciendo clic en **el estado de instalación del dispositivo**. Comprueba que el dispositivo se muestra aquí.

    > [!div class="mx-imgBorder"]
    > ![Imagen del estado de instalación del dispositivo.](images/900c0197aa59f9b7abd762ab2b32e80c.png)

2. En el dispositivo, puedes validar el estado de incorporación yendo al **perfil de trabajo**. Confirme que Defender for Endpoint está disponible y que está inscrito en los dispositivos de propiedad **personal con perfil de trabajo**. Si estás inscrito en un dispositivo de usuario totalmente administrado propiedad de la **empresa,** tendrá un único perfil en el dispositivo donde puedes confirmar que Defender for Endpoint está disponible.

    ![Imagen de la aplicación en un dispositivo móvil.](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. Cuando la aplicación esté instalada, abre la aplicación y acepta los permisos y, a continuación, la incorporación debe ser correcta.

    ![Imagen del dispositivo móvil con la aplicación Microsoft Defender para endpoint](images/MDE_new.png)

4. En esta fase, el dispositivo se incorpora correctamente a Defender para Endpoint en Android. Para comprobar esto en el [Centro de seguridad de Microsoft Defender,](https://securitycenter.microsoft.com) vaya a la página **Dispositivos.**

    ![Imagen del portal de Microsoft Defender para endpoint.](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
