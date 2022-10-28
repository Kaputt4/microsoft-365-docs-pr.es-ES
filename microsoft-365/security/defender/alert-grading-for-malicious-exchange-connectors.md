---
title: Clasificación de alertas para conectores de intercambio malintencionados
description: Alerte a los destinatarios de la clasificación de la actividad de conectores de intercambio malintencionados y protejan su red frente a ataques malintencionados.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 83f7bdc0ac44b84953f760f31b5615ce793311f0
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770489"
---
# <a name="alert-grading-for-malicious-exchange-connectors"></a>Clasificación de alertas para conectores de intercambio malintencionados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Los actores de amenazas usan conectores de intercambio en peligro para enviar correos electrónicos de spam y phishing de forma masiva a destinatarios desprevenidos enmascarando correos electrónicos legítimos. Dado que el conector está en peligro, los destinatarios suelen confiar en los correos electrónicos. Estos tipos de correos electrónicos de suplantación de identidad son vectores comunes para las campañas de suplantación de identidad (phishing) y el escenario de riesgo de correo electrónico empresarial (BEC). Por lo tanto, estos correos electrónicos deben supervisarse en gran medida debido a la probabilidad de que los compromisos de los destinatarios sean elevados.

El cuaderno de estrategias ayuda a investigar las instancias, donde los actores malintencionados configuran o implementan conectores malintencionados. En consecuencia, toman las medidas necesarias para corregir el ataque y mitigar los riesgos de seguridad derivados de él. El cuaderno de estrategias está disponible para equipos de seguridad como el Centro de operaciones de seguridad (SOC) y los administradores de TI, que revisan, administran y califican las alertas. El cuaderno de estrategias le ayudará a calificar las alertas como Verdadero positivo (TP) o Falso positivo (FP). Si hay TP, el cuaderno de estrategias realizará las acciones recomendadas necesarias para corregir el ataque.

A continuación se muestran los resultados del uso de un cuaderno de estrategias:

- Determinación de la alerta como malintencionada (TP) o benigna (FP).
- Si es malintencionado, corrija o quite el conector malintencionado del entorno.

## <a name="exchange-connectors"></a>Conectores de Exchange

Los conectores de Exchange son una colección de instrucciones que personalizan la forma en que el correo electrónico fluye hacia y desde su organización de Microsoft 365 o Office 365. Por lo general, la mayoría de las organizaciones de Microsoft 365 y Office 365 no necesitan conectores para el flujo de correo normal.

Los conectores se usan para enrutar el tráfico de correo entre sistemas de correo electrónico remotos y Office 365 (O365) o O365 y sistemas de correo electrónico locales.

## <a name="malicious-exchange-connectors"></a>Conectores de Exchange malintencionados

Los atacantes pueden poner en peligro un conector de exchange existente o poner en peligro a un administrador y configurar un nuevo conector mediante el envío de correos electrónicos de correo no deseado o correo no deseado o masivo.

Los indicadores típicos de un conector malintencionado se pueden encontrar al examinar el tráfico de correo electrónico y sus encabezados. Por ejemplo, cuando se observa tráfico de correo electrónico desde un nodo del conector con una falta de coincidencia en las direcciones de remitente P1 (remitente del encabezado) y P2 (remitente de sobre) junto con ninguna información sobre accountObjectId del remitente.

Esta alerta intenta identificar dichas instancias de flujo de correo, donde la actividad de envío de correo parece sospechosa agregar a esa información relevante en el remitente no está disponible.

## <a name="playbook-workflow"></a>Flujo de trabajo del cuaderno de estrategias

Debe seguir la secuencia para identificar conectores de intercambio malintencionados:

- Identifique qué cuentas envían correos electrónicos:
  - ¿Las cuentas parecen estar en peligro?
- Identifique la retransmisión del conector en los correos electrónicos para comprobar lo siguiente:
  - ¿Si se supone que el conector envía correos electrónicos de gran volumen?
  - ¿Si el conector se modificó o creó recientemente?
- ¿Los correos electrónicos van a direcciones de correo electrónico internas?
  - ¿Los correos electrónicos van a direcciones externas (rociar y orar correo no deseado)?
  - ¿Los correos electrónicos van a direcciones externas que pertenecen a clientes o proveedores (ataque de tipo cadena de suministro)?
- Compruebe si los dominios de encabezado FROM y Remitente de sobre son iguales o diferentes.

## <a name="investigating-malicious-connectors"></a>Investigación de conectores malintencionados

En esta sección se describen los pasos para investigar una alerta y corregir el riesgo de seguridad debido a este incidente.

- Determine si el conector muestra un comportamiento incorrecto (malintencionado).
  - Busque eventos que indiquen tráfico de correo inusual e identifique si se agregó algún nuevo conector de Exchange recientemente.
    - Para el tráfico de correo observado, determine si las cuentas de correo electrónico están en peligro mediante la inspección de si las cuentas son responsables del tráfico de correo inusual.
  - Busque contenido de correo que contenga artefactos malintencionados (vínculos o datos adjuntos incorrectos).
  - Busque dominios que no formen parte de su entorno.
- Determine que las cuentas de correo electrónico no están en peligro. Identifique el conector que se agregó o modificó recientemente en el entorno.
- Buscar:
  - Valores de campo en el remitente P1 (remitente del encabezado de correo electrónico) y el remitente P2 (remitente de sobre), y compruebe si hay una discrepancia.
  - Valores vacíos en el campo SenderObjectId.
- Use los datos de telemetría para tener en cuenta lo siguiente:
  - NetworkMessageId (id. de mensaje) de los correos electrónicos que se enviaron desde el conector malintencionado.
  - Fecha de creación del conector, fecha de última modificación y última modificación por fecha.
  - Dirección IP del conector desde donde se observa el tráfico de correo electrónico.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

Puede usar consultas [de búsqueda avanzadas](/microsoft-365/security/defender/advanced-hunting-overview?) para recopilar información relacionada con una alerta y determinar si la actividad es sospechosa.

Asegúrese de que tiene acceso a las tablas siguientes:

|Nombre de la tabla|Descripción|
|---|---|
|EmailEvents| Contiene información relacionada con el flujo de correo electrónico.|
|CloudAppEvents|Contiene el registro de auditoría de las actividades del usuario.|
|IdentityLogonEvents|Contiene información de inicio de sesión para todos los usuarios.|

## <a name="references"></a>Referencias

Ejemplos de AHQs como referencia:

- Ejecute este KQL para comprobar la creación del nuevo conector.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  CloudAppEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty(AccountObjectId)
  | where ActionType == "New-InboundConnector"
  | mvexpand property = RawEventData.Parameters
  | extend ConnectorName = iff(property.Name == "Name", property.Value, ""), 
  IsEnabled = iff((property.Name == "Enabled" and property.Value == "True"), 
  true, false)
  | where isnotempty( ConnectorName) or IsEnabled
  | project-reorder ConnectorName, IsEnabled
  ```

- Ejecute este KQL para comprobar el volumen de eventos desde el conector con una ventana de tiempo de antes y después de las alertas.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  let connectorOperations = pack_array("Set-OutboundConnector", 
  "New-OutboundConnector", "Set-InboundConnector", "New-InboundConnector");
  let mailThreshold = 100; //define threshold for inspection and filtering
  let myConnector= //use this code block to specify relevant connector(s)
  CloudAppEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where ActionType has_any (connectorOperations)
  | mv-expand property = RawEventData.Parameters
  | where property.Name == "Name"
  | summarize by ConnectorName=tostring(property.Value)
  ;
  EmailEvents
  | where isnotempty( toscalar (myConnector))
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty( SenderObjectId) and isnotempty( Connectors)
  | where Connectors in (toscalar (myConnector))
  | summarize MailCount = dcount(NetworkMessageId) by Connectors, 
  SenderObjectId, bin(Timestamp, 1h)
  | where MailCount >= mailThreshold
   ```

- Ejecute este KQL para comprobar si los correos electrónicos se envían a dominios externos.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  EmailEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty( SenderObjectId)
  | extend RecipientDomain= split(RecipientEmailAddress, "@")[1]
  | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain 
  != RecipientDomain)
  | where EmailDirection !in ("Intra-org" , "Inbound") //comment this line to 
  look across all mailflow directions
  ```

  - Si se envía a dominios externos, quién más en el entorno envía correos electrónicos similares (podría indicar que el usuario está en peligro si el destinatario es un dominio desconocido).

     ```KQL
     //modify timeWindow to modify the lookback.
     let timeWindow = now(-7d); let timeNow = now();
     let countThreshold= 100; //modify count threshold accordingly 
     EmailEvents
     | where Timestamp between (timeWindow .. timeNow)
     | where isnotempty( SenderObjectId)
     | extend RecipientDomain= split(RecipientEmailAddress, "@")[1]
     | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain 
     != RecipientDomain)
     | where EmailDirection !in ("Intra-org" , "Inbound")
     | summarize MailCount= dcount(NetworkMessageId) by SenderObjectId, 
     SenderFromAddress, SenderMailFromAddress , bin(Timestamp, 1h)
     | where MailCount > countThreshold
     ```

    - Comprobar si el contenido del correo es incorrecto
    - Examine las direcciones URL del correo electrónico o correo electrónico que tienen datos adjuntos.

## <a name="ahq-considerations"></a>Consideraciones de AHQ

A continuación se muestran las consideraciones de AHQ para proteger a los destinatarios frente a ataques malintencionados.

- Compruebe si hay inicios de sesión de administrador para aquellos que administran con frecuencia conectores desde ubicaciones inusuales (genere estadísticas y excluya ubicaciones desde donde se observen los inicios de sesión más correctos).

- Busque errores de inicio de sesión desde ubicaciones inusuales.

  ```
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  let logonFail= materialize (
  IdentityLogonEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty(AccountObjectId)
  | where Application != "Active Directory"
  | where ActionType == "LogonFailed"
  | where ISP != "Microsoft Azure"
  | summarize failedLogonCount=count(), LatestTime = max(Timestamp), 
  EarliestTime = min(Timestamp) by AccountObjectId, Application, ISP, 
  CountryCode, bin(Timestamp, 60s)
  | where failedLogonCount > 100);
  // let hasLogonFails = isnotempty(toscalar (logonFail));
  let logonFailUsers = materialize ( logonFail | distinct AccountObjectId | 
  take 100);
  let hasLogonFails = isnotempty(toscalar (logonFailUsers));
  let logonSuccess=
  IdentityLogonEvents
  | where hasLogonFails
  | where Timestamp between (timeWindow .. timeNow)
  | where AccountObjectId in (logonFailUsers)
  | where Application != "Active Directory"
  | where ISP != "Microsoft Azure"
  | where ActionType == "LogonSuccess"
  | project SuccessTime= Timestamp, ReportId, AccountUpn, AccountObjectId, 
  ISP, CountryCode, Application;
  logonFail
  | join kind = innerunique logonSuccess on AccountObjectId, ISP, Application
  | where SuccessTime between (LatestTime .. (LatestTime + 10s))
  | summarize arg_min(SuccessTime, ReportId), EarliestFailedTime=min
  (EarliestTime), LatestFailedTime=max(LatestTime), failedLogonCount=
  take_any(failedLogonCount), SuccessLogonCount=count(), ISPSet=
  make_set(ISP), CountrySet=make_set(CountryCode), AppSet=make_set
  (Application) by AccountObjectId, AccountUpn
  | project-rename Timestamp=SuccessTime
  ```

## <a name="recommended-actions"></a>Acciones recomendadas

Una vez que se determina que las actividades de alerta observadas forman parte de TP, clasifique esas alertas y realice las acciones siguientes:

- Deshabilite o quite el conector que se encontró como malintencionado.
- Si la cuenta de administrador está en peligro, restablezca las credenciales de la cuenta del administrador. Además, deshabilite o revoque tokens para la cuenta de administrador en peligro y habilite la autenticación multifactor para todas las cuentas de administrador.
- Busque actividades sospechosas realizadas por el administrador.
- Compruebe si hay otras actividades sospechosas en otros conectores del entorno.
