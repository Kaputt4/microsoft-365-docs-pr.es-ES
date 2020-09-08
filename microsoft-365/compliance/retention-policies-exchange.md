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
ms.openlocfilehash: e12f46b68feb4b64ade14cfb046061d89e1a607c
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394717"
---
# <a name="learn-about-retention-for-exchange"></a>Más información sobre la retención para Exchange

La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Exchange.

## <a name="how-retention-works-for-exchange"></a>Cómo funciona la retención para Exchange

Tanto un buzón como una carpeta pública utilizan la [carpeta Elementos recuperables](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) para retener elementos. Sólo las personas a las que se les han asignado permisos de eDiscovery pueden ver los elementos de la carpeta Elementos recuperables de otro usuario.
  
Cuando una persona elimina un mensaje en una carpeta distinta de la carpeta Elementos eliminados, de forma predeterminada, el mensaje pasa a la carpeta Elementos eliminados. Cuando una persona elimina un elemento de la carpeta Elementos eliminados, el mensaje se mueve a la carpeta Elementos recuperables. Sin embargo, un usuario puede borrar un elemento (Mayús+Supr) en cualquier carpeta, lo que evita la carpeta Elementos eliminados y mueve el elemento directamente a la carpeta Elementos recuperables.
  
Cuando aplica una configuración de retención a los datos de Exchange, un trabajo de temporizador evalúa periódicamente los elementos de la carpeta Elementos recuperables. Si un elemento no coincide con las reglas de al menos una directiva o etiqueta de retención, el elemento se elimina permanentemente (lo que también se conoce como eliminación permanente) de la carpeta Elementos recuperables.

El trabajo del temporizador puede tardar hasta siete días en ejecutarse y la ubicación de Exchange debe contar con al menos 10 MB de espacio.
  
When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed. Esto ocurre con cada cambio posterior. Al final del período de retención, se eliminan de forma permanente las copias de la carpeta Elementos recuperables.

Una vez que se aplica la configuración de retención al contenido de Exchange, las rutas que sigue el contenido dependen de si la configuración de retención debe retener y eliminar, solo retener o solo eliminar.

Cuando los ajustes de retención son para retener y borrar:

![Diagrama de flujo de retención en el correo electrónico y las carpetas públicas](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Si el elemento se ha modificado o eliminado permanentemente** por el usuario (usando MAYÚS+SUPR o eliminarlo de Elementos eliminados) durante el periodo de retención: el elemento se mueve (o es copiado, en el caso de la modificación) a la carpeta Elementos recuperables. Allí, un trabajo de temporizador se ejecuta periódicamente e identifica los artículos cuyo período de retención ha expirado, y estos artículos se eliminan de forma permanente dentro de los 14 días siguientes a la finalización del período de retención. Tenga en cuenta que 14 días es la opción predeterminada, pero puede configurar hasta 30 días.

2. **Si no se modifica ni elimina el elemento** durante el periodo de retención: se ejecuta periódicamente el mismo proceso en todas las carpetas en el buzón y se identifican los elementos cuyo periodo de retención ha caducado. Estos elementos se eliminan permanentemente en el plazo de 14 días al finalizar el periodo de retención. Tenga en cuenta que 14 días es la opción predeterminada, pero puede configurar hasta 30 días. 

Cuando los ajustes de retención son sólo de retención o sólo de borrado, las rutas de contenido son variaciones de retención y borrado:

### <a name="content-paths-for-retain-only-retention-settings"></a>Rutas de contenido para la configuración de la retención de sólo lectura

1. **Si el elemento se modifica o elimina** durante el período de retención, se crea una copia del elemento original en la carpeta elementos recuperables y se conserva hasta el final del período de retención, cuando la copia en la carpeta elementos recuperables se elimina permanentemente dentro de los 14 días posteriores a la caducidad del elemento. 

2. **Si el elemento se modifica o elimina** durante el período de retención, nada sucede antes y después del período de retención; el artículo permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Rutas de contenido para la configuración de retención de sólo borrado

1. **Si el elemento no se elimina** durante el período configurado: al final del período configurado en la directiva de retención, el elemento se mueve a la carpeta Elementos recuperables. 

2. **Si el elemento se elimina** durante el período configurado: el elemento se mueve inmediatamente a la carpeta Elementos recuperables. Si un usuario elimina el elemento o vacía la carpeta Elementos recuperables, el elemento se elimina de forma permanente. En caso contrario, el elemento se elimina permanentemente después de estar en la carpeta Elementos recuperables durante 14 días. 

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y su buzón está incluido en una directiva de retención, el buzón pasa a estado inactivo cuando se elimina la cuenta de Microsoft 365 del usuario. El contenido de un buzón inactivo sigue estando sujeto a cualquier directiva de retención que se hubiera aplicado al buzón antes de que pasara a estar inactivo, y está disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).

Si está listo para configurar una directiva de retención o etiqueta de retención para Exchange, consulte las siguientes instrucciones:
- [Crear y configurar directivas de retención](create-retention-policies.md)
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)