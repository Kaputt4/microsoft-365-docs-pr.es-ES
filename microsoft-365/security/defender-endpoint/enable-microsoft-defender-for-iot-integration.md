---
title: Habilitar la integración de Microsoft Defender para IoT en Microsoft Defender para endpoint
description: Habilitar la integración de Microsoft Defender para IoT para obtener visibilidad centrada en dispositivos IoT/OT en áreas de la red donde MDE no está implementado
keywords: habilitar siem connector, siem, connector, security information and events
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 00b7a7abbf6c9fcb9395723e5e62ef0e89b2114a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470535"
---
# <a name="enable-microsoft-defender-for-iot-integration"></a>Habilitar Microsoft Defender para la integración de IoT

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft Defender para endpoint ahora se puede integrar con Microsoft Defender para IoT. Esta integración amplía las capacidades de detección de dispositivos con las funciones de supervisión sin agente proporcionadas por Microsoft Defender para IoT. Esto ayudará a proteger los dispositivos ioT empresariales conectados a redes de IT, como dispositivos de voz sobre protocolo de Internet (VoIP), impresoras y cámaras. Permite a las organizaciones aprovechar una única solución integrada que protege toda su infraestructura de IoT y tecnología operativa (OT). Para obtener más información, [vea Enterprise protección de red de IoT](/azure/defender-for-iot/organizations/overview-eiot).

Con esta integración habilitada, Microsoft Defender para endpoint obtiene mayor visibilidad para ayudar a localizar, identificar y proteger los dispositivos IoT en la red. Los dispositivos IoT detectados por Microsoft Defender para IoT o Microsoft Defender para Endpoint se sincronizarán automáticamente en ambos portales. Esto le dará una única vista unificada de su inventario completo de OT/IoT junto con el resto de sus dispositivos de TI (estaciones de trabajo, servidores y dispositivos móviles).

Microsoft Defender para IoT también incluye un sensor de red implementable que proporciona un origen de datos adicional. La configuración de un sensor de red como parte de la integración le ofrece la vista más completa de los dispositivos IoT y OT, específicamente para segmentos de red en los que los sensores de Microsoft Defender para endpoints no están presentes y cuando los empleados tienen acceso a la información de forma remota.

## <a name="prerequisites"></a>Requisitos previos

Para habilitar Microsoft Defender para IoT, el usuario debe tener los siguientes roles:

- Administrador global de inquilinos en Azure Active Directory
- Administrador de seguridad de la suscripción de Azure que se usará para la integración de Microsoft Defender para IoT

## <a name="enabling-the-microsoft-defender-for-iot-integration"></a>Habilitar la integración de Microsoft Defender para IoT

1. En el panel de navegación del [https://security.microsoft.com](https://security.microsoft.com/) portal, seleccione **Configuración** \> **Detección de** \> **dispositivos de Microsoft Defender para IoT**.

   :::image type="content" source="images/enable-defender-for-iot.png" alt-text="Configuración de integración de IoT" lightbox="images/enable-defender-for-iot.png":::

2. **Seleccione una suscripción de Azure** en la lista desplegable de suscripciones disponibles en Azure Active Directory inquilino y **seleccione Guardar**.

## <a name="set-up-a-network-sensor"></a>Configurar un sensor de red

Con una suscripción de Azure seleccionada, puede agregar un sensor de red.

Para agregar un sensor de red, en **Configurar sensores de red** , elija el vínculo **Microsoft Defender para IoT** . Esto le lleva al proceso de configuración del sensor incorporado en Azure Portal. Para obtener más información, consulte [Manage sensors with Defender for IoT in the Azure Portal](/azure/defender-for-iot/organizations/how-to-manage-sensors-on-the-cloud).

## <a name="turn-off-subscription-integration"></a>Desactivar la integración de suscripción

Puede desactivar la integración de la suscripción de Azure desde la página de configuración de Microsoft Defender para IoT en el [https://security.microsoft.com](https://security.microsoft.com/) portal. Una vez desactivada la suscripción, ya no verá los dispositivos IoT detectados por Microsoft Defender para IoT en el inventario de dispositivos de Microsoft Defender para endpoint.

## <a name="see-also"></a>Vea también

- [Información general de la detección de dispositivo](configure-device-discovery.md)
- [Preguntas más frecuentes sobre la detección de dispositivo](device-discovery-faq.md)
