---
title: Ver los resultados de una investigación automatizada en Microsoft 365
keywords: AIR, autoIR, Microsoft Defender para punto de conexión, automatizado, investigación, corrección, acciones
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Durante y después de una investigación automatizada en Microsoft 365, puede ver los resultados y los resultados clave.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b99573f73d5b53b6ea0e8d0cd1e44b539fa47db9
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649085"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalles y resultados de una investigación automatizada en Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Cuando se produce una [investigación automatizada](office-365-air.md) en [Microsoft Defender para Office 365](defender-for-office-365.md), los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado. Si tiene los permisos necesarios, puede ver esos detalles en el portal de Microsoft 365 Defender. Los detalles de la investigación proporcionan un estado actualizado y la capacidad de aprobar las acciones pendientes.

> [!TIP]
> Consulte la nueva página de investigación unificada en el portal de Microsoft 365 Defender. Para obtener más información, consulte [(¡NUEVO!) Página de investigación unificada](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Estado de la investigación

El estado de la investigación indica el progreso del análisis y las acciones. A medida que se ejecuta la investigación, el estado cambia para indicar si se encontraron amenazas y si se han aprobado acciones.

|Estado|Descripción|
|---|---|
|**Iniciando**|La investigación se ha desencadenado y está a la espera de empezar a ejecutarse.|
|**En funcionamiento**|El proceso de investigación se ha iniciado y está en curso. Este estado también se produce cuando se aprueban [las acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) .|
|**No se encontraron amenazas**|La investigación ha finalizado y no se ha identificado ninguna amenaza (cuenta de usuario, mensaje de correo electrónico, dirección URL o archivo). <p> **SUGERENCIA**: Si sospecha que se ha perdido algo (por ejemplo, un falso negativo), puede tomar medidas mediante [el Explorador de amenazas](threat-explorer.md).|
|**Amenazas encontradas**|La investigación automatizada encontró problemas, pero no hay ninguna acción de corrección específica para resolver esos problemas. <p> El estado **Amenazas encontradas** puede producirse cuando se ha identificado algún tipo de actividad de usuario, pero no hay ninguna acción de limpieza disponible. Entre los ejemplos se incluye cualquiera de las siguientes actividades de usuario: <ul><li>Un evento [de prevención de pérdida de datos](../../compliance/dlp-learn-about-dlp.md)</li><li>Anomalía de envío de correo electrónico</li><li>Malware enviado</li><li>Phish enviado</li></ul> <p> La investigación no encontró direcciones URL malintencionadas, archivos o mensajes de correo electrónico que corregir y ninguna actividad de buzón que corregir, como desactivar las reglas de reenvío o la delegación. <p> **SUGERENCIA**: Si sospecha que se ha perdido algo (por ejemplo, un falso negativo), puede investigar y tomar medidas mediante [el Explorador de amenazas](threat-explorer.md).|
|**Terminado por el sistema**|La investigación se detuvo. Una investigación puede detenerse por varias razones: <ul><li>Las acciones pendientes de la investigación han expirado. Tiempo de espera de las acciones pendientes después de esperar la aprobación durante una semana</li><li>Hay demasiadas acciones. Por ejemplo, si hay demasiados usuarios haciendo clic en direcciones URL malintencionadas, puede superar la capacidad de la investigación de ejecutar todos los analizadores, por lo que la investigación se detiene.</li></ul> <p> **SUGERENCIA**: Si una investigación se detiene antes de realizar acciones, intente usar [el Explorador de amenazas](threat-explorer.md) para buscar y abordar amenazas.|
|**Acción pendiente**|La investigación ha encontrado una amenaza, como un correo electrónico malintencionado, una dirección URL malintencionada o una configuración de buzón de correo de riesgo, y una acción para corregir que la amenaza está [en espera de aprobación](air-review-approve-pending-completed-actions.md). <p> El estado **Acción pendiente** se desencadena cuando se encuentra cualquier amenaza con una acción correspondiente. Sin embargo, la lista de acciones pendientes puede aumentar a medida que se ejecuta una investigación. Vea los detalles de la investigación para ver si otros elementos siguen pendientes de finalización.|
|**Corregido**|La investigación finalizó y se aprobaron todas las acciones de corrección (se anotó como totalmente corregido). <p> **NOTA**: Las acciones de corrección aprobadas pueden tener errores que impidan que se realicen las acciones. Independientemente de si las acciones de corrección se completan correctamente, el estado de la investigación no cambia. Ver los detalles de la investigación.|
|**Parcialmente corregido**|La investigación produjo acciones de corrección y algunas se aprobaron y completaron. Otras acciones siguen [pendientes](air-review-approve-pending-completed-actions.md).|
|**Failed**|Al menos un analizador de investigación se encontró con un problema en el que no pudo completarse correctamente. <p> **NOTA** Si se produce un error en una investigación después de aprobar las acciones de corrección, es posible que las acciones de corrección se hayan realizado correctamente. Vea los detalles de la investigación.|
|**En cola por limitación**|Una investigación se mantiene en una cola. Cuando se completen otras investigaciones, comienzan las investigaciones en cola. La limitación ayuda a evitar un rendimiento deficiente del servicio.  <p> **SUGERENCIA**: Las acciones pendientes pueden limitar el número de investigaciones nuevas que se pueden ejecutar. Asegúrese de [aprobar (o rechazar) las acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).|
|**Terminado por limitación**|Si una investigación se mantiene en la cola demasiado tiempo, se detiene. <p> **SUGERENCIA**: Puede [iniciar una investigación desde el Explorador de amenazas](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|

## <a name="view-details-of-an-investigation"></a>Ver detalles de una investigación

1. Vaya al portal de Microsoft 365 Defender (<https://security.microsoft.com>) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En las pestañas **Pendiente** o **Historial** , seleccione una acción. Se abre el panel flotante.
4. En el panel flotante, seleccione **Abrir página de investigación**. 
5. Use las distintas pestañas para obtener más información sobre la investigación.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver detalles sobre una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan una investigación automatizada en Microsoft 365. Para más información, consulte [Directivas de alerta que desencadenan investigaciones automatizadas](office-365-air.md#which-alert-policies-trigger-automated-investigations).

1. Vaya al portal de Microsoft 365 Defender (<https://security.microsoft.com>) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En las pestañas **Pendiente** o **Historial** , seleccione una acción. Se abre el panel flotante.
4. En el panel flotante, seleccione **Abrir página de investigación**.
5. Seleccione la pestaña **Alertas** para ver una lista de todas las alertas asociadas a esa investigación.
6. Seleccione un elemento de la lista para abrir su panel flotante. Allí, puede ver más información sobre la alerta.

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- Los recuentos de correo electrónico se calculan en el momento de la investigación y algunos recuentos se recalculan al abrir los controles flotantes de la investigación (en función de una consulta subyacente).

- Los recuentos de correo electrónico que se muestran para los clústeres de correo electrónico en la pestaña **Correo electrónico** y el valor de cantidad de correo electrónico que se muestra en el control flotante del clúster se calculan en el momento de la investigación y no cambian.

- El recuento de correo electrónico que se muestra en la parte inferior de la pestaña **Correo electrónico** del control flotante del clúster de correo electrónico y el número de mensajes de correo electrónico que se muestran en el Explorador reflejan los mensajes de correo electrónico recibidos después del análisis inicial de la investigación.

  Por lo tanto, un clúster de correo electrónico que muestra una cantidad original de 10 mensajes de correo electrónico mostraría un total de 15 cuando llegan cinco mensajes de correo electrónico más entre la fase de análisis de investigación y cuando el administrador revisa la investigación. Del mismo modo, las investigaciones antiguas podrían empezar a mostrar recuentos más altos de los que muestran las consultas del Explorador, ya que los datos de Microsoft Defender para Office 365 Plan 2 expiran después de siete días para las pruebas y después de 30 días para las licencias de pago.

  Se muestra el recuento de recuentos históricos y actuales en vistas diferentes para indicar el impacto del correo electrónico en el momento de la investigación y el impacto actual hasta el momento en que se ejecuta la corrección.

- En el contexto del correo electrónico, es posible que vea una superficie de amenaza de anomalía de volumen como parte de la investigación. Una anomalía de volumen indica un aumento en mensajes de correo electrónico similares en torno al tiempo del evento de investigación en comparación con los períodos de tiempo anteriores. Un pico en el tráfico de correo electrónico junto con ciertas características (por ejemplo, el dominio del asunto y el remitente, la similitud del cuerpo y la dirección IP del remitente) es típico del inicio de campañas o ataques de correo electrónico. Sin embargo, las campañas masivas, de correo no deseado y de correo electrónico legítimo suelen compartir estas características.

- Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con las amenazas de malware o phish que se identifican mediante motores antivirus, detonación o reputación malintencionada.

- No es necesario aprobar todas las acciones. Si no está de acuerdo con la acción recomendada o su organización no elige determinados tipos de acciones, puede optar por **rechazar** las acciones o simplemente ignorarlas y no realizar ninguna acción.

- Aprobar o rechazar todas las acciones permite que la investigación se cierre por completo (el estado se corrige), mientras que dejar algunas acciones incompletas da como resultado que el estado de la investigación cambie a un estado parcialmente corregido.

## <a name="next-steps"></a>Siguientes pasos

- [Revisión y aprobación de acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
