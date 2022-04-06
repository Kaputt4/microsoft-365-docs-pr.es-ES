---
title: Microsoft Defender para punto de conexión instalación del dispositivo de control de dispositivos
description: En este tema se proporciona un tutorial sobre Microsoft Defender para punto de conexión instalación del dispositivo de control de dispositivos
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
ms.openlocfilehash: dc05633d1badfc29b2179915ac6d318dd9523834
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666402"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Microsoft Defender para punto de conexión instalación del dispositivo de control de dispositivos

**Se aplica a**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para punto de conexión Instalación del dispositivo de control de dispositivos le permite realizar la siguiente tarea:

- Impedir que las personas instalen dispositivos específicos.
- Permitir a las personas instalar dispositivos específicos, pero evitar otros dispositivos.

> [!NOTE]
> Para encontrar la diferencia entre la instalación del dispositivo y el control de acceso de almacenamiento extraíble, consulte [Microsoft Defender para punto de conexión Device Control Removable Storage Protection](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true).

|Privilegio|Permiso|
|---|---|
|Access|Instalación del dispositivo |
|Modo de acción|Permitir, impedir |
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en el usuario|No|
|Compatibilidad basada en máquinas|Sí|

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente la instalación de dispositivos en Windows 10, dispositivos Windows 11, Windows Server 2022.

## <a name="device-properties"></a>Propiedades de dispositivo

La compatibilidad con la instalación de dispositivos admite las siguientes propiedades de dispositivo:

- Id. de dispositivo
- Id. de hardware
- Identificador compatible
- Clase de dispositivo
- Tipo de dispositivo "Dispositivo extraíble": algunos dispositivos se podrían clasificar como Dispositivo extraíble. Un dispositivo se considera extraíble cuando el controlador del dispositivo al que está conectado indica que el dispositivo es extraíble. Por ejemplo, los controladores del concentrador USB al que está conectado el dispositivo notifican que un dispositivo USB es extraíble.
Para obtener más información, consulte [Instalación de dispositivos en Windows](/windows/client-management/manage-device-installation-with-group-policy).

## <a name="policies"></a>Directivas

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo

Esta configuración de directiva le permite especificar una lista de Plug and Play identificadores de hardware e identificadores compatibles para los dispositivos que Windows pueden instalar. Esta configuración de directiva está pensada para usarse solo cuando se habilita la opción **de directiva Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** .

Cuando esta configuración de directiva está habilitada junto con la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo**, Windows puede instalar o actualizar cualquier dispositivo cuyo identificador de hardware o identificador compatible de Plug and Play aparezca en la lista que cree, a menos que otra configuración de directiva en el mismo nivel o superior de la jerarquía impida específicamente  esa instalación, como la siguiente configuración de directiva:

- Impedir la instalación de dispositivos que coincidan con estos identificadores de dispositivo.
- Impedir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo.

Si la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación.

> [!NOTE]
> La configuración **de directiva Impedir la instalación de dispositivos no descrita por otras configuraciones de directiva** se ha reemplazado por la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todas las** directivas de criterios de coincidencia de dispositivos para las versiones de Windows 10 de destino y Windows 11 compatibles. Se recomienda usar la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** siempre que sea posible.

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo

Esta configuración de directiva le permite especificar una lista de Plug and Play identificadores de instancia de dispositivo para los dispositivos que Windows pueden instalar. Esta configuración de directiva está pensada para usarse solo cuando se habilita la opción **de directiva Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** .

Cuando esta configuración de directiva está habilitada junto con la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo**, Windows puede instalar o actualizar cualquier dispositivo cuyo identificador de instancia de dispositivo Plug and Play aparezca en la lista que cree, a menos que otra configuración de directiva en el mismo nivel o superior de la jerarquía impida específicamente que  instalación, como la siguiente configuración de directiva:

- Impedir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo

Si la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación.

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>Permitir la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos

Esta configuración de directiva le permite especificar una lista de identificadores únicos globales (GUID) de clase de configuración de dispositivo para los paquetes de controladores que Windows se pueden instalar. Esta configuración de directiva está pensada para usarse solo cuando se habilita la opción **de directiva Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** .

Cuando esta configuración de directiva está habilitada junto con la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo**, Windows puede instalar o actualizar paquetes de controladores cuyos GUID de clase de configuración de dispositivo aparecen en la lista que cree, a menos que otra configuración de directiva en el mismo nivel o superior de la jerarquía impida específicamente esa instalación,  como la siguiente configuración de directiva:

- Impedir la instalación de dispositivos para estas clases de dispositivo
- Impedir la instalación de dispositivos que coincidan con estos identificadores de dispositivo
- Impedir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo

Si la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** no está habilitada con esta configuración de directiva, tendrá prioridad cualquier otra configuración de directiva que impida específicamente la instalación.

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>Aplicar el orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos

Esta configuración de directiva cambiará el orden de evaluación en el que se aplica la configuración de directiva Permitir y evitar cuando se aplica más de una configuración de directiva de instalación para un dispositivo determinado. Habilite esta configuración de directiva para asegurarse de que se aplican criterios de coincidencia de dispositivo superpuestos en función de una jerarquía establecida en la que criterios de coincidencia más específicos reemplazan a criterios de coincidencia menos específicos. El orden jerárquico de evaluación de la configuración de directiva que especifica criterios de coincidencia de dispositivo es el siguiente:

**Identificadores** \> de instancia de dispositivo **Identificadores de dispositivo** \> **Clase de configuración de dispositivo** \> **Dispositivos extraíbles**

#### <a name="device-instance-ids"></a>Identificadores de instancia de dispositivo

1. Impedir la instalación de dispositivos mediante controladores que coincidan con estos identificadores de instancia de dispositivo.
2. Permitir la instalación de dispositivos mediante controladores que coincidan con estos identificadores de instancia de dispositivo.

#### <a name="device-ids"></a>Id. de dispositivos

1. Impedir la instalación de dispositivos mediante controladores que coincidan con estos identificadores de dispositivo.
2. Permitir la instalación de dispositivos mediante controladores que coincidan con estos identificadores de dispositivo.

#### <a name="device-setup-class"></a>Clase de configuración de dispositivo

1. Evite la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos.
2. Permitir la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos.

#### <a name="removable-devices"></a>Dispositivos extraíbles

Impedir la instalación de dispositivos extraíbles

> [!NOTE]
> Esta configuración de directiva proporciona un control más pormenorizado que la configuración **de directiva Impedir la instalación de dispositivos no descrita por otra configuración de directiva** . Si estas configuraciones de directiva en conflicto están habilitadas al mismo tiempo, se habilitará la opción **Aplicar orden de evaluación por capas para Permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivo** y se omitirá la otra configuración de directiva.

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>Impedir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo

Esta configuración de directiva permite especificar una lista de identificadores de hardware Plug and Play e identificadores compatibles para los dispositivos que Windows no se pueden instalar. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que permita a Windows instalar un dispositivo.

> [!NOTE]
> Para habilitar la configuración **de directiva Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo** para reemplazar esta configuración de directiva para los dispositivos aplicables, habilite la opción **Aplicar orden de evaluación por capas para Permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos** .

Si habilita esta configuración de directiva, Windows no podrá instalar un dispositivo cuyo identificador de hardware o identificador compatible aparezca en la lista que cree. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilita o no establece esta configuración de directiva, los dispositivos se pueden instalar y actualizar según lo permitido o lo impiden otras opciones de configuración de directiva.

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>Impedir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo

Esta configuración de directiva permite especificar una lista de Plug and Play identificadores de instancia de dispositivo para los dispositivos que Windows no se pueden instalar. Esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que permita a Windows instalar un dispositivo.

Si habilita esta configuración de directiva, Windows no podrá instalar un dispositivo cuyo identificador de instancia de dispositivo aparezca en la lista que cree. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilita o no establece esta configuración de directiva, los dispositivos se pueden instalar y actualizar según lo permitido o lo impiden otras opciones de configuración de directiva.

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>Impedir la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos

Esta configuración de directiva permite especificar una lista de identificadores únicos globales (GUID) de clase de configuración de dispositivo para los paquetes de controladores que Windows no se pueden instalar. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que permita a Windows instalar un dispositivo.

> [!NOTE]
> Para habilitar la opción **Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo** y **Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo** para reemplazar esta configuración de directiva para los dispositivos aplicables, habilite la opción **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos** .

Si habilita esta configuración de directiva, Windows no podrá instalar o actualizar paquetes de controladores cuyos GUID de clase de configuración de dispositivo aparecen en la lista que cree. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos especificados desde un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilita o no establece esta configuración de directiva, Windows puede instalar y actualizar los dispositivos según lo permitido o impedido por otra configuración de directiva.

### <a name="prevent-installation-of-removable-devices"></a>Impedir la instalación de dispositivos extraíbles

Esta configuración de directiva le permite evitar que Windows instale dispositivos extraíbles. Un dispositivo se considera extraíble cuando el controlador del dispositivo al que está conectado indica que el dispositivo es extraíble. Por ejemplo, los controladores del concentrador USB al que está conectado el dispositivo informan de que un dispositivo bus serie universal (USB) es extraíble. De forma predeterminada, esta configuración de directiva tiene prioridad sobre cualquier otra configuración de directiva que permita a Windows instalar un dispositivo.

> [!NOTE]
> Para habilitar la opción **Permitir la instalación de dispositivos con controladores que coincidan con estas clases de configuración de dispositivos**, **permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo** y **permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo** para reemplazar esta configuración de directiva para los dispositivos aplicables, habilite la opción **Aplicar orden de evaluación por capas para Permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos** .

Si habilita esta configuración de directiva, Windows no podrá instalar dispositivos extraíbles y los dispositivos extraíbles existentes no podrán actualizar sus controladores. Si habilita esta configuración de directiva en un servidor de escritorio remoto, la configuración de directiva afecta al redireccionamiento de los dispositivos extraíbles de un cliente de escritorio remoto al servidor de escritorio remoto.

Si deshabilita o no establece esta configuración de directiva, Windows puede instalar y actualizar paquetes de controladores para dispositivos extraíbles según lo permitido o impedido por otras opciones de configuración de directiva.

## <a name="common-removable-storage-access-control-scenarios"></a>Escenarios de Storage Access Control extraíbles comunes

Para ayudarle a familiarizarse con Microsoft Defender para punto de conexión Storage Access Control extraíbles, hemos elaborado algunos escenarios comunes que debe seguir.

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>Escenario 1: Impedir la instalación de todos los dispositivos USB al tiempo que se permite la instalación de solo una unidad usb autorizada

En este escenario, se usarán las siguientes directivas:

- Evite la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos.
- Aplique el orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos.
- Permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de instancia de dispositivo o permitir la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo.

#### <a name="deploying-and-managing-policy-via-intune"></a>Implementación y administración de directivas a través de Intune

La característica Instalación del dispositivo le permite aplicar la directiva a través de Intune al dispositivo.

#### <a name="licensing"></a>Licencias

Antes de empezar a instalar el dispositivo, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar la instalación del dispositivo, debe tener Microsoft 365 E3.

#### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivo. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos:

- Rol de administrador de perfiles y directivas
- O un rol personalizado con los permisos Crear/Editar/Actualizar/Leer/Eliminar/Ver informes activados para los perfiles de configuración de dispositivos
- O administrador global

#### <a name="deploying-policy"></a>Implementación de la directiva

En Microsoft Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)

1. Configure **Impedir la instalación de dispositivos mediante controladores que coincidan con estas clases de configuración de dispositivos**.

    - Abra Seguridad del punto de conexión > Reducción de la superficie expuesta a ataques > Crear directiva > Plataforma: Windows 10 (y versiones posteriores) & Perfil: Control de dispositivo.

      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="Página Editar perfil" lightbox="../../media/devicepolicy-editprofile.png":::

2. Conecte un dispositivo USB y verá el siguiente mensaje de error:

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="Mensaje de error" lightbox="../../media/devicepolicy-errormsg.png":::

3. Habilite **Aplicar orden de evaluación por capas para permitir y evitar directivas de instalación de dispositivos en todos los criterios de coincidencia de dispositivos**.

    - **solo admite OMA-URI por ahora**: Dispositivos > Perfiles de configuración > Crear perfil > Plataforma: Windows 10 (y versiones posteriores) & Perfil: Personalizado

      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="Página Editar fila" lightbox="../../media/devicepolicy-editrow.png":::

4. Habilitar y agregar el identificador de instancia USB permitido: **permite la instalación de dispositivos que coincidan con cualquiera de estos identificadores de dispositivo**.

    - Actualización del perfil de control de dispositivo del paso 1

      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="Un identificador en la página Control de dispositivos" lightbox="../../media/devicepolicy-devicecontrol.png":::

    Agregar PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1&HOST; USB\ROOT_HUB30; USB\ROOT_HUB20; USB\USB20_HUB en la captura de pantalla anterior se debe a que no es suficiente habilitar un solo identificador de hardware para habilitar una sola unidad usb. Debe asegurarse de que todos los dispositivos USB que preceden al de destino no están bloqueados (permitidos). Puede abrir Administrador de dispositivos y cambiar la vista a "Dispositivos por conexiones" para ver cómo se instalan los dispositivos en el árbol PnP. En nuestro caso, se deben permitir los siguientes dispositivos para que también se pueda permitir la unidad usb de destino:

    Agregar PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1&HOST; USB\ROOT_HUB30; USB\ROOT_HUB20; USB\USB20_HUB en la captura de pantalla anterior se debe a que no es suficiente habilitar un solo identificador de hardware para habilitar una sola unidad usb. Debe asegurarse de que todos los dispositivos USB que preceden al de destino no están bloqueados (permitidos). Puede abrir Administrador de dispositivos y cambiar la vista a "Dispositivos por conexiones" para ver cómo se instalan los dispositivos en el árbol PnP. En nuestro caso, se deben permitir los siguientes dispositivos para que también se pueda permitir la unidad usb de destino:

    - "Controlador de host Intel(R) USB 3.0 eXtensible – 1.0 (Microsoft)" -> PCI\CC_0C03
    - "Usb Root Hub (USB 3.0)" -> USB\ROOT_HUB30
    - "Concentrador USB genérico" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="Elemento de menú Ver de la página Administrador de dispositivos" lightbox="../../media/devicepolicy-devicemgr.png":::

    > [!NOTE]
    > Algunos dispositivos del sistema tienen varias capas de conectividad para definir su instalación en el sistema. Las unidades usb son tales dispositivos. Por lo tanto, al buscar bloquearlos o permitirlos en un sistema, es importante comprender la ruta de conectividad de cada dispositivo. Hay varios identificadores de dispositivo genéricos que se usan habitualmente en los sistemas y podrían proporcionar un buen comienzo para crear una "lista de permitidos" en estos casos. El siguiente es un ejemplo (no siempre es el mismo para todos los USB; debe comprender el árbol PnP del dispositivo que desea administrar a través de la Administrador de dispositivos):
    >
    > PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1&HOST (para controladores host)/ USB\ROOT_HUB30; USB\ROOT_HUB20 (para concentradores raíz USB)/ USB\USB20_HUB (para concentradores USB genéricos)/
    >
    > Específicamente para máquinas de escritorio, es importante enumerar todos los dispositivos USB a los que están conectados los teclados y ratones en la lista anterior. Si no lo hace, podría impedir que un usuario acceda a su máquina a través de dispositivos HID.
    >
    > A veces, diferentes fabricantes de PC tienen diferentes maneras de anidar dispositivos USB en el árbol PnP, pero en general esto es lo que se hace.

5. Vuelva a conectar el USB permitido. Verá que ahora está permitido y disponible.

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="Página Quitar detalles de la unidad" lightbox="../../media/devicepolicy-removedrive.png":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>Implementación y administración de directivas mediante directiva de grupo

La característica Instalación del dispositivo le permite aplicar la directiva a través de directiva de grupo.

#### <a name="licensing"></a>Licencias

Para acceder y usar la instalación del dispositivo, debe tener Windows E3.

#### <a name="deploying-policy"></a>Implementación de la directiva

Puede encontrar los detalles de la implementación aquí: [Administrar la instalación de dispositivos con directiva de grupo (Windows 10): cliente de Windows](/windows/client-management/manage-device-installation-with-group-policy).

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos de Storage Access Control extraíbles de Control de dispositivos en Microsoft Defender para punto de conexión

El [portal de seguridad de Microsoft 365](https://sip.security.microsoft.com/homepage) muestra el almacenamiento extraíble bloqueado por la instalación del dispositivo de control de dispositivos. Para acceder a la seguridad de Microsoft 365, debe tener la siguiente suscripción:

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

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="Almacenamiento en bloques" lightbox="../../media/block-removable-storage2.png":::

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>¿Cómo puedo saber si la máquina de destino obtiene la directiva implementada?

Puede usar la siguiente consulta para obtener la versión del cliente antimalware en el portal de seguridad de Microsoft 365:

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens
DeviceRegistryEvents
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\"
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>¿Por qué la directiva Permitir no funciona?

No es suficiente habilitar un solo identificador de hardware para habilitar una única unidad usb. Asegúrese de que todos los dispositivos USB que preceden al dispositivo de destino no estén bloqueados (permitidos).

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="Preguntas más frecuentes sobre la instalación del dispositivo" lightbox="../../media/devicemgrscrnshot.png":::
