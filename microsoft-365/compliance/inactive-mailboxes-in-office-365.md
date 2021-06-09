---
title: Información general sobre buzones inactivos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo conservar el contenido del buzón de correo para antiguos empleados convirtiendo el buzón en un buzón inactivo.
ms.openlocfilehash: 6aeb10f1557a991523b60b8e8e85a99fc61f4b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911256"
---
# <a name="overview-of-inactive-mailboxes"></a>Información general sobre buzones inactivos

Es posible que su organización necesite conservar el correo electrónico de los antiguos empleados después de abandonar la organización. Dependiendo de los requisitos de retención de la organización, es posible que deba conservar el contenido del buzón durante unos meses o años después de que finalice el empleo, o quizás deba conservar el contenido del buzón de correo indefinidamente. Independientemente de cuánto tiempo necesites retener el correo electrónico, puedes crear buzones inactivos para conservar el buzón de correo de antiguos empleados.

## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado deja la organización (o se retira de una licencia extendida), puede quitar su Microsoft 365 cuenta. Los datos del buzón del empleado se conservan durante 30 días después de quitar la cuenta. Durante este período, puede recuperar los datos del buzón eliminando la cuenta. Después de 30 días, los datos se quitan permanentemente.

Pero si su organización necesita conservar el contenido del buzón para antiguos empleados, puede convertir el buzón en un buzón inactivo colocando el buzón en retención por juicio o aplicando una directiva de retención de Microsoft 365 al buzón en el Centro de cumplimiento de & y, a continuación, quitando la cuenta Microsoft 365 correspondiente. El contenido de un buzón inactivo se conserva durante la retención por juicio colocada en el buzón o el período de retención de la directiva de retención aplicada antes de eliminar el buzón. Todavía puede recuperar la cuenta de usuario correspondiente durante un período de 30 días. Sin embargo, después de 30 días, el buzón inactivo se conserva en Microsoft 365 hasta que se quita la directiva de retención o retención.

> [!IMPORTANT]
> A medida que seguimos invirtiendo de diferentes maneras para conservar el contenido del buzón, estamos anunciando la retirada de las In-Place en el centro Exchange administración. Esto significa que debe usar las retenciones por juicio y las Microsoft 365 de retención para crear un buzón inactivo. A partir del 1 de julio de 2020 no podrá crear nuevas retenciones In-Place en Exchange Online. Pero aún podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de la retención. Solo podrá eliminar un buzón inactivo quitando la In-Place espera. Los buzones inactivos existentes que están en In-Place conservación se conservarán hasta que se quite la retención. Para obtener más información sobre cuándo In-Place se retirarán las retenciones, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Buzones inactivos y directivas Microsoft 365 de retención

Además de la retención por juicio, el uso de la nueva característica de directiva de retención Microsoft 365 en el centro de cumplimiento de Microsoft 365 es otra forma de hacer que un buzón esté inactivo. Para usar una directiva de retención para crear un buzón inactivo:

- Debe configurarse para conservar el contenido o retenerlo y, a continuación, eliminarlo. Si una directiva de retención está configurada para eliminar solo contenido, un buzón al que se aplica la directiva no se volverá inactivo cuando se elimine la cuenta de usuario.

- Debe aplicarse a Exchange buzones de correo o Skype Empresarial (ya que Skype contenido relacionado con el usuario se almacena en el buzón del usuario).

- Se puede basar en consultas para que conserve solo los elementos que coincidan con una consulta de búsqueda.

Para obtener más información acerca de las directivas de retención, vea [Learn about retention policies and retention labels](retention.md).

Si usa una directiva de retención para crear un buzón inactivo, Microsoft 365 continúa procesando la directiva de retención en el buzón inactivo. Esto significa que si la directiva de retención está configurada para retener y, a continuación, eliminar contenido, los elementos se mueven a la carpeta Elementos recuperables cuando expire la duración de retención y, a continuación, se purgarán del buzón inactivo. Si la directiva de retención no está configurada para elementos eliminados, los elementos que no han sido eliminados permanentemente por el usuario (antes de que el buzón esté inactivo) no se mueven a la carpeta Elementos recuperables y se conservarán indefinidamente después de que el buzón esté inactivo.

Es posible que considere la posibilidad de crear Microsoft 365 directiva de retención específicamente para buzones inactivos. Estas son algunas razones para hacer esto y cosas que hay que tener en cuenta.

- Puede configurar la directiva de retención para conservar el contenido del buzón solo el tiempo que sea necesario para cumplir los requisitos de su organización para los antiguos empleados.

- Es una buena forma de identificar buzones inactivos porque la directiva de retención solo se aplicará a buzones inactivos.

- Puede identificar rápidamente la directiva de retención asignada a los buzones inactivos de la organización. Esto facilita cambiar la configuración de retención (o eliminación) si es necesario. También facilitará la eliminación permanente de un buzón inactivo porque puede quitarlo de la directiva mediante el Centro de seguridad & cumplimiento. De lo contrario, debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo o usar PowerShell del Centro de seguridad & cumplimiento para excluir un buzón inactivo de una directiva de retención de Microsoft 365 organización.

- Si crea una directiva Microsoft 365 de retención específicamente para buzones inactivos, puede agregar un máximo de 1.000 buzones a la directiva. Si es una organización grande, es posible que tenga que crear más de una directiva de retención Microsoft 365 usar para buzones inactivos.

> [!CAUTION]
> Si usa una directiva de retención para hacer inactivo un buzón, no cambie ni quite el nombre principal de usuario (UPN) del buzón antes de eliminar la cuenta de usuario correspondiente. Además, no cambie la dirección SMTP principal (derivada del UPN) ni quite esta dirección de correo electrónico de la lista de direcciones SMTP secundarias asociadas con el buzón antes de hacer que el buzón esté inactivo. Si cambia el UPN o las direcciones de correo electrónico (que se asignaron al buzón en el momento en que se aplicó la directiva de retención) y, a continuación, elimina la cuenta de usuario para que el buzón esté inactivo, no podrá eliminar el buzón inactivo cuando ya no necesite conservarlo. Esto se debe a que no puede quitar el buzón inactivo de la directiva de retención mediante un UPN o una dirección de correo electrónico (para identificar el buzón inactivo) que sea diferente de los que existían cuando la directiva de retención se aplicó inicialmente al buzón. Para obtener más información acerca de cómo eliminar buzones inactivos, vea Eliminar un buzón inactivo [en Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones inactivos y retenciones de casos de exhibición de documentos electrónicos

Si una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & se coloca en un buzón y, a continuación, se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. Sin embargo, no recomendamos usar retenciones de casos de exhibición de documentos electrónicos para hacer que un buzón sea inactivo. Esto se debe a que los casos de exhibición de documentos electrónicos están destinados a casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y se quitarán las retenciones asociadas al caso y se cerrará el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y, a continuación, la retención se libera o el caso de exhibición de documentos electrónicos se cierra (o elimina), el buzón inactivo se eliminará permanentemente. Además, no puede crear una retención de exhibición de documentos electrónicos basada en tiempo. Esto significa que el contenido de un buzón inactivo se conserva para siempre o hasta que se quita la retención y se elimina el buzón inactivo. Por lo tanto, se recomienda usar una retención por juicio o una directiva de retención para buzones inactivos.

Para obtener más información acerca de los casos y las retenciones de exhibición de documentos electrónicos, vea [casos de exhibición de documentos electrónicos](./get-started-core-ediscovery.md).

## <a name="inactive-mailboxes-and-labels"></a>Buzones y etiquetas inactivos

Las etiquetas de retención le ayudan a clasificar los datos de correo electrónico de la organización para su gobierno y a aplicar reglas de retención basadas en esa clasificación. Los usuarios o los administradores pueden aplicar una etiqueta de retención a un elemento de correo electrónico manualmente o automáticamente, y un elemento de correo electrónico solo puede tener asignada una sola etiqueta. Si un único elemento de correo electrónico en el buzón de un usuario tiene asignada una etiqueta (y está configurado para retener o conservar y, a continuación, eliminar el elemento) y se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. De forma similar a las retenciones de casos de exhibición de documentos electrónicos, no se recomienda usar etiquetas de retención para hacer que un buzón de correo se inactive. En su lugar, se recomienda usar una retención por juicio o una directiva de retención. En el caso de las etiquetas de retención, es posible que no se dé cuenta de que se ha aplicado una etiqueta de retención a un elemento de correo electrónico y, a continuación, se convierte accidentalmente en un buzón inactivo al eliminar la cuenta del usuario.

Para obtener más información acerca de las directivas de retención y las etiquetas de retención, vea [Learn about retention policies and retention labels in Office 365](retention.md).

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Buzones inactivos y archivos de expansión automática

Un buzón inactivo configurado con un archivo de expansión automática no se puede recuperar ni restaurar. En situaciones en las que es necesario recuperar datos de un buzón inactivo con un archivo de expansión automática, se recomienda usar la herramienta de búsqueda de contenido para exportar los datos del buzón y luego importarlos a otro buzón. Para obtener instrucciones paso a paso para buscar en un buzón inactivo y exportar los resultados de búsqueda, vea:

- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones inactivos y directivas Exchange de retención de MRM

Si una directiva de retención de Exchange (la característica Administración de registros de mensajería o MRM, en Exchange Online) se aplicó al  buzón cuando se activó, las directivas de eliminación (que son etiquetas de retención configuradas con una acción de retención Eliminar) seguirán procesandose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se moverán a la carpeta Elementos recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.

## <a name="creating-an-inactive-mailbox"></a>Creación de un buzón inactivo

Para que un buzón esté inactivo, se le debe asignar una licencia del Plan 2 de Exchange Online (o una licencia del Plan 1 de Exchange Online con una licencia de complemento de Archivado de Exchange Online) para que se pueda aplicar una retención por juicio o una directiva de retención Microsoft 365 al buzón antes de eliminarla. Después de eliminar la cuenta de usuario, cualquier licencia Exchange Online asociada a la cuenta de usuario estará disponible para asignarla a un nuevo usuario.

En la tabla siguiente se resume el proceso de creación de un buzón inactivo para distintos escenarios de retención. Para obtener más información, vea [Manage inactive mailboxes](create-and-manage-inactive-mailboxes.md).

****

|Para...|Haga esto...|Resultado|
|---|---|---|
|Conservar el contenido del buzón de correo indefinidamente después de que un empleado abandone la organización|Coloque el buzón en retención por juicio o aplique una directiva de retención Microsoft 365 (que está configurada para conservar contenido) al buzón. <br/> No especifique una duración de retención para la retención por juicio o no configure la directiva de retención para eliminar elementos. Como alternativa, puede usar una directiva de retención que conserve los elementos para siempre. <br/> Quite la cuenta de Microsoft 365 usuario.|Todo el contenido del buzón inactivo, incluidos los elementos de la carpeta Elementos recuperables, se conserva indefinidamente.|
|Conservar el contenido del buzón durante un período específico después de que un empleado abandone la organización y, a continuación, eliminarlo|Aplique una directiva Microsoft 365 de retención al buzón. <br/> Configure la directiva de retención para conservar y, a continuación, eliminar elementos cuando expire el período de retención. <br/> Quite la cuenta de Microsoft 365 usuario.|Cuando expira el período de retención de un elemento de buzón de correo, el elemento se mueve a la carpeta Elementos recuperables y, a continuación, se elimina permanentemente (purga) del buzón inactivo cuando expira el período de retención de elementos eliminados (para buzones de correo Exchange). El período de retención de la directiva Microsoft 365 de retención se puede configurar en función de la fecha original en que se recibió o creó un elemento de buzón, o cuando se modificó por última vez.|
|

**NOTA:** Si ya se ha colocado una retención por juicio en un buzón de correo o si ya se aplica una directiva de retención de Microsoft 365 (que está configurada para retener o conservar y, a continuación, eliminar contenido), lo único que tiene que hacer es eliminar la cuenta de usuario correspondiente para crear un buzón inactivo.

## <a name="managing-inactive-mailboxes"></a>Administrar buzones inactivos

Después de hacer inactivo un buzón, puede realizar varias tareas de administración en buzones inactivos.

- **Cambiar la duración de retención de un buzón inactivo.** Después de que un buzón esté inactivo, puede cambiar la duración de retención de la retención por juicio o Microsoft 365 directiva de retención aplicada al buzón inactivo. Para ver los procedimientos paso a paso, vea Cambiar la [duración de retención de un buzón inactivo.](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > No puede aplicar otras directivas de retención a un buzón inactivo. Solo puede cambiar la duración de retención de una directiva de retención existente aplicada al buzón inactivo.

- **Recuperar un buzón inactivo.** Si un antiguo empleado (o un empleado en ausencia) vuelve a su organización o si se contrata a un nuevo empleado para asumir las responsabilidades laborales del antiguo empleado, puede recuperar el contenido del buzón inactivo. Al recuperar un buzón inactivo, el buzón se convierte en un buzón nuevo, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. Para obtener procedimientos paso a paso e información acerca de lo que sucede al recuperar un buzón inactivo, vea [Recover an inactive mailbox](recover-an-inactive-mailbox.md).

  > [!NOTE]
  > Si recupera un buzón inactivo que se asignó *a* una directiva de retención con bloqueo de conservación (denominado directiva de retención bloqueada), el buzón recuperado se asigna a la misma directiva de retención bloqueada. Si recupera un buzón inactivo que se asignó a una directiva de retención sin bloqueo de conservación, el buzón recuperado se quitará de la directiva de retención desbloqueada. Sin embargo, la retención por juicio está habilitada en el buzón recuperado para evitar la eliminación del contenido del buzón en función de las directivas de retención de toda la organización que eliminen contenido con una antigüedad específica.

- **Restaurar un buzón inactivo.** Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. El buzón inactivo todavía se puede buscar con herramientas de exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón y se puede recuperar o eliminar más adelante. Para ver los procedimientos paso a paso, vea [Restore an inactive mailbox](restore-an-inactive-mailbox.md).

- **Eliminar un buzón inactivo.** Cuando ya no necesite conservar el contenido de un buzón inactivo, puede eliminarlo permanentemente quitando todas las retenciones o directivas de retención Microsoft 365 aplicadas al buzón inactivo. Si un buzón se hizo inactivo hace más de 30 días, se marcará para su eliminación permanente después de quitar la retención. Si el buzón se ha inactivo en los últimos 30 días, puede volver a activarlo después de quitar la directiva de retención o retención. Para ver los procedimientos paso a paso, vea [Delete an inactive mailbox](delete-an-inactive-mailbox.md).