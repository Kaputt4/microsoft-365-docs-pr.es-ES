---
title: 'Información de privacidad: Microsoft Defender para endpoint en iOS'
ms.reviewer: ''
description: Describe la información de privacidad de Microsoft Defender para Endpoint en iOS
keywords: microsoft, defender, Microsoft Defender para endpoint, ios, policy, overview
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7d4a7d53286f93b1d2cede9921061d237f65be3fba5750aee797c8ded56a45b9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53902840"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>Información de privacidad: Microsoft Defender para endpoint en iOS

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender para endpoint en iOS usa una VPN para proporcionar la característica de Protección web. Esta no es una VPN normal y es una VPN local o de bucle propio que no toma tráfico fuera del dispositivo. **Microsoft o su organización, no ve su actividad de exploración.**

Defender para endpoint en iOS recopila información de los dispositivos iOS configurados y la almacena en el mismo espacio empresarial donde tiene Defender para endpoint. La información se recopila para ayudar a mantener Defender for Endpoint en iOS segura, actualizada, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre el almacenamiento de datos, vea [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).


Para obtener más información sobre las preguntas de privacidad más comunes sobre Microsoft Defender para endpoint en dispositivos móviles Android e iOS, consulta Microsoft Defender para endpoint y tu privacidad en dispositivos móviles Android e [iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)

## <a name="required-data"></a>Datos necesarios 

Los datos requeridos constan de datos necesarios para que Defender for Endpoint en iOS funcione como se esperaba. Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones. 

Esta es una lista de los tipos de datos que se recopilan: 

### <a name="web-page-or-network-information"></a>Información de red o página web 

- Nombre de dominio y dirección IP del sitio web solo cuando se detecta una conexión malintencionada o una página web. 

### <a name="device-and-account-information"></a>Información de dispositivo y cuenta 

- Información del dispositivo, como fecha &, versión de iOS, información de CPU e identificador de dispositivo, donde el identificador de dispositivo es uno de los siguientes: 

    - Wi-Fi mac del adaptador 

    - Identificador único global (GUID) generado aleatoriamente 

- Información de inquilino, dispositivo y usuario 

    - Azure Active Directory de dispositivo (AD) y el id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory. 

    - Identificador de inquilino de Azure: GUID que identifica la organización dentro de Azure Active Directory. 

    - Id. de la organización de Microsoft Defender para extremo: identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si hay problemas que afectan a un conjunto selecto de empresas y al número de empresas afectadas. 

    - Nombre principal de usuario: identificador de correo electrónico del usuario. 

### <a name="product-and-service-usage-data"></a>Datos de uso de productos y servicios 

La siguiente información se recopila solo para la aplicación de Microsoft Defender para endpoint instalada en el dispositivo. 

- Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación. 

- Acciones realizadas en la aplicación. 

- Registros de informes de bloqueo generados por iOS. 

- Datos de uso de memoria. 

## <a name="optional-data"></a>Datos opcionales 

Los datos opcionales incluyen datos de diagnóstico y datos de comentarios del cliente. Los datos de diagnóstico opcionales son datos adicionales que nos ayudan a realizar mejoras en el producto y proporcionan información mejorada que nos ayuda a detectar, diagnosticar y solucionar problemas. Estos datos solo tienen fines de diagnóstico y no son necesarios para el servicio en sí. 

Los datos de diagnóstico opcionales incluyen: 

- Uso de aplicaciones, CPU y red para Defender for Endpoint. 

- Características configuradas por el administrador para Defender for Endpoint. 

Los datos de comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario. 

- La dirección de correo electrónico del usuario, si decide proporcionarla.

- Tipo de comentarios (sonreir, fruncir, idea) y los comentarios enviados por el usuario. 

Para obtener más información, consulta [Más información sobre privacidad.](https://aka.ms/mdatpiosprivacystatement)


