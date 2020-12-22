---
title: Explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use el explorador y las detecciones en tiempo real en el centro de seguridad y &amp; cumplimiento para investigar y responder a las amenazas con eficacia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8bca8e39029fe041c0bab59e92d8a653647746ef
ms.sourcegitcommit: 0ecac0387be6b49025b79ce8eb949a8cf62481e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2020
ms.locfileid: "49724419"
---
# <a name="threat-explorer-and-real-time-detections"></a>Explorador de amenazas y detecciones en tiempo real

Si su organización tiene [Microsoft defender para Office 365](office-365-atp.md) y dispone de los [permisos necesarios](#required-licenses-and-permissions), tendrá acceso al *Explorador* o a las *detecciones en tiempo real*, que antes eran *informes en tiempo real*. ([Consulte](#new-features-in-threat-explorer-and-real-time-detections)las novedades). En el centro de seguridad & cumplimiento, vaya a **Administración de amenazas** y, a continuación, seleccione **Explorer** _o_ **detección en tiempo real**.

|Con Microsoft defender para Office 365 plan 2, verá:|Con Microsoft defender para Office 365 plan 1, verá:|
|---|---|
|![Explorador de amenazas](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

El explorador o las detecciones en tiempo real ayudan a su equipo de operaciones de seguridad a investigar y responder a las amenazas con eficacia. El informe es similar a la siguiente imagen:

![Ir al explorador de administración de amenazas \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con este informe, puede:

- [Ver malware detectado por las características de seguridad de Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Ver la dirección URL de phishing y hacer clic en datos de veredicto](#view-phishing-url-and-click-verdict-data)
- [Inicie un proceso de investigación y respuesta automatizado desde una vista del explorador (solo en el](#start-automated-investigation-and-response) caso de defender para Office 365 plan 2)
- [Investigar el correo electrónico malintencionado y mucho más](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Mejoras en el explorador de amenazas y detecciones en tiempo real

### <a name="tags-in-threat-explorer"></a>Etiquetas en el explorador de amenazas

> [!NOTE]
> La característica de etiquetas de usuario está en *versión preliminar*, no está disponible para todos los usuarios y está sujeta a cambios. Para obtener información sobre la programación de versiones, consulte el plan de desarrollo de Microsoft 365.

Las etiquetas de usuario identifican grupos de usuarios específicos en Microsoft defender para Office 365. Para obtener más información acerca de las etiquetas, incluidas las licencias y la configuración, consulte [User Tags](user-tags.md).

En el explorador de amenazas, puede ver información acerca de las etiquetas de usuario en las siguientes experiencias.

#### <a name="email-grid-view"></a>Vista de cuadrícula de correo electrónico

La columna **etiquetas** de la cuadrícula de correo electrónico contiene todas las etiquetas que se han aplicado a los buzones del remitente o del destinatario. De forma predeterminada, las etiquetas del sistema, como las cuentas de prioridad, se muestran en primer lugar.

> [!div class="mx-imgBorder"]
> ![Filtrar etiquetas en la vista de cuadrícula de correo electrónico](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtrado

Puede usar las etiquetas como filtro. Buscar solo en las cuentas de prioridad o en escenarios específicos de etiquetas de usuario. También puede excluir los resultados que tengan algunas etiquetas. Combine esta funcionalidad con otros filtros para limitar el ámbito de investigación.

[![Etiquetas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![No filtrar etiquetas](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Control flotante de detalles de correo electrónico
Para ver las etiquetas individuales del remitente y el destinatario, seleccione el asunto para abrir el control flotante detalles del mensaje. En la pestaña **Resumen** , las etiquetas remitente y destinatario se muestran por separado, si están presentes para un correo electrónico.
La información sobre las etiquetas individuales para el remitente y el destinatario también se extiende a los datos CSV exportados, donde puede ver estos detalles en dos columnas independientes.

> [!div class="mx-imgBorder"]
> ![Etiquetas de detalles de correo electrónico](../../media/tags-flyout.png)

También se muestra información de etiquetas en la dirección URL hace clic en el control flotante. Para verla, vaya a phish o a toda la vista de correo electrónico y, a continuación, a la ficha **URL** o **clics de dirección URL** . Seleccione un control flotante de dirección URL individual para ver detalles adicionales acerca de los clics de esa dirección URL, incluidas las etiquetas asociadas a ese clic.

> [!div class="mx-imgBorder"]
> ![Etiquetas URL](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Mejoras en la experiencia de búsqueda de amenazas (próximamente)

### <a name="updated-threat-information-for-emails"></a>Información de amenazas actualizada para los correos electrónicos

Nos hemos concentrado en mejoras de la plataforma y la calidad de los datos para aumentar la precisión de los datos y la coherencia de los registros de correo electrónico. Entre las mejoras se incluyen la consolidación de la información de entrega previa y posentrega, como las acciones ejecutadas en un correo electrónico como parte del proceso de ZAP, en un único registro. También se incluyen detalles adicionales como el veredicto de correo no deseado, las amenazas a nivel de entidad (por ejemplo, qué dirección URL malintencionada) y las ubicaciones de entrega más recientes.

Después de estas actualizaciones, verá una entrada única para cada mensaje, independientemente de los distintos eventos posteriores a la entrega que afecten al mensaje. Las acciones pueden incluir ZAP, corrección manual (que significa acción de administrador), entrega dinámica, etc.

Además de mostrar las amenazas de malware y de suplantación de identidad, se ve el veredicto de correo no deseado asociado a un correo electrónico. En el correo electrónico, vea todas las amenazas asociadas con el correo electrónico junto con las tecnologías de detección correspondientes. Un correo electrónico puede tener cero, una o varias amenazas. Verá las amenazas actuales en la sección **detalles** del control flotante de correo electrónico. Para varias amenazas (como malware y phishing), el campo **detección** en la tecnología muestra la asignación de detección de amenazas, que es la tecnología de detección que identificó la amenaza.

El conjunto de tecnologías de detección ahora incluye nuevos métodos de detección, así como tecnologías de detección de correo no deseado. Puede usar el mismo conjunto de tecnologías de detección para filtrar los resultados en las diferentes vistas de correo electrónico (malware, phish, todo el correo electrónico).

> [!NOTE]
> Es posible que el análisis del veredicto no esté ligado necesariamente a las entidades. Por ejemplo, un correo electrónico puede clasificarse como phish o correo no deseado, pero no hay direcciones URL que se hayan marcado con un veredicto de phish o correo no deseado. Esto se debe a que los filtros también evalúan el contenido y otros detalles de un correo electrónico antes de asignar un veredicto.

#### <a name="threats-in-urls"></a>Amenazas en direcciones URL

Ahora puede ver la amenaza específica para una dirección URL en la pestaña **detalles** del control de correo electrónico. La amenaza puede ser *malware*, *phish*, *correo no deseado* o *ninguno*.)

> [!div class="mx-imgBorder"]
> ![Amenazas de URL](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Vista escala de tiempo actualizada (próximamente)

> [!div class="mx-imgBorder"]
> ![Vista escala de tiempo actualizada](../../media/Email_Timeline.png)

La vista escala de tiempo identifica todos los eventos de entrega y posterior a la entrega. Incluye información sobre la amenaza identificada en ese punto de tiempo para un subconjunto de estos eventos. La vista escala de tiempo también proporciona información acerca de cualquier acción adicional tomada (como una corrección manual o de ZAP), junto con el resultado de dicha acción. La información de la vista de escala de tiempo incluye:

- **Origen:** Origen del evento. Puede ser administrador/sistema/usuario.
- **Evento:** Incluye eventos de nivel superior, como la entrega original, corrección manual, ZAP, envíos y entrega dinámica.
- **Acción:** La acción específica que se ha realizado ya sea como parte de la acción de ZAP o de administrador (por ejemplo, eliminación temporal).
- **Amenazas:** Trata las amenazas (malware, phish, correo no deseado) identificadas en ese momento.
- **Resultado/detalles:** Más información sobre el resultado de la acción, por ejemplo, si se realizó como parte de la acción de ZAP/admin.

### <a name="original-and-latest-delivery-location"></a>Ubicación de entrega original y última

Actualmente, se muestra la ubicación de entrega en la cuadrícula de correo electrónico y el control flotante de correo electrónico. El campo **Ubicación de entrega** se cambia de nombre * ubicación de *_entrega original_* _. Y estamos introduciendo otro campo, la _*_última ubicación de entrega_*_.

_ La *Ubicación de entrega original** proporcionará más información sobre dónde se entregó un correo electrónico inicialmente. La **última ubicación de entrega** indicará dónde se descargará un correo electrónico después de acciones del sistema como *Zap* o acciones de administración, como *mover a elementos eliminados*. La última ubicación de entrega tiene como objetivo indicar a los administradores la última ubicación conocida del mensaje posterior a la entrega o cualquier acción del sistema o de administración. No incluye acciones de usuario final en el correo electrónico. Por ejemplo, si un usuario eliminó un mensaje o movió el mensaje a archivo/pst, no se actualizará la ubicación de entrega del mensaje. Pero si una acción del sistema actualizó la ubicación (por ejemplo, ZAP que da como resultado un mensaje de correo electrónico que se mueve a cuarentena), la **Ubicación de entrega más reciente** aparecería como "cuarentena".

> [!div class="mx-imgBorder"]
> ![Ubicaciones de entrega actualizadas](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Hay algunos casos en los que la **Ubicación de entrega** y la acción de **entrega** podrían mostrarse como "desconocido":
>
> - Puede ver la **Ubicación de entrega** como "entregado" y la **Ubicación de entrega** como "desconocido" si el mensaje se entregó, pero una regla de la bandeja de entrada movió el mensaje a una carpeta predeterminada (como borrador o archivo) en lugar de a la bandeja de entrada o a la carpeta de correo electrónico no deseado.
>
> - La **última ubicación de entrega** puede ser desconocida si se ha intentado realizar una acción del administrador o del sistema (como ZAP), pero no se ha encontrado el mensaje. Normalmente, la acción se produce después de que el usuario haya movido o eliminado el mensaje. En estos casos, Compruebe la columna **resultado/detalles** en la vista escala de tiempo. Busque la instrucción "el mensaje movió o eliminó el usuario".

> [!div class="mx-imgBorder"]
> ![Ubicaciones de entrega para la escala de tiempo](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Acciones adicionales

Se aplicaron *acciones adicionales* tras la entrega del correo electrónico. Pueden incluir *Zap*, *corrección manual* (acción emprendida por un administrador, como eliminación temporal), *entrega dinámica* y *reprocesamiento* (para un correo electrónico que se haya detectado como bueno de forma retroactiva).

> [!NOTE]
> - Como parte de los cambios pendientes, el valor "quitado por ZAP" que actualmente se encuentra en el filtro de acción de entrega está desaparecedo. Tendrá una forma de buscar todo el correo electrónico con el intento de ZAP a través de **acciones adicionales**.
>
> - Habrá nuevos campos y valores para tecnologías de **detección** y **acciones adicionales** (especialmente para los escenarios de ZAP). Deberá evaluar las consultas guardadas y las consultas de seguimiento existentes para asegurarse de que funcionan con los nuevos valores.

> [!div class="mx-imgBorder"]

> ![Acciones adicionales en el explorador](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Invalidaciones del sistema

Las *invalidaciones del sistema* le permiten hacer excepciones a la ubicación de entrega prevista de un mensaje. Reemplace la ubicación de entrega proporcionada por el sistema, en función de las amenazas y otras detecciones identificadas por la pila de filtros. Las invalidaciones del sistema se pueden establecer a través de la Directiva de inquilino o usuario para entregar el mensaje como lo sugiere la Directiva. Las invalidaciones pueden identificar la entrega involuntaria de mensajes malintencionados debido a una brecha de configuración, como una directiva de remitentes seguros demasiado amplia establecida por un usuario. Estos valores de reemplazo pueden ser:

- Permitido por la Directiva de usuario: un usuario crea directivas en el nivel de buzón para permitir dominios o remitentes.
- Bloqueado por la Directiva de usuario: un usuario crea directivas en el nivel de buzón de correo para bloquear dominios o remitentes.
- Permitido por la Directiva de la organización: los equipos de seguridad de la organización establecen directivas o reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) para permitir a los remitentes y dominios para los usuarios de su organización. Esto puede ser para un conjunto de usuarios o para toda la organización.
- Bloqueado por la Directiva de la organización: los equipos de seguridad de la organización establecen directivas o reglas de flujo de correo para bloquear a los usuarios de su organización los remitentes, dominios, idiomas de mensajes o direcciones IP de origen. Esto puede aplicarse a un conjunto de usuarios o a toda la organización.
- Extensión de archivo bloqueada por la Directiva de la organización: el equipo de seguridad de una organización bloquea una extensión de nombre de archivo mediante la configuración de la Directiva antimalware. Estos valores se mostrarán ahora en detalles de correo electrónico para ayudar con las investigaciones. Secops Teams también puede usar la funcionalidad de filtrado enriquecido para filtrar las extensiones de archivo bloqueadas.

[![Invalidaciones del sistema en el explorador](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![El sistema invalida la cuadrícula en el explorador](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Mejoras para la dirección URL y la experiencia de clics

Las mejoras incluyen:

- Muestra la dirección URL completa de clics (incluidos los parámetros de consulta que forman parte de la dirección URL) en la sección **clics** del elemento emergente de dirección URL. Actualmente, el dominio y la ruta de acceso de la dirección URL aparecen en la barra de título. Esta información se amplía para mostrar la dirección URL completa.

- Correcciones a través de filtros de direcciones URL (*dirección URL* *frente a dominio* *y ruta* de direcciones URL): las actualizaciones afectan a la búsqueda de mensajes que contienen un veredicto de URL o clic. Hemos habilitado la compatibilidad con las búsquedas de protocolos independientes, por lo que puede buscar una dirección URL sin usar `http` . De forma predeterminada, la búsqueda de direcciones URL se asigna a http, a menos que se especifique otro valor explícitamente. Por ejemplo:

   -  Busque con y sin el `http://` prefijo en los campos **URL**, **dominio** de dirección URL y dominio de dirección URL y filtro de **ruta de acceso** . Las búsquedas deben mostrar los mismos resultados.

   -  Busque el `https://` prefijo en **URL**. Si no se especifica ningún valor, `http://` se presupone el prefijo.

   - `/` se omite al principio y al final de los campos **ruta de dirección URL**, **dominio** de dirección URL, **dominio de dirección URL y ruta de acceso** . `/` al final del campo **dirección URL** se omite.

### <a name="phish-confidence-level"></a>Nivel de confianza de phish

Nivel de confianza de phish ayuda a identificar el grado de confianza con el que un correo electrónico se ha clasificado como "phish". Los dos valores posibles son *alta* y *normal*. En las fases iniciales, este filtro solo estará disponible en la vista phish del explorador de amenazas.

[![Nivel de confianza de phish en el explorador](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Señal de dirección URL ZAP

La señal de dirección URL de ZAP suele usarse en escenarios de alerta de phish en los que un correo electrónico se identificó como phish y se quitó tras la entrega. Esta señal conecta la alerta con los resultados correspondientes en el explorador. Es una de las IOCs de la alerta.

Para mejorar el proceso de búsqueda, hemos actualizado las detecciones en tiempo real y el explorador de amenazas para que la experiencia de búsqueda sea más coherente. Los cambios se describen a continuación:

- [Mejoras en la zona horaria](#timezone-improvements)
- [Actualizar en el proceso de actualización](#update-in-the-refresh-process)
- [Desglose del gráfico para agregar a los filtros](#chart-drilldown-to-add-to-filters)
- [En actualizaciones de información del producto](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrar por etiquetas de usuario

Ahora puede ordenar y filtrar por etiquetas de usuario personalizadas o del sistema para captar rápidamente el ámbito de las amenazas. Para obtener más información, consulte [User Tags](user-tags.md).

> [!IMPORTANT]
> El filtrado y la ordenación por etiquetas de usuario se encuentra actualmente en versión preliminar pública. Esta funcionalidad se puede modificar de forma sustancial antes de su lanzamiento comercial. Microsoft no ofrece ninguna garantía, expresa o implícita, con respecto a la información que se proporciona a continuación.

![Columna de etiquetas en el explorador](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Mejoras en la zona horaria

Verá la zona horaria de los registros de correo electrónico del portal y de los datos exportados. Será visible en todas las experiencias como cuadrícula de correo electrónico, flotante de detalles, escala de tiempo de correo electrónico y correos electrónicos similares, por lo que la zona horaria del conjunto de resultados está desactivada.

> [!div class="mx-imgBorder"]
> ![Ver la zona horaria en el explorador](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Actualizar en el proceso de actualización

Algunos usuarios han comentado la confusión con la actualización automática (por ejemplo, tan pronto como cambie la fecha, la página se actualiza) y la actualización manual (para otros filtros). De forma similar, quitar los filtros conduce a la actualización automática. Cambiar los filtros mientras se modifica la consulta puede provocar experiencias de búsqueda incoherentes. Para resolver estos problemas, estamos cambiando a un mecanismo de filtrado manual.

Desde el punto de vista de la experiencia, el usuario puede aplicar y quitar el intervalo de filtros diferente (desde el conjunto de filtros y la fecha) y seleccionar el botón actualizar para filtrar los resultados después de haber definido la consulta. El botón Actualizar ahora también se enfatiza en la pantalla. También hemos actualizado la información sobre herramientas relacionada y la documentación del producto.

> [!div class="mx-imgBorder"]
> ![Seleccione actualizar para filtrar resultados](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Desglose del gráfico para agregar a los filtros

Ahora puede representar los valores de leyenda para agregarlos como filtros. Seleccione el botón **Actualizar** para filtrar los resultados.

> [!div class="mx-imgBorder"]
> ![Explorar en profundidad los gráficos para filtrar](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Actualizaciones de información del producto

Ahora hay disponibles detalles adicionales en el producto, como el número total de resultados de búsqueda dentro de la cuadrícula (vea a continuación). Hemos mejorado las etiquetas, los mensajes de error y la información sobre herramientas para proporcionar más información sobre los filtros, la experiencia de búsqueda y el conjunto de resultados.

> [!div class="mx-imgBorder"]
> ![Ver información del producto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Capacidades extendidas en el explorador de amenazas

### <a name="top-targeted-users"></a>Usuarios de destino principales

En la actualidad, exponemos la lista de los usuarios de destino más importantes en la vista de malware para los correos electrónicos en la sección **principales familias de malware** . Esta vista se ampliará también en el phish y en todas las vistas de correo electrónico. Podrá ver los principales cinco usuarios de destino, junto con el número de intentos de cada usuario para la vista correspondiente. Por ejemplo, para la vista phish, verá el número de intentos de phish.

Podrá exportar la lista de usuarios de destino, hasta un máximo de 3.000, junto con el número de intentos de análisis sin conexión para cada vista de correo electrónico. Además, al seleccionar el número de intentos (por ejemplo, 13 intentos en la imagen siguiente), se abrirá una vista filtrada en el explorador de amenazas, para que pueda ver más detalles de los mensajes de correo electrónico y las amenazas de ese usuario.

> [!div class="mx-imgBorder"]
> ![Usuarios de destino principales](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Reglas de transporte de Exchange

Como parte del enriquecimiento de datos, podrá ver todas las diferentes reglas de transporte de Exchange (ETR) que se aplicaron a un mensaje. Esta información estará disponible en la vista de cuadrícula de correo electrónico. Para verla, seleccione **Opciones de columna** en la cuadrícula y, a continuación, **Agregar regla de transporte de Exchange** desde las opciones de columna. También estará visible en el control flotante en los **detalles** del correo electrónico.

Podrá ver el GUID y el nombre de las reglas de transporte que se han aplicado al mensaje. Podrá buscar los mensajes con el nombre de la regla de transporte. Se trata de una búsqueda de "contiene", lo que significa que también puede realizar búsquedas parciales.

#### <a name="important-note"></a>Nota importante:

La búsqueda y la disponibilidad de nombres de ETR dependen del rol específico que se le haya asignado. Debe disponer de uno de los siguientes roles o permisos para ver los nombres y la búsqueda de ETR. Si no tiene ninguno de estos roles asignados a usted, no podrá ver los nombres de las reglas de transporte ni buscar mensajes con nombres ETR. Sin embargo, puede ver la etiqueta ETR y la información de GUID en los detalles de correo electrónico. Otras experiencias de visualización de registros en las cuadrículas de correo electrónico, los controles flotantes de correo electrónico, los filtros y la exportación no se ven afectadas.

- Solo EXO-prevención de pérdida de datos: ALL
- Solo EXO-O365SupportViewConfig: ALL
- Microsoft Azure Active Directory o EXO-Security admin: ALL
- AAD o EXO-Security Reader: ALL
- Solo EXO-reglas de transporte: todas
- Solo EXO-configuración View-Only: ALL

Dentro de la cuadrícula de correo electrónico, los detalles flotantes y el archivo CSV exportado, el ETR se presenta con un nombre/GUID, tal como se muestra a continuación.

> [!div class="mx-imgBorder"]
> ![Reglas de transporte de Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Conectores de entrada

Los conectores son una colección de instrucciones que personalizan el modo en que el correo electrónico fluye hacia y desde la organización de Microsoft 365 u Office 365. Permiten aplicar cualquier restricción o control de seguridad. En el explorador de amenazas, ahora puede ver los conectores que están relacionados con un correo electrónico y buscar correos electrónicos con los nombres de los conectores.

La búsqueda de conectores es "contiene" en su naturaleza, lo que significa que las búsquedas de palabras clave parciales también deben funcionar. En la vista de cuadrícula principal, el control flotante de detalles y el archivo CSV exportado, los conectores se muestran en el formato nombre/GUID como se muestra a continuación:

> [!div class="mx-imgBorder"]
> ![Detalles del conector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuevas características del explorador de amenazas y detecciones en tiempo real

Hay tres nuevas características disponibles en el explorador de amenazas y en detecciones en tiempo real:

- [Vista previa del encabezado de correo electrónico y descarga del cuerpo](#preview-email-header-and-download-email-body)
- [Escala de tiempo de correo electrónico](#email-timeline)
- [Exportar dirección URL haga clic en datos](#export-url-click-data)

Estas nuevas características se describen a continuación.

### <a name="preview-email-header-and-download-email-body"></a>Vista previa del encabezado de correo electrónico y descarga del cuerpo

Ahora puede obtener una vista previa de un encabezado de correo electrónico y descargar el cuerpo del correo electrónico en el explorador de amenazas los administradores pueden analizar los encabezados y mensajes de correo electrónico descargados en busca de amenazas. Como la descarga de mensajes de correo electrónico puede arriesgar la exposición de la información, este proceso se controla mediante el control de acceso basado en roles (RBAC). Un nuevo rol, *vista previa*, debe agregarse a otro grupo de roles (como operaciones de seguridad o administrador de seguridad) para poder descargar los correos electrónicos y obtener una vista previa de los encabezados en la vista de todos los mensajes de correo electrónico.

El explorador y las detecciones en tiempo real también obtendrán nuevos campos que proporcionan una imagen más completa de dónde se encuentran los mensajes de correo electrónico. Estos cambios hacen que la búsqueda resulte más sencilla para las operaciones de seguridad. Pero el resultado principal es que puede conocer la ubicación de los mensajes de correo electrónico con problemas de un vistazo.

¿Cómo se hace esto? El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : estado del correo electrónico.
- **Ubicación de entrega** : donde se enrutó el correo electrónico.

La *acción de entrega* es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones para un correo electrónico:

|Pronuncia|Correo electrónico no deseado|Blocked|Sustitui|
|---|---|---|---|
|El correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él.|El correo electrónico se envió a la carpeta de correo no deseado o eliminada del usuario y el usuario puede tener acceso a él.|Mensajes de correo electrónico que se han puesto en cuarentena, erróneos o se han perdido. Estos mensajes son inaccesibles para el usuario.|Los mensajes de correo electrónico con datos adjuntos malintencionados reemplazados por archivos. txt que indican que el archivo adjunto era malintencionado.|

Esto es lo que el usuario puede ver y no puede ver:

|Accesible para los usuarios finales|Inaccesibles para los usuarios finales|
|---|---|
|Pronuncia|Blocked|
|Correo electrónico no deseado|Sustitui|

**Ubicación de entrega** muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a **_acción de entrega_* _. Estos son los valores posibles:

- _Inbox o carpeta *: el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
- *Local o externa*: el buzón no existe en la nube pero es local.
- *Carpeta de correo no deseado*: el correo electrónico se encuentra en la carpeta de correo no deseado del usuario.
- *Carpeta elementos eliminados*: el correo electrónico en la carpeta elementos eliminados de un usuario.
- *Quarantine*: el correo electrónico está en cuarentena y no en el buzón de un usuario.
- *Error*: el correo electrónico no pudo llegar al buzón.
- *Quitado*: el correo electrónico se perdió en algún lugar del flujo de correo.

### <a name="email-timeline"></a>Escala de tiempo de correo electrónico

La **escala de tiempo de correo electrónico** es una nueva característica del explorador que mejora la experiencia de búsqueda para administradores. Reduce el tiempo dedicado a comprobar diferentes ubicaciones para tratar de comprender el evento. Cuando se producen varios eventos en o cerca de la misma vez que recibe un mensaje de correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos eventos que se producen en la entrega de correo electrónico se capturan en la columna **acción especial** . Los administradores pueden combinar información de la escala de tiempo con la acción especial que se lleva a cabo en la entrega de correo electrónico para conocer el funcionamiento de sus directivas, donde el correo se enrutó finalmente y, en algunos casos, cuál era la evaluación final.

Para obtener más información, consulte [investigar y corregir el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportar dirección URL haga clic en datos

Ahora puede exportar informes para los clics de URL a Microsoft Excel para ver su **identificador de mensaje de red** y **hacer clic en el veredicto**, que ayuda a explicar dónde se originó la URL haga clic en el tráfico. Esto es lo que funciona: en administración de amenazas en la barra de inicio rápido de Office 365, siga esta cadena:

**Explorador** \> **Ver phish** \> **Hace clic en** \> **Direcciones URL principales** o **clics principales** \> Seleccione cualquier registro para abrir el control flotante de dirección URL.

Cuando seleccione una dirección URL de la lista, verá un nuevo botón **exportar** en el panel desplegable. Use este botón para mover datos a una hoja de cálculo de Excel para facilitar la creación de informes.

Siga esta ruta de acceso para ir a la misma ubicación en el informe de detecciones en tiempo real:

**Explorador** \> Detecciones en tiempo **real** \> **Ver phish** \> **Direcciones URL** \> **Direcciones URL principales** o **principales clics** \> Seleccione cualquier registro para abrir el control flotante de dirección URL, \> Desplácese hasta la pestaña **clics** .

> [!TIP]
> El identificador de mensaje de red asigna el clic de nuevo a los mensajes específicos cuando se realiza una búsqueda en el identificador a través del explorador o con herramientas de terceros asociadas. Estas búsquedas identifican el correo electrónico asociado con un resultado de clic. Tener el identificador de mensaje de red correlacionado facilita un análisis más rápido y eficaz.

> [!div class="mx-imgBorder"]
> ![Pestañas en el explorador](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en correo electrónico por tecnología

Supongamos que desea ver el malware detectado en un correo electrónico ordenado por la tecnología de Microsoft 365. Para ello, use la vista [Email > malware](threat-explorer-views.md#email--malware) de Explorer (o detecciones en tiempo real).

1. En el centro de seguridad & cumplimiento ( <https://protection.office.com> ), elija **Threat Management** \> **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija malware de **correo electrónico** \> .

   > [!div class="mx-imgBorder"]
   > ![Menú Ver para el explorador](../../media/ExplorerViewEmailMalwareMenu.png)

3. Haga clic en **remitente** y, a continuación, elija tecnología de  \> **detección** básica.

   Las tecnologías de detección están ahora disponibles como filtros para el informe.

   > [!div class="mx-imgBorder"]
   > ![Tecnologías de detección de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Elija una opción. A continuación, seleccione el botón **Actualizar** para aplicar ese filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnología de detección seleccionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

El informe se actualiza para mostrar los resultados del malware detectados en el correo electrónico, usando la opción de tecnología seleccionada. Desde aquí, puede realizar análisis adicionales.

## <a name="view-phishing-url-and-click-verdict-data"></a>Ver la dirección URL de phishing y hacer clic en datos de veredicto

Supongamos que desea ver los intentos de suplantación de identidad mediante direcciones URL en el correo electrónico, incluida una lista de direcciones URL que se han permitido, bloqueado y reemplazado. Para identificar las direcciones URL en las que se hizo clic, se deben configurar [vínculos seguros](atp-safe-links.md) . Asegúrese de configurar [directivas de vínculos seguros](set-up-atp-safe-links-policies.md) para la protección del tiempo de clic y el registro de los veredictos de clics por vínculos seguros.

Para revisar direcciones URL de phish en mensajes y hacer clic en direcciones URL en mensajes de Phish, use la vista [  >  **phish** de **correo electrónico**](threat-explorer-views.md#email--phish) del explorador o detecciones en tiempo real.

1. En el centro de seguridad & cumplimiento ( <https://protection.office.com> ), elija **Threat Management** \> **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija phishing de **correo electrónico** \> .

   > [!div class="mx-imgBorder"]
   > ![Ver el menú del explorador en el contexto de suplantación de identidad](../../media/ExplorerViewEmailPhishMenu.png)

3. Haga clic en **remitente** y, a continuación, elija **direcciones URL** , \> **haga clic en veredicto**.

4. Seleccione una o más opciones, como **bloqueada** y **bloque invalidado** y, a continuación, seleccione el botón **Actualizar** en la misma línea que las opciones para aplicar ese filtro. (No actualice la ventana del explorador).

   > [!div class="mx-imgBorder"]
   > ![Direcciones URL y haga clic en veredictos](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la ficha dirección URL del informe:

   - Las **direcciones URL principales** son las direcciones URL de los mensajes que ha filtrado y el número de acciones de entrega de correo electrónico para cada dirección URL. En la vista correo phish, esta lista suele contener direcciones URL legítimas. Los atacantes incluyen una mezcla de direcciones URL buenas y incorrectas en sus mensajes para intentar entregarlos, pero hacen que los vínculos malintencionados tengan un aspecto más interesante. La tabla de direcciones URL se ordena por el recuento de correo electrónico total, pero esta columna está oculta para simplificar la vista.

   - Los **clics principales** son las direcciones URL ajustadas para vínculos seguros en las que se hizo clic, ordenadas por el número total de clics. Esta columna tampoco se muestra, para simplificar la vista. Número total de recuentos por columna indique los vínculos seguros haga clic en recuento de veredictos para cada dirección URL con clic. En la vista de correo phish, suelen ser direcciones URL malintencionadas o sospechosas. Pero la vista podría incluir direcciones URL que no son amenazas pero están en mensajes de phish. Los clics de dirección URL en vínculos desajustados no se muestran aquí.

   Las dos tablas de direcciones URL muestran direcciones URL principales en los mensajes de correo electrónico de suplantación por acción y ubicación de entrega. Las tablas muestran los clics en direcciones URL que se bloquearon o visitaron a pesar de una advertencia, de modo que pueda ver qué posibles vínculos no válidos se presentaron a los usuarios y que se hizo clic en el usuario. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico puede ver las direcciones URL principales en los mensajes de correo electrónico que estaban bloqueados en el entorno de su organización.

   > [!div class="mx-imgBorder"]
   > ![URL del explorador que se bloquearon](../../media/ExplorerPhishClickVerdictURLs.png)

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo flotante de URL, se quita el filtrado de los mensajes de correo electrónico para mostrar la vista completa de la exposición de la dirección URL en el entorno. Esto le permite filtrar los mensajes de correo electrónico que le interesan en el explorador, buscar direcciones URL específicas que sean posibles amenazas y, a continuación, expandir su comprensión de la exposición de URL en su entorno (a través del cuadro de diálogo Detalles de dirección URL) sin tener que agregar filtros de dirección URL a la vista del explorador.

### <a name="interpretation-of-click-verdicts"></a>Interpretación de los veredictos de clics

En los controles flotantes de correo electrónico o dirección URL, los clics principales, así como en nuestras experiencias de filtrado, verá distintos valores de veredicto de clics:

- **None:** No se puede capturar el veredicto para la dirección URL. Es posible que el usuario haya acpulsado a través de la dirección URL.
- **Permitido:** Se ha permitido al usuario navegar a la dirección URL.
- **Bloqueado:** Se ha bloqueado al usuario para que navegue a la dirección URL.
- **Veredicto pendiente:** Se presentó al usuario la página pendiente de detonación.
- **Bloqueado invalidado:** El usuario no se pudo navegar directamente a la dirección URL. Pero el usuario overrode? el bloque para desplazarse a la dirección URL.
- Se **omite el veredicto pendiente:** Se presentó al usuario la página de detonación. Pero el usuario overrode? el mensaje para obtener acceso a la dirección URL.
- **Error:** Se presentó al usuario la página de error o se produjo un error al capturar el veredicto.
- **Error:** Se produjo una excepción desconocida al capturar el veredicto. Es posible que el usuario haya acpulsado a través de la dirección URL.

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico enviados por los usuarios

Supongamos que desea ver los mensajes de correo electrónico que los usuarios de su organización han notificado como *correo* no deseado, correo *deseado* o *suplantación de identidad* mediante el [complemento de mensajes de informe para Outlook y Outlook en la web](enable-the-report-message-add-in.md). Para verlos, use la vista [  >  **envíos** **por correo electrónico**](threat-explorer-views.md#email--submissions) del explorador (o detecciones en tiempo real).

1. En el centro de seguridad & cumplimiento ( <https://protection.office.com> ), elija **Threat Management** \> **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija  \> **envíos** de correo electrónico.

   > [!div class="mx-imgBorder"]
   > ![Menú Ver para el explorador de correo electrónico](../../media/explorer-view-menu-email-user-reported.png)

3. Haga clic en **remitente** y, a continuación, elija tipo de  \> **Informe** básico.

4. Seleccione una opción, como **phish** y, a continuación, seleccione el botón **Actualizar** .

   > [!div class="mx-imgBorder"]
   > ![Phish notificados por el usuario](../../media/EmailUserReportedReportType.png)

El informe se actualiza para Mostrar datos sobre los mensajes de correo electrónico que los usuarios de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar las [directivas antiphishing en Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Iniciar investigación y respuesta automatizadas

> [!NOTE]
> Las capacidades de investigación y respuesta automatizadas están disponibles en *Microsoft defender para office 365 plan 2* y *Office 365 E5*.

La [investigación y la respuesta automatizadas](automated-investigation-response-office.md) pueden ahorrar tiempo al equipo de operaciones de seguridad y esfuerzo dedican a investigar y mitigar cyberattacks. Además de configurar alertas que pueden desencadenar una guía de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador. Para obtener más información, consulte [ejemplo: un administrador de seguridad desencadena una investigación desde el explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Más formas de usar Explorer y detecciones en tiempo real

Además de los escenarios descritos en este artículo, tiene muchas más opciones de informes disponibles con el explorador (o detecciones en tiempo real). Consulte los siguientes artículos:

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obtener información general sobre las vistas en el explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft defender para Office 365](office-365-atp.md) para usar el explorador o detección en tiempo real.

- Explorer se incluye en defender para Office 365 plan 2.
- El informe de detecciones en tiempo real se incluye en defender para Office 365 plan 1.
- Planee la asignación de licencias para todos los usuarios que deban estar protegidos por defender para Office 365. El explorador y las detecciones en tiempo real muestran los datos de detección de los usuarios con licencia.

Para ver y usar el explorador o las detecciones en tiempo real, debe tener los permisos adecuados, como los que se han concedido a un administrador de seguridad o un lector de seguridad.

- Para el centro de seguridad & cumplimiento, debe tener asignada una de las siguientes funciones:

  - Administración de la organización
  - Administrador de seguridad (puede asignarse en el centro de administración de Azure Active Directory ( <https://aad.portal.azure.com> )
  - Lector de seguridad

- Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange ( <https://admin.protection.outlook.com/ecp/> ) o [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):

  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información acerca de los roles y los permisos, vea los siguientes recursos:

- [Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)
- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferencias entre el explorador de amenazas y las detecciones en tiempo real

- El informe de *detecciones en tiempo real* está disponible en defender para Office 365 plan 1. El *Explorador de amenazas* está disponible en defender para Office 365 plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El explorador de amenazas hace esto también, pero también proporciona detalles adicionales para un ataque determinado.
- La vista *todo el correo electrónico* está disponible en el explorador de amenazas, pero no en el informe de detecciones en tiempo real.
- En el explorador de amenazas se incluyen más funciones de filtrado y acciones disponibles. Para obtener más información, vea [Descripción del servicio de Microsoft defender para office 365: disponibilidad de características en los planes de defender para office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
