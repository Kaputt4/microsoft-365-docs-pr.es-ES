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
ms.openlocfilehash: ab00bb47555b317bbaf7bf5b96202196ac6f658d
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497881"
---
# <a name="onboard-with-microsoft-defender-for-iot"></a>Incorporación con Microsoft Defender para IoT

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión P2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft Defender para punto de conexión ahora se integra perfectamente con Microsoft Defender para IoT. Esta integración amplía las funcionalidades de detección de dispositivos con las funcionalidades de supervisión sin agente proporcionadas por Defender para IoT. La integración de Defender para IoT proporciona una mayor visibilidad para ayudar a localizar, identificar y proteger los dispositivos IoT empresariales en la red, como los dispositivos, impresoras y cámaras de protocolo de voz a través de Internet (VoIP).

Esto permite a las organizaciones aprovechar una única solución integrada que protege toda su infraestructura de IoT y tecnología operativa (OT). Para obtener más información, consulte [Protección de red de IoT empresarial](/azure/defender-for-iot/organizations/overview-eiot).

La integración de Defender para IoT le ofrece una única vista unificada del inventario completo de OT/IoT junto con el resto de los dispositivos de TI (estaciones de trabajo, servidores y dispositivos móviles). Los clientes que se han incorporado a Defender para IoT también obtendrán información sobre alertas, vulnerabilidades y recomendaciones de seguridad para sus dispositivos IoT.

## <a name="prerequisites"></a>Requisitos previos

Para modificar la configuración de la integración de Defender para punto de conexión, el usuario debe tener los siguientes roles:

- Administrador global de inquilinos en Azure Active Directory
- Administrador de seguridad de la suscripción de Azure que se usará para la integración de Microsoft Defender para IoT

## <a name="onboard-a-defender-for-iot-plan"></a>Incorporación de un plan de Defender para IoT

1. En el panel de navegación del [https://security.microsoft.com](https://security.microsoft.com/) portal, seleccione **Configuración Detección** \> **de dispositivos** \> **Enterprise IoT**.

2. Seleccione las siguientes opciones para el plan:

   - Seleccione la suscripción de Azure en la lista de suscripciones disponibles en el inquilino de Azure Active Directory donde desea agregar un plan.

   - Seleccione un plan de precios, un compromiso mensual o anual, o una evaluación. Microsoft Defender para IoT proporciona una evaluación gratuita de 30 días para los primeros 1000 dispositivos confirmados con fines de evaluación.

      Para obtener más información, consulte la [página de precios de Microsoft Defender para IoT](https://azure.microsoft.com/pricing/details/iot-defender/).

   - Seleccione el número de dispositivos confirmados que desea supervisar. Si seleccionó una prueba, esta sección no aparece porque tiene un valor predeterminado de 1000 dispositivos.

3. Acepte los **términos y condiciones** y seleccione **Guardar**.

> [!NOTE]
> La configuración de un sensor de red de IoT empresarial está actualmente en versión preliminar pública. Para obtener más información, consulte [Inventario de dispositivos compartidos](#shared-device-inventory).

## <a name="managing-your-iot-devices"></a>Administración de dispositivos IoT

Para ver y administrar los dispositivos IoT en Microsoft 365 Defender [portal](https://security.microsoft.com/), vaya al **inventario** de dispositivos en el menú de navegación **Puntos de conexión** y seleccione la pestaña **Dispositivos IoT**.

Para obtener información sobre cómo ver los dispositivos en Defender para IoT, consulte [Administración de dispositivos IoT con el inventario de dispositivos para organizaciones](/azure/defender-for-iot/organizations/how-to-manage-device-inventory-for-organizations).

## <a name="view-devices-alerts-recommendations-and-vulnerabilities"></a>Visualización de dispositivos, alertas, recomendaciones y vulnerabilidades

Después de incorporarse a un plan de Defender para IoT, vea los datos detectados y las evaluaciones de seguridad en las siguientes ubicaciones:

- Visualización de datos de dispositivos en Defender para punto de conexión o Defender para IoT
- Vea [alertas](alerts-queue-endpoint-detection-response.md), [recomendaciones](../defender-vulnerability-management/tvm-security-recommendation.md) y [vulnerabilidades](../defender-vulnerability-management/tvm-weaknesses.md) en el [portal de Microsoft 365 Defender](https://security.microsoft.com).

### <a name="shared-device-inventory"></a>Inventario de dispositivos compartidos

Los clientes de Defender para punto de conexión también pueden configurar el sensor de red de IoT empresarial (actualmente en **versión preliminar pública**) para obtener más visibilidad sobre los segmentos de IoT adicionales de la red corporativa que no estaban cubiertos previamente por Defender para punto de conexión. Los clientes que hayan configurado un sensor de red de IoT empresarial podrán ver todos los dispositivos detectados en el **inventario de** dispositivos en Defender para punto de conexión o Defender para IoT.

Para agregar un sensor de red, en el panel de navegación del [https://security.microsoft.com](https://security.microsoft.com/) portal:

1. Seleccione **Configuración Detección** \> \> **de dispositivos** **Enterprise IoT**
2. En **Configurar sensores de red** , elija el vínculo **De Microsoft Defender para IoT** .

Esto le lleva al proceso de configuración del sensor en el Azure Portal. Para obtener más información, consulte [Introducción a Enterprise IoT](/azure/defender-for-iot/organizations/tutorial-getting-started-eiot-sensor).

> [!IMPORTANT]
> La configuración de un sensor de enterprise IoT Network está actualmente en versión preliminar. Consulte los [Términos de uso complementarios para las versiones preliminares de Microsoft Azure para obtener términos](https://azure.microsoft.com/support/legal/preview-supplemental-terms/) legales adicionales que se aplican a las características de Azure que están en versión beta, versión preliminar o que aún no se han publicado en disponibilidad general.

## <a name="cancel-your-defender-for-iot-plan"></a>Cancelación del plan de Defender para IoT

Cancele el plan de Defender para IoT desde la página configuración de Defender para punto de conexión del [https://security.microsoft.com](https://security.microsoft.com/) portal. Una vez que cancele el plan, la integración se detiene y ya no obtendrá el valor de evaluación de seguridad en Defender para punto de conexión ni detectará nuevos dispositivos en Defender para IoT.

Para obtener más información sobre la cancelación del plan y las consideraciones sobre los datos, consulte [Cancelar un plan de Defender para IoT](/azure/defender-for-iot/organizations/how-to-manage-subscriptions#cancel-a-defender-for-iot-plan-from-a-subscription) en la documentación de Defender para IoT.

## <a name="see-also"></a>Vea también

- [Información general de la detección de dispositivo](configure-device-discovery.md)
- [Preguntas más frecuentes sobre la detección de dispositivo](device-discovery-faq.md)
