---
title: Borrar un dispositivo móvil en movilidad y seguridad básicas
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
search.appverid:
- MET150
description: Usa la movilidad y seguridad básicas integradas para quitar información de los dispositivos inscritos.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876833"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Borrar un dispositivo móvil en movilidad y seguridad básicas

Puede usar la movilidad básica y la seguridad integradas de Microsoft 365 para quitar solo la información de la organización o realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos de Microsoft 365 de su organización. Para ayudar a proteger la información de su organización, puede realizar un restablecimiento de fábrica o quitar los datos de la empresa:

- **Restablecimiento de** fábrica: elimina todos los datos del dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal. Una vez completada la eliminación, el dispositivo se restaura a su configuración de fábrica.

- **Quitar datos de la** empresa: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.

- **Cuando se elimina un dispositivo (Restablecimiento** de fábrica o Quitar datos de la compañía), el dispositivo se quita de la lista de dispositivos administrados.
    
- **Restablecer automáticamente** un dispositivo: puedes configurar una directiva básica de movilidad y seguridad que restablece automáticamente un dispositivo de fábrica después de que el usuario intente introducir la contraseña del dispositivo un número específico de veces. Para ello, siga los pasos descritos en Crear directivas de [seguridad de dispositivos en movilidad y seguridad básicas.](create-device-security-policies.md)
    
- **Si quieres conocer la experiencia del** usuario al borrar su dispositivo, consulta ¿Cuál es el impacto del usuario y del   [dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Borrar un dispositivo móvil

1. Vaya al Centro [de administración de Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Escriba Administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** en la lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción básica de administración de dispositivos móviles de movilidad y secruidad":::

3. Seleccione **Administrar dispositivos.**

4. Seleccione el dispositivo que desea quitar.

5. Seleccione **Administrar**.

6. Seleccione el tipo de eliminación remota que desea realizar.

    - Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, selecciona **Restablecimiento de fábrica.**
    - Para realizar una eliminación selectiva y eliminar solo la información de la organización de Microsoft 365, **seleccione Quitar datos de la empresa.**
    - Para quitar el dispositivo de la organización, selecciona **Quitar dispositivo.**

7. Seleccione **Sí** para confirmar.

## <a name="how-do-i-know-it-worked"></a>¿Cómo sé que ha funcionado?

Ya no verá el dispositivo móvil en la lista de dispositivos administrados.

## <a name="why-would-you-want-to-wipe-a-device"></a>¿Por qué quieres borrar un dispositivo?

Borre un dispositivo por estos motivos:

- Los dispositivos móviles, como smartphones y tabletas, están cada vez más completos. Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial como identificación personal o comunicaciones confidenciales y acceder a ella sobre la marcha. Si se pierde o se roba uno de estos dispositivos móviles, borrar el dispositivo puede ayudar a evitar que la información de la organización termine en manos equivocadas.
- Cuando un usuario abandona la organización con un dispositivo personal inscrito en Movilidad y Seguridad básica, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.
- Si su organización proporciona dispositivos móviles a los usuarios, es posible que deba reasignar dispositivos de vez en cuando. Realizar un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimine cualquier información confidencial del propietario anterior.

## <a name="whats-the-user-and-device-impact"></a>¿Cuál es el impacto en el usuario y el dispositivo?

La eliminación se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory. Aunque todos los datos se quitan cuando un dispositivo se restablece a los valores predeterminados de fábrica, en la tabla siguiente se describe qué contenido se quita para cada tipo de dispositivo cuando se quitan los datos de la empresa.

|**Amenaza de contenido**|**iOS 10 y versiones posteriores**|**Android 5 y versiones posteriores**|
|:-----|:-----|:-----|
|Los datos de la aplicación de Microsoft 365 se borran si el dispositivo está protegido por directivas de Intune App Protection. Las aplicaciones no se quitan. En el caso de dispositivos no protegidos por directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.<br/>**Nota** Para aplicar directivas de Protección de aplicaciones de Intune, debes tener una licencia de Intune.|Sí|Sí|
|La configuración de directiva aplicada por movilidad básica y seguridad a los dispositivos ya no se aplica; los usuarios pueden cambiar la configuración.|Sí|Sí|
|Los perfiles de correo electrónico creados por movilidad y seguridad básicas se quitan y se elimina el correo electrónico almacenado en caché en el dispositivo.|Sí|N/D|
>[!NOTE]
>La aplicación Portal de empresa está disponible en la App Store para iOS y la Play Store para dispositivos Android.

## <a name="related-topics"></a>Temas relacionados

[Configurar la Seguridad de Movilidad Básica](set-up.md)