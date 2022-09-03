---
title: Microsoft Defender para punto de conexión Protección contra impresoras de control de dispositivos
description: Microsoft Defender para punto de conexión Device Control Printer Protection impide que las personas impriman a través de impresoras no corporativas o impresoras USB no aprobadas.
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: dansimp
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 49d03062da1f5440013faf49c08190c63f9a831e
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585948"
---
# <a name="device-control-printer-protection"></a>Protección de la impresora de control de dispositivo

**Se aplica a**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para punto de conexión Device Control Printer Protection impide que las personas impriman a través de impresoras no corporativas o impresoras USB no aprobadas.

## <a name="licensing"></a>Licencias

Antes de empezar a trabajar con Printer Protection, debe [confirmar su suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). Para acceder y usar Printer Protection, debe tener lo siguiente:

- Microsoft 365 E3 para la implementación de funciones o directivas
- Microsoft 365 E5 para la generación de informes

## <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, para implementar la directiva a través de OMA-URI, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivo. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos:

- Rol de administrador de perfiles y directivas.
- O un rol personalizado con los permisos Crear/Editar/Actualizar/Leer/Eliminar/Ver informes activados para los perfiles de configuración de dispositivos
- O administrador global

Para ver los informes de configuración del dispositivo, la cuenta debe tener permisos de visualización de informes. Puede crear roles personalizados o usar los roles integrados con estos permisos:

- Administrador de seguridad global
- Administrador de seguridad
- Lector de seguridad

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Asegúrese de que los dispositivos Windows 10 o Windows 11 que tiene previsto implementar Printer Protection para cumplir estos requisitos.

1. Se instalan las siguientes actualizaciones de Windows.
    - Para Windows 1809: instalar Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - Para Windows 1909: instalar Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Para Windows 2004 o posterior

2. Si tiene previsto implementar la directiva a través de directiva de grupo, el dispositivo debe incorporarse a Microsoft Defender para punto de conexión unido; si tiene previsto implementar la directiva a través de Microsoft Endpoint Manager, el dispositivo debe estar unido mediante el uso de Microsoft Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Implementación de la directiva de protección de impresora de control de dispositivos

Puede implementar la directiva mediante directiva de grupo o Intune.

<br>

****

|Título|Descripción|Compatibilidad con CSP | Compatibilidad con GPO | Soporte técnico basado en el usuario | Compatibilidad basada en máquinas |
|---|---|:---:|:---:|:---:|:---:|
|**Habilitar restricciones de impresión del control de dispositivos**|Impedir que las personas impriman a través de una impresora no corporativa|Sí|Sí|Sí|Sí|
|**Lista de dispositivos de impresión conectados a USB aprobados**\*|Permitir una impresora USB específica|Sí|Sí|Sí|Sí|
|

\* Esta directiva debe usarse junto con **Habilitar restricciones de impresión del control de dispositivo**.

## <a name="deploy-policy-via-intune"></a>Implementación de directivas a través de Intune

Por Intune, actualmente Device Control Printer Protection solo admite OMA-URI.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Escenario 1: Impedir que los usuarios impriman a través de cualquier impresora no corporativa mediante Intune

- Aplicar directiva a través de la máquina:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- Aplicar directiva sobre el usuario:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

La cadena de compatibilidad de CSP con `<enabled/>`:

:::image type="content" source="../../media/customeditrow.png" alt-text="Página Personalizada" lightbox="../../media/customeditrow.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Escenario 2: Permitir impresoras USB aprobadas específicas mediante Intune

- Aplicar directiva a través de la máquina:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- Aplicar directiva sobre el usuario:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

La cadena de compatibilidad de CSP con impresoras USB aprobadas a través de la propiedad "ApprovedUsbPrintDevices", por ejemplo `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`:

:::image type="content" source="../../media/editrow.png" alt-text="Panel Editar fila" lightbox="../../media/editrow.png":::

## <a name="deploy-policy-via-group-policy"></a>Implementación de directivas a través de directiva de grupo

Si el dispositivo no está Intune unido, también puede implementar la directiva a través de directiva de grupo.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Escenario 1: Impedir que los usuarios impriman a través de cualquier impresora no corporativa mediante directiva de grupo

- Aplicar directiva a través de la máquina:

  Impresora de plantillas \> administrativas de configuración \> del equipo: habilitar restricciones de impresión de control de dispositivos

- Aplicar directiva sobre el usuario:

  Plantillas \> administrativas de configuración \> de usuario Panel de control \> impresoras: Habilitar restricciones de impresión de control de dispositivos

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="Panel Habilitar restricciones de impresión de control de dispositivos" lightbox="../../media/enable-device-ctrl-printing-restrictions.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Escenario 2: Permitir impresoras USB aprobadas específicas mediante directiva de grupo

- Aplicar directiva a través de la máquina:

  Impresora de plantillas \> administrativas de configuración \> del equipo: lista de dispositivos de impresión conectados a USB aprobados

- Aplicar directiva sobre el usuario:

  Plantillas \> administrativas de configuración \> de usuario Panel de control \> impresoras: lista de dispositivos de impresión conectados a USB aprobados

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="Lista de dispositivos de impresión conectados a USB aprobados" lightbox="../../media/list-of-approved-connected-print-devices.png":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Visualización de datos de protección de impresora de Control de dispositivos en Microsoft Defender para punto de conexión portal

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> muestra la impresión bloqueada por la directiva protección de impresora de control de dispositivos anterior.

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="búsqueda avanzada" lightbox="../../media/device-control-advanced-hunting.png":::

 Puede usar el evento PnP para buscar la impresora USB usada en la organización:

```kusto
//find the USB Printer VID/PID
DeviceEvents
| where ActionType == "PnpDeviceConnected"
| extend parsed=parse_json(AdditionalFields)
| extend DeviceDescription = tostring(parsed.DeviceDescription) 
| extend PrinterDeviceId = tostring(parsed.DeviceId) 
| extend VID_PID_Array = split(split(PrinterDeviceId, "\\")[1], "&")
| extend VID_PID = replace_string(strcat(VID_PID_Array[0], '/', VID_PID_Array[1]), 'VID_', '')
| extend VID_PID = replace_string(VID_PID, 'PID_', '')
| extend ClassId = tostring(parsed.ClassId) 
| extend VendorIds = tostring(parsed.VendorIds) 
| where DeviceDescription == 'USB Printing Support'
| project Timestamp , DeviceId, DeviceName, ActionType, DeviceDescription, VID_PID, ClassId, PrinterDeviceId, VendorIds, parsed
| order by Timestamp desc
```

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="Página Búsqueda avanzada" lightbox="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png":::
