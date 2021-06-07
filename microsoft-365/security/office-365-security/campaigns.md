---
title: Vistas de campaña en Microsoft Defender para Office 365 plan
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las vistas de campaña en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04e3d76271e95d36d73dd473076029cb60c06900
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779470"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Vistas de campaña en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Vistas de campaña es una característica de Microsoft Defender para Office 365 Plan 2 (por ejemplo, Microsoft 365 E5 u organizaciones con un complemento defender para Office 365 Plan 2). Las vistas de campaña en el Microsoft 365 de seguridad identifican y clasifican los ataques de suplantación de identidad en el servicio. Vistas de la campaña puede ayudarle a:

- Investigar y responder eficazmente a los ataques de suplantación de identidad.
- Entender mejor el alcance del ataque.
- Proporcionar información a los responsables de la toma de decisiones.

La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.

## <a name="what-is-a-campaign"></a>¿Qué es una campaña?

Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones. Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector grande y lucrativo. A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo por garantizar el éxito continuo.

Microsoft aprovecha las grandes cantidades de datos contra suplantación de identidad (phishing), antispam y antimalware en todo el servicio para ayudar a identificar las campañas. Analizamos y clasificamos la información de ataque según varios factores. Por ejemplo:

- **Origen de ataque:** las direcciones IP de origen y los dominios de correo electrónico del remitente.
- **Propiedades del** mensaje: el contenido, el estilo y el tono de los mensajes.
- **Destinatarios de mensajes:** cómo están relacionados los destinatarios. Por ejemplo, dominios de destinatarios, funciones de trabajo de destinatarios (administradores, ejecutivos, etc.), tipos de empresas (grandes, pequeñas, públicas, privadas, etc.) e industrias.
- **Carga de ataque:** vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.

Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos. Una campaña puede iniciarse en su organización específica o su organización puede formar parte de una campaña más grande en varias empresas.

## <a name="campaign-views-in-the-security-center"></a>Vistas de campaña en el centro de seguridad

Las vistas de campaña están disponibles en [el centro Microsoft 365 seguridad](https://security.microsoft.com) en Email & **collaboration** \> **Campaigns**, o directamente en <https://security.microsoft.com/campaigns> .

![Introducción a las campañas en el centro Microsoft 365 seguridad](../../media/campaigns-overview.png)

También puedes acceder a vistas de campaña desde:

- **Colaboración & correo electrónico** \> **Explorador** \> **Ver** \> **Campañas**
- **Colaboración & correo electrónico** \> **Explorador** \> **Ver** \> **Todo el correo electrónico** \> **Pestaña Campaña**
- **Colaboración & correo electrónico** \> **Explorador** \> **Ver** \> **Phish** \> **Pestaña Campaña**
- **Colaboración & correo electrónico** \> **Explorador** \> **Ver** \> **Malware** \> **Pestaña Campaña**

Para obtener acceso a las vistas de campaña, debe ser  miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad o Lector de seguridad en el centro de seguridad. Para obtener más información, vea [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](permissions-microsoft-365-security-center.md).

## <a name="campaigns-overview"></a>Introducción a las campañas

La página de información general muestra información sobre todas las campañas.

En la pestaña **Campaña** predeterminada, el área **Tipo de** campaña muestra un gráfico de barras que muestra el número de destinatarios por día. De forma predeterminada, el gráfico muestra datos **de phishing** **y malware.**

> [!TIP]
> Si no ve ningún dato de campaña, intente cambiar el intervalo de fechas o los [filtros](#filters-and-settings).

La tabla debajo del gráfico de la página de información general muestra la siguiente información en la **pestaña Campaña:**

- **Nombre**

- **Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña. Ten en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.

- **Dirigido:** el porcentaje calculado por: (el número de destinatarios de la campaña en su organización) / (el número total de destinatarios de la campaña en todas las organizaciones del servicio). Este valor indica el grado en que la campaña se dirige solo a su organización (un valor más alto) frente a otras organizaciones del servicio (un valor inferior).

- **Tipo**: Este valor es **Phish** o **Malware**.

- **Subtipo:** este valor contiene más detalles sobre la campaña. Por ejemplo:
  - **Phish:** cuando esté disponible, la marca que está suplantado por esta campaña. Por ejemplo, `Microsoft` , , , o `365` `Unknown` `Outlook` `DocuSign` .
  - **Malware**: Por ejemplo, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .

  Cuando esté disponible, la marca que se está suplantado por esta campaña. Cuando La detección es controlada por Defender Office 365 tecnología, el prefijo **ATP-** se agrega al valor de subtipo.

- **Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.

- **Bandeja de entrada:** el número de usuarios que recibieron mensajes de esta campaña en su Bandeja de entrada (no entregado a su carpeta correo no deseado).

- **Clic:** número de usuarios que han hecho clic en la dirección URL o han abierto los datos adjuntos en el mensaje de suplantación de identidad.

- **Tasa de clics:** el porcentaje calculado por "**Bandeja** de entrada  /  **con clic".** Este valor es un indicador de la eficacia de la campaña. En otras palabras, si los destinatarios pudieron identificar el mensaje como suplantación de identidad y si no hicieron clic en la dirección URL de carga.

  Ten en cuenta **que la tasa** de clics no se usa en campañas de malware.

- **Visitado:** cuántos usuarios llegaron realmente al sitio web de carga. Si hay valores **clicked,** pero Caja fuerte bloqueado el acceso al sitio web, este valor será cero.

La **pestaña Origen de** la campaña muestra los orígenes de mensajes en un mapa del mundo.

### <a name="filters-and-settings"></a>Filtros y configuración

En la parte superior de la **página Campaña,** hay varias opciones de configuración de filtro y consulta que le ayudarán a encontrar y aislar campañas específicas.

![Filtros de campaña](../../media/campaign-filters-and-settings.png)

El filtrado más básico que puede hacer es la fecha y hora de inicio y la fecha y hora de finalización.

Para filtrar aún más la vista, puede hacer una sola propiedad con varios valores filtrando haciendo clic en el botón **Tipo** de campaña, realizando la selección y, a continuación, haciendo clic en **Actualizar**.

Las propiedades de campaña filtrables que están disponibles en el botón **Tipo** de campaña se describen en la siguiente lista:

- **Básico**:
  - **Tipo de campaña**: Seleccione **Malware** o **Phish**. Borrar las selecciones tiene el mismo resultado que seleccionar ambas.
  - **Nombre de la campaña**
  - **Subtipo campaña**
  - **Remitente**
  - **Destinatarios**
  - **Dominio del remitente**
  - **Asunto**
  - **Nombres de archivos adjuntos**
  - **Familia de malware**
  - **Etiquetas:** usuarios o grupos a los que se ha aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).
  - **Acción de entrega**
  - **Acción adicional**
  - **Directionality**
  - **Tecnología de detección**
  - **Ubicación de entrega original**
  - **Ubicación de entrega más reciente**
  - **Invalidaciones del sistema**

- **Avanzadas**:
  - **Id. de mensaje de Internet:** disponible en el **campo de encabezado Id. de** mensaje en el encabezado del mensaje. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).
  - **Id. de** mensaje de red: valor GUID que está disponible en el campo de encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el encabezado del mensaje.
  - **IP del remitente**
  - **Datos adjuntos SHA256:** para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Id. de clúster**
  - **Id. de alerta**
  - **Id. de directiva de alerta**
  - **Id. de campaña**
  - **Señal de dirección URL de ZAP**

- **DIRECCIONES URL:**
  - **Dominio de dirección URL**
  - **Dominio y ruta de acceso url**
  - **URL**
  - **Ruta de acceso url**
  - **Veredicto de clic**

Para un filtrado más avanzado, incluido el filtrado por varias propiedades, puede hacer clic en el **botón** Filtro avanzado para crear una consulta. Las mismas propiedades de campaña están disponibles, pero con las siguientes mejoras:

- Puede hacer clic **en Agregar una condición para** seleccionar varias condiciones.
- Puede elegir el **operador And** o **Or** entre condiciones.
- Puede seleccionar el elemento **de grupo Condición** en la parte inferior de la lista de condiciones para formar condiciones compuestas complejas.

Cuando haya terminado, haga clic en el **botón** Consulta.

Después de crear un filtro básico o avanzado, puede guardarlo con **Guardar** consulta o **Guardar consulta como**. Más adelante, cuando vuelva a la **página Campañas,** puede cargar un filtro guardado haciendo clic en **Configuración de consulta guardada.**

Para exportar el gráfico o la lista de campañas, haga clic en Exportar **y** seleccione Exportar **datos del** gráfico o Exportar lista **de campañas.**

Si tienes una suscripción a Microsoft Defender para endpoint, puedes hacer clic en **MDE Configuración** para conectar o desconectar la información de las campañas con Microsoft Defender para endpoint. Para obtener más información, vea [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).

## <a name="campaign-details"></a>Detalles de la campaña

Al hacer clic en el nombre de una campaña, los detalles de la campaña aparecen en un desplegable.

### <a name="campaign-information"></a>Información de campaña

En la parte superior de la vista de detalles de la campaña, está disponible la siguiente información de campaña:

- **Identificador de campaña:** el identificador único de la campaña.
- **Actividad:** duración y actividad de la campaña.
- Los siguientes datos para el filtro de intervalo de fechas que seleccionó (o que seleccione en la escala de tiempo):
- **Impacto**
- **Mensajes:** número total de destinatarios.
- **Bandeja de entrada:** el número de mensajes que se entregaron a la Bandeja de entrada, no a la carpeta Correo no deseado.
- **Vínculo al que se ha** hecho clic: cuántos usuarios han hecho clic en la carga de la dirección URL en el mensaje de suplantación de identidad.
- **Vínculo visitado:** cuántos usuarios visitaron la dirección URL.
- **Targeted(%)**: el porcentaje calculado por: (el número de destinatarios de la campaña en su organización) / (el número total de destinatarios de la campaña en todas las organizaciones del servicio). Tenga en cuenta que este valor se calcula durante toda la duración de la campaña y no cambia en función de los filtros de fecha.
- La fecha y hora de inicio y los filtros de fecha y hora de finalización para el flujo de la campaña se describen en la sección siguiente.
- Escala de tiempo interactiva de la actividad de la campaña: la escala de tiempo muestra la actividad durante toda la vida útil de la campaña. Puede pasar el puntero sobre los puntos de datos del gráfico para ver la cantidad de mensajes detectados.

![Información de campaña](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Flujo de la campaña

En medio de la vista de detalles de la campaña, los detalles importantes sobre la campaña se presentan en un diagrama de flujo horizontal (conocido como diagrama _de Sankey)._ Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.

> [!TIP]
> La información que se muestra en el diagrama de flujo se controla mediante el filtro de intervalo de fechas de la escala de tiempo, tal como se describe en la sección anterior.

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).

El diagrama contiene la información siguiente:

- **IP de remitentes**
- **Dominios de remitente**
- **Veredictos de** filtro: los valores de veredicto están relacionados con los veredictos de filtrado de correo no deseado y suplantación de identidad disponibles, tal como se describe en Encabezados de mensajes contra [correo no deseado.](anti-spam-message-headers.md) Los valores disponibles se describen en la tabla siguiente:

  <br>

  ****

  |Valor|Veredicto de filtro de correo no deseado|Descripción|
  |---|---|---|
  |**Permitido**|`SFV:SKN` <p> `SFV:SKI`|El mensaje se marcó como no correo no deseado o filtrado omitido antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, una regla de flujo de correo (también conocida como regla de transporte) marcó el mensaje como no correo no deseado. <p> El mensaje omitió el filtrado de correo no deseado por otros motivos. Por ejemplo, el remitente y el destinatario parecen estar en la misma organización.|
  |**Bloqueado**|`SFV:SKS`|El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, mediante una regla de flujo de correo.|
  |**Detectados**|`SFV:SPM`|El mensaje se marcó como correo no deseado por el filtro de correo no deseado.|
  |**No detectado**|`SFV:NSPM`|El mensaje se marcó como correo no deseado mediante el filtrado de correo no deseado.|
  |**Liberado**|`SFV:SKQ`|El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.|
  |**Permitir inquilino**<sup>\*</sup>|`SFV:SKA`|El mensaje omitió el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**Bloque de inquilinos**<sup>\*\*</sup>|`SFV:SKA`|El filtrado de correo no deseado bloqueó el mensaje debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**User Allow**<sup>\*</sup>|`SFV:SFE`|El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes Caja fuerte usuario.|
  |**Bloqueo de usuario**<sup>\*\*</sup>|`SFV:BLK`|El mensaje se bloqueó mediante el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados de un usuario.|
  |**ZAP**|No aplicable|[La purga automática de hora cero (ZAP)](zero-hour-auto-purge.md) movió el mensaje entregado a la carpeta o cuarentena de correo no deseado. La acción se configura en la directiva contra correo no deseado.|
  |

  <sup>\*</sup> Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.

  <sup>\*\*</sup> Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregarse.

- **Destinos** de mensajes: es probable que desee investigar los mensajes que se entregaron a los destinatarios (ya sea a la Bandeja de entrada o a la carpeta Correo no deseado), incluso si los usuarios no han hecho clic en la dirección URL de carga del mensaje. También puede quitar los mensajes en cuarentena de la cuarentena. Para obtener más información, vea [Quarantined email messages in EOP](quarantine-email-messages.md).
  - **Carpeta eliminada**
  - **Se ha descartado**
  - **Externo:** el destinatario se encuentra en la organización de correo electrónico local en entornos híbridos.
  - **Failed**
  - **Reenviado**
  - **Bandeja de entrada**
  - **Carpeta de correo no deseado**
  - **Cuarentena**
  - **Desconocido**

- **Clics de dirección URL:** estos valores se describen en la siguiente sección.

> [!NOTE]
> En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **Otros**.

#### <a name="url-clicks"></a>Clics de URL

Cuando se entrega un mensaje de suplantación de identidad (phishing) a la carpeta Bandeja de entrada o correo no deseado de un destinatario, siempre existe la posibilidad de que el usuario haga clic en la dirección URL de carga. No hacer clic en la dirección URL es una pequeña medida de éxito, pero debe determinar por qué el mensaje de suplantación de identidad se entregó incluso al buzón.

Si un usuario hizo clic en la dirección URL de carga en el mensaje de suplantación de identidad, las acciones se muestran en el área de **clics** de dirección URL del diagrama en la vista de detalles de la campaña.

- **Permitido**
- **BlockPage:** el destinatario hizo clic en la dirección URL de carga, pero su acceso al sitio web malintencionado fue bloqueado por una directiva de [vínculos](safe-links.md) Caja fuerte de la organización.
- **BlockPageOverride:** el destinatario hizo clic en la dirección URL de carga del mensaje, Caja fuerte Los vínculos intentaron detenerlos, pero se les permitió invalidar el bloque. Inspeccione las [directivas Caja fuerte links para](set-up-safe-links-policies.md) ver por qué los usuarios pueden invalidar el veredicto de vínculos Caja fuerte y continuar con el sitio web malintencionado.
- **PendingDetonationPage:** Caja fuerte datos adjuntos de Microsoft Defender para Office 365 está en proceso de abrir e investigar la dirección URL de carga en un entorno de equipo virtual.
- **PendingDetonationPageOverride:** se permitió al destinatario invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar a los resultados.

### <a name="tabs"></a>Pestañas

Las pestañas de la vista detalles de la campaña te permiten investigar aún más la campaña.

> [!TIP]
> La información que se muestra en las pestañas se controla mediante el filtro de intervalo de fechas de la escala de tiempo, tal como se describe en la sección [Información de campaña.](#campaign-information)

- **Clics de dirección URL:** si los usuarios no han hecho clic en la dirección URL de carga del mensaje, esta sección estará en blanco. Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:
  - **Usuario**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Hora de hacer clic**
  - **Veredicto de clic**

- **IP de remitentes**
  - **IP del remitente**<sup>\*</sup>
  - **Recuento total**
  - **Bandeja de entrada**
  - **Sin bandeja de entrada**
  - **SPF pasado:** el remitente fue autenticado por el Marco de [directivas de remitente (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Un remitente que no pasa la validación de SPF indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.

- **Remitentes**
  - **Remitente:** esta es la dirección de remitente real del comando SMTP MAIL FROM, que no es necesariamente la dirección de correo electrónico De: que los usuarios ven en sus clientes de correo electrónico.
  - **Recuento total**
  - **Bandeja de entrada**
  - **Sin bandeja de entrada**
  - **DKIM pasado:** el remitente se autenticó mediante el correo identificado de claves de dominio [(DKIM).](support-for-validation-of-dkim-signed-messages.md) Un remitente que no pasa la validación DKIM indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.
  - **DMARC pasado:** el remitente se autenticó mediante autenticación de mensajes basada en dominio, informes [y conformidad (DMARC).](use-dmarc-to-validate-email.md) Un remitente que no pasa la validación dmarc indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.

- **Archivos adjuntos**
  - **Filename**
  - **SHA256**
  - **Familia de malware**
  - **Recuento total**

- **URL**
  - **URL**<sup>\*</sup>
  - **Recuento total**

<sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña. Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.

### <a name="buttons"></a>Botones

Los botones de la parte inferior de la vista detalles de la campaña te permiten investigar y registrar detalles sobre la campaña:

- **Explorar mensajes:** usa el poder del Explorador de amenazas para investigar aún más la campaña:
  - **Todos los mensajes:** abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de** campaña como filtro de búsqueda.
  - **Mensajes en bandeja de entrada:** abre una nueva pestaña de búsqueda del Explorador de amenazas con el **id.** de campaña y la ubicación de **entrega: Bandeja** de entrada como filtro de búsqueda.
  - **Mensajes internos:** abre una nueva pestaña de búsqueda del Explorador de amenazas con el **id.** de campaña y **direccionalidad: intra-org** como filtro de búsqueda.

- **Descargar informe de amenazas:** descargue los detalles de la campaña en un documento de Word (de forma predeterminada, denominado CampaignReport.docx). Ten en cuenta que la descarga contiene detalles durante toda la duración de la campaña (no solo las fechas de filtro seleccionadas).
