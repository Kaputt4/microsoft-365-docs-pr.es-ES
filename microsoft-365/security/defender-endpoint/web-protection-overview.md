---
title: Protección web
description: Obtenga información sobre la protección web en Microsoft Defender para punto de conexión y cómo puede proteger su organización
keywords: protección web, protección contra amenazas web, navegación web, seguridad, phishing, malware, vulnerabilidad de seguridad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web, sitios web malintencionados
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 07/25/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 886ed68514235669d72fe260cacc9b150d9a04d3
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497788"
---
# <a name="web-protection"></a>Protección web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

## <a name="about-web-protection"></a>Acerca de la protección web

La protección web en Microsoft Defender para punto de conexión es una funcionalidad formada por [protección contra amenazas web](web-threat-protection.md), [filtrado de contenido web](web-content-filtering.md) e [indicadores personalizados](manage-indicators.md). La protección web le permite proteger los dispositivos frente a amenazas web y le ayuda a regular el contenido no deseado. Para encontrar informes de protección web en el portal de Microsoft 365 Defender, vaya a **Informes > protección web**.

:::image type="content" source="images/web-protection.png" alt-text="Tarjetas de protección web" lightbox="images/web-protection.png":::

### <a name="web-threat-protection"></a>Protección contra amenazas web

Las tarjetas que componen la protección contra amenazas web son **detecciones de amenazas web a lo largo del tiempo** y **resumen de amenazas web**.

La protección contra amenazas web incluye:

- Visibilidad completa de las amenazas web que afectan a su organización.
- Capacidades de investigación sobre la actividad de amenazas relacionada con la web a través de alertas y perfiles completos de direcciones URL y los dispositivos que acceden a estas direcciones URL.
- Un conjunto completo de características de seguridad que realizan un seguimiento de las tendencias generales de acceso a sitios web malintencionados y no deseados.

> [!NOTE]
> En el caso de procesos distintos de Microsoft Edge e Internet Explorer, los escenarios de protección web aprovechan la protección de red para la inspección y el cumplimiento:
>
> - Ip es compatible con los tres protocolos (TCP, HTTP y HTTPS (TLS)).
> - Solo se admiten direcciones IP únicas (sin bloques CIDR ni intervalos IP) en indicadores personalizados.
> - Las direcciones URL cifradas (ruta de acceso completa) solo se pueden bloquear en exploradores de primera entidad (Internet Explorer, Edge).
> - Las direcciones URL cifradas (solo FQDN) se pueden bloquear en exploradores de terceros (es decir, distintas de Internet Explorer, Edge).
> - Los bloques de ruta de acceso de dirección URL completa se pueden aplicar a direcciones URL sin cifrar.
>
> Puede haber hasta 2 horas de latencia (normalmente menos) entre el momento en que se realiza la acción y la dirección URL y la dirección IP bloqueadas.

Para obtener más información, consulte [Protección contra amenazas web](web-threat-protection.md).

### <a name="custom-indicators"></a>Indicadores personalizados

Las detecciones de indicadores personalizados también se resumen en los informes de amenazas web de las **organizaciones en Detecciones de amenazas web a lo largo del tiempo** y **Resumen de amenazas web**.

El indicador personalizado incluye:

- Capacidad de crear indicadores de compromiso basados en direcciones IP y URL para proteger su organización frente a amenazas.
- Capacidades de investigación sobre las actividades relacionadas con los perfiles de DIRECCIÓN IP/URL personalizados y los dispositivos que acceden a estas direcciones URL.
- La capacidad de crear directivas Allow, Block y Warn para direcciones IP y direcciones URL.

Para obtener más información, consulte [Creación de indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md).

### <a name="web-content-filtering"></a>Filtrado de contenido web

El filtrado de contenido web incluye **actividad web por categoría**, **resumen de filtrado de contenido web** y **resumen de actividad web**.

El filtrado de contenido web incluye:

- Se impide que los usuarios accedan a sitios web en categorías bloqueadas, ya sea que naveguen de forma local o fuera.
- Puede implementar directivas variadas en varios conjuntos de usuarios mediante los grupos de dispositivos definidos en la [configuración de control de acceso basado en rol Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/rbac).
- Puede acceder a los informes web en la misma ubicación central, con visibilidad sobre los bloques reales y el uso web.

Para obtener más información, vea [Filtrado de contenido web](web-content-filtering.md).

## <a name="order-of-precedence"></a>Orden de precedencia

La protección web se compone de los siguientes componentes, enumerados en orden de prioridad. Cada uno de estos componentes se aplica mediante el cliente SmartScreen en Microsoft Edge y el cliente de Network Protection en todos los demás exploradores y procesos.

- Indicadores personalizados (ip/dirección URL, directivas de Microsoft Defender for Cloud Apps)
  - Permitir
  - Advertir
  - Bloquear

- Amenazas web (malware, phish)
  - SmartScreen Intel, incluido Exchange Online Protection (EOP)
  - Escalamientos

- Filtrado de contenido web (WCF)

> [!NOTE]
> Microsoft Defender for Cloud Apps genera actualmente indicadores solo para las direcciones URL bloqueadas.

El orden de precedencia se relaciona con el orden de las operaciones por el que se evalúa una dirección URL o una dirección IP. Por ejemplo, si tiene una directiva de filtrado de contenido web, puede crear exclusiones a través de indicadores IP/URL personalizados. Los indicadores personalizados de peligro (IoC) son más altos en el orden de precedencia que los bloques WCF.

De forma similar, durante un conflicto entre indicadores, permite siempre tener prioridad sobre los bloques (invalidar la lógica). Esto significa que un indicador de permitir ganará cualquier indicador de bloque que esté presente.

En la tabla siguiente se resumen algunas configuraciones comunes que presentarían conflictos dentro de la pila de protección web. También identifica las determinaciones resultantes en función de la precedencia enumerada anteriormente.

<br>

****

|Directiva de indicador personalizado|Directiva de amenazas web|Directiva de WCF|Directiva de Defender for Cloud Apps|Resultado|
|---|---|---|---|---|
|Permitir|Bloquear|Bloquear|Bloquear|Permitir (invalidación de protección web)|
|Permitir|Permitir|Bloquear|Bloquear|Allow (excepción wcf)|
|Advertir|Bloquear|Bloquear|Bloquear|Advertir (invalidar)|
|

Los indicadores personalizados no admiten las direcciones IP internas. Para una directiva de advertencia cuando el usuario final la omite, el sitio se desbloqueará durante 24 horas para ese usuario de forma predeterminada. El Administración puede modificar este período de tiempo y lo pasa el servicio en la nube SmartScreen. La capacidad de omitir una advertencia también se puede deshabilitar en Microsoft Edge mediante CSP para bloques de amenazas web (malware/phishing). Para obtener más información, consulte [Configuración de SmartScreen de Microsoft Edge](/DeployEdge/microsoft-edge-policies#smartscreen-settings-policies).

## <a name="protect-browsers"></a>Proteger exploradores

En todos los escenarios de protección web, SmartScreen y Network Protection se pueden usar conjuntamente para garantizar la protección en los procesos y los exploradores de terceros. SmartScreen se integra directamente en Microsoft Edge, mientras que Network Protection supervisa el tráfico en exploradores y procesos de terceros. En el diagrama siguiente se muestra este concepto. Este diagrama de los dos clientes que trabajan juntos para proporcionar varias coberturas de explorador o aplicación es preciso para todas las características de Protección web (Indicadores, Amenazas web, Filtrado de contenido).

:::image type="content" source="../../media/web-protection-protect-browsers.png" alt-text="El uso de smartScreen y Network Protection juntos" lightbox="../../media/web-protection-protect-browsers.png":::

## <a name="troubleshoot-endpoint-blocks"></a>Solución de problemas de bloques de puntos de conexión

Las respuestas de la nube de SmartScreen están estandarizadas. Herramientas como Fiddler se pueden usar para inspeccionar la respuesta del servicio en la nube, lo que ayudará a determinar el origen del bloque.

Cuando el servicio en la nube SmartScreen responde con una respuesta de permitir, bloquear o advertir, una categoría de respuesta y el contexto del servidor se retransmiten de nuevo al cliente. En Microsoft Edge, la categoría de respuesta es la que se usa para determinar la página de bloque adecuada que se va a mostrar (malintencionado, phishing, directiva organizativa).

En la tabla siguiente se muestran las respuestas y sus características correlacionadas.

<br>

****

|ResponseCategory|Característica responsable del bloque|
|---|---|
|CustomPolicy|Wcf|
|CustomBlockList|Indicadores personalizados|
|CasbPolicy|Defender for Cloud Apps|
|Malintencionado|Amenazas web|
|Suplantación de identidad (phishing)|Amenazas web|
|||

## <a name="advanced-hunting-for-web-protection"></a>Búsqueda avanzada para la protección web

Las consultas de Kusto en la búsqueda avanzada se pueden usar para resumir los bloques de protección web de su organización durante un máximo de 30 días. Estas consultas usan la información enumerada anteriormente para distinguir entre los distintos orígenes de bloques y resumirlos de una manera fácil de usar. Por ejemplo, en la consulta siguiente se enumeran todos los bloques WCF que se originaron en Microsoft Edge.

```kusto
DeviceEvents
| where ActionType == "SmartScreenUrlWarning"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, Experience=tostring(ParsedFields.Experience)
| where Experience == "CustomPolicy"
```

Del mismo modo, puede usar la consulta siguiente para enumerar todos los bloques WCF que se originen en Network Protection (por ejemplo, un bloque WCF en un explorador de terceros). Tenga en cuenta que actiontype se ha actualizado y 'Experiencia' se ha cambiado a 'ResponseCategory'.

```kusto
DeviceEvents
| where ActionType == "ExploitGuardNetworkProtectionBlocked"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, ResponseCategory=tostring(ParsedFields.ResponseCategory)
| where ResponseCategory == "CustomPolicy"
```

Para enumerar los bloques que se deben a otras características (como indicadores personalizados), consulte la tabla anterior que describe cada característica y su categoría de respuesta correspondiente. Estas consultas también se pueden modificar para buscar telemetría relacionada con máquinas específicas de la organización. Tenga en cuenta que el ActionType que se muestra en cada consulta anterior mostrará solo las conexiones bloqueadas por una característica de Protección web y no todo el tráfico de red.

## <a name="user-experience"></a>Experiencia del usuario

Si un usuario visita una página web que supone un riesgo de malware, suplantación de identidad (phishing) u otras amenazas web, Microsoft Edge desencadenará una página de bloque que lea "Este sitio se ha notificado como no seguro" junto con información relacionada con la amenaza.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-malicious-block.png" alt-text="Página bloqueada por Microsoft Edge" lightbox="../../media/web-protection-malicious-block.png":::

Si WCF o un indicador personalizado bloquean, se muestra una página de bloque en Microsoft Edge que indica al usuario que su organización bloquea este sitio.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-indicator-blockpage.png" alt-text="Página bloqueada por la organización" lightbox="../../media/web-protection-indicator-blockpage.png":::

En cualquier caso, no se muestran páginas en bloque en exploradores de terceros y el usuario ve una página "Error de conexión segura" junto con una notificación del sistema. En función de la directiva responsable del bloque, un usuario verá un mensaje diferente en la notificación del sistema. Por ejemplo, el filtrado de contenido web mostrará el mensaje "Este contenido está bloqueado".

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-np-block.png" alt-text="Página bloqueada por WCF" lightbox="../../media/web-protection-np-block.png":::

## <a name="report-false-positives"></a>Notificar falsos positivos

Para notificar un falso positivo para sitios que SmartScreen ha considerado peligrosos, use el vínculo que aparece en la página de bloques de Microsoft Edge (como se muestra anteriormente).

Para WCF, puede disputar la categoría de un dominio. Vaya a la pestaña **Dominios** de los informes wcf y, a continuación, haga clic en **Imprecisión del informe**. Se abrirá un control flotante. Establezca la prioridad del incidente y proporcione algunos detalles adicionales, como la categoría sugerida. Para obtener más información sobre cómo activar WCF y cómo disputar categorías, vea [Filtrado de contenido web](web-content-filtering.md).

Para obtener más información sobre cómo enviar falsos positivos o negativos, consulte [Dirección de falsos positivos o negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md).

## <a name="related-information"></a>Información relacionada

<br>

****

|Tema|Descripción|
|---|---|
|[Protección contra amenazas web](web-threat-protection.md) | Detenga el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidades de seguridad, sitios que no son de confianza o de baja reputación y sitios que ha bloqueado.|
|[Filtrado de contenido web](web-content-filtering.md) | Realizar un seguimiento y regular el acceso a los sitios web en función de sus categorías de contenido.|
|
