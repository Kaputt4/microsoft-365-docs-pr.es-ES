---
title: Seguridad de correo electrónico con el Explorador de amenazas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Ver e investigar intentos de suplantación de identidad de malware.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb62961bb26b079c508cbd5bc559a95d172cff86
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029890"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Seguridad de correo electrónico con el Explorador de amenazas en Microsoft Defender para Office 365

En este artículo:

- [Ver malware detectado en el correo electrónico](#view-malware-detected-in-email)
- [Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto](#view-phishing-url-and-click-verdict-data)
- [Iniciar la investigación y respuesta automatizadas](#start-automated-investigation-and-response)

> [!NOTE]
> Esto forma parte de una serie de **3** artículos sobre explorador de amenazas **(Explorer),** seguridad de correo electrónico y **conceptos** básicos de detecciones de Explorador y tiempo real (como diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son [Búsqueda](threat-hunting-in-threat-explorer.md) de amenazas en el Explorador de amenazas y explorador de amenazas y conceptos básicos de detecciones [en tiempo real.](real-time-detections.md)

En este artículo se explica cómo ver e investigar los intentos de malware y suplantación de identidad detectados en el correo electrónico por Microsoft 365 de seguridad.

**Se aplica a:**

- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Ver malware detectado en el correo electrónico

Para ver el malware detectado en el correo electrónico ordenado por Microsoft 365, use la vista Correo [> malware](threat-explorer-views.md#email--malware) del Explorador (o detecciones en tiempo real). El malware es la vista predeterminada, por lo que puede seleccionarse tan pronto como abra el Explorador.

1. En el portal Microsoft 365 Defender ( ), elija Correo & explorador de <https://security.microsoft.com> **colaboración** \>  (o **Detecciones en tiempo real**; En este ejemplo se usa Explorer).

   A partir de aquí, comience en la vista, elija un período de tiempo determinado para investigar (si es necesario) y centre los filtros, según el recorrido [del Explorador.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)

2. En la **lista** desplegable Ver, compruebe que **el** malware de correo electrónico \>  está seleccionado.

3. Haga **clic en Remitente** y, a continuación, elija **Tecnología** básica \> **de detección** en la lista desplegable.

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="Tecnología de detección de malware":::

   Las tecnologías de detección ahora están disponibles como filtros para el informe.

4. Elija una opción y, a continuación, haga clic en **Actualizar** para aplicar ese filtro (no actualice la ventana del explorador).

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="tecnología de detección seleccionada":::

   El informe se actualiza para mostrar los resultados que el malware detectó en el correo electrónico, mediante la opción de tecnología seleccionada. Desde aquí, puede realizar más análisis.

## <a name="view-phishing-url-and-click-verdict-data"></a>Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto

Puede ver los intentos de suplantación de identidad a través de direcciones URL en el correo electrónico, incluida una lista de direcciones URL permitidas, bloqueadas e invalidadas. Para identificar las direcciones URL en las que [se hizo](safe-links.md) clic, Caja fuerte deben configurarse los vínculos. Asegúrese de configurar las directivas de [vínculos](set-up-safe-links-policies.md) Caja fuerte para la protección con tiempo de clic y el registro de veredictos de clics Caja fuerte vínculos.

1. En el portal Microsoft 365 Defender ( ), elija Correo & explorador de <https://security.microsoft.com> **colaboración** \>  (o **Detecciones en tiempo real**; En este ejemplo se usa Explorer).

2. En la **lista** desplegable Ver, elija **Email** \> **Phish**.

   > [!div class="mx-imgBorder"]
   > ![Menú Ver para explorador en contexto de suplantación de identidad](../../media/ExplorerViewEmailPhishMenu.png)

3. Haga **clic en Remitente** y, a continuación, elija Direcciones URL **Haga** clic en \> **Veredicto** en la lista desplegable.

4. En las opciones que aparecen, seleccione una o más opciones, como **Bloqueado** y Bloquear invalidados y, a continuación, haga clic en **Actualizar** (no actualice la ventana del explorador).

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="Direcciones URL y veredictos de clic":::

   El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la pestaña **Direcciones** URL del informe:

   - **Las direcciones URL principales** son las direcciones URL de los mensajes que se filtraron hacia abajo y la acción de entrega de correo electrónico cuenta para cada dirección URL. En la vista Correo electrónico de suplantación de identidad, esta lista suele contener direcciones URL legítimas. Los atacantes incluyen una combinación de direcciones URL buenas y malas en sus mensajes para intentar que se entreguen, pero hacen que los vínculos malintencionados parezcan más interesantes. La tabla de direcciones URL se ordena por recuento total de correo electrónico, pero esta columna está oculta para simplificar la vista.

   - **Los clics principales** son las Caja fuerte direcciones URL ajustadas por vínculos que se han hecho clic, ordenadas por recuento total de clics. Esta columna tampoco se muestra para simplificar la vista. Los recuentos totales por columna indican Caja fuerte recuento de veredictos de clics de vínculos para cada dirección URL en la que se ha hecho clic. En la vista Correo electrónico de suplantación de identidad, normalmente son direcciones URL sospechosas o malintencionadas. Pero la vista podría incluir direcciones URL que no son amenazas pero que están en mensajes de suplantación de identidad. Los clics de dirección URL en vínculos sin envolver no se muestran aquí.

   Las dos tablas de dirección URL muestran las direcciones URL principales en los mensajes de correo electrónico de suplantación de identidad por acción de entrega y ubicación. Las tablas muestran los clics de dirección URL bloqueados o visitados a pesar de una advertencia, por lo que puede ver qué posibles vínculos no se han presentado a los usuarios y que los usuarios han hecho clic. Desde aquí, puede realizar más análisis. Por ejemplo, debajo del gráfico puede ver las direcciones URL principales de los mensajes de correo electrónico bloqueados en el entorno de su organización.

   > [!div class="mx-imgBorder"]
   > ![Direcciones URL del explorador bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo desplegable Dirección URL, el filtrado de mensajes de correo electrónico se quita para mostrar la vista completa de la exposición de la dirección URL en el entorno. Esto le permite filtrar los mensajes de correo electrónico que le preocupan en el Explorador, buscar direcciones URL específicas que son amenazas potenciales y, a continuación, ampliar la comprensión de la exposición de la dirección URL en su entorno (a través del cuadro de diálogo Detalles de dirección URL) sin tener que agregar filtros de dirección URL a la propia vista Explorador.

### <a name="interpretation-of-click-verdicts"></a>Interpretación de veredictos de clic

En los menús desplegables Correo electrónico o URL, Clics superiores y en nuestras experiencias de filtrado, verá diferentes valores de veredicto de clic:

- **Ninguno:** No se puede capturar el veredicto de la dirección URL. Es posible que el usuario haya hecho clic en la dirección URL.
- **Permitido:** Se permitió al usuario navegar a la dirección URL.
- **Bloqueado:** Se bloqueó al usuario para que no navegara a la dirección URL.
- **Veredicto pendiente:** El usuario se presentó con la página pendiente de detonación.
- **Bloqueado invalidado:** Se bloqueó al usuario para que no navegara directamente a la dirección URL. Pero el usuario sobreestroba el bloque para navegar a la dirección URL.
- **Se omitió el veredicto pendiente:** El usuario se presentó con la página de detonación. Pero el usuario sobrevó el mensaje para obtener acceso a la dirección URL.
- **Error:** El usuario se presentó con la página de error o se produjo un error al capturar el veredicto.
- **Error:** Se produjo una excepción desconocida al capturar el veredicto. Es posible que el usuario haya hecho clic en la dirección URL.

## <a name="start-automated-investigation-and-response"></a>Iniciar la investigación y respuesta automatizadas

> [!NOTE]
> Las capacidades automatizadas de investigación y respuesta están disponibles en *Microsoft Defender Office 365 plan 2* y *Office 365 E5*.

[La investigación y respuesta automatizadas](automated-investigation-response-office.md) pueden ahorrarle al equipo de operaciones de seguridad el tiempo y el esfuerzo invertidos en investigar y mitigar los ciberataques. Además de configurar alertas que pueden desencadenar un libro de juegos de seguridad, puedes iniciar un proceso automatizado de investigación y respuesta desde una vista en el Explorador. Para obtener más información, [vea Ejemplo: un administrador de seguridad desencadena una investigación desde el Explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="other-articles"></a>Otros artículos

[Investigar correos electrónicos con la página Entidad de correo electrónico](mdo-email-entity-page.md)
