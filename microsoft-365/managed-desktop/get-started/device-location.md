---
title: Servicio de ubicación de Windows 10
description: Cómo tener activados los servicios de ubicación de Windows para tus dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929526"
---
# <a name="windows-10-location-service"></a>Servicio de ubicación de Windows 10

Los dispositivos de Escritorio administrado de Microsoft se registran mediante Windows Autopilot. Este proceso nos permite administrarlos con Azure Active Directory y Microsoft Intune. De forma predeterminada, el servicio de ubicación de Windows 10 está deshabilitado cuando se activa un dispositivo por primera vez, a menos que esta característica esté habilitada en la configuración de privacidad durante la "experiencia de inicio de sesión". Esta configuración se oculta durante la inscripción de Autopilot en Microsoft Managed Desktop. Para obtener más información acerca de cómo se configura Autopilot, vea [First-run experience with Autopilot y la página Enrollment Status .](esp-first-run.md)

Por este motivo, los dispositivos de Escritorio administrado de Microsoft no pueden obtener su ubicación de dispositivo, lo que limita la funcionalidad de varias características de Windows, como las zonas horarias. Para obtener más información acerca del servicio de ubicación de Windows 10, consulta Servicio de ubicación y [privacidad de Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

No tiene que usar el servicio de ubicación para participar en Microsoft Managed Desktop, pero la experiencia del usuario estará restringida. Por ejemplo, los dispositivos no podrán determinar automáticamente la zona horaria en la que se encuentra cuando los usuarios trabajan en una zona horaria diferente.

## <a name="enable-the-location-service"></a>Habilitar el servicio de ubicación

Puede optar por usar el servicio de ubicación al inscribir dispositivos en el servicio de Escritorio administrado de Microsoft o puede activar o desactivar el servicio después de la inscripción.

### <a name="opt-in-during-enrollment"></a>Participar durante la inscripción

Puede hacer que el servicio de Escritorio administrado de Microsoft habilite el servicio de ubicación. Durante la secuencia de inscripción, se te pedirá que selecciones si quieres permitir que el servicio de ubicación de Windows 10 esté habilitado en dispositivos.

### <a name="control-the-location-service-after-enrollment"></a>Controlar el servicio de ubicación después de la inscripción

Puede tener el servicio de ubicación activado (o desactivado) en cualquier momento enviando una solicitud de soporte [técnico](../working-with-managed-desktop/admin-support.md) a través del [portal de administración](access-admin-portal.md).

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Cómo Microsoft Managed Desktop configura el servicio de ubicación de Windows 10

Si opta por usar el servicio de ubicación, usamos la configuración mínima necesaria sin afectar a la privacidad de los usuarios. Para obtener más información, consulta Servicio de ubicación de [Windows 10 y privacidad.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Managed Desktop habilita la configuración **De privacidad de** ubicación en la configuración de **Windows** para Permitir el acceso a la ubicación en **este dispositivo.** La interfaz de usuario tiene este aspecto:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configuración de ubicación en la configuración de Windows":::

> [!NOTE]
> Si optas por usar el servicio de ubicación, esto solo se aplica al propio sistema operativo Windows. Las aplicaciones no pueden usar servicios de ubicación. Cada usuario puede elegir si desea permitir que las aplicaciones accedan a su ubicación.