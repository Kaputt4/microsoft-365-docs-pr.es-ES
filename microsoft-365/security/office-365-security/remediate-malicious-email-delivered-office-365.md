---
title: Corregir el correo electrónico malintencionado que se entregó en Office 365
author: msfttracyp
ms.author: tracyp
manager: ''
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
ms.openlocfilehash: 6c1a07c6de55022797f284eb471d8ad054cd325e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101705"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Corregir el correo electrónico malintencionado que se entregó en Office 365

La corrección supone realizar una acción conformada contra una amenaza. Los mensajes malintencionados enviados a la organización pueden ser limpiados por el sistema, a través de ZAP (purga automática de cero horas) o por los equipos de seguridad a través de acciones de corrección como mover a la bandeja de entrada, mover a correo no deseado, mover a la carpeta elementos eliminados, eliminar temporalmente o eliminar temporalmente. La protección contra amenazas avanzada de Office (ATP de Office) P2/E5 ofrece a los equipos de operaciones de seguridad Microsoft la capacidad de mediar amenazas en los correos electrónicos y la colaboración a través de la búsqueda y las investigaciones automáticas manuales.

> [!NOTE]
> Para que los equipos de seguridad corrijan los correos electrónicos, deben tener asignado el rol de búsqueda y depuración. La asignación de roles se realiza a través de permisos en el centro de seguridad y cumplimiento. 

## <a name="what-you-need-to-know-before-you-begin"></a>Lo que debe saber antes de empezar

Para llevar a cabo determinadas acciones, como ver los encabezados de mensajes o descargar el contenido de los mensajes de correo electrónico, debe tener un nuevo rol denominado *vista previa* agregado a otro grupo de funciones apropiado. La siguiente tabla clarifica los permisos y las funciones necesarias.

|Actividad  |Grupo de funciones |¿Se requiere un rol de vista previa?  |
|---------|---------|---------|
|Usar el explorador de amenazas (y detecciones en tiempo real) para analizar las amenazas     |Administrador global <br> Administrador de seguridad <br> Lector de seguridad     | No   |
|Usar el explorador de amenazas (y detecciones en tiempo real) para ver los encabezados de los mensajes de correo electrónico, así como para obtener una vista previa y descargar los mensajes de correo electrónico en cuarentena    |Administrador global <br> Administrador de seguridad <br>Lector de seguridad   |       No  |
|Usar el explorador de amenazas para ver los encabezados y descargar los mensajes de correo electrónico que se entregan a los buzones     |Administrador global <br>Administrador de seguridad <br> Lector de seguridad <br> Preview   |   Sí      |

> [!NOTE]
> La *vista previa* es un rol y no un grupo de roles; el rol de vista previa debe agregarse a un grupo de roles existente para Office 365. La función de administrador global se asigna al centro de administración de Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) y el administrador de seguridad y los roles de lector de seguridad se asignan en el centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ). Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Los administradores pueden llevar a cabo las acciones necesarias en los correos electrónicos, pero para que se apruebe la acción, deben tener asignado el rol "buscar y purgar" a través de los permisos del centro de seguridad y cumplimiento >.

## <a name="manual-and-automated-remediation"></a>Corrección manual y automatizada

La búsqueda **manual** se produce cuando los equipos de seguridad identifican las amenazas manualmente, usando las capacidades de búsqueda y filtrado del explorador de amenazas. La corrección manual en los correos electrónicos se puede desencadenar a través de cualquier vista de correo electrónico (malware, phish o todo el correo electrónico) después de encontrar un conjunto de mensajes de correo electrónico que deben corregirse.

[La búsqueda manual en el explorador de amenazas de Office 365 por fecha.](../../media/tp-RemediationArticle1.png)

La selección de los correos electrónicos puede realizarse de varias formas mediante el explorador de amenazas: 

1. Elegir manualmente los mensajes de correo electrónico: Esto significa que los equipos de operaciones de seguridad pueden usar filtros en las vistas correspondientes y seleccionar unos pocos correos electrónicos del explorador de amenazas que necesitan ser corregidos. El límite superior para seleccionar correos electrónicos es 100 (100). Los equipos de operaciones de seguridad no pueden elegir más de cientos de mensajes de correo electrónico de forma manual. 

2. Selección de consulta: operaciones de seguridad Teams puede seleccionar una consulta completa mediante el botón "seleccionar todo" de la parte superior. La misma consulta se muestra también en la información de envío de correo del centro de actividades. 

3. Selección de consulta con exclusión: en ocasiones, es posible que los equipos de operaciones de seguridad decidan corregir los mensajes de correo electrónico seleccionando una consulta completa y excluyendo algunos mensajes de correo electrónico de la consulta de forma manual. Para ello, un administrador puede usar la casilla "seleccionar todo" y desplazarse hacia abajo para excluir algunos mensajes de correo electrónico de forma manual. El número máximo de mensajes que puede contener la consulta es 1000 (1.000) y el número máximo de exclusiones es 100 (100), en este caso.

Una vez que se seleccionan los correos electrónicos en el explorador de amenazas, la creación de la corrección puede comenzar realizando una acción directa o poniendo en cola los correos electrónicos para una acción: 

1. Aprobación directa: cuando acciones como "mover a la bandeja de entrada", "mover a correo no deseado", "mover a elementos eliminados", "eliminación temporal", "eliminación temporal" los selecciona el personal de seguridad con los permisos adecuados y se siguen los pasos siguientes, el proceso de corrección comienza a ejecutar una acción seleccionada. Un control flotante temporal muestra la corrección en curso. 

2. Aprobación en dos pasos: la acción "Agregar a corrección" puede llevarla a cabo un administrador que no tenga los permisos adecuados o que tenga que esperar más para ejecutar la acción. En este caso, la acción de corrección no se ejecuta directamente. En su lugar, los correos electrónicos se agregan a un contenedor de corrección que debe aprobarse para ejecutarse. Hasta que se apruebe la corrección, el correo electrónico no será corregido. Una vez que se aprueba la corrección, se realizarán acciones en el correo electrónico. 

Las acciones de **investigación y respuesta automatizadas (Air)** las desencadenan las alertas o los equipos de operaciones de seguridad desde dentro del explorador de amenazas. Pueden incluir algunas reparaciones recomendadas que deben ser aprobadas por los equipos de operaciones de seguridad. Estas acciones de corrección se incluyen en la ficha acción dentro de la investigación automatizada.  

[El correo con malware es zapped página que muestra la hora de la ejecución de la Zap.](../../media/tp-RemediationArticle3.png)

Todas las correcciones (ya sean de aprobación directa o de dos pasos) creadas mediante el explorador de amenazas y las acciones aprobadas que provienen de investigaciones automatizadas se muestran en el centro de actividades, al que se puede obtener acceso a través del panel de navegación izquierdo, en * Review * > **centro de actividades**.

[El centro de actividades con una lista de amenazas por fecha y gravedad.](../../media/tp-RemediationArticle4.png)

El centro de actividades muestra todas las acciones de corrección de los últimos 30 días. Las acciones realizadas en el explorador se muestran con el mismo nombre proporcionado por los equipos de operaciones de seguridad cuando se creó la corrección. Las acciones realizadas a través de investigaciones automatizadas se exponen con los títulos que comienzan con la alerta relacionada que desencadenó la investigación, por ejemplo, "el clúster de correo electrónico Zap...".

Cada elemento de corrección se puede abrir para ver detalles sobre él. Cuando se abre un elemento de corrección, se muestran los detalles de corrección básicos, el nombre de corrección, la fecha de creación, la descripción, la gravedad de la amenaza y el estado. También muestra dos pestañas. 

1. **Ficha envío de correo**: es el número de correos electrónicos enviados a través del explorador de amenazas o investigaciones automatizadas que se van a corregir. Estos mensajes de correo electrónico pueden ser: 

[El centro de actividades con acciones que se tienen que actuar y no son posibles.](../../media/tp-RemediationArticle5.png)

**Accionable**: los correos electrónicos en las siguientes ubicaciones de buzones de la nube pueden actuar y moverse, es decir, cualquier correo electrónico de la categoría remedible se puede mover de una ubicación a otra: 
  - Bandeja de entrada 
  - Desea  
  - Carpeta eliminada 
  - Carpeta eliminada temporalmente 

[!NOTE]
> Actualmente, solo un usuario final con acceso al buzón puede recuperar elementos de una carpeta de eliminación temporal.

**No se puede accionar**: los correos electrónicos en las siguientes ubicaciones no se pueden realizar o mover como parte de las acciones de correo electrónico, es decir, los correos electrónicos en categorías no remedibles no se pueden mover ni en la categoría no remedible ni en remedibles. Las ubicaciones no remedibles son: 

  - Quarantine 
  - Carpeta eliminada permanentemente
  - Local o externo 
  - Error/pérdida los mensajes sospechosos enviados se clasifican como remedibles o no remedibles. En la mayoría de los casos, los mensajes remedibles y no remedibles deben agregar hasta el total de mensajes enviados. Sin embargo, puede haber casos raros en los que los mensajes enviados pueden no sumarse a la suma de elementos remedibles y no remedibles, y pueden ser superiores o inferiores al número total de mensajes enviados. Esto puede ocurrir debido a retrasos del sistema, tiempos de espera o mensajes caducados. Los mensajes expiran en función del período de retención del explorador para su organización. 

A menos que remedie mensajes antiguos después del período de retención del explorador de la organización, si ve incoherencias en los números, es aconsejable volver a intentar corregir los elementos. Para los retrasos del sistema, las actualizaciones de la corrección suelen actualizarse en unas pocas horas. 

Si el período de retención de la organización para el correo electrónico en el explorador es de 30 días y va a corregir los correos electrónicos que van de 29-30 días atrás, es posible que los recuentos de envíos de correo no siempre se agreguen porque los correos electrónicos podrían haber empezado a salir del período de retención. 

Si las correcciones se bloquean en un estado "en curso" durante un tiempo, es probable que se deba a retrasos en el sistema. La corrección puede tardar hasta unas pocas horas en corregirse. Puede haber una variación observada en el envío de correo se recuento porque algunos de los correos electrónicos no formaban parte de la consulta al iniciar la corrección, debido a retrasos en el sistema. Es una buena idea volver a intentar la corrección en estos casos.  

Para obtener los mejores resultados, la corrección debe realizarse en lotes más pequeños de alrededor de 50 KB o menos de correo electrónico.  

De todos los correos electrónicos en el envío de correo, los correos electrónicos remedibles son los únicos que se actuarán durante la corrección. El sistema de correo electrónico Office 365 no puede corregir los correos electrónicos no remedibles, ya que no se almacenan en los buzones de la nube. 

Para los mensajes de correo electrónico que se encuentran en cuarentena, los administradores pueden ponerse en cuarentena para realizar acciones en esos correos electrónicos si es necesario, pero los mensajes de correo electrónico expirarán a partir de cuarentena si no se purgan manualmente. Los mensajes de correo electrónico en cuarentena debido a contenido malintencionado no son accesibles para los usuarios finales, por lo que el personal de seguridad no tiene que realizar ninguna acción específica para deshacerse de la amenaza en cuarentena. Si los correos electrónicos son locales o externos, se puede contactar con el usuario final para dirigir el correo electrónico sospechoso o usar herramientas de seguridad/servidor de correo electrónico independientes para la eliminación. Estos mensajes de correo electrónico se pueden identificar mediante la aplicación de ubicación de entrega = local o filtro externo en el explorador de amenazas. Para el correo electrónico fallido o perdido, o el correo electrónico no accesible para el usuario final, no debe haber un mensaje de correo electrónico que se pueda mitigar, ya que no llegan al buzón. 

Este es el modo en que se muestra un envío en el centro de actividades. Una corrección puede contener varios envíos. Si se aprueban varias acciones mediante una investigación automatizada, cada acción de correo electrónico o de clúster de correo electrónico se muestra en la misma corrección que un envío diferente.

[Panel flotante de clúster de correo electrónico ZAP.](../../media/tp-RemediationArticle6.png)

Al hacer clic en un elemento de envío de correo, se mostrarán los detalles de dicha corrección, como la consulta (cuando se desencadena la corrección mediante investigaciones automatizadas o el explorador de amenazas mediante la selección de una consulta), la hora de inicio y la hora de finalización de la corrección. También muestra una lista de los mensajes que se enviaron para su corrección. A medida que los mensajes salgan del período de retención del explorador, los mensajes desaparecerán de esta lista. Esta lista también muestra mensajes individuales de la lista que son remedibles.

2. **Ficha registros de acciones**: esta pestaña muestra el resultado de los mensajes corregidos, incluidos los detalles como fecha aprobada, aprobador (administrador que aprobó la acción), acción, estado y recuentos.  

Status es el estado global de la corrección. El estado puede ser: 

  - Se **inició**: cuando se desencadena una corrección. 
  - **En cola**: cuando la corrección se pone en cola para mitigar los mensajes de correo electrónico. 
  - **En curso**: cuando la mitigación está en curso. 
  - **Completado**: cuando la mitigación de todos los correos electrónicos remedibles se realiza correctamente o con algunos errores. 
  - **Error**: cuando ninguna corrección se ha realizado correctamente. 

Como solo se puede actuar sobre los correos electrónicos remedibles, la limpieza de cada mensaje se considera como correcta o con errores. Desde el total de mensajes de correo electrónico remedibles, exponemos las mitigaciones correctas y con error. 

  - **Correcto**: cuando se realiza la acción deseada en los correos electrónicos remedibles y coincide con la intención del administrador. Por ejemplo: un administrador desea quitar los correos electrónicos de los buzones de correo, de modo que lleve a cabo la acción de eliminar temporalmente los correos electrónicos. Si no se encuentra un correo electrónico remedible en la carpeta original después de que se haya realizado la acción, el estado mostrará como correcto.  

  - **Error**: cuando se produce un error en la acción deseada en los correos electrónicos remedibles. Por ejemplo: un administrador desea quitar los correos electrónicos de los buzones de correo, por lo que realiza la acción de eliminar los correos electrónicos de forma temporal. Si todavía se encuentra un mensaje de correo electrónico remedible en el buzón, el estado se mostrará como erróneo. 

Al hacer clic en un elemento en el registro de acciones, se muestran detalles de corrección. Para los elementos correctos, si los detalles indican, se han realizado correctamente o no se encuentran en el buzón, significa que el elemento ya se ha quitado del buzón. A veces se producen errores debidos a un error sistémico durante la corrección y, en esos casos, es una buena idea volver a intentar la corrección.  

La corrección es una herramienta eficaz para mitigar las amenazas y hacer frente a los correos electrónicos sospechosos. Ayuda a mantener la seguridad y seguridad de una organización.  

## <a name="more-info"></a>Más información

Consulte [investigar correo electrónico malintencionado](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

