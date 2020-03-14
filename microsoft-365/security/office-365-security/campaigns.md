---
title: Vistas de las campañas en ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre las Vistas de la campaña en la Protección contra amenazas avanzada de Office 365.
ms.openlocfilehash: 40eab14dff8d0c51a35bfbc7a04365a5a025e207
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637333"
---
# <a name="campaign-views-in-office-365-atp"></a>Vistas de la campaña en ATP de Office 365

Vistas de la campaña es una característica de la Protección contra amenazas avanzada (ATP) del Centro de seguridad y cumplimiento de Office 365 que identifica y categoriza los ataques de suplantación de identidad en el servicio. Vistas de la campaña puede ayudarle a:

- Investigar y responder eficazmente a los ataques de suplantación de identidad.

- Entender mejor el alcance del ataque.

- Proporcionar información a los responsables de la toma de decisiones.

La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.

## <a name="what-is-a-campaign"></a>¿Qué es una campaña?

Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones. Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector importante y lucrativo. A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar un éxito continuo.

Microsoft aprovecha la gran cantidad de datos antiphishing, contra correo electrónico no deseado y antimalware en todo el servicio de Office 365 para ayudarle a identificar las campañas. Analizamos y clasificamos la información de ataques de acuerdo con varios factores. Por ejemplo:

- **Origen del ataque**: direcciones IP de origen y dominios de correo electrónico del remitente.

- **Propiedades del mensaje del ataque**: contenido, estilo y tono de los mensajes del ataque.

- **Los destinatarios del ataque**: dominios de destinatarios, funciones de trabajo de los destinatarios (administradores, ejecutivos, etc.), tipos de empresa (grandes, pequeñas, públicas, privadas, etc.) y sectores.

- **Carga de ataques**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes de ataque.

Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos. Es posible que se inicie una campaña en su organización específica o que la organización forme parte de una campaña más grande en varias compañías.

## <a name="campaign-views-the-office-365-security--compliance-center"></a>Vistas de la campaña en el Centro de seguridad y cumplimiento de Office 365

Las vistas de campaña están disponibles en el [centro de seguridad & cumplimiento](https://protection.office.com) en las **campañas**de **Administración** \> de amenazas.

![Información general de las campañas en el Centro de seguridad y cumplimiento](../../media/campaigns-overview.png)

También puede obtener acceso a la vista campañas desde:

- **Threat management** \> **Explorer** Explorador \> de administración de amenazas **Ver** \> **campañas**

- **Threat management** \> **Explorer** Explorador \> de administración de amenazas **Ver** \> **todas las** \> **campañas** de correo electrónico

> [!TIP]
> Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas.

La página de información general muestra la siguiente información sobre la campaña:

- **Nombre**

- **Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña. Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.

- **Tipo**: Actualmente, este valor es siempre **phish**.

- **Subtipo**: si está disponible, la marca a la que la campaña está dirigiendo los ataques de suplantación de identidad. Cuando la tecnología ATP controla la detección, el prefijo **ATP-** se agrega al valor SubType.

- **Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.

- **Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no se entregaron a correo no deseado).

- **Haga clic en**: el número de usuarios que hizo clic en la dirección URL en el mensaje de suplantación de identidad.

- **Tasa de clic**: porcentaje calculado con "se ha**pulsado en** / la**bandeja de entrada**". Este valor es un indicador de la efectividad de la campaña y de si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y evitar hacer clic en la dirección URL de carga.

- **Visitado**: el número de usuarios que se han realizado realmente a través del sitio web de carga. Si hay valores en los que se ha **pulsado** , pero los vínculos seguros han bloqueado el acceso al sitio web, este valor será cero.

Al hacer clic en el nombre de una campaña, se muestran los detalles de la campaña en un control flotante.

## <a name="campaign-details"></a>Detalles de la campaña

En la vista de detalles de la campaña se muestra una gran cantidad de información sobre la campaña:

- Información de la campaña:

  - **ID**: el identificador único de la campaña.

  - **Iniciada** y **Finalizada**: el filtro del intervalo de fechas que se ha seleccionado.

  - **Impacto**: los siguientes datos para el filtro de intervalo de fechas seleccionado:
  
    - Número total de destinatarios.

    - El número de mensajes que se han "bandeja de entrada" (es decir, que se entregan a la bandeja de entrada, no de correo no deseado).

    - El número de usuarios que hizo clic en la carga de la URL en el mensaje de suplantación de identidad.

    - Howe muchos usuarios visitaron la dirección URL.

  - Una escala de tiempo de la actividad de la campaña: cuándo comenzó y finalizó la campaña y el volumen de mensajes a lo largo del tiempo.

### <a name="campaign-flow"></a>Flujo de la campaña

Los detalles importantes sobre la campaña se presentan en un diagrama de flujo horizontal (conocido como diagrama de _Sankey_) en la sección **Flujo**. Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).

El diagrama contiene la información siguiente:

- **IP de remitentes**

- **Dominios de remitente**

- **Filtrar veredictos**: los valores aquí están relacionados con los veredictos de filtrado de suplantación de identidad (phishing) y correo no deseado disponibles como se describe en [encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). En la tabla siguiente se describen los valores disponibles:

  |Valor|Veredicto de filtro de correo no deseado|Descripción|
  |:-----|:-----|:-----|
  | **Permitido**|`SFV:SKN` <br/><br/> `SFV:SKI`|El mensaje se marcó como no es correo no deseado o omitido antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo, también denominada regla de transporte).<br/><br/>El mensaje omitió el filtrado de correo no deseado por otros motivos (por ejemplo, el remitente y el destinatario parecen estar en la misma organización).|
  |**Blocked**|`SFV:SKS`|El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo).|
  |**Detectados**|`SFV:SPM`|El mensaje se marcó como correo no deseado por el filtrado de correo no deseado.|
  |**No detectado**|`SFV:NSPM`|El mensaje se marcó como no correo no deseado por el filtrado de correo no deseado.|
  |**Exento**|`SFV:SKQ`|El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.|
  |**Permitir inquilino**<sup>\*</sup>|`SFV:SKA`|El mensaje omitió el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).|
  |**Bloque tenant**<sup>\*\*</sup>|`SFV:SKA`|El mensaje fue bloqueado por el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).|
  |**Permitir al usuario**<sup>\*</sup>|`SFV:SFE`|El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros de un usuario en Outlook.|
  |**Bloque de usuario**<sup>\*\*</sup>|`SFV:BLK`|El mensaje fue bloqueado por el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados de un usuario en Outlook.|
  |**ZAP**|n/a|La [depuración automática de cero horas (ZAP)](zero-hour-auto-purge.md) llevó a cabo una acción en el mensaje entregado de acuerdo con la configuración de la Directiva contra correo no deseado (se movió a la carpeta de correo no deseado o en cuarentena).|

  <sup>\*</sup>Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.

  <sup>\*\*</sup>Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregados.

- **Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea en la bandeja de entrada o en la carpeta de correo no deseado), incluso aunque los usuarios no hayan hecho clic en la URL de carga del mensaje. También puede quitar los mensajes en cuarentena de la cuarentena. Para obtener más información, vea [cuarentena de mensajes de correo electrónico en Office 365](quarantine-email-messages.md).

  - **Carpeta eliminada**

  - **Sombra**

  - **Externos**: el destinatario se encuentra en su organización de correo electrónico local.

  - **Failed**

  - **Reenviado**

  - **Bandeja de entrada**

  - **Carpeta de correo no deseado**

  - **Cuarentena**

  - **Desconocido**

> [!NOTE]
> En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **otros**.

#### <a name="url-clicks"></a>Clics de URL

Cuando se entrega un mensaje de suplantación de identidad a un destinatario (en la bandeja de entrada o en la carpeta de correo electrónico no deseado), siempre hay una posibilidad de que el usuario haga clic en la dirección URL de la carga. No hacer clic en la dirección URL de un mensaje entregado es una pequeña medida de éxito, pero debe determinar por qué el mensaje de suplantación de identidad (phishing) se entregó a su buzón en primer lugar.

Si un usuario hace clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área de **clics de la dirección URL** del diagrama en la vista detalles de la campaña.

- **Permitido**

- **BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero el acceso al sitio Web malintencionado fue bloqueado por las directivas de [vínculos seguros de ATP](atp-safe-links.md) en su organización.

- **BlockPageOverride**: el destinatario hizo clic en la dirección URL de carga en el mensaje, los vínculos seguros de ATP intentaron detenerlos, pero se permitió invalidar el bloque. Debe investigar sus directivas de [vínculos seguros](set-up-atp-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio Web malintencionado.

- **PendingDetonationPage**: los datos adjuntos seguros de ATP están en proceso de abrir la URL de carga en un entorno de equipo virtual y ver qué sucede.

- **PendingDetonationPageOverride**: el destinatario tuvo permiso para invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar los resultados.

### <a name="tabs"></a>Pestañas

En la vista de detalles de la campaña hay varias pestañas que permiten investigar más a fondo la campaña.

- **Clics en dirección URL**: si los usuarios no han hecho clic en la dirección URL de carga en el mensaje de suplantación de identidad, esta sección estará en blanco. Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:

  - **Usuario**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **Hora del clic**

  - **Acción del clic**

- **IP de remitentes**

  - **IP del remitente**<sup>\*</sup>

  - **Recuento total**

  - **Recuento de entregados en bandeja de entrada**

  - **Recuento de bloqueados**

  - **SPF superado**: el [marco de directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)autenticó el remitente. Un remitente que no pasa la validación SPF indica que el remitente no está autenticado o que está suplantando a un remitente legítimo.

- **Remitentes**

  - **Sender**: esta es la dirección del remitente real en el comando SMTP mail from, que no tiene que ser necesariamente la dirección de correo electrónico que los usuarios ven en sus clientes de correo electrónico.

  - **Recuento total**

  - **En la bandeja de entrada**

  - **Sin bandeja de entrada**

  - **DKIM pasado**: el remitente ha sido autenticado por el [correo identificado por claves de dominio (DKIM)](support-for-validation-of-dkim-signed-messages.md). Un remitente que no pasa la validación de DKIM indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.

  - **DMARC pasada**: el remitente ha sido autenticado por la [autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC)](use-dmarc-to-validate-email.md). Un remitente que no pasa la validación de DMARC indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.

- **Cargas**

  - **URL**<sup>\*</sup>

  - **Recuento total**

<sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña. Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.

### <a name="buttons"></a>Botones

Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.

- **Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.

- **Explorar mensajes**de la bandeja de entrada: abre una nueva ficha de búsqueda del explorador de amenazas usando el identificador de la **campaña** y la **Ubicación de entrega: bandeja de entrada** como filtro de búsqueda.
