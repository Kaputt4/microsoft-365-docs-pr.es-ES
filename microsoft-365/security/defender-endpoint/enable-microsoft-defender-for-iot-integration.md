---
title: Incorporación de Microsoft Defender para IoT con Microsoft Defender para punto de conexión
description: Incorporación con Microsoft Defender para IoT para obtener visibilidad y evaluaciones de seguridad centradas en dispositivos IoT.
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
ms.openlocfilehash: a70b61ff9a27b10e66b6f4537751790eaabc59af
ms.sourcegitcommit: 44ece87e3e0c0c851dfc1e77211ac3e5e4a5b973
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66617290"
---
# <a name="onboard-with-microsoft-defender-for-iot"></a>Incorporación con Microsoft Defender para IoT

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft Defender para punto de conexión ahora se integra perfectamente con Microsoft Defender para IoT. Esta integración amplía las funcionalidades de detección de dispositivos con las funcionalidades de supervisión sin agente proporcionadas por Defender para IoT. Esto ayudará a proteger los dispositivos IoT empresariales conectados a redes de TI, como dispositivos de voz a través de Protocolo de Internet (VoIP), impresoras y cámaras. Permite a las organizaciones aprovechar una única solución integrada que protege toda su infraestructura de IoT y tecnología operativa (OT). Para obtener más información, consulte [Protección de red de IoT empresarial](/azure/defender-for-iot/organizations/overview-eiot).

Una vez que haya definido un plan de Defender para IoT y configurado un sensor de red de IoT empresarial, los datos del dispositivo inician automáticamente el streaming en los portales de Defender para punto de conexión y Defender para IoT. 

La integración de Defender para IoT proporciona una mayor visibilidad para ayudar a localizar, identificar y proteger los dispositivos IoT en la red. Esto le proporcionará una única vista unificada del inventario de OT/IoT completo junto con el resto de los dispositivos de TI (estaciones de trabajo, servidores y dispositivos móviles).

Los clientes que se han incorporado a Defender para IoT también tienen recomendaciones de seguridad para evaluaciones de vulnerabilidades y configuraciones incorrectas para dispositivos IoT.

## <a name="prerequisites"></a>Requisitos previos

Para modificar la configuración de la integración de Defender para punto de conexión, el usuario debe tener los siguientes roles:

- Administrador global de inquilinos en Azure Active Directory
- Administrador de seguridad de la suscripción de Azure que se usará para la integración de Microsoft Defender para IoT

## <a name="onboard-a-defender-for-iot-plan"></a>Incorporación de un plan de Defender para IoT

1. En el panel de navegación del [https://security.microsoft.com](https://security.microsoft.com/) portal, seleccione **Configuración Detección** \> **de dispositivos** \> **Enterprise IoT**.

1. Seleccione las siguientes opciones para el plan:

   - Seleccione la suscripción de Azure en la lista de suscripciones disponibles en el inquilino de Azure Active Directory donde desea agregar un plan.

   - Seleccione un plan de precios, un compromiso mensual o anual, o una evaluación. Microsoft Defender para IoT proporciona una evaluación gratuita de 30 días para los primeros 1000 dispositivos confirmados con fines de evaluación.

      Para obtener más información, consulte la [página de precios de Microsoft Defender para IoT](https://azure.microsoft.com/pricing/details/iot-defender/).
   
   - Seleccione el número de dispositivos confirmados que desea supervisar. Si seleccionó una prueba, esta sección no aparece porque tiene un valor predeterminado de 1000 dispositivos.

## <a name="set-up-a-network-sensor"></a>Configuración de un sensor de red

Para configurar un sensor de red, la suscripción de Azure debe tener un plan de Defender para IoT con dispositivos IoT empresariales agregados. Para obtener más información, consulte [Introducción a Defender para IoT](/azure/defender-for-iot/organizations/getting-started).

Para agregar un sensor de red, en **Configurar sensores de red** , elija el vínculo **Microsoft Defender para IoT** . Esto le lleva al proceso de configuración del sensor de incorporación en el Azure Portal. Para obtener más información, consulte [Introducción a Enterprise IoT](/azure/defender-for-iot/organizations/tutorial-getting-started-eiot-sensor).

## <a name="managing-your-iot-devices"></a>Administración de dispositivos IoT

Para ver y administrar los dispositivos IoT en Microsoft 365 Defender [portal](https://security.microsoft.com/), vaya al **inventario** de dispositivos en el menú de navegación **Puntos de conexión** y seleccione la pestaña **Dispositivos IoT**.

Para obtener información sobre cómo ver los dispositivos en Defender para IoT, consulte [Administración de dispositivos IoT con el inventario de dispositivos para organizaciones](/azure/defender-for-iot/organizations/how-to-manage-device-inventory-for-organizations).


## <a name="view-devices-alerts-recommendations-and-vulnerabilities"></a>Visualización de dispositivos, alertas, recomendaciones y vulnerabilidades

Después de definir el plan y configurar un sensor de red, vea los datos detectados y las evaluaciones de seguridad en las siguientes ubicaciones:

- Visualización de datos de dispositivos en Defender para punto de conexión o Defender para IoT
- Visualización de alertas, recomendaciones y vulnerabilidades en Defender para punto de conexión

Para obtener más información, consulte la [página de precios de Defender para IoT](https://azure.microsoft.com/pricing/details/iot-defender/). 

## <a name="cancel-your-defender-for-iot-plan"></a>Cancelación del plan de Defender para IoT

Puede cancelar el plan de Defender para IoT desde la página configuración de Defender para punto de conexión del [https://security.microsoft.com](https://security.microsoft.com/) portal. Una vez que cancele el plan, la integración se detiene y ya no obtendrá el valor de evaluación de seguridad en Defender para punto de conexión ni detectará nuevos dispositivos en Defender para IoT.

## <a name="see-also"></a>Vea también

- [Información general de la detección de dispositivo](configure-device-discovery.md)
- [Preguntas más frecuentes sobre la detección de dispositivo](device-discovery-faq.md)
