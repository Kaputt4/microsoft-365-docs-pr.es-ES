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
ms.openlocfilehash: 629d475c160d5836d155ca0374630ad64b0928b4
ms.sourcegitcommit: 3226bdf213b290ec5262670873c3a75f17b66ddd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65372029"
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
> La integración está disponible en el software Corelight Sensor v25 y versiones posteriores.
> 
> Necesitará conectividad a Internet para que el sensor llegue a los servicios en la nube de Defender y Corelight para que la solución funcione.

#### <a name="enable-the-integration-in-the-corelight-web-interface"></a>Habilitación de la integración en la interfaz web de Corelight

1. En la interfaz web de Corelight, vaya a **Exportación de sensor**\>.

   :::image type="content" source="images/exporttodefender.png" alt-text="Exportación de kafka" lightbox="images/exporttodefender.png":::

2. Habilite **Exportar a Microsoft Defender**.
3. Escriba el identificador de inquilino de Microsoft 356 Defender.
4. Opcionalmente, puede:
    - establezca los **registros de Zeek en Excluir**. El conjunto mínimo de registros que debe incluir son: dns, conn, files, http, ssl, ssh, x509, snmp, smtp, ftp, sip, dhcp y notice.
    - elija crear un **filtro de registro de Microsoft Defender**.
5. Seleccione **Aplicar cambios**.

#### <a name="enable-the-integration-in-the-corelight-client"></a>Habilitación de la integración en corelight-client

1. Habilite **Exportar a Microsoft Defender** mediante el siguiente comando en corelight-client:

    ``` command
    corelight-client configuration update \
    --bro.export.defender.enable True
    ```

2. Establecimiento del identificador de inquilino

3. Opcionalmente, puede usar el siguiente comando para excluir determinados registros o para crear un filtro de registro de Microsoft Defender. El conjunto mínimo de registros que debe incluir son: dns, conn, files, http, ssl, ssh, x509, snmp, smtp, ftp, sip, dhcp y notice.

   ``` command
     corelight-client configuration update \
    --bro.export.defender.exclude=<logs_to_exclude> \
    --bro.export.defender.filter=<logs_to_filter>
   ```

## <a name="see-also"></a>Vea también

- [Preguntas más frecuentes sobre la detección de dispositivo](device-discovery-faq.md)
