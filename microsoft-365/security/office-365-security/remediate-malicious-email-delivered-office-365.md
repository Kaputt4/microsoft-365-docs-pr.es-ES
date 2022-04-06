---
title: Corregir el correo electrónico malintencionado que se entregó en Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.collection: M365-security-compliance
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection: ''
search.appverid: MET150
description: Corrección de amenazas
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ba8564ef5ecbd261dc47b2f0a48d6d4d77d620a
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638323"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Corregir el correo electrónico malintencionado entregado en Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Remediation means taking a prescribed action against a threat. El sistema puede limpiar el correo electrónico malintencionado enviado a su organización, mediante la purga automática (ZAP) de hora cero, o por los equipos de seguridad a través de acciones de corrección como mover a la bandeja de *entrada, pasar* a correo no *deseado, mover* a elementos eliminados *, eliminar* temporalmente o eliminar de forma *permanente.* Pertahanan Microsoft untuk Office 365 Plan 2/E5 permite a los equipos de seguridad corregir las amenazas en la funcionalidad de correo electrónico y colaboración mediante una investigación manual y automatizada.

> [!NOTE]
> Para corregir el correo electrónico malintencionado, los equipos de seguridad necesitan el rol *Buscar* y purgar asignados. La asignación de roles se [realiza mediante permisos en el portal de Microsoft 365 Defender funciones](permissions-microsoft-365-security-center.md).

## <a name="what-you-need-to-know-before-you-begin"></a>Lo que necesita saber antes de comenzar

Los administradores pueden realizar las acciones necesarias en los correos electrónicos, pero para que se aprueben estas  acciones, deben tener el rol Buscar y purgar asignados en los permisos de colaboración correo electrónico **&** en el portal de Microsoft 365 Defender. Sin el *rol Buscar y purgar"* agregado a uno de los grupos de roles, no podrán ejecutar la acción.

## <a name="manual-and-automated-remediation"></a>Corrección manual y automatizada

*La búsqueda manual* se produce cuando los equipos de seguridad identifican las amenazas manualmente mediante las funciones de búsqueda y filtrado del Explorador. La corrección manual del correo electrónico se puede desencadenar a través de cualquier vista de correo electrónico (*malware*, *phish* o *todo* el correo electrónico) después de identificar un conjunto de correos electrónicos que deben corregirse.

> [!div class="mx-imgBorder"]
> [![Captura de pantalla de la búsqueda manual Office 365 explorador de amenazas por fecha.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Los equipos de seguridad pueden usar el Explorador para seleccionar correos electrónicos de varias maneras:

- Elegir correos electrónicos a mano: use filtros en varias vistas. Seleccione hasta 100 correos electrónicos para corregir.

- Selección de consulta: seleccione una consulta completa mediante el botón **seleccionar todo en la** parte superior. La misma consulta también se muestra en detalles de envío de correo del centro de acciones. Los clientes pueden enviar un máximo de 200 000 correos electrónicos desde el explorador de amenazas.  

- Selección de consultas con exclusión: en ocasiones, los equipos de operaciones de seguridad pueden querer corregir los correos electrónicos seleccionando una consulta completa y excluyendo algunos correos electrónicos de la consulta manualmente. Para ello, un administrador puede usar la casilla **Seleccionar** todo y desplazarse hacia abajo para excluir los correos electrónicos manualmente. La consulta puede contener un máximo de 1.000 correos electrónicos. El número máximo de exclusiones es 100.

Una vez que los correos electrónicos se seleccionan a través del Explorador, puede comenzar la corrección mediante la acción directa o mediante la cola de correos electrónicos para una acción:

- Aprobación directa: cuando las acciones como mover a la  bandeja de *entrada, pasar* a correo no *deseado, mover* a elementos eliminados *, eliminar* temporalmente o eliminar de forma permanente son seleccionadas por el personal de seguridad que tiene los permisos adecuados y se siguen los pasos siguientes en la corrección, el proceso de corrección comienza a ejecutar la acción seleccionada.
> [!NOTE]
>A medida que se pone en marcha la corrección, genera una alerta y una investigación en paralelo. La alerta aparece en la cola de alertas con el nombre "Acción administrativa enviada por un administrador", lo que sugiere que el personal de seguridad realizó la acción de corregir una entidad. Presenta detalles como el nombre de la persona que realizó la acción, el vínculo de investigación de soporte, el tiempo, etc. Funciona muy bien para saber cada vez que se realiza una acción dura como la corrección en las entidades. Todas estas acciones se pueden realizar en la ficha Centro de **acciones & envíosHistoria** \>   ->  (versión preliminar pública).

- Aprobación en dos pasos: los administradores que no tienen permisos adecuados o que necesitan esperar para ejecutar la acción pueden realizar una acción de "agregar a la corrección". En este caso, los correos electrónicos dirigidos se agregan a un contenedor de corrección. La aprobación es necesaria antes de que se ejecute la corrección.

**Las acciones automatizadas de investigación** y respuesta se desencadenan mediante alertas o por equipos de operaciones de seguridad desde el Explorador. Estas pueden incluir acciones de corrección recomendadas que deben ser aprobadas por un equipo de operaciones de seguridad. Estas acciones se incluyen en la **pestaña Acción** en la investigación automatizada.

> [!div class="mx-imgBorder"]
> [![Correo con malware en la página "Zapped" que muestra el tiempo de ejecución de Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Todas las correcciones (aprobaciones directas) creadas en el Explorador, búsqueda avanzada o a través de la investigación automatizada se muestran en el Centro de acciones. Accede a ellos a través del panel de navegación izquierdo en **Acciones & de acciones** **del**  ->  centro de **envíosHistoria**\>.

Todas las correcciones (aprobaciones directas) que se crearon en explorer o búsqueda avanzada o a través de la investigación automatizada se muestran en el Centro de acciones. Accede a ellos a través del panel de navegación izquierdo en **Acciones & de acciones** **del**  ->  centro de **envíosHistoria**\>. 

Acciones manuales pendientes de aprobación mediante el proceso de aprobación en dos pasos (1. agregar a la corrección por un miembro del equipo de operación de seguridad, 2. revisado y aprobado por otro miembro del equipo de operaciones de seguridad) solo están visibles en el centro de acción de Defender pre Office 365  heredado y no \> en incidentes/investigaciones ni en el Centro de acción unificada.

> [!NOTE]
> Aprobación en dos pasos: acciones solo disponibles en el Centro de acciones de office  **Review** \> **Action Center**

:::image type="content" source="../../media/microsoft-365-defender-action-center-history.png" alt-text="El Centro de acciones unificado muestra 30 días de acciones de corrección.":::

El Centro de acciones unificado muestra las acciones de corrección de los últimos 30 días. Las acciones realizadas a través del Explorador se enumeran por el nombre que el equipo de operaciones de seguridad proporcionó cuando se creó la corrección, así como el identificador de aprobación, el identificador de investigación. Las acciones realizadas a través de investigaciones automatizadas tienen títulos que comienzan con la alerta relacionada que desencadenó la investigación, como el clúster de correo electrónico *Zap*.

Abra cualquier elemento de corrección para ver detalles sobre él, incluido su nombre de corrección, id. de aprobación, identificador de investigación, fecha de creación, descripción, estado, origen de acción, tipo de acción, decidido por, estado. También abre un panel lateral con detalles de acción, detalles del clúster de correo electrónico, alertas e detalles del incidente.

- *Esta página abre* una investigación de administrador que contiene menos detalles y pestañas. Muestra detalles como: alerta relacionada, entidad seleccionada para corrección, acción realizada, estado de corrección, recuento de entidades, registros, aprobador de acción. Esta investigación realiza un seguimiento de la investigación realizada por el administrador manualmente y contiene detalles de las selecciones realizadas por el administrador, por lo que se denomina investigación de acción de administrador. No es necesario actuar sobre la investigación y alertar de que ya está en estado aprobado.   
- *Recuento de correo electrónico* Muestra el número de correos electrónicos enviados a través del Explorador de amenazas. Estos correos electrónicos pueden ser acciónbles o no se pueden realizar acciones. 
- *Registros de acciones* Muestra los detalles del estado de corrección como correcto/ con error/ ya en el destino

  > [!div class="mx-imgBorder"]
  > [![Captura de pantalla del centro de acciones con amenazas que pueden actuar y que no pueden actuar.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Actionable**: los correos electrónicos en las siguientes ubicaciones de buzones de correo en la nube se pueden actuar y mover:
    - Bandeja de entrada
    - Correo no deseado
    - Carpeta eliminada
    - Carpeta eliminada temporalmente

      > [!NOTE]
      > Actualmente, solo un usuario con acceso al buzón puede recuperar elementos de una carpeta eliminada temporalmente.

  - **No se pueden realizar** acciones: los correos electrónicos de las siguientes ubicaciones no se pueden actuar ni mover en acciones de corrección:
    - Quarantine
    - Carpeta eliminada de forma permanente
    - Local/externo
    - Error o caída

  Los mensajes sospechosos se clasifican como remediables o nomediables. En la mayoría de los casos, los mensajes remediables y nomediables combinan igual al total de mensajes enviados. Pero, en raras ocasiones, esto puede no ser cierto. Esto puede ocurrir debido a retrasos del sistema, tiempos de espera o mensajes expirados. Los mensajes expiran en función del período de retención del Explorador para su organización.

  A menos que esté remediando mensajes antiguos después del período de retención del Explorador de la organización, es aconsejable reintentar la corrección de elementos si ve incoherencias de número. En el caso de los retrasos del sistema, las actualizaciones de corrección normalmente se actualizan en unas pocas horas.

  Si el período de retención de su organización para el correo electrónico en el Explorador es de 30 días y está remediando los correos electrónicos que se van de 29 a 30 días, es posible que los recuentos de envíos de correo no siempre se agreguen. Es posible que los correos electrónicos ya empezaron a salir del período de retención.

  Si las correcciones están bloqueadas en el estado "En curso" durante un tiempo, es probable que se deba a retrasos del sistema. Podría tardar hasta unas horas en corregirse. Es posible que vea variaciones en los recuentos de envío de correo, ya que es posible que algunos de los correos electrónicos no se hayan incluido en la consulta al principio de la corrección debido a retrasos del sistema. Es una buena idea reintentar la corrección en estos casos.

  > [!NOTE]
  > Para obtener mejores resultados, la corrección debe realizarse en lotes de 50 000 o menos.

  Solo se actúan los correos electrónicos que se pueden corregir durante la corrección. El sistema de correo electrónico Office 365 no puede corregir los correos electrónicos no inmediatos, ya que no se almacenan en buzones de correo en la nube.

  Los administradores pueden realizar acciones en los correos electrónicos en cuarentena si es necesario, pero esos correos electrónicos expirarán fuera de cuarentena si no se purgan manualmente. De forma predeterminada, los usuarios no pueden acceder a los correos electrónicos en cuarentena debido a contenido malintencionado, por lo que el personal de seguridad no tiene que realizar ninguna acción para deshacerse de las amenazas en cuarentena. Si los correos electrónicos son locales o externos, se puede ponerse en contacto con el usuario para dirigirse al correo electrónico sospechoso. O bien, los administradores pueden usar herramientas de seguridad/servidor de correo electrónico independientes para la eliminación. Estos correos electrónicos se pueden identificar aplicando la ubicación *de entrega =* filtro externo local en el Explorador. Para correo electrónico con errores o eliminados, o correo electrónico no accesible por los usuarios, no habrá ningún correo electrónico para mitigar, ya que estos correos no llegan al buzón.

 
- **Registros de acciones**: muestra los mensajes corregidos, correctos, con errores, ya en el destino.

  El estado puede ser:

  - **Iniciado**: se desencadena la corrección.
    - **En cola**: la corrección se pone en cola para mitigar los mensajes de correo electrónico.
    - **En curso**: la mitigación está en curso.
    - **Completado**: mitigación de todos los correos electrónicos que se pueden corregir completados correctamente o con algunos errores.
    - **Error**: no se ha realizado correctamente ninguna corrección.

  Como solo se pueden actuar mensajes de correo electrónico que se puedan corregir, la limpieza de cada correo electrónico se muestra como correcta o con errores. Del total de mensajes de correo electrónico que se pueden corregir, se notifican mitigaciones correctas y con errores.

  - **Correcto**: se ha realizado la acción deseada en los correos electrónicos que se pueden corregir. Por ejemplo: un administrador desea quitar correos electrónicos de buzones de correo, por lo que el administrador realiza la acción de eliminar mensajes de correo electrónico de forma suave. Si no se encuentra un correo electrónico correcto en la carpeta original después de realizar la acción, el estado se mostrará como correcto.

  - **Error**: error en la acción deseada en los correos electrónicos que se pueden corregir. Por ejemplo: un administrador desea quitar correos electrónicos de buzones de correo, por lo que el administrador realiza la acción de eliminar mensajes de correo electrónico de forma suave. Si aún se encuentra un correo electrónico que se puede corregir en el buzón después de realizar la acción, el estado se mostrará como con error.
  
  - **Ya en el destino**: la acción deseada ya se ha realizado en el correo electrónico o el correo electrónico ya existía en la ubicación de destino. Por ejemplo: el administrador eliminó temporalmente un correo electrónico a través del Explorador el primer día. A continuación, los correos electrónicos similares se muestran el día 2, que el administrador vuelve a eliminar temporalmente. Al seleccionar estos correos electrónicos, el administrador termina seleccionando algunos correos electrónicos del primer día que ya se han eliminado temporalmente. Ahora estos correos electrónicos no se volverán a realizar, solo se mostrarán como "ya en destino", ya que no se ha realizado ninguna acción sobre ellos como existían en la ubicación de destino.

  - **Nuevo**: Se *ha agregado una columna* Ya en destino en el registro de acciones. Esta característica usa la ubicación de entrega más reciente en el Explorador de amenazas para indicar si el correo ya se ha corregido. *Ya en el destino* ayudará a los equipos de seguridad a comprender el número total de mensajes que aún deben abordarse.

Las acciones solo se pueden realizar en los mensajes de las carpetas Bandeja de entrada, Correo no deseado, Eliminado y Eliminado temporalmente del Explorador de amenazas. Este es un ejemplo de cómo funciona la nueva columna. Una *acción de eliminación* suave tiene lugar en el mensaje presente en la Bandeja de entrada y, a continuación, el mensaje se controlará según las directivas. La próxima vez que se realice una eliminación suave, este mensaje se mostrará debajo de la columna "Ya en el destino" que indica que no es necesario que se vuelva a tratar.

Seleccione cualquier elemento del registro de acciones para mostrar los detalles de corrección. Si los detalles dicen "correcto" o "no se encontró en el buzón", ese elemento ya se quitó del buzón. A veces hay un error del sistema durante la corrección. En esos casos, es una buena idea volver a intentar la acción de corrección.

En caso de corregir grandes lotes de correo electrónico, exporte los mensajes enviados para su corrección a través del envío de correo y los mensajes que se han corregido a través de registros de acciones. El límite de exportación se aumenta a 100 000 registros.

 Los administradores pueden realizar acciones de corrección como mover mensajes de correo electrónico a la carpeta Elementos eliminados, Bandeja de entrada o correo no deseado y eliminar acciones como eliminación temporal o eliminación permanente de páginas de búsqueda avanzada.

:::image type="content" source="../../media/microsoft-365-defender-advanced-hunting-actions-pane.png" alt-text="El panel Búsqueda avanzada, Tomar acciones con tu elección de acciones.":::

La corrección mitiga las amenazas, aborda correos electrónicos sospechosos y ayuda a mantener una organización segura.
