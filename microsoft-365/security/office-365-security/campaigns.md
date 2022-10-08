---
title: Vistas de campaña en el plan de Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom: ''
description: Obtenga información sobre las vistas de campaña en Microsoft Defender para Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 61f5f6269d4d6fa01aa5866063d716a3cface0ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68082819"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Vistas de campaña en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Vistas de campaña es una característica de Microsoft Defender para Office 365 Plan 2 (por ejemplo, Microsoft 365 E5 u organizaciones con un complemento Defender para Office 365 Plan 2). Las vistas de campaña del portal de Microsoft 365 Defender identifican y clasifican los ataques de suplantación de identidad (phishing) en el servicio. Vistas de la campaña puede ayudarle a:

- Investigar y responder eficazmente a los ataques de suplantación de identidad.
- Entender mejor el alcance del ataque.
- Proporcionar información a los responsables de la toma de decisiones.

La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.

Vea este breve vídeo sobre cómo las vistas de las campañas en Microsoft Defender para Office 365 le ayudan a comprender las campañas de ataque dirigidas a su organización.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGBL8]

## <a name="what-is-a-campaign"></a>¿Qué es una campaña?

Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones. Email ataques que roban credenciales y datos de la empresa son un sector grande y lucrativo. A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar el éxito continuo.

Microsoft aprovecha las grandes cantidades de datos anti-phishing, antispam y antimalware en todo el servicio para ayudar a identificar las campañas. Analizamos y clasificamos la información de ataque según varios factores. Por ejemplo:

- **Origen de ataque**: las direcciones IP de origen y los dominios de correo electrónico del remitente.
- **Propiedades del mensaje**: contenido, estilo y tono de los mensajes.
- **Destinatarios de mensajes**: cómo están relacionados los destinatarios. Por ejemplo, dominios de destinatario, funciones de trabajo de destinatario (administradores, ejecutivos, etc.), tipos de empresa (grandes, pequeños, públicos, privados, etc.) e industrias.
- **Carga de ataque**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.

Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos. Es posible que se inicie una campaña en su organización específica o que su organización forme parte de una campaña más grande en varias empresas.

## <a name="campaign-views-in-the-microsoft-365-defender-portal"></a>Vistas de campaña en el portal de Microsoft 365 Defender

Las vistas de campaña están disponibles en el portal de Microsoft 365 Defender en <https://security.microsoft.com> **Email & campañas de colaboración** \> o directamente en .<https://security.microsoft.com/campaigns>

:::image type="content" source="../../media/campaigns-overview.png" alt-text="Información general sobre las campañas en el portal de Microsoft 365 Defender" lightbox="../../media/campaigns-overview.png":::

También puedes acceder a Las vistas de campaña desde:

- **Email &** **campañas** de **vista del** \> **Explorador** \> de colaboración \>
- Email & **pestaña** **Ver** \> todas las campañas de **correo electrónico** \> del **Explorador** \> de **colaboración** \>
- Email & pestaña Ver **campaña** **de phish** \> **del** \> **Explorador** \> de **colaboración** \>
- Email & pestaña Ver **campaña** de **malware** \> **del** \> **Explorador** \> de **colaboración** \>

Para acceder a las vistas de campaña, debe ser miembro de los grupos de roles Administración de la **organización**, **Administrador de seguridad** o **Lector de seguridad** en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="campaigns-overview"></a>Introducción a las campañas

En la página de información general se muestra información sobre todas las campañas.

En la pestaña **Campaña** predeterminada, el área **Tipo de campaña** muestra un gráfico de barras que muestra el número de destinatarios al día. De forma predeterminada, el gráfico muestra los datos **de Phish** y **Malware** .

> [!TIP]
> Si no ve ningún dato de campaña, intente cambiar el intervalo de fechas o [los filtros](#filters-and-settings).

La tabla debajo del gráfico de la página de información general muestra la siguiente información en la pestaña **Campaña** :

- **Nombre**

- **Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña. Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.

- **Dirigido**: el porcentaje calculado por: (el número de destinatarios de la campaña en su organización) / (el número total de destinatarios de la campaña en todas las organizaciones del servicio). Este valor indica el grado al que se dirige la campaña solo a su organización (un valor más alto) frente a otras organizaciones del servicio (un valor inferior).

- **Tipo**: este valor es **Phish** o **Malware**.

- **Subtipo**: este valor contiene más detalles sobre la campaña. Por ejemplo:
  - **Phish**: Cuando esté disponible, la marca que está siendo protegida por esta campaña. Por ejemplo, , `Microsoft``365`, `Unknown`, `Outlook`o `DocuSign`.
  - **Malware**: por ejemplo, `HTML/PHISH` o `HTML/<MalwareFamilyName>`.

  Cuando esté disponible, la marca que está siendo protegida por esta campaña. Cuando la detección se controla mediante Defender para Office 365 tecnología, el prefijo **ATP-** se agrega al valor del subtipo.

- **Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.

- **Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no entregados a su carpeta de Email de correo no deseado).

- **Clicado**: el número de usuarios que han hecho clic en la dirección URL o que han abierto los datos adjuntos en el mensaje de suplantación de identidad (phishing).

- **Tasa de clics**: porcentaje calculado por "**Bandeja de entrada** **con** /  clic". Este valor es un indicador de la eficacia de la campaña. Es decir, si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y si no hicieron clic en la dirección URL de carga.

  Tenga en cuenta que **la tasa de clics** no se usa en las campañas de malware.

- **Visitado**: cuántos usuarios realmente lo hicieron a través del sitio web de carga útil. Si hay valores **clicked** , pero vínculos seguros bloquearon el acceso al sitio web, este valor será cero.

La pestaña **Origen de la campaña** muestra los orígenes de mensajes en un mapa del mundo.

### <a name="filters-and-settings"></a>Filtros y configuración

En la parte superior de la página **Campaña** , hay varias configuraciones de filtro y consulta que le ayudarán a buscar y aislar campañas específicas.

:::image type="content" source="../../media/campaign-filters-and-settings.png" alt-text="Filtros de campaña" lightbox="../../media/campaign-filters-and-settings.png":::

El filtrado más básico que puede hacer es la fecha y hora de inicio y la fecha y hora de finalización.

Para filtrar aún más la vista, puede realizar un filtrado de propiedades únicas con varios valores haciendo clic en el botón **Tipo de campaña** , realizando la selección y, a continuación, haciendo clic en **Actualizar**.

Las propiedades de campaña filtrables que están disponibles en el botón **Tipo de campaña** se describen en la lista siguiente:

- **Básico**:
  - **Tipo de campaña**: seleccione **Malware** o **Phish**. Borrar las selecciones tiene el mismo resultado que seleccionar ambas.
  - **Nombre de la campaña**
  - **Subtipo de campaña**
  - **Sender**
  - **Destinatarios**
  - **Dominio del remitente**
  - **Asunto**
  - **Nombres de archivos adjuntos**
  - **Familia de malware**
  - **Etiquetas**: usuarios o grupos que han aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).
  - **Acción de entrega**
  - **Acción adicional**
  - **Directionality**
  - **Tecnología de detección**
  - **Ubicación de entrega original**
  - **Ubicación de entrega más reciente**
  - **Invalidaciones del sistema**

- **Avanzadas**:
  - **Id. de mensaje de Internet**: disponible en el campo encabezado **Message-ID** del encabezado del mensaje. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).
  - **Id**. de mensaje de red: valor GUID que está disponible en el campo de encabezado **X-MS-Exchange-Organization-Network-Message-Id** del encabezado del mensaje.
  - **IP del remitente**
  - **Datos adjuntos SHA256**: para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.
  - **Id. de clúster**
  - **Identificador de alerta**
  - **Identificador de directiva de alerta**
  - **Identificador de campaña**
  - **Señal de dirección URL de ZAP**

- **Direcciones URL**:
  - **Dominio DE DIRECCIÓN URL**
  - **Dominio y ruta de acceso url**
  - **URL**
  - **Ruta de acceso url**
  - **Haga clic en veredicto**

Para obtener un filtrado más avanzado, incluido el filtrado por varias propiedades, puede hacer clic en el botón **Filtro avanzado** para compilar una consulta. Las mismas propiedades de campaña están disponibles, pero con las siguientes mejoras:

- Puede hacer clic en **Agregar una condición** para seleccionar varias condiciones.
- Puede elegir el operador **And** o **Or** entre condiciones.
- Puede seleccionar el elemento **Grupo de condiciones** en la parte inferior de la lista de condiciones para formar condiciones compuestas complejas.

Cuando haya terminado, haga clic en el botón **Consulta** .

Después de crear un filtro básico o avanzado, puede guardarlo mediante **Guardar consulta** o **Guardar consulta como**. Más adelante, cuando vuelva a la página **Campañas** , puede cargar un filtro guardado haciendo clic en **Configuración de consulta guardada**.

Para exportar el gráfico o la lista de campañas, haga clic en **Exportar** y seleccione **Exportar datos de gráficos** o **Exportar lista de campañas**.

Si tiene una suscripción Microsoft Defender para punto de conexión, puede hacer clic en **Configuración de MDE** para conectar o desconectar la información de las campañas con Microsoft Defender para punto de conexión. Para obtener más información, consulte [Integración de Microsoft Defender para Office 365 con Microsoft Defender para punto de conexión](integrate-office-365-ti-with-mde.md).

## <a name="campaign-details"></a>Detalles de la campaña

Al hacer clic en el nombre de una campaña, los detalles de la campaña aparecen en un control flotante.

### <a name="campaign-information"></a>Información de la campaña

En la parte superior de la vista de detalles de la campaña, está disponible la siguiente información de campaña:

- **Identificador de campaña**: identificador de campaña único.
- **Actividad**: duración y actividad de la campaña.
- Los siguientes datos para el filtro de intervalo de fechas seleccionado (o que seleccione en la escala de tiempo):
- **Impacto**
- **Mensajes**: el número total de destinatarios.
- **Bandeja de entrada**: el número de mensajes que se entregaron a la bandeja de entrada, no a la carpeta de Email de correo no deseado.
- **Vínculo en el que se ha hecho clic**: cuántos usuarios han hecho clic en la carga de la dirección URL en el mensaje de suplantación de identidad ( phishing).
- **Vínculo visitado**: cuántos usuarios visitaron la dirección URL.
- **Targeted(%)**: el porcentaje calculado por: (el número de destinatarios de la campaña en su organización) / (el número total de destinatarios de la campaña en todas las organizaciones del servicio). Tenga en cuenta que este valor se calcula durante toda la duración de la campaña y no cambia en función de los filtros de fecha.
- Filtros de fecha y hora de inicio y finalización de datos y hora para el flujo de campaña, como se describe en la sección siguiente.
- Una escala de tiempo interactiva de la actividad de la campaña: la escala de tiempo muestra la actividad durante toda la duración de la campaña. Puede mantener el puntero sobre los puntos de datos del gráfico para ver la cantidad de mensajes detectados.

:::image type="content" source="../../media/campaign-details-campaign-info.png" alt-text="La información de la campaña" lightbox="../../media/campaign-details-campaign-info.png":::

### <a name="campaign-flow"></a>Flujo de la campaña

En medio de la vista de detalles de la campaña, se presentan detalles importantes sobre la campaña en un diagrama de flujo horizontal (conocido como diagrama _sankey_ ). Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.

> [!TIP]
> La información que se muestra en el diagrama de flujo se controla mediante el filtro de intervalo de fechas de la escala de tiempo, tal como se describe en la sección anterior.

:::image type="content" source="../../media/campaign-details-no-recipient-actions.png" alt-text="Detalles de la campaña que no contienen clics en la dirección URL del usuario" lightbox="../../media/campaign-details-no-recipient-actions.png":::

Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).

El diagrama contiene la información siguiente:

- **IP de remitentes**
- **Dominios de remitente**
- **Veredictos de filtro: los** valores de veredicto están relacionados con los veredictos de filtrado de spam y phishing disponibles, como se describe en [Encabezados de mensajes antispam](anti-spam-message-headers.md). Los valores disponibles se describen en la tabla siguiente:

  |Valor|Veredicto de filtro de correo no deseado|Descripción|
  |---|---|---|
  |**Permitido**|`SFV:SKN` <p> `SFV:SKI`|El mensaje se ha marcado como no spam ni filtrado omitido antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, el mensaje se ha marcado como no spam mediante una regla de flujo de correo (también conocida como regla de transporte). <p> El mensaje omitió el filtrado de correo no deseado por otras razones. Por ejemplo, el remitente y el destinatario parecen estar en la misma organización.|
  |**Bloqueado**|`SFV:SKS`|El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, mediante una regla de flujo de correo.|
  |**Detectados**|`SFV:SPM`|El mensaje se marcó como correo no deseado por el filtro de correo no deseado.|
  |**No detectado**|`SFV:NSPM`|El filtro de correo no deseado marcó el mensaje como no spam.|
  |**Fecha de publicación**|`SFV:SKQ`|El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.|
  |**Permitir inquilino**<sup>\*</sup>|`SFV:SKA`|El mensaje omitió el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**Bloque de inquilinos**<sup>\*\*</sup>|`SFV:SKA`|El filtro de correo no deseado bloqueó el mensaje debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**Permitir usuario**<sup>\*</sup>|`SFV:SFE`|El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros de un usuario.|
  |**Bloque de usuario**<sup>\*\*</sup>|`SFV:BLK`|El filtrado de correo no deseado bloqueó el mensaje porque el remitente estaba en la lista de remitentes bloqueados de un usuario.|
  |**ZAP**|No aplicable|[La purga automática de cero horas (ZAP)](zero-hour-auto-purge.md) ha movido el mensaje entregado a la carpeta o cuarentena de Email no deseado. La acción se configura en [directivas contra correo no deseado](configure-your-spam-filter-policies.md).|

  <sup>\*</sup> Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.

  <sup>\*\*</sup> Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregarse.

- **Destinos del mensaje**: es probable que quiera investigar los mensajes que se entregaron a los destinatarios (ya sea a la bandeja de entrada o a la carpeta de Email no deseado), incluso si los usuarios no hicieron clic en la dirección URL de carga del mensaje. También puede quitar los mensajes en cuarentena de la cuarentena. Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).
  - **Carpeta eliminada**
  - **Cayó**
  - **Externo**: el destinatario se encuentra en la organización de correo electrónico local en entornos híbridos.
  - **Failed**
  - **Reenviado**
  - **Bandeja de entrada**
  - **Carpeta de correo no deseado**
  - **Cuarentena**
  - **Desconocido**

- **Clics de dirección URL**: estos valores se describen en la sección siguiente.

> [!NOTE]
> En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **Otros**.

#### <a name="url-clicks"></a>Clics de URL

Cuando se entrega un mensaje de suplantación de identidad (phishing) a la bandeja de entrada o a la carpeta de Email no deseado de un destinatario, siempre existe la posibilidad de que el usuario haga clic en la dirección URL de carga. No hacer clic en la dirección URL es una pequeña medida de éxito, pero debe determinar por qué el mensaje de suplantación de identidad se entregó incluso al buzón de correo.

Si un usuario ha hecho clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área **url clicks** del diagrama en la vista de detalles de la campaña.

- **Permitido**
- **BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero su acceso al sitio web malintencionado fue bloqueado por una directiva [de vínculos seguros](safe-links.md) de su organización.
- **BlockPageOverride**: el destinatario ha hecho clic en la dirección URL de carga del mensaje, Vínculos seguros intentó detenerlos, pero se les permitió invalidar el bloque. Inspeccione [las directivas de vínculos seguros](set-up-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio web malintencionado.
- **PendingDetonationPage**: datos adjuntos seguros en Microsoft Defender para Office 365 está en proceso de abrir e investigar la dirección URL de carga en un entorno de equipo virtual.
- **PendingDetonationPageOverride**: se permitió al destinatario invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar a los resultados.

### <a name="tabs"></a>Pestañas

Las pestañas de la vista de detalles de la campaña le permiten investigar aún más la campaña.

> [!TIP]
> La información que se muestra en las pestañas se controla mediante el filtro de intervalo de fechas de la escala de tiempo, tal como se describe en la sección [Información](#campaign-information) de la campaña.

- **Clics en la dirección URL**: si los usuarios no hacen clic en la dirección URL de carga del mensaje, esta sección estará en blanco. Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:
  - **Usuario**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Tiempo de clic**
  - **Haga clic en veredicto**

- **IP de remitentes**
  - **IP del remitente**<sup>\*</sup>
  - **Recuento total**
  - **Bandeja de entrada**
  - **Sin bandeja de entrada**
  - **SPF pasado**: el marco de [directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md) autenticó el remitente. Un remitente que no pasa la validación SPF indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.

- **Remitentes**
  - **Remitente**: esta es la dirección de remitente real en el comando SMTP MAIL FROM, que no es necesariamente la dirección de correo electrónico De: que los usuarios ven en sus clientes de correo electrónico.
  - **Recuento total**
  - **Bandeja de entrada**
  - **Sin bandeja de entrada**
  - **DKIM pasado**: el remitente se autenticó mediante [correo identificado de claves de dominio (DKIM).](support-for-validation-of-dkim-signed-messages.md) Un remitente que no pasa la validación DKIM indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.
  - **DMARC pasado**: el remitente se autenticó mediante [autenticación de mensajes basada en dominio, informes y conformidad (DMARC).](use-dmarc-to-validate-email.md) Un remitente que no pasa la validación de DMARC indica un remitente no autenticado o el mensaje suplanta a un remitente legítimo.

- **Adjuntos**
  - **Filename**
  - **SHA256**
  - **Familia de malware**
  - **Recuento total**

- **URL**
  - **URL**<sup>\*</sup>
  - **Recuento total**

<sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña. Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.

### <a name="buttons"></a>Botones

Los botones de la parte inferior de la vista de detalles de la campaña le permiten investigar y registrar detalles sobre la campaña:

- **Explorar mensajes**: use la eficacia del Explorador de amenazas para investigar aún más la campaña:
  - **Todos los mensajes**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **id. de campaña** como filtro de búsqueda.
  - **Mensajes bandeja de entrada**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el **identificador de campaña** y la **ubicación de entrega: Bandeja de entrada** como filtro de búsqueda.
  - **Mensajes internos**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el **identificador de campaña** y **direccionalidad: Intra-org** como filtro de búsqueda.

- **Descargar informe de amenazas**: descargue los detalles de la campaña en un documento de Word (de forma predeterminada, denominado CampaignReport.docx). Tenga en cuenta que la descarga contiene detalles durante toda la duración de la campaña (no solo las fechas de filtro que seleccionó).
