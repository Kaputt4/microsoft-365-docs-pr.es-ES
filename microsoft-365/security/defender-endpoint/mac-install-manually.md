---
title: Implementación manual para Microsoft Defender para punto de conexión en macOS
description: Instale Microsoft Defender para punto de conexión en macOS manualmente, desde la línea de comandos.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 68f91e4b8f789087aacea14b6b2a8a8b67262fd0
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159627"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación manual para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una evaluación gratuita](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink).

En este tema se describe cómo implementar Microsoft Defender para punto de conexión en macOS manualmente. Una implementación correcta requiere la finalización de todos los pasos siguientes:

- [Descarga de paquetes de instalación e incorporación](#download-installation-and-onboarding-packages)
- [Instalación de aplicaciones (macOS 10.15)](#application-installation-macos-1015)
- [Instalación de aplicaciones (macOS 11 y versiones más recientes)](#application-installation-macos-11-and-newer-versions)
- [Configuración del cliente](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte [la Microsoft Defender para punto de conexión principal en macOS página](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

## <a name="download-installation-and-onboarding-packages"></a>Descarga de paquetes de instalación e incorporación

Descargue los paquetes de instalación e incorporación de Microsoft 365 Defender portal:

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, vaya a **Configuración > Puntos de conexión > Administración de dispositivos > Incorporación**.
2. En la sección 1 de la página, establezca el sistema operativo en **macOS** y el método deployment en **Script local**.
3. En la sección 2 de la página, seleccione **Descargar paquete de instalación**. Guárdelo como wdav.pkg en un directorio local.
4. En la sección 2 de la página, seleccione **Descargar paquete de incorporación**. Guárdelo como WindowsDefenderATPOnboardingPackage.zip en el mismo directorio.

   :::image type="content" source="images/portal-onboarding-macos.png" alt-text="Opciones para descargar los paquetes de instalación e incorporación" lightbox="images/portal-onboarding-macos.png":::

5. Desde un símbolo del sistema, compruebe que tiene los dos archivos.

## <a name="application-installation-macos-1015"></a>Instalación de aplicaciones (macOS 10.15)

Para completar este proceso, debe tener privilegios de administrador en el dispositivo.

1. Vaya al archivo wdav.pkg descargado en Finder y ábralo.

   :::image type="content" source="images/mdatp-28-appinstall.png" alt-text="La instalación de la aplicación" lightbox="images/mdatp-28-appinstall.png":::

2. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le solicite.

   :::image type="content" source="images/mdatp-29-appinstalllogin.png" alt-text="Instalación de la aplicación" lightbox="images/mdatp-29-appinstalllogin.png":::

   > [!IMPORTANT]
   > Se le pedirá que permita instalar un controlador de Microsoft (ya sea "Extensión del sistema bloqueada" o "La instalación está en espera" o ambas. Se debe permitir que se instale el controlador.

     :::image type="content" source="images/mdatp-30-systemextension.png" alt-text="Instalación de la aplicación" lightbox="images/mdatp-30-systemextension.png":::

3. Seleccione **Abrir preferencias de seguridad** o **Abrir preferencias del sistema > seguridad & privacidad**. Seleccione **Permitir**:

   :::image type="content" source="images/mdatp-31-securityprivacysettings.png" alt-text="Ventana Seguridad y privacidad" lightbox="images/mdatp-31-securityprivacysettings.png":::

   La instalación continúa.

   > [!CAUTION]
   > Si no selecciona **Permitir**, la instalación continuará después de 5 minutos. Microsoft Defender para punto de conexión se cargarán, pero algunas características, como la protección en tiempo real, se deshabilitarán. Consulte [Solución de problemas de extensión de kernel](mac-support-kext.md) para obtener información sobre cómo resolverlo.

> [!NOTE]
> macOS puede solicitar reiniciar el dispositivo en la primera instalación de Microsoft Defender para punto de conexión. La protección en tiempo real no estará disponible hasta que se reinicie el dispositivo.

## <a name="application-installation-macos-11-and-newer-versions"></a>Instalación de aplicaciones (macOS 11 y versiones más recientes)

Para completar este proceso, debe tener privilegios de administrador en el dispositivo.

1. Vaya al archivo wdav.pkg descargado en Finder y ábralo.

   :::image type="content" source="images/monterey-install-1.png" alt-text="Proceso de instalación de la aplicación" lightbox="images/monterey-install-1.png":::

2. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le solicite.

3. Al final del proceso de instalación, se le promoverá para aprobar las extensiones del sistema usadas por el producto. Seleccione **Abrir preferencias de seguridad**.

   :::image type="content" source="images/monterey-install-2.png" alt-text="Aprobación de la extensión del sistema" lightbox="images/monterey-install-2.png":::

4. En la ventana **Seguridad & privacidad** , seleccione **Permitir**.

   :::image type="content" source="images/monterey-install-3.png" alt-text="Preferencias de seguridad de la extensión del sistema1" lightbox="images/monterey-install-3.png":::

5. Repita los pasos 3 & 4 para todas las extensiones del sistema distribuidas con Microsoft Defender para punto de conexión en Mac.

6. Como parte de las funcionalidades de detección y respuesta de puntos de conexión, Microsoft Defender para punto de conexión en Mac inspecciona el tráfico de socket e informa de esta información al portal de Microsoft 365 Defender. Cuando se le pida que conceda permisos de Microsoft Defender para punto de conexión para filtrar el tráfico de red, seleccione **Permitir**.

   :::image type="content" source="images/monterey-install-4.png" alt-text="Preferencias de seguridad de la extensión del sistema2" lightbox="images/monterey-install-4.png":::

7. Abra **Preferencias** \> del sistema **Seguridad & privacidad** y vaya a la pestaña **Privacidad** . Conceda permiso **de acceso total al disco** a **Microsoft Defender** y a la **extensión de seguridad del punto de conexión de Microsoft Defenders**.

   :::image type="content" source="images/monterey-install-5.png" alt-text="Acceso al disco completo" lightbox="images/monterey-install-5.png":::

## <a name="client-configuration"></a>Configuración de clientes

1. Copie wdav.pkg y MicrosoftDefenderATPOnboardingMacOs.sh en el dispositivo donde implemente Microsoft Defender para punto de conexión en macOS.

    El dispositivo cliente no está asociado a org_id. Tenga en cuenta que el atributo *org_id* está en blanco.

    ```bash
    mdatp health --field org_id
    ```

2. Ejecute el script de Bash para instalar el archivo de configuración:

    ```bash
    Sudo bash -x MicrosoftDefenderATPOnboardingMacOs.sh
    ```

3. Compruebe que el dispositivo ahora está asociado a su organización e informa de un identificador de organización válido:

    ```bash
    mdatp health --field org_id
    ```

    Después de la instalación, verá el icono de Microsoft Defender en la barra de estado macOS de la esquina superior derecha.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="Icono de Microsoft Defender en la barra de estado" lightbox="images/mdatp-icon-bar.png":::

## <a name="how-to-allow-full-disk-access"></a>Cómo permitir el acceso completo al disco

> [!CAUTION]
> macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como documentos, descargas, escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para punto de conexión no puede proteger completamente el dispositivo.

1. Para conceder el consentimiento, abra **Preferencias** \> **del sistema Seguridad &** \> **privacidad** \> **Acceso completo al disco**. Haga clic en el icono de bloqueo para realizar cambios (parte inferior del cuadro de diálogo). Seleccione Microsoft Defender para punto de conexión.

2. Ejecute una prueba de detección de ANTIVIRUS para comprobar que el dispositivo está incorporado correctamente e informar al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

    1. Asegúrese de que la protección en tiempo real está habilitada (indicada por el resultado de 1 de la ejecución del siguiente comando):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Abra una ventana terminal. Copie y ejecute el siguiente comando:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. Defender para punto de conexión en Mac debería haber puesto en cuarentena el archivo. Use el siguiente comando para enumerar todas las amenazas detectadas:

        ```bash
        mdatp threat list
        ```

3. Ejecute una prueba de detección de EDR para comprobar que el dispositivo está incorporado correctamente e informar al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

   1. En el explorador, como Microsoft Edge para Mac o Safari.

   1. Descargue MDATP MacOS DIY.zip de https://aka.ms/mdatpmacosdiy y extraiga.

      Es posible que se le pida lo siguiente:

      > ¿Desea permitir descargas en "mdatpclientanalyzer.blob.core.windows.net"?<br/>
      > Puede cambiar qué sitios web pueden descargar archivos en Preferencias de sitios web.

4. Haga clic en **Permitir**.

5. Abra **Descargas**.

6. Debería ver **MDATP MacOS DIY**.

   > [!TIP]
   > Si hace doble clic, recibirá el siguiente mensaje:
   >
   > > **No se puede abrir "MDATP MacOS DIY" porque el desarrollador no puede ser comprobador.**<br/>
   > > macOS no puede comprobar que esta aplicación está libre de malware.<br/>
   > > **\[Mover a la papelera\]** **\[Cancelar\]**

7. Haga clic en **Cancelar**.

8. Haga clic con el botón derecho en **MDATP MacOS DIYy**, a continuación, haga clic en **Abrir**.

    El sistema debe mostrar el siguiente mensaje:

    > **macOS no puede comprobar el desarrollador de MDATP MacOS DIY. ¿Está seguro de que desea abrirlo?**<br/>
    > Al abrir esta aplicación, se reemplazará la seguridad del sistema que puede exponer su equipo y la información personal a malware que puede dañar su Mac o poner en peligro su privacidad.

9. Haga clic en **Open** (Abrir).

    El sistema debe mostrar el siguiente mensaje:

    > Microsoft Defender para punto de conexión: macOS EDR archivo de prueba DE BRICOLAJE<br/>
    > La alerta correspondiente estará disponible en el portal de MDATP.

10. Haga clic en **Open** (Abrir).

    En unos minutos se debe generar una alerta denominada "macOS EDR alerta de prueba".

11. Vaya a Microsoft 365 Defender portal (https://security.microsoft.com/).

12. Vaya a la cola de alertas.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Una macOS EDR alerta de prueba que muestra la gravedad, la categoría, el origen de detección y un menú contraído de acciones" lightbox="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png":::

    Examine los detalles de la alerta y la escala de tiempo del dispositivo y realice los pasos de investigación normales.

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Consulte [Problemas de instalación de registro](mac-resources.md#logging-installation-issues) para obtener más información sobre cómo buscar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="uninstallation"></a>Desinstalación

Consulte [Desinstalación](mac-resources.md#uninstalling) para obtener más información sobre cómo quitar Microsoft Defender para punto de conexión en macOS de dispositivos cliente.
