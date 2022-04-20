---
title: Explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use el Explorador y las detecciones en tiempo real en el portal de Microsoft 365 Defender para investigar y responder a las amenazas de forma eficaz.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8a5029ad6de3de33eacdf814729ed2eafcd2cf89
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941685"
---
# <a name="threat-explorer-and-real-time-detections"></a>Explorador de amenazas y detecciones en tiempo real

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si su organización tiene [Microsoft Defender para Office 365](defender-for-office-365.md) y tiene los [permisos necesarios](#required-licenses-and-permissions), tiene detecciones de **Explorador** o **en tiempo real** (anteriormente *informes en tiempo real*, [consulte las novedades](#new-features-in-threat-explorer-and-real-time-detections)). En el Centro de cumplimiento de seguridad &, vaya a **Administración de amenazas** y elija **Explorador** _o_ **Detecciones en tiempo real**.

|Con Microsoft Defender para Office 365 plan 2, verá lo siguiente:|Con Microsoft Defender para Office 365 plan 1, verá lo siguiente:|
|---|---|
|![Explorador de amenazas.](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|

Las detecciones en tiempo real o explorador ayudan al equipo de operaciones de seguridad a investigar y responder a las amenazas de forma eficaz. El informe es similar a la siguiente imagen:

:::image type="content" source="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png" alt-text="Elemento de menú Explorador en el portal de cumplimiento de seguridad &" lightbox="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png":::

Con este informe, puede:

- [Ver el malware detectado por Microsoft 365 características de seguridad](#see-malware-detected-in-email-by-technology)
- [Ver la dirección URL de phishing y hacer clic en datos de veredicto](#view-phishing-url-and-click-verdict-data)
- [Iniciar un proceso de investigación y respuesta automatizado desde una vista en el Explorador](#start-automated-investigation-and-response) (solo Defender para Office 365 plan 2)
- [Investigar el correo electrónico malintencionado y mucho más](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a>Mejoras en la experiencia de búsqueda de amenazas


### <a name="introduction-of-alert-id-for-defender-for-office-365-alerts-within-explorerreal-time-detections"></a>Introducción al identificador de alerta para las alertas de Defender para Office 365 en el Explorador/Detecciones en tiempo real

Hoy en día, si navega desde una alerta al Explorador de amenazas, se abre una vista filtrada en el Explorador, con la vista filtrada por identificador de directiva de alerta (el identificador de directiva es un identificador único para una directiva de alerta).
Estamos haciendo que esta integración sea más relevante mediante la introducción del identificador de alerta (consulte un ejemplo de identificador de alerta a continuación) en el Explorador de amenazas y detecciones en tiempo real para que vea los mensajes que son relevantes para la alerta específica, así como un recuento de correos electrónicos. También podrá ver si un mensaje formaba parte de una alerta, así como navegar desde ese mensaje a la alerta específica.

El identificador de alerta está disponible en la dirección URL cuando se ve una alerta individual; un ejemplo es `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-Filter.png" alt-text="Filtrado del identificador de alerta" lightbox="../../media/AlertID-Filter.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-DetailsFlyout.png" alt-text="El control flotante Id. de alerta en detalles" lightbox="../../media/AlertID-DetailsFlyout.png":::

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days"></a>Ampliación de la retención de datos del Explorador (y detecciones en tiempo real) y el límite de búsqueda para inquilinos de prueba de 7 a 30 días

Como parte de este cambio, podrá buscar y filtrar los datos de correo electrónico durante 30 días (un aumento con respecto a los 7 días anteriores) en El Explorador de amenazas/Detecciones en tiempo real para los inquilinos de prueba de Defender para Office P1 y P2.
Esto no afecta a los inquilinos de producción para los clientes P1 y P2/E5, que ya tienen las capacidades de retención y búsqueda de datos de 30 días.

### <a name="updated-limits-for-export-of-records-for-threat-explorer"></a>Límites actualizados para la exportación de registros para el Explorador de amenazas

Como parte de esta actualización, el número de filas de registros de correo electrónico que se pueden exportar desde el Explorador de amenazas aumenta de 9990 a 200 000 registros. El conjunto de columnas que se pueden exportar actualmente seguirá siendo el mismo, pero el número de filas aumentará con respecto al límite actual.

### <a name="tags-in-threat-explorer"></a>Etiquetas en el Explorador de amenazas

> [!NOTE]
> La característica de etiquetas de usuario está en *versión preliminar*, no está disponible para todos y está sujeta a cambios. Para obtener información sobre la programación de la versión, consulte la hoja de ruta de Microsoft 365.

Las etiquetas de usuario identifican grupos específicos de usuarios en Microsoft Defender para Office 365. Para obtener más información sobre las etiquetas, incluidas las licencias y la configuración, consulte [Etiquetas de usuario](user-tags.md).

En el Explorador de amenazas, puede ver información sobre las etiquetas de usuario en las siguientes experiencias.

#### <a name="email-grid-view"></a>Vista de cuadrícula de correo electrónico

La columna **Etiquetas** de la cuadrícula de correo electrónico contiene todas las etiquetas que se han aplicado a los buzones de remitente o destinatario. De forma predeterminada, las etiquetas del sistema, como las cuentas de prioridad, se muestran primero.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-grid.png" alt-text="Etiquetas de filtro en la vista de cuadrícula de correo electrónico" lightbox="../../media/tags-grid.png":::

#### <a name="filtering"></a>Filtrado

Puede usar etiquetas como filtro. Busque solo entre cuentas de prioridad o escenarios de etiquetas de usuario específicos. También puede excluir los resultados que tienen ciertas etiquetas. Combine esta funcionalidad con otros filtros para restringir el ámbito de investigación.

[![Etiquetas de filtro.](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-filter-not.png" alt-text="Las etiquetas que no se filtran" lightbox="../../media/tags-filter-not.png":::

#### <a name="email-detail-flyout"></a>Control flotante de detalles de correo electrónico

Para ver las etiquetas individuales del remitente y el destinatario, seleccione el asunto para abrir el control flotante de detalles del mensaje. En la pestaña **Resumen** , las etiquetas de remitente y destinatario se muestran por separado, si están presentes para un correo electrónico.
La información sobre etiquetas individuales para remitente y destinatario también se extiende a los datos CSV exportados, donde puede ver estos detalles en dos columnas independientes.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-flyout.png" alt-text="Etiquetas de detalles de correo electrónico" lightbox="../../media/tags-flyout.png":::

La información de etiquetas también se muestra en el control flotante Clics de dirección URL. Para verlo, vaya a la vista Phish o Todo el correo electrónico y, a continuación, a la pestaña **Url** o **URL Clics** . Seleccione un control flotante de dirección URL individual para ver detalles adicionales sobre los clics de esa dirección URL, incluidas las etiquetas asociadas a ese clic.

### <a name="updated-timeline-view"></a>Vista de escala de tiempo actualizada

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-urls.png" alt-text="Las etiquetas url" lightbox="../../media/tags-urls.png":::
>
Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Mejoras en la experiencia de búsqueda de amenazas (próximamente)

### <a name="updated-threat-information-for-emails"></a>Información de amenazas actualizada para correos electrónicos

Nos hemos centrado en las mejoras de la plataforma y la calidad de los datos para aumentar la precisión y la coherencia de los datos para los registros de correo electrónico. Las mejoras incluyen la consolidación de la información previa y posterior a la entrega, como las acciones ejecutadas en un correo electrónico como parte del proceso ZAP, en un único registro. También se incluyen detalles adicionales como el veredicto de correo no deseado, las amenazas de nivel de entidad (por ejemplo, qué dirección URL era malintencionada) y las ubicaciones de entrega más recientes.

Después de estas actualizaciones, verá una única entrada para cada mensaje, independientemente de los distintos eventos posteriores a la entrega que afectan al mensaje. Las acciones pueden incluir ZAP, corrección manual (lo que significa acción de administración), [entrega dinámica](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies), etc.

Además de mostrar amenazas de malware y phishing, verá el veredicto de correo no deseado asociado a un correo electrónico. En el correo electrónico, vea todas las amenazas asociadas al correo electrónico junto con las tecnologías de detección correspondientes. Un correo electrónico puede tener cero, una o varias amenazas. Verá las amenazas actuales en la sección **Detalles** del control flotante de correo electrónico. En el caso de varias amenazas (como malware y phishing), el campo **tecnología de detección** muestra la asignación de detección de amenazas, que es la tecnología de detección que identificó la amenaza.

El conjunto de tecnologías de detección ahora incluye nuevos métodos de detección, así como tecnologías de detección de correo no deseado. Puede usar el mismo conjunto de tecnologías de detección para filtrar los resultados en las distintas vistas de correo electrónico (Malware, Phish, Todo el correo electrónico).

> [!NOTE]
> Es posible que el análisis de veredictos no esté necesariamente vinculado a entidades. Por ejemplo, un correo electrónico podría clasificarse como phish o spam, pero no hay direcciones URL que estén selladas con un veredicto de phish/spam. Esto se debe a que los filtros también evalúan el contenido y otros detalles de un correo electrónico antes de asignar un veredicto.

#### <a name="threats-in-urls"></a>Amenazas en direcciones URL

Ahora puede ver la amenaza específica de una dirección URL en la pestaña **Detalles** del control flotante de correo electrónico. La amenaza puede ser *malware*, *phish*, *spam* o *ninguno*).

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/URL_Threats.png" alt-text="Amenazas de dirección URL" lightbox="../../media/URL_Threats.png":::

### <a name="updated-timeline-view-upcoming"></a>Vista de escala de tiempo actualizada (próximamente)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Email_Timeline.png" alt-text="Vista de escala de tiempo actualizada" lightbox="../../media/Email_Timeline.png":::

La vista escala de tiempo identifica todos los eventos de entrega y posteriores a la entrega. Incluye información sobre la amenaza identificada en ese momento para un subconjunto de estos eventos. La vista escala de tiempo también proporciona información sobre cualquier acción adicional realizada (como ZAP o corrección manual), junto con el resultado de esa acción. La información de la vista de escala de tiempo incluye:

- **Fuente:** Origen del evento. Puede ser administrador, sistema o usuario.
- **Evento:** Incluye eventos de nivel superior, como entrega original, corrección manual, ZAP, envíos y entrega dinámica.
- **Acción:** Acción específica que se realizó como parte de zap o acción de administrador (por ejemplo, eliminación temporal).
- **Amenazas:** Cubre las amenazas (malware, phish, spam) identificadas en ese momento.
- **Resultado/Detalles:** Más información sobre el resultado de la acción, como si se realizó como parte de la acción ZAP/admin.

### <a name="original-and-latest-delivery-location"></a>Ubicación de entrega original y más reciente

Actualmente, exponemos la ubicación de entrega en la cuadrícula de correo electrónico y el control flotante de correo electrónico. El campo **Ubicación de entrega** se ha cambiado de nombre **_Ubicación de entrega original_*_. Y vamos a introducir otro campo, _*_Latest delivery location (Ubicación de entrega más reciente_**).

**La ubicación de entrega original** proporcionará más información sobre dónde se entregó inicialmente un correo electrónico. **La ubicación de entrega más reciente** indicará dónde aterrizó un correo electrónico después de acciones del sistema como *ZAP* o acciones de administrador, como *Mover a elementos eliminados*. La ubicación de entrega más reciente está pensada para indicar a los administradores la última ubicación conocida del mensaje después de la entrega o cualquier acción del sistema o administrador. No incluye ninguna acción del usuario final en el correo electrónico. Por ejemplo, si un usuario eliminó un mensaje o movió el mensaje a archive/pst, la ubicación del mensaje "entrega" no se actualizará. Pero si una acción del sistema actualizó la ubicación (por ejemplo, ZAP, lo que da lugar a un correo electrónico que se mueve a cuarentena), la **ubicación de entrega más reciente** se mostraría como "cuarentena".

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Updated_Delivery_Location.png" alt-text="Ubicaciones de entrega actualizadas" lightbox="../../media/Updated_Delivery_Location.png":::

> [!NOTE]
> Hay algunos casos en los que **la ubicación de entrega** y **la acción de entrega** pueden mostrarse como "desconocidos":
>
> - Es posible que vea **Ubicación de entrega** como "entregada" y **Ubicación de entrega** como "desconocida" si el mensaje se ha entregado, pero una regla de bandeja de entrada ha movido el mensaje a una carpeta predeterminada (como Borrador o Archivo) en lugar de a la carpeta Bandeja de entrada o Correo electrónico no deseado.
>
> - **La ubicación de entrega más reciente** puede ser desconocida si se intentó realizar una acción de administrador o sistema (como ZAP), pero no se encontró el mensaje. Normalmente, la acción se produce después de que el usuario haya movido o eliminado el mensaje. En tales casos, compruebe la columna **Resultado/Detalles** en la vista de escala de tiempo. Busque la instrucción "Mensaje movido o eliminado por el usuario".

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Updated_Timeline_Delivery_Location.png" alt-text="Ubicaciones de entrega para la escala de tiempo" lightbox="../../media/Updated_Timeline_Delivery_Location.png":::

### <a name="additional-actions"></a>Acciones adicionales

Se aplicaron *acciones adicionales* después de la entrega del correo electrónico. Pueden incluir *ZAP*, *corrección manual* (acción realizada por un administrador, como la eliminación temporal), *entrega dinámica* y *reprocesamiento* (para un correo electrónico que se detectó de forma retroactiva como correcto).

> [!NOTE]
> Como parte de los cambios pendientes, el valor "Quitado por ZAP" que aparece actualmente en el filtro Acción de entrega desaparece. Tendrá una manera de buscar todo el correo electrónico con el intento ZAP a través de **acciones adicionales**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Additional_Actions.png" alt-text="Acciones adicionales en el Explorador" lightbox="../../media/Additional_Actions.png":::

### <a name="system-overrides"></a>Invalidaciones del sistema

*Las invalidaciones del sistema* permiten realizar excepciones en la ubicación de entrega prevista de un mensaje. La ubicación de entrega proporcionada por el sistema se invalida en función de las amenazas y otras detecciones identificadas por la pila de filtrado. Las invalidaciones del sistema se pueden establecer a través de la directiva de inquilino o de usuario para entregar el mensaje tal y como sugiere la directiva. Las invalidaciones pueden identificar la entrega involuntaria de mensajes malintencionados debido a brechas de configuración, como una directiva de remitente demasiado amplia Caja fuerte establecida por un usuario. Estos valores de invalidación pueden ser:

- Permitido por la directiva de usuario: un usuario crea directivas en el nivel de buzón para permitir dominios o remitentes.

- Bloqueado por la directiva de usuario: un usuario crea directivas en el nivel de cuadro de correo para bloquear dominios o remitentes.

- Permitido por la directiva de la organización: los equipos de seguridad de la organización establecen directivas o Exchange reglas de flujo de correo (también conocidas como reglas de transporte) para permitir remitentes y dominios para los usuarios de su organización. Esto puede ser para un conjunto de usuarios o toda la organización.

- Bloqueado por la directiva de la organización: los equipos de seguridad de la organización establecen directivas o reglas de flujo de correo para bloquear remitentes, dominios, idiomas de mensaje o direcciones IP de origen para los usuarios de su organización. Esto se puede aplicar a un conjunto de usuarios o a toda la organización.

- Extensión de archivo bloqueada por la directiva de la organización: el equipo de seguridad de una organización bloquea una extensión de nombre de archivo a través de la configuración de la directiva antimalware. Estos valores ahora se mostrarán en los detalles del correo electrónico para ayudar con las investigaciones. Los equipos de Secops también pueden usar la funcionalidad de filtrado enriquecido para filtrar las extensiones de archivo bloqueadas.

[![Invalidaciones del sistema en el Explorador.](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/System_Overrides_Grid.png" alt-text="El sistema invalida la cuadrícula en el Explorador" lightbox="../../media/System_Overrides_Grid.png":::

### <a name="improvements-for-the-url-and-clicks-experience"></a>Mejoras en la experiencia de url y clics

Las mejoras incluyen:

- Muestre la dirección URL completa en la que se ha hecho clic (incluidos los parámetros de consulta que forman parte de la dirección URL) en la sección **Clics** del control flotante URL. Actualmente, el dominio y la ruta de acceso de la dirección URL aparecen en la barra de título. Vamos a ampliar esa información para mostrar la dirección URL completa.

- Correcciones entre filtros de dirección *URL (dirección URL* frente a *dominio de dirección URL* frente a *dominio y ruta de acceso de dirección URL*): las actualizaciones afectan a la búsqueda de mensajes que contienen un veredicto de dirección URL o clic. Hemos habilitado la compatibilidad con búsquedas independientes del protocolo, por lo que puede buscar una dirección URL sin usar `http`. De forma predeterminada, la búsqueda de direcciones URL se asigna a http, a menos que se especifique explícitamente otro valor. Por ejemplo:
  - Busque con y sin el `http://` prefijo en los campos **url**, **dominio url** y **dominio url y filtro de ruta de acceso** . Las búsquedas deben mostrar los mismos resultados.
  - Busque el prefijo en la `https://` **dirección URL**. Cuando no se especifica ningún valor, se asume el `http://` prefijo.
  - `/` se omite al principio y al final de los campos **URL path**, **URL Domain**, **URL domain y path** . `/` al final del campo **URL** se omite.

### <a name="phish-confidence-level"></a>Nivel de confianza de phish

El nivel de confianza de phish ayuda a identificar el grado de confianza con el que se clasificó un correo electrónico como "phish". Los dos valores posibles son *Alta* y *Normal*. En las fases iniciales, este filtro solo estará disponible en la vista Phish del Explorador de amenazas.

[![Nivel de confianza de phish en el Explorador.](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Señal de dirección URL de ZAP

La señal de dirección URL de ZAP se usa normalmente para escenarios de alertas de phish de ZAP en los que un correo electrónico se identificó como Phish y se quitó después de la entrega. Esta señal conecta la alerta con los resultados correspondientes en el Explorador. Es uno de los IOC de la alerta.

Para mejorar el proceso de búsqueda, hemos actualizado el Explorador de amenazas y las detecciones en tiempo real para que la experiencia de búsqueda sea más coherente. Los cambios se describen aquí:

- [Mejoras en la zona horaria](#timezone-improvements)
- [Actualización en el proceso de actualización](#update-in-the-refresh-process)
- [Obtención de detalles del gráfico para agregar a filtros](#chart-drilldown-to-add-to-filters)
- [En las actualizaciones de información del producto](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrar por etiquetas de usuario

Ahora puede ordenar y filtrar las etiquetas de usuario personalizadas o del sistema para comprender rápidamente el ámbito de las amenazas. Para más información, consulte [Etiquetas de usuario](user-tags.md).

> [!IMPORTANT]
> El filtrado y ordenación por etiquetas de usuario está actualmente en versión preliminar pública. Esta funcionalidad puede modificarse sustancialmente antes de que se publique comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, con respecto a la información proporcionada al respecto.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-tags.png" alt-text="Columna Etiquetas en el Explorador" lightbox="../../media/threat-explorer-tags.png":::

### <a name="timezone-improvements"></a>Mejoras en la zona horaria

Verá la zona horaria para los registros de correo electrónico en el portal, así como para los datos exportados. Será visible en experiencias como Email Grid, control flotante Detalles, Escala de tiempo de correo electrónico y Correos electrónicos similares, por lo que la zona horaria del conjunto de resultados es clara.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/TimezoneImprovements.png" alt-text="Vista de la zona horaria en el Explorador" lightbox="../../media/TimezoneImprovements.png":::

### <a name="update-in-the-refresh-process"></a>Actualización en el proceso de actualización

Algunos usuarios han comentado sobre la confusión con la actualización automática (por ejemplo, en cuanto cambia la fecha, la página se actualiza) y la actualización manual (para otros filtros). De forma similar, la eliminación de filtros conduce a la actualización automática. Cambiar los filtros al modificar la consulta puede provocar experiencias de búsqueda incoherentes. Para resolver estos problemas, vamos a pasar a un mecanismo de filtrado manual.

Desde el punto de vista de la experiencia, el usuario puede aplicar y quitar el intervalo diferente de filtros (del conjunto de filtros y la fecha) y seleccionar el botón actualizar para filtrar los resultados una vez que haya definido la consulta. El botón actualizar también se resalta ahora en la pantalla. También hemos actualizado la información sobre herramientas relacionada y la documentación del producto.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ManualRefresh.png" alt-text="El botón Actualizar para filtrar los resultados" lightbox="../../media/ManualRefresh.png":::

### <a name="chart-drilldown-to-add-to-filters"></a>Obtención de detalles del gráfico para agregar a filtros

Ahora puede crear gráficos de valores de leyenda para agregarlos como filtros. Seleccione el botón **Actualizar** para filtrar los resultados.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ChartDrilldown.png" alt-text="Explorar en profundidad los gráficos que se van a filtrar" lightbox="../../media/ChartDrilldown.png":::

### <a name="in-product-information-updates"></a>Actualizaciones de información del producto

Ahora hay detalles adicionales disponibles en el producto, como el número total de resultados de búsqueda dentro de la cuadrícula (consulte a continuación). Hemos mejorado las etiquetas, los mensajes de error y la información sobre herramientas para proporcionar más información sobre los filtros, la experiencia de búsqueda y el conjunto de resultados.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ProductInfo.png" alt-text="Información del producto que se va a ver" lightbox="../../media/ProductInfo.png":::

## <a name="extended-capabilities-in-threat-explorer"></a>Funcionalidades extendidas en el Explorador de amenazas

### <a name="top-targeted-users"></a>Usuarios de destino superior

Hoy exponemos la lista de los usuarios de destino principales en la vista Malware para correos electrónicos, en la sección **Principales familias de malware** . Ampliaremos esta vista también en las vistas Phish y All Email. Podrá ver los cinco usuarios de destino principales, junto con el número de intentos de cada usuario para la vista correspondiente. Por ejemplo, para la vista Phish, verá el número de intentos de Phish.

Podrá exportar la lista de usuarios de destino, hasta un límite de 3000, junto con el número de intentos de análisis sin conexión para cada vista de correo electrónico. Además, al seleccionar el número de intentos (por ejemplo, 13 intentos en la imagen siguiente), se abrirá una vista filtrada en el Explorador de amenazas, para que pueda ver más detalles en los correos electrónicos y las amenazas de ese usuario.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Top_Targeted_Users.png" alt-text="Los usuarios de destino superior" lightbox="../../media/Top_Targeted_Users.png":::

### <a name="exchange-transport-rules"></a>Exchange reglas de transporte

Como parte del enriquecimiento de datos, podrá ver todas las diferentes reglas de transporte de Exchange (ETR) que se aplicaron a un mensaje. Esta información estará disponible en la vista de cuadrícula Correo electrónico. Para verlo, seleccione **Opciones de columna** en la cuadrícula y, a continuación, **Agregue Exchange regla de transporte** en las opciones de columna. También estará visible en el control flotante **Detalles** del correo electrónico.

Podrá ver el GUID y el nombre de las reglas de transporte que se aplicaron al mensaje. Podrá buscar los mensajes mediante el nombre de la regla de transporte. Se trata de una búsqueda "Contiene", lo que significa que también puede realizar búsquedas parciales.

> [!IMPORTANT]
> La disponibilidad de nombres y búsqueda de ETR depende del rol específico que se le asigne. Debe tener uno de los siguientes roles o permisos para ver los nombres y la búsqueda de ETR. Si no tiene ninguno de estos roles asignados, no podrá ver los nombres de las reglas de transporte ni buscar mensajes mediante nombres ETR. Sin embargo, podría ver la etiqueta ETR y la información del GUID en Detalles del correo electrónico. Otras experiencias de visualización de registros en cuadrículas de correo electrónico, controles flotantes de correo electrónico, filtros y exportación no se ven afectados.
>
> - Solo EXO: prevención de pérdida de datos: todos
> - Solo EXO: O365SupportViewConfig: todos
> - Microsoft Azure Active Directory o EXO: administrador de seguridad: todos
> - AAD o EXO: Lector de seguridad: todos
> - Solo EXO: reglas de transporte: todas
> - Solo EXO: configuración de View-Only: todos
>
> Dentro de la cuadrícula de correo electrónico, el control flotante Detalles y CSV exportado, los ETR se presentan con un nombre o GUID, como se muestra a continuación.
>
> > [!div class="mx-imgBorder"]
> > :::image type="content" source="../../media/ETR_Details.png" alt-text="Reglas de transporte de Exchange" lightbox="../../media/ETR_Details.png":::

### <a name="inbound-connectors"></a>Conectores de entrada

Los conectores son una colección de instrucciones que personalizan cómo fluye el correo electrónico hacia y desde la Microsoft 365 o Office 365 organización. Permiten aplicar restricciones o controles de seguridad. En el Explorador de amenazas, ahora puede ver los conectores relacionados con un correo electrónico y buscar correos electrónicos mediante nombres de conector.

La búsqueda de conectores es "contiene" por naturaleza, lo que significa que las búsquedas parciales de palabras clave también deberían funcionar. En la vista de cuadrícula Principal, el control flotante Detalles y el ARCHIVO CSV exportado, los conectores se muestran en el formato nombre/GUID, como se muestra aquí:

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Connector_Details.png" alt-text="Detalles del conector" lightbox="../../media/Connector_Details.png":::

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuevas características del Explorador de amenazas y detecciones en tiempo real

- [Visualización de correos electrónicos de suplantación de identidad enviados a usuarios y dominios suplantados](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [Vista previa del encabezado de correo electrónico y descarga del cuerpo del correo electrónico](#preview-email-header-and-download-email-body)
- [Escala de tiempo del correo electrónico](#email-timeline)
- [Exportar datos de clic de dirección URL](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a>Visualización de correos electrónicos de suplantación de identidad enviados a usuarios y dominios suplantados

Para identificar los intentos de suplantación de identidad de los usuarios y dominios que son usuarios suplantados se deben agregar a la lista de *usuarios que se van a proteger*. En el caso de los dominios, los administradores deben habilitar *los dominios de la organización* o agregar un nombre de dominio a *Dominios para protegerlos*. Los dominios que se van a proteger se encuentran en la *página Directiva contra suplantación de identidad* en la sección *Suplantación* .

Para revisar los mensajes de phish y buscar usuarios o dominios suplantados, use la [vista Correo electrónico > Phish](threat-explorer-views.md) del Explorador.

En este ejemplo se usa el Explorador de amenazas.

1. En el [Centro de cumplimiento de seguridad &](https://protection.office.com) (https://protection.office.com), elija Administración de amenazas > Explorer (o Detecciones en tiempo real).

2. En el menú Ver, elija Correo electrónico > Phish.

   Aquí puede elegir un **dominio suplantado** o un **usuario suplantado**.

3. **Seleccione** **Dominio suplantado** y escriba un dominio protegido en el cuadro de texto.

   Por ejemplo, busque nombres de dominio protegidos como *contoso*, *contoso.com* o *contoso.com.au*.

4. Seleccione el Asunto de cualquier mensaje en la pestaña Correo electrónico > pestaña Detalles para ver información de suplantación adicional, como Dominio suplantado o Ubicación detectada.

    **OR**

    Seleccione **Usuario suplantado** y escriba la dirección de correo electrónico de un usuario protegido en el cuadro de texto.

    > [!TIP]
    > **Para obtener los mejores resultados**, use *direcciones de correo electrónico completas* para buscar usuarios protegidos. Encontrará el usuario protegido más rápido y correctamente si busca *firstname.lastname@contoso.com*, por ejemplo, al investigar la suplantación de usuario. Al buscar un dominio protegido, la búsqueda tomará el dominio raíz (contoso.com, por ejemplo) y el nombre de dominio (*contoso*). La búsqueda del dominio raíz *contoso.com* devolverá las suplantaciones de *contoso.com* y el nombre de dominio *contoso*.

5. Seleccione el **Asunto** de cualquier mensaje en **la pestaña** >  Correo **electrónicoDetails** para ver información adicional de suplantación sobre el usuario o dominio y la *ubicación Detectada*.

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="El panel de detalles del Explorador de amenazas para un usuario protegido que muestra la ubicación de detección y la amenaza detectada (aquí suplantación de identidad de un usuario)" lightbox="../../media/threat-ex-views-impersonated-user-image.png":::

> [!NOTE]
> En el paso 3 o 5, si elige **Tecnología de detección** y selecciona **Dominio de suplantación** o **Usuario de suplantación**, respectivamente, la información de la **pestaña** >  Correo electrónicoDetails sobre el usuario o dominio y la *ubicación Detectada* solo se mostrarán en los mensajes relacionados con el usuario o dominio **enumerados** en la página *Directiva anti phishing*.

### <a name="preview-email-header-and-download-email-body"></a>Vista previa del encabezado de correo electrónico y descarga del cuerpo del correo electrónico

Ahora puede obtener una vista previa de un encabezado de correo electrónico y descargar el cuerpo del correo electrónico en el Explorador de amenazas. Los administradores pueden analizar los encabezados descargados o los mensajes de correo electrónico para detectar amenazas. Dado que la descarga de mensajes de correo electrónico puede arriesgar la exposición de información, este proceso se controla mediante el control de acceso basado en rol (RBAC). Se requiere un nuevo rol, *Versión preliminar*, para conceder la capacidad de descargar correos electrónicos en la vista de mensajes de correo electrónico completo. Sin embargo, la visualización del encabezado de correo electrónico no requiere ningún rol adicional (aparte de lo necesario para ver los mensajes en el Explorador de amenazas). Para crear un nuevo grupo de roles con el rol De vista previa:

1. Seleccione un grupo de roles integrado que solo tenga el rol Vista previa, como Investigador de datos o Administrador de exhibición de documentos electrónicos.
2. Seleccione **Copiar grupo de roles**.
3. Elija un nombre y una descripción para el nuevo grupo de roles y seleccione **Siguiente**.
4. Modifique los roles agregando y quitando roles según sea necesario, pero dejando el rol Vista previa.
5. Agregue miembros y, a continuación, seleccione **Crear grupo de roles**.

Las detecciones en tiempo real y explorador también obtendrán nuevos campos que proporcionan una imagen más completa de dónde llegan los mensajes de correo electrónico. Estos cambios facilitan la búsqueda de operaciones de seguridad. Pero el resultado principal es que puede conocer la ubicación de los mensajes de correo electrónico problemáticos de un vistazo.

¿Cómo se hace esto? El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : estado del correo electrónico.
- **Ubicación de entrega** : dónde se enrutó el correo electrónico.

*La acción de entrega* es la acción realizada en un correo electrónico debido a directivas o detecciones existentes. Estas son las acciones posibles para un correo electrónico:

|Entregado|Tirados|Blocked|Substituido|
|---|---|---|---|
|El correo electrónico se entregó en la bandeja de entrada o carpeta de un usuario y el usuario puede acceder a él.|El correo electrónico se envió a la carpeta No deseado o Eliminado del usuario y el usuario puede acceder a él.|Correos electrónicos en cuarentena, con errores o eliminados. Estos correos no son accesibles para el usuario.|El correo electrónico tenía datos adjuntos malintencionados reemplazados por .txt archivos que indican que los datos adjuntos eran malintencionados.|

Esto es lo que el usuario puede y no puede ver:

|Accesible para los usuarios finales|Inaccesible para los usuarios finales|
|---|---|
|Entregado|Blocked|
|Tirados|Substituido|

**La ubicación de entrega** muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a la **_acción de entrega_**. Estos son los valores posibles:

- *Bandeja de entrada o carpeta*: el correo electrónico está en la bandeja de entrada o en una carpeta (de acuerdo con las reglas de correo electrónico).
- *Local o externo*: el buzón no existe en la nube, pero es local.
- *Carpeta no deseada*: el correo electrónico está en la carpeta No deseado de un usuario.
- *Carpeta elementos eliminados*: el correo electrónico de la carpeta Elementos eliminados de un usuario.
- *Cuarentena*: el correo electrónico está en cuarentena y no en el buzón de un usuario.
- *Error*: el correo electrónico no pudo llegar al buzón de correo.
- *Eliminado*: el correo electrónico se perdió en algún lugar del flujo de correo.

### <a name="email-timeline"></a>Escala de tiempo del correo electrónico

La **escala de tiempo de correo electrónico** es una nueva característica del Explorador que mejora la experiencia de búsqueda de los administradores. Reduce el tiempo dedicado a comprobar diferentes ubicaciones para intentar comprender el evento. Cuando se producen varios eventos en o cerca del mismo momento en que llega un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos eventos que se producen en el correo electrónico posterior a la entrega se capturan en la columna **Acción especial** . Los administradores pueden combinar información de la escala de tiempo con la acción especial realizada en el correo posterior a la entrega para obtener información sobre cómo funcionan sus directivas, dónde se enrutó finalmente el correo y, en algunos casos, cuál fue la evaluación final.

Para obtener más información, vea [Investigar y corregir el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportar datos de clic de dirección URL

Ahora puede exportar informes de clics de dirección URL para Microsoft Excel para ver su **identificador de mensaje de red** y **veredicto de clics**, lo que ayuda a explicar dónde se originó el tráfico de clic de la dirección URL. Este es el funcionamiento: En Administración de amenazas en la barra de inicio rápido Office 365, siga esta cadena:

**Explorador** \> **Ver phish** \> **Clics** \> **Las direcciones URL principales** o **los clics** \> superiores de dirección URL seleccionan cualquier registro para abrir el control flotante de direcciones URL.

Al seleccionar una dirección URL en la lista, verá un nuevo botón **Exportar** en el panel flotante. Use este botón para mover datos a una hoja de cálculo de Excel para facilitar la generación de informes.

Siga esta ruta de acceso para llegar a la misma ubicación en el informe Detecciones en tiempo real:

**Explorador** \> **Detecciones en** \> tiempo real **Ver phish** \> **Url** \> **Direcciones URL principales** o **Clics** \> superiores Seleccione cualquier registro para abrir el control flotante \> url, vaya a la pestaña **Clics** .

> [!TIP]
> El identificador de mensaje de red asigna el clic de nuevo a correos electrónicos específicos al buscar en el identificador a través del Explorador o de herramientas de terceros asociadas. Estas búsquedas identifican el correo electrónico asociado a un resultado de clic. Tener el identificador de mensaje de red correlacionado permite un análisis más rápido y eficaz.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tp_ExportClickResultAndNetworkID.png" alt-text="Pestaña Clics en el Explorador" lightbox="../../media/tp_ExportClickResultAndNetworkID.png":::

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en el correo electrónico por tecnología

Supongamos que desea ver el malware detectado en el correo electrónico ordenado por Microsoft 365 tecnología. Para ello, use la vista [Correo electrónico > Malware](threat-explorer-views.md#email--malware) del Explorador (o detecciones en tiempo real).

1. En el Centro de cumplimiento de seguridad & (<https://protection.office.com>), elija **Explorador** **de administración** \> de amenazas (o **Detecciones en tiempo real**). (En este ejemplo se usa el Explorador).

2. En el menú **Ver**, elija **Malware de correo electrónico**\>.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailMalwareMenu.png" alt-text="Menú Ver del Explorador" lightbox="../../media/ExplorerViewEmailMalwareMenu.png":::

3. Haga clic en **Remitente** y, a continuación, elija **Tecnología de detección** **básica**\>.

   Las tecnologías de detección ahora están disponibles como filtros para el informe.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerEmailMalwareDetectionTech.png" alt-text="Tecnologías de detección de malware" lightbox="../../media/ExplorerEmailMalwareDetectionTech.png":::

4. Elija una opción. A continuación, seleccione el botón **Actualizar** para aplicar ese filtro.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerEmailMalwareDetectionTechATP.png" alt-text="La tecnología de detección seleccionada" lightbox="../../media/ExplorerEmailMalwareDetectionTechATP.png":::

El informe se actualiza para mostrar los resultados detectados por malware en el correo electrónico, mediante la opción de tecnología seleccionada. Desde aquí, puede realizar análisis adicionales.

## <a name="view-phishing-url-and-click-verdict-data"></a>Ver la dirección URL de phishing y hacer clic en datos de veredicto

Supongamos que desea ver los intentos de suplantación de identidad a través de direcciones URL en el correo electrónico, incluida una lista de direcciones URL permitidas, bloqueadas y reemplazadas. Para identificar las direcciones URL en las que se ha hecho clic, se debe configurar [Caja fuerte Vínculos](safe-links.md). Asegúrese de configurar [las directivas de vínculos de Caja fuerte](set-up-safe-links-policies.md) para la protección con el tiempo de clic y el registro de veredictos de clics mediante Caja fuerte Vínculos.

Para revisar las direcciones URL de phish en los mensajes y hacer clic en las direcciones URL de los mensajes de phish, use la vista [**EmailPhish** > ](threat-explorer-views.md#email--phish) del Explorador o las detecciones en tiempo real.

1. En el Centro de cumplimiento de seguridad & (<https://protection.office.com>), elija **Explorador** **de administración** \> de amenazas (o **Detecciones en tiempo real**). (En este ejemplo se usa el Explorador).

2. En el menú **Ver** , elija **Email** \> **Phish**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailPhishMenu.png" alt-text="El menú Ver del Explorador en contexto de suplantación de identidad" lightbox="../../media/ExplorerViewEmailPhishMenu.png":::

3. Haga clic en **Remitentey**, a continuación, elija **Direcciones** \> URL **Haga clic en veredicto**.

4. Seleccione una o varias opciones, como **Bloqueado** y **Bloquear invalidados**, y, a continuación, seleccione el botón **Actualizar** en la misma línea que las opciones para aplicar ese filtro. (No actualice la ventana del explorador).

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ThreatExplorerEmailPhishClickVerdictOptions.png" alt-text="Las direcciones URL y los veredictos de clic" lightbox="../../media/ThreatExplorerEmailPhishClickVerdictOptions.png":::

   El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la pestaña URL del informe:

   - **Las direcciones URL principales** son las direcciones URL de los mensajes a los que filtró y la acción de entrega de correo electrónico cuenta para cada dirección URL. En la vista de correo electrónico de Phish, esta lista normalmente contiene direcciones URL legítimas. Los atacantes incluyen una combinación de direcciones URL buenas y malas en sus mensajes para intentar que se entreguen, pero hacen que los vínculos malintencionados parezcan más interesantes. La tabla de direcciones URL se ordena por número total de correo electrónico, pero esta columna está oculta para simplificar la vista.

   - **Los clics superiores son las direcciones URL ajustadas por vínculos** Caja fuerte en las que se ha hecho clic, ordenadas por número total de clics. Esta columna tampoco se muestra para simplificar la vista. Los recuentos totales por columna indican el número de veredictos de clic de vínculos de Caja fuerte para cada dirección URL en la que se ha hecho clic. En la vista de correo electrónico de Phish, suelen ser direcciones URL sospechosas o malintencionadas. Pero la vista podría incluir direcciones URL que no son amenazas, pero que están en mensajes de tipo phish. Los clics de dirección URL en los vínculos desencapsados no aparecen aquí.

   Las dos tablas de direcciones URL muestran las direcciones URL principales en los mensajes de correo electrónico de suplantación de identidad por acción de entrega y ubicación. Las tablas muestran los clics de dirección URL que se bloquearon o visitaron a pesar de una advertencia, por lo que puede ver qué posibles vínculos incorrectos se presentaron a los usuarios y en los que se hizo clic en el usuario. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico puede ver las direcciones URL principales en los mensajes de correo electrónico que se bloquearon en el entorno de la organización.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerPhishClickVerdictURLs.png" alt-text="Las direcciones URL del Explorador que se bloquearon" lightbox="../../media/ExplorerPhishClickVerdictURLs.png":::

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo de control flotante URL, se quita el filtrado de mensajes de correo electrónico para mostrar la vista completa de la exposición de la dirección URL en su entorno. Esto le permite filtrar los mensajes de correo electrónico que le preocupan en el Explorador, buscar direcciones URL específicas que son posibles amenazas y, a continuación, ampliar la comprensión de la exposición de direcciones URL en su entorno (a través del cuadro de diálogo Detalles de dirección URL) sin tener que agregar filtros de dirección URL a la propia vista del Explorador.

### <a name="interpretation-of-click-verdicts"></a>Interpretación de los veredictos de clic

Dentro de los controles flotantes Correo electrónico o DIRECCIÓN URL, Clics superiores, así como dentro de nuestras experiencias de filtrado, verá diferentes valores de veredicto de clics:

- **Ninguno:** No se puede capturar el veredicto de la dirección URL. Es posible que el usuario haya hecho clic en la dirección URL.
- **Permitido:** Se permitió al usuario navegar a la dirección URL.
- **Bloqueado:** El usuario no pudo navegar a la dirección URL.
- **Veredicto pendiente:** Al usuario se le presentó la página pendiente de detonación.
- **Bloqueado invalidado:** El usuario no pudo navegar directamente a la dirección URL. Pero el usuario superó el bloque para navegar a la dirección URL.
- **Veredicto pendiente omitido:** Al usuario se le presentó la página de detonación. Pero el usuario superó el mensaje para acceder a la dirección URL.
- **Error:** Al usuario se le presentó la página de error o se produjo un error al capturar el veredicto.
- **Fracaso:** Se produjo una excepción desconocida al capturar el veredicto. Es posible que el usuario haya hecho clic en la dirección URL.

## <a name="review-email-messages-reported-by-users"></a>Revisión de los mensajes de correo electrónico notificados por los usuarios

Supongamos que desea ver mensajes de correo electrónico que los usuarios de su organización notificaron como *No deseado*, *No no deseado* o *Phishing* a través del [complemento Mensaje](enable-the-report-message-add-in.md) de informe o el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe. Para verlos, use la vista [**EmailSubmissions** > ](threat-explorer-views.md#email--submissions) del Explorador (o detecciones en tiempo real).

1. En el Centro de cumplimiento de seguridad & (<https://protection.office.com>), elija **Explorador** **de administración** \> de amenazas (o **Detecciones en tiempo real**). (En este ejemplo se usa el Explorador).

2. En el menú **Ver**, elija **Envíos de** **correo electrónico**\>.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/explorer-view-menu-email-user-reported.png" alt-text="El menú Ver del Explorador para correos electrónicos" lightbox="../../media/explorer-view-menu-email-user-reported.png":::

3. Haga clic en **Remitente** y, a continuación, elija **Tipo de informe** **básico**\>.

4. Seleccione una opción, como **Phish**, y, a continuación, seleccione el botón **Actualizar** .

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/EmailUserReportedReportType.png" alt-text="La phish notificada por el usuario" lightbox="../../media/EmailUserReportedReportType.png":::

El informe se actualiza para mostrar los datos sobre los mensajes de correo electrónico que los usuarios de su organización notificaron como un intento de suplantación de identidad (phishing). Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar [las directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Inicio de una investigación y respuesta automatizadas

> [!NOTE]
> Las funcionalidades automatizadas de investigación y respuesta están disponibles en *Microsoft Defender para Office 365 plan 2* y *Office 365 E5*.

[La investigación y la respuesta automatizadas](automated-investigation-response-office.md) pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad dedicados a investigar y mitigar ciberataques. Además de configurar alertas que pueden desencadenar un cuaderno de estrategias de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el Explorador. Para obtener más información, vea [Ejemplo: Un administrador de seguridad desencadena una investigación desde el Explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Más formas de usar el Explorador y las detecciones en tiempo real

Además de los escenarios descritos en este artículo, tiene muchas más opciones de informes disponibles con explorer (o detecciones en tiempo real). Consulte los siguientes artículos:

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Visualización de archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](./mdo-for-spo-odb-and-teams.md)
- [Obtenga información general sobre las vistas en el Explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) para usar el Explorador o las detecciones en tiempo real.

- Explorer se incluye en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender para Office 365 plan 1.
- Planee asignar licencias para todos los usuarios que deben estar protegidos por Defender para Office 365. Las detecciones del Explorador y en tiempo real muestran los datos de detección de los usuarios con licencia.

Para ver y usar el Explorador o las detecciones en tiempo real, debe tener los permisos adecuados, como los concedidos a un administrador de seguridad o a un lector de seguridad.

- Para el Centro de cumplimiento de seguridad &, debe tener asignado uno de los siguientes roles:

  - Administración de la organización
  - Administrador de seguridad (esto se puede asignar en el centro de administración de Azure Active Directory (<https://aad.portal.azure.com>)
  - Lector de seguridad

- Para Exchange Online, debe tener uno de los siguientes roles asignados en el Centro de administración de Exchange (EAC) o [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):

  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información sobre los roles y permisos, consulte los siguientes recursos:

- [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Permisos de características de Exchange Online](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferencias entre el Explorador de amenazas y las detecciones en tiempo real

- El informe *de detecciones en tiempo real* está disponible en Defender para Office 365 plan 1. *El Explorador de amenazas* está disponible en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El Explorador de amenazas también lo hace, pero también proporciona detalles adicionales para un ataque determinado.
- Una vista *De todo el correo electrónico* está disponible en el Explorador de amenazas, pero no en el informe de detecciones en tiempo real.
- En el Explorador de amenazas se incluyen más funcionalidades de filtrado y acciones disponibles. Para obtener más información, consulte [Microsoft Defender para Office 365 Descripción del servicio: disponibilidad de características en los planes de Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="other-articles"></a>Otros artículos

[Investigación de correos electrónicos con la página Entidad de correo electrónico](mdo-email-entity-page.md)
