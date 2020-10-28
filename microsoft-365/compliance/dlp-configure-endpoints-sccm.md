---
title: Dispositivos incorporados de Windows 10 con Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use Configuration Manager para implementar el paquete de configuración en dispositivos para que estén integrados en el servicio.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769517"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Dispositivos incorporados de Windows 10 con Configuration Manager

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Administrador de configuración de System Center 2012 R2

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Dispositivos integrados con System Center Configuration Manager

1. Abra el archivo. zip del paquete de configuración de Configuration Manager ( *DeviceComplianceOnboardingPackage.zip* ) que ha descargado del asistente de incorporación de servicios. También puede obtener el paquete del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).

2. En el panel de navegación, seleccione la incorporación de la incorporación de dispositivos de **configuración**  >  **Device Onboarding**  >  **Onboarding** .

3. En el campo **método de implementación** , seleccione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
 
4. Seleccione **Descargar paquete** y guarde el archivo. zip.

5. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que van a implementar el paquete. Debe tener un archivo denominado *DeviceComplianceOnboardingScript. cmd* .

6. Implemente el paquete siguiendo los pasos descritos en el artículo [Packages and Programs del System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

7. Elija una colección de dispositivos predefinida en la que se va a implementar el paquete.

> [!NOTE]
> La prevención de pérdida de datos de extremos de Microsoft 365 no es compatible con la incorporación durante la fase [de la experiencia rápida (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) . Asegúrese de que los usuarios completen OOBE después de ejecutar la instalación o actualización de Windows.

>[!TIP]
> Después de incorporar el dispositivo, puede elegir ejecutar una prueba de detección para comprobar que un dispositivo se incorpora correctamente al servicio. Para obtener más información, vea [ejecutar una prueba de detección en un dispositivo ATP de Microsoft defender recién incorporado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).
>
> Tenga en cuenta que es posible crear una regla de detección en una aplicación de Configuration Manager para comprobar de forma continua si se ha incorporado un dispositivo. Una aplicación es un tipo de objeto diferente que un paquete y un programa.
> Si aún no se ha incorporado un dispositivo (debido a una finalización de OOBE pendiente o a cualquier otro motivo), el administrador de configuración volverá a intentar incorporar el dispositivo hasta que la regla detecte el cambio de estado.
> 
> Este comportamiento se puede lograr creando una regla de detección que compruebe si el valor del registro "OnboardingState" (de tipo REG_DWORD) = 1.
> Este valor del registro se encuentra en "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Para obtener más información, consulte [configurar métodos de detección en System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Configuración de la recopilación de muestras

Para cada dispositivo, puede establecer un valor de configuración para que indique si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través del centro de seguridad de Microsoft defender para enviar un archivo para un análisis detallado.

>[!NOTE]
>Estas opciones de configuración se suelen realizar mediante el administrador de configuración. 

Puede establecer una regla de cumplimiento para el elemento de configuración en Configuration Manager para cambiar la configuración de recurso compartido de muestra en un dispositivo.

Esta regla debe ser un elemento de configuración de la regla de cumplimiento de *corrección* que establece el valor de una clave del registro en los dispositivos de destino para asegurarse de que son quejas.

La configuración se establece a través de la siguiente entrada de clave del registro:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Donde:<br>
El tipo de clave es D-WORD. <br>
Los valores posibles son:
- 0: no permite el uso compartido de muestras desde este dispositivo
- 1-permite el uso compartido de todos los tipos de archivo desde este dispositivo

El valor predeterminado en caso de que la clave del registro no exista es 1.

Para obtener más información acerca del cumplimiento del administrador de configuración de System Center, consulte [Introduction to Compliance Settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas
Después de incorporar los dispositivos al servicio, es importante aprovechar las capacidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.

### <a name="device-collection-configuration"></a>Configuración de la colección de dispositivos
Si está usando el administrador de configuración de extremo, versión 2002 o posterior, puede optar por ampliar la implementación para que incluya servidores o clientes de nivel inferior.


### <a name="next-generation-protection-configuration"></a>Configuración de protección de próxima generación

Se recomiendan las siguientes opciones de configuración:

**Escanear**

- Examinar dispositivos de almacenamiento extraíbles como unidades USB: sí

**Protección en tiempo real**

- Habilitar la supervisión de comportamiento: sí
- Habilitar la protección contra aplicaciones potencialmente no deseadas durante la descarga y antes de la instalación: sí

**Servicio de protección en la nube**

- Tipo de pertenencia del servicio de protección en la nube: pertenencia avanzada

**Reducción** de la superficie de ataques Configure todas las reglas disponibles para auditar.

>[!NOTE]
> El bloqueo de estas actividades puede interrumpir procesos empresariales legítimos. El mejor método es configurar todos los usuarios que se van a auditar, identificar cuáles son seguros para activar y, a continuación, habilitar esa configuración en los extremos que no tienen detecciones de falsos positivos.

**Protección de red**

Antes de habilitar la protección de red en el modo de auditoría o bloqueo, asegúrese de que ha instalado la actualización de la plataforma antimalware, que se puede obtener en la [Página de soporte técnico](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).


**Acceso controlado a carpetas**

Habilite la característica en modo auditoría durante al menos 30 días. Después de este período, revise las detecciones y cree una lista de aplicaciones que puedan escribir en directorios protegidos.

Para obtener más información, consulte [evaluar el acceso controlado a carpetas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).


## <a name="offboard-devices-using-configuration-manager"></a>Dispositivos desincorpora con Configuration Manager

Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó. Los paquetes de retirada expirados enviados a un dispositivo se rechazarán. Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Dispositivos desincorpora que usan la rama actual de Microsoft Endpoint Configuration Manager

Si usa la rama actual de Microsoft Endpoint Configuration Manager, consulte [crear un archivo de configuración de retirada](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivos desincorpora con System Center 2012 R2 Configuration Manager

1. Obtenga el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/):

2. En el panel de navegación, seleccione **configuración** de la  >   **incorporación de dispositivos** de configuración >  **Offboarding** .

3. Seleccione Windows 10 como sistema operativo.

4. En el campo **método de implementación** , seleccione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
    
5. Seleccione **Descargar paquete** y guarde el archivo. zip.

6. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que van a implementar el paquete. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

7. Implemente el paquete siguiendo los pasos descritos en el artículo [Packages and Programs del System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

8. Elija una colección de dispositivos predefinida en la que se va a implementar el paquete.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a cualquier alerta que haya tenido, se conservará durante un máximo de 6 meses.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo

Si está usando la rama actual de Microsoft Endpoint Configuration Manager, use el panel de ATP de Microsoft defender integrado en la consola de Configuration Manager. Para obtener más información, consulte [protección contra amenazas avanzada de Microsoft defender: monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Si utiliza el administrador de configuración de System Center 2012 R2, la supervisión consta de dos partes:

1. Confirmar que el paquete de configuración se ha implementado correctamente y que se está ejecutando (o se ha ejecutado correctamente) en los dispositivos de la red.

2. Comprobando que los dispositivos son compatibles con el servicio de prevención de pérdida de datos de extremos de Microsoft 365 (esto garantiza que el dispositivo pueda completar el proceso de incorporación y pueda seguir notificando datos al servicio).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirmar que el paquete de configuración se ha implementado correctamente

1. En la consola de Configuration Manager, haga clic en **supervisión** en la parte inferior del panel de navegación.

2. Seleccione **información general** y **implementaciones** .

3. Seleccione en la implementación con el nombre del paquete.

4. Revise los indicadores de estado en **estadísticas de finalización** y **Estado de contenido** .

    Si hay implementaciones fallidas (dispositivos con **error** , **requisitos no cumplidos** o **Estados erróneos** ), es posible que deba solucionar los problemas de los dispositivos. Para obtener más información, vea [solucionar problemas de incorporación de protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Administrador de configuración que muestra una implementación correcta sin errores](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Comprobar que los dispositivos son compatibles con el servicio de prevención de pérdida de datos de extremos de Microsoft 365

Puede establecer una regla de cumplimiento para el elemento de configuración en System Center 2012 R2 Configuration Manager para supervisar la implementación.

> [!NOTE]
> Este procedimiento y la entrada del registro se aplican al terminal DLP, así como a la protección contra amenazas avanzada.

Esta regla debe ser un elemento de configuración de regla de cumplimiento *no corregido* que supervise el valor de una clave del registro en los dispositivos de destino.

Supervise la siguiente entrada de clave del registro:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Para obtener más información, vea [Introducción a la configuración de cumplimiento en el administrador de configuración de System Center 2012 R2](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Temas relacionados
- [Dispositivos de Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Dispositivos de Windows 10 incorporados que usan un script local](dlp-configure-endpoints-script.md)
- [Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo ATP de Microsoft defender recién integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
