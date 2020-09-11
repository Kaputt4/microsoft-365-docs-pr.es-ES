---
title: Borrar un dispositivo móvil en la movilidad y la seguridad básicas
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
description: Use la movilidad y la seguridad básicas integradas para quitar información de dispositivos inscritos.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429955"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Borrar un dispositivo móvil en la movilidad y la seguridad básicas

Puede usar la movilidad básica integrada y la seguridad de Microsoft 365 para quitar la información de la organización, o realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos móviles pueden almacenar información de la organización confidencial y proporcionar acceso a los recursos de Microsoft 365 de la organización. Para ayudar a proteger la información de su organización, puede restablecer o quitar datos de la compañía:
    
- **Restablecimiento de fábrica**: elimina todos los datos en el dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal. Una vez finalizado el borrado, el dispositivo se restaura a su configuración de fábrica.
    
- **Quitar datos**de la compañía: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.   

- **Cuando se borra un dispositivo (restablecimiento de fábrica o eliminación de datos de la empresa)**, el dispositivo se quita de la lista de dispositivos administrados.
    
- **Restablecer automáticamente un dispositivo**: puede configurar una directiva básica de movilidad y seguridad que Factory restablece automáticamente un dispositivo después de que el usuario no intente escribir la contraseña del dispositivo un número específico de veces. Para ello, siga los pasos descritos en [Create Device Security policies in Basic Mobility and Security](create-device-security-policies.md).
    
- **Si quiere conocer la experiencia del usuario** al borrar el dispositivo, consulte  [¿cuál es el impacto del dispositivo y el usuario?](#whats-the-user-and-device-impact)   

## <a name="wipe-a-mobile-device"></a>Borrar un dispositivo móvil

1. Vaya al [centro de administración de Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Escriba administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** en la lista de resultados. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Movilidad básica y opción de administración de dispositivos móviles de secruity":::

3. Seleccione **administrar dispositivos**.

4. Seleccione el dispositivo que desea quitar.

5. Seleccione **administrar**.

6. Seleccione el tipo de eliminación remota que desea realizar.

    - Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, seleccione **restablecimiento de fábrica**.
    - Para realizar un borrado selectivo y eliminar solo la información de la organización de Microsoft 365, seleccione **Quitar datos**de la compañía.
    - Para quitar el dispositivo de la organización, seleccione **quitar dispositivo**.

7. Seleccione **Sí** para confirmar.

## <a name="how-do-i-know-it-worked"></a>¿Cómo sé que funcionó?

Ya no verá el dispositivo móvil en la lista de dispositivos administrados.

## <a name="why-would-you-want-to-wipe-a-device"></a>¿Por qué deseas borrar un dispositivo?

Limpie un dispositivo por estos motivos:

- Los dispositivos móviles, como los smartphones y las tabletas, son cada vez más completos. Esto significa que es más fácil para sus usuarios almacenar información confidencial de la empresa, como identificación personal o comunicaciones confidenciales, y tener acceso a ella en el viaje. Si se pierde o se roba uno de estos dispositivos móviles, el borrado del dispositivo puede ayudar a evitar que la información de la organización acabe en las manos equivocadas.
- Cuando un usuario deja la organización con un dispositivo personal que está inscrito en la movilidad y la seguridad básicas, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.
- Si su organización proporciona dispositivos móviles a los usuarios, es posible que tenga que reasignar los dispositivos de vez en cuando. Realizar un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimina toda la información confidencial del propietario anterior.

## <a name="whats-the-user-and-device-impact"></a>¿Cuál es el impacto de los usuarios y los dispositivos?

El barrido se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory. Mientras se eliminan todos los datos cuando se restablece un dispositivo a los valores predeterminados de fábrica, en la tabla siguiente se describe el contenido que se elimina para cada tipo de dispositivo cuando se quitan datos de la compañía.

|**Imvelocidads de contenido**|**iOS 10 y versiones posteriores**|**Android 5 y versiones posteriores**|
|:-----|:-----|:-----|
|Los datos de la aplicación Microsoft 365 se borran si el dispositivo está protegido por las directivas de protección de aplicaciones de Intune. Las aplicaciones no se quitan. Para los dispositivos no protegidos por las directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.<br/>**Nota:** Para aplicar directivas de protección de aplicaciones de Intune, debe tener una licencia de Intune.|Sí|Sí|
|La configuración de la Directiva aplicada por la movilidad básica y la seguridad a los dispositivos ya no se aplican; los usuarios pueden cambiar la configuración.|Sí|Sí|
|Los perfiles de correo electrónico creados por la movilidad básica y la seguridad se eliminan y se elimina el correo electrónico almacenado en caché en el dispositivo.|Sí|N/D|
>[!NOTE] 
>La aplicación portal de empresa está disponible en la App Store para iOS y en la tienda de reproducción para dispositivos Android.

## <a name="related-topics"></a>Temas relacionados

[Configurar la Seguridad de Movilidad Básica](set-up.md)