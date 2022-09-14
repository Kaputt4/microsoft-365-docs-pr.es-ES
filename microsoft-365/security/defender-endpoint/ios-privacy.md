---
title: 'Información de privacidad: Microsoft Defender para punto de conexión en iOS'
ms.reviewer: ''
description: Describe la información de privacidad de Microsoft Defender para punto de conexión en iOS
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, policy, overview
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
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 64e6856be6311f8e04ea8e6f5e682b52e715ef4d
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688931"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>Información de privacidad: Microsoft Defender para punto de conexión en iOS

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender para punto de conexión en iOS usa una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo. **Microsoft o su organización no ven su actividad de exploración.**

Defender para punto de conexión en iOS recopila información de los dispositivos iOS configurados y la almacena en el mismo inquilino donde tiene Defender para punto de conexión. La información se recopila para ayudar a mantener Defender para punto de conexión seguro en iOS, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre el almacenamiento de datos, consulte [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](data-storage-privacy.md).

Para obtener más información sobre las preguntas de privacidad más comunes sobre Microsoft Defender para punto de conexión en dispositivos móviles Android e iOS, consulte [Microsoft Defender para punto de conexión y su privacidad en dispositivos móviles Android e iOS](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).

## <a name="required-data"></a>Datos necesarios

Los datos necesarios constan de datos necesarios para que Defender para punto de conexión en iOS funcione según lo previsto. Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones.

Esta es una lista de los tipos de datos que se recopilan:

### <a name="web-page-or-network-information"></a>Página web o información de red

- Nombre de dominio y dirección IP del sitio web solo cuando se detecta una conexión o página web malintencionada.

### <a name="device-and-account-information"></a>Información de dispositivo y cuenta

- Información del dispositivo, como la fecha & hora, la versión de iOS, la información de CPU y el identificador de dispositivo, donde El identificador de dispositivo es uno de los siguientes:
  - Wi-Fi dirección MAC del adaptador
  - Identificador único global (GUID) generado aleatoriamente
- Información de inquilino, dispositivo y usuario
  - Id. de dispositivo de Azure Active Directory (AD) e Id. de usuario de Azure: identifica de forma única el dispositivo, El usuario, respectivamente, en Azure Active Directory.
  - Identificador de inquilino de Azure: GUID que identifica la organización en Azure Active Directory.
  - Microsoft Defender para punto de conexión id. de la organización: identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si hay problemas que afectan a un conjunto selecto de empresas y al número de empresas afectadas.
  - Nombre principal de usuario: Email id. del usuario.

### <a name="product-and-service-usage-data"></a>Datos de uso de productos y servicios

La siguiente información solo se recopila para Microsoft Defender para punto de conexión aplicación instalada en el dispositivo.

- Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación.
- Acciones realizadas en la aplicación.
- Registros de informes de bloqueo generados por iOS.
- Datos de uso de memoria.

## <a name="optional-data"></a>Datos opcionales

Los datos opcionales incluyen datos de diagnóstico y datos de comentarios del cliente. Los datos de diagnóstico opcionales son datos adicionales que nos ayudan a realizar mejoras en el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y corregir problemas. Estos datos son solo para fines de diagnóstico y no son necesarios para el propio servicio.

Los datos de diagnóstico opcionales incluyen:

- Uso de aplicaciones, CPU y red para Defender para punto de conexión.
- Características configuradas por el administrador de Defender para punto de conexión.

Los datos de comentarios se recopilan a través de comentarios desde la aplicación proporcionados por el usuario.

- La dirección de correo electrónico del usuario, si decide proporcionarla.
- Tipo de comentarios (sonrisa, ceño fruncido, idea) y los comentarios enviados por el usuario.

Para obtener más información, consulte [Más información sobre privacidad](https://aka.ms/mdatpiosprivacystatement).
