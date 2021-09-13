---
title: Borrar un dispositivo móvil en Movilidad básica y seguridad
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: Usa la movilidad básica y la seguridad integradas para quitar información de los dispositivos inscritos.
ms.openlocfilehash: b687b3d13f95cb05d9261064d385d35ef6d7f7bf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184990"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Borrar un dispositivo móvil en Movilidad básica y seguridad

Puedes usar la movilidad y seguridad básicas integradas para Microsoft 365 para quitar solo la información de la organización o para realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos Microsoft 365 organización. Para ayudar a proteger la información de su organización, puede realizar el restablecimiento de fábrica o quitar los datos de la empresa:

- **Restablecimiento de** fábrica: elimina todos los datos del dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal. Una vez completada la eliminación, el dispositivo se restaura a su configuración de fábrica.

- **Quitar datos de la** empresa: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.

- **Cuando se elimina un dispositivo (Restablecimiento** de fábrica o Quitar datos de empresa), el dispositivo se quita de la lista de dispositivos administrados.
    
- **Restablecer automáticamente** un dispositivo: puedes configurar una directiva básica de movilidad y seguridad que restablece automáticamente un dispositivo después de que el usuario intente introducir la contraseña del dispositivo sin éxito un número específico de veces. Para ello, siga los pasos descritos en Crear directivas [de seguridad de dispositivos en movilidad y seguridad básicas.](create-device-security-policies.md)
    
- **Si quieres conocer la experiencia del** usuario al borrar su dispositivo, consulta ¿Cuál es el impacto del usuario y del   [dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Borrar un dispositivo móvil

1. Vaya a la [Centro de administración de Microsoft 365](../../admin/admin-overview/about-the-admin-center.md).

2. Escribe Administración de dispositivos móviles en el campo de búsqueda y selecciona **Administración de dispositivos móviles** en la lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción básica de administración de dispositivos móviles Movilidad y Secruity.":::

3. Seleccione **Administrar dispositivos**.

4. Seleccione el dispositivo que desea quitar.

5. Seleccione **Administrar**.

6. Seleccione el tipo de eliminación remota que desea realizar.

    - Para realizar una eliminación completa y restaurar el dispositivo a su configuración de fábrica, seleccione **Restablecimiento de fábrica.**
    - Para realizar un borrado selectivo y eliminar solo Microsoft 365 de la organización, seleccione **Quitar datos de la empresa**.
    - Para quitar el dispositivo de la organización, selecciona **Quitar dispositivo**.

7. Seleccione **Sí** para confirmar.

## <a name="how-do-i-know-it-worked"></a>¿Cómo sé que funcionó?

Ya no ves el dispositivo móvil en la lista de dispositivos administrados.

## <a name="why-would-you-want-to-wipe-a-device"></a>¿Por qué quieres borrar un dispositivo?

Borre un dispositivo por estos motivos:

- Los dispositivos móviles, como smartphones y tabletas, son cada vez más completos. Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial, como la identificación personal o las comunicaciones confidenciales, y acceder a ella sobre la marcha. Si uno de estos dispositivos móviles se pierde o se roba, limpiar el dispositivo puede ayudar a evitar que la información de la organización termine en manos equivocadas.
- Cuando un usuario deja la organización con un dispositivo personal inscrito en Movilidad y seguridad básicas, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.
- Si tu organización proporciona dispositivos móviles a los usuarios, es posible que debas reasignar dispositivos de vez en cuando. Hacer un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimine cualquier información confidencial del propietario anterior.

## <a name="whats-the-user-and-device-impact"></a>¿Cuál es el impacto del usuario y del dispositivo?

El borrado se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory. Aunque todos los datos se quitan cuando un dispositivo se restablece a los valores predeterminados de fábrica, en la tabla siguiente se describe qué contenido se quita para cada tipo de dispositivo cuando un dispositivo quita los datos de la empresa.

|**Impacto en el contenido**|**iOS 10 y versiones posteriores**|**Android 5 y versiones posteriores**|
|:-----|:-----|:-----|
|Microsoft 365 datos de la aplicación se borran si el dispositivo está protegido por directivas de Protección de aplicaciones de Intune. Las aplicaciones no se quitan. Para dispositivos que no están protegidos por directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.<br/>**Nota** Para aplicar directivas de Protección de aplicaciones de Intune, debe tener una licencia de Intune.|Sí|Sí|
|La configuración de directiva aplicada por Movilidad básica y Seguridad a los dispositivos ya no se aplica; los usuarios pueden cambiar la configuración.|Sí|Sí|
|Los perfiles de correo electrónico creados por Basic Mobility and Security se quitan y se elimina el correo electrónico almacenado en caché en el dispositivo.|Sí|N/D|

> [!NOTE]
> Portal de empresa app está disponible en la App Store para iOS y la Play Store para dispositivos Android.
