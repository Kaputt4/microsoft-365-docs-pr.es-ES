---
title: Más información sobre la retención para Yammer
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
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre las directivas de retención de Microsoft 365 que se aplican a Yammer para que pueda administrar la retención automática o la eliminación de mensajes de Yammer para su organización.
ms.openlocfilehash: 631e8172d29826b3bad6c95c006a8ea8c18bce59
ms.sourcegitcommit: edc9d4dec92ca81cff39bbf9590f1cd3a75ec436
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68484377"
---
# <a name="learn-about-retention-for-yammer"></a>Más información sobre la retención para Yammer

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Yammer.

Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

Tanto los mensajes de usuario como los mensajes de la comunidad de Yammer se pueden eliminar mediante directivas de retención para Yammer y, además del texto de los mensajes, se pueden conservar los siguientes elementos por motivos de cumplimiento: vínculos de hipertexto y vínculos a otros mensajes de Yammer.

> [!NOTE]
> Como se explica en la sección siguiente, los mensajes de usuario incluyen mensajes privados para un usuario individual y cualquier mensaje de la comunidad asociado con ese usuario.
> 
> Los mensajes de usuario también incluyen [publicaciones de argumental](https://support.microsoft.com/office/overview-of-storyline-for-yammer-and-viva-engage-530e4e66-9f1c-4be1-b371-08ea40dc4b69), que son compatibles con las directivas de retención.

Los mensajes de usuario incluyen todos los nombres de las personas del chat y los mensajes de la comunidad incluyen el nombre de la comunidad y el título del mensaje (si se ha proporcionado).

No se conservan las reacciones de los demás usuarios en forma de emoticonos cuando se usan directivas de retención para Yammer.

Files that you use with Yammer aren't included in retention policies for Yammer. These items have their own retention policies.

## <a name="how-retention-works-with-yammer"></a>Cómo funciona la retención con Yammer

Use esta sección para comprender cómo los procesos y el almacenamiento de backend cumplen sus requisitos de cumplimiento, y las herramientas de exhibición de documentos electrónicos deben verificarlos en lugar de los mensajes que están visibles actualmente en la aplicación Yammer.

Puede usar una directiva de retención para conservar los datos de los mensajes de la comunidad y los mensajes de usuario en Yammer y eliminar estos mensajes. En segundo plano, se usan buzones de Exchange para almacenar datos copiados de estos mensajes. Los datos de los mensajes de usuario de Yammer se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el mensaje de usuario y se usa una carpeta oculta similar en un buzón de grupo para los mensajes de la comunidad.

Las copias de los mensajes de la comunidad también se pueden almacenar en la carpeta oculta de los buzones de usuario cuando @mencionan a usuarios o notifican al usuario una respuesta. Aunque estos mensajes se originan como un mensaje de la comunidad, una directiva de retención para los mensajes de usuario de Yammer a menudo incluirá copias de mensajes de la comunidad. Como resultado, los mensajes de usuario no se restringen a los mensajes privados.

Estas carpetas ocultas no están diseñadas para que los usuarios o administradores puedan acceder directamente a ellas, sino que almacenan datos que los administradores de cumplimiento pueden buscar con herramientas de exhibición de documentos electrónicos.

Si bien los mensajes de Yammer se almacenan en Exchange, estos mensajes de Yammer se incluyen solo por una directiva de retención que está configurada para los **mensajes de la comunidad de Yammer** y las ubicaciones de los **mensajes privados de Yammer**.

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los datos de Yammer y usted elimina el buzón de un usuario incluido en esta directiva, dicho buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md) para retener los datos de Yammer. Si no necesita retener los datos de Yammer del usuario, excluya la cuenta del usuario de la directiva de retención antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes de Yammer, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta en la que se almacenan estos mensajes de Yammer. El trabajo de temporizador tarda hasta siete días en ejecutarse. Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, una carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente.

> [!IMPORTANT]
> Debido al [primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence) y dado que los mensajes de Yammer se almacenan en buzones de Exchange Online, la eliminación permanente de la carpeta SubstrateHolds siempre se suspenderá si el buzón se ve afectado por otra directiva de retención de Yammer para la misma ubicación, suspensión por litigio, suspensión por retraso o si se aplica una retención de eDiscovery al buzón por motivos legales o de investigación.
>
> Aunque el buzón se incluye en una retención aplicable, los mensajes de Yammer que se hayan eliminado ya no estarán visibles en Yammer, pero seguirán detectables con eDiscovery.

Una vez que se configura una directiva de retención para los mensajes de Yammer, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo para retener, o solo para eliminar.

Cuando la directiva de retención consiste en retener y luego eliminar:

![Diagrama de flujo de retención para mensajes de Yammer.](../media/yammerretentionlifecycle.png)

Para las dos rutas en el diagrama:

1. Si el usuario **edita o elimina un mensaje de Yammer** durante el período de retención, el mensaje original se copia (si se edita) o se traslada (si se elimina) a la carpeta SubstrateHolds de manera inmediata. El mensaje se almacena hasta que finaliza el período de retención y, luego, se elimina de forma permanente e inmediata.

2. **Si no se elimina un mensaje de Yammer**, o se editan mensajes actuales, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención expire. Esta acción tarda hasta siete días después de la fecha de expiración. Cuando un mensaje se encuentra en la carpeta SubstrateHolds, se elimina entonces de forma permanente e inmediata. 

> [!NOTE]
> Los mensajes de la carpeta SubstrateHolds se pueden buscar con las herramientas de eDiscovery. Hasta que los mensajes se eliminen permanentemente de la carpeta SubstrateHolds, las herramientas de eDiscovery pueden buscarlos.

Cuando expira el período de retención y mueve un mensaje a la carpeta SubstrateHolds, se comunica una operación de eliminación al servicio Yammer, que luego retransmite la misma operación a la aplicación cliente de Yammer. Los retrasos en esta comunicación o almacenamiento en caché pueden explicar por qué, durante un breve período de tiempo, los usuarios siguen viendo estos mensajes en su aplicación de Yammer.

En este escenario, en el que el servicio de Yammer recibe un comando de eliminación debido a una directiva de retención, el mensaje correspondiente en la aplicación de Yammer se elimina para todos los usuarios de la conversación. Algunos de estos usuarios pueden ser de otra organización, tener una directiva de retención con un período de retención más largo o ninguna directiva de retención asignada a ellos. Para estos usuarios, las copias de los mensajes aún se almacenan en sus buzones y permanecen disponibles para la búsqueda en eDiscovery hasta que otra directiva de retención elimine permanentemente los mensajes.

> [!IMPORTANT]
> Los mensajes visibles en la aplicación Yammer no son un reflejo exacto de si se conservan o eliminan permanentemente para cumplir con los requisitos.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires. Then the message is immediately permanently deleted from the SubstrateHolds folder.

2. **Si el mensaje de Yammer no se modifica ni se elimina** y se editan mensajes actuales durante el período de retención: no sucede nada antes ni después del período de retención. El mensaje permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. **Si el mensaje de Yammer no se elimina** durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. Esta acción tarda hasta siete días después de la fecha de expiración. Luego, el mensaje se elimina de forma permanente e inmediata de la carpeta SubstrateHolds.

2. **Si el usuario elimina el mensaje de Yammer** durante el período, el elemento se mueve inmediatamente a la carpeta SubstrateHolds, donde se eliminará de forma permanente e inmediata.

#### <a name="example-flows-and-timings-for-retention-policies"></a>Ejemplos de flujos y tiempos para políticas de retención

Utilice los siguientes ejemplos para ver cómo los procesos y tiempos explicados en las secciones anteriores se aplican a las políticas de retención que tienen las siguientes configuraciones:

- [Ejemplo 1: solo retención durante 7 años](#example-1-retain-only-for-7-years)
- [Ejemplo 2: conservar durante 30 días y luego eliminar](#example-2-retain-for-30-days-and-then-delete)
- [Ejemplo 3: solo eliminar después de 1 día](#example-3-delete-only-after-1-day)

Para todos los ejemplos que hacen referencia a la eliminación permanente, debido a los [principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), esta acción se suspende si el mensaje está sujeto a otra política de retención para retener el elemento o si está sujeto a una retención de eDiscovery.

##### <a name="example-1-retain-only-for-7-years"></a>Ejemplo 1: solo retención durante 7 años

El día 1, el usuario publica un nuevo mensaje de Yammer.

El día 5, el usuario edita ese mensaje.

El día 30, el usuario elimina el mensaje actual.

Resultados de retención:

- Para el mensaje original:
    - El día 5, el mensaje se copia en la carpeta SubstrateHolds, donde aún se puede buscar con herramientas de eDiscovery durante un mínimo de 7 años a partir del día 1 (el período de retención).

- Para el mensaje actual (editado):
    - El día 30, el mensaje se mueve a la carpeta SubstrateHolds donde aún se puede buscar con herramientas de eDiscovery durante un mínimo de 7 años a partir del día 1 (el período de retención).

Si el usuario hubiera eliminado el mensaje actual después del período de retención especificado, en lugar de dentro del período de retención, el mensaje aún se movería a la carpeta SubstrateHolds. Sin embargo, ahora que el período de retención ha expirado, el mensaje se eliminará permanentemente después del mínimo de 1 día y luego, por lo general, dentro de 1 a 7 días.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Ejemplo 2: conservar durante 30 días y luego eliminar

El día 1, el usuario publica un nuevo mensaje de Yammer.

El día 10, el usuario edita ese mensaje.

El usuario no realiza más modificaciones y no elimina el mensaje.

Resultados de retención:

- Para el mensaje original:
    - El día 10, el mensaje se copia en la carpeta SubstrateHolds, donde aún se puede buscar con herramientas de eDiscovery.
    - Al final del período de retención (30 días a partir del día 1), el mensaje se elimina permanentemente, por lo general, dentro de 1 a 7 días después del mínimo de 1 día, y luego no se devolverá con las búsquedas de eDiscovery.

- Para el mensaje actual (editado):
    - Al final del período de retención (30 días a partir del día 1), el mensaje se mueve a la carpeta SubstrateHolds normalmente dentro de 1 a 7 días, donde aún se puede buscar con herramientas de eDiscovery.
    - Luego, el mensaje se elimina permanentemente, por lo general, dentro de 1 a 7 días después del mínimo de 1 día, y luego no se devolverá con las búsquedas de exhibición de documentos electrónicos.

##### <a name="example-3-delete-only-after-1-day"></a>Ejemplo 3: solo eliminar después de 1 día

> [!NOTE]
> Debido a la corta duración de un día de esta configuración y los procesos de retención que operan dentro de un período de tiempo de 1 a 7 días, esta sección muestra ejemplos de tiempos que están dentro de los rangos de tiempo típicos.

El día 1, el usuario publica un nuevo mensaje de Yammer.

Ejemplo de resultado de retención si el usuario no edita o elimina el mensaje:

- Día 5 (normalmente de 1 a 7 días después del inicio del período de retención el día 2):
    - El mensaje se mueve a la carpeta SubstrateHolds y permanece allí durante al menos 1 día donde aún se puede buscar con herramientas de eDiscovery.

- Día 9 (normalmente de 1 a 7 días después de un mínimo de 1 día en la carpeta SubstrateHolds):
    - Cuando un mensaje se elimina de forma permanente, no se mostrará en una búsqueda de eDiscovery.

Como muestra este ejemplo, aunque puede configurar una política de retención para eliminar mensajes después de solo un día, el servicio se somete a varios procesos para garantizar una eliminación compatible. Como resultado, una acción de eliminación después de 1 día podría tardar 16 días antes de que el mensaje se elimine permanentemente para que ya no se devuelva en las búsquedas de exhibición de documentos electrónicos.

## <a name="messages-and-external-users"></a>Mensajes y usuarios externos

De forma predeterminada, las directivas de retención para los mensajes del usuario de Yammer aplican a todos los usuarios de su organización, pero no aplica a los usuarios externos. Puede aplicar una directiva de retención a usuarios externos con la opción **Editar** para los usuarios incluidos y especificando su cuenta.

En este momento, no se admiten usuarios invitados B2B de Azure.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y se elimina su cuenta de Microsoft 365, los mensajes del usuario de Yammer que estén sujetos a la retención se almacenarán en un buzón inactivo. Estos mensajes seguirán sujetos a cualquier directiva de retención que se haya aplicado al buzón antes de pasar a estado inactivo, y el contenido estará disponible para la búsqueda de eDiscovery. Para obtener más información acerca de los buzones inactivos, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md).

Si el usuario ha guardado archivos en Yammer, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.

## <a name="limitations"></a>Limitaciones

Tenga en cuenta la siguiente limitación cuando utilice la retención para los mensajes de la comunidad Yammer y los mensajes de usuario:

- Al seleccionar **Editar** para la ubicación de los **mensajes del usuario de Yammer**, es posible que pueda ver a los invitados y a los usuarios sin buzón de correo. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md).

Si está listo para configurar una directiva de retención para Yammer, consulte [Crear y configurar directivas de retención](create-retention-policies.md).
