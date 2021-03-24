---
title: 'Información de privacidad: Microsoft Defender para endpoint para iOS'
ms.reviewer: ''
description: Describe la información de privacidad de Microsoft Defender para endpoint para iOS
keywords: microsoft, defender, atp, ios, policy, overview
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52694322c7f084df777a8e97fe5b84cc3cb4e6d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072307"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>Información de privacidad: Microsoft Defender para endpoint para iOS

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender para endpoint para iOS usa una VPN para proporcionar la característica de protección web. Esta no es una VPN normal y es una VPN local o de bucle propio que no toma tráfico fuera del dispositivo. **Microsoft o su organización, no ve su actividad de exploración.**

Defender para endpoint para iOS recopila información de los dispositivos iOS configurados y la almacena en el mismo espacio empresarial donde tiene Defender for Endpoint. La información se recopila para ayudar a mantener Defender for Endpoint for iOS seguro, actualizado, con el rendimiento esperado y para admitir el servicio.

Para obtener más información sobre el almacenamiento de datos, vea [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

## <a name="required-data"></a>Datos necesarios 

Los datos requeridos constan de datos necesarios para que Defender for Endpoint for iOS funcione según lo esperado. Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones. 

Esta es una lista de los tipos de datos que se recopilan: 

### <a name="web-page-or-network-information"></a>Información de red o página web 

- Nombre de dominio del sitio web solo cuando se detecta una conexión malintencionada o una página web. 

### <a name="device-and-account-information"></a>Información de dispositivo y cuenta 

- Información del dispositivo, como fecha &, versión de iOS, información de CPU e identificador de dispositivo, donde el identificador de dispositivo es uno de los siguientes: 

    - Wi-Fi mac del adaptador 

    - Identificador único global (GUID) generado aleatoriamente 

- Información de inquilino, dispositivo y usuario 

    - Id. de dispositivo de Azure Active Directory (AD) e id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory. 

    - Identificador de inquilino de Azure: GUID que identifica la organización en Azure Active Directory. 

    - Id. de la organización de Microsoft Defender para extremo: identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si hay problemas que afectan a un conjunto selecto de empresas y al número de empresas afectadas. 

    - Nombre principal de usuario: identificador de correo electrónico del usuario. 

### <a name="product-and-service-usage-data"></a>Datos de uso de productos y servicios 

La siguiente información se recopila solo para la aplicación de Microsoft Defender para endpoint instalada en el dispositivo. 

- Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación. 

- Acciones realizadas en la aplicación. 

- Registros de informes de bloqueo generados por iOS. 

- Datos de uso de memoria. 

## <a name="optional-data"></a>Datos opcionales 

Los datos opcionales incluyen datos de diagnóstico y datos de comentarios del cliente. Datos de diagnóstico opcionales: datos adicionales que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas. Estos datos solo tienen fines de diagnóstico y no son necesarios para el servicio en sí. 

Los datos de diagnóstico opcionales incluyen: 

- Uso de aplicaciones, CPU y red para Defender for Endpoint. 

- Características configuradas por el administrador para Defender for Endpoint. 

Los datos de comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario. 

- La dirección de correo electrónico del usuario, si decide proporcionarla.

- Tipo de comentarios (sonreir, fruncir, idea) y los comentarios enviados por el usuario. 

Para obtener más información, consulta [Más información sobre privacidad.](https://aka.ms/mdatpiosprivacystatement)


