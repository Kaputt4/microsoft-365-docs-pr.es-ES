---
title: Implementación manual para ATP de Microsoft Defender para macOS
description: Instale ATP de Microsoft Defender para macOS manualmente, desde la línea de comandos.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 382abd78ffa5e30c79804f9eaed211dffba7589c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070328"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a>Implementación manual de Microsoft Defender para endpoint para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

En este tema se describe cómo implementar Microsoft Defender para Endpoint para macOS manualmente. Una implementación correcta requiere la finalización de todos los pasos siguientes:
- [Descargar paquetes de instalación e incorporación](#download-installation-and-onboarding-packages)
- [Instalación de aplicaciones (macOS 10.15 y versiones anteriores)](#application-installation-macos-1015-and-older-versions)
- [Instalación de aplicaciones (macOS 11 y versiones más recientes)](#application-installation-macos-11-and-newer-versions)
- [Configuración de cliente](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte la página principal de Microsoft Defender para endpoint [para macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

## <a name="download-installation-and-onboarding-packages"></a>Descargar paquetes de instalación e incorporación

Descargue los paquetes de instalación e incorporación del Centro de seguridad de Microsoft Defender:

1. En el Centro de seguridad de Microsoft Defender, vaya **a Configuración > Administración de dispositivos > incorporación**.
2. En la sección 1 de la página, establezca el sistema operativo en **macOS** y el método Deployment en **Script local**.
3. En la sección 2 de la página, seleccione **Descargar paquete de instalación**. Guárdelo como wdav.pkg en un directorio local.
4. En la sección 2 de la página, seleccione **Descargar paquete de incorporación**. Guárdelo WindowsDefenderATPOnboardingPackage.zip en el mismo directorio.

    ![Captura de pantalla del Centro de seguridad de Microsoft Defender](images/atp-portal-onboarding-page.png)

5. Desde un símbolo del sistema, compruebe que tiene los dos archivos.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Instalación de aplicaciones (macOS 10.15 y versiones anteriores)

Para completar este proceso, debes tener privilegios de administrador en el dispositivo.

1. Navegue hasta el wdav.pkg descargado en Finder y ábralo.

    ![Captura de pantalla de instalación de aplicaciones1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. Seleccione **Continuar,** acepte los términos de licencia y escriba la contraseña cuando se le pida.

    ![Captura de pantalla de instalación de la aplicación2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > Se le pedirá que permita que se instale un controlador de Microsoft (ya sea "System Extension Blocked" o "Installation is on hold" o ambos. Se debe permitir la instalación del controlador.

   ![Captura de pantalla de instalación de la aplicación3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. Seleccione **Abrir preferencias de seguridad** o Abrir preferencias del sistema > Seguridad & **privacidad**. Seleccione **Permitir**:

    ![Captura de pantalla de la ventana seguridad y privacidad](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   La instalación continúa.

   > [!CAUTION]
   > Si no selecciona **Permitir,** la instalación continuará después de 5 minutos. Microsoft Defender para endpoint se cargará, pero algunas características, como la protección en tiempo real, se deshabilitarán. Consulte [Solucionar problemas de extensión del kernel](mac-support-kext.md) para obtener información sobre cómo resolver esto.

> [!NOTE]
> macOS puede solicitar reiniciar el dispositivo tras la primera instalación de Microsoft Defender para endpoint. La protección en tiempo real no estará disponible hasta que se reinicie el dispositivo.

## <a name="application-installation-macos-11-and-newer-versions"></a>Instalación de aplicaciones (macOS 11 y versiones más recientes)

Para completar este proceso, debes tener privilegios de administrador en el dispositivo.

1. Navegue hasta el wdav.pkg descargado en Finder y ábralo.

    ![Captura de pantalla de instalación de la aplicación4](images/big-sur-install-1.png)

2. Seleccione **Continuar,** acepte los términos de licencia y escriba la contraseña cuando se le pida.

3. Al final del proceso de instalación, se le promoverá para aprobar las extensiones del sistema usadas por el producto. Seleccione **Abrir preferencias de seguridad**.

    ![Aprobación de extensión del sistema](images/big-sur-install-2.png)

4. En la **ventana Seguridad & privacidad,** seleccione **Permitir**.

    ![Preferencias de seguridad de extensión del sistema1](images/big-sur-install-3.png)

5. Repita los pasos 3 & 4 para todas las extensiones del sistema distribuidas con Microsoft Defender para Endpoint para Mac.

6. Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint para Mac inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender. Cuando se le pida que conceda a Microsoft Defender permisos de extremo para filtrar el tráfico de red, seleccione **Permitir**.

    ![Preferencias de seguridad de extensión del sistema2](images/big-sur-install-4.png)

7. Abra **System Preferences** Security & Privacidad y vaya a la pestaña Privacidad. Conceda permiso de acceso en disco completo a Atp de Microsoft Defender y Extensión de seguridad de punto de conexión de ATP de Microsoft  >   **Defender.**   

    ![Acceso en disco completo](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Configuración de clientes

1. Copia wdav.pkg y MicrosoftDefenderATPOnboardingMacOs.py en el dispositivo donde implementas Microsoft Defender para Endpoint para macOS.

    El dispositivo cliente no está asociado con orgId. Tenga en cuenta que *el atributo orgId* está en blanco.

    ```bash
    mdatp health --field org_id
    ```

2. Ejecute el script de Python para instalar el archivo de configuración:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Comprueba que el dispositivo está asociado a tu organización e informa de un *orgId válido:*

    ```bash
    mdatp health --field org_id
    ```

Después de la instalación, verás el icono de Microsoft Defender en la barra de estado de macOS en la esquina superior derecha.

   ![Icono de Microsoft Defender en la captura de pantalla de la barra de estado](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a>Cómo permitir el acceso en disco completo

> [!CAUTION]
> macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.

Para conceder el consentimiento, abra Preferencias del sistema -> Seguridad & privacidad -> privacidad -> acceso en disco completo. Haga clic en el icono de bloqueo para realizar cambios (parte inferior del cuadro de diálogo). Seleccione Microsoft Defender para Endpoint.

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Consulte [Problemas de instalación de registro](mac-resources.md#logging-installation-issues) para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="uninstallation"></a>Desinstalación

Consulta [Desinstalar para obtener](mac-resources.md#uninstalling) más información sobre cómo quitar Microsoft Defender para Endpoint para macOS de los dispositivos cliente.
