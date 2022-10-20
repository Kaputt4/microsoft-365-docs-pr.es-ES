---
title: Incorporación de dispositivos Windows mediante Configuration Manager
description: Use Configuration Manager para implementar el paquete de configuración en los dispositivos de modo que se incorporen al servicio Defender para punto de conexión.
keywords: incorporación de dispositivos mediante sccm, administración de dispositivos, configuración de dispositivos Microsoft Defender para punto de conexión
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
ms.date: 09/22/2021
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: f343c6b0d1acb409b081e11f65eb6215ac328199
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647747"
---
# <a name="onboard-windows-devices-using-configuration-manager"></a>Incorporación de dispositivos Windows mediante Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Rama actual de Microsoft Endpoint Configuration Manager
- Administrador de configuración de System Center 2012 R2

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="prerequisites"></a>Requisitos previos
- [Rol de sistema de sitio de punto de Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-site-role)

> [!IMPORTANT]
> El rol de sistema de sitio de punto de Endpoint Protection es necesario para que las directivas de reducción de superficie expuesta a ataques y antivirus se implementen correctamente en los puntos de conexión de destino.  Sin este rol, los puntos de conexión de la colección de dispositivos no recibirán las directivas de reducción de superficie expuesta a ataques y antivirus configuradas.

Puede usar Configuration Manager para incorporar puntos de conexión al servicio Microsoft Defender para punto de conexión. 

Hay varias opciones que puede usar para incorporar dispositivos mediante Configuration Manager:
- [Incorporación de dispositivos mediante System Center Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Asociación de inquilinos](/mem/configmgr/tenant-attach/)



Para Windows Server 2012 R2 y Windows Server 2016: después de completar los pasos de incorporación, deberá [configurar y actualizar System Center Endpoint Protection clientes](onboard-downlevel.md#configure-and-update-system-center-endpoint-protection-clients).

> [!NOTE]
> Defender para punto de conexión no admite la incorporación durante la fase [de experiencia rápida (OOBE).](/windows-hardware/test/assessments/out-of-box-experience) Asegúrese de que los usuarios completen OOBE después de ejecutar la instalación o actualización de Windows.
>
> Tenga en cuenta que es posible crear una regla de detección en una aplicación de Configuration Manager para comprobar continuamente si se ha incorporado un dispositivo. Una aplicación es un tipo de objeto diferente que un paquete y un programa.
> Si un dispositivo aún no está incorporado (debido a la finalización de OOBE pendiente o por cualquier otro motivo), Configuration Manager volverá a intentar incorporarlo hasta que la regla detecte el cambio de estado.
>
> Este comportamiento se puede realizar mediante la creación de una regla de detección que compruebe si el valor del Registro "OnboardingState" (de tipo REG_DWORD) = 1.
> Este valor del Registro se encuentra en "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Para obtener más información, vea [Configurar métodos de detección en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

Para cada dispositivo, puede establecer un valor de configuración para indicar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender para enviar un archivo para un análisis profundo.

> [!NOTE]
> Estas opciones de configuración se suelen realizar a través de Configuration Manager.

Puede establecer una regla de cumplimiento para el elemento de configuración de Configuration Manager para cambiar la configuración del recurso compartido de ejemplo en un dispositivo.

Esta regla debe *ser un elemento* de configuración de regla de cumplimiento que establezca el valor de una clave del Registro en los dispositivos de destino para asegurarse de que son compatibles.

La configuración se establece a través de la siguiente entrada de clave del Registro:

```text
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Donde Tipo de clave es D-WORD. Los posibles valores son:

- 0: No permite el uso compartido de ejemplos desde este dispositivo
- 1: Permite el uso compartido de todos los tipos de archivo de este dispositivo

El valor predeterminado en caso de que la clave del Registro no exista es 1.

Para obtener más información sobre el cumplimiento de System Center Configuration Manager, consulte [Introducción a la configuración de cumplimiento en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

Después de incorporar dispositivos al servicio, es importante aprovechar las funcionalidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.

### <a name="device-collection-configuration"></a>Configuración de recopilación de dispositivos

Si usa Endpoint Configuration Manager, versión 2002 o posterior, puede optar por ampliar la implementación para incluir servidores o clientes de nivel inferior.

### <a name="next-generation-protection-configuration"></a>Configuración de protección de próxima generación

Se recomiendan los siguientes valores de configuración:

#### <a name="scan"></a>Examinar

- Examinar dispositivos de almacenamiento extraíbles, como unidades USB: Sí

#### <a name="real-time-protection"></a>Protección en tiempo real

- Habilitación de la supervisión del comportamiento: sí
- Habilitar la protección contra aplicaciones potencialmente no deseadas en la descarga y antes de la instalación: Sí

#### <a name="cloud-protection-service"></a>Servicio de protección en la nube

- Tipo de pertenencia de Cloud Protection Service: pertenencia avanzada

#### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

Configure todas las reglas disponibles en Auditar.

> [!NOTE]
> Bloquear estas actividades puede interrumpir procesos empresariales legítimos. El mejor enfoque es establecer todo para auditar, identificar cuáles son seguras de activar y, a continuación, habilitar esa configuración en puntos de conexión que no tienen detecciones de falsos positivos.

Para implementar directivas de antivirus (AV) y reducción de superficie expuesta a ataques (ASR) a través de Microsoft Endpoint Configuration Manager (SCCM), siga estos pasos:

- Habilite Endpoint Protection y configure opciones de cliente personalizadas.
- Instale el cliente de Endpoint Protection desde un símbolo del sistema.
- Compruebe la instalación del cliente de Endpoint Protection.

##### <a name="enable-endpoint-protection-and-configure-custom-client-settings"></a>Habilitar Endpoint Protection y configurar opciones de cliente personalizadas
Siga los pasos para habilitar la protección de puntos de conexión y la configuración de la configuración de cliente personalizada:

1. En la consola de Configuration Manager, haga clic en **Administración.**
1. En el área de trabajo **Administración** , haga clic en **Configuración de cliente.**
1. En la pestaña **Inicio** , en el grupo **Crear** , haga clic en **Crear configuración de dispositivo cliente personalizada.**
1. En el cuadro de diálogo **Crear configuración de dispositivo cliente personalizado** , proporcione un nombre y una descripción para el grupo de configuración y, a continuación, seleccione **Endpoint Protection.**
1. Configure los valores de cliente de Endpoint Protection que necesite. Para obtener una lista completa de la configuración de cliente de Endpoint Protection que puede configurar, consulte la sección Endpoint Protection en Acerca de la [configuración de cliente.](/mem/configmgr/core/clients/deploy/about-client-settings#endpoint-protection)

    > [!IMPORTANT]
    > Instale el rol de sistema de sitio de Endpoint Protection antes de configurar los valores de cliente para Endpoint Protection.

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Crear configuración de dispositivo cliente personalizada** . La nueva configuración de cliente se muestra en el nodo **Configuración de cliente** del área de trabajo **Administración** .
1. A continuación, implemente la configuración de cliente personalizada en una colección. Seleccione la configuración de cliente personalizada que desea implementar. En la pestaña **Inicio** , en el grupo **Configuración de cliente** , haga clic en **Implementar.**
1. En el cuadro de diálogo **Seleccionar recopilación** , elija la colección en la que desea implementar la configuración de cliente y, a continuación, haga clic en **Aceptar.** La nueva implementación se muestra en la pestaña **Implementaciones** del panel de detalles.

Los clientes se configuran con esta configuración cuando descargan la directiva de cliente. Para obtener más información, consulte [Inicio de la recuperación de directivas para un cliente de Configuration Manager.](/mem/configmgr/core/clients/manage/manage-clients)


##### <a name="installation-of-endpoint-protection-client-from-a-command-prompt"></a>Instalación del cliente de Endpoint Protection desde un símbolo del sistema
Siga los pasos para completar la instalación del cliente de Endpoint Protection desde el símbolo del sistema.

1. Copie **scepinstall.exe** de la carpeta **Cliente** de la carpeta de instalación de Configuration Manager en el equipo en el que desea instalar el software cliente de Endpoint Protection.
1. Abra un símbolo del sistema como administrador. Cambie el directorio a la carpeta con el instalador. A continuación, ejecute ```scepinstall.exe```, agregando las propiedades adicionales de la línea de comandos que necesite:

     |**Propiedad**  |**Descripción**  |
     |---------|---------|
     |```/s```      |Ejecutar el instalador de forma silenciosa|
     |```/q```      |Extraer los archivos de instalación de forma silenciosa|
     |```/i```      |Ejecutar el instalador con normalidad|
     |```/policy``` |Especificar un archivo de directiva antimalware para configurar el cliente durante la instalación|
     |```/sqmoptin```|Participar en el Programa de mejora de la experiencia del cliente (CEIP) de Microsoft|

1. Siga las instrucciones en pantalla para completar la instalación del cliente.
1. Si descargó el paquete de definición de actualización más reciente, copie el paquete en el equipo cliente y, a continuación, haga doble clic en el paquete de definición para instalarlo.

     > [!NOTE]
     > Una vez completada la instalación del cliente de Endpoint Protection, el cliente realiza automáticamente una comprobación de actualización de definición. Si esta comprobación de actualización se realiza correctamente, no es necesario instalar manualmente el paquete de actualización de definición más reciente.

**Ejemplo: instalación del cliente con una directiva antimalware**

```scepinstall.exe /policy <full path>\<policy file>```

##### <a name="verify-the-endpoint-protection-client-installation"></a>Comprobación de la instalación del cliente de Endpoint Protection

Después de instalar el cliente de Endpoint Protection en el equipo de referencia, compruebe que el cliente funciona correctamente.

1. En el equipo de referencia, abra **System Center Endpoint Protection** desde el área de notificación de Windows.
1. En la pestaña **Inicio** del cuadro de diálogo **System Center Endpoint Protection**, compruebe que **La protección en tiempo real** está establecida en **Activado.**
1. Compruebe que se muestra **Actualizado** para **las definiciones de virus y spyware.**
1. Para asegurarse de que el equipo de referencia está listo para la creación de imágenes, en **Opciones de examen,** seleccione **Completo y,** a continuación, haga clic en **Examinar ahora.**


#### <a name="network-protection"></a>Protección de red

Antes de habilitar la protección de red en modo de auditoría o bloqueo, asegúrese de que ha instalado la actualización de la plataforma antimalware, que se puede obtener de la [página de soporte técnico](https://support.microsoft.com/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).

#### <a name="controlled-folder-access"></a>Acceso controlado a carpetas

Habilite la característica en modo de auditoría durante al menos 30 días. Después de este período, revise las detecciones y cree una lista de aplicaciones que pueden escribir en directorios protegidos.

Para obtener más información, consulte [Evaluación del acceso controlado a carpetas](evaluate-controlled-folder-access.md).

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecución de una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="offboard-devices-using-configuration-manager"></a>Dispositivos fuera del panel con Configuration Manager

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Dispositivos fuera del panel con Microsoft Endpoint Manager rama actual

Si usa Microsoft Endpoint Manager rama actual, consulte [Creación de un archivo de configuración de offboarding](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivos fuera del panel con System Center 2012 R2 Configuration Manager

1. Obtenga el paquete de offboarding de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>:
    1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** \> Administración **de** \>  **dispositivos Offboarding**.
    1. Seleccione Windows 10 o Windows 11 como sistema operativo.
    1. En el campo **Método de implementación**, seleccione **System Center Configuration Manager 2012/2012 R2/1511/1602**.
    1. Seleccione **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Implemente el paquete siguiendo los pasos del artículo [Paquetes y programas en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

   Elija una colección de dispositivos predefinida en la que implementar el paquete.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo

Si usa Microsoft Endpoint Manager rama actual, use el panel integrado de Defender para punto de conexión en la consola de Configuration Manager. Para obtener más información, consulte [Defender para punto de conexión: supervisión](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Si usa System Center 2012 R2 Configuration Manager, la supervisión consta de dos partes:

1. Confirmación de que el paquete de configuración se ha implementado correctamente y se está ejecutando (o se ha ejecutado correctamente) en los dispositivos de la red.

2. Comprobar que los dispositivos son compatibles con el servicio Defender para punto de conexión (esto garantiza que el dispositivo puede completar el proceso de incorporación y puede seguir notificando datos al servicio).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirmación de que el paquete de configuración se ha implementado correctamente

1. En la consola de Configuration Manager, haga clic en **Supervisión** en la parte inferior del panel de navegación.

2. Seleccione **Información general** y, a continuación, **Implementaciones**.

3. Seleccione en la implementación con el nombre del paquete.

4. Revise los indicadores de estado en **Estadísticas de finalización** y **Estado de contenido**.

    Si hay implementaciones **con errores** (dispositivos con errores, **requisitos no cumplidos** o **estados con errores**), es posible que tenga que solucionar los problemas de los dispositivos. Para obtener más información, consulte [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md).

    :::image type="content" source="images/sccm-deployment.png" alt-text="Configuration Manager muestra una implementación correcta sin errores" lightbox="images/sccm-deployment.png":::

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Compruebe que los dispositivos son compatibles con el servicio Microsoft Defender para punto de conexión

Puede establecer una regla de cumplimiento para el elemento de configuración en System Center 2012 R2 Configuration Manager para supervisar la implementación.

Esta regla debe ser un elemento de configuración de regla de cumplimiento no *correctivo* que supervise el valor de una clave del Registro en los dispositivos de destino.

Supervise la siguiente entrada de clave del Registro:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Para obtener más información, consulte [Introducción a la configuración de cumplimiento en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
