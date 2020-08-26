---
title: Corregir el correo electrónico malintencionado que se entregó en Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Corrección de amenazas
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 44f20b29dcc88b1d991f9e93929aacc0e8aece32
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903888"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Corregir el correo electrónico malintencionado entregado en Office 365

La corrección supone realizar una acción conformada contra una amenaza. El sistema puede limpiar el correo electrónico malintencionado enviado a su organización, a través de la depuración automática de cero horas (ZAP) o por parte de los equipos de seguridad mediante acciones de corrección como *mover a la bandeja de entrada*, *desplazarse a correo no deseado*, *mover a elementos eliminados*, *eliminar temporalmente*o *eliminar permanentemente*. La protección contra amenazas avanzada de Office (ATP de Office) P2/E5 permite a los equipos de seguridad corregir amenazas en el correo electrónico y la funcionalidad de colaboración mediante la investigación manual y automatizada.

> [!NOTE]
> Para corregir el correo electrónico malintencionado, los equipos de seguridad necesitan la función de *búsqueda y depuración* que tienen asignada. La asignación de roles se realiza a través de permisos en el centro de seguridad y cumplimiento.

## <a name="what-you-need-to-know-before-you-begin"></a>Lo que debe saber antes de empezar

Para realizar acciones como ver encabezados de mensajes o descargar contenido de correo electrónico, debe tener un nuevo rol denominado *vista previa* agregada a otro grupo de roles adecuado. En la siguiente tabla se muestran los roles y permisos necesarios.

****

|Actividad|Grupo de funciones|¿Se requiere un rol de *vista previa* ?|
|---|---|---|
|Usar el explorador de amenazas (y detecciones en tiempo real) para analizar las amenazas |Administrador global <br> Administrador de seguridad <br> Lector de seguridad|No|
|Usar el explorador de amenazas (y la detección en tiempo real) para ver los encabezados de los mensajes de correo electrónico y obtener una vista previa y descargar los mensajes de correo electrónico en cuarentena|Administrador global <br> Administrador de seguridad <br>Lector de seguridad|No|
|Usar el explorador de amenazas para ver los encabezados y descargar los mensajes de correo electrónico que se entregan a los buzones|Administrador global <br>Administrador de seguridad <br> Lector de seguridad <br> Preview|Sí|


> [!NOTE]
> La vista previa es un *rol*, no un *grupo de roles*. El rol de vista previa debe agregarse a un grupo de roles existente para Office 365. El *rol de administrador global* se asigna en el [centro de administración de Microsoft 365](https://admin.microsoft.com). Los roles de administrador de seguridad y lector de seguridad se asignan en los [centros de seguridad y cumplimiento](https://protection.office.com). Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Security and Compliance Centers](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Los administradores pueden realizar las acciones necesarias en los mensajes de correo electrónico, pero para que estas acciones sean aprobadas, deben tener asignada la función de *búsqueda y depuración* a través de los permisos del **centro de seguridad y cumplimiento**  >  **Permissions**.

## <a name="manual-and-automated-remediation"></a>Corrección manual y automatizada

La búsqueda *manual* se produce cuando los equipos de seguridad identifican las amenazas manualmente mediante las funciones de búsqueda y filtrado del explorador de amenazas. La corrección manual de correo electrónico se puede desencadenar a través de cualquier vista de correo electrónico (*malware*, *phish*o *todo el correo electrónico*) después de identificar un conjunto de correos electrónicos que deben corregirse.

![La búsqueda manual en el explorador de amenazas de Office 365 por fecha.](../../media/tp-RemediationArticle1.png)

Los equipos de seguridad pueden usar el explorador de amenazas para seleccionar mensajes de correo electrónico de varias formas:

- Elija correos electrónicos a mano: usar filtros en varias vistas. Seleccione hasta 100 correos electrónicos para corregir la suscripción.

- Selección de consulta: Seleccione una consulta completa mediante el botón Top **Select All** . La misma consulta también se muestra en los detalles del envío de correo del centro de actividades.

- Selección de consulta con exclusión: a veces, es posible que los equipos de operaciones de seguridad deseen corregir los mensajes de correo electrónico seleccionando una consulta completa y excluyendo determinados mensajes de la consulta de forma manual. Para ello, un administrador puede usar la casilla **seleccionar todo** y desplazarse hacia abajo para excluir mensajes de correo electrónico de forma manual. La consulta puede contener un máximo de 1.000 mensajes de correo electrónico. El número máximo de exclusiones es de 100.

Una vez que se seleccionan los correos electrónicos a través del explorador de amenazas, puede iniciar la corrección llevando a cabo la acción directa o poniendo en cola los correos electrónicos para una acción:

- Aprobación directa: cuando acciones como *mover a la bandeja de entrada*, *desplazarse a correo no deseado*, *mover a elementos eliminados*, *eliminación temporal*o *eliminación de hardware* están seleccionados por el personal de seguridad que tiene los permisos adecuados y se siguen los pasos siguientes en la corrección, el proceso de corrección comienza a ejecutar la acción seleccionada. Un control flotante temporal muestra la corrección en curso.

- Aprobación en dos pasos: la acción "Agregar a corrección" puede ser realizada por los administradores que no tienen los permisos adecuados o que necesitan esperar para ejecutar la acción. En este caso, los correos electrónicos de destino se agregan a un contenedor de corrección. La aprobación es necesaria antes de que se ejecute la corrección.

La **investigación automatizada y** las acciones de respuesta las desencadenan las alertas o los equipos de operaciones de seguridad desde el explorador de amenazas. Estos pueden incluir acciones de corrección recomendadas que deben ser aprobadas por un equipo de operaciones de seguridad. Estas acciones se incluyen en la pestaña **acción** de la investigación automatizada.

![Correo con malware en la página "zapped" que muestra la hora de la ejecución de la Zap.](../../media/tp-RemediationArticle3.png)

En el centro de actividades se muestran todas las correcciones (tanto la aprobación directa como la aprobación en dos pasos) que se crearon en el explorador de amenazas y las acciones aprobadas que provienen de las investigaciones automatizadas. Obtenga acceso a estos mediante el panel de navegación izquierdo en **revisión**del  >  **centro de actividades**.

![El centro de actividades con una lista de amenazas por fecha y gravedad.](../../media/tp-RemediationArticle4.png)

El centro de actividades muestra todas las acciones de corrección de los últimos 30 días. Las acciones realizadas a través del explorador de amenazas se muestran por el nombre que el equipo de operaciones de seguridad proporcionó cuando se creó la corrección. Las acciones realizadas a través de investigaciones automatizadas tienen títulos que comienzan con la alerta relacionada que desencadenó la investigación, como "el clúster de correo electrónico Zap... ."

Abra cualquier elemento de corrección para ver los detalles del mismo, como su nombre, la fecha de creación, la descripción, la gravedad de la amenaza y el estado. También se muestran las dos pestañas siguientes.

- Ficha **envío de correo** : muestra el número de correos electrónicos enviados a través del explorador de amenazas o investigaciones automatizadas que se van a corregir. Estos mensajes de correo electrónico pueden ser accionables o no accionables.<br/><br/>![El centro de actividades con acciones que se tienen que actuar y no son posibles.](../../media/tp-RemediationArticle5.png)

   - **Accionable**: los correos electrónicos en las siguientes ubicaciones de buzones en la nube se pueden actuar y mover:

     - Bandeja de entrada
     - Desea
     - Carpeta eliminada
     - Carpeta eliminada temporalmente

     > [!NOTE]
     > Actualmente, solo un usuario con acceso al buzón puede recuperar elementos de una carpeta eliminada temporalmente.

   - **No se puede accionar**: los correos electrónicos en las siguientes ubicaciones no se pueden actuar o mover en acciones de corrección:

     - Quarantine
     - Carpeta eliminada permanentemente
     - Local/externo
     - Error/interrumpido

   Los mensajes sospechosos se clasifican como remedibles o no corregibles. En la mayoría de los casos, los mensajes remedibles y no corregibles combinados se combinan todos los mensajes enviados. Pero, en algunos casos excepcionales, es posible que esto no sea verdad. Esto puede ocurrir por los retrasos del sistema, los tiempos de espera o los mensajes expirados. Los mensajes expiran en función del período de retención del explorador de amenazas de la organización.

   A menos que esté corrigiendo mensajes antiguos después del período de retención del explorador de amenazas de la organización, es aconsejable reintentar la corrección de elementos si ve incoherencias de número. Para los retrasos del sistema, las actualizaciones de la corrección suelen actualizarse en unas pocas horas.

   Si el período de retención de la organización para el correo electrónico en el explorador de amenazas es de 30 días y está corrigiendo los correos electrónicos que van hacia atrás 29-30 días, los recuentos de envíos de correo no siempre se agregan. Es posible que los correos electrónicos ya hayan empezado a salir del período de retención.

   Si las correcciones se detienen en el estado "en curso" durante un tiempo, es probable que se deba a retrasos en el sistema. La corrección puede tardar hasta unas pocas horas en corregirse. Es posible que vea variaciones en los recuentos de envío de correo, ya que es posible que algunos de los correos electrónicos no se hayan incluido en la consulta en el inicio de la corrección debido a retrasos en el sistema. Es una buena idea volver a intentar la corrección en estos casos.

  >[!Note]
  >Para obtener los mejores resultados, la corrección debe realizarse en lotes de 50.000 o menos.

   Solo se actúa sobre los correos electrónicos remedibles durante la corrección. El sistema de correo electrónico de Office 365 no puede corregir los correos electrónicos no corregidos, ya que no se almacenan en los buzones de la nube.

   Si es necesario, los administradores pueden realizar acciones en los correos electrónicos en cuarentena, pero esos mensajes de correo electrónico expirarán en cuarentena si no se purgan manualmente. Los correos electrónicos en cuarentena debido a contenido malintencionado no son accesibles para los usuarios, por lo que el personal de seguridad no tiene que realizar ninguna acción para deshacerse de las amenazas en cuarentena. Si los mensajes de correo electrónico son locales o externos, se puede contactar con el usuario para dirigir el correo electrónico sospechoso. O los administradores pueden usar distintas herramientas de servidor de correo electrónico o de seguridad para la eliminación. Estos mensajes de correo electrónico se pueden identificar aplicando el filtro externo *de ubicación de entrega = local* en el explorador de amenazas. Para el correo electrónico que ha fallado o perdido, o el correo electrónico no es accesible para los usuarios, no habrá ningún correo electrónico que se pueda mitigar, ya que estos correos no llegan al buzón.

   En la siguiente imagen se muestra el aspecto de un envío en el centro de actividades. Una corrección puede contener varios envíos. Si se aprueban varias acciones mediante una investigación automatizada, cada acción de correo electrónico o de clúster de correo electrónico aparece en la misma corrección que un envío diferente.

   ![Panel flotante de clúster de correo electrónico ZAP.](../../media/tp-RemediationArticle6.png)

   Seleccione un elemento de envío de correo para mostrar los detalles de la corrección, como la consulta (cuando se desencadena la corrección mediante investigaciones automatizadas o el explorador de amenazas mediante la selección de una consulta) y las horas de inicio y finalización de la corrección. También muestra una lista de los mensajes que se enviaron para su corrección. A medida que los mensajes salen del período de retención del explorador de amenazas, los mensajes desaparecen de esta lista. La lista también muestra mensajes individuales que son remedibles.

- **Registros de acciones**: esta pestaña muestra los mensajes corregidos, incluida la fecha de aprobación, el administrador que aprobó la acción, la acción, el estado y los recuentos.

   El estado puede ser:

     - **Iniciado**: se desencadena la corrección.
     - **En cola**: la corrección se pone en cola para mitigar los mensajes de correo electrónico.
     - **En curso**: la mitigación está en curso.
     - **Completado**: mitigación de todos los correos electrónicos remedibles completados correctamente o con errores.
     - **Error**: no se realizó correctamente ninguna corrección.

   Como solo se puede actuar en los correos electrónicos remedibles, la limpieza de cada mensaje se muestra como correcta o con error. Se informa del total de los correos electrónicos remedibles, las mitigaciones correctas y con errores.

   - **Correcto**: se ha realizado la acción deseada en los correos electrónicos remedibles. Por ejemplo: un administrador desea quitar los correos electrónicos de los buzones de correo, por lo que el administrador realiza la acción de eliminar los correos electrónicos de forma temporal. Si no se encuentra un correo electrónico remedible en la carpeta original después de que se haya realizado la acción, el estado mostrará como correcto.

   - **Error**: no se pudo realizar la acción deseada en los correos electrónicos remedibles. Por ejemplo: un administrador desea quitar los correos electrónicos de los buzones de correo, por lo que el administrador realiza la acción de eliminar los correos electrónicos de forma temporal. Si todavía se encuentra un correo electrónico remedible en el buzón de correo después de que se haya realizado la acción, el estado se mostrará como erróneo.

   Seleccione cualquier elemento en el registro de acciones para mostrar los detalles de corrección. Si los detalles indican "correcto" o "no se encuentra en el buzón", ese elemento ya se ha quitado del buzón de correo. A veces hay un error sistémico durante la corrección. En esos casos, es una buena idea volver a intentar la corrección.

 La corrección es una herramienta eficaz para mitigar las amenazas y dirigir los correos electrónicos sospechosos. Ayuda a mantener segura una organización.

