---
title: Novedades de Microsoft Defender para punto de conexión en Android
description: Obtenga información sobre los cambios principales de las versiones anteriores de Microsoft Defender para punto de conexión en Android.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 48d6ef27e71f89f6a81ac3c77ea17cf60dc90ee1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664576"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Novedades de Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender para punto de conexión ahora es Microsoft Defender en play store

Microsoft Defender para punto de conexión ahora está disponible como **Microsoft Defender** en el almacén de juegos. Con esta actualización, la aplicación estará disponible como versión preliminar para **consumidores en la región de EE. UU.**; en función de cómo inicie sesión en la aplicación con su cuenta profesional o personal, tendrá acceso a características para Microsoft Defender para punto de conexión o a características de Microsoft Defender para personas. Consulte [este blog](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals) para obtener más detalles.

## <a name="threat-and-vulnerability-management"></a>Administración de amenazas y vulnerabilidades

El 25 de enero de 2022, anunciamos la disponibilidad general de la administración de amenazas y vulnerabilidades en Android e iOS. Para obtener más información, consulte [la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663).

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Próximos cambios de permisos para Microsoft Defender para punto de conexión que ejecutan Android 11 o posterior (noviembre de 2021)

Compilación de la versión: 1.0.3501.0301 Mes de la versión: noviembre de 2021 Microsoft Defender para punto de conexión ha publicado esta actualización requerida por [Google](https://developer.android.com/distribute/play-policies#APILevel30) para actualizar a Android API 30. Este cambio pedirá a los usuarios que busquen acceso al [nuevo permiso de almacenamiento](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play), para los dispositivos que ejecutan Android 11 o posterior. Los usuarios tendrán que aceptar este nuevo permiso de almacenamiento una vez que actualicen la aplicación Defender con la versión 1.0.3501.0301 o posterior. Esto garantizará que la característica de seguridad de aplicaciones de Defender para punto de conexión funcione sin ninguna interrupción. Para obtener más información, revise las secciones siguientes.

**Cómo afectará esto a su organización:** Estos cambios surtirán efecto si usa Microsoft Defender para punto de conexión en dispositivos que ejecutan Android 11 o posterior y ha actualizado Defender para punto de conexión para que publique la compilación 1.0.3501.0301 o posterior.

> [!NOTE]
> El administrador no puede configurar los nuevos permisos de almacenamiento para "Aprobar automáticamente" mediante Microsoft Endpoint Manager. El usuario tendrá que tomar medidas para proporcionar acceso a este permiso.

- **Experiencia del usuario:** Los usuarios recibirán una notificación que indica que falta un permiso para la seguridad de aplicaciones. Si el usuario deniega este permiso, la funcionalidad "App security" se desactivará en el dispositivo. Si el usuario no acepta ni deniega el permiso, seguirá recibiendo el mensaje al desbloquear su dispositivo o abrir la aplicación, hasta que se haya aprobado.

> [!NOTE]
> Si su organización está realizando una vista previa de la característica "Protección contra alteraciones" y si el usuario no concede los nuevos permisos de almacenamiento en un plazo de 7 días a partir de la actualización a la versión más reciente, es posible que el usuario pierda el acceso a los recursos corporativos.

**Cómo prepararse:**

Notifique a los usuarios y al departamento de soporte técnico (según corresponda) que los usuarios tendrán que aceptar los nuevos permisos cuando se le pida que actualicen Defender para punto de conexión para compilar la versión 1.0.3501.0301 o posterior. Para aceptar los permisos, los usuarios deben:

1. Pulse en la notificación desde la aplicación de Defender para punto de conexión o abra la aplicación Defender para punto de conexión. Los usuarios verán una pantalla que muestra los permisos necesarios. Faltará una marca de verificación verde junto al permiso de Storage.

2. Pulse **Comenzar**.

3. Pulse el botón de alternancia para **Permitir el acceso para administrar todos los archivos.**

4. El dispositivo ahora está protegido.

  > [!NOTE]
  > Este permiso permite a Microsoft Defender para punto de conexión acceder al almacenamiento en el dispositivo del usuario, lo que ayuda a detectar y quitar aplicaciones malintencionadas y no deseadas. Microsoft Defender para punto de conexión solo accede o examina el archivo de paquete de la aplicación Android (.apk). En dispositivos con un perfil de trabajo, Defender para punto de conexión solo examina los archivos relacionados con el trabajo.
