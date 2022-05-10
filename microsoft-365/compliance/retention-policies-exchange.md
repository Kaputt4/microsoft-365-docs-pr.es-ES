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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información acerca de cómo funciona la retención para Exchange.
ms.openlocfilehash: b49a21f5358bb8d4b25c1b164d30180f1fa265d9
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2022
ms.locfileid: "65285954"
---
# <a name="learn-about-retention-for-exchange"></a>Más información sobre la retención para Exchange

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Exchange. Para otras cargas de trabajo, consulte:

- [Más información sobre las directivas de retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>¿Qué se incluye para la retención y eliminación?

Los siguientes elementos de Exchange de buzones de usuario y buzones compartidos se pueden conservar y eliminar mediante directivas de retención y etiquetas de retención: los mensajes de correo (incluidos mensajes recibidos, borradores o mensajes enviados) con datos adjuntos, las tareas cuando tienen una fecha de finalización y las notas. 

Los elementos de calendario que tienen una fecha de finalización son compatibles con las directivas de retención, pero no son compatibles con las etiquetas de retención.

Los contactos y las tareas y elementos del calendario que no tienen una fecha de finalización no son compatibles.

Otros elementos almacenados en un buzón de correo, como los mensajes de Skype y Teams, no están incluidos en las directivas ni etiquetas de retención de Exchange. Estos elementos tienen sus propias directivas de retención.

Los buzones deben tener al menos 10 MB de datos antes de que se les aplique la configuración de retención, y las etiquetas de retención se puedan publicar en ellos.

## <a name="how-retention-works-for-exchange"></a>Cómo funciona la retención para Exchange

Tanto el buzón de correo como la carpeta pública usan la [carpeta Elementos recuperables](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) para retener elementos. Solo los usuarios a los que se les han asignado permisos de eDiscovery pueden ver elementos en la carpeta Elementos recuperables de otro usuario.
  
Cuando un usuario elimina un mensaje de una carpeta distinta de la carpeta Elementos eliminados, el mensaje se mueve de forma predeterminada a la carpeta Elementos eliminados. Sin embargo, un usuario puede eliminar temporalmente un elemento (Mayús+Eliminar) en cualquier carpeta, lo que omite la carpeta Elementos eliminados y mueve el elemento directamente a la carpeta Elementos recuperables.
  
Cuando aplica una configuración de retención a los datos de Exchange, un trabajo de temporizador evalúa periódicamente los elementos de la carpeta Elementos recuperables. Si un elemento no coincide con las reglas de al menos una directiva o etiqueta de retención, para retener el elemento este se elimina permanentemente (lo que también se conoce como eliminación permanente) de la carpeta Elementos recuperables.

> [!NOTE]
> Debido [al primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), la eliminación permanente siempre se suspende si el mismo elemento debe conservarse debido a otra directiva de retención o etiqueta de retención, o si está en retención de eDiscovery por motivos legales o de investigación.

El trabajo del temporizador puede tardar hasta siete días en ejecutarse y la ubicación de Exchange debe contar con al menos 10 MB de espacio.
  
Cuando un usuario intenta cambiar las propiedades de un elemento del buzón (como el asunto, el cuerpo, los datos adjuntos, los remitentes y los destinatarios, o la fecha de envío o recepción de un mensaje) se guarda una copia del elemento original en la carpeta Elementos recuperables antes de aplicar el cambio. Esto ocurre con cada cambio posterior. Al finalizar el período de retención, se eliminan las copias de la carpeta Elementos recuperables de forma permanente.

Una vez que se aplica la configuración de retención al contenido de Exchange, las rutas que sigue el contenido dependen de si la configuración de retención debe retener y eliminar, solo retener o solo eliminar.

Cuando los ajustes de retención son para retener y borrar:

![Diagrama de flujo de retención en el correo electrónico y las carpetas públicas.](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Si el usuario modifica o elimina el elemento de forma permanente** (mediante MAYÚS+SUPR o eliminándolo de Elementos eliminados) durante el período de retención, el elemento se mueve (o copia, en el caso de la edición) a la carpeta Elementos recuperables. Allí se ejecuta un trabajo de temporizador de forma periódica que identifica los elementos cuyo período de retención ha expirado y estos se eliminan permanentemente en un plazo de 14 días al finalizar el período de retención. Tenga en cuenta que 14 días es la configuración predeterminada, pero es posible cambiar la configuración hasta un máximo de 30 días.

2. **Si el elemento no se ha modificado o eliminado** durante el período de retención, el mismo proceso se ejecuta periódicamente en todas las carpetas del buzón para identificar los elementos cuyo período de retención ha expirado y estos se eliminan de forma permanente en un plazo de 14 días al final del período de retención. Tenga en cuenta que 14 días es la configuración predeterminada, pero es posible configurar hasta 30 días. 

Cuando los ajustes de retención son sólo de retención o sólo de borrado, las rutas de contenido son variaciones de retención y borrado:

### <a name="content-paths-for-retain-only-retention-settings"></a>Rutas de contenido para la configuración de la retención de sólo lectura

1. **Si el elemento se modifica o elimina** durante el período de retención, se crea una copia del elemento original en la carpeta elementos recuperables y se conserva hasta el final del período de retención, cuando la copia en la carpeta elementos recuperables se elimina permanentemente dentro de los 14 días posteriores a la caducidad del elemento. 

2. **Si el elemento se modifica o elimina** durante el período de retención, nada sucede antes y después del período de retención; el artículo permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Rutas de contenido para la configuración de retención de sólo borrado

1. **Si el elemento no se elimina** durante el período configurado: al final del período configurado en la directiva de retención, el elemento se mueve a la carpeta Elementos recuperables. 

2. **Si el elemento se elimina** durante el período configurado: el elemento se mueve inmediatamente a la carpeta Elementos recuperables. Si un usuario elimina el elemento o vacía la carpeta Elementos recuperables, el elemento se elimina de forma permanente. En caso contrario, el elemento se elimina permanentemente después de estar en la carpeta Elementos recuperables durante 14 días. 

## <a name="user-notification-of-expiry-date"></a>Notificación de usuario de la fecha de expiración

Las directivas de retención para Exchange, a diferencia de las directivas de retención para las otras cargas de trabajo de Microsoft 365, tienen presencia en el usuario mostrando en la parte superior de cada mensaje de correo electrónico el nombre de la directiva de retención que tiene la fecha de caducidad más corta para el elemento, y la fecha de caducidad calculada para ese elemento. Los usuarios no ven esta notificación si la directiva de retención no elimina elementos (solo retención).

Si se aplica una etiqueta de retención a un mensaje de correo electrónico, siempre se muestra el nombre de esa etiqueta y la fecha de expiración correspondiente, y reemplazará el nombre y la fecha de cualquier directiva de retención aplicada al buzón.

Recuerde que, en este contexto, la fecha de caducidad para la eliminación de un correo electrónico es el momento en que los usuarios pueden esperar a que el mensaje de correo electrónico se mueva automáticamente a la carpeta de elementos recuperables (si no está ya allí). Los correos electrónicos de la carpeta Elementos recuperables no se eliminarán de forma permanente, pero permanecerán allí por motivos de cumplimiento si están sujetos a cualquier configuración de retención para conservarla, o si se encuentran en una suspensión de eDiscovery por motivos legales o de investigación.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y su buzón de correo está incluido en una directiva de retención, el buzón pasa a estar inactivo cuando se elimina la cuenta de Microsoft 365 de dicho usuario. El contenido de un buzón inactivo sigue sujeto a cualquier directiva de retención que se le hubiera aplicado antes de que pasara a estar inactivo, y el contenido estará disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Buzones inactivos en Exchange Online](inactive-mailboxes-in-office-365.md).

Cuando la configuración de retención ya no aplique porque los datos se eliminaron permanentemente, o el período de retención expiró, el administrador de Exchange podrá [eliminar el buzón de correo inactivo](delete-an-inactive-mailbox.md). En este caso, el buzón inactivo no se elimina automáticamente.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md).

Si está listo para configurar una directiva de retención o etiqueta de retención para Exchange, consulte las siguientes instrucciones:
- [Crear y configurar directivas de retención](create-retention-policies.md)
- [Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)
