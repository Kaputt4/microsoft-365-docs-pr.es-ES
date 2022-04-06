---
title: Habilitación de la integración de Corelight en Microsoft Defender para punto de conexión
description: Habilitación de la integración de Corelight para obtener visibilidad centrada en los dispositivos IoT/OT en áreas de la red en las que no se implementa MDE
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
ms.openlocfilehash: bf3095b9178b4ff2e71d4ee5f652d9316f233746
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664598"
---
# <a name="enable-corelight-data-integration"></a>Habilitar la integración de datos de Corelight

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft se ha asociado con [Corelight](https://corelight.com/integrations/iot-security), proveedor de la plataforma líder de detección y respuesta de red abierta (NDR) del sector, para ayudarle a detectar dispositivos IoT/OT en toda la organización. El uso de datos, enviados desde dispositivos de red corelight, Microsoft 365 Defender mejora la visibilidad de las actividades de red de los dispositivos no administrados, incluida la comunicación con otros dispositivos no administrados o redes externas.

Con este origen de datos habilitado, todos los eventos de los dispositivos de red corelight se envían a Microsoft 365 Defender. Puede ver estas actividades en la escala de tiempo de dispositivos no administrados, disponible en el inventario de dispositivos Microsoft Defender para punto de conexión. Para obtener más información, consulte [Detección de dispositivos](device-discovery.md).

## <a name="enabling-the-corelight-integration"></a>Habilitación de la integración de Corelight

Para habilitar la integración de Corelight, deberá realizar los pasos siguientes:

[Paso 1: Activar Corelight como origen de datos](#step-1-turn-on-corelight-as-a-data-source)<br>
[Paso 2: Proporcionar permiso para que Corelight envíe eventos a Microsoft 365 Defender](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[Paso 3: Configuración del dispositivo Corelight para enviar datos a Microsoft 365 Defender](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>Paso 1: Activar Corelight como origen de datos

1. En el panel de navegación del [https://security.microsoft.com](https://security.microsoft.com/) portal, seleccione **Configuración** \> **Orígenes de datos de detección** \> de **dispositivos**.

   :::image type="content" source="images/enable-corelight.png" alt-text="Página orígenes de datos del portal de Microsoft 365 Defender" lightbox="images/enable-corelight.png":::

2. Seleccione **Enviar datos de Corelight a M365D** y seleccione **Guardar**.

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>Paso 2: Proporcionar permiso para que Corelight envíe eventos a Microsoft 365 Defender

> [!NOTE]
> Debe ser un administrador global para conceder permiso a Corelight para acceder a los recursos de su organización.

1. Como administrador global de inquilinos, vaya a este [vínculo](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) para conceder permiso.
2. Vaya al [https://security.microsoft.com](https://security.microsoft.com/) portal, seleccione **Configuración** \> **Microsoft 365 Defender** y tome nota del **identificador de inquilino**. Necesitará esta información al configurar el dispositivo Corelight.

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>Paso 3: Configuración del dispositivo Corelight para enviar datos a Microsoft 365 Defender

> [!NOTE]
>  La integración será pública en el software Corelight Sensor v24 y versiones posteriores. 

Para obtener una vista previa en v23 o v22.1, debe ejecutar `corelight-client configuration update --enable.adfiot 1` para habilitar la sección de configuración en la GUI.

Además de esto, la validación de la GUI requiere que un agente esté configurado en la sección de configuración en todas las versiones v23.  El agente que proporcione es necesario, pero no se usará realmente. Escriba `127.0.0.1:1234` en el campo _agente kafka_ para garantizar una validación correcta antes de seguir los pasos siguientes para habilitar el envío de datos a Microsoft 365 Defender.

> [!NOTE]
> Necesitará conectividad a Internet para que el sensor llegue a los servicios en la nube de Defender y Corelight para que la solución funcione.

#### <a name="enabling-in-the-corelight-sensor-gui"></a>Habilitación en la GUI de Corelight Sensor

1. En la sección Configuración de la GUI del sensor corelight, seleccione **Exportación** **de sensor**\>.
2. En la lista, vaya a **EXPORTAR A KAFKA** y seleccione el modificador para activarlo.

   :::image type="content" source="images/exporttokafka.png" alt-text="Exportación de kafka" lightbox="images/exporttokafka.png":::

3. A continuación, active **EXPORTAR A AZURE DEFENDER FOR IOT** y escriba el identificador de inquilino, que se indica en el paso 1, en el campo IDENTIFICADOR DE INQUILINO.

   :::image type="content" source="images/exporttodiot.png" alt-text="Exportación de iot" lightbox="images/exporttodiot.png":::

4. Seleccione **Aplicar cambios**.

   :::image type="content" source="images/corelightapply.png" alt-text="Icono Aplicar cambios" lightbox="images/corelightapply.png":::

> [!NOTE]
> Las opciones de configuración de Kafka (excepto la exclusión de registros y los filtros) no deben cambiarse. Los cambios realizados se omitirán.

#### <a name="enabling-in-the-corelight-client"></a>Habilitación en corelight-client

Puede activar **EXPORT TO KAFKA** y **EXPORT TO AZURE DEFENDER FOR IOT** mediante el siguiente comando en corelight-client:

`corelight-client configuration update --bro.export.kafka.defender.enable true --bro.export.kafka.defender.tenant\_id <your tenant>`.

> [!IMPORTANT]
> Si ya usa la exportación de Kafka, póngase en contacto con el soporte técnico de Corelight para obtener una configuración alternativa.

Para configurar solo el envío del conjunto mínimo de registros:

1. En la GUI de Corelight Sensor, vaya a la sección Kafka.
2. Vaya a **Registros de Zeek para excluir**
3. Seleccionar **todo**
4. A continuación, seleccione **x** junto a los registros siguientes para asegurarse de que continúan fluyendo a Microsoft:  
    `dns  conn  files  http  ssl  ssh  x509  snmp  smtp  ftp  sip  dhcp  notice`
5. Seleccione **Aplicar cambios.**

La lista de registros que fluyen a Microsoft puede expandirse con el tiempo.

## <a name="see-also"></a>Vea también

- [Preguntas más frecuentes sobre la detección de dispositivo](device-discovery-faq.md)
