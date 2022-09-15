---
title: Novedades de Microsoft Defender para punto de conexión en Android
description: Obtenga información sobre los cambios principales de las versiones anteriores de Microsoft Defender para punto de conexión en Android.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, macos, whatsnew
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: bf5e73b8e382d392673a8f82616089c8990ea2a8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67695789"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Novedades de Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

>[!IMPORTANT]
> el **motor antimalware** de Microsoft Defender para punto de conexión ya está disponible con carácter general. Todos los usuarios deben tener una versión de Microsoft Defender para punto de conexión superior a **la 1.0.3815.0000** para usar esta nueva funcionalidad de protección contra malware. A los usuarios de Microsoft Defender para punto de conexión versión inferior a la 1.0.3815.0000 se les enviarán notificaciones y mensajes de superposición desde la aplicación para actualizar sus Microsoft Defender para punto de conexión aplicación. Los usuarios pueden hacer clic en el vínculo proporcionado en el mensaje de superposición para ir al almacén de reproducción administrado y actualizar la aplicación. 
>
> Si los usuarios no pueden acceder a play store, la aplicación se puede actualizar a través del portal de empresa. 

## <a name="privacy-controls"></a>Controles de privacidad

Microsoft Defender para punto de conexión en Android habilita los controles de privacidad tanto para los administradores como para los usuarios finales. Esto incluye los controles para dispositivos inscritos (MDM) y no inscritos (MAM) (en versión preliminar). Los administradores pueden configurar la privacidad en el informe de alertas, mientras que los usuarios finales pueden configurar la información compartida con su organización. Para obtener más información, consulte [Controles de privacidad (MDM)](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) y [controles de privacidad (MAM).](/microsoft-365/security/defender-endpoint/android-configure-mam#configure-privacy-controls)

## <a name="optional-permissions-and-disable-web-protection"></a>Permisos opcionales y deshabilitación de la protección web

Microsoft Defender para punto de conexión en Android habilita **permisos opcionales** en el flujo de incorporación. Actualmente, los permisos requeridos por MDE son obligatorios en el flujo de incorporación. Con esta característica, el administrador puede implementar MDE en dispositivos sin aplicar los permisos **obligatorios de VPN** y **accesibilidad** durante la incorporación. Los usuarios finales pueden incorporar la aplicación sin los permisos obligatorios y pueden revisarlos más adelante. Esta característica solo está presente actualmente para dispositivos no inscritos (MAM). Para obtener más información, consulte [permisos opcionales](/microsoft-365/security/defender-endpoint/android-configure-mam#optional-permissions).


## <a name="microsoft-defender-on-android-enterprise-byod-personal-profile"></a>Perfil personal byod de Microsoft Defender en Android Enterprise
Microsoft Defender para punto de conexión ahora se admite en el perfil personal de Android Enterprise (solo BYOD) con todas las características clave, como el análisis de malware, la protección contra vínculos de phishing, la protección de red y la administración de vulnerabilidades. Esta compatibilidad se combina con [controles de privacidad](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) para garantizar la privacidad del usuario en el perfil personal. Para obtener más información, lea el [anuncio](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979) y la [guía de implementación](/microsoft-365/security/defender-endpoint/android-intune#set-up-microsoft-defender-in-personal-profile-on-android-enterprise-in-byod-mode).

## <a name="network-protection"></a>Protección de red
La protección de red en Microsoft Defender para punto de conexión está ahora en versión preliminar pública. La protección de red proporciona protección contra amenazas no autorizadas Wi-Fi relacionadas, hardware no autorizado como dispositivos de piña y notifica al usuario si se detecta una amenaza relacionada. Los usuarios también verán una experiencia guiada para conectarse a redes seguras y cambiar las redes cuando estén conectadas a una conexión no segura.

Incluye varios controles de administración para ofrecer flexibilidad, como la capacidad de configurar la característica desde el Centro de microsoft Endpoint Manager Administración. Los administradores también pueden habilitar los controles de privacidad para configurar los datos enviados por Defender para punto de conexión desde dispositivos Android. 

Si está interesado en participar en esta versión preliminar pública, comparta su identificador de inquilino con nosotros en networkprotection@microsoft.com. Para obtener más información, consulte [Protección de red](/microsoft-365/security/defender-endpoint/android-configure).

>[!NOTE]
>Microsoft Defender ya no es compatible con versiones inferiores a 1.0.3011.0302. Se solicita a los usuarios que actualicen a las versiones más recientes para proteger sus dispositivos.
Para actualizar, los usuarios pueden seguir estos pasos:
>1. En tu perfil de trabajo, ve a Managed Play Store.
>2. Pulse en el icono de perfil de la esquina superior derecha y seleccione "Administrar aplicaciones y dispositivos".
>3. Busque MDE en Actualizaciones disponibles y seleccione Actualizar.
>
>Si encuentra algún problema, [envíe comentarios desde la aplicación](/security/defender-endpoint/android-support-signin#send-in-app-feedback).

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender para punto de conexión ahora es Microsoft Defender en play store

Microsoft Defender para punto de conexión ahora está disponible como **Microsoft Defender** en el almacén de juegos. Con esta actualización, la aplicación estará disponible como versión preliminar para **consumidores en la región de EE. UU.**; en función de cómo inicie sesión en la aplicación con su cuenta profesional o personal, tendrá acceso a características para Microsoft Defender para punto de conexión o a características de Microsoft Defender para personas. Consulte [este blog](https://www.microsoft.com/microsoft-365/microsoft-defender-for-individuals) para obtener más detalles.

## <a name="vulnerability-management"></a>Administración de vulnerabilidades

El 25 de enero de 2022, anunciamos la disponibilidad general de la administración de vulnerabilidades en Android e iOS. Para obtener más información, consulte [la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663).

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Próximos cambios de permisos para Microsoft Defender para punto de conexión que ejecutan Android 11 o posterior (noviembre de 2021)

Compilación de la versión: 1.0.3501.0301 Mes de la versión: noviembre de 2021 Microsoft Defender para punto de conexión ha publicado esta actualización requerida por [Google](https://developer.android.com/distribute/play-policies#APILevel30) para actualizar a Android API 30. Este cambio pedirá a los usuarios que busquen acceso al [nuevo permiso de almacenamiento](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play), para los dispositivos que ejecutan Android 11 o posterior. Los usuarios tendrán que aceptar este nuevo permiso de almacenamiento una vez que actualicen la aplicación Defender con la versión 1.0.3501.0301 o posterior. Esto garantizará que la característica de seguridad de aplicaciones de Defender para punto de conexión funcione sin ninguna interrupción. Para obtener más información, revise las secciones siguientes.

**Cómo afectará esto a su organización:** Estos cambios surtirán efecto si usa Microsoft Defender para punto de conexión en dispositivos que ejecutan Android 11 o posterior y ha actualizado Defender para punto de conexión para que publique la compilación 1.0.3501.0301 o posterior.

> [!NOTE]
> El administrador no puede configurar los nuevos permisos de almacenamiento para "Aprobar automáticamente" a través de Microsoft Endpoint Manager. El usuario tendrá que tomar medidas para proporcionar acceso a este permiso.

- **Experiencia del usuario:** Los usuarios recibirán una notificación que indica que falta un permiso para la seguridad de aplicaciones. Si el usuario deniega este permiso, la funcionalidad "App security" se desactivará en el dispositivo. Si el usuario no acepta ni deniega el permiso, seguirá recibiendo el mensaje al desbloquear su dispositivo o abrir la aplicación, hasta que se haya aprobado.

> [!NOTE]
> Si su organización está realizando una vista previa de la característica "Protección contra alteraciones" y si el usuario no concede los nuevos permisos de almacenamiento en un plazo de 7 días a partir de la actualización a la versión más reciente, es posible que el usuario pierda el acceso a los recursos corporativos.

**Cómo prepararse:**

Notifique a los usuarios y al departamento de soporte técnico (según corresponda) que los usuarios tendrán que aceptar los nuevos permisos cuando se le pida que actualicen Defender para punto de conexión para compilar la versión 1.0.3501.0301 o posterior. Para aceptar los permisos, los usuarios deben:

1. Pulse en la notificación desde la aplicación de Defender para punto de conexión o abra la aplicación Defender para punto de conexión. Los usuarios verán una pantalla que muestra los permisos necesarios. Faltará una marca de verificación verde junto al permiso Almacenamiento.

2. Pulse **Comenzar**.

3. Pulse el botón de alternancia para **Permitir el acceso para administrar todos los archivos.**

4. El dispositivo ahora está protegido.

  > [!NOTE]
  > Este permiso permite a Microsoft Defender para punto de conexión acceder al almacenamiento en el dispositivo del usuario, lo que ayuda a detectar y quitar aplicaciones malintencionadas y no deseadas. Microsoft Defender para punto de conexión solo accede o examina el archivo de paquete de la aplicación Android (.apk). En dispositivos con un perfil de trabajo, Defender para punto de conexión solo examina los archivos relacionados con el trabajo.
