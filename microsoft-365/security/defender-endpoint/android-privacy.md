---
title: 'Microsoft Defender para punto de conexión en Android: información de privacidad'
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y la información sobre los datos de diagnóstico recopilados en Microsoft Defender para Endpoint en Android.
keywords: microsoft, defender, Microsoft Defender para endpoint, android, privacidad, diagnóstico
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 359c52acbf59f6989a59a2fcd57886673beba815
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53590760"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender para punto de conexión en Android: información de privacidad

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint en Android recopila información de los dispositivos Android configurados y la almacena en el mismo espacio empresarial donde tiene Defender para endpoint. La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre el almacenamiento de datos, vea [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre las preguntas de privacidad más comunes sobre Microsoft Defender para endpoint en dispositivos móviles Android e iOS, consulta Microsoft Defender para endpoint y tu privacidad en dispositivos móviles Android e [iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)

## <a name="required-data"></a>Datos requeridos

Los datos requeridos constan de datos necesarios para que Defender for Endpoint for Android funcione según lo esperado. Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones. Esta es una lista de los tipos de datos que se recopilan:

### <a name="app-information"></a>Información de la aplicación

Información sobre **paquetes de** aplicaciones android malintencionadas (APK) en el dispositivo, incluidos los

- Instalar origen
- Storage ubicación (ruta de acceso de archivo) del APK
- Tiempo de instalación, tamaño del APK y permisos

### <a name="web-page--network-information"></a>Página web / Información de red

- Dirección URL completa del sitio web solo cuando se detecta una conexión malintencionada o una página web.
- Información de conexión
- Tipo de protocolo (como HTTP, HTTPS, etc.)

### <a name="device-and-account-information"></a>Información de dispositivo y cuenta

- Información del dispositivo, como fecha & hora, versión de Android, modelo OEM, información de CPU e identificador de dispositivo.
- El identificador de dispositivo es uno de los siguientes:
  - Wi-Fi mac del adaptador
  - [Id. de Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generado por Android en el momento del primer arranque del dispositivo).
  - Identificador único global (GUID) generado aleatoriamente.

- Información de inquilino, dispositivo y usuario
  - Azure Active Directory de dispositivo (AD) y el id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory.
  - Identificador de inquilino de Azure: GUID que identifica la organización dentro de Azure Active Directory.
  - Id. de la organización de Microsoft Defender para extremo: identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se verán afectadas.
  - Nombre principal del usuario: id. de correo electrónico del usuario

### <a name="product-and-service-usage-data"></a>Datos de uso de productos y servicios

La siguiente información se recopila solo para la aplicación de Microsoft Defender para endpoint instalada en el dispositivo. 

- Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación.
- Acciones realizadas en la aplicación.
- Información de detección de amenazas, como el nombre de la amenaza, la categoría, etc.
- Registros de informes de bloqueo generados por Android.

## <a name="optional-data"></a>Datos opcionales

Los datos opcionales incluyen datos de diagnóstico y datos de comentarios. Datos de diagnóstico opcionales: datos adicionales que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas. Los datos de diagnóstico opcionales incluyen:

- Uso de aplicaciones, CPU y red.
- Estado del dispositivo desde la perspectiva de la aplicación, incluido el estado del examen, los tiempos de examen, los permisos de aplicación concedidos y el estado de actualización.
- Características configuradas por el administrador.
- Información básica sobre los exploradores del dispositivo.

**Los datos de** comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario

- La dirección de correo electrónico del usuario, si decide proporcionarla.
- Tipo de comentarios (sonreir, fruncir, idea) y los comentarios enviados por el usuario.
