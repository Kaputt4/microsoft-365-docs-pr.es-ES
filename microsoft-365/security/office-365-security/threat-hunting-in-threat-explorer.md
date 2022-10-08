---
title: Búsqueda de amenazas en el Explorador de amenazas para Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Use el Explorador de amenazas o las detecciones en tiempo real en el portal de Microsoft 365 Defender para investigar y responder a las amenazas de forma eficaz.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 4e581dadd7b17552aee277fa978b788f914607f3
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68054762"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a>Búsqueda de amenazas en el Explorador de amenazas para Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo:

- [Tutorial del Explorador de amenazas](#threat-explorer-walk-through)
- [Email investigación](#email-investigation)
- [Email corrección](#email-remediation)
- [Mejoras en la experiencia de búsqueda de amenazas](#improvements-to-threat-hunting-experience)

> [!NOTE]
> Esto forma parte de una **serie de 3 artículos** sobre **el Explorador de amenazas (Explorer),** **la seguridad del correo electrónico** **y las detecciones del Explorador y en tiempo real** (como las diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son [Email seguridad con el Explorador de amenazas](email-security-in-microsoft-defender.md) y [el Explorador de amenazas y las detecciones en tiempo real](real-time-detections.md).

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si su organización tiene [Microsoft Defender para Office 365](defender-for-office-365.md) y tiene los [permisos](#required-licenses-and-permissions), puede usar el **Explorador** o **las detecciones en tiempo real** para detectar y corregir amenazas.

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & colaboración** y, a continuación, elija **Explorador** o **Detecciones en tiempo real**. Para ir directamente a la página, use <https://security.microsoft.com/threatexplorer> o <https://security.microsoft.com/realtimereports>.

Con estas herramientas, puede:

- Ver el malware detectado por las características de seguridad de Microsoft 365
- Ver la dirección URL de phishing y hacer clic en datos de veredicto
- Inicio de un proceso de investigación y respuesta automatizado desde una vista en el Explorador
- Investigar el correo electrónico malintencionado y mucho más

Para obtener más información, consulte [Email seguridad con el Explorador de amenazas](email-security-in-microsoft-defender.md).

Vea este breve vídeo para aprender a buscar e investigar amenazas basadas en el correo electrónico y la colaboración mediante Microsoft Defender para Office 365. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWyPRU]

## <a name="threat-explorer-walk-through"></a>Tutorial del Explorador de amenazas

En Microsoft Defender para Office 365, hay dos planes de suscripción: plan 1 y plan 2. Las herramientas de búsqueda de amenazas operadas manualmente existen en ambos planes, con nombres diferentes y con diferentes funcionalidades.

Defender para Office 365 Plan 1 usa *detecciones en tiempo real*, que es un subconjunto de la herramienta de búsqueda *explorador de amenazas* del plan 2. En esta serie de artículos, la mayoría de los ejemplos se crearon con el Explorador de amenazas completo. Los administradores deben probar los pasos de las detecciones en tiempo real para ver dónde se aplican.

Después de ir al **Explorador**, de forma predeterminada, llegará a la página **Malware** , pero use la lista desplegable **Ver** para familiarizarse con las opciones. Si estás cazando a Phish o profundizando en una campaña de amenazas, elige esas vistas.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/view-drop-down.png" alt-text="La lista desplegable Ver en el Explorador de amenazas" lightbox="../../media/view-drop-down.png":::

Una vez que una persona de operaciones de seguridad (s ops) selecciona los datos que desea ver, si el ámbito es una vista estrecha como **envíos** de usuarios o una vista más amplia, como **Todo el correo electrónico**, puede usar el botón **Remitente** para filtrar más. No olvide seleccionar Actualizar para completar las acciones de filtrado.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/sender-drop-down.png" alt-text="Botón Remitente en el Explorador de amenazas" lightbox="../../media/sender-drop-down.png":::

El enfoque de refinamiento en el Explorador o la detección en tiempo real se puede considerar en capas. El primero es **Ver**. El segundo se puede considerar como un *foco filtrado*. Por ejemplo, puede volver a rastrear los pasos que tomó para encontrar una amenaza registrando sus decisiones como esta: Para encontrar el problema en el Explorador, **he elegido la vista Malware con un foco de filtro Destinatario**. Esto facilita la reanudación de los pasos.

> [!TIP]
> Si las operaciones por segundo usan **etiquetas** para marcar las cuentas que consideran destinos de alto valor, pueden realizar selecciones como *La vista de phish con un foco de filtro Etiquetas (incluir un intervalo de fechas si se usa).* Esto les mostrará los intentos de suplantación de identidad dirigidos a sus objetivos de usuario de alto valor durante un intervalo de tiempo (por ejemplo, las fechas en las que ciertos ataques de suplantación de identidad están ocurriendo mucho para su sector).

Los refinamientos se pueden realizar en intervalos de fechas mediante los controles de intervalo de fechas. Aquí puede ver el Explorador en la vista **Malware** , con un foco **de filtro de tecnología de detección** . Pero es el botón **de filtro Avanzado** el que permite a los equipos de Operaciones sec profundizar.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/advanced-filter.png" alt-text="Filtro avanzado en el Explorador de amenazas" lightbox="../../media/advanced-filter.png":::

Al hacer clic en el **filtro Avanzado** aparece un panel que permitirá a los cazadores de operaciones sec crear consultas por sí mismos, lo que les permite incluir o excluir la información que necesitan ver. Tanto el gráfico como la tabla de la página Explorador reflejarán sus resultados.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-chart-table.png" alt-text="Resultados de una consulta" lightbox="../../media/threat-explorer-chart-table.png":::

Use el botón **Opciones de columna** para obtener el tipo de información de la tabla que sería más útil:

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-column-options.png" alt-text="Botón Opciones de columna resaltado" lightbox="../../media/threat-explorer-column-options.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/column-options.png" alt-text="Las opciones disponibles en Columnas" lightbox="../../media/column-options.png":::

En el mismo mien, asegúrese de probar las opciones de visualización. Diferentes audiencias reaccionarán bien a diferentes presentaciones de los mismos datos. Para algunos espectadores, el mapa **de orígenes de Email** puede mostrar que una amenaza está generalizada o discreta más rápidamente que la opción **de visualización Campaña** situada junto a ella. Las operaciones sec pueden usar estas pantallas para destacar mejor la necesidad de seguridad y protección, o para una comparación posterior, para demostrar la eficacia de sus acciones.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-origin-map.png" alt-text="Mapa de orígenes de Email" lightbox="../../media/threat-explorer-email-origin-map.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-campaign-display.png" alt-text="Opciones de presentación de campaña" lightbox="../../media/threat-explorer-campaign-display.png":::

### <a name="email-investigation"></a>Email investigación

Cuando vea un correo electrónico sospechoso, haga clic en el nombre para expandir el control flotante de la derecha. Aquí está disponible el banner que permite a Sec Ops ver la [página de entidad de correo electrónico](mdo-email-entity-page.md) .

La página de entidad de correo electrónico recopila contenido que se puede encontrar en **Detalles**, **Datos adjuntos**, **Dispositivos**, pero que incluye datos más organizados. Esto incluye elementos como los resultados de DMARC, la visualización de texto sin formato del encabezado de correo electrónico con una opción de copia, la información de veredicto sobre los datos adjuntos que se detonaron de forma segura y los archivos que se quitaron esas detonaciones (pueden incluir direcciones IP que se han contactado y capturas de pantalla de páginas o archivos). Las direcciones URL y sus veredictos también se enumeran con detalles similares notificados.

Cuando llegue a esta fase, la página de la entidad de correo electrónico será fundamental para el paso final: *corrección*.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-entity-page.png" alt-text="Página de la entidad de correo electrónico" lightbox="../../media/threat-explorer-email-entity-page.png":::

> [!TIP]
> Para obtener más información sobre la página de entidad de correo electrónico enriquecida (que se muestra a continuación en la pestaña **Análisis**), incluidos los resultados de los datos adjuntos detonados, los resultados de las direcciones URL incluidas y la versión preliminar Email segura, haga clic [aquí](mdo-email-entity-page.md).

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-analysis-tab.png" alt-text="Pestaña Análisis de la página de entidad de correo electrónico" lightbox="../../media/threat-explorer-analysis-tab.png":::

### <a name="email-remediation"></a>Email corrección

Una vez que una persona de Operaciones por segundo determina que un correo electrónico es una amenaza, el siguiente paso de detección en tiempo real o Explorador se ocupa de la amenaza y la corrige. Para ello, vuelva al Explorador de amenazas, active la casilla del correo electrónico del problema y use el botón **Acciones** .

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-button.png" alt-text="Botón Acciones en el Explorador de amenazas" lightbox="../../media/threat-explorer-email-actions-button.png":::

Aquí, el analista puede realizar acciones como informar del correo como spam, phishing o malware, ponerse en contacto con los destinatarios o realizar investigaciones adicionales que pueden incluir la activación de cuadernos de estrategias de investigación y respuesta automatizadas (o AIR) (si tiene plan 2). O bien, el correo también se puede notificar como limpio.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-drop-down.png" alt-text="Menú desplegable Acciones" lightbox="../../media/threat-explorer-email-actions-drop-down.png":::

## <a name="improvements-to-threat-hunting-experience"></a>Mejoras en la experiencia de búsqueda de amenazas

### <a name="alert-id"></a>Identificador de alerta

Al navegar desde una alerta al Explorador de amenazas, la **vista** se filtrará por **identificador de alerta**. Esto también se aplica en la detección en tiempo real. Se muestran los mensajes relevantes para la alerta específica y un total de correo electrónico (un recuento). Podrá ver si un mensaje formaba parte de una alerta, así como navegar desde ese mensaje a la alerta relacionada.

Por último, el identificador de alerta se incluye en la dirección URL, por ejemplo: `https://https://security.microsoft.com/viewalerts`

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-Filter.png" alt-text="Filtro para el identificador de alerta" lightbox="../../media/AlertID-Filter.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-DetailsFlyout.png" alt-text="El control flotante Id. de alerta en detalles" lightbox="../../media/AlertID-DetailsFlyout.png":::

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a>Extensión de la retención de datos del Explorador (y detecciones en tiempo real) y el límite de búsqueda para inquilinos de prueba

Como parte de este cambio, los analistas podrán buscar y filtrar los datos de correo electrónico durante 30 días (se aumenta desde siete días) en el Explorador de amenazas y las detecciones en tiempo real para los inquilinos de prueba de Defender para Office P1 y P2. Esto no afecta a los inquilinos de producción para los clientes P1 y P2 E5, donde el valor predeterminado de retención ya es de 30 días.

### <a name="updated-export-limit"></a>Límite de exportación actualizado

El número de registros de correos electrónicos que se pueden exportar desde el Explorador de amenazas es ahora de 200 000 (en lugar de 9990). El conjunto de columnas que se pueden exportar no cambia.

### <a name="tags-in-threat-explorer"></a>Etiquetas en el Explorador de amenazas

> [!NOTE]
> La característica de etiquetas de usuario está en versión preliminar y es posible que no esté disponible para todos los usuarios. Además, las versiones preliminares están sujetas a cambios. Para obtener información sobre la programación de lanzamiento, consulte el plan de desarrollo de Microsoft 365.

Las etiquetas de usuario identifican grupos específicos de usuarios en Microsoft Defender para Office 365. Para obtener más información sobre las etiquetas, incluidas las licencias y la configuración, consulte [Etiquetas de usuario](user-tags.md).

En el Explorador de amenazas, puede ver información sobre las etiquetas de usuario en las siguientes experiencias.

#### <a name="email-grid-view"></a>Email vista de cuadrícula

Cuando los analistas examinan la columna **Etiquetas** de la cuadrícula de correo electrónico, ven todas las etiquetas que se han aplicado a buzones de remitente o destinatario. De forma predeterminada, las etiquetas del sistema, como *las cuentas de prioridad* , se muestran primero.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-grid.png" alt-text="Etiquetas de filtro en la vista de cuadrícula de correo electrónico" lightbox="../../media/tags-grid.png":::

#### <a name="filtering"></a>Filtrado

Las etiquetas se pueden usar como filtros. Busque solo entre cuentas de prioridad o use escenarios de etiquetas de usuario específicos de esta manera. También puede excluir los resultados que tienen ciertas etiquetas. Combine etiquetas con otros filtros e intervalos de fechas para restringir el ámbito de investigación.

[![Etiquetas de filtro.](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-filter-not.png" alt-text="Las etiquetas que no se han filtrado" lightbox="../../media/tags-filter-not.png":::

#### <a name="email-detail-flyout"></a>Email control flotante de detalles

Para ver las etiquetas individuales del remitente y el destinatario, seleccione un correo electrónico para abrir el control flotante de detalles del mensaje. En la pestaña **Resumen** , las etiquetas remitente y destinatario se muestran por separado. La información sobre etiquetas individuales para remitente y destinatario se puede exportar como datos CSV.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-flyout.png" alt-text="Etiquetas de detalles de Email" lightbox="../../media/tags-flyout.png":::

La información de etiquetas también se muestra en el control flotante Clics de dirección URL. Para verlo, vaya a la pestaña Phish o All Email view > **URL** or **URL Clicks (Direcciones URL o url).** Seleccione un control flotante de dirección URL individual para ver detalles adicionales sobre los clics de esa dirección URL, incluidas las etiquetas asociadas a ese clic.

### <a name="updated-timeline-view"></a>Vista de escala de tiempo actualizada

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-urls.png" alt-text="Las etiquetas url" lightbox="../../media/tags-urls.png":::
>
Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).

## <a name="extended-capabilities"></a>Funcionalidades extendidas

### <a name="top-targeted-users"></a>Usuarios de destino superior

Top Malware Families muestra los **usuarios de destino principales** en la sección Malware. Los usuarios de destino superior también se ampliarán a través de las vistas Phish y All Email. Los analistas podrán ver los cinco primeros usuarios de destino, junto con el número de intentos de cada usuario en cada vista.

Las operaciones de seguridad pueden exportar la lista de usuarios de destino, hasta un límite de 3000, junto con el número de intentos realizados, para el análisis sin conexión de cada vista de correo electrónico. Además, al seleccionar el número de intentos (por ejemplo, 13 intentos en la imagen siguiente) se abrirá una vista filtrada en el Explorador de amenazas, para que pueda ver más detalles en los correos electrónicos y las amenazas para ese usuario.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Top_Targeted_Users.png" alt-text="Los usuarios que más se han dirigido" lightbox="../../media/Top_Targeted_Users.png":::

### <a name="exchange-transport-rules"></a>Reglas de transporte de Exchange

El equipo de operaciones de seguridad podrá ver todas las reglas de transporte de Exchange (o reglas de flujo de correo) aplicadas a un mensaje, en la vista de cuadrícula de Email. Seleccione **Opciones de columna** en la cuadrícula y, a continuación, **Agregar regla de transporte de Exchange** en las opciones de columna. La opción Reglas de transporte de Exchange también está visible en el control flotante **Detalles** del correo electrónico.

Aparecen nombres y GUID de las reglas de transporte aplicadas al mensaje. Los analistas podrán buscar mensajes mediante el nombre de la regla de transporte. Se trata de una búsqueda CONTAINS, lo que significa que también puede realizar búsquedas parciales.

> [!IMPORTANT]
> La disponibilidad de nombres y búsqueda de reglas de transporte de Exchange depende del rol específico que se le haya asignado. Debe tener uno de los siguientes roles o permisos para ver los nombres de las reglas de transporte y la búsqueda. Sin embargo, incluso sin los roles o permisos siguientes, un analista puede ver la etiqueta de regla de transporte y la información del GUID en los detalles de Email. Otras experiencias de visualización de registros en Email Grids, Email controles flotantes, filtros y exportación no se ven afectados.
>
> - solo Exchange Online: prevención de pérdida de datos: todos
> - solo Exchange Online - O365SupportViewConfig: Todos
> - Microsoft Azure Active Directory o Exchange Online: Administración de seguridad: todos
> - Azure Active Directory o Exchange Online: Lector de seguridad: todos
> - solo Exchange Online: reglas de transporte: todas
> - solo Exchange Online: configuración de View-Only: todos
>
> Dentro de la cuadrícula de correo electrónico, el control flotante Detalles y CSV exportado, los ETR se presentan con un nombre o GUID, como se muestra a continuación.
>
> > [!div class="mx-imgBorder"]
> > :::image type="content" source="../../media/ETR_Details.png" alt-text="Las reglas del transporte de Exchange" lightbox="../../media/ETR_Details.png":::

### <a name="inbound-connectors"></a>Conectores entrantes

Los conectores son una colección de instrucciones que personalizan cómo fluye el correo electrónico hacia y desde su organización de Microsoft 365 o Office 365. Permiten aplicar restricciones o controles de seguridad. En el Explorador de amenazas, puede ver los conectores relacionados con un correo electrónico y buscar correos electrónicos mediante nombres de conector.

La búsqueda de conectores es una consulta CONTAINS, lo que significa que las búsquedas parciales de palabras clave pueden funcionar:

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Connector_Details.png" alt-text="Detalles del conector" lightbox="../../media/Connector_Details.png":::

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) para usar el Explorador o las detecciones en tiempo real.

- Explorer se incluye en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender para Office 365 plan 1.
- Planee asignar licencias para todos los usuarios que deben estar protegidos por Defender para Office 365. Las detecciones del Explorador y en tiempo real muestran los datos de detección de los usuarios con licencia.

Para ver y usar el Explorador o las detecciones en tiempo real, debe tener los permisos siguientes:

- En el portal de Microsoft 365 Defender:
  - Administración de la organización
  - Administrador de seguridad (esto se puede asignar en el Centro de administración de Azure Active Directory (<https://aad.portal.azure.com>)
  - Lector de seguridad
- En Exchange Online:
  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información sobre los roles y permisos, consulte los siguientes recursos:

- [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Más información

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Visualización de archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Obtenga información general sobre las vistas en el Explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](automated-investigation-response-office.md)
- [Investigación de correos electrónicos con la página de entidad Email](mdo-email-entity-page.md)
