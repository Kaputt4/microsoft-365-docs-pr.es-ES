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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 820c93804615e9aafcb34052d65f09bbd3e3d1c9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717644"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Novedades de Microsoft Defender para Endpoint en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later"></a>Próximos cambios de permisos para Microsoft Defender para endpoint que ejecute Android 11 o posterior

En noviembre, Microsoft Defender para Endpoint será requerido por [Google](https://developer.android.com/distribute/play-policies#APILevel30) para pasar a la API de Android 30. Este movimiento pedirá un nuevo permiso [de almacenamiento](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) para dispositivos que ejecutan Android 11 o posterior. Los usuarios tendrán que aceptar este nuevo permiso de almacenamiento una vez que actualicen a la versión de noviembre de Microsoft Defender para endpoint. Esto continuará con la funcionalidad "Seguridad de la aplicación" de Defender en sus dispositivos. Para obtener más información, vea los detalles de las secciones siguientes.

**Cómo afectará esto a su organización:**

Estos cambios solo te afectarán si usas Microsoft Defender para Endpoint en dispositivos que ejecutan Android 11 o posterior y se actualizan a la aplicación de noviembre. Esta configuración no se puede configurar mediante Microsoft Endpoint Manager; los usuarios tendrán que tomar medidas debido a los cambios de la API de Google mencionados anteriormente.

- **Experiencia del usuario:** Los usuarios recibirán una notificación que indica que falta un permiso para la seguridad de la aplicación. Si el usuario niega este permiso, la funcionalidad "Seguridad de la aplicación" se desactivará en el dispositivo. Si el usuario no acepta o deniega el permiso, seguirá recibiendo el mensaje al desbloquear su dispositivo o abrir la aplicación hasta que se haya aprobado.

>[!NOTE] 
> Si su organización está previsualizando la característica "Protección contra alteraciones" y si el usuario no concede los nuevos permisos de almacenamiento en un plazo de 7 días a partir de la actualización a la versión más reciente, es posible que el usuario pierda el acceso a los recursos corporativos.

**Lo que necesita hacer para preparar:**

Notifique a los usuarios y al departamento de soporte técnico (según corresponda) que los usuarios tendrán que aceptar los nuevos permisos cuando se les pida una vez que se actualicen a la versión de noviembre de la aplicación Microsoft Defender para endpoint. Para aceptar los permisos, los usuarios deben:

1. Pulsa en la notificación desde la aplicación defender o abre la aplicación Microsoft Defender para endpoint. Los usuarios verán una pantalla que enumera los permisos necesarios. Faltará una marca de verificación verde junto al Storage permiso.

2. Pulsa **Comenzar**.

3. Pulsa el botón de alternancia **de Permitir acceso para administrar todos los archivos.** 

  >[!NOTE] 
  >Este permiso permite a Microsoft Defender for Endpoint acceder al almacenamiento en el dispositivo del usuario, lo que ayuda a detectar y quitar aplicaciones malintencionadas y no deseadas. Microsoft Defender para endpoint solo accede o examina el archivo del paquete de la aplicación Android (.apk) y en dispositivos con un perfil de trabajo, solo examina archivos relacionados con el trabajo.

4. El dispositivo ya está protegido.





