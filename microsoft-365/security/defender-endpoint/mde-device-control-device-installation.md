---
title: Instalación de dispositivos de control de dispositivos de Microsoft Defender para endpoint
description: En este tema se proporciona un recorrido por la instalación de dispositivos de control de dispositivos de punto de conexión de Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b56f6ba5cc481de7c295305ab1d5abfbec68cd4
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662303"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Instalación de dispositivos de control de dispositivos de Microsoft Defender para endpoint 

Microsoft Defender para endpoint device control removable Storage Access Control permite realizar la siguiente tarea:

- Impedir que las personas instalen dispositivos específicos.
- Permitir que las personas instalen dispositivos específicos pero evitar que otros.

> [!NOTE]
> Para encontrar la diferencia entre la instalación de dispositivos y el control de acceso de almacenamiento extraíble, consulta Microsoft Defender para Endpoint [Device Control Removable Storage Protection](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true).

|Privilegio|Permiso|
|---|---|
|Access|Instalación del dispositivo |
|Modo de acción|Allow, Prevent |
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en usuarios|No|
|Compatibilidad basada en máquina|Sí|

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente la instalación de dispositivos Windows 10 dispositivos, Windows Server 2022.

## <a name="device-properties"></a>Propiedades de dispositivo

Las siguientes propiedades del dispositivo son compatibles con la instalación de dispositivos:

- Id. de dispositivo 
- Id. de hardware 
- Id. compatible 
- Clase device 
- Tipo de dispositivo "Dispositivo extraíble": algunos dispositivos pueden clasificarse como dispositivo extraíble. Un dispositivo se considera extraíble cuando el controlador del dispositivo al que está conectado indica que el dispositivo es extraíble. Por ejemplo, los controladores del concentrador USB al que está conectado el dispositivo informan de que un dispositivo USB es extraíble. Para obtener más información, consulta [Instalación del dispositivo en Windows](/windows/client-management/manage-device-installation-with-group-policy).

## <a name="policies"></a>Directivas

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>Permitir la instalación de dispositivos que coincidan con cualquiera de estos IDs de dispositivo

Esta configuración de directiva le permite especificar una lista de los IDs de hardware plug and play y los IDs compatibles para dispositivos que Windows pueden instalar. Esta configuración de directiva está diseñada para usarse solo cuando la configuración de directiva Aplicar orden de evaluación por capas para **Permitir** e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos está habilitada.

Cuando esta configuración de directiva  está habilitada junto con la opción Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos, Windows puede instalar o actualizar cualquier dispositivo cuyo identificador de hardware plug and play o id. compatible aparezca en la lista que cree, a menos que otra configuración de directiva en la misma capa o superior de la jerarquía impida específicamente esa instalación,  como la siguiente configuración de directiva:

- Impedir la instalación de dispositivos que coincidan con estos IDs de dispositivo.
- Impedir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo.

Si  la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación. 

> [!NOTE]
> La  configuración de directiva Impedir la instalación de dispositivos  no descrita por otras configuraciones de directiva se ha reemplazado por la opción Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos para las versiones de destino Windows 10 compatibles. Se recomienda usar la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia **de** dispositivos cuando sea posible.

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>Permitir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo 

Esta configuración de directiva te permite especificar una lista de los IDs de instancia de dispositivo Plug and Play para dispositivos que Windows pueden instalar. Esta configuración de directiva está diseñada para usarse solo cuando la configuración de directiva Aplicar orden de evaluación por capas para **Permitir** e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos está habilitada. 

Cuando esta configuración de directiva  está habilitada junto con la opción Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las opciones de directiva de criterios de coincidencia de dispositivos, Windows puede instalar o actualizar cualquier dispositivo cuyo identificador de instancia de dispositivo Plug and Play aparezca en la lista que cree, a menos que otra configuración de directiva en la misma capa o superior de la jerarquía impida específicamente esa instalación,  como la siguiente configuración de directiva:

- Impedir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo 

Si  la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación. 

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>Permitir la instalación de dispositivos con controladores que coincidan con estas clases de configuración de dispositivos 

Esta configuración de directiva te permite especificar una lista de identificadores únicos globales (GUID) de la clase de configuración de dispositivo para los paquetes de controladores que Windows pueden instalarse. Esta configuración de directiva está diseñada para usarse solo cuando la configuración de directiva Aplicar orden de evaluación por capas para **Permitir** e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos está habilitada.

Cuando esta configuración de directiva  está habilitada junto con el orden de evaluación Aplicar orden de evaluación en capas para permitir y evitar directivas de instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos, Windows puede instalar o actualizar paquetes de controladores cuyos GUID de clase de configuración de dispositivo aparecen en la lista que cree, a menos que otra configuración de directiva en la misma capa o superior de la jerarquía impida específicamente esa instalación,  como la siguiente configuración de directiva: 

- Impedir la instalación de dispositivos para estas clases de dispositivo 
- Impedir la instalación de dispositivos que coincidan con estos IDs de dispositivo 
- Impedir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo 

Si  la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación.

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>Aplicar el orden de evaluación por capas para las directivas de instalación de dispositivos permitir e impedir en todos los criterios de coincidencia de dispositivos 

Esta configuración de directiva cambiará el orden de evaluación en el que se aplica la configuración de directiva Permitir e Impedir cuando se aplique más de una configuración de directiva de instalación para un dispositivo determinado. Habilite esta configuración de directiva para asegurarse de que los criterios de coincidencia de dispositivos superpuestos se aplican en función de una jerarquía establecida en la que los criterios de coincidencia más específicos sustituyen a criterios de coincidencia menos específicos. El orden jerárquico de evaluación de la configuración de directiva que especifica los criterios de coincidencia de dispositivos es el siguiente:

**Los IDs de instancia de dispositivo > de dispositivos > clase de configuración de dispositivo > dispositivos extraíbles**

#### <a name="device-instance-ids"></a>IDs de instancia de dispositivo 

1. Impedir la instalación de dispositivos con controladores que coincidan con estos IDs de instancia de dispositivo.
2. Permitir la instalación de dispositivos con controladores que coincidan con estos IDs de instancia de dispositivo.

#### <a name="device-ids"></a>Id. de dispositivos 

1. Impedir la instalación de dispositivos con controladores que coincidan con estos IDs de dispositivo.
2. Permitir la instalación de dispositivos con controladores que coincidan con estos IDs de dispositivo.

#### <a name="device-setup-class"></a>Clase de configuración de dispositivos 

1. Impedir la instalación de dispositivos con controladores que coincidan con estas clases de configuración del dispositivo.
2. Permitir la instalación de dispositivos con controladores que coincidan con estas clases de configuración del dispositivo.

#### <a name="removable-devices"></a>Dispositivos extraíbles 

Impedir la instalación de dispositivos extraíbles 

> [!NOTE]
> Esta configuración de directiva proporciona un control más detallado que la configuración impedir la instalación de dispositivos no **descrita por otras** configuraciones de directiva. Si estas configuraciones de directiva en conflicto  están habilitadas al mismo tiempo, se habilitará la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos y se omitirá la otra configuración de directiva. 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>Impedir la instalación de dispositivos que coincidan con cualquiera de estos IDs de dispositivo 

Esta configuración de directiva te permite especificar una lista de los IDs de hardware plug and play e IDs compatibles para dispositivos que Windows se impide la instalación. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que Windows instalar un dispositivo.

> [!NOTE]
> Para habilitar la configuración de directiva Permitir la instalación de dispositivos que coincidan con  cualquiera de estos **IDs** de instancia de dispositivo para reemplazar esta configuración de directiva para los dispositivos aplicables, habilite la opción Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todas las directivas de criterios de coincidencia de dispositivos. 

Si habilitas esta configuración de directiva, Windows no podrá instalar un dispositivo cuyo identificador de hardware o id. compatible aparezca en la lista que crees. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilitas o no configuras esta configuración de directiva, los dispositivos se pueden instalar y actualizar según lo permitido o impedido por otras configuraciones de directiva. 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>Impedir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo 

Esta configuración de directiva te permite especificar una lista de los IDs de instancia de dispositivo Plug and Play para dispositivos que Windows no se puedan instalar. Esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que Windows para instalar un dispositivo. 

Si habilitas esta configuración de directiva, Windows se impide instalar un dispositivo cuyo identificador de instancia de dispositivo aparece en la lista que crees. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto. 

Si deshabilitas o no configuras esta configuración de directiva, los dispositivos se pueden instalar y actualizar según lo permitido o impedido por otras configuraciones de directiva. 

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>Impedir la instalación de dispositivos con controladores que coincidan con estas clases de configuración de dispositivos 

Esta configuración de directiva te permite especificar una lista de identificadores únicos globales (GUID) de la clase de configuración de dispositivo para paquetes de controladores que Windows no se puedan instalar. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que Windows instalar un dispositivo.

> [!NOTE]
> Para habilitar la opción Permitir la instalación de dispositivos que coincidan con cualquiera de estos **IDs** de dispositivo y Permitir  la instalación de dispositivos que coincidan con cualquiera de estas configuraciones de directiva de IDs de instancia de dispositivo para reemplazar esta configuración de directiva para los **dispositivos aplicables,** habilita la configuración de directiva Aplicar orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos.

Si habilitas esta configuración de directiva, Windows se impide instalar o actualizar paquetes de controladores cuyos GUID de clase de configuración del dispositivo aparecen en la lista que crees. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto. 

Si deshabilitas o no configuras esta configuración de directiva, Windows instalar y actualizar dispositivos según lo permitido o impedido por otras configuraciones de directiva. 

### <a name="prevent-installation-of-removable-devices"></a>Impedir la instalación de dispositivos extraíbles 

Esta configuración de directiva le permite evitar que Windows instalar dispositivos extraíbles. Un dispositivo se considera extraíble cuando el controlador del dispositivo al que está conectado indica que el dispositivo es extraíble. Por ejemplo, los controladores del concentrador USB al que está conectado el dispositivo notifican que un dispositivo de bus serie universal (USB) es extraíble. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que Windows instalar un dispositivo. 

> [!NOTE]
> Para habilitar la instalación de dispositivos con controladores que coincidan con estas clases de configuración de **dispositivos**, Permitir la instalación de dispositivos que coincidan con cualquiera  de estos **IDs** de dispositivo y Permitir la instalación de dispositivos que coincidan con cualquiera de estas configuraciones de directiva de IDs de instancia de dispositivo para reemplazar esta configuración de directiva para **dispositivos aplicables,** habilite el orden de evaluación Aplicar en capas para permitir e impedir la instalación de dispositivos en todas las configuraciones de directiva de criterios de coincidencia de dispositivos.

Si habilitas esta configuración de directiva, Windows se impide instalar dispositivos extraíbles y los dispositivos extraíbles existentes no pueden tener actualizados sus controladores. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta a la redirección de dispositivos extraíbles desde un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilitas o no configuras esta configuración de directiva, Windows instalar y actualizar paquetes de controladores para dispositivos extraíbles según lo permitido o impedido por otras configuraciones de directiva.

## <a name="common-removable-storage-access-control-scenarios"></a>Escenarios comunes Storage control de acceso extraíble

Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>Escenario 1: Impedir la instalación de todos los dispositivos USB al permitir la instalación de solo una unidad usb autorizada 

Para este escenario, se usarán las siguientes directivas:

- Impedir la instalación de dispositivos con controladores que coincidan con estas clases de configuración del dispositivo.
- Aplicar el orden de evaluación por capas para permitir e impedir la instalación de dispositivos en todos los criterios de coincidencia de dispositivos.
- Permitir la instalación de dispositivos que coincidan con cualquiera de estos IDs de instancia de dispositivo o Permitir la instalación de dispositivos que coincidan con cualquiera de estos IDs de dispositivo.

#### <a name="deploying-and-managing-policy-via-intune"></a>Implementación y administración de directivas a través de Intune 

La característica de instalación de dispositivos te permite aplicar directivas a través de Intune al dispositivo.

#### <a name="licensing"></a>Licencias 

Antes de empezar con la instalación del dispositivo, debes confirmar tu [Microsoft 365 suscripción](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar la instalación del dispositivo, debes tener Microsoft 365 E3.

#### <a name="permission"></a>Permiso 

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos:  

- Rol Administrador de directivas y perfiles
- O rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos
- O Administrador global

#### <a name="deploying-policy"></a>Implementación de directivas 

En Microsoft Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)  

1. Configurar **Impedir la instalación de dispositivos con controladores que coincidan con estas clases de configuración del dispositivo**.

    - Abra Endpoint security > Attack surface reduction > Create Policy > Platform: Windows 10 (y posterior) & Profile: Device control.
    
      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="editar perfil":::
    
2. Conecta un dispositivo USB y verás el siguiente mensaje de error:

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="mensaje de error":::

3. Habilitar Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación **de dispositivos en todos los criterios de coincidencia de dispositivos.**

    - **solo admiten OMA-URI** por ahora: Dispositivos > Perfiles de configuración > Crear perfiles > Plataforma: Windows 10 (y posterior) &: Personalizado
    
      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="editar fila":::

4. Habilitar y agregar el identificador de instancia USB permitido: permitir la instalación de **dispositivos que coincidan** con cualquiera de estos identificadores de dispositivo .

    - Actualizar el perfil de control de dispositivo del paso 1
    
      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="devicecontrol":::
       
    Agregar PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1 &HOST; USB\ROOT_HUB30; USB\ROOT_HUB20; USB\USB20_HUB en la captura de pantalla superior se debe a que no basta con habilitar un solo identificador de hardware para habilitar una única unidad usb. Debes asegurarte de que todos los dispositivos USB que preceden al destino no están bloqueados (permitidos). Puedes abrir el Administrador de dispositivos y cambiar la vista a "Dispositivos por conexiones" para ver cómo se instalan los dispositivos en el árbol PnP. En nuestro caso, se deben permitir los siguientes dispositivos para que también se pueda permitir la unidad usb de destino: 

    - "Controlador de host intel(R) USB 3.0 eXtensible – 1.0 (Microsoft)" -> PCI\CC_0C03 
    - "Concentrador raíz USB (USB 3.0)" -> USB\ROOT_HUB30 
    - "Concentrador USB genérico" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="control de dispositivo":::

    > [!NOTE]
    > Algunos dispositivos del sistema tienen varias capas de conectividad para definir su instalación en el sistema. Las unidades usb son estos dispositivos. Por lo tanto, cuando se busca bloquearlos o permitirlos en un sistema, es importante comprender la ruta de conectividad para cada dispositivo. Hay varios IDs de dispositivo genéricos que se usan habitualmente en sistemas y podrían proporcionar un buen comienzo para crear una "lista de permitidos" en estos casos. El siguiente es un ejemplo (no siempre es lo mismo para todos los USB; debes comprender el árbol PnP del dispositivo que quieres administrar a través del Administrador de dispositivos):
    >
    > PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1&HOST (para controladores de host)/ USB\ROOT_HUB30; USB\ROOT_HUB20 (para concentradores raíz USB)/ USB\USB20_HUB (para concentradores USB genéricos)/ 
    >
    > Específicamente para máquinas de escritorio, es importante enumerar todos los dispositivos USB a los que están conectados los teclados y los ratones en la lista anterior. Si no lo hace, podría impedir que un usuario acceda a su máquina a través de dispositivos HID. 
    >
    > A veces, los distintos fabricantes de equipos tienen distintas formas de anidar dispositivos USB en el árbol pnp, pero, en general, así se hace. 

5. Vuelva a conectar el USB permitido. Verá que ahora está permitido y disponible.

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="quitar unidad":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>Implementación y administración de directivas mediante directiva de grupo

La característica de instalación de dispositivos te permite aplicar la directiva a través de la directiva de grupo.

#### <a name="licensing"></a>Licencias

Para acceder y usar la instalación del dispositivo, debes tener Windows E3.

#### <a name="deploying-policy"></a>Implementación de directivas

Encontrará los detalles de implementación aquí: Administrar la instalación de dispositivos con directiva de grupo [(Windows 10) - Windows cliente](/windows/client-management/manage-device-installation-with-group-policy).

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos extraíbles Storage control de acceso en Microsoft Defender para endpoint

El [Microsoft 365 de seguridad muestra](https://sip.security.microsoft.com/homepage) el almacenamiento extraíble bloqueado por la instalación del dispositivo de control de dispositivos. Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:

- Microsoft 365 para informes E5

```kusto
//events triggered by Device Installation policies 
DeviceEvents 
| where ActionType == "PnpDeviceBlocked" or ActionType == "PnpDeviceAllowed" 
| extend parsed=parse_json(AdditionalFields) 
| extend MediaClassGuid = tostring(parsed.ClassGuid)  
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaDeviceId = tostring(parsed.MatchingDeviceId) 
| project Timestamp , DeviceId, DeviceName, ActionType, MediaClassGuid, MediaDeviceId, MediaInstanceId, AdditionalFields 
| order by Timestamp desc 
```

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="almacenamiento en bloques":::

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>¿Cómo puedo saber si la máquina de destino obtiene la directiva implementada? 
Puede usar la siguiente consulta para obtener la versión del cliente antimalware en el portal de seguridad Microsoft 365 web:

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens   
DeviceRegistryEvents 
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\" 
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>¿Por qué la directiva Permitir no funciona?
No basta con habilitar un solo identificador de hardware para habilitar una única unidad usb. Asegúrate de que todos los dispositivos USB que preceden al destino no están bloqueados (permitidos).

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="Preguntas frecuentes sobre instalación de dispositivos":::

