---
title: Más información sobre la retención para el intercambio
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información acerca de cómo funciona la retención para Exchange.
ms.openlocfilehash: efb95b22355bff292ef63c77fb77fb5a15d66722
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861136"
---
# <a name="learn-about-retention-for-exchange"></a>Más información sobre la retención para Exchange

La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Exchange.  Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>¿Qué se incluye para la retención y eliminación?

Los siguientes elementos de Exchange pueden ser retenidas y eliminadas con las directivas de retención y las etiquetas de retención: mensajes de correo (incluidos los borradores) con datos adjuntos, tareas que tienen una fecha de finalización y notas. 

Los elementos de calendario que tienen una fecha de finalización son compatibles con las directivas de retención, pero no son compatibles con las etiquetas de retención.

Los contactos y las tareas y elementos del calendario que no tienen una fecha de finalización no son compatibles.

Otros elementos almacenados en un buzón de correo, como los mensajes de Skype y Teams, no están incluidos en las directivas ni etiquetas de retención de Exchange. Estos elementos tienen sus propias directivas de retención.

## <a name="how-retention-works-for-exchange"></a>Cómo funciona la retención para Exchange

Tanto un buzón como una carpeta pública utilizan la [carpeta Elementos recuperables](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) para retener elementos. Sólo las personas a las que se les han asignado permisos de eDiscovery pueden ver los elementos de la carpeta Elementos recuperables de otro usuario.
  
De manera predeterminada, cuando un usuario elimina un mensaje de una carpeta que no sea la carpeta Elementos eliminados, el mensaje se mueve a esta carpeta. Cuando un usuario elimina un elemento de la carpeta Elementos eliminados, el mensaje se mueve a la carpeta Elementos recuperables. Sin embargo, un usuario puede eliminar temporalmente un elemento de cualquier carpeta (MAYÚS+Supr). Esta acción omite la carpeta Elementos eliminados y coloca el elemento directamente en la carpeta Elementos recuperables.
  
Cuando aplica una configuración de retención a los datos de Exchange, un trabajo de temporizador evalúa periódicamente los elementos de la carpeta Elementos recuperables. Si un elemento no coincide con las reglas de al menos una directiva o etiqueta de retención, para retener el elemento este se elimina permanentemente (lo que también se conoce como eliminación permanente) de la carpeta Elementos recuperables.

> [!NOTE]
> Debido [al primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), la eliminación permanente siempre se suspende si el mismo elemento debe conservarse debido a otra directiva de retención o etiqueta de retención, o si está en retención de eDiscovery por motivos legales o de investigación.

El trabajo del temporizador puede tardar hasta siete días en ejecutarse y la ubicación de Exchange debe contar con al menos 10 MB de espacio.
  
Cuando un usuario intenta cambiar las propiedades de un elemento del buzón (como el asunto, el cuerpo, los datos adjuntos, los remitentes y los destinatarios, o la fecha de envío o recepción de un mensaje) se guarda una copia del elemento original en la carpeta Elementos recuperables antes de aplicar el cambio. Esto ocurre con cada cambio posterior. Al finalizar el período de retención, se eliminan las copias de la carpeta Elementos recuperables de forma permanente.

Una vez que se aplica la configuración de retención al contenido de Exchange, las rutas que sigue el contenido dependen de si la configuración de retención debe retener y eliminar, solo retener o solo eliminar.

Cuando los ajustes de retención son para retener y borrar:

![Diagrama de flujo de retención en el correo electrónico y las carpetas públicas](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Si el elemento se ha modificado o eliminado permanentemente** por el usuario (usando MAYÚS+SUPR o eliminarlo de Elementos eliminados) durante el periodo de retención: el elemento se mueve (o es copiado, en el caso de la modificación) a la carpeta Elementos recuperables. Allí, un trabajo de temporizador se ejecuta periódicamente e identifica los artículos cuyo período de retención ha expirado, y estos artículos se eliminan de forma permanente dentro de los 14 días siguientes a la finalización del período de retención. Tenga en cuenta que 14 días es la opción predeterminada, pero puede configurar hasta 30 días.

2. **Si el elemento no se ha modificado o eliminado** durante el período de retención, el mismo proceso se ejecuta periódicamente en todas las carpetas del buzón para identificar los elementos cuyo período de retención ha expirado y estos se eliminan de forma permanente en un plazo de 14 días al final del período de retención. Tenga en cuenta que 14 días es la configuración predeterminada, pero es posible configurar hasta 30 días. 

Cuando los ajustes de retención son sólo de retención o sólo de borrado, las rutas de contenido son variaciones de retención y borrado:

### <a name="content-paths-for-retain-only-retention-settings"></a>Rutas de contenido para la configuración de la retención de sólo lectura

1. **Si el elemento se modifica o elimina** durante el período de retención, se crea una copia del elemento original en la carpeta elementos recuperables y se conserva hasta el final del período de retención, cuando la copia en la carpeta elementos recuperables se elimina permanentemente dentro de los 14 días posteriores a la caducidad del elemento. 

2. **Si el elemento se modifica o elimina** durante el período de retención, nada sucede antes y después del período de retención; el artículo permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Rutas de contenido para la configuración de retención de sólo borrado

1. **Si el elemento no se elimina** durante el período configurado: al final del período configurado en la directiva de retención, el elemento se mueve a la carpeta Elementos recuperables. 

2. **Si el elemento se elimina** durante el período configurado: el elemento se mueve inmediatamente a la carpeta Elementos recuperables. Si un usuario elimina el elemento o vacía la carpeta Elementos recuperables, el elemento se elimina de forma permanente. En caso contrario, el elemento se elimina permanentemente después de estar en la carpeta Elementos recuperables durante 14 días. 

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y su buzón está incluido en una directiva de retención, el buzón pasa a estado inactivo cuando se elimina la cuenta de Microsoft 365 del usuario. El contenido de un buzón inactivo sigue estando sujeto a cualquier directiva de retención que se hubiera aplicado al buzón antes de que pasara a estar inactivo, y está disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md).

Si está listo para configurar una directiva de retención o etiqueta de retención para Exchange, consulte las siguientes instrucciones:
- [Crear y configurar directivas de retención](create-retention-policies.md)
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)