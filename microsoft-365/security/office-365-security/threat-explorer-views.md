---
title: Vistas en el explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre cómo usar el Explorador de amenazas y el informe de detecciones en tiempo real para investigar y responder a las amenazas en el portal Microsoft 365 Defender amenazas.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fa6e3f1c591f41544a1450def3e05259be3b6a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474957"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Vistas en el explorador de amenazas y detecciones en tiempo real

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


:::image type="content" source="../../media/explorer.png" alt-text="La página Explorador de amenazas" lightbox="../../media/explorer.png":::

[El Explorador de](threat-explorer.md) amenazas (y el informe de detecciones en tiempo real) es una herramienta eficaz y casi en tiempo real que ayuda a los equipos de operaciones de seguridad a investigar y responder a las amenazas en el portal de Microsoft 365 Defender seguridad. El Explorador (y el informe de detecciones en tiempo real) muestra información sobre el malware sospechoso y la suplantación de identidad (phish) en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.

- Si tienes [Microsoft Defender para Office 365](defender-for-office-365.md) plan 2, tienes Explorer.
- Si tienes Microsoft Defender para Office 365 plan 1, tienes detecciones en tiempo real.

Al abrir por primera vez el Explorador (o el informe de detecciones en tiempo real), la vista predeterminada muestra las detecciones de malware de correo electrónico de los últimos 7 días. En este informe también pueden mostrarse las detecciones de Microsoft Defender para Office 365, como direcciones URL malintencionadas detectadas por [Vínculos seguros](safe-links.md) y archivos malintencionados detectados por [Datos adjuntos seguros](safe-attachments.md). Este informe se puede modificar para mostrar los datos de los últimos 30 días (con una suscripción de pago de Microsoft Defender para Office 365 P2). Las suscripciones de prueba solo incluirán datos de los últimos siete días.

|Suscripción |Utilidad|Días de datos|
|---|---|---|
|Prueba de Microsoft Defender Office 365 P1|Detecciones en tiempo real|7 |
|Microsoft Defender para Office 365 P1 pagado|Detecciones en tiempo real|30|
|Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial|Explorador de amenazas|7 |
|Prueba de Microsoft Defender Office 365 P2|Explorador de amenazas|7 |
|Microsoft Defender para Office 365 P2 pagado|Explorador de amenazas|30|

> [!NOTE]
> Pronto ampliaremos el límite de búsqueda y retención de datos del Explorador (y detecciones en tiempo real) para los inquilinos de prueba de 7 a 30 días. Este cambio se realiza como parte del elemento de la hoja de ruta n. 70544 y actualmente se encuentra en una fase de implementación.

Use el menú **Ver** para cambiar la información que se muestra. La información sobre herramientas le ayudará a determinar qué vista usar.

:::image type="content" source="../../media/all-email.png" alt-text="Menú Vista del Explorador de amenazas" lightbox="../../media/all-email.png":::

Una vez que seleccione una vista, puede aplicar filtros y establecer consultas para realizar análisis adicionales. Las secciones siguientes proporcionan una breve introducción a las distintas vistas disponibles en el Explorador (o detecciones en tiempo real).

## <a name="email--malware"></a>Malware > correo electrónico

Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> malware **de correo** \> **electrónico**. Esta vista muestra información sobre los mensajes de correo electrónico que se identificaron como que contienen malware.

:::image type="content" source="../../media/detection-technology.png" alt-text="Ver datos sobre correo electrónico identificado como malware" lightbox="../../media/detection-technology.png":::

Haga **clic en** Remitente para abrir la lista de opciones de visualización. Use esta lista para ver datos por remitente, destinatarios, dominio del remitente, asunto, tecnología de detección, estado de protección y mucho más.

Por ejemplo, para ver qué acciones se realizaron en los mensajes de correo electrónico detectados, elija **Estado de protección en** la lista. Seleccione una opción y, a continuación, haga clic en el botón Actualizar para aplicar ese filtro al informe.

:::image type="content" source="../../media/ThreatExplorerProtectionStatusOptions.png" alt-text="Opciones de estado de protección contra amenazas para el Explorador de amenazas" lightbox="../../media/ThreatExplorerProtectionStatusOptions.png":::

Debajo del gráfico, vea más detalles sobre mensajes específicos. Al seleccionar un elemento de la lista, se abre un panel desplegable, donde puede obtener más información sobre el elemento seleccionado.

:::image type="content" source="../../media/ThreatExplorerMalwareItemSelectedFlyout.png" alt-text="El Explorador de amenazas con el menú desplegable abierto" lightbox="../../media/ThreatExplorerMalwareItemSelectedFlyout.png":::

## <a name="email--phish"></a>Correo electrónico > phishing

Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> **suplantación de identidad de correo** \> **electrónico**. En esta vista se muestran los mensajes de correo electrónico identificados como intentos de suplantación de identidad.

:::image type="content" source="../../media/phish.png" alt-text="Ver datos sobre correo electrónico identificados como intentos de suplantación de identidad" lightbox="../../media/phish.png":::

Haga **clic en** Remitente para abrir la lista de opciones de visualización. Use esta lista para ver los datos por remitente, destinatarios, dominio del remitente, IP del remitente, dominio url, veredicto de clic y mucho más.

Por ejemplo, para ver qué acciones se realizaron cuando las personas hicieron clic en direcciones URL que se identificaron como intentos de suplantación de identidad, elija Hacer clic en veredicto en la lista, seleccione una o más opciones y, a continuación, haga clic en el botón Actualizar.

:::image type="content" source="../../media/click-verdict.png" alt-text="Opciones de veredicto de clic para el informe de suplantación de identidad" lightbox="../../media/click-verdict.png":::

Debajo del gráfico, vea más detalles sobre mensajes específicos, clics de dirección URL, direcciones URL y origen de correo electrónico.

:::image type="content" source="../../media/ThreatExplorerEmailPhishURLs.png" alt-text="Las direcciones URL detectadas como suplantación de identidad en mensajes de correo electrónico" lightbox="../../media/ThreatExplorerEmailPhishURLs.png":::

Al seleccionar un elemento de la lista, como una dirección URL que se detectó, se abrirá un panel desplegable, donde podrá obtener más información sobre el elemento que seleccionó.

:::image type="content" source="../../media/ThreatExplorerEmailPhishURLDetails.png" alt-text="Detalles sobre una dirección URL detectada" lightbox="../../media/ThreatExplorerEmailPhishURLDetails.png":::

## <a name="email--submissions"></a>Envíos > correo electrónico

Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> **envíos** \> **de correo electrónico**. Esta vista muestra el correo electrónico que los usuarios han notificado como correo no deseado, no como correo no deseado o correo electrónico de suplantación de identidad.

:::image type="content" source="../../media/ThreatExplorerEmailUserReportedViewOptions.png" alt-text="Los mensajes de correo electrónico notificados por los usuarios" lightbox="../../media/ThreatExplorerEmailUserReportedViewOptions.png":::

Haga **clic en** Remitente para abrir la lista de opciones de visualización. Use esta lista para ver información por remitente, destinatarios, tipo de informe (la determinación del usuario de que el correo electrónico era correo no deseado, no correo no deseado o suplantación de identidad) y mucho más.

Por ejemplo, para ver información sobre los mensajes de correo electrónico que se notificaron como intentos de suplantación de identidad,  \> haga clic en Tipo de informe del **remitente, seleccione** **Suplantación** de identidad y, a continuación, haga clic en el botón Actualizar.

![Suplantación de identidad seleccionada para el filtro Tipo de informe.](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, la dirección IP del remitente, el usuario que informó del mensaje como correo no deseado, no correo no deseado o suplantación de identidad, etc.

:::image type="content" source="../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png" alt-text="Los mensajes que se informaron como intentos de suplantación de identidad" lightbox="../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png":::

Seleccione un elemento de la lista para ver detalles adicionales.

## <a name="email--all-email"></a>Correo > todo el correo electrónico

Para ver este informe, en el Explorador, elija **Ver** \> **correo electrónico** \> **todo el correo**. Esta vista muestra una vista general de la actividad del correo electrónico, incluido el correo electrónico identificado como malintencionado debido a la suplantación de identidad o malware, así como todo el correo no malintencionado (correo electrónico normal, correo no deseado y correo masivo).

> [!NOTE]
> Si recibe un error que lee **demasiados datos** para mostrar, agregue un filtro y, si es necesario, limite el intervalo de fechas que está viendo.

Para aplicar un filtro, elija **Remitente**, seleccione un elemento de la lista y, a continuación, haga clic en el botón Actualizar. En nuestro ejemplo, utilizamos la **tecnología de detección** como filtro (hay varias opciones disponibles). Ver información por remitente, dominio del remitente, destinatarios, asunto, nombre de archivo de datos adjuntos, familia de malware, estado de protección (acciones realizadas por las características y directivas de protección contra amenazas en Office 365), tecnología de detección (cómo se detectó el malware) y mucho más.

:::image type="content" source="../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png" alt-text="Ver datos sobre correo electrónico detectado mediante tecnología de detección" lightbox="../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png":::

Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, el destinatario, el remitente, el estado, etc.

## <a name="content--malware"></a>Malware > contenido

Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> **malware de** \> **contenido**. Esta vista muestra los archivos identificados como malintencionados por Microsoft Defender para Office 365 en [SharePoint Online, OneDrive para la Empresa y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Ver información por familia de malware, tecnología de detección (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o Teams).

:::image type="content" source="../../media/malware-family.png" alt-text="Ver datos sobre malware detectado" lightbox="../../media/malware-family.png":::

Debajo del gráfico, vea más detalles sobre archivos específicos, como el nombre de archivo de datos adjuntos, la carga de trabajo, el tamaño del archivo, quién modificó por última vez el archivo y mucho más.

## <a name="click-to-filter-capabilities"></a>Capacidades de hacer clic y filtrar

Con el Explorador (y las detecciones en tiempo real), puede aplicar un filtro en un clic. Haga clic en un elemento de la leyenda y ese elemento se convierte en un filtro para el informe. Por ejemplo, supongamos que estamos viendo la vista Malware en el Explorador:

:::image type="content" source="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png" alt-text="La página Explorador del portal de seguridad & cumplimiento" lightbox="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png":::

Al **hacer clic en Detonación de ATP** en este gráfico, se muestra una vista como esta:

:::image type="content" source="../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png" alt-text="El Explorador filtrado para mostrar solo Defender para obtener Office 365 detonación" lightbox="../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png":::

En esta vista, ahora estamos buscando datos para los archivos que fueron detonados [por Caja fuerte datos adjuntos](safe-attachments.md). Debajo del gráfico, podemos ver detalles sobre mensajes de correo electrónico específicos que tenían datos adjuntos detectados por Caja fuerte datos adjuntos.

:::image type="content" source="../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png" alt-text="Detalles específicos sobre los mensajes de correo electrónico con datos adjuntos detectados" lightbox="../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png":::

Al seleccionar uno o varios elementos, se activa el **menú Acciones,** que ofrece varias opciones entre las que elegir para los elementos seleccionados.

:::image type="content" source="../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png" alt-text="Proceso de selección de un elemento que activa el menú Acciones" lightbox="../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png":::

La capacidad de filtrar en un clic y navegar a detalles específicos puede ahorrarle mucho tiempo en investigar amenazas.

## <a name="queries-and-filters"></a>Consultas y filtros

El Explorador (así como el informe de detecciones en tiempo real) tiene varios filtros eficaces y capacidades de consulta que le permiten profundizar en detalles, como los principales usuarios dirigidos, las principales familias de malware, la tecnología de detección y mucho más. Cada tipo de informe ofrece una variedad de formas de ver y explorar datos.

> [!IMPORTANT]
> No use caracteres comodín, como un asterisco o un signo de interrogación, en la barra de consultas del Explorador (o detecciones en tiempo real). Al buscar mensajes de correo electrónico en el campo **Asunto** , el Explorador (o detecciones en tiempo real) realizará coincidencias parciales y dará resultados similares a una búsqueda de caracteres comodín.
