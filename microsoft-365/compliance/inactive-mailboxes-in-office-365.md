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
description: Obtenga información sobre cómo conservar el contenido del buzón de correo para antiguos empleados convirtiendo el buzón en un buzón inactivo.
ms.openlocfilehash: 72d048bc99876c0f252feffe3159d3ce01303028
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241520"
---
# <a name="learn-about-inactive-mailboxes"></a>Más información sobre los buzones inactivos

Es posible que su organización necesite conservar el correo electrónico de los antiguos empleados después de abandonar la organización. Dependiendo de los requisitos de retención de la organización, es posible que deba conservar el contenido del buzón durante unos meses o años después de que finalice el empleo, o quizás deba conservar el contenido del buzón de correo indefinidamente. Independientemente de cuánto tiempo necesites retener el correo electrónico, puedes crear buzones inactivos para conservar el buzón de correo de antiguos empleados.

## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado deja la organización (o se retira de una licencia extendida), puede quitar su Microsoft 365 cuenta. Los datos del buzón del empleado se conservan durante 30 días después de quitar la cuenta. Durante este período, puede recuperar los datos del buzón eliminando la cuenta. Después de 30 días, los datos se quitan permanentemente.

Pero si se aplica una retención al buzón antes de eliminar la cuenta Microsoft 365, el buzón se convertirá en un buzón inactivo. Las secciones siguientes contienen información acerca de las retenciones que se pueden aplicar con Microsoft 365 retención y retención de exhibición de documentos electrónicos.

Los buzones inactivos son útiles cuando la organización necesita conservar el contenido del buzón de los antiguos empleados por motivos normativos u otros. Aunque cualquier tipo de retención que aparece en este documento obligará a que un buzón se haga inactivo cuando se elimina un objeto de usuario, se recomienda hacerlo aplicando una directiva de retención de Microsoft 365 o etiquetas de [retención,](#confirming-a-hold-is-applied-to-a-mailbox)confirme que se aplica la retención y, a continuación, quite la cuenta de Microsoft 365 correspondiente. En ese momento, el contenido del buzón inactivo se conserva durante el período de retención especificado antes de eliminar la cuenta de usuario. Todavía puede recuperar la cuenta de usuario correspondiente durante un período de 30 días, pero después de 30 días, el buzón se conserva en Microsoft 365 como buzón inactivo hasta que se quitan las etiquetas de retención o directiva de retención.

> [!IMPORTANT]
> Como hemos mencionado anteriormente, se recomienda usar la retención Microsoft 365 para crear un buzón inactivo:
> - In-Place las retenciones en el Exchange de administración ya están retiradas. A partir del 1 de julio de 2020, las nuevas In-Place no se podían crear en Exchange Online. A partir del 1 de octubre de 2020, ya no se podía cambiar la duración de retención de las retenciones locales. Cualquier buzón inactivo que tenga una retención In-Place aplicación solo se puede eliminar quitando la In-Place espera. Los buzones inactivos existentes que están In-Place conservarán hasta que se quite la retención. Para obtener más información sobre In-Place de retención de documentos electrónicos, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
> 
> - [La retención por](create-a-litigation-hold.md) juicio sigue siendo compatible como un método alternativo para retener contenido en un buzón y hacerlo inactivo después de eliminar una cuenta de usuario. Sin embargo, como una tecnología más antigua, se recomienda usar la retención Microsoft 365 en su lugar.

Cuando hay varias retenciones en [](retention.md#the-principles-of-retention-or-what-takes-precedence) el mismo contenido, se aplica el principio de retención y el contenido se conserva durante el período más largo.

### <a name="confirming-a-hold-is-applied-to-a-mailbox"></a>Confirmar que se aplica una retención a un buzón

Tanto si aplica una directiva de retención de Microsoft 365, etiquetas de retención, retención de exhibición de documentos electrónicos, retención por juicio o una retención de In-Place existente, puede confirmar que la retención se aplicó correctamente al buzón mediante PowerShell. Si ha configurado la retención recientemente, es posible que deba esperar hasta que se aplique al buzón.

Para evitar la eliminación accidental o involuntaria, se recomienda confirmar la retención antes de eliminar la cuenta de usuario. Si no se aplica la retención, el buzón no se convertirá en un buzón inactivo.

Para obtener instrucciones, [vea How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention"></a>Buzones inactivos y Microsoft 365 retención

Si se aplica una directiva de retención de Microsoft 365 a un buzón o uno o varios elementos de correo electrónico de un buzón tienen una etiqueta de retención aplicada y, a continuación, se elimina la cuenta de usuario de Microsoft 365, el buzón se convertirá en un buzón inactivo. Para que se cree el buzón inactivo:

- La configuración de retención debe configurarse para conservar contenido o conservar [y,](retention-settings.md#settings-for-retaining-and-deleting-content)a continuación, eliminar el contenido . Si la acción de retención está configurada para eliminar solo contenido, el buzón no estará inactivo cuando se elimine la cuenta de usuario. Para los buzones inactivos, se recomienda usar la opción conservar y eliminar.

- La configuración de retención debe aplicarse a una ubicación [de retención](retention-settings.md#locations) asociada con un buzón de Exchange:
    - Correo electrónico de Exchange
    - Grupos de Microsoft 365
    - Skype Empresarial
    - Carpetas públicas de Exchange
    - Mensajes de canal de Teams
    - Chats de Teams
    - Mensajes del canal privado de Teams
    - Mensajes de la comunidad de Yammer
    - Mensajes del usuario de Yammer

Para obtener más información acerca de la retención de Microsoft, vea [Learn about retention policies and retention labels](retention.md).

Si Microsoft 365 se usa para crear un buzón inactivo, la configuración de retención de la directiva de retención o las etiquetas de retención siguen apliquen al buzón inactivo. Esto significa que si la configuración de retención está configurada para retener y eliminar el contenido, los elementos se mueven a la carpeta Elementos recuperables cuando expire la duración de retención y, a continuación, se purgarán del buzón inactivo. Si la configuración de retención no está configurada para los elementos eliminados, los elementos que el usuario no haya eliminado permanentemente (antes de que el buzón esté inactivo) no se moverán a la carpeta Elementos recuperables y se conservarán indefinidamente después de que el buzón esté inactivo.

> [!TIP]
> Puede usar la propiedad *ComplianceTagHoldApplied* para identificar si un buzón tiene elementos que tienen una o más etiquetas de retención aplicadas para retener o retener y, a continuación, eliminar contenido. Para obtener más información, vea [Identifying mailboxes on hold because a retention label has been applied to a folder or item](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item).

### <a name="using-adaptive-policy-scopes-to-manage-retention-of-inactive-mailboxes"></a>Uso de ámbitos de directivas adaptables para administrar la retención de buzones inactivos

Con [los ámbitos de directiva adaptables,](retention.md#adaptive-or-static-policy-scopes-for-retention)puede aplicar la configuración de retención específicamente a los buzones inactivos. Entre las ventajas de esta configuración se incluyen:

- Puede cumplir con las normativas o directivas de su organización que requieren diferentes períodos de retención para empleados activos y antiguos empleados.

- Puede configurar las opciones de retención para conservar el contenido del buzón solo durante el tiempo que sea necesario para cumplir los requisitos de su organización para los antiguos empleados.

- Puede identificar rápidamente la directiva de retención asignada a buzones inactivos de la organización, lo que facilita cambiar la configuración de retención si es necesario. 

- Es más fácil eliminar permanentemente un buzón inactivo porque puede [](retention-settings.md#to-configure-an-adaptive-scope) quitarlo de la directiva configurando el ámbito adaptable para excluirlo, en función de los atributos o propiedades del buzón inactivo. De lo contrario, debe usar [Exchange Online PowerShell antes](delete-an-inactive-mailbox.md#remove-an-inactive-mailbox-from-a-retention-policy) [de eliminar el buzón](delete-an-inactive-mailbox.md#before-you-delete-an-inactive-mailbox).

> [!NOTE]
> Según la configuración del ámbito de directiva adaptable, los buzones inactivos pueden o no incluirse.  Para dirigirse específicamente o excluir buzones inactivos de un ámbito de directiva adaptable, vea información de configuración para Exchange correo electrónico y Exchange [carpetas públicas](retention-settings.md#locations).

### <a name="using-static-policy-scopes-and-inactive-mailboxes"></a>Uso de ámbitos de directiva estática y buzones inactivos

Si no usa [ámbitos](retention.md#adaptive-or-static-policy-scopes-for-retention) de directiva adaptables Microsoft 365 retención y, en su lugar, usa un ámbito [estático,](retention.md#adaptive-or-static-policy-scopes-for-retention)tenga en cuenta lo siguiente:

- Los ámbitos de directiva estática incluyen buzones inactivos cuando se usa la configuración predeterminada **Todos los destinatarios**, pero no se admiten para [inclusiones o exclusiones específicas](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions). Sin embargo, si incluye o excluye un destinatario que tiene un buzón de correo activo en el momento en que se aplica la directiva y el buzón más adelante pasa a estar inactivo, la configuración de retención se seguirá aplicando o excluyendo. En este escenario, [aún se aplican límites](retention-limits.md) específicos de inclusión y exclusión.
    
    > [!NOTE]
    > Esto también significa que cualquier nueva configuración Microsoft 365 de retención mediante un ámbito estático que se aplica a la selección predeterminada de Todos los destinatarios incluirá automáticamente todos los **buzones inactivos** existentes.

- Si cambia la selección predeterminada de Todos los destinatarios para incluir destinatarios específicos, la configuración de retención de la directiva ya no se aplicará a los buzones **inactivos,** que ahora son aptos para la eliminación automática.

- Si desea liberar una directiva de retención que se aplica a un buzón inactivo, vea Liberar una [directiva para retención](retention.md#releasing-a-policy-for-retention).

> [!CAUTION]
> Cuando use la retención Microsoft 365 para hacer inactivo un buzón, no cambie ni quite el nombre principal de usuario (UPN) del buzón antes de eliminar la cuenta de usuario correspondiente. Además, no cambie la dirección SMTP principal (derivada del UPN) ni quite esta dirección de correo electrónico de la lista de direcciones SMTP secundarias asociadas con el buzón antes de hacer que el buzón esté inactivo.
> 
> Si cambia el UPN o las direcciones de correo electrónico (que se asignaron al buzón en el momento en que se aplicó la configuración de retención) y, a continuación, elimina la cuenta de usuario para que el buzón esté inactivo, no podrá eliminar el buzón inactivo si ya no necesita conservarlo. Esto se debe a que no puede quitar el buzón inactivo de la directiva mediante un UPN o una dirección de correo electrónico (para identificar el buzón inactivo) que sea diferente de los que existían cuando la configuración de retención se aplicó inicialmente al buzón. Para obtener más información acerca de cómo eliminar buzones inactivos, vea Eliminar un buzón inactivo [en Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones inactivos y retenciones de casos de exhibición de documentos electrónicos

Si una retención asociada a [](./get-started-core-ediscovery.md) un caso de exhibición de documentos electrónicos en Centro de cumplimiento de Microsoft 365 se coloca en un buzón y, a continuación, se elimina el buzón o la cuenta del usuario, el buzón se convierte en un buzón inactivo. Sin embargo, no recomendamos usar retenciones de casos de exhibición de documentos electrónicos para hacer que un buzón sea inactivo. Esto se debe a que los casos de exhibición de documentos electrónicos están destinados a casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y se quitarán las retenciones asociadas al caso y se cerrará el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y, a continuación, la retención se libera o el caso de exhibición de documentos electrónicos se cierra (o elimina), el buzón inactivo se eliminará permanentemente. Además, no puede crear una retención de exhibición de documentos electrónicos basada en tiempo. Esto significa que el contenido de un buzón inactivo se conserva para siempre o hasta que se quita la retención y se elimina el buzón inactivo. Por lo tanto, se recomienda usar Microsoft 365 retención de buzones inactivos.

Para obtener más información acerca de las diferencias entre las retenciones de exhibición de documentos electrónicos y la retención Microsoft 365, vea When [to use retention policies and retention labels or eDiscovery holds](retention.md#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Buzones inactivos y archivos de expansión automática

Un buzón inactivo configurado con un archivo de expansión automática no se puede recuperar ni restaurar. En situaciones en las que es necesario recuperar datos de un buzón inactivo con un archivo de expansión automática, se recomienda usar la herramienta de búsqueda de contenido para exportar los datos del buzón y luego importarlos a otro buzón. Para obtener instrucciones paso a paso para buscar en un buzón inactivo y exportar los resultados de búsqueda, vea:

- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones inactivos y directivas Exchange de retención de MRM

La aplicación de una directiva Exchange de retención (la característica De administración de registros de mensajería o MRM en Exchange Online) no crea un buzón inactivo cuando se elimina la cuenta de usuario.

Sin embargo, si esta directiva de retención de MRM se aplicó **a** un buzón antes de que se inactivase, las directivas de eliminación (etiquetas de retención de MRM configuradas con una acción Eliminar) seguirán procesandose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación de MRM se mueven a la carpeta [Elementos](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

Por el contrario, se omiten las directivas de archivo (etiquetas de retención de MRM configuradas con una acción **MoveToArchive)** que se incluyen en la directiva de retención de MRM asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.

## <a name="next-steps"></a>Pasos siguientes

Para hacer inactivo un buzón y administrarlo, como recuperarlo, restaurarlo y eliminarlo, vea [Create and manage inactive mailboxes](create-and-manage-inactive-mailboxes.md).
