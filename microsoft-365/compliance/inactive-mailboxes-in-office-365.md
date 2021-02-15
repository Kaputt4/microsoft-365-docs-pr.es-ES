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
description: Obtenga información sobre cómo conservar el contenido del buzón para antiguos empleados convirtiendo el buzón en un buzón inactivo.
ms.openlocfilehash: f7b81d259fb850c05a1539c37008c04d43030fde
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655717"
---
# <a name="overview-of-inactive-mailboxes"></a>Información general sobre buzones inactivos

Es posible que su organización necesite conservar el correo electrónico de los antiguos empleados después de abandonar la organización. En función de los requisitos de retención de su organización, es posible que deba conservar el contenido del buzón durante unos meses o años después de que finalice el empleo, o puede que deba conservar el contenido del buzón indefinidamente. Independientemente del tiempo que necesite conservar el correo electrónico, puede crear buzones inactivos para conservar el buzón de los antiguos empleados.

## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado abandona su organización (o se va de ausencia ampliada), puede quitar su cuenta de Microsoft 365. Los datos del buzón del empleado se conservan durante 30 días después de quitar la cuenta. Durante este período, aún puede recuperar los datos del buzón eliminando la cuenta. Después de 30 días, los datos se quitan permanentemente.

Pero si su organización necesita conservar el contenido del buzón para los antiguos empleados, puede convertir el buzón en un buzón inactivo colocando el buzón en retención por juicio o aplicando una directiva de retención de Microsoft 365 al buzón en el Centro de seguridad & Cumplimiento y, a continuación, quitando la cuenta de Microsoft 365 correspondiente. El contenido de un buzón inactivo se conserva mientras dure la retención por juicio colocada en el buzón o el período de retención de la directiva de retención aplicada antes de que se elimine el buzón. Aún puede recuperar la cuenta de usuario correspondiente durante un período de 30 días. Sin embargo, después de 30 días, el buzón inactivo se conserva en Microsoft 365 hasta que se quita la retención o la directiva de retención.

> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de In-Place retenciones en el Centro de administración de Exchange. Esto significa que debe usar las retenciones por juicio y las directivas de retención de Microsoft 365 para crear un buzón inactivo. A partir del 1 de julio de 2020 no podrá crear nuevas retenciones de In-Place en Exchange Online. Sin embargo, podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de retención. Solo podrá eliminar un buzón inactivo quitando la retención In-Place correo. Los buzones inactivos existentes que están In-Place conservación local se conservarán hasta que se quite la retención. Para obtener más información acerca de In-Place se retirarán las retenciones, consulte Retirada de herramientas de exhibición de [documentos electrónicos heredadas.](legacy-ediscovery-retirement.md)

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Buzones inactivos y directivas de retención de Microsoft 365

Además de la retención por juicio, el uso de la nueva característica de directiva de retención de Microsoft 365 en el Centro de seguridad & cumplimiento es otra forma de hacer que un buzón esté inactivo. Para usar una directiva de retención para convertir un buzón inactivo:

- Debe configurarse para conservar el contenido o retenerlo y, a continuación, eliminar el contenido. Si una directiva de retención está configurada para eliminar solo contenido, un buzón al que se aplica la directiva no se volverá inactivo cuando se elimine el buzón.

- Debe aplicarse a los buzones de Exchange o a las ubicaciones de Skype Empresarial (porque el contenido relacionado con Skype se almacena en el buzón del usuario).

- Puede basarse en consultas para que solo conserve elementos que coincidan con una consulta de búsqueda.

Para obtener más información acerca de las directivas de retención, vea [Más información sobre las directivas de retención y las etiquetas de retención.](retention.md)

Si usa una directiva de retención para convertir un buzón inactivo, Microsoft 365 sigue procesando la directiva de retención en el buzón inactivo. Esto significa que si la directiva de retención está configurada para retener y eliminar contenido, los elementos se mueven a la carpeta Elementos recuperables cuando expira la duración de retención y, a continuación, se purgan del buzón inactivo. Si la directiva de retención no está configurada para elementos eliminados, los elementos que el usuario no haya eliminado permanentemente (antes de que el buzón se pasara a inactivo) no se trasladarán a la carpeta Elementos recuperables y se conservarán indefinidamente después de que el buzón se vuelva inactivo.

Considere la posibilidad de crear una directiva de retención de Microsoft 365 específicamente para buzones inactivos. Estas son algunas razones para hacerlo y cosas que debe tener en cuenta.

- Puede configurar la directiva de retención para que retenga el contenido del buzón solo el tiempo necesario para satisfacer los requisitos de su organización para los antiguos empleados.

- Es una buena manera de identificar buzones inactivos porque la directiva de retención solo se aplicará a los buzones inactivos.

- Puede identificar rápidamente la directiva de retención que se asigna a los buzones inactivos de su organización. Esto facilita cambiar la configuración de retención (o eliminación) si es necesario. También facilitará la eliminación permanente de un buzón inactivo, ya que puede quitarlo de la directiva mediante el Centro de seguridad & cumplimiento. De lo contrario, debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo o usar PowerShell del Centro de seguridad & Cumplimiento para excluir un buzón inactivo de una directiva de retención de Microsoft 365 en toda la organización.

- Si crea una directiva de retención de Microsoft 365 específicamente para buzones inactivos, puede agregar un máximo de 1.000 buzones a la directiva. Si es una organización grande, es posible que tenga que crear más de una directiva de retención de Microsoft 365 para usarla en los buzones inactivos.

> [!CAUTION]
> Si usa una directiva de retención para convertir un buzón en inactivo, no cambie ni quite el nombre principal de usuario (UPN) del buzón antes de eliminar la cuenta de usuario correspondiente. Además, no cambie la dirección SMTP principal (derivada del UPN) ni quite esta dirección de correo electrónico de la lista de direcciones SMTP secundarias asociadas con el buzón antes de que el buzón esté inactivo. Si cambia el UPN o las direcciones de correo electrónico (que se asignaron al buzón en el momento en que se aplicó la directiva de retención) y, a continuación, elimina la cuenta de usuario para que el buzón esté inactivo, no podrá eliminar el buzón inactivo cuando ya no necesite conservarlo. Esto se debe a que no puede quitar el buzón inactivo de la directiva de retención con un UPN o una dirección de correo electrónico (para identificar el buzón inactivo) que sea diferente de los que existían cuando la directiva de retención se aplicó inicialmente al buzón. Para obtener más información acerca de cómo eliminar buzones inactivos, vea Eliminar un buzón [inactivo en Office 365.](delete-an-inactive-mailbox.md)

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones inactivos y retenciones de casos de exhibición de documentos electrónicos

Si se coloca una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & en un buzón y, a continuación, se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. Sin embargo, no recomendamos usar retenciones de casos de exhibición de documentos electrónicos para hacer que un buzón sea inactivo. Esto se debe a que los casos de exhibición de documentos electrónicos están destinados a casos específicos y limitados por tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y las retenciones asociadas con el caso se quitarán y se cerrará el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada con un caso de exhibición de documentos electrónicos y, a continuación, se libera la retención o el caso de eDiscovery se cierra (o elimina), el buzón inactivo se eliminará permanentemente. Además, no puede crear una retención de exhibición de documentos electrónicos basada en tiempo. Esto significa que el contenido de un buzón inactivo se conserva para siempre o hasta que se quita la retención y se elimina el buzón inactivo. Por lo tanto, se recomienda usar una retención por juicio o una directiva de retención para buzones inactivos.

Para obtener más información acerca de los casos y retenciones de exhibición de documentos electrónicos, vea [casos de exhibición de documentos electrónicos.](ediscovery-cases.md)

## <a name="inactive-mailboxes-and-labels"></a>Buzones y etiquetas inactivos

Las etiquetas de retención le ayudan a clasificar los datos de correo electrónico de su organización para su gobierno y a aplicar reglas de retención basadas en esa clasificación. Los usuarios o los administradores pueden aplicar una etiqueta de retención a un elemento de correo electrónico manualmente o automáticamente, y un elemento de correo electrónico solo puede tener asignada una sola etiqueta. Si un único elemento de correo electrónico del buzón de un usuario tiene una etiqueta asignada (y está configurado para retener o conservar y eliminar el elemento) y se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. Al igual que las retenciones de casos de exhibición de documentos electrónicos, no recomendamos usar etiquetas de retención para que un buzón de correo sea inactivo. En su lugar, se recomienda usar una retención por juicio o una directiva de retención. En el caso de las etiquetas de retención, es posible que no se dé cuenta de que se ha aplicado una etiqueta de retención a un elemento de correo electrónico y, a continuación, se convierte accidentalmente en un buzón inactivo al eliminar la cuenta del usuario.

Para obtener más información acerca de las directivas de retención y las etiquetas de retención, vea Más información sobre las directivas de retención y las etiquetas de [retención en Office 365.](retention.md)

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Buzones inactivos y archivos de expansión automática

Un buzón inactivo que está configurado con un archivo de expansión automática no se puede recuperar ni restaurar. En situaciones en las que es necesario recuperar datos de un buzón inactivo con un archivo de expansión automática, se recomienda usar la herramienta de búsqueda de contenido para exportar los datos del buzón y, a continuación, importarlos a otro buzón. Para obtener instrucciones paso a paso para buscar en un buzón inactivo y exportar los resultados de la búsqueda, consulte:

- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones inactivos y directivas de retención de MRM de Exchange

Si se aplicó una directiva de retención de Exchange (la característica Administración de registros de mensajería o MRM en Exchange  Online) al buzón cuando se activó, las directivas de eliminación (que son etiquetas de retención configuradas con una acción de retención Eliminar) se seguirán procesando en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se moverán a la carpeta Elementos recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.

## <a name="creating-an-inactive-mailbox"></a>Creación de un buzón inactivo

Para que un buzón esté inactivo, debe tener asignada una licencia de Exchange Online Plan 2 (o una licencia de Exchange Online Plan 1 con una licencia de complemento de Archivado de Exchange Online) para que se pueda aplicar una retención por juicio o una directiva de retención de Microsoft 365 al buzón antes de que se elimine. Después de eliminar el buzón, cualquier licencia de Exchange Online asociada a él estará disponible para asignarla a un nuevo usuario.

En la tabla siguiente se resume el proceso de hacer un buzón inactivo para diferentes escenarios de retención. Para obtener más información, vea [Administrar buzones inactivos.](create-and-manage-inactive-mailboxes.md)

****

|Para...|Haga esto...|Resultado|
|---|---|---|
|Conservar el contenido del buzón indefinidamente después de que un empleado abandone la organización|Coloque el buzón en retención por juicio o aplique una directiva de retención de Microsoft 365 (que está configurada para retener contenido) al buzón. <br/> No especifique una duración de retención para la retención por juicio o no configure la directiva de retención para eliminar elementos. Como alternativa, puede usar una directiva de retención que retenga los elementos para siempre. <br/> Quite la cuenta de Microsoft 365 del usuario.|Todo el contenido del buzón inactivo, incluidos los elementos de la carpeta Elementos recuperables, se conserva indefinidamente.|
|Conservar el contenido del buzón durante un período específico después de que un empleado abandone la organización y, a continuación, eliminarlo|Aplicar una directiva de retención de Microsoft 365 al buzón. <br/> Configure la directiva de retención para retener y, a continuación, eliminar elementos cuando expire el período de retención. <br/> Quite la cuenta de Microsoft 365 del usuario.|Cuando expira el período de retención de un elemento de buzón de correo, el elemento se mueve a la carpeta Elementos recuperables y, a continuación, se elimina permanentemente (purga) del buzón inactivo cuando expira el período de retención de elementos eliminados (para buzones de Exchange). El período de retención de la directiva de retención de Microsoft 365 se puede configurar en función de la fecha original en que se recibió o creó un elemento de buzón, o cuando se modificó por última vez.|
|

**NOTA:** Si ya se ha colocado una retención por juicio en un buzón de correo, o si ya se ha aplicado una directiva de retención de Microsoft 365 (que está configurada para retener o retener y, a continuación, eliminar contenido), lo único que tiene que hacer es eliminar la cuenta de usuario correspondiente para crear un buzón inactivo.

## <a name="managing-inactive-mailboxes"></a>Administrar buzones inactivos

Después de convertir un buzón en inactivo, puede realizar varias tareas de administración en buzones inactivos.

- **Cambiar la duración de retención de un buzón inactivo.** Después de que un buzón esté inactivo, puede cambiar la duración de retención de la retención por juicio o la directiva de retención de Microsoft 365 aplicada al buzón inactivo. Para ver los procedimientos paso a paso, consulte Cambiar la duración [de retención de un buzón inactivo.](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > No puede aplicar otras directivas de retención a un buzón inactivo. Solo puede cambiar la duración de retención de una directiva de retención existente aplicada al buzón inactivo.

- **Recuperar un buzón inactivo.** Si un antiguo empleado (o un empleado en ausencia) vuelve a la organización o si se contrata a un nuevo empleado para que asista a las responsabilidades del antiguo empleado, puede recuperar el contenido del buzón inactivo. Cuando recupera un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. Para obtener procedimientos paso a paso e información sobre lo que sucede al recuperar un buzón inactivo, consulte [Recuperar un buzón inactivo.](recover-an-inactive-mailbox.md)

  > [!NOTE]
  > Si recupera un buzón inactivo que se asignó a una directiva de retención con bloqueo de conservación (denominada *directiva* de retención bloqueada), el buzón recuperado se asigna a la misma directiva de retención bloqueada. Si recupera un buzón inactivo que se asignó a una directiva de retención sin bloqueo de conservación, el buzón recuperado se quitará de la directiva de retención desbloqueada. Sin embargo, la retención por juicio está habilitada en el buzón recuperado para evitar la eliminación del contenido del buzón en función de las directivas de retención de toda la organización que eliminen contenido con una antigüedad específica.

- **Restaurar un buzón inactivo.** Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. El buzón inactivo aún se puede buscar con herramientas de exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón y se puede recuperar o eliminar más adelante. Para ver los procedimientos paso a paso, consulte [Restaurar un buzón inactivo.](restore-an-inactive-mailbox.md)

- **Eliminar un buzón inactivo.** Cuando ya no necesite conservar el contenido de un buzón inactivo, puede eliminarlo permanentemente quitando todas las retenciones o directivas de retención de Microsoft 365 aplicadas al buzón inactivo. Si un buzón se activó hace más de 30 días, se marcará para su eliminación permanente después de quitar la retención. Si el buzón se ha vuelto inactivo en los últimos 30 días, puede volver a activarlo después de quitar la retención o la directiva de retención. Para ver los procedimientos paso a paso, consulte [Eliminar un buzón inactivo.](delete-an-inactive-mailbox.md)
