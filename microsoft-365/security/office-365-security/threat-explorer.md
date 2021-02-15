---
title: Explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use las detecciones en tiempo real y del Explorador en el Centro de cumplimiento de seguridad para investigar y &amp; responder a las amenazas de forma eficaz.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c07ea4a44eb965ab6df834260c9dcef6e79c02a
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142330"
---
# <a name="threat-explorer-and-real-time-detections"></a>Explorador de amenazas y detecciones en tiempo real


**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si su organización tiene Microsoft Defender para Office [365](office-365-atp.md)y tiene los permisos necesarios, tiene detecciones [](#new-features-in-threat-explorer-and-real-time-detections)en tiempo **real** o **explorer** (anteriormente informes en tiempo *real,* vea las novedades). [](#required-licenses-and-permissions) En el Centro de & cumplimiento, vaya a Administración de amenazas y, a continuación, elija  **Detecciones en** tiempo real o Explorador.  


|Con Microsoft Defender para Office 365 Plan 2, verá:|Con Microsoft Defender para Office 365 Plan 1, verá:|
|---|---|
|![Explorador de amenazas](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

Las detecciones de explorador o en tiempo real ayudan al equipo de operaciones de seguridad a investigar y responder a las amenazas de forma eficaz. El informe es similar a la imagen siguiente:

![Ir al Explorador de administración de \> amenazas](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con este informe, puede:

- [Ver malware detectado por las características de seguridad de Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en los datos del veredicto](#view-phishing-url-and-click-verdict-data)
- [Iniciar un proceso automatizado de investigación y respuesta desde una vista en el Explorador](#start-automated-investigation-and-response) (solo Defender para Office 365 Plan 2)
- [Investigar correo electrónico malintencionado y mucho más](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Mejoras en el Explorador de amenazas y las detecciones en tiempo real

### <a name="tags-in-threat-explorer"></a>Etiquetas en el Explorador de amenazas

> [!NOTE]
> La característica de etiquetas de usuario está en *versión preliminar,* no está disponible para todos los usuarios y está sujeta a cambios. Para obtener información sobre la programación de lanzamientos, consulte la guía básica de Microsoft 365.

Las etiquetas de usuario identifican grupos específicos de usuarios en Microsoft Defender para Office 365. Para obtener más información acerca de las etiquetas, incluidas las licencias y la configuración, vea [Etiquetas de usuario.](user-tags.md)

En el Explorador de amenazas, puede ver información sobre las etiquetas de usuario en las siguientes experiencias.

#### <a name="email-grid-view"></a>Vista de cuadrícula de correo electrónico

La **columna** Etiquetas de la cuadrícula de correo electrónico contiene todas las etiquetas que se han aplicado a los buzones de correo del remitente o destinatario. De forma predeterminada, las etiquetas del sistema, como las cuentas de prioridad, se muestran en primer lugar.

> [!div class="mx-imgBorder"]
> ![Filtrar etiquetas en la vista de cuadrícula de correo electrónico](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtrado

Puede usar etiquetas como filtro. Busca solo entre cuentas de prioridad o escenarios de etiquetas de usuario específicos. También puede excluir los resultados que tienen determinadas etiquetas. Combine esta funcionalidad con otros filtros para restringir el ámbito de investigación.

[![Etiquetas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Etiquetas sin filtro](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Menú desplegable de detalles de correo electrónico
Para ver las etiquetas individuales del remitente y el destinatario, seleccione el asunto para abrir el control desplegable de detalles del mensaje. En la **pestaña Resumen,** las etiquetas de remitente y destinatario se muestran por separado, si están presentes para un correo electrónico.
La información sobre las etiquetas individuales del remitente y el destinatario también se extiende a los datos CSV exportados, donde puede ver estos detalles en dos columnas independientes.

> [!div class="mx-imgBorder"]
> ![Etiquetas de detalles de correo electrónico](../../media/tags-flyout.png)

La información de etiquetas también se muestra en el control desplegable de clics de dirección URL. Para verlo, vaya a la vista Suplantación de identidad o Todo el correo electrónico y, a continuación, a la pestaña Url **o** **Clics de** url. Seleccione un control desplegable de dirección URL individual para ver detalles adicionales sobre los clics de esa dirección URL, incluidas las etiquetas asociadas con ese clic.

> [!div class="mx-imgBorder"]
> ![Etiquetas URL](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Mejoras en la experiencia de búsqueda de amenazas (próximamente)

### <a name="updated-threat-information-for-emails"></a>Información de amenazas actualizada para mensajes de correo electrónico

Nos hemos centrado en las mejoras de la plataforma y la calidad de los datos para aumentar la precisión y la coherencia de los datos para los registros de correo electrónico. Entre las mejoras se incluye la consolidación de la información de entrega previa y posterior a la entrega, como las acciones ejecutadas en un correo electrónico como parte del proceso ZAP, en un único registro. También se incluyen detalles adicionales como el veredicto de correo no deseado, las amenazas de nivel de entidad (por ejemplo, qué dirección URL era malintencionada) y las ubicaciones de entrega más recientes.

Después de estas actualizaciones, verá una sola entrada para cada mensaje, independientemente de los diferentes eventos posteriores a la entrega que afectan al mensaje. Las acciones pueden incluir ZAP, corrección manual (lo que significa acción de administrador), entrega dinámica, entre otras.

Además de mostrar amenazas de malware y phishing, verá el veredicto de correo no deseado asociado a un correo electrónico. En el correo electrónico, vea todas las amenazas asociadas con el correo electrónico junto con las tecnologías de detección correspondientes. Un correo electrónico puede tener cero, una o varias amenazas. Verá las amenazas actuales en la sección **Detalles** del menú desplegable de correo electrónico. Para varias amenazas (como malware y  phishing), el campo técnico Detección muestra la asignación de detección de amenazas, que es la tecnología de detección que identificó la amenaza.

El conjunto de tecnologías de detección ahora incluye nuevos métodos de detección, así como tecnologías de detección de correo no deseado. Puede usar el mismo conjunto de tecnologías de detección para filtrar los resultados en las distintas vistas de correo electrónico (malware, phishing, todo el correo electrónico).

> [!NOTE]
> Es posible que el análisis de veredicto no esté necesariamente vinculado a entidades. Por ejemplo, un correo electrónico puede clasificarse como suplantación de identidad o correo no deseado, pero no hay direcciones URL que se marcan con un veredicto de suplantación de identidad o correo no deseado. Esto se debe a que los filtros también evalúan el contenido y otros detalles de un correo electrónico antes de asignar un veredicto.

#### <a name="threats-in-urls"></a>Amenazas en direcciones URL

Ahora puede ver la amenaza específica de una dirección URL en la pestaña Detalles del control desplegable **de** correo electrónico. La amenaza puede ser *malware,* *phish,* *correo no deseado* o *ninguno).*

> [!div class="mx-imgBorder"]
> ![Amenazas de url](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Vista de escala de tiempo actualizada (próxima)

> [!div class="mx-imgBorder"]
> ![Vista escala de tiempo actualizada](../../media/Email_Timeline.png)

La vista escala de tiempo identifica todos los eventos de entrega y posterior a la entrega. Incluye información sobre la amenaza identificada en ese momento para un subconjunto de estos eventos. La vista escala de tiempo también proporciona información sobre cualquier acción adicional realizada (como ZAP o corrección manual), junto con el resultado de esa acción. La información de la vista escala de tiempo incluye:

- **Origen:** Origen del evento. Puede ser admin/system/user.
- **Evento:** Incluye eventos de nivel superior como entrega original, corrección manual, ZAP, envíos y entrega dinámica.
- **Acción:** La acción específica que se ha realizado como parte de la acción de ZAP o de administrador (por ejemplo, eliminación parcial).
- **Amenazas:** Cubre las amenazas (malware, phishing, correo no deseado) identificadas en ese momento.
- **Resultado/Detalles:** Más información sobre el resultado de la acción, como si se realizó como parte de la acción ZAP/admin.

### <a name="original-and-latest-delivery-location"></a>Ubicación de entrega original y más reciente

Actualmente, se muestra la ubicación de entrega en la cuadrícula de correo electrónico y el control desplegable de correo electrónico. El **campo Ubicación de** entrega cambia su nombre a Ubicación de entrega **_original_*_. Y estamos introduciendo otro campo, _*_Ubicación de entrega más reciente._**

**La ubicación de entrega original** dará más información sobre dónde se entregó un correo electrónico inicialmente. **La ubicación de entrega más** reciente mostrará dónde aterrizó un correo electrónico después de acciones del sistema como *ZAP* o acciones de administración como Mover a *elementos eliminados.* La ubicación de entrega más reciente está pensada para proporcionar a los administradores la última ubicación conocida posterior a la entrega del mensaje o cualquier acción del sistema o administrador. No incluye ninguna acción del usuario final en el correo electrónico. Por ejemplo, si un usuario eliminó un mensaje o movió el mensaje a archivo/pst, la ubicación del mensaje "entrega" no se actualizará. Pero si una acción del sistema actualiza la ubicación (por ejemplo, ZAP da como resultado un correo electrónico que pasa a **cuarentena),** la ubicación de entrega más reciente se mostrará como "cuarentena".

> [!div class="mx-imgBorder"]
> ![Ubicaciones de entrega actualizadas](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Hay algunos casos en los que la **ubicación de entrega** y la acción de **entrega** pueden mostrarse como "desconocidas":
>
> - Es posible  que vea la  ubicación de entrega como "entregado" y la ubicación de entrega como "desconocida" si el mensaje se entregó, pero una regla de bandeja de entrada movió el mensaje a una carpeta predeterminada (como Borrador o Archivo) en lugar de a la carpeta Bandeja de entrada o Correo no deseado.
>
> - **La ubicación de entrega más** reciente puede ser desconocida si se intentó realizar una acción de administrador o sistema (como ZAP), pero no se encontró el mensaje. Normalmente, la acción se produce después de que el usuario haya movido o eliminado el mensaje. En estos casos, compruebe la columna **Resultado/Detalles** en la vista escala de tiempo. Busque la instrucción "El usuario movió o eliminó el mensaje".

> [!div class="mx-imgBorder"]
> ![Ubicaciones de entrega para escala de tiempo](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Acciones adicionales

*Se aplicaron* acciones adicionales después de la entrega del correo electrónico. Pueden incluir *ZAP,* corrección *manual* (acción realizada por un administrador como eliminación *temporal),* entrega dinámica y *reprocesamiento* (para un correo electrónico que se detectó retroactivamente como correcto).

> [!NOTE]
> - Como parte de los cambios pendientes, el valor "Quitado por ZAP" que se muestra actualmente en el filtro acción de entrega va a desaparecer. You'll have a way to search for all email with the ZAP attempt through **Additional actions**.
>
> - Habrá nuevos campos y valores para las tecnologías **de** detección y **acciones adicionales** (especialmente para escenarios ZAP). Deberá evaluar las consultas guardadas existentes y las consultas de seguimiento para asegurarse de que funcionan con los nuevos valores.

> [!div class="mx-imgBorder"]

> ![Acciones adicionales en el Explorador](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Invalidaciones del sistema

*Las invalidaciones del* sistema permiten realizar excepciones en la ubicación de entrega prevista de un mensaje. Se reemplaza la ubicación de entrega proporcionada por el sistema, en función de las amenazas y otras detecciones identificadas por la pila de filtrado. Los reemplazos del sistema se pueden establecer a través de la directiva de usuario o inquilino para entregar el mensaje según lo sugerido por la directiva. Los reemplazos pueden identificar la entrega no intencionada de mensajes malintencionados debido a diferencias de configuraciones, como una directiva de remitente seguro demasiado amplia establecida por un usuario. Estos valores de invalidación pueden ser:

- Permitido por la directiva de usuario: un usuario crea directivas en el nivel de buzón para permitir dominios o remitentes.
- Bloqueado por la directiva de usuario: un usuario crea directivas en el nivel de cuadro de correo para bloquear dominios o remitentes.
- Permitido por la directiva de la organización: los equipos de seguridad de la organización establecen directivas o reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) para permitir remitentes y dominios para los usuarios de su organización. Puede ser para un conjunto de usuarios o para toda la organización.
- Bloqueados por la directiva de la organización: los equipos de seguridad de la organización establecen directivas o reglas de flujo de correo para bloquear remitentes, dominios, idiomas de mensajes o direcciones IP de origen para los usuarios de su organización. Esto se puede aplicar a un conjunto de usuarios o a toda la organización.
- Extensión de archivo bloqueada por la directiva de la organización: el equipo de seguridad de una organización bloquea una extensión de nombre de archivo a través de la configuración de directiva antimalware. Estos valores ahora se mostrarán en los detalles del correo electrónico para ayudar con las investigaciones. Los equipos de Secops también pueden usar la capacidad de filtrado enriquecido para filtrar por extensiones de archivo bloqueadas.

[![Invalidaciones del sistema en el Explorador](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Sistema invalida la cuadrícula en el Explorador](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Mejoras para la experiencia de url y clics

Entre las mejoras se incluyen:

- Muestra la dirección URL con clics completos (incluidos los parámetros de consulta que forman parte de la dirección URL) en la sección **Clics** del control desplegable url. Actualmente, el dominio de dirección URL y la ruta de acceso aparecen en la barra de título. Estamos ampliando esa información para mostrar la dirección URL completa.

- Correcciones entre filtros de dirección *URL* (dirección *URL* frente a dominio de dirección *URL* frente a dominio y ruta de acceso url): las actualizaciones afectan a la búsqueda de mensajes que contienen un veredicto de dirección URL/clic. Habilitamos la compatibilidad con búsquedas independientes del protocolo, por lo que puede buscar una dirección URL sin usar `http` . De forma predeterminada, la búsqueda de dirección URL se asigna a http, a menos que se especifique explícitamente otro valor. Por ejemplo:

   -  Busque con y sin el prefijo en los campos de filtro Dirección URL, Dominio de dirección URL y `http://` Dominio y Ruta de acceso de la dirección **URL.**   Las búsquedas deben mostrar los mismos resultados.

   -  Busque el `https://` prefijo en la dirección **URL.** Cuando no se especifica ningún valor, se `http://` asume el prefijo.

   - `/` se omite al principio y al final de los campos de ruta de acceso **url,** dominio de dirección **URL,** dominio de dirección **URL y ruta de** acceso. `/` al final del campo **dirección URL** se omite.

### <a name="phish-confidence-level"></a>Nivel de confianza de suplantación de identidad

El nivel de confianza de suplantación de identidad ayuda a identificar el grado de confianza con el que se clasificó un correo electrónico como "phishing". Los dos valores posibles *son High* y *Normal*. En las fases iniciales, este filtro solo estará disponible en la vista de suplantación de identidad del Explorador de amenazas.

[![Nivel de confianza de suplantación de identidad en el Explorador](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Señal de DIRECCIÓN URL de ZAP

La señal de dirección URL de ZAP se usa normalmente para escenarios de alerta de suplantación de identidad ZAP en los que un correo electrónico se identificó como phishing y se quitó después de la entrega. Esta señal conecta la alerta con los resultados correspondientes en el Explorador. Es uno de los IIC de la alerta.

Para mejorar el proceso de búsqueda, hemos actualizado el Explorador de amenazas y las detecciones en tiempo real para que la experiencia de búsqueda sea más coherente. Los cambios se describen aquí:

- [Mejoras en la zona horaria](#timezone-improvements)
- [Actualización en el proceso de actualización](#update-in-the-refresh-process)
- [Obtención de detalles del gráfico para agregar a filtros](#chart-drilldown-to-add-to-filters)
- [En las actualizaciones de información del producto](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrar por etiquetas de usuario

Ahora puede ordenar y filtrar las etiquetas de usuario personalizadas o del sistema para comprender rápidamente el ámbito de las amenazas. Para obtener más información, vea [Etiquetas de usuario.](user-tags.md)

> [!IMPORTANT]
> El filtrado y la ordenación por etiquetas de usuario se encuentra actualmente en versión preliminar pública. Esta funcionalidad puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece ninguna garantía, expresa o implícita, con respecto a la información proporcionada al respecto.

![Columna Etiquetas en el Explorador](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Mejoras en la zona horaria

Verá la zona horaria para los registros de correo electrónico en el portal, así como para los datos exportados. Estará visible en experiencias como Cuadrícula de correo electrónico, Control de detalles, Escala de tiempo de correo electrónico y Correos electrónicos similares, por lo que la zona horaria del conjunto de resultados es clara.

> [!div class="mx-imgBorder"]
> ![Ver zona horaria en el Explorador](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Actualización en el proceso de actualización

Algunos usuarios han comentado confusión con la actualización automática (por ejemplo, en cuanto cambia la fecha, la página se actualiza) y la actualización manual (para otros filtros). De forma similar, la eliminación de filtros conduce a la actualización automática. El cambio de filtros al modificar la consulta puede provocar experiencias de búsqueda incoherentes. Para resolver estos problemas, estamos pasando a un mecanismo de filtrado manual.

Desde el punto de vista de la experiencia, el usuario puede aplicar y quitar los distintos intervalos de filtros (del conjunto de filtros y la fecha) y seleccionar el botón actualizar para filtrar los resultados después de haber definido la consulta. El botón de actualización también se resalta ahora en la pantalla. También hemos actualizado la información sobre herramientas relacionada y la documentación del producto.

> [!div class="mx-imgBorder"]
> ![Seleccionar Actualizar para filtrar resultados](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Obtención de detalles del gráfico para agregar a filtros

Ahora puede crear gráficos de valores de leyenda para agregarlos como filtros. Seleccione el **botón Actualizar** para filtrar los resultados.

> [!div class="mx-imgBorder"]
> ![Explorar en profundidad los gráficos para filtrar](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Actualizaciones de información del producto

Ahora hay detalles adicionales disponibles en el producto, como el número total de resultados de búsqueda dentro de la cuadrícula (vea a continuación). Hemos mejorado las etiquetas, los mensajes de error y la información sobre herramientas para proporcionar más información sobre los filtros, la experiencia de búsqueda y el conjunto de resultados.

> [!div class="mx-imgBorder"]
> ![Ver información del producto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Funcionalidades extendidas en el Explorador de amenazas

### <a name="top-targeted-users"></a>Principales usuarios de destino

Hoy exponemos la lista de los principales usuarios de destino en la vista Malware de los correos electrónicos, en la sección Principales familias **de malware.** También ampliaremos esta vista en las vistas Suplantación de identidad y Todo el correo electrónico. Podrás ver los cinco primeros usuarios de destino, junto con el número de intentos de cada usuario para la vista correspondiente. Por ejemplo, para la vista de suplantación de identidad, verá el número de intentos de suplantación de identidad.

Podrá exportar la lista de usuarios de destino, hasta un límite de 3.000, junto con el número de intentos de análisis sin conexión para cada vista de correo electrónico. Además, al seleccionar el número de intentos (por ejemplo, 13 intentos en la imagen siguiente) se abrirá una vista filtrada en el Explorador de amenazas, para que pueda ver más detalles entre correos electrónicos y amenazas para ese usuario.

> [!div class="mx-imgBorder"]
> ![Principales usuarios de destino](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Reglas de transporte de Exchange

Como parte del enriquecimiento de datos, podrá ver todas las diferentes reglas de transporte de Exchange (ETR) que se aplicaron a un mensaje. Esta información estará disponible en la vista Cuadrícula de correo electrónico. Para verlo, seleccione **Opciones de columna en** la cuadrícula y, a continuación, Agregue regla de transporte de **Exchange** desde las opciones de columna. También estará visible en el menú **desplegable** Detalles del correo electrónico.

Podrá ver tanto el GUID como el nombre de las reglas de transporte que se aplicaron al mensaje. Podrá buscar los mensajes con el nombre de la regla de transporte. Se trata de una búsqueda "Contiene", lo que significa que también puede realizar búsquedas parciales.

#### <a name="important-note"></a>Nota importante:

La disponibilidad de nombre y búsqueda de ETR depende del rol específico que se le asigne. Debe tener uno de los siguientes roles o permisos para ver los nombres y la búsqueda de ETR. Si no tiene ninguno de estos roles asignados, no puede ver los nombres de las reglas de transporte ni buscar mensajes con nombres ETR. Sin embargo, podría ver la etiqueta ETR y la información guid en los detalles de correo electrónico. Otras experiencias de visualización de registros en cuadrículas de correo electrónico, menús desplegables de correo electrónico, filtros y exportación no se ven afectadas.

- Exo solo - Prevención de pérdida de datos: todo
- EXO Only - O365SupportViewConfig: All
- Microsoft Azure Active Directory o EXO: administrador de seguridad: todos
- AAD o EXO: lector de seguridad: todos
- Exo solo - Reglas de transporte: todas
- Solo EXO: View-Only configuración: todo

Dentro de la cuadrícula de correo electrónico, el control desplegable Detalles y el ARCHIVO CSV exportado, los ETR se presentan con un nombre o GUID, como se muestra a continuación.

> [!div class="mx-imgBorder"]
> ![Reglas de transporte de Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Conectores de entrada

Los conectores son una colección de instrucciones que personalizan cómo fluye el correo electrónico hacia y desde su organización de Microsoft 365 u Office 365. Permiten aplicar restricciones o controles de seguridad. En el Explorador de amenazas, ahora puede ver los conectores relacionados con un correo electrónico y buscar correos electrónicos mediante el uso de nombres de conectores.

La búsqueda de conectores tiene un carácter "contiene", lo que significa que las búsquedas parciales de palabras clave también deberían funcionar. Dentro de la vista de cuadrícula principal, el control desplegable Detalles y el CSV exportado, los conectores se muestran en el formato Nombre/GUID, como se muestra aquí:

> [!div class="mx-imgBorder"]
> ![Detalles del conector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuevas características del Explorador de amenazas y detecciones en tiempo real

Hay tres nuevas características disponibles en el Explorador de amenazas y en las detecciones en tiempo real:

- [Obtener una vista previa del encabezado de correo electrónico y descargar el cuerpo del correo electrónico](#preview-email-header-and-download-email-body)
- [Escala de tiempo del correo electrónico](#email-timeline)
- [Exportar datos de clic de dirección URL](#export-url-click-data)

Estas nuevas características se describen a continuación.

### <a name="preview-email-header-and-download-email-body"></a>Obtener una vista previa del encabezado de correo electrónico y descargar el cuerpo del correo electrónico

Ahora puede obtener una vista previa de un encabezado de correo electrónico y descargar el cuerpo del correo electrónico en Los administradores del Explorador de amenazas pueden analizar los encabezados descargados o los mensajes de correo electrónico en busca de amenazas. Dado que la descarga de mensajes de correo electrónico puede correr el riesgo de exposición de información, este proceso se controla mediante el control de acceso basado en roles (RBAC). Debe agregarse un nuevo *rol,* vista previa, a otro grupo de roles (como Operaciones de seguridad o Administrador de seguridad) para conceder la capacidad de descargar correos y obtener una vista previa de encabezados en la vista de mensajes de correo electrónico.

Las detecciones de explorador y en tiempo real también recibirán nuevos campos que proporcionan una imagen más completa de dónde llegarán los mensajes de correo electrónico. Estos cambios facilitan la búsqueda de operaciones de seguridad. Pero el resultado principal es que puede conocer la ubicación de los mensajes de correo electrónico con problemas de un vistazo.

¿Cómo se hace? El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega:** estado del correo electrónico.
- **Ubicación de entrega:** dónde se enrutó el correo electrónico.

*La acción de* entrega es la acción realizada en un correo electrónico debido a directivas o detecciones existentes. Estas son las acciones posibles para un correo electrónico:

|Entregado|Junked|Blocked|Reemplazado|
|---|---|---|---|
|El correo electrónico se entregó a la bandeja de entrada o carpeta de un usuario y el usuario puede acceder a él.|El correo electrónico se envió a la carpeta Correo no deseado o Eliminado del usuario y el usuario puede acceder a él.|Mensajes de correo electrónico que se ponen en cuarentena, que han fallado o que se han descartado. Estos correos no son accesibles para el usuario.|El correo electrónico tenía datos adjuntos malintencionados reemplazados por archivos .txt que den como resultado que los datos adjuntos son malintencionados.|

Esto es lo que el usuario puede y no puede ver:

|Accesible para los usuarios finales|Inaccesible para los usuarios finales|
|---|---|
|Entregado|Blocked|
|Junked|Reemplazado|

**La ubicación de** entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a la acción **_De entrega._** Estos son los valores posibles:

- *Bandeja de entrada o carpeta:* el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
- *Local o externo:* el buzón no existe en la nube, pero es local.
- *Carpeta de correo* no deseado: el correo electrónico se encuentra en la carpeta de correo no deseado de un usuario.
- *Carpeta elementos eliminados:* el correo electrónico de la carpeta Elementos eliminados de un usuario.
- *Cuarentena:* el correo electrónico está en cuarentena y no en el buzón de un usuario.
- *Error:* el correo electrónico no pudo llegar al buzón.
- *Descartado:* el correo electrónico se perdió en algún lugar del flujo de correo.

### <a name="email-timeline"></a>Escala de tiempo del correo electrónico

La **escala de tiempo de** correo electrónico es una nueva característica del explorador que mejora la experiencia de búsqueda para los administradores. Reduce el tiempo dedicado a comprobar diferentes ubicaciones para intentar comprender el evento. Cuando se suceden varios eventos al mismo tiempo o casi al mismo tiempo que llega un correo electrónico, estos eventos se muestran en una vista de escala de tiempo. Algunos eventos que se suceden en el correo electrónico posterior a la entrega se capturan en la **columna Acción** especial. Los administradores pueden combinar información de la escala de tiempo con la acción especial realizada en la entrega posterior al correo para obtener información sobre cómo funcionan sus directivas, dónde se enrutó finalmente el correo y, en algunos casos, cuál fue la evaluación final.

Para obtener más información, vea Investigar y corregir el correo electrónico malintencionado [que se entregó en Office 365.](investigate-malicious-email-that-was-delivered.md)

### <a name="export-url-click-data"></a>Exportar datos de clic de dirección URL

Ahora puede exportar informes de clics de  url a Microsoft Excel para ver el id. de mensaje de red y hacer clic en veredicto, lo que ayuda a explicar dónde se originó el tráfico de clics de la dirección URL. Así es como funciona: en Administración de amenazas en la barra de inicio rápido de Office 365, siga esta cadena:

**Explorador** \> **Ver suplantación de identidad** \> **Clics** \> **Las direcciones URL principales** o **los clics** superiores de la dirección URL \> seleccionan cualquier registro para abrir el menú desplegable de direcciones URL.

Cuando seleccione una dirección URL en la lista, verá un nuevo botón **Exportar** en el panel desplegable. Use este botón para mover datos a una hoja de cálculo de Excel para facilitar la creación de informes.

Siga esta ruta para llegar a la misma ubicación en el informe de detecciones en tiempo real:

**Explorador** \> **Detecciones en tiempo real** \> **Ver suplantación de identidad** \> **Direcciones URL** \> **Direcciones URL principales o** **clics superiores** Seleccione cualquier registro para abrir el control desplegable dirección URL, vaya a \> la pestaña \> **Clics.**

> [!TIP]
> El id. de mensaje de red asigna el clic a correos específicos cuando busca en el identificador a través del Explorador o las herramientas de terceros asociadas. Estas búsquedas identifican el correo electrónico asociado con un resultado de clic. Tener el id. de mensaje de red correlacionado permite un análisis más rápido y eficaz.

> [!div class="mx-imgBorder"]
> ![Pestaña Clics en el Explorador](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en el correo electrónico por tecnología

Supongamos que desea ver malware detectado en el correo electrónico ordenado por la tecnología de Microsoft 365. Para ello, usa la vista [Detección > malware](threat-explorer-views.md#email--malware) del Explorador (o detecciones en tiempo real).

1. En el Centro de & cumplimiento ( ), elija Explorador de administración de amenazas <https://protection.office.com>  \>  (o **detecciones en tiempo real).** (En este ejemplo se usa Explorer).

2. En el **menú Ver,** elija Malware **de** \> **correo electrónico.**

   > [!div class="mx-imgBorder"]
   > ![Menú Ver del Explorador](../../media/ExplorerViewEmailMalwareMenu.png)

3. Haga **clic en Remitente** y, a continuación, elija Tecnología **de** \> **detección básica.**

   Las tecnologías de detección ahora están disponibles como filtros para el informe.

   > [!div class="mx-imgBorder"]
   > ![Tecnologías de detección de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Elija una opción. A continuación, **seleccione** el botón Actualizar para aplicar ese filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnología de detección seleccionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

El informe se actualiza para mostrar los resultados que el malware detectó en el correo electrónico, mediante la opción de tecnología seleccionada. Desde aquí, puede realizar más análisis.

## <a name="view-phishing-url-and-click-verdict-data"></a>Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en los datos del veredicto

Supongamos que desea ver intentos de suplantación de identidad a través de direcciones URL en el correo electrónico, incluida una lista de direcciones URL permitidas, bloqueadas e invalidadas. Para identificar las direcciones URL en las que se hizo clic, deben configurarse [vínculos](atp-safe-links.md) seguros. Asegúrese de configurar [](set-up-atp-safe-links-policies.md) directivas de vínculos seguros para la protección con el tiempo de clic y el registro de veredictos de clic mediante vínculos seguros.

Para revisar las direcciones URL de suplantación de identidad [   >   ](threat-explorer-views.md#email--phish) en los mensajes y los clics en las direcciones URL de los mensajes de suplantación de identidad, use la vista de suplantación de identidad de correo electrónico del explorador o las detecciones en tiempo real.

1. En el Centro de & cumplimiento ( ), elija Explorador de administración de amenazas <https://protection.office.com>  \>  (o **detecciones en tiempo real).** (En este ejemplo se usa Explorer).

2. En el **menú Ver,** elija Suplantación de identidad **de correo** \> **electrónico.**

   > [!div class="mx-imgBorder"]
   > ![Menú Ver del Explorador en contexto de suplantación de identidad](../../media/ExplorerViewEmailPhishMenu.png)

3. Haga **clic en Remitente** y, a continuación, elija Direcciones **URL** Hacer clic \> **en veredicto.**

4. Seleccione una o más opciones, como **Bloqueado** y Bloquear  invalidados y, a continuación, seleccione el botón Actualizar en la misma línea que las opciones para aplicar ese filtro. (No actualice la ventana del explorador).

   > [!div class="mx-imgBorder"]
   > ![Url y veredictos de clic](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la pestaña Dirección URL del informe:

   - **Las direcciones URL principales** son las direcciones URL de los mensajes filtrados y la acción de entrega de correo electrónico cuenta para cada dirección URL. En la vista de correo electrónico de suplantación de identidad, esta lista normalmente contiene direcciones URL legítimas. Los atacantes incluyen una combinación de direcciones URL buenas y mal en sus mensajes para intentar que se entreguen, pero hacen que los vínculos malintencionados parezcan más interesantes. La tabla de direcciones URL se ordena por recuento total de correo electrónico, pero esta columna está oculta para simplificar la vista.

   - **Los clics principales** son las direcciones URL ajustadas por vínculos seguros en las que se hizo clic, ordenadas por recuento total de clics. Esta columna tampoco se muestra para simplificar la vista. Los recuentos totales por columna indican el recuento de veredictos de clic de Vínculos seguros para cada dirección URL en la que se ha hecho clic. En la vista de correo electrónico de suplantación de identidad, normalmente son direcciones URL sospechosas o malintencionadas. Pero la vista podría incluir direcciones URL que no son amenazas pero que están en mensajes de suplantación de identidad. Los clics de url en vínculos sin envolver no se muestran aquí.

   Las dos tablas url muestran las direcciones URL principales en los mensajes de correo electrónico de suplantación de identidad por acción de entrega y ubicación. En las tablas se muestran los clics de dirección URL que se bloquearon o visitaron a pesar de una advertencia, para que pueda ver qué posibles vínculos no se mostraron a los usuarios y en los que se hizo clic en el usuario. Desde aquí, puede realizar más análisis. Por ejemplo, debajo del gráfico puede ver las direcciones URL principales de los mensajes de correo electrónico bloqueados en el entorno de su organización.

   > [!div class="mx-imgBorder"]
   > ![Direcciones URL del explorador bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo desplegable dirección URL, se quita el filtrado de mensajes de correo electrónico para mostrar la vista completa de la exposición de la dirección URL en su entorno. Esto le permite filtrar los mensajes de correo electrónico que le preocupan en el Explorador, buscar direcciones URL específicas que son amenazas potenciales y, a continuación, ampliar su comprensión de la exposición de direcciones URL en su entorno (a través del cuadro de diálogo de detalles de la dirección URL) sin tener que agregar filtros de dirección URL a la propia vista del Explorador.

### <a name="interpretation-of-click-verdicts"></a>Interpretación de veredictos de clic

Dentro de los menús desplegables Correo electrónico o URL, Clics principales, así como en nuestras experiencias de filtrado, verá diferentes valores de veredicto de clic:

- **Ninguno:** No se puede capturar el veredicto de la dirección URL. Es posible que el usuario haya hecho clic en la dirección URL.
- **Permitido:** Se permitió al usuario navegar a la dirección URL.
- **Bloqueado:** Se bloqueó al usuario para que no navegara a la dirección URL.
- **Veredicto pendiente:** Al usuario se le presentó la página pendiente de detonación.
- **Bloqueado invalidado:** Se bloqueó al usuario para que no navegara directamente a la dirección URL. Pero el usuario supera el bloque para navegar a la dirección URL.
- **Se omitió el veredicto pendiente:** Se presentó al usuario la página de detonación. Pero el usuario ha sobresalto el mensaje para tener acceso a la dirección URL.
- **Error:** Al usuario se le presentó la página de error o se produjo un error al capturar el veredicto.
- **Error:** Se produjo una excepción desconocida al capturar el veredicto. Es posible que el usuario haya hecho clic en la dirección URL.

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico notificados por los usuarios

Supongamos que desea ver los mensajes de correo electrónico que los usuarios de [](enable-the-report-message-add-in.md) su organización han notificado como correo no *deseado,* correo no deseado o *suplantación* de identidad a través del complemento Informar de mensajes o el complemento Informar de [suplantación de identidad](enable-the-report-phish-add-in.md). Para verlos, usa la vista [   >  **Envíos de**](threat-explorer-views.md#email--submissions) correo electrónico del Explorador (o detecciones en tiempo real).

1. En el Centro de & cumplimiento ( ), elija Explorador de administración de amenazas <https://protection.office.com>  \>  (o **detecciones en tiempo real).** (En este ejemplo se usa Explorer).

2. En el **menú Ver,** elija  \> **Envíos de correo electrónico.**

   > [!div class="mx-imgBorder"]
   > ![Menú Ver del Explorador para mensajes de correo electrónico](../../media/explorer-view-menu-email-user-reported.png)

3. Haga **clic en Remitente** y, a continuación, elija Tipo **de** informe \> **básico.**

4. Seleccione una opción, como **suplantación** de identidad y, a continuación, seleccione el **botón** Actualizar.

   > [!div class="mx-imgBorder"]
   > ![Suplantación de identidad notificada por el usuario](../../media/EmailUserReportedReportType.png)

El informe se actualiza para mostrar datos sobre los mensajes de correo electrónico que las personas de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar más análisis y, si es necesario, ajustar las directivas contra suplantación de identidad en [Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="start-automated-investigation-and-response"></a>Iniciar investigación y respuesta automatizadas

> [!NOTE]
> Las capacidades automatizadas de investigación y respuesta están disponibles en Microsoft Defender para *Office 365 Plan 2* y *Office 365 E5.*

[La investigación y respuesta automatizadas](automated-investigation-response-office.md) pueden ahorrarle al equipo de operaciones de seguridad el tiempo y el esfuerzo invertidos en investigar y mitigar los ciberataques. Además de configurar alertas que pueden desencadenar un libro de estrategias de seguridad, puedes iniciar una investigación automatizada y un proceso de respuesta desde una vista en el Explorador. Para obtener más información, [vea Ejemplo: un administrador de seguridad desencadena una investigación desde el Explorador.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Más formas de usar detecciones en tiempo real y explorer

Además de los escenarios descritos en este artículo, tienes muchas más opciones de informes disponibles con explorer (o detecciones en tiempo real). Consulte los siguientes artículos:

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obtener información general sobre las vistas en el Explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](office-365-atp.md) para usar detecciones en tiempo real o explorer.

- El explorador se incluye en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender para Office 365 Plan 1.
- Planee asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365. Las detecciones de explorador y en tiempo real muestran los datos de detección de los usuarios con licencia.

Para ver y usar detecciones en tiempo real o explorer, debe tener los permisos adecuados, como los concedidos a un administrador de seguridad o un lector de seguridad.

- Para el Centro de & cumplimiento, debe tener asignado uno de los siguientes roles:

  - Administración de la organización
  - Administrador de seguridad (se puede asignar en el Centro de administración de Azure Active Directory ( <https://aad.portal.azure.com> )
  - Lector de seguridad

- Para Exchange Online, debe tener uno de los siguientes roles asignados en el Centro de administración de Exchange ( <https://admin.protection.outlook.com/ecp/> ) o Exchange Online [PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):

  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información acerca de los roles y permisos, vea los siguientes recursos:

- [Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)
- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferencias entre el Explorador de amenazas y las detecciones en tiempo real

- El *informe de detecciones en tiempo* real está disponible en Defender para Office 365 Plan 1. *El Explorador de* amenazas está disponible en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El Explorador de amenazas también hace esto, pero también proporciona detalles adicionales para un ataque determinado.
- La *vista Todo el* correo electrónico está disponible en el Explorador de amenazas, pero no en el informe de detecciones en tiempo real.
- En el Explorador de amenazas se incluyen más capacidades de filtrado y acciones disponibles. Para obtener más información, vea Descripción del servicio de Microsoft Defender para Office 365: disponibilidad de características en los planes de Defender para [Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
