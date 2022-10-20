---
title: Incorporación de dispositivos que no son de Windows al servicio Microsoft Defender para punto de conexión
description: Configure dispositivos que no sean de Windows para que puedan enviar datos del sensor al servicio de Microsoft Defender para punto de conexión.
keywords: incorporación de dispositivos que no son de Windows, macos, Linux, administración de dispositivos, configuración de dispositivos Microsoft Defender para punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 6332486cfd1937f867e77b984be64fd2d376c1f1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638618"
---
# <a name="onboard-non-windows-devices"></a>Incorporar dispositivos que no tienen Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-nonwindows-abovefoldlink)

Defender para punto de conexión proporciona una experiencia de operaciones de seguridad centralizada para plataformas windows y no windows. Podrá ver alertas de varios sistemas operativos (SO) compatibles en Microsoft 365 Defender y proteger mejor la red de su organización.

Necesitará conocer las versiones exactas de Linux distros y macOS que son compatibles con Defender para punto de conexión para que la integración funcione. Para obtener más información, consulte:

- [Microsoft Defender para punto de conexión en los requisitos del sistema Linux](microsoft-defender-endpoint-linux.md#system-requirements)
- [Microsoft Defender para punto de conexión en los requisitos del sistema macOS](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Incorporación de dispositivos que no son de Windows

Tendrá que realizar los pasos siguientes para incorporar dispositivos que no sean de Windows:

1. Seleccione el método de incorporación que prefiera:

   - En el caso de los dispositivos macOS, puede optar por incorporarse a través de Microsoft Defender para punto de conexión o a través de una solución de terceros. Para obtener más información, consulte [Microsoft Defender para punto de conexión en Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).

   - Para otros dispositivos que no sean de Windows, elija **Incorporar dispositivos que no sean de Windows mediante la integración de terceros**.
    1. En el panel de navegación, seleccione **Asociados y API** \> **Aplicaciones de asociados** . Asegúrese de que aparece la solución de terceros.
    2. En la página **Aplicaciones de asociado** , seleccione el asociado que admite los dispositivos que no son de Windows.
    3. Haga clic en **Ver** para abrir la página del asociado. Siga las instrucciones proporcionadas en la página.
    4. Después de crear una cuenta o suscribirse a la solución de asociado, debe llegar a una fase en la que se pida a un Administración global de inquilino de su organización que acepte una solicitud de permiso de la aplicación asociada. Lea detenidamente la solicitud de permiso para asegurarse de que está alineada con el servicio que necesita.

2. Ejecute una prueba de detección siguiendo las instrucciones de la solución de terceros.

## <a name="offboard-non-windows-devices"></a>Dispositivos fuera del panel que no son de Windows

En el caso de los dispositivos macOS y Linux, puede optar por desconectarse a través de Microsoft Defender para punto de conexión. En el panel de navegación, seleccione **Configuración** \> **Offboard** \> **Seleccionar sistema operativo para iniciar el proceso de eliminación**.

También puede desconectar dispositivos que no sean de Windows deshabilitando la integración de terceros. Habilite la cobertura para dispositivos que ejecutan plataformas que no son de Windows [mediante la integración de soluciones de terceros](https://security.microsoft.com/interoperability/partners).

## <a name="related-topics"></a>Temas relacionados
- [incorporar dispositivos Windows](configure-endpoints.md)
- [Incorporación de servidores](configure-server-endpoints.md)
- [Configurar las opciones del proxy y de conectividad a Internet](configure-proxy-internet.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
