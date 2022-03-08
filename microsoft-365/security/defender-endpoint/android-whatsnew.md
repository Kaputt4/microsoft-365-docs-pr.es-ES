---
title: Novedades de Microsoft Defender para Endpoint en Android
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para Endpoint en Android.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, installation, macos, whatsnew
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
ms.openlocfilehash: d250fefbdcc2c268563b6321ee7d91eca4881063
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328699"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Novedades de Microsoft Defender para Endpoint en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender para endpoint ahora es Microsoft Defender en la Tienda Play

Microsoft Defender para endpoint ya está disponible como **Microsoft Defender** en la tienda de juegos. Con esta actualización, la aplicación estará disponible como versión preliminar para los **consumidores** de la región de Estados Unidos: en función de cómo inicie sesión en la aplicación con su cuenta personal o laboral, tendrá acceso a las características de Microsoft Defender para Endpoint o a las características de Microsoft Defender para personas. Vea este [blog para](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals) obtener más información.

## <a name="threat-and-vulnerability-management"></a>Administración de amenazas y vulnerabilidades

El 25 de enero de 2022, anunciamos la disponibilidad general de la administración de amenazas y vulnerabilidades en Android e iOS. Para obtener más información, [consulta la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663).

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Próximos cambios de permisos para Microsoft Defender para endpoint que ejecute Android 11 o posterior (noviembre de 2021)

Compilación de la versión: 1.0.3501.0301 Mes de la versión: Noviembre de 2021 Microsoft Defender para endpoint ha publicado esta actualización requerida por [Google](https://developer.android.com/distribute/play-policies#APILevel30) para actualizar a la API de Android 30. Este cambio pedirá a los usuarios que busquen acceso a [un nuevo permiso de almacenamiento](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) para dispositivos que ejecuten Android 11 o posterior. Los usuarios tendrán que aceptar este nuevo permiso de almacenamiento una vez que actualicen la aplicación defender con la compilación de la versión 1.0.3501.0301 o posterior. Esto garantizará que la característica de seguridad de aplicaciones de Defender for Endpoint funcione sin interrupciones. Para obtener más información, revise las secciones siguientes.

**Cómo afectará esto a su organización:** Estos cambios tendrán efecto si usa Microsoft Defender para Endpoint en dispositivos que ejecutan Android 11 o versiones posteriores y actualiza Defender para endpoint para publicar la compilación 1.0.3501.0301 o posterior.

> [!NOTE]
> Los nuevos permisos de almacenamiento no se pueden configurar por el administrador en "Auto Approve" a través de Microsoft Endpoint Manager. El usuario tendrá que tomar medidas para proporcionar acceso a este permiso.

- **Experiencia del usuario:** Los usuarios recibirán una notificación que indica que falta un permiso para la seguridad de la aplicación. Si el usuario niega este permiso, la funcionalidad "Seguridad de la aplicación" se desactivará en el dispositivo. Si el usuario no acepta o deniega el permiso, seguirá recibiendo el mensaje al desbloquear su dispositivo o abrir la aplicación, hasta que se haya aprobado.

> [!NOTE]
> Si su organización está previsualizando la característica "Protección contra alteraciones" y si el usuario no concede los nuevos permisos de almacenamiento en un plazo de 7 días a partir de la actualización a la versión más reciente, es posible que el usuario pierda el acceso a los recursos corporativos.

**Cómo prepararse:**

Notifique a los usuarios y al departamento de soporte técnico (según corresponda) que los usuarios tendrán que aceptar los nuevos permisos cuando se le pida después de haber actualizado Defender for Endpoint para crear la versión 1.0.3501.0301 o posterior. Para aceptar los permisos, los usuarios deben:

1. Pulsa en la notificación Defender para endpoint desde la aplicación o abre la aplicación Defender para endpoint. Los usuarios verán una pantalla que enumera los permisos necesarios. Faltará una marca de verificación verde junto al permiso Storage usuario.

2. Pulsa **Comenzar**.

3. Pulsa el botón de alternancia **de Permitir acceso para administrar todos los archivos.**

4. El dispositivo ya está protegido.

  > [!NOTE]
  > Este permiso permite a Microsoft Defender for Endpoint acceder al almacenamiento en el dispositivo del usuario, lo que ayuda a detectar y quitar aplicaciones malintencionadas y no deseadas. Microsoft Defender for Endpoint accesses/scans Android app package file (.apk) only. En dispositivos con un perfil de trabajo, Defender para endpoint solo examina archivos relacionados con el trabajo.
