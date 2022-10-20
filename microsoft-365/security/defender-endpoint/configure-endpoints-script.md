---
title: Incorporar dispositivos Windows mediante un script local
description: Use un script local para implementar el paquete de configuración en los dispositivos a fin de habilitar la incorporación de los dispositivos al servicio.
keywords: configurar dispositivos mediante un script local, administración de dispositivos, configuración de dispositivos Microsoft Defender para punto de conexión
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 20f77106a290462ea01e2897c840c1b40e240d51
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621825"
---
# <a name="onboard-windows-devices-using-a-local-script"></a>Incorporar dispositivos Windows mediante un script local

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

También puede incorporar manualmente dispositivos individuales a Defender para punto de conexión. Es posible que quiera hacerlo primero al probar el servicio antes de confirmar la incorporación de todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta diez dispositivos.
> El scripting local es un método de incorporación especial para evaluar Microsoft Defender para punto de conexión.
> La frecuencia de informes de datos se establece con mayor frecuencia que con otros métodos de incorporación al incorporar mediante un script local.
> Esta configuración es para fines de evaluación y normalmente no se usa en implementaciones de producción. Por este motivo, hay preocupaciones sobre el impacto medioambiental, por lo que se recomienda limitar el número de implementaciones mediante scripts locales a diez.
> Si va a realizar la implementación en un entorno de producción como se describió anteriormente, use [otras opciones de implementación](configure-endpoints.md) como समूह नीति o Microsoft Endpoint Configuration Manager.

Consulte el [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para punto de conexión. 

## <a name="onboard-devices"></a>Incorporar dispositivos 

1.  Abra el archivo de .zip del paquete de configuración de GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para la incorporación de servicios. También puede obtener el paquete de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:

    1. En el panel de navegación, seleccione **Configuración** > **Puntos de conexión** > **Incorporación** **de administración de** >  dispositivos.


Consulte el [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  o  [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para punto de conexión.

1. Abra el archivo de .zip del paquete de configuración de GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para la incorporación de servicios. También puede obtener el paquete de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:
    1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** \> **Incorporación** **de administración de** \> dispositivos.
    2. Seleccione Windows 10 o Windows 11 como sistema operativo.
    3. En el campo **Método de implementación** , seleccione **Script local**.
    4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del paquete de configuración en una ubicación del dispositivo que desea incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *WindowsDefenderATPLocalOnboardingScript.cmd*.

3. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

    :::image type="content" source="images/run-as-admin.png" alt-text="El menú Inicio de la ventana que apunta a Ejecutar como administrador" lightbox="images/run-as-admin.png":::

4.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  Presione la tecla **Entrar** o haga clic en **Aceptar**.

Para obtener información sobre cómo puede validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md).

> [!TIP]
> Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un punto de conexión de Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

Para cada dispositivo, puede establecer un valor de configuración para indicar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender para enviar un archivo para un análisis profundo.

Puede configurar manualmente la configuración de uso compartido de ejemplo en el dispositivo mediante *regedit* o creando y ejecutando un archivo *.reg* .

La configuración se establece a través de la siguiente entrada de clave del Registro:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Donde Tipo de nombre es D-WORD. Los posibles valores son:

- 0: no permite el uso compartido de ejemplos desde este dispositivo
- 1: permite compartir todos los tipos de archivo de este dispositivo.

El valor predeterminado en caso de que la clave del Registro no exista es 1.

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecución de una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos fuera del panel con un script local

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:
    1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** \> Administración **de** \> **dispositivos Offboarding**.
    2. Seleccione Windows 10 o Windows 11 como sistema operativo.
    3. En el campo **Método de implementación** , seleccione **Script local**.
    4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los dispositivos. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

      :::image type="content" source="images/run-as-admin.png" alt-text="El menú Inicio de Windows que apunta a la opción Ejecutar como administrador" lightbox="images/run-as-admin.png":::

4. Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5. Presione la tecla **Entrar** o haga clic en **Aceptar**.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo

Puede seguir los diferentes pasos de comprobación en [Solución de problemas de incorporación](troubleshoot-onboarding.md) para comprobar que el script se completó correctamente y que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisión de dispositivos mediante el portal

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.
2. Haga clic en **Inventario de dispositivos**.
3. Compruebe que aparecen los dispositivos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
