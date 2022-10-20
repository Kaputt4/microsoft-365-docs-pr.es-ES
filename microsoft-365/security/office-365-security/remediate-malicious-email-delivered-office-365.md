---
title: Corrección del correo electrónico malintencionado que se entregó en Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: conceptual
ms.collection: m365-security
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection: ''
search.appverid: MET150
description: Corrección de amenazas
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 09479dc2a8da8e7b8df9d4a2eae07d5a4c0b4dc6
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622076"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Corregir el correo electrónico malintencionado entregado en Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

La corrección significa tomar una acción prescrita contra una amenaza. El sistema puede limpiar el correo electrónico malintencionado enviado a su organización mediante la purga automática de cero horas (ZAP) o los equipos de seguridad a través de acciones de corrección, como *pasar a la bandeja de entrada*, *pasar a correo no deseado*, *mover a elementos eliminados*, *eliminar temporalmente* o *eliminar de forma rígida*. Microsoft Defender para Office 365 Plan 2/E5 permite a los equipos de seguridad corregir las amenazas en la funcionalidad de correo electrónico y colaboración a través de una investigación manual y automatizada.

> [!NOTE]
> Para corregir el correo electrónico malintencionado, los equipos de seguridad necesitan que se les asigne el rol *Buscar y purgar* . La asignación de roles se realiza mediante [permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="what-you-need-to-know-before-you-begin"></a>Lo que necesita saber antes de empezar

Los administradores pueden realizar las acciones necesarias en los correos electrónicos, pero para obtener la aprobación de esas acciones, deben tener asignado el rol *Buscar y purgar* en el Email & permisos de **colaboración** en el portal de Microsoft 365 Defender. Sin el rol *Buscar y purgar agregado* a uno de los grupos de roles, no podrán ejecutar la acción.

Dado que las acciones de correo electrónico crean investigaciones automatizadas en el back-end, debe habilitar *La investigación automatizada*. Vaya a **Configuración** \> **Puntos de conexión** **Características avanzadas** \> y active **Investigación automatizada**.

## <a name="manual-and-automated-remediation"></a>Corrección manual y automatizada

*La búsqueda manual* se produce cuando los equipos de seguridad identifican las amenazas manualmente mediante las funcionalidades de búsqueda y filtrado en el Explorador. La corrección manual del correo electrónico se puede desencadenar a través de cualquier vista de correo electrónico (*malware*, *phish* o *todo el correo electrónico*) después de identificar un conjunto de correos electrónicos que deben corregirse.

:::image type="content" source="../../media/microsoft-365-defender-threat-explorer-manual-remediation.png" alt-text="Captura de pantalla de la búsqueda manual en Office 365 Explorer por fecha.":::

Los equipos de seguridad pueden usar el Explorador para seleccionar correos electrónicos de varias maneras:

- Elegir correos electrónicos a mano: use filtros en varias vistas. Seleccione hasta 100 correos electrónicos para corregirlos.

- Selección de consulta: seleccione una consulta completa con el botón **seleccionar todo** en la parte superior. La misma consulta también se muestra en los detalles del envío de correo del centro de acciones. Los clientes pueden enviar un máximo de 200 000 correos electrónicos desde el explorador de amenazas.  

- Selección de consultas con exclusión: en ocasiones, es posible que los equipos de operaciones de seguridad quieran corregir los correos electrónicos seleccionando una consulta completa y excluyendo manualmente determinados correos electrónicos de la consulta. Para ello, un administrador puede usar la casilla **Seleccionar todo** y desplazarse hacia abajo para excluir los correos electrónicos manualmente. La consulta puede contener un máximo de 1000 correos electrónicos. El número máximo de exclusiones es 100.

Una vez seleccionados los correos electrónicos a través del Explorador, puede iniciar la corrección realizando acciones directas o mediante la puesta en cola de correos electrónicos para una acción:

- Aprobación directa: cuando el personal de seguridad que tiene permisos adecuados selecciona acciones como *mover a la bandeja de entrada*, *mover a elementos* *eliminados*, *eliminar temporalmente* o *eliminar de forma rígida* y se siguen los pasos siguientes en la corrección, el proceso de corrección comienza a ejecutar la acción seleccionada.
> [!NOTE]
> A medida que se inicia la corrección, genera una alerta y una investigación en paralelo. La alerta aparece en la cola de alertas con el nombre "Acción administrativa enviada por un administrador", lo que sugiere que el personal de seguridad tomó la acción de corregir una entidad. Presenta detalles como el nombre de la persona que realizó la acción, el vínculo de apoyo a la investigación, la hora, etc. Funciona muy bien saber cada vez que se realiza una acción dura como la corrección en las entidades. Todas estas acciones se pueden realizar en la **pestaña Historial** del **centro**  ->  de acciones **acciones & envíos** \> (versión preliminar pública).

- Aprobación en dos pasos: los administradores que no tienen los permisos adecuados o que necesitan esperar para ejecutar la acción pueden realizar una acción de "agregar a la corrección". En este caso, los correos electrónicos de destino se agregan a un contenedor de corrección. La aprobación es necesaria antes de que se ejecute la corrección.

Las alertas o los equipos de operaciones de seguridad del Explorador desencadenan acciones **automatizadas de investigación y respuesta**. Estos pueden incluir acciones de corrección recomendadas que deben ser aprobadas por un equipo de operaciones de seguridad. Estas acciones se incluyen en la pestaña **Acción** de la investigación automatizada.

> [!div class="mx-imgBorder"]
> [![Correo con malware en la página "Zapped" que muestra el tiempo de ejecución de Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Todas las correcciones (aprobaciones directas ) creadas en el Explorador, la búsqueda avanzada o la investigación automatizada se muestran en el Centro de acciones. Acceda a ellos a través del panel de navegación izquierdo en la **pestaña** Historial del **Centro**  ->  de acciones **acciones & envíos**\>.

Todas las correcciones (aprobaciones directas) que se crearon en el Explorador o la búsqueda avanzada o a través de la investigación automatizada se muestran en el Centro de acciones. Acceda a ellos a través del panel de navegación izquierdo en la **pestaña** Historial del **Centro**  ->  de acciones **acciones & envíos**\>. 

Acciones manuales pendientes de aprobación mediante el proceso de aprobación en dos pasos (1. agregar a la corrección por un miembro del equipo de operaciones de seguridad, 2. revisados y aprobados por otro miembro del equipo de operaciones de seguridad) solo son visibles en el centro de acción de **revisión** \> del centro de acciones de Defender para Office 365 **heredado y no** en incidentes e investigaciones ni en el Centro de acción unificada.

> [!NOTE]
> Aprobación en dos pasos: las acciones solo están disponibles en el **Centro** de acciones de la oficina **Centro de acciones de revisión** \>

:::image type="content" source="../../media/microsoft-365-defender-action-center-history.png" alt-text="El Centro de acciones unificado muestra 30 días de acciones de corrección.":::

El Centro de acciones unificadas muestra las acciones de corrección de los últimos 30 días. Las acciones realizadas a través del Explorador se enumeran por el nombre que el equipo de operaciones de seguridad proporcionó cuando se creó la corrección, así como el identificador de aprobación, el identificador de investigación. Las acciones realizadas a través de investigaciones automatizadas tienen títulos que comienzan con la alerta relacionada que desencadenó la investigación, como el *clúster de correo electrónico de Zap*.

Abra cualquier elemento de corrección para ver los detalles sobre él, incluidos su nombre de corrección, el identificador de aprobación, el identificador de investigación, la fecha de creación, la descripción, el estado, el origen de la acción, el tipo de acción, decidido por, el estado. También se abre un panel lateral con detalles de acción, detalles del clúster de correo electrónico, alertas y detalles de incidentes.

- *Abra la página Investigación* , lo que abre una investigación de administrador que contiene menos detalles y pestañas. Muestra detalles como: alerta relacionada, entidad seleccionada para la corrección, acción realizada, estado de corrección, recuento de entidades, registros, aprobador de la acción. Esta investigación realiza un seguimiento de la investigación realizada por el administrador manualmente y contiene detalles de las selecciones realizadas por el administrador, por lo que se denomina investigación de acción de administrador. No es necesario actuar sobre la investigación y alertar a su ya en estado aprobado.
- *recuento de Email* Muestra el número de correos electrónicos enviados a través del Explorador de amenazas. Estos correos electrónicos pueden ser accionables o no accionables.
- *Registros de acciones* Muestra los detalles de los estados de corrección, como correcto, erróneo y ya en destino.

:::image type="content" source="../../media/microsoft-365-defender-action-center-history-panel.png" alt-text="Se abre el Centro de acciones con la opción Mover a bandeja de entrada.":::

  - **Accionable**: los correos electrónicos de las siguientes ubicaciones de buzón en la nube se pueden actuar y mover:
    - Bandeja de entrada
    - Basura
    - Carpeta eliminada
    - Carpeta eliminada temporalmente

      > [!NOTE]
      > Actualmente, solo un usuario con acceso al buzón puede recuperar elementos de una carpeta eliminada temporalmente.

  - **No accionable**: los correos electrónicos de las siguientes ubicaciones no se pueden actuar ni mover en acciones de corrección:
    - Quarantine
    - Carpeta eliminada de forma rígida
    - Local/externo
    - Error o se ha eliminado

  Los mensajes sospechosos se clasifican como remediables o nomediables. En la mayoría de los casos, los mensajes corregibles y nomediables combinan igual que el total de mensajes enviados. Pero en raras ocasiones esto puede no ser cierto. Esto puede ocurrir debido a retrasos del sistema, tiempos de espera o mensajes expirados. Los mensajes expiran en función del período de retención del Explorador para su organización.

  A menos que corrija mensajes antiguos después del período de retención del Explorador de la organización, es recomendable volver a intentar corregir los elementos si ve incoherencias en el número. En el caso de los retrasos del sistema, las actualizaciones de corrección se suelen actualizar en unas pocas horas.

  Si el período de retención de correo electrónico de su organización en el Explorador es de 30 días y va a corregir los correos electrónicos que se vuelven de 29 a 30 días, es posible que los recuentos de envíos de correo no siempre se suman. Es posible que los correos electrónicos ya hayan empezado a salir del período de retención.

  Si las correcciones se bloquean en el estado "En curso" durante un tiempo, es probable que se deba a retrasos del sistema. La corrección puede tardar hasta unas horas. Es posible que vea variaciones en los recuentos de envío de correo, ya que es posible que algunos de los correos electrónicos no se hayan incluido en la consulta al principio de la corrección debido a retrasos del sistema. Es una buena idea reintentar la corrección en estos casos.

  > [!NOTE]
  > Para obtener mejores resultados, la corrección debe realizarse en lotes de 50 000 o menos.

  Solo los correos electrónicos que se pueden corregir se actúan durante la corrección. El sistema de correo electrónico Office 365 no puede corregir los correos electrónicos nomediables, ya que no se almacenan en buzones de correo en la nube.

  Los administradores pueden realizar acciones en los correos electrónicos en cuarentena si es necesario, pero esos correos expirarán fuera de cuarentena si no se purgan manualmente. De forma predeterminada, los correos electrónicos en cuarentena debido a contenido malintencionado no son accesibles para los usuarios, por lo que el personal de seguridad no tiene que realizar ninguna acción para deshacerse de las amenazas en cuarentena. Si los correos electrónicos son locales o externos, se puede ponerse en contacto con el usuario para dirigir el correo electrónico sospechoso. O bien, los administradores pueden usar herramientas de seguridad o servidor de correo electrónico independientes para la eliminación. Estos correos electrónicos se pueden identificar aplicando la *ubicación de entrega =* filtro externo local en el Explorador. En el caso del correo electrónico con errores o eliminados, o el correo electrónico no accesible para los usuarios, no habrá ningún correo electrónico que mitigar, ya que estos correos no llegan al buzón.

 
- **Registros de acciones**: muestra los mensajes corregidos, correctos, erróneos, que ya están en destino.

  El estado puede ser:

  - **Iniciado**: se desencadena la corrección.
    - **En cola**: la corrección se pone en cola para mitigar los correos electrónicos.
    - **En curso**: la mitigación está en curso.
    - **Completado**: la mitigación en todos los correos electrónicos correctos se completó correctamente o con algunos errores.
    - **Error**: no se han realizado correctamente las correcciones.

  Como solo se pueden actuar en los correos electrónicos correctos, la limpieza de cada correo electrónico se muestra como correcta o errónea. Del total de correos electrónicos que se pueden corregir, se notifican mitigaciones correctas y erróneas.

  - **Correcto**: se ha realizado la acción deseada en los correos electrónicos que se pueden corregir. Por ejemplo: un administrador quiere quitar correos electrónicos de los buzones, por lo que el administrador realiza la acción de eliminación temporal de correos electrónicos. Si no se encuentra un correo electrónico correcto en la carpeta original después de realizar la acción, el estado se mostrará como correcto.

  - **Error**: error en la acción deseada en los correos electrónicos que se pueden corregir. Por ejemplo: un administrador quiere quitar correos electrónicos de los buzones, por lo que el administrador realiza la acción de eliminación temporal de correos electrónicos. Si todavía se encuentra un correo electrónico correcto en el buzón después de realizar la acción, el estado se mostrará como erróneo.
  
  - **Ya en destino**: la acción deseada ya se ha realizado en el correo electrónico o el correo electrónico ya existe en la ubicación de destino. Por ejemplo: el administrador eliminó temporalmente un correo electrónico a través del Explorador el primer día. A continuación, los correos electrónicos similares aparecen el día 2, que el administrador vuelve a eliminar temporalmente. Al seleccionar estos correos electrónicos, el administrador termina recogiendo algunos correos electrónicos del primer día que ya se han eliminado temporalmente. Ahora estos correos electrónicos no se volverán a actuar, simplemente se mostrarán como "ya en destino", ya que no se ha realizado ninguna acción en ellos tal y como existían en la ubicación de destino.

  - **Nuevo**: Se ha agregado una columna *Ya en destino* en el registro de acciones. Esta característica usa la ubicación de entrega más reciente en el Explorador de amenazas para indicar si el correo ya se ha corregido. *Ya en el destino* ayudará a los equipos de seguridad a comprender el número total de mensajes que todavía deben abordarse.

Las acciones solo se pueden realizar en los mensajes de las carpetas Bandeja de entrada, Correo no deseado, Eliminado y Eliminado temporalmente del Explorador de amenazas. Este es un ejemplo de cómo funciona la nueva columna. Se realiza una *acción de eliminación temporal* en el mensaje presente en la Bandeja de entrada y, a continuación, el mensaje se controlará según las directivas. La próxima vez que se realice una eliminación temporal, este mensaje se mostrará en la columna "Ya en destino" señalando que no es necesario volver a abordarlo.

Seleccione cualquier elemento del registro de acciones para mostrar los detalles de la corrección. Si los detalles dicen "correcto" o "no encontrado en el buzón", ese elemento ya se quitó del buzón. A veces hay un error del sistema durante la corrección. En esos casos, es una buena idea volver a intentar la acción de corrección.

En caso de corregir grandes lotes de correo electrónico, exporte los mensajes enviados para la corrección a través del envío de correo y los mensajes que se corrigieron a través de registros de acciones. El límite de exportación se aumenta a 100 000 registros.

 Los administradores pueden realizar acciones de corrección, como mover mensajes de correo electrónico a la carpeta Correo no deseado, Bandeja de entrada o Elementos eliminados, y eliminar acciones como eliminación temporal o eliminación rígida de páginas de búsqueda avanzada.

:::image type="content" source="../../media/microsoft-365-defender-advanced-hunting-actions-pane.png" alt-text="El panel Búsqueda avanzada y Acciones con su elección de acciones.":::

La corrección mitiga las amenazas, aborda los correos electrónicos sospechosos y ayuda a mantener una organización segura.
