---
title: Ver los resultados de una investigación automatizada en Microsoft 365
keywords: AIR, autoIR, ATP, automatizado, investigación, corrección, acciones
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
ms.openlocfilehash: 9ab32444f2c0b4f9f6140c20fe8356f016d62c30
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287082"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalles y resultados de una investigación automatizada en Microsoft 365

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Cuando se [produce una investigación](office-365-air.md) automatizada en Microsoft Defender para Office [365,](office-365-atp.md)los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizada. Si tiene los permisos necesarios, puede ver esos detalles en el Centro de seguridad de Microsoft 365. Los detalles de la investigación le proporcionan el estado actualizado y la capacidad de aprobar las acciones pendientes.

> [!TIP]
> Consulte la nueva página de investigación unificada en el Centro de seguridad de Microsoft 365. Para obtener más información, vea [(¡NUEVO!) Página de investigación unificada.](../mtp/mtp-autoir-results.md#new-unified-investigation-page)

## <a name="investigation-status"></a>Estado de la investigación

El estado de la investigación indica el progreso del análisis y las acciones. A medida que se ejecuta la investigación, el estado cambia para indicar si se encontraron amenazas y si se han aprobado las acciones.

|Estado|Descripción|
|:---|:---|
|**Iniciando**|La investigación se ha desencadenado y está esperando a empezar a ejecutarse.|
|**En funcionamiento**|El proceso de investigación se ha iniciado y está en curso. Este estado también se produce cuando se [aprueban las acciones](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) pendientes.|
|**No se encontraron amenazas**|La investigación ha finalizado y no se ha identificado ninguna amenaza (cuenta de usuario, mensaje de correo electrónico, dirección URL o archivo). <p> **SUGERENCIA:** Si sospecha que se ha perdido algo (como un falso negativo), puede tomar medidas con el Explorador [de amenazas.](threat-explorer.md)|
|**Amenazas encontradas**|La investigación automatizada encontró problemas, pero no hay acciones de corrección específicas para resolverlos. <p> El **estado Amenazas encontradas** puede producirse cuando se identifica algún tipo de actividad de usuario, pero no hay acciones de limpieza disponibles. Entre los ejemplos se incluyen cualquiera de las siguientes actividades de usuario: <br/>- Un [evento de prevención de pérdida](../../compliance/data-loss-prevention-policies.md) de datos (DLP)<br/>- Un correo electrónico que envía anomalías<br/>- Malware enviado<br/>- Suplantación de identidad enviada <p> La investigación no encontró direcciones URL malintencionadas, archivos o mensajes de correo electrónico para corregir, ni actividad de buzón para corregir, como desactivar las reglas de reenvío o la delegación. <p> **SUGERENCIA:** Si sospecha que se ha perdido algo (como un falso negativo), puede investigar y tomar medidas con el Explorador [de amenazas.](threat-explorer.md)|
|**Terminado por el sistema**|La investigación se detuvo. Una investigación puede detenerse por varias razones: <br/>- Las acciones pendientes de la investigación han expirado. El tiempo de espera de las acciones pendientes después de esperar la aprobación durante una semana.<br/>- Hay demasiadas acciones. Por ejemplo, si hay demasiados usuarios haciendo clic en direcciones URL malintencionadas, puede superar la capacidad de la investigación para ejecutar todos los analizadores, por lo que la investigación se detiene.<p> **SUGERENCIA:** Si una investigación se detiene antes de realizar acciones, pruebe a usar el Explorador de amenazas [para](threat-explorer.md) buscar y solucionar las amenazas.|
|**Acción pendiente**|The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md). <p> El **estado Acción pendiente** se desencadena cuando se encuentra cualquier amenaza con una acción correspondiente. Sin embargo, la lista de acciones pendientes puede aumentar a medida que se ejecuta una investigación. Ver los detalles de la investigación para ver si otros elementos siguen pendientes de finalización.|
|**Corregido**|La investigación finalizó y se aprobaron todas las acciones de corrección (que se señalaron como totalmente correcionadas). <p> **NOTA:** Las acciones de corrección aprobadas pueden tener errores que impiden la toma de acciones. Independientemente de si las acciones de corrección se completan correctamente, el estado de la investigación no cambia. Ver detalles de la investigación.|
|**Parcialmente corregido**|La investigación dio como resultado medidas correctivas y algunas se aprobaron y completaron. Otras acciones aún están [pendientes.](air-review-approve-pending-completed-actions.md)|
|**Failed**|Al menos un analizador de investigación encontró un problema en el que no se pudo completar correctamente. <p> **NOTA:** Si se produce un error en una investigación después de que se aprobaron las acciones de corrección, es posible que las acciones de corrección se hubieran hecho correctamente. Ver los detalles de la investigación. |
|**En cola por limitación**|Se está celebrando una investigación en una cola. Cuando se completen otras investigaciones, comienzan las investigaciones en cola. La limitación ayuda a evitar un rendimiento del servicio deficiente.  <p> **SUGERENCIA:** Las acciones pendientes pueden limitar el número de investigaciones nuevas que se pueden ejecutar. Asegúrese de aprobar [(o rechazar) acciones pendientes.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Finalizado por limitación**|Si una investigación se mantiene en la cola demasiado larga, se detiene. <p> **SUGERENCIA:** Puede iniciar [una investigación desde el Explorador de amenazas.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Ver detalles de una investigación

1. Vaya al Centro de seguridad de Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones.**
3. En las **pestañas Pendiente** o **Historial,** seleccione una acción. Se abre el panel desplegable.
4. En el panel desplegable, seleccione **Abrir página de investigación.** 
5. Usa las distintas pestañas para obtener más información sobre la investigación.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver detalles sobre una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan una investigación automatizada en Microsoft 365. Para obtener más información, vea las [directivas de alerta que desencadenan investigaciones automatizadas.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Vaya al Centro de seguridad de Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones.**
3. En las **pestañas** **Pendiente** o Historial, seleccione una acción. Se abre el panel desplegable.
4. En el panel desplegable, seleccione **Abrir página de investigación.** 
5. Selecciona la **pestaña Alertas** para ver una lista de todas las alertas asociadas con esa investigación.
6. Seleccione un elemento de la lista para abrir su panel desplegable. Allí, puede ver más información sobre la alerta.

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta lo siguiente

- Los recuentos de correo electrónico se calculan en el momento de la investigación y algunos recuentos se vuelven a calcular al abrir los menús desplegables de investigación (basados en una consulta subyacente).

- Los recuentos de correo electrónico  que se muestran para los clústeres de correo electrónico en la pestaña Correo electrónico y el valor de cantidad de correo electrónico que se muestra en el control desplegable del clúster se calculan en el momento de la investigación y no cambian.

- El recuento de correo electrónico  que se muestra en la parte inferior de la pestaña Correo electrónico del control desplegable del clúster de correo electrónico y el recuento de mensajes de correo electrónico que se muestran en el Explorador reflejan los mensajes de correo electrónico recibidos después del análisis inicial de la investigación.

  Por lo tanto, un clúster de correo electrónico que muestra una cantidad original de 10 mensajes de correo electrónico mostraría un total de 15 cuando llegan cinco mensajes de correo electrónico más entre la fase de análisis de investigación y cuando el administrador revisa la investigación. Del mismo modo, es posible que las investigaciones anteriores empiecen a mostrar recuentos más altos de los que muestran las consultas de Explorer, porque los datos del Plan 2 de Microsoft Defender para Office 365 expiran después de siete días para las pruebas y después de 30 días para las licencias de pago.

  Mostrar recuentos históricos y actuales en distintas vistas se realiza para indicar el impacto del correo electrónico en el momento de la investigación y el impacto actual hasta el momento en que se ejecuta la corrección.

- En el contexto del correo electrónico, es posible que vea una superficie de amenaza de anomalías de volumen como parte de la investigación. Una anomalía de volumen indica un pico en mensajes de correo electrónico similares en relación con el tiempo del evento de investigación en comparación con períodos de tiempo anteriores. Un pico en el tráfico de correo electrónico junto con determinadas características (por ejemplo, dominio de asunto y remitente, similitud de cuerpo e IP del remitente) es típico del inicio de campañas o ataques de correo electrónico. Sin embargo, las campañas masivas, de correo no deseado y de correo electrónico legítimo normalmente comparten estas características.

- Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con las amenazas de malware o phishing que se identifican mediante motores antivirus, detonaciones o reputación malintencionada.

- No es necesario aprobar todas las acciones. Si no está de acuerdo con la acción recomendada o su organización no  elige determinados tipos de acciones, puede elegir Rechazar las acciones o simplemente ignorarlas y no realizar ninguna acción.

- Aprobar o rechazar todas las acciones permite que la investigación se cierre completamente (el estado se corrige), mientras que dejar algunas acciones incompletas da como resultado que el estado de la investigación cambie a un estado parcialmente corregido.

## <a name="next-steps"></a>Pasos siguientes

- [Revisar y aprobar acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
