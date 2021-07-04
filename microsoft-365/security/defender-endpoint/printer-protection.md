---
title: Protección de impresora de control de dispositivos de Microsoft Defender para Endpoint
description: Microsoft Defender para Endpoint Device Control Printer Protection bloquea la impresión de personas a través de impresoras no corporativas o impresoras USB no aprobadas.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289696"
---
# <a name="device-control-printer-protection"></a>Protección de la impresora de control de dispositivo

Microsoft Defender para Endpoint Device Control Printer Protection bloquea la impresión de personas a través de impresoras no corporativas o impresoras USB no aprobadas.

## <a name="licensing"></a>Licencias

Antes de empezar a usar Printer Protection, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). Para obtener acceso y usar la protección de impresoras, debe tener lo siguiente:

- Microsoft 365 E3 para la implementación de directivas/funcionalidad
- Microsoft 365 E5 para informes

## <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, para implementar la directiva a través de OMA-URI, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos:

- Rol Administrador de directivas y perfiles.
- O rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos
- O Administrador global

Para ver los informes de configuración del dispositivo, la cuenta debe tener permisos de vista de informes. Puede crear roles personalizados o usar los roles integrados con estos permisos:

- Administrador de seguridad global
- Administrador de seguridad
- Lector de seguridad

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Asegúrese de que los dispositivos Windows 10 que planee implementar Printer Protection cumplan estos requisitos.

1. Únase al programa Insider.

1. Se instalan las siguientes actualizaciones de Windows.
    - For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Para Windows 2004 o posterior

1. Si estás planeando implementar la directiva a través de la directiva de grupo, el dispositivo debe estar unido a MDATP; si planea implementar la directiva a través de MEM, el dispositivo debe estar unido a Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Implementar directiva de protección de impresoras de control de dispositivos

Puedes implementar la directiva a través de la directiva de grupo o Intune.

<br>

****

|Título|Descripción|Compatibilidad con CSP | Compatibilidad con GPO | Soporte técnico basado en usuarios | Compatibilidad basada en máquina |
|---|---|:---:|:---:|:---:|:---:|
|**Habilitar restricciones de impresión del control de dispositivos**|Bloquear la impresión de personas a través de impresoras no corporativas|Sí|Sí|Sí|Sí|
|**Lista de dispositivos de impresión conectados a USB aprobados**\*|Permitir una impresora USB específica|Sí|Sí|Sí|Sí|
|

\*Esta directiva debe usarse junto con **Habilitar restricciones de impresión del control de dispositivo.**

## <a name="deploy-policy-via-intune"></a>Implementar la directiva a través de Intune

En Intune, actualmente Device Control Printer Protection solo admite OMA-URI.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Escenario 1: Bloquear la impresión de personas a través de cualquier impresora no corporativa con Intune

- Aplicar directiva sobre el equipo:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- Aplicar directiva sobre el usuario:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

La cadena de compatibilidad de CSP con `<enabled/>` :

:::image type="content" source="../../media/customeditrow.png" alt-text="fila de edición personalizada":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Escenario 2: Permitir impresoras USB aprobadas específicas con Intune

- Aplicar directiva sobre el equipo:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- Aplicar directiva sobre el usuario:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

La cadena de compatibilidad de CSP con impresoras USB aprobadas a través de la propiedad "ApprovedUsbPrintDevices", por `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` ejemplo:

:::image type="content" source="../../media/editrow.png" alt-text="editar fila":::

## <a name="deploy-policy-via-group-policy"></a>Implementar la directiva a través de la directiva de grupo

Si el dispositivo no está unido a Intune, también puedes implementar la directiva a través de la directiva de grupo.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Escenario 1: Bloquear la impresión de personas a través de cualquier impresora no corporativa mediante la directiva de grupo

- Aplicar directiva sobre el equipo:

  Impresora de plantillas administrativas de configuración \> \> del equipo: Habilitar restricciones de impresión del control de dispositivos

- Aplicar directiva sobre el usuario:

  Configuración de usuario \> Plantillas administrativas \> Impresoras del panel de \> control: Habilitar restricciones de impresión del control de dispositivos

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="habilitar restricciones de impresión de dispositivos":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Escenario 2: Permitir impresoras USB aprobadas específicas con la directiva de grupo

- Aplicar directiva sobre el equipo:

  Impresora de plantillas administrativas de configuración \> \> del equipo: lista de dispositivos de impresión conectados a USB aprobados

- Aplicar directiva sobre el usuario:

  Impresoras de panel de control de plantillas administrativas de configuración \> \> de \> usuario: lista de dispositivos de impresión conectados a USB aprobados

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista de dispositivos de impresión conectados usb aprobados":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Ver datos de protección de impresoras de control de dispositivos en Microsoft Defender para el portal de puntos de conexión

El [Microsoft 365 de seguridad muestra](https://security.microsoft.com) la impresión bloqueada por la directiva de protección de impresoras de control de dispositivos anterior.

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="búsqueda avanzada":::
