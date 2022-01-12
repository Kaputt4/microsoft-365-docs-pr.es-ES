---
title: Incorporar dispositivos Windows mediante un script local
description: Use un script local para implementar el paquete de configuración en dispositivos para habilitar la incorporación de los dispositivos al servicio.
keywords: configurar dispositivos mediante un script local, administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6abd2c26f8557277b4c1b13e5189a42fea9a60f1
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61943393"
---
# <a name="onboard-windows-devices-using-a-local-script"></a>Incorporar dispositivos Windows mediante un script local

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

También puedes incorporar manualmente dispositivos individuales a Defender para endpoint. Es posible que quieras hacerlo primero al probar el servicio antes de comprometerte a incorporar todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta diez dispositivos.
> El scripting local es un método de incorporación especial para evaluar Microsoft Defender para endpoint.
> La frecuencia de informes de datos se establece más alta que con otros métodos de incorporación al incorporar mediante un script local.
> Esta configuración se usa con fines de evaluación y normalmente no se usa en implementaciones de producción. Por este motivo, hay preocupaciones sobre el impacto ambiental, por lo que se recomienda limitar el número de implementaciones mediante scripts locales a diez.
> Si va a implementar en un entorno de producción como se describió anteriormente, [use](configure-endpoints.md) otras opciones de implementación como directiva de grupo o Microsoft Endpoint Configuration Manager.

Consulte el [ARCHIVO PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint. 

## <a name="onboard-devices"></a>Incorporar dispositivos 

1.  Abra el archivo de configuración .zip GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para incorporación de servicios. También puede obtener el paquete desde <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal:</a>

    1. En el panel de navegación, **seleccione Configuración**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.


Consulte el [ARCHIVO PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint.

1. Abra el archivo de configuración .zip GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para incorporación de servicios. También puede obtener el paquete desde <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal:</a>
    1. En el panel de navegación, **seleccione Configuración** \> **Endpoints** \> **Device management** \> **Onboarding**.
    2. Seleccione Windows 10 o Windows 11 como sistema operativo.
    3. En el **campo Método de** implementación, seleccione Script **local**.
    4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extrae el contenido del paquete de configuración en una ubicación en el dispositivo que quieras incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *WindowsDefenderATPLocalOnboardingScript.cmd*.

3. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

    ![Window menú Inicio que apunta a Ejecutar como administrador.](images/run-as-admin.png)

4.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  Presione la **tecla Entrar** o haga clic en **Aceptar**.

Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, vea [Ejecutar una prueba de detección en un](run-detection-test.md)punto de conexión de Microsoft Defender para endpoint recién incorporado.

## <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

Para cada dispositivo, puedes establecer un valor de configuración para especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender enviar un archivo para un análisis profundo.

Puedes configurar manualmente la configuración de uso compartido de ejemplo en el dispositivo mediante *regedit* o creando y ejecutando un *archivo .reg.*

La configuración se establece mediante la siguiente entrada de clave del Registro:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Donde Tipo de nombre es un D-WORD. Los posibles valores son:

- 0: no permite el uso compartido de muestras desde este dispositivo
- 1: permite compartir todos los tipos de archivo desde este dispositivo

El valor predeterminado en caso de que la clave del Registro no exista es 1.

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecutar una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](run-detection-test.md)recién incorporado.

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos offboard con un script local

Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtener el paquete de offboarding desde <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:
    1. En el panel de navegación, **seleccione Configuración** \> **Endpoints** Administración \> **de dispositivos** \> **Offboarding**.
    2. Seleccione Windows 10 o Windows 11 como sistema operativo.
    3. En el **campo Método de** implementación, seleccione Script **local**.
    4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

        ![Window menú Inicio que apunta a Ejecutar como administrador.](images/run-as-admin.png)

4. Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5. Presione la **tecla Entrar** o haga clic en **Aceptar**.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo

Puede seguir los distintos pasos de comprobación en [solucionar](troubleshoot-onboarding.md) problemas de incorporación para comprobar que el script se completó correctamente y que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.
2. Haga clic **en Inventario de dispositivos**.
3. Compruebe que aparecen dispositivos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado](run-detection-test.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
