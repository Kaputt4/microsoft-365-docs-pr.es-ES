---
title: Vistas de campaña en Office 365 plan ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre las Vistas de la campaña en la Protección contra amenazas avanzada de Office 365.
ms.openlocfilehash: 72662519177f4ac43e3de04e9755fd99f5ffb03f
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867204"
---
# <a name="campaign-views-in-office-365-atp"></a>Vistas de la campaña en ATP de Office 365

Las vistas de campañas son una característica del plan 2 de la protección contra amenazas avanzada (ATP) (por ejemplo, Microsoft 365 E5 u organizaciones con un complemento ATP plan 2). Campaing views in the Security & Compliance Center identifica y categoriza los ataques de suplantación de identidad (phishing) en el servicio. Vistas de la campaña puede ayudarle a:

- Investigar y responder eficazmente a los ataques de suplantación de identidad.
- Entender mejor el alcance del ataque.
- Proporcionar información a los responsables de la toma de decisiones.

La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.

## <a name="what-is-a-campaign"></a>¿Qué es una campaña?

Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones. Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector importante y lucrativo. A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar un éxito continuo.

Microsoft aprovecha la gran cantidad de datos contra phishing, contra correo electrónico no deseado y antimalware en todo el servicio para ayudarle a identificar las campañas. Analizamos y clasificamos la información de ataques de acuerdo con varios factores. Por ejemplo:

- **Origen del ataque**: las direcciones IP de origen y los dominios de correo electrónico del remitente.
- **Propiedades del mensaje**: el contenido, el estilo y el tono de los mensajes.
- **Destinatarios del mensaje**: cómo se relacionan los destinatarios. Por ejemplo, dominios de destinatarios, funciones de trabajo de destinatarios (administradores, ejecutivos, etc.), tipos de empresas (grandes, pequeñas, públicas, privadas, etc.) y sectores.
- **Carga de ataques**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.

Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos. Es posible que se inicie una campaña en su organización específica o que la organización forme parte de una campaña más grande en varias compañías.

## <a name="campaign-views-the-security--compliance-center"></a>Vistas de campaña el centro de seguridad & cumplimiento

Las vistas de campaña están disponibles en el [centro de seguridad & cumplimiento](https://protection.office.com) en las campañas de **Administración de amenazas** \> **Campaigns**, o directamente en <https://protection.office.com/campaigns> .

![Información general de las campañas en el Centro de seguridad y cumplimiento](../../media/campaigns-overview.png)

También puede obtener acceso a las vistas de campañas desde:

- **Administración** \> de amenazas **Explorador** \> **Ver** \> **Campañas**

- **Administración** \> de amenazas **Explorador** \> **Ver** \> **Todo el correo electrónico** \> Ficha **campaña**

- **Administración** \> de amenazas **Explorador** \> **Ver** \> **Phish** \> Ficha **campaña**

- **Administración** \> de amenazas **Explorador** \> **Ver** \> **Malware** \> Ficha **campaña**

Para tener acceso a las vistas de campaña, debe ser miembro de los grupos de roles administración de la **organización**, **Administrador de seguridad**o **lector** de seguridad en el centro de seguridad & cumplimiento. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Información general sobre campañas

La página información general muestra información sobre todas las campañas.

En la ficha **campaña** predeterminada, el área **tipo de campaña** muestra un gráfico de barras que muestra el número de destinatarios por día. De forma predeterminada, el gráfico muestra los datos de **phish** y **malware** .

> [!TIP]
> Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas o los [filtros](#filters-and-settings).

El resto de la página de información general muestra la siguiente información en la pestaña **campaña** :

- **Nombre**

- **Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña. Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.

- **Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio). Este valor indica el grado al que se dirige la campaña sólo a la organización (un valor superior) en comparación con otras organizaciones del servicio (un valor inferior).

- **Tipo**: este valor puede ser **phish** o **malware**.

- **Subtipo**: este valor contiene más información sobre la campaña. Por ejemplo:

  - **Phish**: donde esté disponible, la marca que se está suplantando en esta campaña. Por ejemplo,,,, `Microsoft` `365` `Unknown` `Outlook` o `DocuSign` .

  - **Malware**: por ejemplo, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .

Donde esté disponible, la marca que está en phish a la campaña. Cuando la tecnología ATP controla la detección, el prefijo **ATP-** se agrega al valor SubType.

- **Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.

- **Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no se entregaron a la carpeta de correo electrónico no deseado).

- **Haga clic en**: el número de usuarios que hizo clic en la dirección URL o abrieron los datos adjuntos en el mensaje de suplantación de identidad.

- **Tasa de clic**: porcentaje calculado con "se ha**pulsado en**la  /  **bandeja de entrada**". Este valor es un indicador de la efectividad de la campaña. Es decir, si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y no han hecho clic en la dirección URL de carga.

  Tenga en cuenta que la **tasa de clics** no se usa en las campañas de malware.

- **Visitado**: el número de usuarios que se han realizado realmente a través del sitio web de carga. Si hay valores en los que se ha **pulsado** , pero los vínculos seguros han bloqueado el acceso al sitio web, este valor será cero.

La pestaña origen de la **campaña** muestra los orígenes del mensaje en un mapa del mundo.

### <a name="filters-and-settings"></a>Filtros y configuración

En la parte superior de la página vistas de campañas, hay varios filtros y configuraciones de consulta para ayudarle a encontrar y aislar campañas específicas.

![Filtros de campaña](../../media/campaign-filters-and-settings.png)

El filtrado más básico que puede hacer es la fecha y hora de inicio y la fecha y hora de finalización.

Para filtrar más la vista, puede hacer una sola propiedad con varios valores al filtrar haciendo clic en el botón **tipo de campaña** , haciendo su selección y, a continuación, haciendo clic en **Actualizar**.

Las propiedades de la campaña disponibles se describen en la siguiente lista:

- Basic

  - **Tipo de campaña**: seleccione **malware** o **phish**. Si se quitan las selecciones, se obtiene el mismo resultado que al seleccionar ambas.
  - **Nombre de la campaña**
  - **Subtipo de campaña**
  - **Remitente**
  - **Destinatarios**
  - **Dominio del remitente**
  - **Asunto**
  - **Nombres de archivos adjuntos**
  - **Familia de malware**
  - **Acción de entrega**
  - **Tecnología de detección**
  - **Tags**
  - **Invalidaciones del sistema**

- Opciones avanzadas

  - **Identificador del mensaje de Internet**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).
  
  - **Identificador de mensaje de red**: un valor GUID que está disponible en el campo de encabezado **X-MS-Exchange-Organization-Network-Message-ID** en el encabezado del mensaje.
  
  - **IP del remitente**
  
  - **Datos adjuntos SHA256**: para buscar el valor de hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **IDENTIFICADOR de clúster**
  
  - **IDENTIFICADOR de la Directiva de alertas**

- Direcciones URL

  - **Dominio de dirección URL**
  - **Dominio y ruta de acceso de dirección URL**
  - **URL**
  - **Ruta de dirección URL**
  - **Haga clic en veredicto**

Para un filtrado más avanzado, incluido el filtrado por varias propiedades, puede hacer clic en el botón **filtro avanzado** para crear una consulta. Están disponibles las mismas propiedades de la campaña, pero con las siguientes mejoras:

- Puede hacer clic en **Agregar condición** para seleccionar varias condiciones.
- Puede elegir el operador **y** u **o** entre las condiciones.
- Puede seleccionar el elemento de **grupo de condición** en la parte inferior de la lista de condiciones para crear condiciones compuestas complejas.

Cuando haya terminado, haga clic en el botón **consulta** .

Después de crear un filtro básico o avanzado, puede guardarlo con **Guardar consulta** o **Guardar consulta como**. Más adelante, cuando vuelva a las vistas de campañas, puede cargar un filtro guardado haciendo clic en **configuración de consulta guardada**.

Para exportar el gráfico o la lista de campañas, haga clic en **exportar** y seleccione **exportar datos de gráfico** o **Exportar lista de campañas**.

Si tiene una suscripción ATP de Microsoft defender, puede hacer clic en **WDATP** para conectar o desconectar la información sobre campañas con ATP de Microsoft defender. Para obtener más información, consulte [integrar Office 365 ATP con Microsoft defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).

## <a name="campaign-details"></a>Detalles de la campaña

Al hacer clic en el nombre de una campaña, los detalles de la campaña aparecen en un control flotante.

### <a name="campaign-information"></a>Información de la campaña

En la parte superior de la vista detalles de la campaña, está disponible la siguiente información de la campaña:

- **ID**: el identificador único de la campaña.

- **Iniciado** y **finalizado**: fecha de inicio y fecha de finalización de la campaña. Tenga en cuenta que estas fechas pueden extenderse más allá de las fechas de filtro que ha seleccionado en la página información general.

- **Impacto**: esta sección contiene los datos siguientes para el filtro de intervalo de fechas que haya seleccionado (o que seleccione en la escala de tiempo):
  
  - Número total de destinatarios.
  - El número de mensajes que se han "bandeja de entrada" (es decir, que se entregan a la bandeja de entrada y no a la carpeta de correo electrónico no deseado).
  - El número de usuarios que hizo clic en la carga de la URL en el mensaje de suplantación de identidad.
  - Howe muchos usuarios visitaron la dirección URL.

- **Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio). Tenga en cuenta que este valor se calcula en toda la duración de la campaña y no cambia en función de los filtros de fecha.

- Escala de tiempo interactiva de la actividad de la campaña: la escala de tiempo muestra la actividad durante toda la duración de la campaña. De forma predeterminada, el área sombreada incluye el filtro de intervalo de fechas que ha seleccionado en la información general. Puede hacer clic y arrastrar para seleccionar un punto inicial y un punto final específicos, <u>que cambiarán los datos que se muestran en el área de **impacto** y el resto de la página, tal y como se describe en las siguientes secciones</u>.

En la barra de título, puede hacer clic en el icono de descarga de la campaña de descarga del botón de instalación de la **campaña** ![ para descargar ](../../media/download-campaign-write-up-button.png) los detalles de la campaña en un documento de Word (de forma predeterminada, con el nombre CampaignReport.docx). Tenga en cuenta que la descarga contiene detalles sobre toda la duración de la campaña (no solo las fechas de filtro seleccionadas).

![Información de la campaña](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Flujo de la campaña

En la parte central de la vista detalles de la campaña, los detalles importantes sobre la campaña se presentan en la sección **flujo** en un diagrama de flujo horizontal (conocido como diagrama _Sankey_ ). Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.

> [!TIP]
> La información que se muestra en el diagrama de **flujo** está controlada por el intervalo de fechas sombreado de la escala de tiempo tal como se describe en la sección anterior.

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).

El diagrama contiene la información siguiente:

- **IP de remitentes**

- **Dominios de remitente**

- **Filtrar veredictos**: los valores de veredicto están relacionados con los veredictos de filtrado de suplantación de identidad y correo no deseado disponibles, como se describe en [encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). En la tabla siguiente se describen los valores disponibles:

  ****

  |Valor|Veredicto de filtro de correo no deseado|Description|
  |---|---|---|
  |**Permitido**|`SFV:SKN` <br/><br/> `SFV:SKI`|El mensaje se marcó como no es correo no deseado o omitido antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, un mensaje se marcó como no correo no deseado mediante una regla de flujo de correo (también denominada regla de transporte).<br/><br/>El mensaje omitió el filtrado de correo no deseado por otros motivos. Por ejemplo, el remitente y el destinatario parecen estar en la misma organización.|
  |**Bloqueado**|`SFV:SKS`|El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado. Por ejemplo, por una regla de flujo de correo.|
  |**Detectados**|`SFV:SPM`|El mensaje se marcó como correo no deseado por el filtro de correo no deseado.|
  |**No detectado**|`SFV:NSPM`|El mensaje se marcó como no correo no deseado por el filtrado de correo no deseado.|
  |**Exento**|`SFV:SKQ`|El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.|
  |**Permitir inquilino**<sup>\*</sup>|`SFV:SKA`|El mensaje omitió el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**Bloque tenant**<sup>\*\*</sup>|`SFV:SKA`|El mensaje fue bloqueado por el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado. Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.|
  |**Permitir al usuario**<sup>\*</sup>|`SFV:SFE`|El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros del usuario.|
  |**Bloque de usuario**<sup>\*\*</sup>|`SFV:BLK`|El mensaje fue bloqueado por el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados del usuario.|
  |**ZAP**|No aplicable|La [depuración automática de cero horas (ZAP)](zero-hour-auto-purge.md) movió el mensaje entregado a la carpeta de correo electrónico no deseado o a la cuarentena. La acción se configura en la Directiva contra correo no deseado.|
  |

  <sup>\*</sup> Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.

  <sup>\*\*</sup> Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregados.

- **Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea a la bandeja de entrada o a la carpeta de correo electrónico no deseado), incluso si los usuarios no han hecho clic en la dirección URL de carga en el mensaje. También puede quitar los mensajes en cuarentena de la cuarentena. Para obtener más información, vea [mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).

  - **Carpeta eliminada**
  - **Sombra**
  - **Externos**: el destinatario se encuentra en su organización de correo electrónico local en entornos híbridos.
  - **Failed**
  - **Reenviado**
  - **Bandeja de entrada**
  - **Carpeta de correo no deseado**
  - **Cuarentena**
  - **Desconocido**

- **Clics de dirección URL**: estos valores se describen en la siguiente sección.

> [!NOTE]
> En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **otros**.

#### <a name="url-clicks"></a>Clics de URL

Cuando un mensaje de suplantación de identidad se entrega a la bandeja de entrada o a la carpeta de correo no deseado del destinatario, siempre existe la posibilidad de que el usuario haga clic en la dirección URL de la carga. No hacer clic en la dirección URL es una pequeña medida del éxito, pero debe determinar por qué el mensaje de suplantación de identidad se entregó hasta el buzón.

Si un usuario hace clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área de **clics de la dirección URL** del diagrama en la vista detalles de la campaña.

- **Permitido**

- **BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero el acceso al sitio Web malintencionado fue bloqueado por las directivas de [vínculos seguros de ATP](atp-safe-links.md) en su organización.

- **BlockPageOverride**: el destinatario hizo clic en la dirección URL de carga en el mensaje, los vínculos seguros de ATP intentaron detenerlos, pero se permitió invalidar el bloque. Revise sus [directivas de vínculos seguros](set-up-atp-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio Web malintencionado.

- **PendingDetonationPage**: datos adjuntos seguros en Office 365 ATP está en proceso de abrir y investigar la dirección URL de carga en un entorno de equipo virtual.

- **PendingDetonationPageOverride**: el destinatario tuvo permiso para invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar los resultados.

### <a name="tabs"></a>Pestañas

Las pestañas de la vista detalles de la campaña le permiten investigar más detalladamente la campaña.

> [!TIP]
> La información que se muestra en las pestañas se controla mediante el intervalo de fechas sombreado en la escala de tiempo como se describe en la sección información de la [campaña](#campaign-information) .

- **Clics en dirección URL**: si los usuarios no han hecho clic en la dirección URL de la carga en el mensaje, esta sección estará en blanco. Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:

  - **Usuario**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Haga clic en hora**
  - **Haga clic en veredicto**

- **IP de remitentes**

  - **IP del remitente**<sup>\*</sup>
  - **Recuento total**
  - **En la bandeja de entrada**
  - **Sin bandeja de entrada**
  - **SPF superado**: el [marco de directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)autenticó el remitente. Un remitente que no pasa la validación SPF indica que un remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.

- **Remitentes**

  - **Sender**: esta es la dirección del remitente real en el comando SMTP mail from, que no tiene que ser necesariamente la dirección de correo electrónico que los usuarios ven en sus clientes de correo electrónico.
  - **Recuento total**
  - **En la bandeja de entrada**
  - **Sin bandeja de entrada**
  - **DKIM pasado**: el remitente ha sido autenticado por el [correo identificado por claves de dominio (DKIM)](support-for-validation-of-dkim-signed-messages.md). Un remitente que no pasa la validación de DKIM indica un remitente no autenticado o el mensaje está suplantando a un remitente legítimo.
  - **DMARC pasada**: el remitente ha sido autenticado por la [autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC)](use-dmarc-to-validate-email.md). Un remitente que no pasa la validación de DMARC indica un remitente no autenticado o el mensaje está suplantando a un remitente legítimo.

- **Attachments**

  - **Filename**
  - **SHA256**
  - **Familia de malware**
  - **Recuento total**

- **URL**

  - **URL**<sup>\*</sup>
  - **Recuento total**

<sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña. Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.

### <a name="buttons"></a>Botones

Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.

- **Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.

- **Explorar mensajes**de la bandeja de entrada: abre una nueva ficha de búsqueda del explorador de amenazas usando el identificador de la **campaña** y la **Ubicación de entrega: bandeja de entrada** como filtro de búsqueda.
