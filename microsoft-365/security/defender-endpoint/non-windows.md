---
title: Microsoft Defender para punto de conexión para plataformas que no sean de Windows
description: Más información sobre las funcionalidades de Microsoft Defender para punto de conexión para plataformas que no son de Windows
keywords: no windows, mac, macos, linux, android
search.product: eADQiWindows 10XVcnh
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
- m365solution-evalutatemtp
- highpri
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 9aa75ec8defb9c9df576efb65dda4aa674afe690
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637891"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Microsoft Defender para punto de conexión para plataformas que no sean de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión, plan 1 y plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft ha estado en un viaje para ampliar sus capacidades de seguridad de punto de conexión líderes del sector más allá de Windows y Windows Server a macOS, Linux, Android e iOS.

Las organizaciones se enfrentan a amenazas en una variedad de plataformas y dispositivos. Nuestros equipos se han comprometido a crear soluciones de seguridad no solo *para* Microsoft, sino también *desde* Microsoft para permitir a nuestros clientes proteger y asegurar sus entornos heterogéneos. Estamos escuchando los comentarios de los clientes y colaborando estrechamente con nuestros clientes para crear soluciones que satisfagan sus necesidades.

Con Microsoft Defender para punto de conexión, los clientes se benefician de una vista unificada de todas las amenazas y alertas en el portal de Microsoft 365 Defender, en todas las plataformas Windows y no Windows, lo que les permite obtener una imagen completa de lo que está sucediendo en su entorno, lo que les permite evaluar y responder más rápidamente a las amenazas.

## <a name="microsoft-defender-for-endpoint-on-macos"></a>Microsoft Defender para punto de conexión en macOS

Microsoft Defender para punto de conexión en macOS ofrece funcionalidades de antivirus, detección y respuesta de puntos de conexión (EDR) y administración de vulnerabilidades para las tres versiones más recientes de macOS. Los clientes pueden implementar y administrar la solución a través de Microsoft Endpoint Manager y Jamf. Al igual que con las aplicaciones de Microsoft Office en macOS, Microsoft Auto Update se usa para administrar las actualizaciones de Microsoft Defender para punto de conexión en Mac. Para obtener información sobre las principales características y ventajas, lea nuestros [anuncios](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).

Para obtener más información sobre cómo empezar, visite la [documentación](microsoft-defender-endpoint-mac.md) de Defender para punto de conexión en macOS.

> [!NOTE]
> Las siguientes funcionalidades no se admiten actualmente en los puntos de conexión de macOS:
>
> - Administración de seguridad para Microsoft Defender para punto de conexión

## <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender para punto de conexión en Linux

Microsoft Defender para punto de conexión en Linux ofrece antivirus preventivo (AV), detección y respuesta de puntos de conexión (EDR) y funcionalidades de administración de vulnerabilidades para servidores Linux. Esto incluye una experiencia de línea de comandos completa para configurar y administrar el agente, iniciar exámenes y administrar amenazas. Se admiten versiones recientes de las seis distribuciones más comunes de Linux Server: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS o superior LTS, SLES 12+, Debian 9+, y Oracle Linux 7.2. Microsoft Defender para punto de conexión en Linux se puede implementar y configurar mediante Puppet, Ansible o con la herramienta de administración de configuración de Linux existente. Para obtener más información sobre las principales características y ventajas, lea nuestros [anuncios](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).

Para obtener más información sobre cómo empezar, visite la [documentación](microsoft-defender-endpoint-linux.md) de Microsoft Defender para punto de conexión en Linux.


> [!NOTE]
> Las siguientes funcionalidades no se admiten actualmente en los puntos de conexión de Linux:
>
> - Prevención de pérdida de datos
> - Administración de seguridad para Microsoft Defender para punto de conexión

## <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender para punto de conexión en Android

Microsoft Defender para punto de conexión en Android es nuestra solución de defensa contra amenazas móviles para dispositivos que ejecutan Android 6.0 y versiones posteriores. Se admiten los modos Android Enterprise (perfil de trabajo) y Administrador de dispositivos. En Android, ofrecemos protección web que incluye protección contra suplantación de identidad,bloqueo de conexiones no seguras y configuración de indicadores personalizados. La solución busca malware y aplicaciones potencialmente no deseadas (PUA) y ofrece funcionalidades adicionales de prevención de infracciones mediante la integración con Microsoft Endpoint Manager y el acceso condicional. Para obtener información sobre las principales características y ventajas, lea nuestros [anuncios](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).

Para obtener más información sobre cómo empezar, visite la [documentación](microsoft-defender-endpoint-android.md) de Microsoft Defender para punto de conexión en Android.

## <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para punto de conexión en iOS

Microsoft Defender para punto de conexión en iOS es nuestra solución de defensa contra amenazas móviles para dispositivos que ejecutan iOS 11.0 y versiones posteriores. Se admiten los dispositivos registrados en el inquilino de un cliente (inscritos o no inscritos). Se admiten dispositivos inscritos, tanto supervisados como no supervisados. En iOS, ofrecemos protección web, que incluye protección contra la suplantación de identidad, bloqueo de conexiones no seguras y establecimiento de indicadores personalizados, y detección de jailbreak. Para obtener más información sobre las principales características y ventajas, lea nuestros [anuncios](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

Para obtener más información sobre cómo empezar, visite la [documentación](microsoft-defender-endpoint-ios.md) de Microsoft Defender para punto de conexión en iOS.

## <a name="licensing-requirements"></a>Requisitos de licencias

Los usuarios con licencia elegibles pueden usar Microsoft Defender para punto de conexión en un máximo de cinco dispositivos simultáneos. Microsoft Defender para punto de conexión también está disponible para su compra desde un proveedor de soluciones en la nube (CSP).

Los clientes pueden obtener Microsoft Defender para punto de conexión en macOS a través de una licencia independiente de Microsoft Defender para punto de conexión, como parte de Microsoft 365 A5/E5 o Microsoft 365 Security.

Las funcionalidades recientemente anunciadas de Microsoft Defender para punto de conexión en Android e iOS se incluyen en las ofertas mencionadas anteriormente como parte de los cinco dispositivos calificados para los usuarios con licencia elegibles.

Defender para punto de conexión en Linux está disponible a través de la SKU Defender for Endpoint Server, que está disponible tanto para clientes comerciales como para clientes del sector educativo.

Póngase en contacto con su equipo de cuentas o CSP para conocer los precios y los requisitos de elegibilidad adicionales.
