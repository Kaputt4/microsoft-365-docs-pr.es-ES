---
title: Servicio de ubicación de Windows 10
description: Describe cómo tener activados Windows de ubicación para los dispositivos
keywords: 'Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación'
ms.service: m365-md
author: tiaraquan
f1.keywords:
  - NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# <a name="windows-10-location-service"></a>Servicio de ubicación de Windows 10

Los dispositivos de Escritorio administrado de Microsoft se registran mediante Windows Autopilot. Este proceso nos permite administrarlos con Azure Active Directory y Microsoft Intune.

De forma predeterminada, el servicio de ubicación de Windows 10 está deshabilitado cuando se activa un dispositivo por primera vez, a menos que esta característica esté habilitada en la configuración de privacidad durante la "experiencia de salida". Esta configuración se oculta durante la inscripción de Autopilot en Microsoft Managed Desktop. Para obtener más información sobre cómo se configura Autopilot, consulte [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).

Por este motivo, los dispositivos de Escritorio administrado de Microsoft no pueden obtener su ubicación de dispositivo y limitan la funcionalidad de varias Windows, como las zonas horarias. Para obtener más información acerca del Windows 10 de ubicación, [consulte Windows 10 de ubicación y privacidad](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).

No tiene que usar el servicio de ubicación para poder participar en Microsoft Managed Desktop. Se restringirá la experiencia del usuario. Por ejemplo, los dispositivos no podrán determinar automáticamente la zona horaria en la que se encuentra cuando los usuarios trabajan en una zona horaria diferente.

## <a name="enable-the-location-service"></a>Habilitar el servicio de ubicación

Puede:

- Participar para usar el servicio de ubicación al inscribir dispositivos en el servicio de Escritorio administrado de Microsoft, o
- Puede activar o desactivar el servicio después de la inscripción.

### <a name="opt-in-during-enrollment"></a>Participar durante la inscripción

Puede hacer que el servicio de Escritorio administrado de Microsoft habilite el servicio de ubicación. Durante la secuencia de inscripción, se te pedirá que selecciones si quieres permitir que el servicio de Windows 10 ubicación esté habilitado en dispositivos.

### <a name="control-the-location-service-after-enrollment"></a>Controlar el servicio de ubicación después de la inscripción

Puede tener el servicio de ubicación activado (o desactivado), en cualquier momento, enviando una solicitud de [soporte técnico a](../working-with-managed-desktop/admin-support.md) través del [portal de administración](access-admin-portal.md).

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Cómo Microsoft Managed Desktop configura el servicio de Windows 10 de ubicación

Si opta por usar el servicio de ubicación, usamos la configuración mínima necesaria sin afectar a la privacidad de los usuarios. Para obtener más información, [consulte Windows 10 de ubicación y privacidad](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).

Microsoft Managed Desktop habilita la configuración **de** privacidad de ubicación **en Windows configuración** para permitir el acceso **a la ubicación en este dispositivo**. La interfaz de usuario tiene este aspecto:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configuración de ubicación en Windows configuración.":::

> [!NOTE]
> Si opta por usar el servicio de ubicación, esto solo se aplica al Windows sistema operativo en sí. Las aplicaciones no pueden usar servicios de ubicación. Cada usuario puede elegir si desea permitir que las aplicaciones accedan a su ubicación.
