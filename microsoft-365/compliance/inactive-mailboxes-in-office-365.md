---
title: Más información sobre los buzones inactivos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo conservar el contenido del buzón de correo de los empleados anteriores convirtiendo el buzón en un buzón inactivo.
ms.openlocfilehash: 981675f64015e0320805e2be8e955cbd6d98769a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627225"
---
# <a name="learn-about-inactive-mailboxes"></a>Más información sobre los buzones inactivos

Es posible que la organización tenga que conservar el correo electrónico de los empleados anteriores después de abandonar la organización. En función de los requisitos de retención de su organización, es posible que tenga que conservar el contenido del buzón durante unos meses o años después de que finalice el empleo, o puede que tenga que conservar el contenido del buzón indefinidamente. Independientemente de cuánto tiempo necesites retener el correo electrónico, puedes crear buzones inactivos para conservar el buzón de correo de antiguos empleados.

## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado deja la organización (o se queda sin permiso), puede quitar su cuenta de Microsoft 365. Los datos del buzón del empleado se conservan durante 30 días después de quitar la cuenta. Durante este período, puede recuperar los datos del buzón mediante la eliminación de la cuenta. Después de 30 días, los datos se quitan permanentemente.

Pero si se aplica una suspensión al buzón antes de eliminar la cuenta de Microsoft 365, el buzón se convertirá en un buzón inactivo. Las secciones siguientes contienen información sobre las retenciones que se pueden aplicar con retención de Microsoft 365 y retenciones de exhibición de documentos electrónicos.

Los buzones inactivos son útiles cuando su organización necesita conservar el contenido del buzón de correo de los empleados anteriores por motivos normativos u otros motivos. Aunque cualquier tipo de retención que aparezca en este documento obligará a que un buzón se inactiva cuando se elimine un objeto de usuario, se recomienda aplicar una directiva de retención o etiquetas de retención de Microsoft 365, [confirmar que se aplica la suspensión](#confirming-a-hold-is-applied-to-a-mailbox) y, a continuación, quitar la cuenta de Microsoft 365 correspondiente. En ese momento, el contenido del buzón inactivo se conserva durante el período de retención especificado antes de eliminar la cuenta de usuario. Todavía puede recuperar la cuenta de usuario correspondiente durante un período de 30 días, pero después de 30 días, el buzón se conserva en Microsoft 365 como buzón inactivo hasta que se quiten la directiva de retención o las etiquetas de retención.

> [!IMPORTANT]
> Como se mencionó anteriormente, se recomienda usar la retención de Microsoft 365 para crear un buzón inactivo:
> - In-Place se han retirado las retenciones en el Centro de administración de Exchange. A partir del 1 de julio de 2020, no se pudieron crear nuevas suspensiones de In-Place en Exchange Online. A partir del 1 de octubre de 2020, la duración de la suspensión de las retenciones en contexto ya no se podía cambiar. Cualquier buzón inactivo que tenga aplicada una suspensión In-Place solo se puede eliminar quitando la In-Place Suspensión. Los buzones inactivos existentes que están en In-Place suspensión se seguirán conservando hasta que se quite la suspensión. Para obtener más información sobre la retirada de In-Place holds, consulte [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md).
> 
> - [La suspensión por juicio](create-a-litigation-hold.md) sigue siendo compatible como método alternativo para conservar el contenido de un buzón y convertirlo en inactivo después de eliminar una cuenta de usuario. Sin embargo, como tecnología anterior, se recomienda usar la retención de Microsoft 365 en su lugar.

Cuando hay varias retenciones en el mismo contenido, se [aplica el principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence) y el contenido se conserva durante el período más largo.

### <a name="confirming-a-hold-is-applied-to-a-mailbox"></a>Confirmación de que se aplica una suspensión a un buzón

Si aplica una directiva de retención de Microsoft 365, etiquetas de retención, suspensión de exhibición de documentos electrónicos, suspensión por juicio o si tiene una In-Place de suspensión existente, puede confirmar que la suspensión se aplica correctamente al buzón mediante PowerShell. Si ha configurado recientemente la suspensión, es posible que tenga que esperar hasta que se aplique al buzón.

Para evitar la eliminación accidental o involuntaria, se recomienda confirmar la suspensión antes de eliminar la cuenta de usuario. Si no se aplica la suspensión, el buzón no se convertirá en un buzón inactivo.

Para obtener instrucciones, consulte [Cómo identificar el tipo de retención colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention"></a>Buzones inactivos y retención de Microsoft 365

Si se aplica una directiva de retención de Microsoft 365 a un buzón de correo o uno o varios elementos de correo electrónico de un buzón tienen aplicada una etiqueta de retención y, a continuación, se elimina la cuenta de usuario de Microsoft 365, el buzón se convertirá en un buzón inactivo. Para crear el buzón inactivo:

- La configuración de retención debe configurarse para [conservar el contenido o conservar y eliminar el contenido](retention-settings.md#settings-for-retaining-and-deleting-content). Si la acción de retención está configurada para eliminar solo contenido, el buzón no estará inactivo cuando se elimine la cuenta de usuario. En el caso de los buzones inactivos, se recomienda usar la opción conservar y eliminar.

- La configuración de retención debe aplicarse a una [ubicación de retención](retention-settings.md#locations) asociada a un buzón de Exchange:
    - Correo electrónico de Exchange
    - Grupos de Microsoft 365
    - Skype Empresarial
    - Carpetas públicas de Exchange
    - Mensajes de canal de Teams
    - Chats de Teams
    - Mensajes del canal privado de Teams
    - Mensajes de la comunidad de Yammer
    - Mensajes del usuario de Yammer

Para obtener más información sobre la retención de Microsoft, consulte [Información sobre las directivas de retención y las etiquetas de retención](retention.md).

Si se usa la retención de Microsoft 365 para crear un buzón inactivo, la configuración de retención de la directiva de retención o las etiquetas de retención sigue aplicándose al buzón inactivo. Esto significa que si la configuración de retención está configurada para conservar y eliminar contenido, los elementos se moverán a la carpeta Elementos recuperables cuando expire la duración de la retención y, a continuación, se purgarán del buzón inactivo. Si la configuración de retención no está configurada para elementos eliminados, los elementos que el usuario no haya eliminado permanentemente (antes de que el buzón se inactiva) no se moverán a la carpeta Elementos recuperables y se conservarán indefinidamente después de que el buzón se inactiva.

> [!TIP]
> Puede usar la propiedad *ComplianceTagHoldApplied* para identificar si un buzón de correo tiene elementos que tienen una o varias etiquetas de retención aplicadas para conservar o conservar y eliminar contenido. Para obtener más información, vea [Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item).

### <a name="using-adaptive-policy-scopes-to-manage-retention-of-inactive-mailboxes"></a>Uso de ámbitos de directiva adaptable para administrar la retención de buzones inactivos

Con [los ámbitos de directiva adaptable](retention.md#adaptive-or-static-policy-scopes-for-retention), puede aplicar la configuración de retención específicamente a los buzones inactivos. Entre las ventajas de esta configuración se incluyen:

- Puede cumplir las normativas o directivas de su organización que requieren diferentes períodos de retención para los empleados activos y los empleados antiguos.

- Puede configurar las opciones de retención para conservar el contenido del buzón solo durante el tiempo necesario para satisfacer los requisitos de su organización para los empleados anteriores.

- Puede identificar rápidamente la directiva de retención asignada a buzones inactivos de su organización, lo que facilita el cambio de la configuración de retención si es necesario. 

- Es más fácil eliminar permanentemente un buzón inactivo porque puede quitarlo de la directiva [configurando el ámbito adaptable](retention-settings.md#to-configure-an-adaptive-scope) para excluirlo, en función de los atributos o propiedades del buzón inactivo. De lo contrario, debe usar [Exchange Online PowerShell](delete-an-inactive-mailbox.md#remove-an-inactive-mailbox-from-a-retention-policy) antes [de eliminar el buzón](delete-an-inactive-mailbox.md#before-you-delete-an-inactive-mailbox).

> [!NOTE]
> En función de la configuración del ámbito de la directiva adaptable, es posible que se incluyan o no buzones inactivos.  Para dirigirse específicamente o excluir buzones inactivos de un ámbito de directiva adaptable, consulte [información de configuración para el correo electrónico de Exchange y las carpetas públicas de Exchange](retention-settings.md#locations).

### <a name="using-static-policy-scopes-and-inactive-mailboxes"></a>Uso de ámbitos de directiva estática y buzones inactivos

Si no usa [ámbitos de directiva adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) con retención de Microsoft 365 y, en su lugar, usa un [ámbito estático](retention.md#adaptive-or-static-policy-scopes-for-retention), tenga en cuenta lo siguiente:

- Los ámbitos de directiva estática incluyen buzones inactivos cuando se usa la configuración predeterminada **Todos los destinatarios**, pero no se admiten para [inclusiones o exclusiones específicas](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions). Sin embargo, si incluye o excluye un destinatario que tiene un buzón de correo activo en el momento en que se aplica la directiva y el buzón más adelante pasa a estar inactivo, la configuración de retención se seguirá aplicando o excluyendo. En este escenario, se siguen aplicando [límites específicos de inclusión y exclusión](retention-limits.md) .
    
    > [!NOTE]
    > Esto también significa que cualquier nueva configuración de retención de Microsoft 365 mediante un ámbito estático que se aplique a la selección predeterminada de **Todos los destinatarios** incluirá automáticamente todos los buzones inactivos existentes.

- Si cambia la selección predeterminada de **Todos los destinatarios** para incluir destinatarios específicos, la configuración de retención de la directiva ya no se aplicará a los buzones inactivos, que ahora se convierten en aptos para la eliminación automática.

- Si desea liberar una directiva de retención que se aplica a un buzón inactivo, consulte [Liberación de una directiva para la retención](retention.md#releasing-a-policy-for-retention).

> [!CAUTION]
> Cuando use la retención de Microsoft 365 para que un buzón esté inactivo, no cambie ni quite el nombre principal de usuario (UPN) del buzón antes de eliminar la cuenta de usuario correspondiente. Además, no cambie la dirección SMTP principal (derivada del UPN) ni quite esta dirección de correo electrónico de la lista de direcciones SMTP secundarias asociadas al buzón antes de que el buzón esté inactivo.
> 
> Si cambia el UPN o las direcciones de correo electrónico (que se asignaron al buzón en el momento en que se aplicó la configuración de retención) y, a continuación, elimina la cuenta de usuario para que el buzón esté inactivo, no podrá eliminar el buzón inactivo si ya no necesita conservarlo. Esto se debe a que no puede quitar el buzón inactivo de la directiva mediante un UPN o una dirección de correo electrónico (para identificar el buzón inactivo) que sea diferente de los que existían cuando la configuración de retención se aplicó inicialmente al buzón. Para obtener más información sobre cómo eliminar buzones inactivos, vea [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones inactivos y retenciones de casos de exhibición de documentos electrónicos

Si una suspensión asociada a un caso de [exhibición](./get-started-core-ediscovery.md) de documentos electrónicos en el portal de cumplimiento Microsoft Purview se coloca en un buzón y, a continuación, se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. Sin embargo, no se recomienda usar las retenciones de mayúsculas y minúsculas de eDiscovery para que un buzón esté inactivo. Esto se debe a que los casos de eDiscovery están diseñados para casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y se quitarán las retenciones asociadas al caso y se cerrará el caso de eDiscovery. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y, a continuación, se libera la suspensión o se cierra (o elimina el caso de exhibición de documentos electrónicos), el buzón inactivo se eliminará permanentemente. Además, no se puede crear una suspensión de exhibición de documentos electrónicos basada en el tiempo. Esto significa que el contenido de un buzón inactivo se conserva para siempre o hasta que se quita la suspensión y se elimina el buzón inactivo. Por lo tanto, se recomienda usar la retención de Microsoft 365 para buzones inactivos.

Para obtener más información sobre las diferencias entre las retenciones de eDiscovery y la retención de Microsoft 365, vea [Cuándo usar directivas de retención y etiquetas de retención o retenciones de eDiscovery](retention.md#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Buzones inactivos y archivos de expansión automática

No se puede recuperar ni restaurar un buzón inactivo configurado con un archivo de expansión automática. En situaciones en las que es necesario recuperar datos de un buzón inactivo con un archivo de expansión automática, se recomienda usar la herramienta de búsqueda de contenido para exportar los datos del buzón y, a continuación, importarlos a otro buzón. Para obtener instrucciones paso a paso para buscar en un buzón inactivo y exportar los resultados de búsqueda, consulte:

- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones inactivos y directivas de retención de Exchange MRM

La aplicación de una directiva de retención de Exchange (la característica Administración de registros de mensajería o MRM en Exchange Online) no crea un buzón inactivo cuando se elimina la cuenta de usuario.

Sin embargo, si esta directiva de retención de MRM se aplicó a un buzón antes de que se inactiva, las directivas de eliminación (etiquetas de retención de MRM configuradas con una acción **Eliminar** ) se seguirán procesando en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación de MRM se moverán a la [carpeta Elementos recuperables](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

Por el contrario, se omiten las directivas de archivo (etiquetas de retención de MRM configuradas con una acción **MoveToArchive** ) que se incluyen en la directiva de retención de MRM asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.

## <a name="next-steps"></a>Pasos siguientes

Para que un buzón esté inactivo y administrarlo, como recuperarlo, restaurarlo y eliminarlo, consulte [Creación y administración de buzones inactivos](create-and-manage-inactive-mailboxes.md).
