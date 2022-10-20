---
title: Vistas en el explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Obtenga información sobre cómo usar el Explorador de amenazas y el informe de detecciones en tiempo real para investigar y responder a amenazas en el portal de Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: dae696dea94a821a2fd3ae7b9fc6b175587bb246
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628453"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Vistas en el explorador de amenazas y detecciones en tiempo real

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

:::image type="content" source="../../media/explorer.png" alt-text="Página Explorador de amenazas" lightbox="../../media/explorer.png":::

[El Explorador de amenazas](threat-explorer.md) (y el informe de detecciones en tiempo real) es una herramienta eficaz casi en tiempo real para ayudar a los equipos de operaciones de seguridad a investigar y responder a amenazas en el portal de Microsoft 365 Defender. El Explorador (y el informe de detecciones en tiempo real) muestra información sobre sospechas de malware y fish en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.

- Si tiene [Microsoft Defender para Office 365](defender-for-office-365.md) Plan 2, tiene Explorador.
- Si tiene Microsoft Defender para Office 365 Plan 1, tiene detecciones en tiempo real.

Al abrir por primera vez el Explorador (o el informe de detecciones en tiempo real), la vista predeterminada muestra las detecciones de malware por correo electrónico de los últimos 7 días. En este informe también pueden mostrarse las detecciones de Microsoft Defender para Office 365, como direcciones URL malintencionadas detectadas por [Vínculos seguros](safe-links.md) y archivos malintencionados detectados por [Datos adjuntos seguros](safe-attachments.md). Este informe se puede modificar para mostrar los datos de los últimos 30 días (con una suscripción de pago de Microsoft Defender para Office 365 P2). Las suscripciones de prueba solo incluirán datos de los últimos siete días.

|Suscripción |Utilidad|Días de datos|
|---|---|---|
|prueba de Microsoft Defender para Office 365 P1|Detecciones en tiempo real|7 |
|Microsoft Defender para Office 365 P1 pagado|Detecciones en tiempo real|30|
|prueba de pago de Microsoft Defender para Office 365 P1 Defender para Office 365 P2|Explorador de amenazas|7 |
|Microsoft Defender para Office 365 versión de prueba de P2|Explorador de amenazas|7 |
|Microsoft Defender para Office 365 P2 pagado|Explorador de amenazas|30|

> [!NOTE]
> Pronto ampliaremos la retención de datos del Explorador (y las detecciones en tiempo real) y el límite de búsqueda para los inquilinos de prueba de 7 a 30 días. Este cambio se está realizando como parte del punto de hoja de ruta nº 70544 y se encuentra actualmente en una fase de implementación.

Use el menú **Ver** para cambiar la información que se muestra. La información sobre herramientas le ayudará a determinar qué vista usar.

:::image type="content" source="../../media/all-email.png" alt-text="Menú Vista del Explorador de amenazas" lightbox="../../media/all-email.png":::

Una vez que seleccione una vista, puede aplicar filtros y establecer consultas para realizar análisis adicionales. En las secciones siguientes se proporciona una breve introducción a las distintas vistas disponibles en el Explorador (o en las detecciones en tiempo real).

## <a name="email--malware"></a>malware Email >

Para ver este informe, en explorador (o detecciones en tiempo real), elija **Ver** \> **Email** \> **malware**. En esta vista se muestra información sobre los mensajes de correo electrónico que se identificaron como que contienen malware.

:::image type="content" source="../../media/detection-technology.png" alt-text="Ver datos sobre el correo electrónico identificado como malware" lightbox="../../media/detection-technology.png":::

Haga clic en **Remitente** para abrir la lista de opciones de visualización. Use esta lista para ver los datos por remitente, destinatarios, dominio del remitente, asunto, tecnología de detección, estado de protección, etc.

Por ejemplo, para ver qué acciones se realizaron en los mensajes de correo electrónico detectados, elija **Estado de protección** en la lista. Seleccione una opción y, a continuación, haga clic en el botón Actualizar para aplicar ese filtro al informe.

:::image type="content" source="../../media/ThreatExplorerProtectionStatusOptions.png" alt-text="Opciones de estado de protección contra amenazas para el Explorador de amenazas" lightbox="../../media/ThreatExplorerProtectionStatusOptions.png":::

Debajo del gráfico, vea más detalles sobre mensajes específicos. Al seleccionar un elemento de la lista, se abre un panel flotante, donde puede obtener más información sobre el elemento seleccionado.

:::image type="content" source="../../media/ThreatExplorerMalwareItemSelectedFlyout.png" alt-text="El Explorador de amenazas con el control flotante abierto" lightbox="../../media/ThreatExplorerMalwareItemSelectedFlyout.png":::

## <a name="email--phish"></a>Email > Phish

Para ver este informe, en explorador (o detecciones en tiempo real), elija **Ver** \> **Email** \> **Phish**. En esta vista se muestran los mensajes de correo electrónico identificados como intentos de suplantación de identidad ( phishing).

:::image type="content" source="../../media/phish.png" alt-text="Ver datos sobre correo electrónico identificados como intentos de suplantación de identidad" lightbox="../../media/phish.png":::

Haga clic en **Remitente** para abrir la lista de opciones de visualización. Use esta lista para ver los datos por remitente, destinatarios, dominio del remitente, dirección IP del remitente, dominio url, veredicto de clics y mucho más.

Por ejemplo, para ver qué acciones se realizaron cuando las personas hicieron clic en las direcciones URL que se identificaron como intentos de suplantación de identidad (phishing), elija **Click verdict (Hacer clic en veredicto** ) en la lista, seleccione una o varias opciones y, a continuación, haga clic en el botón Actualizar.

:::image type="content" source="../../media/click-verdict.png" alt-text="Las opciones Click verdict (Hacer clic en veredicto) del informe Phish" lightbox="../../media/click-verdict.png":::

Debajo del gráfico, vea más detalles sobre mensajes específicos, clics de dirección URL, direcciones URL y origen del correo electrónico.

:::image type="content" source="../../media/ThreatExplorerEmailPhishURLs.png" alt-text="Las direcciones URL detectadas como phish en los mensajes de correo electrónico" lightbox="../../media/ThreatExplorerEmailPhishURLs.png":::

Al seleccionar un elemento de la lista, como una dirección URL que se detectó, se abre un panel flotante, donde puede obtener más información sobre el elemento que seleccionó.

:::image type="content" source="../../media/ThreatExplorerEmailPhishURLDetails.png" alt-text="Detalles sobre una dirección URL detectada" lightbox="../../media/ThreatExplorerEmailPhishURLDetails.png":::

## <a name="email--submissions"></a>envíos de Email >

Para ver este informe, en explorador (o detecciones en tiempo real), elija **Ver** \> **Email** \> **envíos**. En esta vista se muestra el correo electrónico que los usuarios han notificado como correo no deseado, no como correo no deseado o correo electrónico de phishing.

:::image type="content" source="../../media/ThreatExplorerEmailUserReportedViewOptions.png" alt-text="Los mensajes de Email notificados por los usuarios" lightbox="../../media/ThreatExplorerEmailUserReportedViewOptions.png":::

Haga clic en **Remitente** para abrir la lista de opciones de visualización. Use esta lista para ver la información por remitente, destinatarios, tipo de informe (la determinación del usuario de que el correo electrónico era no deseado, no basura o phish) y mucho más.

Por ejemplo, para ver información sobre los mensajes de correo electrónico que se notificaron como intentos de suplantación de identidad (phishing), haga clic en **Tipo de informe** **del remitente**\>, seleccione **Phish** y, a continuación, haga clic en el botón Actualizar.

![Phish seleccionado para el filtro Tipo de informe.](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, la dirección IP del remitente, el usuario que notificó el mensaje como no deseado, no como correo no deseado o phish, etc.

:::image type="content" source="../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png" alt-text="Los mensajes que se notificaron como intentos de suplantación de identidad" lightbox="../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png":::

Seleccione un elemento de la lista para ver detalles adicionales.

## <a name="email--all-email"></a>Email > todo el correo electrónico

Para ver este informe, en el Explorador, elija **Ver** \> **Email** \> **todo el correo**. Esta vista muestra una vista general de la actividad de correo electrónico, incluido el correo electrónico identificado como malintencionado debido a phishing o malware, así como todo el correo no malintencionado (correo electrónico normal, correo no deseado y correo masivo).

> [!NOTE]
> Si recibe un error que lee **Demasiados datos para mostrar**, agregue un filtro y, si es necesario, limite el intervalo de fechas que está viendo.

Para aplicar un filtro, elija **Remitente**, seleccione un elemento de la lista y, a continuación, haga clic en el botón Actualizar. En nuestro ejemplo, usamos **la tecnología de detección** como filtro (hay varias opciones disponibles). Vea información por remitente, dominio del remitente, destinatarios, asunto, nombre de archivo adjunto, familia de malware, estado de protección (acciones realizadas por las características y directivas de protección contra amenazas en Office 365), tecnología de detección (cómo se detectó el malware) y mucho más.

:::image type="content" source="../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png" alt-text="Ver datos sobre el correo electrónico detectado por la tecnología de detección" lightbox="../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png":::

Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, el destinatario, el remitente, el estado, etc.

## <a name="content--malware"></a>Malware de > de contenido

Para ver este informe, en explorador (o detecciones en tiempo real), elija **Ver** \> **malware de contenido**\>. En esta vista se muestran los archivos identificados como malintencionados por [Microsoft Defender para Office 365 en SharePoint Online, OneDrive para la Empresa y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Vea información por familia de malware, tecnología de detección (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o Teams).

:::image type="content" source="../../media/malware-family.png" alt-text="Ver datos sobre malware detectado" lightbox="../../media/malware-family.png":::

Debajo del gráfico, vea más detalles sobre archivos específicos, como el nombre de archivo adjunto, la carga de trabajo, el tamaño del archivo, quién modificó por última vez el archivo, etc.

## <a name="click-to-filter-capabilities"></a>Funcionalidades de hacer clic para filtrar

Con el Explorador (y las detecciones en tiempo real), puede aplicar un filtro con un clic. Haga clic en un elemento de la leyenda y ese elemento se convierte en un filtro para el informe. Por ejemplo, supongamos que estamos viendo la vista Malware en el Explorador:

:::image type="content" source="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png" alt-text="La página Explorador del portal de cumplimiento de & de seguridad" lightbox="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png":::

Al hacer clic en **Detonación de ATP** en este gráfico, se obtiene una vista similar a la siguiente:

:::image type="content" source="../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png" alt-text="Explorador filtrado para mostrar solo Defender para Office 365 resultados de detonación" lightbox="../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png":::

En esta vista, ahora estamos examinando los datos de los archivos detonados por [datos adjuntos seguros](safe-attachments.md). Debajo del gráfico, podemos ver detalles sobre mensajes de correo electrónico específicos que tenían datos adjuntos detectados por datos adjuntos seguros.

:::image type="content" source="../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png" alt-text="Detalles específicos sobre los mensajes de correo electrónico con datos adjuntos detectados" lightbox="../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png":::

Al seleccionar uno o varios elementos, se activa el menú **Acciones** , que ofrece varias opciones entre las que elegir para los elementos seleccionados.

:::image type="content" source="../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png" alt-text="Proceso de selección de un elemento que activa el menú Acciones" lightbox="../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png":::

La capacidad de filtrar con un clic y navegar a detalles específicos puede ahorrar mucho tiempo en la investigación de amenazas.

## <a name="queries-and-filters"></a>Consultas y filtros

Explorer (así como el informe de detecciones en tiempo real) tiene varios filtros eficaces y funcionalidades de consulta que le permiten profundizar en detalles, como los usuarios de destino superior, las principales familias de malware, la tecnología de detección y mucho más. Cada tipo de informe ofrece una variedad de formas de ver y explorar datos.

> [!IMPORTANT]
> No use caracteres comodín, como un asterisco o un signo de interrogación, en la barra de consulta del Explorador (o detecciones en tiempo real). Al buscar mensajes de correo electrónico en el **campo Asunto** , el Explorador (o las detecciones en tiempo real) realizarán coincidencias parciales y producirán resultados similares a una búsqueda con caracteres comodín.
