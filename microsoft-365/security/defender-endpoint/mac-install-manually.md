---
title: Implementación manual para Microsoft Defender para endpoint en macOS
description: Instale Microsoft Defender para Endpoint en macOS manualmente, desde la línea de comandos.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 7793a367b591490f3b70055bc5b437eec798cb28
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475991"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación manual para Microsoft Defender para endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink).

En este tema se describe cómo implementar Microsoft Defender para endpoint en macOS manualmente. Una implementación correcta requiere la finalización de todos los pasos siguientes:

- [Descargar paquetes de instalación e incorporación](#download-installation-and-onboarding-packages)
- [Instalación de aplicaciones (macOS 10.15)](#application-installation-macos-1015)
- [Instalación de aplicaciones (macOS 11 y versiones más recientes)](#application-installation-macos-11-and-newer-versions)
- [Configuración de cliente](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulta la página principal de [Microsoft Defender para Endpoint en macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

## <a name="download-installation-and-onboarding-packages"></a>Descargar paquetes de instalación e incorporación

Descargue los paquetes de instalación e incorporación de Microsoft 365 Defender portal:

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, vaya **a Configuración > Endpoints > Administración de dispositivos > incorporación**.
2. En la sección 1 de la página, establezca el sistema operativo en **macOS** y el método Deployment en **Script local**.
3. En la sección 2 de la página, seleccione **Descargar paquete de instalación**. Guárdelo como wdav.pkg en un directorio local.
4. En la sección 2 de la página, seleccione **Descargar paquete de incorporación**. Guárdelo WindowsDefenderATPOnboardingPackage.zip en el mismo directorio.

   :::image type="content" source="images/portal-onboarding-macos.png" alt-text="Opciones para descargar los paquetes de instalación e incorporación" lightbox="images/portal-onboarding-macos.png":::

5. Desde un símbolo del sistema, compruebe que tiene los dos archivos.

## <a name="application-installation-macos-1015"></a>Instalación de aplicaciones (macOS 10.15)

Para completar este proceso, debes tener privilegios de administrador en el dispositivo.

1. Navegue hasta el wdav.pkg descargado en Finder y ábralo.

   :::image type="content" source="images/mdatp-28-appinstall.png" alt-text="La instalación de la aplicación" lightbox="images/mdatp-28-appinstall.png":::

2. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le pida.

   :::image type="content" source="images/mdatp-29-appinstalllogin.png" alt-text="Instalación de la aplicación" lightbox="images/mdatp-29-appinstalllogin.png":::

   > [!IMPORTANT]
   > Se le pedirá que permita que se instale un controlador de Microsoft (ya sea "System Extension Blocked" o "Installation is on hold" o ambos. Se debe permitir la instalación del controlador.

     :::image type="content" source="images/mdatp-30-systemextension.png" alt-text="Instalación de la aplicación" lightbox="images/mdatp-30-systemextension.png":::

3. Seleccione **Abrir preferencias de seguridad** o **Abrir preferencias del sistema > Seguridad & privacidad**. Seleccione **Permitir**:

   :::image type="content" source="images/mdatp-31-securityprivacysettings.png" alt-text="La ventana Seguridad y privacidad" lightbox="images/mdatp-31-securityprivacysettings.png":::

   La instalación continúa.

   > [!CAUTION]
   > Si no selecciona **Permitir, la** instalación continuará después de 5 minutos. Microsoft Defender para endpoint se cargará, pero algunas características, como la protección en tiempo real, se deshabilitarán. Consulte [Solucionar problemas de extensión del kernel](mac-support-kext.md) para obtener información sobre cómo resolver esto.

> [!NOTE]
> macOS puede solicitar reiniciar el dispositivo tras la primera instalación de Microsoft Defender para endpoint. La protección en tiempo real no estará disponible hasta que se reinicie el dispositivo.

## <a name="application-installation-macos-11-and-newer-versions"></a>Instalación de aplicaciones (macOS 11 y versiones más recientes)

Para completar este proceso, debes tener privilegios de administrador en el dispositivo.

1. Navegue hasta el wdav.pkg descargado en Finder y ábralo.

   :::image type="content" source="images/monterey-install-1.png" alt-text="Proceso de instalación de la aplicación" lightbox="images/monterey-install-1.png":::

2. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le pida.

3. Al final del proceso de instalación, se te promocionará para aprobar las extensiones del sistema usadas por el producto. Seleccione **Abrir preferencias de seguridad**.

   :::image type="content" source="images/monterey-install-2.png" alt-text="Aprobación de extensión del sistema" lightbox="images/monterey-install-2.png":::

4. En la **ventana Seguridad & privacidad** , seleccione **Permitir**.

   :::image type="content" source="images/monterey-install-3.png" alt-text="Preferencias de seguridad de extensión del sistema1" lightbox="images/monterey-install-3.png":::

5. Repita los pasos 3 & 4 para todas las extensiones del sistema distribuidas con Microsoft Defender para Endpoint en Mac.

6. Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint en Mac inspecciona el tráfico de sockets e informa esta información al portal de Microsoft 365 Defender. Cuando se le pida que conceda a Microsoft Defender permisos de extremo para filtrar el tráfico de red, seleccione **Permitir**.

   :::image type="content" source="images/monterey-install-4.png" alt-text="Preferencias de seguridad de extensión del sistema2" lightbox="images/monterey-install-4.png":::

7. Abra **System Preferences** \> **Security & Privacidad** y vaya a la pestaña Privacidad.  Conceda permiso de acceso  en disco completo a **Microsoft Defender** y Microsoft **Defenders Endpoint Security Extension**.

   :::image type="content" source="images/monterey-install-5.png" alt-text="Acceso en disco completo" lightbox="images/monterey-install-5.png":::

## <a name="client-configuration"></a>Configuración de clientes

1. Copia wdav.pkg y MicrosoftDefenderATPOnboardingMacOs.py en el dispositivo donde implementas Microsoft Defender para Endpoint en macOS.

    El dispositivo cliente no está asociado con org_id. Tenga en cuenta *que el org_id* está en blanco.

    ```bash
    mdatp health --field org_id
    ```

2. Ejecute el script de Python para instalar el archivo de configuración:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Compruebe que el dispositivo esté asociado a su organización e informe de un identificador de organización válido:

    ```bash
    mdatp health --field org_id
    ```

    Después de la instalación, verás el icono de Microsoft Defender en la barra de estado de macOS en la esquina superior derecha.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="El icono de Microsoft Defender en la barra de estado" lightbox="images/mdatp-icon-bar.png":::

## <a name="how-to-allow-full-disk-access"></a>Cómo permitir el acceso en disco completo

> [!CAUTION]
> macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.

1. Para conceder el consentimiento, abra **System Preferences** \> **Security & Privacy** \> **Full** \> **Disk Access**. Haga clic en el icono de bloqueo para realizar cambios (parte inferior del cuadro de diálogo). Seleccione Microsoft Defender para Endpoint.

2. Ejecute una prueba de detección de ANTIVIRUS para comprobar que el dispositivo está correctamente incorporado e informando al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

    1. Asegúrese de que la protección en tiempo real está habilitada (lo indica un resultado de 1 al ejecutar el siguiente comando):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Abra una ventana terminal. Copie y ejecute el siguiente comando:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. El archivo debería haber sido puesto en cuarentena por Defender para Endpoint en Mac. Use el siguiente comando para enumerar todas las amenazas detectadas:

        ```bash
        mdatp threat list
        ```

3. Ejecute una EDR de detección para comprobar que el dispositivo está correctamente incorporado e informando al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

   1. En el explorador, como Microsoft Edge para Mac o Safari.

   1. Descargue MDATP MacOS DIY.zip y https://aka.ms/mdatpmacosdiy extraiga.

      Es posible que se le pida lo siguiente:

      > ¿Desea permitir descargas en "mdatpclientanalyzer.blob.core.windows.net"?<br/>
      > Puede cambiar los sitios web que pueden descargar archivos en Preferencias de sitios web.

4. Haga clic **en Permitir**.

5. Abra **Descargas**.

6. Debería ver **MDATP MacOS DIY**.

   > [!TIP]
   > Si hace doble clic, recibirá el siguiente mensaje:
   >
   > > **"MDATP MacOS DIY" no se puede abrir porque el desarrollador no puede ser verificador.**<br/>
   > > macOS no puede comprobar que esta aplicación está libre de malware.<br/>
   > > **\[Pasar a Cancelar papelera\]** **\[\]**

7. Haga clic en **Cancelar**.

8. Haga clic con el botón **secundario en MDATP MacOS DIY** y, a continuación, haga clic en **Abrir**.

    El sistema debe mostrar el siguiente mensaje:

    > **macOS no puede comprobar el desarrollador de MDATP MacOS DIY. ¿Está seguro de que desea abrirlo?**<br/>
    > Al abrir esta aplicación, invalidará la seguridad del sistema, que puede exponer su equipo y su información personal a malware que pueda dañar su Mac o poner en peligro su privacidad.

9. Haga clic en **Open** (Abrir).

    El sistema debe mostrar el siguiente mensaje:

    > Microsoft Defender para endpoint: macOS EDR de prueba de BRICOLAJE<br/>
    > La alerta correspondiente estará disponible en el portal MDATP.

10. Haga clic en **Open** (Abrir).

    En unos minutos se debe generar una alerta denominada "macOS EDR test alert".

11. Vaya a Microsoft 365 Defender portal (https://security.microsoft.com/).

12. Vaya a la cola de alertas.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Una alerta de prueba EDR macOS que muestra gravedad, categoría, origen de detección y un menú de acciones contraído" lightbox="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png":::

    Consulta los detalles de la alerta y la escala de tiempo del dispositivo y realiza los pasos de investigación habituales.

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Consulte [Problemas de instalación de registro](mac-resources.md#logging-installation-issues) para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="uninstallation"></a>Desinstalación

Consulta [Desinstalar para obtener](mac-resources.md#uninstalling) más información sobre cómo quitar Microsoft Defender para Endpoint en macOS de los dispositivos cliente.
