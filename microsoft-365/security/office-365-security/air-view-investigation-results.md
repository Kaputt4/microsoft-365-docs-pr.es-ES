---
title: Ver los resultados de una investigación automatizada en Microsoft 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Durante y después de una investigación automatizada en Microsoft 365, puede ver los resultados y los resultados principales.
ms.date: 11/05/2020
ms.openlocfilehash: 4dc74987619c3f958c874927af6e4240b9d7e154
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357290"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalles y resultados de una investigación automatizada en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Cuando se produce una [investigación automatizada](office-365-air.md) en [Microsoft Defender para Office 365](office-365-atp.md), los detalles sobre la investigación están disponibles durante y después del proceso de investigación automatizada. Si tiene los permisos necesarios, puede ver estos detalles en el centro de seguridad de Microsoft 365. Los detalles de la investigación le proporcionan el estado actualizado y la capacidad de aprobar cualquier acción pendiente.

## <a name="investigation-status"></a>Estado de la investigación

El estado de la investigación indica el progreso del análisis y las acciones. A medida que se ejecuta la investigación, el estado cambia para indicar si se han encontrado amenazas y si se han aprobado las acciones.

|Estado|Descripción|
|---|---|
|**Iniciando**|La investigación se ha desencadenado y está en espera de comenzar a ejecutarse.|
|**En funcionamiento**|El proceso de investigación se ha iniciado y está en curso. Este estado también se produce cuando se aprueban [las acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) .|
|**No se encontraron amenazas**|La investigación ha finalizado y no se han identificado amenazas (cuenta de usuario, mensaje de correo electrónico, URL o archivo). <p> **Sugerencia**: Si sospecha que se ha perdido algo (como un falso negativo), puede emprender acciones con el [Explorador de amenazas](threat-explorer.md).|
|**Amenazas encontradas**|La investigación automatizada encontró problemas, pero no hay acciones de corrección específicas para resolver estos problemas. <p> El estado de **amenazas encontradas** puede producirse cuando se identificó algún tipo de actividad de usuario, pero no hay ninguna acción de limpieza disponible. Algunos ejemplos son las siguientes actividades de usuario: <ul><li>Un evento de [prevención de pérdida de datos](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP)</li><li>Una anomalía de envío de correo electrónico</li><li>Malware enviado</li><li>Phish enviado</li></ul> <p> La investigación no encontró direcciones URL malintencionadas, archivos ni mensajes de correo electrónico que corregir, y no se ha corregido ninguna actividad de buzón, como desactivar las reglas de reenvío o la delegación. <p> **Sugerencia**: Si sospecha que se ha perdido algo (como un falso negativo), puede investigar y realizar acciones con el [Explorador de amenazas](threat-explorer.md).|
|**Finalizado por el sistema**|Se detuvo la investigación. Una investigación puede detenerse por varias razones: <ul><li>Las acciones pendientes de la investigación expiraron. Se agota el tiempo de espera de las acciones pendientes después de esperar la aprobación durante una semana.</li><li>Hay demasiadas acciones. Por ejemplo, si hay demasiados usuarios haciendo clic en direcciones URL malintencionadas, puede superar la capacidad de la investigación para ejecutar todos los analizadores, de modo que la investigación se detenga.</li></ul> <p> **Sugerencia**: Si una investigación se detiene antes de que se tomaron las acciones, pruebe a usar el [Explorador de amenazas](threat-explorer.md) para encontrar y solucionar amenazas.|
|**Acción pendiente**|La investigación ha encontrado una amenaza, como un correo electrónico malintencionado, una dirección URL malintencionada o una configuración de buzón de correo arriesgado, y una acción para corregir dicha amenaza está en [espera de aprobación](air-review-approve-pending-completed-actions.md). <p> El estado de **acción pendiente** se desencadena cuando se encuentra cualquier amenaza con una acción correspondiente. Sin embargo, la lista de acciones pendientes puede aumentar a medida que se ejecute una investigación. Compruebe el [registro de investigación](#playbook-log) para ver si hay otros elementos aún pendientes de finalización.|
|**Corregido**|Ha finalizado la investigación y se han aprobado todas las acciones de corrección (se indica como corregida completamente). <p> **Nota**: las acciones de corrección aprobadas pueden tener errores que impiden que se tomen las acciones. Independientemente de si las acciones de corrección se completan correctamente, el estado de la investigación no cambia. Consulte el [registro de investigación](#playbook-log) para obtener resultados detallados.|
|**Parcialmente remediado**|La investigación dio como resultado acciones correctivas y algunas fueron aprobadas y completadas. Aún hay otras acciones [pendientes](air-review-approve-pending-completed-actions.md).|
|**Failed**|Al menos un analizador de investigación tuvo un problema en el que no se pudo completar correctamente. <p> **Nota**: si se produce un error en una investigación tras la aprobación de acciones de corrección, es posible que las acciones de corrección sigan teniendo éxito. Consulte el [registro de investigación](#playbook-log) para obtener resultados detallados.|
|**En cola por limitación**|Una investigación se mantiene en una cola. Cuando se completan otras investigaciones, comienzan las investigaciones en cola. La limitación ayuda a evitar un rendimiento deficiente del servicio.  <p> **Sugerencia**: las acciones pendientes pueden limitar el número de investigaciones nuevas que se pueden ejecutar. Asegúrese de [aprobar (o rechazar) acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).|
|**Terminado con la limitación**|Si una investigación se mantiene en la cola demasiado tiempo, se detiene. <p> **Sugerencia**: puede [iniciar una investigación desde el explorador de amenazas](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|
|

## <a name="view-details-of-an-investigation"></a>Ver los detalles de una investigación

1. Vaya al centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Realice una de las siguientes acciones:

    - Vaya al panel de **Administración de amenazas** \> **Dashboard**. Esto le llevará al [Panel de seguridad](security-dashboard.md). Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md). Seleccione un widget, como un **Resumen de investigaciones**.

    - Vaya a investigaciones de **Administración de amenazas** \> **Investigations**.

    Cualquiera de estos métodos le lleva a una lista de investigaciones.

    ![Página principal de investigación para AIR](../../media/air-maininvestigationpage.png)

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . Se abrirá la página Detalles de la investigación, empezando por el gráfico de investigación en la vista.

    ![Página de gráfico de investigación de aire](../../media/air-investigationgraphpage.png)

   Use las distintas pestañas para obtener más información sobre la investigación.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver los detalles de una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan la investigación automatizada en Microsoft 365. Para obtener más información, consulte [directivas de alerta que desencadenan investigaciones automáticas](office-365-air.md#which-alert-policies-trigger-automated-investigations).

Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.

1. Vaya al centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Vaya a investigaciones de **Administración de amenazas** \> **Investigations**.

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** .

4. Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.

5. Seleccione un elemento de la lista. Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.

6. Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir** o **notificar a los usuarios**.

    - **Resolve** equivale a cerrar una alerta

    - **Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado

    - **Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios. (Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).

## <a name="how-to-use-the-various-tabs"></a>Uso de las distintas pestañas

Las siguientes secciones le guiarán por las distintas pestañas de la página investigaciones automatizadas y cómo puede usar la información.

### <a name="automated-investigations-page"></a>Página investigaciones automatizadas

La página investigaciones automatizadas muestra las investigaciones de su organización y sus Estados actuales.

![Página principal de investigación para AIR](../../media/air-maininvestigationpage.png)

Puede:

- Vaya directamente a una investigación (seleccione un **identificador de investigación**).

- Aplicar filtros. Elija entre el **tipo de investigación**, **el intervalo de tiempo**, el **Estado** o una combinación de estos.

- Exporte los datos a un archivo. csv.

### <a name="investigation-graph"></a>Gráfico de investigación

Al abrir una investigación específica, verá la página gráfico de investigación. En esta página se muestran todas las entidades distintas: mensajes de correo electrónico, usuarios (y sus actividades) y dispositivos que se investigaron automáticamente como parte de la alerta que se activó.

![Página de gráfico de investigación de aire](../../media/air-investigationgraphpage.png)

Puede:

- Obtenga información general visual de la investigación actual.
- Ver un resumen de la duración de la investigación.
- Seleccione un nodo de la visualización para ver los detalles de ese nodo.
- Seleccione una pestaña en la parte superior para ver los detalles de esa pestaña.

### <a name="alert-investigation"></a>Investigación de alertas

En la pestaña **alertas** de una investigación, puede ver las alertas relevantes para la investigación. Los detalles incluyen la alerta que desencadenó la investigación y otras alertas correlacionadas, como el inicio de sesión peligroso, las infracciones de [directivas de DLP](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) , etc., que están relacionadas con la investigación. En esta página, un analista de seguridad también puede ver detalles adicionales de alertas individuales.

![Página de alertas de AIR](../../media/air-investigationalertspage.png)

Puede:

- Obtenga información general visual de la alerta desencadenadora actual y de cualquier alerta asociada.
- Seleccione una alerta de la lista para abrir una página emergente que muestre los detalles de la alerta completa.

### <a name="email-investigation"></a>Investigación de correo electrónico

En la pestaña **correo electrónico** de una investigación, puede ver los correos electrónicos originales y los clústeres de correo electrónico similar identificados como parte de la investigación. La pestaña **correo** electrónico también muestra los elementos de correo electrónico relacionados con la investigación, como los detalles de correo electrónico notificados por el usuario, el correo electrónico original que se ha notificado, los mensajes de correo electrónico que se han zapped debido a malware/phish, etc.

![Página de investigación de correo electrónico de AIR](../../media/air-investigationemailpage.png)

Con la investigación de correo electrónico, puede:

- Obtenga información general visual de los resultados y amenazas de clúster actuales encontrados.
- Haga clic en una entidad de clúster o en una lista de amenazas para abrir una página emergente que muestre los detalles de alerta completos.
- Para investigar más detalladamente el clúster de correo electrónico, haga clic en el vínculo **abrir en el explorador** en la parte superior de la pestaña **detalles del clúster de correo electrónico**

![Correo electrónico de investigación de aire con detalles de control flotante](../../media/air-investigationemailpageflyoutdetails.png)

Dado el volumen total de correo electrónico que los usuarios de una organización envían y reciben, además de la naturaleza multiusuario de las comunicaciones y los ataques de correo electrónico, el proceso siguiente puede tardar un tiempo considerable:

1. Agrupar mensajes de correo electrónico en función de atributos similares de un encabezado, cuerpo, dirección URL y datos adjuntos de un mensaje.
2. Separar el correo electrónico malintencionado del buen correo electrónico.
3. Realizar acciones en mensajes de correo electrónico malintencionados.

AIR automatiza este proceso, lo que ahorra tiempo y esfuerzo del equipo de seguridad de su organización.

#### <a name="types-of-email-clusters"></a>Tipos de clústeres de correo electrónico

Se pueden identificar tres tipos diferentes de clústeres de correo electrónico durante el paso de análisis de correo electrónico: clústeres de similitud (todas las investigaciones), clústeres de indicadores (todas las investigaciones) y clústeres de buzones de correo y usuarios. En la tabla siguiente se describen estos tipos de clústeres de correo electrónico.

|Clúster de correo electrónico|Descripción|
|---|---|
|Clústeres de similitud|Mensajes de correo electrónico que se identifican mediante la búsqueda de correos electrónicos con atributos de remitente y contenido similares. Estos clústeres se evalúan para contenido malintencionado en función de las comprobaciones de detección originales. Los clústeres de correo electrónico que contienen suficientes detecciones de correo malintencionado se consideran malintencionados.|
|Clústeres de indicadores|Mensajes de correo electrónico que se identifican mediante la búsqueda de la misma entidad del indicador (hash de archivo o dirección URL) del correo electrónico original. Cuando la entidad de archivo/URL original se identifica como malintencionada, AIR aplica el veredicto del indicador a todo el clúster de mensajes de correo electrónico que contengan esa entidad. Un archivo identificado como malware significa que el clúster de mensajes de correo electrónico que contiene ese archivo se trata como mensajes de correo electrónico de malware.|
|Buzones de correo y usuarios|Mensajes de correo electrónico relacionados con el usuario implicado en una investigación de compromiso del usuario. Estos clústeres de correo electrónico son para el mayor análisis que realiza el equipo de operaciones de seguridad y no generarán acciones de corrección de correo electrónico. <p> La guía de seguridad de usuario comprometida revisa los correos electrónicos que envía el usuario que se está analizando para conocer el impacto potencial de los correos electrónicos que se envían desde el buzón.|

> [!NOTE]
> El objetivo de la agrupación en clústeres es buscar y encontrar otros mensajes de correo electrónico relacionados que envía el mismo remitente como parte de un ataque o una campaña.  En algunos casos, el correo electrónico legítimo puede desencadenar una investigación (por ejemplo, un usuario informa de un correo electrónico de marketing).  En estos escenarios, el clúster de correo electrónico debe identificar que los clústeres de correo electrónico no son malintencionados; cuando lo hace correctamente, **no** indicará ninguna amenaza, ni recomendará la eliminación del correo electrónico.

#### <a name="email-classifications"></a>Clasificaciones de correo electrónico

A medida que se analizan los mensajes de correo electrónico, se clasifican como *malintencionados*, *sospechosos* o *limpios* (como en, *no se identifica como una amenaza*):

- Los *correos electrónicos malintencionados* que se envían desde el buzón o el usuario indican la posible intromisión del buzón de correo o la cuenta. Se muestran otros usuarios o buzones de correo que pueden verse afectados por correo electrónico malintencionado como parte de un riesgo.

- Los *mensajes sospechosos* enviados por el buzón o el usuario indican la posibilidad de una cuenta comprometida o una actividad de correo no deseado. Estos mensajes incluyen todos los correos electrónicos no deseados o masivos enviados desde el buzón.

- Los *correos electrónicos limpios* (correos electrónicos que se consideran una amenaza) enviados por el buzón de correo o el usuario pueden proporcionar al equipo de operaciones de seguridad una vista de los correos electrónicos de usuario legítimos enviados. Sin embargo, estos correos electrónicos también pueden incluir la exfiltración de datos si la cuenta de correo electrónico está en peligro.

#### <a name="more-about-email-counts"></a>Más información sobre los recuentos de correo

El recuento de correo electrónico identificado en la ficha correo electrónico representa actualmente la suma total de todos los mensajes de correo electrónico que se muestran en la ficha **correo electrónico** . Como los mensajes de correo electrónico están presentes en varios clústeres, el número total real de mensajes de correo electrónico identificados (y afectados por acciones de corrección) es el número de mensajes de correo electrónico únicos que aparecen en todos los mensajes de correo electrónico de los destinatarios y los clústeres originales.

Tanto [Explorer](threat-explorer.md) como Air cuentan los mensajes de correo electrónico por destinatario, ya que los veredictos, las acciones y las ubicaciones de entrega de seguridad varían en función de cada destinatario. Por lo tanto, un mensaje de correo electrónico original enviado a tres usuarios cuenta como un total de tres mensajes de correo electrónico en lugar de un mensaje de correo electrónico.

Puede haber casos en los que un correo electrónico se cuente dos o más veces, como cuando un correo electrónico tiene varias acciones en él, o cuando hay varias copias del correo electrónico cuando se producen todas las acciones.

Por ejemplo, un correo electrónico de malware que se detecta al entregar puede dar como resultado un correo electrónico bloqueado (en cuarentena) y un correo electrónico reemplazado (el archivo de amenaza se reemplaza con un archivo de advertencia y, a continuación, se entrega en el buzón del usuario). Dado que hay literalmente dos copias del correo electrónico en el sistema, es posible que ambas se cuenten en el recuento de clústeres.

> [!IMPORTANT]
> Estos son algunos puntos que debe tener en cuenta:
>
> - Los recuentos de correo electrónico se calculan en el momento de la investigación y se recalculan algunos recuentos cuando abre controles flotantes de investigación (según una consulta base).
>
> - Los recuentos de correo electrónico que se muestran para los clústeres de correo electrónico en la pestaña **correo** electrónico y el valor de cantidad de correo electrónico que se muestra en el control flotante de clúster se calculan en el momento de la investigación y no cambian.
>
> - El recuento de correo electrónico que se muestra en la parte inferior de la ficha **correo** electrónico del control flotante del clúster de correo electrónico y el número de mensajes de correo electrónico que se muestran en el explorador reflejan los mensajes de correo electrónico recibidos después del análisis inicial de la investigación.

Por lo tanto, un clúster de correo electrónico que muestra una cantidad original de 10 mensajes de correo electrónico mostraría un total de 15 en la lista de correo electrónico a menos de cinco mensajes de correo electrónico entre la fase de análisis de investigación y el administrador revisa la investigación. Del mismo modo, las investigaciones antiguas podrían empezar a mostrar recuentos superiores a las consultas del explorador, ya que los datos de Microsoft defender para Office 365 plan 2 expiran después de 7 días para las pruebas y después de 30 días para las licencias de pago.

Mostrar recuentos históricos y actuales en vistas diferentes se realiza para indicar el impacto del correo electrónico en el momento de la investigación y el impacto actual hasta el momento en que se ejecuta la corrección.

> [!NOTE]
> En el contexto del correo electrónico, es posible que vea una superficie de amenaza con anomalías de volumen como parte de la investigación. Una anomalía de volumen indica un pico en mensajes de correo electrónico similares en torno a la hora del evento de investigación en comparación con los plazos anteriores. Este pico en el tráfico de correo electrónico con características similares (por ejemplo, el asunto y el dominio del remitente, la similitud de cuerpo y la IP del remitente) es el principio del inicio de las campañas de correo electrónico o de los ataques.
> Sin embargo, las campañas de correo electrónico masivos, de correo no deseado y legítimas suelen compartir estas características.
>
> Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con amenazas de malware o phish identificadas mediante motores antivirus, detonación o reputación malintencionada.

### <a name="user-investigation"></a>Investigación del usuario

En la pestaña **usuarios** , puede ver todos los usuarios identificados como parte de la investigación. Las cuentas de usuario aparecen en la investigación cuando hay un evento o una indicación de que esas cuentas de usuario podrían verse afectadas o en peligro.

Por ejemplo, en la siguiente imagen, AIR ha identificado indicadores de peligro y anomalías en función de una nueva regla de bandeja de entrada creada. Hay disponibles detalles adicionales (evidencia) de la investigación en las vistas detalladas de esta pestaña. Los indicadores de exposición y anomalías también pueden incluir detecciones de anomalías de [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).

![Página de usuarios de investigación de aire](../../media/air-investigationuserspage.png)

Puede:

- Obtenga una introducción visual de los resultados de usuario identificados y los riesgos encontrados.

- Seleccione un usuario para abrir una página emergente que muestre todos los detalles de la alerta.

### <a name="machine-investigation"></a>Investigación de máquina

En la pestaña **máquinas** , puede ver todos los equipos identificados como parte de la investigación.

![Página de la máquina de investigación de aire](../../media/air-investigationmachinepage.png)

Como parte de las guías, AIR correlaciona las amenazas de correo electrónico con los dispositivos (por ejemplo, malware zapped). Por ejemplo, una investigación pasa un hash de archivo malintencionado a [Microsoft defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) que el extremo lo investigue. Esto permite la investigación automatizada de las máquinas pertinentes para los usuarios, para ayudar a garantizar que las amenazas se dirijan en la nube y en los extremos.

Puede:

- Obtenga información general visual de las amenazas y los equipos actuales encontrados.

- Seleccione un equipo para abrir una vista en las investigaciones relacionadas [de Microsoft defender para extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) en el centro de seguridad de Microsoft defender.

### <a name="entity-investigation"></a>Investigación de entidades

En la pestaña **entidades** , puede ver las entidades identificadas y analizadas como parte de la investigación.

Aquí, puede ver las entidades investigadas y los detalles de los tipos de entidades, como los mensajes de correo electrónico, los clústeres, las direcciones IP, los usuarios, etc. También puede ver cuántas entidades se han analizado y las amenazas que se han asociado a cada una de ellas.

![Página de entidades de investigación de aire](../../media/air-investigationentitiespage.png)

Puede:

- Obtenga información general visual de las entidades de investigación y las amenazas encontradas.

- Seleccione una entidad para abrir una página emergente que muestre los detalles de la entidad relacionada.

![Detalles de entidades de investigación de aire](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro de la guía

En la pestaña **registro** , puede ver todos los pasos de la guía que se han producido durante la investigación. El registro captura un inventario completo de todos los analizadores y las acciones completadas por las capacidades de investigación automática de Office 365 como parte del aire. Proporciona una vista clara de todos los pasos realizados, incluida la propia acción, una descripción y la duración de la real desde el principio hasta el final.

![Página de registro de investigación de aire](../../media/air-investigationlogpage.png)

Puede:

- Vea una descripción general visual de los pasos de la guía realizados.
- Exporte los resultados a un archivo CSV.
- Filtrar la vista.

### <a name="recommended-actions"></a>Acciones recomendadas

En la ficha **acciones** , puede ver todas las acciones de la guía que se recomiendan para la corrección después de que la investigación haya finalizado. Acciones Capture los pasos que Microsoft recomienda realizar al final de una investigación. Puede realizar acciones de corrección aquí si selecciona una o varias acciones.

Al seleccionar **APPROVE** permite que se inicie la corrección. (Es necesario disponer de los permisos adecuados: el rol de **búsqueda y purga** es necesario para ejecutar acciones desde el explorador y el aire).

Por ejemplo, un lector de seguridad puede ver las acciones, pero no aprobarlas.

> [!IMPORTANT]
> No es necesario aprobar todas las acciones. Si no está de acuerdo con la acción recomendada o su organización no elige determinados tipos de acciones, puede optar por **rechazar** las acciones o simplemente omitirlas y no realizar ninguna acción.
> La aprobación o el rechazo de todas las acciones permite que la investigación se cierre completamente (el estado pasa a ser corregido), mientras que dejar algunas acciones incompletas da como resultado un cambio en el estado de la investigación a un estado parcialmente corregido.

![Página de acción de investigaciones de aire](../../media/air-investigationactionspage.png)

Puede:

- Obtenga información general visual de las acciones recomendadas de la guía.
- Seleccione una sola acción o varias acciones.
- Aprobar o rechazar acciones recomendadas con comentarios.
- Exporte los resultados a un archivo CSV.
- Filtrar la vista.

## <a name="next-steps"></a>Siguientes pasos

- [Revisar y aprobar acciones pendientes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
