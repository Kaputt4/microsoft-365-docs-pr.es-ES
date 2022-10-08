---
title: Borrado de un dispositivo móvil en Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: Use la movilidad básica y la seguridad integradas para quitar información de los dispositivos inscritos.
ms.openlocfilehash: 314c9dcd4b68a3c809b1f59e60e061b9498e9834
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187391"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Borrado de un dispositivo móvil en Basic Mobility and Security

Puede usar basic mobility and security integrado para Microsoft 365 para quitar solo información de la organización o para realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos de Microsoft 365 de su organización. Para ayudar a proteger la información de su organización, puede realizar el restablecimiento de fábrica o la eliminación de datos de la empresa:

- **Restablecimiento de fábrica**: elimina todos los datos del dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal. Una vez completado el borrado, el dispositivo se restaura a su configuración de fábrica.

- **Quitar datos de la empresa**: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.

- **Cuando se borra un dispositivo (Restablecimiento de fábrica o Eliminación de datos de empresa),** el dispositivo se quita de la lista de dispositivos administrados.

- **Restablecer automáticamente un dispositivo**: puede configurar una directiva básica de movilidad y seguridad que restablezca automáticamente un dispositivo después de que el usuario intente escribir sin éxito la contraseña del dispositivo un número específico de veces. Para ello, siga los pasos descritos en [Creación de directivas de seguridad de dispositivos en movilidad y seguridad básicas](create-device-security-policies.md).

- **Si desea conocer la experiencia del usuario** al borrar su dispositivo, consulte [¿Cuál es el impacto del usuario y del dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Borrar un dispositivo móvil

1. Inicie sesión en el Centro de administración de Microsoft 365 y vaya a la [página Mobile Administración de dispositivos (Mobile Administración de dispositivos).](https://portal.office.com/adminportal/home?#/MifoDevices)

1. Seleccione **Administrar dispositivos**.

1. Seleccione el dispositivo que desea quitar.

1. Haga clic en **Administrar**.

1. Seleccione el tipo de eliminación remota que desea realizar.

    - Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, seleccione **Restablecimiento de fábrica**.
    - Para realizar un borrado selectivo y eliminar solo la información de la organización de Microsoft 365, seleccione **Quitar datos de la empresa**.
    - Para quitar el dispositivo de la organización, seleccione **Quitar dispositivo**.

1. Seleccione **Sí** para confirmar.

## <a name="how-do-i-know-it-worked"></a>Cómo sabes que funcionó?

Ya no verá el dispositivo móvil en la lista de dispositivos administrados.

## <a name="why-would-you-want-to-wipe-a-device"></a>¿Por qué querría borrar un dispositivo?

Borre un dispositivo por estas razones:

- Los dispositivos móviles, como teléfonos inteligentes y tabletas, se están volviendo cada vez más completos. Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial, como la identificación personal o las comunicaciones confidenciales, y acceder a ella desde cualquier lugar. Si uno de estos dispositivos móviles se pierde o se roba, limpiar el dispositivo puede ayudar a evitar que la información de la organización termine en manos equivocadas.
- Cuando un usuario deja la organización con un dispositivo personal inscrito en Basic Mobility and Security, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.
- Si su organización proporciona dispositivos móviles a los usuarios, es posible que tenga que reasignar dispositivos de vez en cuando. Realizar un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimine cualquier información confidencial del propietario anterior.

## <a name="whats-the-user-and-device-impact"></a>¿Cuál es el impacto del usuario y del dispositivo?

El borrado se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory. Aunque todos los datos se quitan cuando un dispositivo se restablece a los valores predeterminados de fábrica, en la tabla siguiente se describe qué contenido se quita para cada tipo de dispositivo cuando un dispositivo se quitan los datos de la empresa.

|Impacto en el contenido|iOS|Android|
|---|---|---|
|Los datos de la aplicación de Microsoft 365 se borran si el dispositivo está protegido por Intune directivas de App Protection. Las aplicaciones no se quitan. En el caso de los dispositivos no protegidos por directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.<br/>**Nota** Para aplicar directivas de Intune Protección de aplicaciones, debe tener una licencia de Intune.|Sí|Sí|
|La configuración de directiva aplicada por Basic Mobility and Security a los dispositivos ya no se aplica; los usuarios pueden cambiar la configuración.|Sí|Sí|
|Email perfiles creados por Basic Mobility and Security se quitan y se elimina el correo electrónico almacenado en caché en el dispositivo.|Sí|N/D|

> [!NOTE]
> Portal de empresa aplicación está disponible en el App Store para iOS y Play Store para dispositivos Android.
