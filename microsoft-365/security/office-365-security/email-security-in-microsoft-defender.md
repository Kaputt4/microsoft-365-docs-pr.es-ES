---
title: Email seguridad con el Explorador de amenazas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Vea e investigue los intentos de suplantación de identidad de malware.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 863ed93bfa4d2139d5ba559dee0cd743367e856f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645217"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Email seguridad con el Explorador de amenazas en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo:

- [Visualización del malware detectado en el correo electrónico](#view-malware-detected-in-email)
- [Ver la dirección URL de phishing y hacer clic en datos de veredicto](#view-phishing-url-and-click-verdict-data)
- [Inicio de una investigación y respuesta automatizadas](#start-automated-investigation-and-response)

> [!NOTE]
> Esto forma parte de una **serie de 3 artículos** sobre **el Explorador de amenazas (Explorer),** **la seguridad del correo electrónico** **y las detecciones del Explorador y en tiempo real** (como las diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son [Búsqueda de amenazas en el Explorador de amenazas y explorador](threat-hunting-in-threat-explorer.md) de [amenazas y detecciones en tiempo real](real-time-detections.md).

En este artículo se explica cómo ver e investigar los intentos de malware y phishing detectados en el correo electrónico por las características de seguridad de Microsoft 365.

## <a name="view-malware-detected-in-email"></a>Visualización del malware detectado en el correo electrónico

Para ver el malware detectado en el correo electrónico ordenado por la tecnología de Microsoft 365, use la vista [**Email \> Malware**](threat-explorer-views.md#email--malware) del Explorador (o detecciones en tiempo real). El malware es la vista predeterminada, por lo que podría seleccionarse en cuanto abra el Explorador.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & colaboración** y, a continuación, elija **Explorador** o **Detecciones en tiempo real**. Para ir directamente a la página, use <https://security.microsoft.com/threatexplorer> o <https://security.microsoft.com/realtimereports>.

   En este ejemplo se usa **el Explorador**.

   Desde aquí, comience en la vista, elija un período de tiempo determinado para investigar (si es necesario) y centre los filtros, según el [tutorial del Explorador](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).

2. En la lista desplegable **Ver**, compruebe que **Email** \> **Malware** está seleccionado.

3. Haga clic en **Remitente** y, a continuación, elija **Tecnología de detección** **básica** \> en la lista desplegable.

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="La tecnología de detección de malware" lightbox="../../media/exploreremailmalwaredetectiontech-newimg.png":::

   Las tecnologías de detección ahora están disponibles como filtros para el informe.

4. Elija una opción y, a continuación, haga clic en **Actualizar** para aplicar ese filtro (no actualice la ventana del explorador).

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="tecnología de detección seleccionada" lightbox="../../media/exploreremailmalwaredetectiontech2-new.png":::

   El informe se actualiza para mostrar los resultados detectados por malware en el correo electrónico, mediante la opción de tecnología seleccionada. Desde aquí, puede realizar análisis adicionales.

### <a name="report-a-message-as-clean-in-explorer"></a>Informe de un mensaje como limpio en el Explorador

Puede usar la opción **Informe limpio** en el Explorador para notificar un mensaje como falso positivo. 

1. En el portal de Microsoft 365 Defender, vaya a Email & **Explorador** de **colaboración** \> y, a continuación, en la lista desplegable **Ver**, compruebe que **Phish** está seleccionado.

2. Compruebe que se encuentra en la pestaña **Email** y, a continuación, en la lista de mensajes notificados, seleccione la que desea notificar como limpia. 

3. Haga clic en **Acciones** para expandir la lista de opciones.

4. Desplácese hacia abajo en la lista de opciones para ir a la sección **Iniciar nuevo envío** y, a continuación, seleccione **Informe limpio**. Aparece un control flotante.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/report-clean-option-explorer.png" alt-text="La opción Informe limpio en el Explorador" lightbox="../../media/report-clean-option-explorer.png":::

5. Cambie el control deslizante a **Activado**. En la lista desplegable, especifique el número de días que desea que se quite el mensaje, agregue una nota si es necesario y, a continuación, seleccione **Enviar**. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Ver la dirección URL de phishing y hacer clic en datos de veredicto

Puede ver los intentos de suplantación de identidad a través de direcciones URL en el correo electrónico, incluida una lista de direcciones URL permitidas, bloqueadas y reemplazadas. Para identificar las direcciones URL en las que se ha hecho clic, se deben configurar [vínculos seguros](safe-links.md) . Asegúrese de configurar [directivas de vínculos seguros](set-up-safe-links-policies.md) para la protección con el tiempo de clic y el registro de veredictos de clics mediante vínculos seguros.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & colaboración** y, a continuación, elija **Explorador** o **Detecciones en tiempo real**. Para ir directamente a la página, use <https://security.microsoft.com/threatexplorer> o <https://security.microsoft.com/realtimereports>.

   En este ejemplo se usa **el Explorador**.

2. En la lista desplegable **Ver**, elija **Email** \> **Phish**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailPhishMenu.png" alt-text="El menú Ver del Explorador en contexto de suplantación de identidad" lightbox="../../media/ExplorerViewEmailPhishMenu.png":::

3. Haga clic en **Remitente** y, a continuación, elija **Direcciones** \> URL **Haga clic en veredicto** en la lista desplegable.

4. En las opciones que aparecen, seleccione una o varias opciones, como **Bloqueado** y **Bloquear invalidados**, y, a continuación, haga clic en **Actualizar** (no actualice la ventana del explorador).

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="Las direcciones URL y los veredictos de clic" lightbox="../../media/threatexploreremailphishclickverdict-new.png":::

   El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la pestaña **Direcciones URL** del informe:

   - **Las direcciones URL principales** son las direcciones URL de los mensajes a los que filtró y la acción de entrega de correo electrónico cuenta para cada dirección URL. En la vista de correo electrónico de Phish, esta lista normalmente contiene direcciones URL legítimas. Los atacantes incluyen una combinación de direcciones URL buenas y malas en sus mensajes para intentar que se entreguen, pero hacen que los vínculos malintencionados parezcan más interesantes. La tabla de direcciones URL se ordena por número total de correo electrónico, pero esta columna está oculta para simplificar la vista.

   - **Los clics superiores son las direcciones** URL encapsuladas en vínculos seguros en las que se ha hecho clic, ordenadas por número total de clics. Esta columna tampoco se muestra para simplificar la vista. Los recuentos totales por columna indican el recuento de veredictos de clic de vínculos seguros para cada dirección URL en la que se ha hecho clic. En la vista de correo electrónico de Phish, suelen ser direcciones URL sospechosas o malintencionadas. Pero la vista podría incluir direcciones URL que no son amenazas, pero que están en mensajes de tipo phish. Los clics de dirección URL en los vínculos desencapsados no aparecen aquí.

   Las dos tablas de direcciones URL muestran las direcciones URL principales en los mensajes de correo electrónico de suplantación de identidad por acción de entrega y ubicación. Las tablas muestran los clics de dirección URL que se bloquearon o visitaron a pesar de una advertencia, para que pueda ver qué posibles vínculos incorrectos se presentaron a los usuarios y en los que los usuarios hicieron clic. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico puede ver las direcciones URL principales en los mensajes de correo electrónico que se bloquearon en el entorno de la organización.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerPhishClickVerdictURLs.png" alt-text="Las direcciones URL del Explorador que se bloquearon" lightbox="../../media/ExplorerPhishClickVerdictURLs.png":::

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo de control flotante URL, se quita el filtrado de mensajes de correo electrónico para mostrar la vista completa de la exposición de la dirección URL en su entorno. Esto le permite filtrar los mensajes de correo electrónico que le preocupan en el Explorador, buscar direcciones URL específicas que son posibles amenazas y, a continuación, ampliar la comprensión de la exposición de direcciones URL en su entorno (a través del cuadro de diálogo Detalles de dirección URL) sin tener que agregar filtros de dirección URL a la propia vista del Explorador.

### <a name="interpretation-of-click-verdicts"></a>Interpretación de los veredictos de clic

En los controles flotantes Email o URL, Clics superiores y, en nuestras experiencias de filtrado, verá diferentes valores de veredicto de clics:

- **Ninguno:** No se puede capturar el veredicto de la dirección URL. Es posible que el usuario haya hecho clic en la dirección URL.
- **Permitido:** Se permitió al usuario navegar a la dirección URL.
- **Bloqueado:** El usuario no pudo navegar a la dirección URL.
- **Veredicto pendiente:** Al usuario se le presentó la página pendiente de detonación.
- **Bloqueado invalidado:** El usuario no pudo navegar directamente a la dirección URL. Pero el usuario superó el bloque para navegar a la dirección URL.
- **Veredicto pendiente omitido:** Al usuario se le presentó la página de detonación. Pero el usuario superó el mensaje para acceder a la dirección URL.
- **Error:** Al usuario se le presentó la página de error o se produjo un error al capturar el veredicto.
- **Fracaso:** Se produjo una excepción desconocida al capturar el veredicto. Es posible que el usuario haya hecho clic en la dirección URL.

## <a name="start-automated-investigation-and-response"></a>Inicio de una investigación y respuesta automatizadas

> [!NOTE]
> Las funcionalidades automatizadas de investigación y respuesta están disponibles en *Microsoft Defender para Office 365 plan 2* y *Office 365 E5*.

[La investigación y la respuesta automatizadas](automated-investigation-response-office.md) pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad dedicados a investigar y mitigar ciberataques. Además de configurar alertas que pueden desencadenar un cuaderno de estrategias de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el Explorador. Para obtener más información, vea [Ejemplo: Un administrador de seguridad desencadena una investigación desde el Explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="other-articles"></a>Otros artículos

[Investigación de correos electrónicos con la página de entidad Email](mdo-email-entity-page.md)
