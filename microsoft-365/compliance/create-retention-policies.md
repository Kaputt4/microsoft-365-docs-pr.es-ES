---
title: Cree y configure directivas de retención para retener o eliminar automáticamente el contenido
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
description: Use una directiva de retención para controlar de forma eficaz el contenido que los usuarios generan con el correo electrónico, los documentos y las conversaciones. Conserve lo que desee y libérese de lo que no quiere.
ms.openlocfilehash: 4a1a0c5334772d9259278d884090c75d8441df22
ms.sourcegitcommit: f6fff04431d632db02e7bdbf12f691091a30efad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "60432606"
---
# <a name="create-and-configure-retention-policies"></a>Crear y configurar directivas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use una directiva de retención con el fin de administrar los datos de su organización. Para ello, decida proactivamente si se retiene el contenido, se elimina o si primero se retiene y después se elimina.

Una directiva de retención le permite hacerlo de manera muy eficaz. Solo tiene que asignar la misma configuración de retención a nivel del contenedor al contenido de ese contenedor, que lo hereda de forma automática. Por ejemplo, todos los elementos de los sitios de SharePoint, todos los mensajes de correo electrónico de los buzones de Exchange de los usuarios, todos los mensajes de canal de los equipos que se usan con Microsoft Teams. Si no está seguro sobre si debe usar una directiva de retención o una etiqueta de retención, consulte [Directivas de retención y etiquetas de retención](retention.md#retention-policies-and-retention-labels).

Para obtener más información sobre las directivas de retención y cómo funciona la retención en Microsoft 365, vea [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).

> [!NOTE]
> La información de esta página es para los administradores de cumplimiento normativo. Si no es administrador y quiere entender cómo se configuraron las directivas de retención para las aplicaciones que usa, póngase en contacto con el departamento de soporte técnico, el departamento de TI o el administrador. Si ve mensajes sobre directivas de retención en los chats de Teams y en los mensajes de canal, puede serle útil revisar [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y modificar directivas de retención. Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

Antes de crear la directiva de retención, decida si será **adaptable** o **estática**. Para obtener más información, vea [Ámbitos de directivas adaptables o estáticas para retención](retention.md#adaptive-or-static-policy-scopes-for-retention). Si decide usar una directiva adaptable, debe crear uno o más ámbitos adaptables antes de crear la directiva de retención. Luego deberá seleccionarlos durante el proceso de creación de directivas de retención. Para obtener instrucciones, vea [Información de configuración para ámbitos adaptables](retention-settings.md#configuration-information-for-adaptive-scopes).

## <a name="create-and-configure-a-retention-policy"></a>Crear y configurar una directiva de retención

Aunque una directiva de retención puede admitir varios servicios identificados como "ubicaciones" en la directiva de retención, no puede crear una sola directiva de retención que incluya todas las ubicaciones compatibles:

- Correo electrónico de Exchange
- Sitio de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial
- Carpetas públicas de Exchange
- Mensajes de canal de Teams
- Chats de Teams
- Mensajes del canal privado de Teams
- Mensajes de la comunidad de Yammer
- Mensajes del usuario de Yammer

Cuando selecciona una de las ubicaciones de Teams o Yammer durante la creación de una directiva de retención, las demás ubicaciones quedan excluidas automáticamente. Por lo tanto, las instrucciones que debe seguir dependerán de si necesita incluir las ubicaciones de Teams o de Yammer:

- [Instrucciones para crear una directiva de retención para ubicaciones de Teams](#retention-policy-for-teams-locations)
- [Instrucciones para crear una directiva de retención para ubicaciones de Yammer](#retention-policy-for-yammer-locations)
- [Instrucciones para crear una directiva de retención para otras ubicaciones fuera de Teams y Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

> [!NOTE]
> Al usar directivas adaptables en lugar de estáticas, puede configurar una única directiva de retención que incluya tanto ubicaciones de Teams como de Yammer. No sucede lo mismo con las directivas estáticas, ya que las ubicaciones de Teams y Yammer requieren su propia directiva de retención.

Si tiene más de una directiva de retención y, además, utiliza etiquetas de retención, consulte [Los principios de la retención o qué tiene prioridad](retention.md#the-principles-of-retention-or-what-takes-precedence) para entender qué resultado se obtiene cuando varias configuraciones de retención se aplican al mismo contenido.

### <a name="retention-policy-for-teams-locations"></a>Directiva de retención para ubicaciones de Teams

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para iniciar la configuración de **Crear directiva de retención** y asigne un nombre a la nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar **chats de Teams** pero no **mensajes de canal de Teams**. 
    
    - Si ha elegido **Estática**: en la página **Elegir ubicaciones para aplicar la directiva**, seleccione una o más ubicaciones para Teams:
        - **Mensaje del canal de Teams**: mensajes de los chats del canal estándar y de las reuniones del canal estándar, pero no de los [canales privados](/microsoftteams/private-channels) que tienen su propia directiva de localización.
        - **Chats de Teams**: mensajes de chats privados 1:1, chats grupales y chats de reunión.
        - **Mensajes del canal privado de Teams**: Mensajes de chats de canales privados y reuniones de canales privados.
        
       De forma predeterminada, [se seleccionan todos los equipos y todos los usuarios](retention-settings.md#a-policy-that-applies-to-entire-locations), pero puede refinar esto al seleccionar la [**Elegir** y **Excluir** opciones](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions). Pero, antes de cambiar el valor predeterminado, tenga en cuenta las siguientes consecuencias para una directiva de retención que elimina los mensajes cuando está configurada para incluir o excluir:
        
        - En el caso de los mensajes de los chats de grupo y los mensajes de los canales privados, como se guarda una copia de los mensajes en el buzón de cada usuario incluido en el chat, se seguirán devolviendo copias de los mensajes en los resultados de eDiscovery de los usuarios a los que no se les asignó la directiva.
        - En el caso de los usuarios a los que no se les haya asignado la directiva, los mensajes eliminados se devolverán en los resultados de la búsqueda de Teams, pero no mostrarán el contenido del mensaje como resultado de la eliminación permanente de la directiva asignada a los usuarios.

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

   Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](retention-settings.md#settings-for-retaining-and-deleting-content).

6. Complete la configuración y guarde los ajustes.

Para obtener instrucciones sobre cuándo usar directivas de retención para Teams y conocer la experiencia del usuario final, vea [Administrar directivas de retención para Microsoft Teams](/microsoftteams/retention-policies) en la documentación de Teams.

Para obtener detalles técnicos sobre el funcionamiento de la retención de Teams, incluidos los elementos de los mensajes admitidos para la retención e información sobre los períodos de tiempo con tutoriales de ejemplo, vea [Más información sobre la retención de Microsoft Teams](retention-policies-teams.md).

#### <a name="known-configuration-issues"></a>Problemas de configuración conocidos

- Aunque puede seleccionar la opción para iniciar el período de retención en el que se modificaron los elementos por última vez, siempre se usa el valor **Cuando se crearon los elementos**. Para los mensajes que se editan, se guarda una copia del mensaje original con la marca de tiempo original para identificar cuándo se creó este mensaje antes de editar, y el mensaje después de editar tiene una marca de tiempo más reciente.

- Al seleccionar **Editar** para la ubicación de los **mensajes del canal Teams** es posible que vea grupos de Microsoft 365 que tampoco son equipos. No seleccione estos grupos.

- Al seleccionar **Editar** para la ubicación de los chats de Teams puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.


#### <a name="additional-retention-policy-needed-to-support-teams"></a>Directivas de retención adicionales que se necesitan para Teams

Teams es mucho más que solo chats y mensajes de canal. Si tiene equipos creados a partir de un grupo de Microsoft 365 (anteriormente "grupo de Office 365"), debe configurar una directiva de retención que incluya el grupo de Microsoft 365 mediante la ubicación de **Grupos de Microsoft 365**. La directiva de retención se aplica al contenido del buzón, del sitio y de los archivos del grupo.

Si tiene sitios de equipo que no estén conectados con un grupo de Microsoft 365, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive** para conservar y eliminar archivos en Teams:

- Los archivos que se comparten en el chat se almacenan en la cuenta de OneDrive del usuario que compartió el archivo.

- Los archivos que se suben a los canales se almacenan en el sitio de SharePoint del equipo.

> [!TIP]
> Puede aplicar una directiva de retención a los archivos de un solo equipo específico cuando no está conectado a un grupo de Microsoft 365. Para ello, seleccione el sitio de SharePoint del equipo y las cuentas de OneDrive de los usuarios del mismo.

Es posible que una directiva de retención que se aplique a los grupos de Microsoft 365, los sitios de SharePoint o las cuentas de OneDrive pueda eliminar un archivo al que se hace referencia en un mensaje de canal o chat de Teams antes de que se eliminen esos mensajes. En este caso, el archivo seguirá apareciendo en el mensaje de Teams, pero cuando los usuarios lo seleccionen, obtendrán un error de "Archivo no encontrado". Este comportamiento no es específico de las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Directiva de retención para ubicaciones de Yammer

> [!NOTE]
> Las directivas de retención de Yammer están en versión preliminar y actualmente no informan a los usuarios cuando los mensajes se eliminan como resultado de una directiva de retención.
>
> Para usar esta característica, la red de Yammer debe estar en [Modo nativo](/yammer/configure-your-yammer-network/overview-native-mode), en lugar de en Modo híbrido.

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para crear una nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar **mensajes de usuario de Yammer** pero no **mensajes de la comunidad de Yammer**. 
    
    - Si ha elegido **Estática**: en la página **Elegir ubicaciones para aplicar la directiva**, alterne entre una o ambas ubicaciones para Yammer: **mensajes de la comunidad de Yammer** y **mensajes de usuario de Yammer**.
        
        > [!IMPORTANT]
        > Aunque puede crear una directiva de retención solo para los mensajes de usuario de Yammer, una directiva de retención para esta ubicación puede eliminar los mensajes de la comunidad de la aplicación Yammer para todos los miembros de la comunidad.
        > 
        > Si elige esta opción y la directiva de retención se configurará para eliminar mensajes de usuario, asegúrese de comprender esta implicación. Para más información, consulte [Cómo funciona la retención con Yammer](retention-policies-yammer.md#how-retention-works-with-yammer).
        
        De forma predeterminada se seleccionan todas las comunidades y los usuarios, pero también puede restringir los resultados al especificar qué comunidades y usuarios desea incluir o excluir.
        
        Para los mensajes del usuario de Yammer: 
        - Si deja la opción predeterminada en **Todos los usuarios**, no se incluirá a los usuarios invitados de Azure B2B. 
        - Si selecciona **Editar** para **Todos los usuarios**, puede aplicar una directiva de retención a los usuarios externos si conoce sus cuentas.

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido. 
    
    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](retention-settings.md#settings-for-retaining-and-deleting-content).

6. Complete la configuración y guarde los ajustes.

Para obtener más información sobre cómo funcionan las directivas de retención de Yammer, consulte [Obtener información sobre la retención para Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Directivas de retención adicionales que se necesitan para admitir Yammer

Yammer es más que solo mensajes de la comunidad y mensajes privados. Para conservar y eliminar los mensajes de correo electrónico de su red de Yammer, configure una directiva de retención adicional que incluya a los grupos de Microsoft 365 que se usan para Yammer, mediante la ubicación de los **Grupos de Microsoft 365**. 

Para conservar y eliminar los archivos almacenados en Yammer, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive**:

- Los archivos compartidos en los mensajes privados se almacenan en la cuenta de OneDrive del usuario que compartió el archivo. 

- Los archivos que se cargan en las comunidades se almacenan en el sitio de SharePoint de la comunidad de Yammer.

Es posible que una directiva de retención que se aplique a los sitios de SharePoint o a las cuentas de OneDrive pueda eliminar un archivo al que se haga referencia en un mensaje de Yammer antes de que dicho mensaje sean eliminado. En este caso, el archivo seguirá mostrándose en el mensaje de Yammer, pero cuando los usuarios lo seleccionen, obtendrán el error "Archivo no encontrado". Este comportamiento no es específico para las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Directivas de retención para otras ubicaciones fuera de Teams y Yammer

Use las siguientes instrucciones para crear directivas de retención que apliquen a cualquiera de estos servicios:

- Correo electrónico y carpetas públicas de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para iniciar la configuración de **Crear directiva de retención** y asigne un nombre a la nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción. Las directivas adaptables no admiten las ubicaciones de las carpetas públicas de Exchange o Skype Empresarial.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar **correo de Exchange** pero no **sitios de SharePoint**. 
    
    - Si ha elegido **Estático**: en la página **Elegir ubicaciones**, active o desactive cualquiera de las ubicaciones excepto las de Teams y Yammer. Para cada ubicación, puede dejar de forma predeterminada [aplicar la directiva a toda la ubicación](retention-settings.md#a-policy-that-applies-to-entire-locations), o [especificar lo que se incluye y excluye](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions).
    
    Información específica de las ubicaciones:
    - [Correo electrónico de Exchange y carpetas públicas de Exchange](retention-settings.md#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Sitios de SharePoint y cuentas de OneDrive](retention-settings.md#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Grupos de Microsoft 365](retention-settings.md#configuration-information-for-microsoft-365-groups)
    - [Skype Empresarial](retention-settings.md#configuration-information-for-skype-for-business)

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.
    
    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](retention-settings.md#settings-for-retaining-and-deleting-content) en esta página.

6. Complete la configuración y guarde los ajustes.
