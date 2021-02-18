---
title: Corregir el correo electrónico malintencionado que se entregó en Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Corrección de amenazas
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b32982298a368dc435dad8b6c09188321d099e2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289238"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Corregir el correo electrónico malintencionado entregado en Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)

La corrección significa tomar una acción recomendada contra una amenaza. El sistema puede limpiar el correo electrónico malintencionado enviado a su organización, a través de la purga automática (ZAP) de cero horas, o bien los equipos de seguridad mediante acciones de corrección como mover a la bandeja de *entrada,* mover a correo no *deseado,* mover a elementos eliminados, eliminar temporalmente o eliminar permanentemente.  Microsoft Defender para Office 365 P2/E5 permite a los equipos de seguridad corregir amenazas en la funcionalidad de colaboración y correo electrónico a través de investigaciones manuales y automatizadas.

> [!NOTE]
> Para corregir el correo electrónico malintencionado, los equipos de seguridad necesitan que se les asigne el rol *de búsqueda* y depuración. La asignación de roles se realiza mediante permisos en el centro de seguridad y cumplimiento.

## <a name="what-you-need-to-know-before-you-begin"></a>Lo que necesita saber antes de comenzar

Los administradores pueden tomar las medidas necesarias en los  correos electrónicos, pero para que se aprueben esas acciones, deben tener asignado el rol de búsqueda y depuración a través de los permisos del Centro de seguridad **&** \> **cumplimiento.** Sin el rol de "búsqueda y depuración" agregado a uno de los grupos de roles, no podrán ejecutar la acción.

## <a name="manual-and-automated-remediation"></a>Corrección manual y automatizada

*La búsqueda manual* se produce cuando los equipos de seguridad identifican las amenazas manualmente mediante las funciones de búsqueda y filtrado en el Explorador de amenazas. La corrección manual del correo electrónico se puede desencadenar a través de cualquier vista de correo electrónico *(malware,* *suplantación* de identidad o todo el correo *electrónico)* después de identificar un conjunto de correos electrónicos que deben corregirse.

> [!div class="mx-imgBorder"]
> [![Búsqueda manual en el Explorador de amenazas de Office 365 por fecha.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Los equipos de seguridad pueden usar el Explorador de amenazas para seleccionar correos electrónicos de varias maneras:

- Elegir correos electrónicos a mano: use filtros en varias vistas. Seleccione hasta 100 correos electrónicos para corregir.

- Selección de consulta: seleccione una consulta completa con el botón **seleccionar todo en la** parte superior. La misma consulta también se muestra en los detalles de envío de correo del centro de acciones.

- Selección de consulta con exclusión: a veces, es posible que los equipos de operaciones de seguridad quieran corregir correos electrónicos seleccionando una consulta completa y excluyendo algunos correos electrónicos de la consulta manualmente. Para ello, un administrador  puede usar la casilla Seleccionar todo y desplazarse hacia abajo para excluir los correos electrónicos manualmente. La consulta puede contener un máximo de 1.000 correos electrónicos. El número máximo de exclusiones es 100.

Una vez que los correos electrónicos se seleccionan a través del Explorador de amenazas, puede comenzar la corrección mediante una acción directa o mediante la cola de correos electrónicos para una acción:

- Aprobación directa: cuando el personal de seguridad que tiene los permisos  adecuados selecciona acciones como mover a la bandeja de *entrada,* mover a correo no *deseado,* mover a elementos eliminados, eliminar temporalmente o eliminar permanentemente, y se siguen los pasos siguientes de la corrección, el proceso de corrección comienza a ejecutar la acción seleccionada. Un menú desplegable temporal muestra la corrección en curso.

- Aprobación en dos pasos: los administradores que no tienen los permisos adecuados o que necesitan esperar para ejecutar la acción pueden realizar una acción de "agregar a la corrección". En este caso, los correos electrónicos dirigidos se agregan a un contenedor de corrección. La aprobación es necesaria antes de que se ejecute la corrección.

**Las acciones automatizadas de investigación y** respuesta se desencadenan mediante alertas o por equipos de operaciones de seguridad desde el Explorador de amenazas. Estas pueden incluir acciones de corrección recomendadas que deben ser aprobadas por un equipo de operaciones de seguridad. Estas acciones se incluyen en la **pestaña Acción** en la investigación automatizada.

> [!div class="mx-imgBorder"]
> [![Correo con malware en la página "Zapped" que muestra el tiempo de ejecución de Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Todas las correcciones (ya sea la aprobación directa o la aprobación en dos pasos) que se crearon en el Explorador de amenazas, así como las acciones aprobadas procedentes de investigaciones automatizadas se muestran en el Centro de actividades. Accede a ellos a través del panel de navegación izquierdo en **El Centro de** acciones de \> **revisión.**

> [!div class="mx-imgBorder"]
> [![El centro de acciones con una lista de amenazas por fecha y gravedad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

El Centro de actividades muestra todas las acciones de corrección de los últimos 30 días. Las acciones realizadas a través del Explorador de amenazas se enumeran con el nombre que el equipo de operaciones de seguridad proporcionó cuando se creó la corrección. Las acciones realizadas a través de investigaciones automatizadas tienen títulos que comienzan con la alerta relacionada que desencadenó la investigación, como "Zap email cluster...".

Abra cualquier elemento de corrección para ver detalles sobre él, incluido su nombre, fecha de creación, descripción, gravedad de amenaza y estado. También muestra las dos pestañas siguientes.

- **Pestaña envío de** correo: muestra el número de correos electrónicos enviados a través del Explorador de amenazas o investigaciones automatizadas que se corregirán. Estos correos electrónicos pueden ser acciones o no se pueden usar.

  > [!div class="mx-imgBorder"]
  > [![El centro de acciones con amenazas que pueden actuar y que no pueden actuar.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Acción:** los correos electrónicos de las siguientes ubicaciones de buzones de correo en la nube se pueden actuar y mover:
    - Bandeja de entrada
    - Correo no deseado
    - Carpeta eliminada
    - Carpeta eliminada temporalmente

      > [!NOTE]
      > Actualmente, solo un usuario con acceso al buzón puede recuperar elementos de una carpeta eliminada temporalmente.

  - **No se puede actuar:** los mensajes de correo electrónico de las siguientes ubicaciones no se pueden actuar ni mover en acciones de corrección:
    - Cuarentena
    - Carpeta eliminada permanentemente
    - Local/externo
    - Error o descartado

  Los mensajes sospechosos se clasifican como corregibles o no. En la mayoría de los casos, la combinación de mensajes correctibles y no recuperables equivale al total de mensajes enviados. Pero en raras ocasiones esto puede no ser cierto. Esto puede ocurrir debido a retrasos del sistema, tiempos de espera o mensajes expirados. Los mensajes expiran en función del período de retención del Explorador de amenazas de la organización.

  A menos que esté remediando mensajes antiguos después del período de retención del Explorador de amenazas de su organización, es aconsejable reintentar la corrección de elementos si ve incoherencias de número. Para los retrasos del sistema, las actualizaciones de corrección se actualizan normalmente en unas pocas horas.

  Si el período de retención de su organización para el correo electrónico en el Explorador de amenazas es de 30 días y va a corregir los correos electrónicos que van de 29 a 30 días, es posible que los recuentos de envío de correo no siempre se agreguen. Es posible que los correos electrónicos ya se han empezado a mover fuera del período de retención.

  Si las correcciones se han quedado bloqueadas en el estado "En curso" durante un tiempo, es probable que se deba a retrasos en el sistema. La corrección puede tardar hasta unas horas. Es posible que vea variaciones en los recuentos de envío de correo, ya que es posible que algunos de los correos electrónicos no se hayan incluido en la consulta al inicio de la corrección debido a retrasos en el sistema. Es una buena idea volver a intentar corregir en estos casos.

  > [!NOTE]
  > Para obtener mejores resultados, la corrección debe realizarse en lotes de 50 000 o menos.

  Durante la corrección, solo se actúa sobre los correos electrónicos que se pueden corregir. El sistema de correo electrónico de Office 365 no puede corregir los correos electrónicos no inmediatos, ya que no se almacenan en buzones en la nube.

  Los administradores pueden tomar medidas en los correos electrónicos en cuarentena si es necesario, pero esos correos electrónicos expirarán de la cuarentena si no se purgan manualmente. Los usuarios no pueden acceder a los correos electrónicos en cuarentena debido a contenido malintencionado, por lo que el personal de seguridad no tiene que realizar ninguna acción para deshacerse de las amenazas en cuarentena. Si los correos electrónicos son locales o externos, se puede contactar con el usuario para dirigirse al correo electrónico sospechoso. O bien, los administradores pueden usar herramientas de seguridad/servidor de correo electrónico independientes para la eliminación. Estos correos electrónicos se pueden identificar aplicando la ubicación de entrega *=* filtro externo local en el Explorador de amenazas. En el caso de correo electrónico fallido o perdido, o correo electrónico no accesible para los usuarios, no habrá ningún correo electrónico para mitigar, ya que estos correos no llegan al buzón.

  La siguiente imagen muestra el aspecto de un envío en el Centro de acciones. Una corrección puede contener varios envíos. Si se aprueban varias acciones a través de una investigación automatizada, cada acción de clúster de correo electrónico o correo electrónico aparece en la misma corrección que un envío diferente.

  > [!div class="mx-imgBorder"]
  > [![Panel desplegable del clúster de correo electrónico ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Seleccione un elemento de envío de correo para mostrar los detalles de esa corrección, como la consulta (cuando se desencadena la corrección mediante investigaciones automatizadas o el Explorador de amenazas mediante la selección de una consulta) y las horas de inicio y finalización de la corrección. También muestra una lista de mensajes que se enviaron para corrección. A medida que los mensajes se mueven fuera del período de retención del Explorador de amenazas, los mensajes desaparecen de esta lista. La lista también muestra mensajes individuales que se pueden corregir.

- **Registros de acciones:** esta pestaña muestra los mensajes corregidos, incluida la fecha de aprobación, el administrador que aprobó la acción, la acción, el estado y los recuentos.

  El estado puede ser:

  - **Iniciado:** se desencadena la corrección.
  - **En cola:** la corrección está en cola para la mitigación de mensajes de correo electrónico.
  - **En curso:** la mitigación está en curso.
  - **Completado:** mitigación en todos los mensajes de correo electrónico que se pueden corregir completados correctamente o con algunos errores.
  - **Error:** no se han realizado correctamente las correcciones.

  Como solo se pueden actuar mensajes de correo electrónico que se pueden corregir, la limpieza de cada correo electrónico se muestra como correcta o con errores. A partir del total de mensajes de correo electrónico que se pueden corregir, se notifican mitigaciones correctas y con errores.

  - **Correcto:** se ha realizado la acción deseada en los correos electrónicos que se pueden corregir. Por ejemplo: un administrador desea quitar correos electrónicos de los buzones, por lo que el administrador realiza la acción de eliminar los correos electrónicos de forma flexible. Si no se encuentra un correo electrónico que se puede corregir en la carpeta original después de realizar la acción, el estado se mostrará como correcto.

  - **Error:** error en la acción deseada en los mensajes de correo electrónico que se pueden corregir. Por ejemplo: un administrador desea quitar correos electrónicos de los buzones, por lo que el administrador realiza la acción de eliminar los correos electrónicos de forma flexible. Si aún se encuentra un correo electrónico que se puede corregir en el buzón después de realizar la acción, el estado se mostrará como con error.

  Seleccione cualquier elemento del registro de acciones para mostrar los detalles de corrección. Si los detalles dicen "correcto" o "no se encontró en el buzón", ese elemento ya se quitó del buzón. A veces hay un error sistémico durante la corrección. En esos casos, es una buena idea reintentar la corrección.

  En el caso de la corrección de lotes grandes, también puede exportar los mensajes enviados para corrección a través del envío de correo y los mensajes que se han corregido a través de registros de acciones. El límite de exportación aumenta a 100.000 registros.

  La corrección es una herramienta eficaz para mitigar las amenazas y solucionar correos electrónicos sospechosos. Ayuda a mantener una organización segura.
