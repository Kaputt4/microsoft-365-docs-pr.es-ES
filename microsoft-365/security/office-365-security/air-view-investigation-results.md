---
title: Ver los resultados de una investigación automatizada en Microsoft 365
keywords: AIR, autoIR, ATP, automated, investigation, remediation, actions
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
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
ms.openlocfilehash: 8bf18a9fb80805581a1439b3965a664fd0868248
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205527"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalles y resultados de una investigación automatizada en Microsoft 365

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cuando se [produce una](office-365-air.md) investigación automatizada en Microsoft Defender para [Office 365,](defender-for-office-365.md)los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado. Si tiene los permisos necesarios, puede ver esos detalles en el Centro de seguridad de Microsoft 365. Los detalles de la investigación le proporcionan el estado actualizado y la capacidad de aprobar cualquier acción pendiente.

> [!TIP]
> Consulte la nueva página de investigación unificada en el Centro de seguridad de Microsoft 365. Para obtener más información, vea [(¡NUEVO!) Página de investigación unificada](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Estado de la investigación

El estado de la investigación indica el progreso del análisis y las acciones. A medida que se ejecuta la investigación, el estado cambia para indicar si se encontraron amenazas y si se han aprobado acciones.

|Estado|Descripción|
|:---|:---|
|**Iniciando**|La investigación se ha desencadenado y está a la espera de empezar a ejecutarse.|
|**En funcionamiento**|El proceso de investigación ha comenzado y está en curso. Este estado también se produce cuando se [aprueban acciones](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) pendientes.|
|**No se encontró ninguna amenaza**|La investigación ha finalizado y no se ha identificado ninguna amenaza (cuenta de usuario, mensaje de correo electrónico, dirección URL o archivo). <p> **SUGERENCIA:** Si sospecha que se ha perdido algo (como un falso negativo), puede tomar medidas con el Explorador [de amenazas](threat-explorer.md).|
|**Amenazas encontradas**|La investigación automatizada encontró problemas, pero no hay acciones de corrección específicas para resolver esos problemas. <p> El **estado Amenazas encontradas** puede producirse cuando se identificó algún tipo de actividad de usuario, pero no hay acciones de limpieza disponibles. Algunos ejemplos incluyen cualquiera de las siguientes actividades de usuario: <br/>- Un [evento de prevención de pérdida de](../../compliance/data-loss-prevention-policies.md) datos (DLP)<br/>- Un correo electrónico que envía anomalías<br/>- Malware enviado<br/>- Suplantación de identidad enviada <p> La investigación no encontró direcciones URL malintencionadas, archivos o mensajes de correo electrónico que corregir y ninguna actividad de buzón para corregir, como desactivar reglas de reenvío o delegación. <p> **SUGERENCIA:** Si sospecha que se ha perdido algo (como un falso negativo), puede investigar y tomar medidas con [el Explorador de amenazas](threat-explorer.md).|
|**Terminado por sistema**|La investigación se detuvo. Una investigación puede detenerse por varias razones: <br/>- Las acciones pendientes de la investigación expiraron. El tiempo de espera de las acciones pendientes después de esperar la aprobación durante una semana.<br/>- Hay demasiadas acciones. Por ejemplo, si hay demasiados usuarios haciendo clic en direcciones URL malintencionadas, puede superar la capacidad de la investigación para ejecutar todos los analizadores, por lo que la investigación se detiene.<p> **SUGERENCIA:** Si una investigación se detiene antes de realizar acciones, intente usar [el](threat-explorer.md) Explorador de amenazas para buscar y solucionar las amenazas.|
|**Acción pendiente**|The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md). <p> El **estado De la acción** pendiente se desencadena cuando se encuentra cualquier amenaza con una acción correspondiente. Sin embargo, la lista de acciones pendientes puede aumentar a medida que se ejecuta una investigación. Vea los detalles de la investigación para ver si otros elementos aún están pendientes de finalización.|
|**Corregido**|La investigación finalizó y se aprobaron todas las acciones de corrección (señaladas como totalmente remediadas). <p> **NOTA:** Las acciones de corrección aprobadas pueden tener errores que impiden que se puedan realizar las acciones. Independientemente de si las acciones de corrección se han completado correctamente, el estado de la investigación no cambia. Ver detalles de investigación.|
|**Parcialmente corregido**|La investigación dio como resultado acciones de corrección y algunas se aprobaron y completaron. Otras acciones aún están [pendientes.](air-review-approve-pending-completed-actions.md)|
|**Failed**|Al menos un analizador de investigación encontró un problema en el que no se pudo completar correctamente. <p> **NOTA:** Si se produce un error en una investigación después de que se aprobaron las acciones de corrección, es posible que las acciones de corrección se hubieran hecho correctamente. Ver los detalles de la investigación. |
|**En cola por limitación**|Se está celebrando una investigación en una cola. Cuando se completen otras investigaciones, comienzan las investigaciones en cola. La limitación ayuda a evitar un rendimiento de servicio deficiente.  <p> **SUGERENCIA:** Las acciones pendientes pueden limitar el número de investigaciones nuevas que se pueden ejecutar. Asegúrese de aprobar [(o rechazar)](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)acciones pendientes .|
|**Terminado por limitación**|Si una investigación se mantiene en la cola demasiado tiempo, se detiene. <p> **SUGERENCIA:** Puede iniciar [una investigación desde el Explorador de amenazas](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|
|

## <a name="view-details-of-an-investigation"></a>Ver detalles de una investigación

1. Vaya al Centro de seguridad de Microsoft 365 ( <https://security.microsoft.com> ) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En las **pestañas Pendiente** o **Historial,** seleccione una acción. Se abre el panel desplegable.
4. En el panel desplegable, seleccione **Abrir página de investigación**. 
5. Use las distintas pestañas para obtener más información sobre la investigación.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver detalles sobre una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan una investigación automatizada en Microsoft 365. Para obtener más información, vea [directivas de alerta que desencadenan investigaciones automatizadas.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Vaya al Centro de seguridad de Microsoft 365 ( <https://security.microsoft.com> ) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.
3. En las **pestañas Pendiente** o **Historial,** seleccione una acción. Se abre el panel desplegable.
4. En el panel desplegable, seleccione **Abrir página de investigación**. 
5. Seleccione la **pestaña** Alertas para ver una lista de todas las alertas asociadas con esa investigación.
6. Seleccione un elemento de la lista para abrir su panel desplegable. Allí, puede ver más información sobre la alerta.

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- Los recuentos de correo electrónico se calculan en el momento de la investigación y algunos recuentos se recalculan al abrir los flyouts de investigación (en función de una consulta subyacente).

- Los recuentos de correo electrónico  que se muestran para los clústeres de correo electrónico en la pestaña Correo electrónico y el valor de cantidad de correo electrónico que se muestra en el control desplegable del clúster se calculan en el momento de la investigación y no cambian.

- El recuento de correo electrónico  que se muestra en la parte inferior de la pestaña Correo electrónico del control desplegable del clúster de correo electrónico y el recuento de mensajes de correo electrónico mostrados en el Explorador reflejan los mensajes de correo electrónico recibidos después del análisis inicial de la investigación.

  Por lo tanto, un clúster de correo electrónico que muestra una cantidad original de 10 mensajes de correo electrónico mostraría una lista de correo electrónico total de 15 cuando lleguen cinco mensajes de correo electrónico más entre la fase de análisis de investigación y cuando el administrador revisa la investigación. Del mismo modo, es posible que las investigaciones antiguas comiencen a mostrar recuentos superiores a los que muestran las consultas de Explorer, ya que los datos del Plan 2 de Microsoft Defender para Office 365 expiran después de siete días para las pruebas y después de 30 días para las licencias de pago.

  Mostrar recuentos históricos y actuales en diferentes vistas se realiza para indicar el impacto del correo electrónico en el momento de la investigación y el impacto actual hasta el momento en que se ejecuta la corrección.

- En el contexto del correo electrónico, es posible que veas una superficie de amenaza de anomalía de volumen como parte de la investigación. Una anomalía de volumen indica un pico en mensajes de correo electrónico similares alrededor del tiempo del evento de investigación en comparación con períodos de tiempo anteriores. Un pico en el tráfico de correo electrónico junto con ciertas características (por ejemplo, dominio de asunto y remitente, similitud de cuerpo e IP del remitente) es típico del inicio de campañas o ataques de correo electrónico. Sin embargo, las campañas masivas, de correo no deseado y de correo electrónico legítimo normalmente comparten estas características.

- Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con las amenazas de malware o phish que se identifican con motores antivirus, detonaciones o reputación malintencionada.

- No es necesario aprobar todas las acciones. Si no está de acuerdo con la acción recomendada o su organización no  elige determinados tipos de acciones, puede optar por Rechazar las acciones o simplemente ignorarlas y no realizar ninguna acción.

- La aprobación o el rechazo de todas las acciones permite que la investigación se cierre completamente (el estado se corrige), mientras que algunas acciones dejan resultados incompletos en el estado de la investigación cambiando a un estado parcialmente corregido.

## <a name="next-steps"></a>Siguientes pasos

- [Revisar y aprobar acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
