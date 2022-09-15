---
title: Alerta de actividad de dirección IP sospechosa relacionada con la difusión de contraseñas
description: Clasificación de alertas para la actividad sospechosa de direcciones IP relacionadas con la difusión de contraseñas para revisar las alertas y realizar las acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, dispositivos, usuarios, 365, microsoft, m365, contraseña, difusión, clasificación de alertas, clasificación de alertas, aplicaciones en la nube, IP sospechosa
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-dgali
author: dgali297
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- met150
ms.openlocfilehash: ac9e4b9618350d22461b1bd8452d8ca2dc6cf6a3
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711092"
---
# <a name="suspicious-password-spray-related-ip-activity"></a>Actividad de IP sospechosa relacionada con la difusión de contraseñas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas usan técnicas de adivinación de contraseñas para obtener acceso a las cuentas de usuario. En un ataque de difusión de contraseñas, el actor de amenazas podría recurrir a algunas de las contraseñas más usadas en muchas cuentas diferentes. Los atacantes ponen en peligro correctamente las cuentas mediante la difusión de contraseñas, ya que muchos usuarios siguen usando contraseñas predeterminadas y débiles.

Esta guía le ayuda a investigar las instancias en las que las direcciones IP se han etiquetado como de riesgo o asociadas a un ataque de difusión de contraseñas, o se han detectado actividades sospechosas no explicadas, como un usuario que inicia sesión desde una ubicación desconocida o un usuario recibe mensajes inesperados de autenticación multifactor (MFA). Esta guía está destinada a equipos de seguridad como el Centro de operaciones de seguridad (SOC) y los administradores de TI que revisan, administran y clasifican las alertas. Esta guía ayuda a clasificar rápidamente las alertas como [verdadero positivo (TP) o falso positivo (FP)](investigate-alerts.md) y, en el caso de TP, realizar las acciones recomendadas para corregir el ataque y mitigar los riesgos de seguridad.

Los resultados previstos del uso de esta guía son:

- Ha identificado las alertas asociadas a direcciones IP de difusión de contraseña como actividades malintencionadas (TP) o falsos positivos (FP).

- Ha realizado la acción necesaria si las direcciones IP han estado realizando ataques de difusión de contraseñas.

## <a name="investigation-steps"></a>Pasos de investigación

Esta sección contiene instrucciones paso a paso para responder a la alerta y realizar las acciones recomendadas para proteger su organización de ataques adicionales.

### <a name="1-review-the-alert"></a>1. Revisar la alerta

Este es un ejemplo de una alerta de difusión de contraseña en la cola de alertas:

:::image type="content" source="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png" alt-text="Captura de pantalla de la alerta de Microsoft Defender 365." lightbox="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png":::

Esto significa que hay actividad sospechosa de usuario que se origina en una dirección IP que podría estar asociada a un intento de difusión por fuerza bruta o contraseña según los orígenes de inteligencia sobre amenazas.

### <a name="2-investigate-the-ip-address"></a>2. Investigar la dirección IP
-   Examine las [actividades](microsoft-365-security-center-defender-cloud-apps.md) que se originaron en la dirección IP:

    - **¿Se trata principalmente de intentos fallidos de iniciar sesión?**

    - **¿El intervalo entre intentos de inicio de sesión parece sospechoso?** Los ataques de difusión de contraseñas automatizadas tienden a tener un intervalo de tiempo regular entre intentos.

    - **¿Hay intentos correctos de que un usuario o varios usuarios inicien sesión con mensajes de [MFA](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365) ?** La existencia de estos intentos podría indicar que la dirección IP no es malintencionada.

    - **¿Se usan protocolos heredados?** El uso de protocolos como POP3, IMAP y SMTP puede indicar un intento de realizar un ataque de difusión de contraseña. La búsqueda `Unknown(BAV2ROPC)` en el agente de usuario (tipo de dispositivo) en el [registro de actividad](/defender-cloud-apps/activity-filters#ip-address-insights) indica el uso de protocolos heredados. Puede consultar el ejemplo siguiente al examinar el registro de actividad. Esta actividad debe correlacionarse aún más con otras actividades.

        :::image type="content" source="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png" alt-text="Captura de pantalla de la interfaz de Microsoft Defender 365 que muestra el tipo de dispositivo." lightbox="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png":::

        _Figura 1. El campo Tipo de dispositivo muestra `Unknown(BAV2ROPC)` el agente de usuario en Microsoft 365 Defender._ 
    - **Compruebe el uso de servidores proxy anónimos o la red Tor.** Los actores de amenazas suelen usar estos servidores proxy alternativos para ocultar su información, lo que dificulta su seguimiento. Sin embargo, no todo el uso de dichos servidores proxy se correlaciona con actividades malintencionadas. Debe investigar otras actividades sospechosas que podrían proporcionar mejores indicadores de ataque.
    - ¿La dirección IP procede de una red privada virtual (VPN)? ¿La VPN es de confianza? **Compruebe si la dirección IP se originó en una VPN y revise la organización detrás de ella mediante herramientas** como [RiskIQ](https://community.riskiq.com/learn-more/enterprise). 
    - **Compruebe otras direcciones IP con la misma subred o ISP.** A veces, los ataques de difusión de contraseñas se originan en muchas direcciones IP diferentes dentro de la misma subred o ISP.
-   **¿La dirección IP es común para el inquilino?** Compruebe el registro de actividad para ver si el inquilino ha visto la dirección IP en los últimos 30 días.
-   **Busque otras actividades o alertas sospechosas que se originaron en la dirección IP del inquilino.** Algunos ejemplos de actividades que hay que buscar pueden ser la eliminación de correo electrónico, la creación de reglas de reenvío o las descargas de archivos después de un intento correcto de iniciar sesión.
-   **Compruebe la puntuación de riesgo de la dirección IP** mediante herramientas como RiskIQ.
    
### <a name="3-investigate-suspicious-user-activity-after-signing-in"></a>3. Investigar la actividad sospechosa del usuario después de iniciar sesión
Una vez reconocida una dirección IP sospechosa, puede revisar las cuentas que iniciaron sesión. Es posible que un grupo de cuentas se haya puesto en peligro y se haya usado correctamente para iniciar sesión desde la dirección IP u otras direcciones IP similares.

Filtre todos los intentos correctos de iniciar sesión desde la dirección IP alrededor y poco después de la hora de las alertas. A continuación, busque actividades malintencionadas o inusuales en dichas cuentas después de iniciar sesión. 
-   Actividades de la cuenta de usuario

    **Compruebe que la actividad de la cuenta anterior a la actividad de difusión de contraseñas no es sospechosa.** Por ejemplo, compruebe si hay actividad anómala basada en una ubicación común o ISP, si la cuenta usa un agente de usuario que no usó antes, si se crearon otras cuentas de invitado, si se crearon otras credenciales después de que la cuenta haya iniciado sesión desde una dirección IP malintencionada, entre otras.
-   Alertas
    
    **Compruebe si el usuario recibió otras alertas anteriores a la actividad de difusión de contraseñas.** Tener estas alertas indica que la cuenta de usuario podría estar en peligro. Algunos ejemplos son la alerta de viaje imposible, la actividad del país poco frecuente y la actividad sospechosa de eliminación de correo electrónico, entre otros.
-   Incidente

    **Compruebe si la alerta está asociada a otras alertas que indican un incidente.** Si es así, compruebe si el incidente contiene otras alertas positivas verdaderas.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

[La búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-overview) es una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar eventos en la red y localizar indicadores de amenazas.

Use esta consulta para buscar cuentas con intentos de iniciar sesión con las puntuaciones de riesgo más altas procedentes de la dirección IP malintencionada. Esta consulta también filtra todos los intentos correctos de iniciar sesión con las puntuaciones de riesgo correspondientes.
```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| where isnotempty(RiskLevelDuringSignIn)
| project Timestamp, IPAddress, AccountObjectId, RiskLevelDuringSignIn, Application, ResourceDisplayName, ErrorCode
| sort by Timestamp asc
| sort by AccountObjectId, RiskLevelDuringSignIn
| partition by AccountObjectId ( top 1 by RiskLevelDuringSignIn ) // remove line to view all successful logins risk scores
```
Use esta consulta para comprobar si la dirección IP sospechosa usó protocolos heredados en los intentos de iniciar sesión.
```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| summarize count() by UserAgent
```
Use esta consulta para revisar todas las alertas de los últimos siete días asociadas a la dirección IP sospechosa.
```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
let ip_alert_ids = materialize ( 
        AlertEvidence
            | where Timestamp between (start_date .. end_date)
            | where RemoteIP == ip_address
            | project AlertId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
```
Use esta consulta para revisar la actividad de la cuenta de las cuentas sospechosas en peligro.
```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
CloudAppEvents
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | summarize ActivityCount = count() by AccountObjectId, ActivityType
    | extend ActivityPack = pack(ActivityType, ActivityCount)
    | summarize AccountActivities = make_bag(ActivityPack) by AccountObjectId
```
Use esta consulta para revisar todas las alertas de las cuentas sospechosas en peligro.
```kusto
let start_date = now(-8h); // change time range
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
let ip_alert_ids = materialize ( AlertEvidence
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | project AlertId, AccountObjectId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
| join kind=innerunique ip_alert_ids on AlertId
| project Timestamp, AccountObjectId, AlertId, Title, Category, Severity, ServiceSource, DetectionSource, AttackTechniques
| sort by AccountObjectId, Timestamp
```
## <a name="recommended-actions"></a>Acciones recomendadas

1. [Bloquee la dirección IP del atacante.](/azure/active-directory/conditional-access/block-legacy-authentication)
2. Restablezca las credenciales de las cuentas de usuario. 
3. Revocar tokens de acceso de cuentas en peligro.
4. [Bloquear la autenticación heredada.](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy) 
5. [Requerir MFA para los usuarios](/microsoft-365/business-premium/m365bp-conditional-access) si es posible para [mejorar la seguridad](/azure/active-directory/authentication/tutorial-enable-azure-mfa) de la cuenta y hacer que la cuenta se vea comprometida por un ataque de difusión de contraseñas difícil para el atacante. 
6. Impedir que la cuenta de usuario en peligro inicie sesión si es necesario.
## <a name="see-also"></a>Vea también

- [Introducción a la clasificación de alertas](alert-grading-playbooks.md)
- [Investigar alertas](investigate-alerts.md)