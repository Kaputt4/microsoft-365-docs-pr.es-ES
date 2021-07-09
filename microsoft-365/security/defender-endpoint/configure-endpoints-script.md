---
title: Incorporar dispositivos Windows 10 mediante un script local
description: Use un script local para implementar el paquete de configuración en dispositivos para habilitar la incorporación de los dispositivos al servicio.
keywords: configurar dispositivos mediante un script local, administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e15a02753c7a1b346021a4351af24b8fd28315da
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339651"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a>Incorporación de Windows 10 dispositivos con un script local

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

También puedes incorporar manualmente dispositivos individuales a Defender para endpoint. Es posible que quieras hacerlo primero al probar el servicio antes de comprometerte a incorporar todos los dispositivos de la red.

> [!IMPORTANT]
> Este script se ha optimizado para su uso en hasta 10 dispositivos.
>
> Para implementar a escala, use [otras opciones de implementación.](configure-endpoints.md) Por ejemplo, puede implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).

## <a name="onboard-devices"></a>Incorporar dispositivos 

[![Imagen del PDF que muestra las distintas rutas de implementación](images/onboard-script.png)](images/onboard-script.png#lightbox)


Consulte el [ARCHIVO PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint. 


1.  Abra el archivo de configuración .zip GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para incorporación de servicios. También puede obtener el paquete desde [Microsoft 365 Portal de Defender:](https://security.microsoft.com/)

    1. En el panel de navegación, **seleccione Configuración**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.

    1. Seleccione Windows 10 como sistema operativo.

    1. En el **campo Método de** implementación, seleccione Script **local**.

    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

  
2.  Extrae el contenido del paquete de configuración en una ubicación en el dispositivo que quieras incorporar (por ejemplo, el escritorio). Debe tener un archivo denominado *WindowsDefenderATPLocalOnboardingScript.cmd*.

3.  Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

    1.  Vaya a **Inicio** y escriba **cmd**.

    1.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

        ![Ventana menú Inicio apuntar a Ejecutar como administrador](images/run-as-admin.png)

4.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  Presione la **tecla Entrar** o haga clic en **Aceptar**.

Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).


>[!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, vea [Ejecutar una prueba de detección en un](run-detection-test.md)punto de conexión de Microsoft Defender para endpoint recién incorporado.

## <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo
Para cada dispositivo, puedes establecer un valor de configuración para especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender enviar un archivo para un análisis profundo.

Puedes configurar manualmente la configuración de uso compartido de ejemplo en el dispositivo mediante *regedit* o creando y ejecutando un *archivo .reg.*  

La configuración se establece mediante la siguiente entrada de clave del Registro:

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Donde:<br>
El tipo de nombre es un D-WORD. <br>
Los valores posibles son:
- 0: no permite el uso compartido de muestras desde este dispositivo
- 1: permite compartir todos los tipos de archivo desde este dispositivo

El valor predeterminado en caso de que la clave del Registro no exista es 1.


## <a name="offboard-devices-using-a-local-script"></a>Dispositivos offboard con un script local
Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtener el paquete de offboarding desde [Microsoft 365 Defender portal](https://security.microsoft.com/):

    1. En el panel de navegación, **seleccione Configuración**  >  **Endpoints** Administración  >  **de dispositivos**  > **Offboarding**.

    1. Seleccione Windows 10 como sistema operativo.

    1. En el **campo Método de** implementación, seleccione Script **local**.

    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3.  Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

    1.  Vaya a **Inicio** y escriba **cmd**.

    1.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

        ![Ventana menú Inicio apuntar a Ejecutar como administrador](images/run-as-admin.png)

4.  Escriba la ubicación del archivo de script. Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Presione la **tecla Entrar** o haga clic en **Aceptar**.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Puede seguir los distintos pasos de comprobación en [solucionar](troubleshoot-onboarding.md) problemas de incorporación para comprobar que el script se completó correctamente y que el agente se está ejecutando.

La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

### <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya a Microsoft 365 Defender portal.

2. Haga clic **en Inventario de dispositivos**.

3. Compruebe que aparecen dispositivos.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación Windows 10 dispositivos con directiva de grupo](configure-endpoints-gp.md)
- [Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado](run-detection-test.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
