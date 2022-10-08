---
title: 'Microsoft Defender para punto de conexión en Android: información de privacidad'
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y a la información sobre los datos de diagnóstico recopilados en Microsoft Defender para punto de conexión en Android.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, android, privacidad, diagnóstico
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: a65012792f930c77977537b724cf36d94cc2527b
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68145675"
---
# <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender para punto de conexión en Android: información de privacidad

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender para punto de conexión en Android recopila información de los dispositivos Android configurados y la almacena en el mismo inquilino donde tiene Defender para punto de conexión. La información se recopila para ayudar a mantener Defender para punto de conexión para Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre el almacenamiento de datos, consulte [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](data-storage-privacy.md).

La información se recopila para ayudar a mantener Defender para punto de conexión para Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre las preguntas de privacidad más comunes sobre Microsoft Defender para punto de conexión en dispositivos móviles Android e iOS, consulte [Microsoft Defender para punto de conexión y su privacidad en dispositivos móviles Android e iOS](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).

## <a name="required-data"></a>Datos necesarios

Los datos necesarios constan de datos necesarios para que Defender para punto de conexión para Android funcione según lo previsto. Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones. Esta es una lista de los tipos de datos que se recopilan:

### <a name="app-information"></a>Información de la aplicación

Información sobre paquetes de aplicaciones Android (APK) **malintencionados** en el dispositivo, incluido

- Instalación del origen
- Ubicación de almacenamiento (ruta de acceso del archivo) del APK
- Hora de instalación, tamaño del APK y permisos

Para dispositivos Android Enterprise totalmente administrados: información sobre los paquetes de aplicaciones Android (APK) instalados en el dispositivo, incluido

- Nombre y nombre del paquete de la aplicación
- Número de versión de la aplicación
- Nombre de proveedor

Para Android Enterprise con un perfil de trabajo: información sobre los paquetes de aplicaciones Android (APK) instalados en el perfil de trabajo del dispositivo, incluido

- Nombre y nombre del paquete de la aplicación
- Número de versión de la aplicación
- Nombre de proveedor

*Su organización también puede optar por configurar Defender para punto de conexión para enviar información sobre todas las aplicaciones instaladas en el dispositivo. De forma predeterminada, esta información no se envía a su organización.*


### <a name="web-page--network-information"></a>Página web/Información de red

- Dirección URL completa del sitio web solo cuando se detecta y bloquea una conexión o página web malintencionada.
- Información de conexión
- Tipo de protocolo (como HTTP, HTTPS, etc.)

### <a name="device-and-account-information"></a>Información de dispositivo y cuenta

- Información del dispositivo, como la fecha & hora, la versión de Android, el modelo OEM, la información de CPU y el identificador de dispositivo.
- El identificador de dispositivo es uno de los siguientes:
  - Wi-Fi dirección MAC del adaptador
  - [Id. de Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generado por Android en el momento del primer arranque del dispositivo).
  - Identificador único global (GUID) generado aleatoriamente.

- Información de inquilino, dispositivo y usuario
  - Id. de dispositivo de Azure Active Directory (AD) e Id. de usuario de Azure: identifica de forma única el dispositivo, El usuario, respectivamente, en Azure Active Directory.
  - Identificador de inquilino de Azure: GUID que identifica la organización en Azure Active Directory.
  - Microsoft Defender para punto de conexión identificador de la organización: identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se ven afectadas.
  - Nombre principal de usuario: Email id. del usuario

### <a name="product-and-service-usage-data"></a>Datos de uso de productos y servicios

La siguiente información solo se recopila para Microsoft Defender para punto de conexión aplicación instalada en el dispositivo. 

- Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación.
- Acciones realizadas en la aplicación.
- Información de detección de amenazas, como nombre de amenaza, categoría, etc.
- Registros de informe de bloqueo generados por Android.

## <a name="optional-data"></a>Datos opcionales

Los datos opcionales incluyen datos de diagnóstico y datos de comentarios. Los datos de diagnóstico opcionales son datos adicionales que nos ayudan a realizar mejoras en el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y corregir problemas. Los datos de diagnóstico opcionales incluyen:

- Uso de la aplicación, cpu y red.
- Estado del dispositivo desde la perspectiva de la aplicación, incluido el estado del examen, los tiempos de examen, los permisos de aplicación concedidos y el estado de actualización.
- Características configuradas por el administrador.
- Información básica sobre los exploradores del dispositivo.

**Los datos de comentarios** se recopilan a través de comentarios desde la aplicación proporcionados por el usuario

- La dirección de correo electrónico del usuario, si decide proporcionarla.
- Tipo de comentarios (sonrisa, ceño fruncido, idea) y los comentarios enviados por el usuario.
