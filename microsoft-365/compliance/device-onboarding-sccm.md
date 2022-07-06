---
title: Incorporación de dispositivos Windows 10 y Windows 11 mediante Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Use Configuration Manager para implementar el paquete de configuración en los dispositivos de modo que se incorporen al servicio.
ms.openlocfilehash: 3bfeadd0008b548b8193333b3509e82831b162c9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630023"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-configuration-manager"></a>Incorporación de dispositivos Windows 10 y Windows 11 mediante Configuration Manager

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Incorporación de dispositivos mediante System Center Configuration Manager

1. Obtenga el archivo de .zip del paquete de configuración (*DeviceComplianceOnboardingPackage.zip*) de [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/).

2. En el panel de navegación, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> > **Incorporación de** >  dispositivos **.**

3. En el campo **Método de implementación**, seleccione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.

4. Seleccione **Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceComplianceOnboardingScript.cmd*.

6. Implemente el paquete siguiendo los pasos del artículo [Paquetes y programas en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)).

7. Elija una colección de dispositivos predefinida en la que implementar el paquete.

> [!NOTE]
> La protección de la información de Microsoft 365 no admite la incorporación durante la fase [de experiencia rápida (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Asegúrese de que los usuarios completen OOBE después de ejecutar la instalación o actualización de Windows.

> [!TIP]
> Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).
>
> Tenga en cuenta que es posible crear una regla de detección en una aplicación Configuration Manager para comprobar continuamente si se ha incorporado un dispositivo. Una aplicación es un tipo de objeto diferente que un paquete y un programa.
> Si un dispositivo aún no está incorporado (debido a la finalización de OOBE pendiente o por cualquier otro motivo), Configuration Manager volverá a intentar incorporarlo hasta que la regla detecte el cambio de estado.
>
> Este comportamiento se puede realizar mediante la creación de una regla de detección que compruebe si el valor del Registro "OnboardingState" (de tipo REG_DWORD) = 1.
> Este valor del Registro se encuentra en "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Para obtener más información, vea [Configurar métodos de detección en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

Para cada dispositivo, puede establecer un valor de configuración para indicar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Centro de seguridad de Microsoft Defender enviar un archivo para un análisis profundo.

> [!NOTE]
> Normalmente, estas opciones de configuración se realizan a través de Configuration Manager.

Puede establecer una regla de cumplimiento para el elemento de configuración en Configuration Manager para cambiar la configuración del recurso compartido de ejemplo en un dispositivo.

Esta regla debe *ser un elemento* de configuración de regla de cumplimiento que establezca el valor de una clave del Registro en los dispositivos de destino para asegurarse de que son quejas.

La configuración se establece a través de la siguiente entrada de clave del Registro:

```text
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Donde:

El tipo de clave es D-WORD.

Los posibles valores son:

- 0: no permite el uso compartido de ejemplos desde este dispositivo
- 1: permite compartir todos los tipos de archivo de este dispositivo.

El valor predeterminado en caso de que la clave del Registro no exista es 1.

Para obtener más información sobre el cumplimiento de System Center Configuration Manager, consulte [Introducción a la configuración de cumplimiento en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).


## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

Después de incorporar dispositivos al servicio, es importante aprovechar las funcionalidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.

### <a name="device-collection-configuration"></a>Configuración de recopilación de dispositivos

Si usa endpoint Configuration Manager, versión 2002 o posterior, puede optar por ampliar la implementación para incluir servidores o clientes de nivel inferior.

### <a name="next-generation-protection-configuration"></a>Configuración de protección de próxima generación

Se recomiendan los siguientes valores de configuración:

**Escanear**

- Examinar dispositivos de almacenamiento extraíbles, como unidades USB: Sí

**Protección en tiempo real**

- Habilitación de la supervisión del comportamiento: sí
- Habilitar la protección contra aplicaciones potencialmente no deseadas en la descarga y antes de la instalación: Sí

**Servicio de protección en la nube**

- Tipo de pertenencia de Cloud Protection Service: pertenencia avanzada

**Reducción de la superficie expuesta a ataques** Configure todas las reglas disponibles en Auditar.

> [!NOTE]
> Bloquear estas actividades puede interrumpir procesos empresariales legítimos. El mejor enfoque es establecer todo para auditar, identificar cuáles son seguras de activar y, a continuación, habilitar esa configuración en puntos de conexión que no tienen detecciones de falsos positivos.

**Protección de red**

Antes de habilitar la protección de red en modo de auditoría o bloqueo, asegúrese de que ha instalado la actualización de la plataforma antimalware, que se puede obtener de la [página de soporte técnico](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).

**Acceso controlado a carpetas**

Habilite la característica en modo de auditoría durante al menos 30 días. Después de este período, revise las detecciones y cree una lista de aplicaciones que pueden escribir en directorios protegidos.

Para obtener más información, consulte [Evaluación del acceso controlado a carpetas](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).

## <a name="offboard-devices-using-configuration-manager"></a>Dispositivos fuera de la placa con Configuration Manager

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Dispositivos fuera del panel mediante el punto de conexión de Microsoft Configuration Manager rama actual

Si usa Microsoft Endpoint Configuration Manager rama actual, consulte [Creación de un archivo de configuración de offboarding](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivos fuera del panel con System Center 2012 R2 Configuration Manager

1. Obtenga el paquete de offboarding de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>:

2. En el panel de navegación, seleccione Configuración Device onboarding Offboarding (<a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración:**</a> >  **incorporación de**>  dispositivos **fuera del panel de navegación**).

3. Seleccione Windows 10 como sistema operativo.

4. En el campo **Método de implementación**, seleccione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.

5. Seleccione **Descargar paquete** y guarde el archivo .zip.

6. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

7. Implemente el paquete siguiendo los pasos del artículo [Paquetes y programas en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)).

8. Elija una colección de dispositivos predefinida en la que implementar el paquete.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo

Si usa Microsoft Endpoint Configuration Manager rama actual, use el panel de Microsoft Defender para punto de conexión integrado en la consola de Configuration Manager. Para obtener más información, consulte [Protección contra amenazas avanzada de Microsoft Defender: supervisión](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Si usa System Center 2012 R2 Configuration Manager, la supervisión consta de dos partes:

1. Confirmación de que el paquete de configuración se ha implementado correctamente y se está ejecutando (o se ha ejecutado correctamente) en los dispositivos de la red.

2. Comprobar que los dispositivos son compatibles con el servicio de incorporación de dispositivos de Microsoft 365 (esto garantiza que el dispositivo puede completar el proceso de incorporación y puede seguir notificando datos al servicio).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirmación de que el paquete de configuración se ha implementado correctamente

1. En la consola de Configuration Manager, haga clic en **Supervisión** en la parte inferior del panel de navegación.

2. Seleccione **Información general** y, a continuación, **Implementaciones**.

3. Seleccione en la implementación con el nombre del paquete.

4. Revise los indicadores de estado en **Estadísticas de finalización** y **Estado de contenido**.

    Si hay implementaciones **con errores** (dispositivos con errores, **requisitos no cumplidos** o **estados con errores**), es posible que tenga que solucionar los problemas de los dispositivos. Para obtener más información, consulte [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Configuration Manager mostrar una implementación correcta sin errores.](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-endpoint-data-loss-prevention-service"></a>Compruebe que los dispositivos son compatibles con el servicio de prevención de pérdida de datos del punto de conexión.

Puede establecer una regla de cumplimiento para el elemento de configuración en System Center 2012 R2 Configuration Manager para supervisar la implementación.

> [!NOTE]
> Este procedimiento y entrada del Registro se aplican a DLP de punto de conexión, así como a Defender para punto de conexión.

Esta regla debe ser un elemento de configuración de regla de cumplimiento no *correctivo* que supervise el valor de una clave del Registro en los dispositivos de destino.

Supervise la siguiente entrada de clave del Registro:

```text
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Para obtener más información, consulte [Introducción a la configuración de cumplimiento en System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).

## <a name="related-topics"></a>Temas relacionados

- [Incorporación de dispositivos Windows 10 y Windows 11 mediante directiva de grupo](device-onboarding-gp.md)
- [Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 mediante un script local](device-onboarding-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md)
- [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
