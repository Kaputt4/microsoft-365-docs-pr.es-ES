---
title: Conservar o eliminar contenido automáticamente mediante directivas de retención
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Use una directiva de retención para controlar de forma eficaz el contenido que los usuarios generan con el correo electrónico, los documentos y las conversaciones. Conserve lo que desee y libérese de lo que no quiere.
ms.openlocfilehash: c8e6540e42b6692c980b96cec859a137d866c965
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793838"
---
# <a name="create-and-configure-retention-policies"></a>Crear y configurar directivas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use una directiva de retención con el fin de administrar los datos de su organización. Para ello, decida proactivamente si se retiene el contenido, se elimina o si primero se retiene y después se elimina.

Una directiva de retención le permite hacerlo de manera muy eficaz. Solo tiene que asignar la misma configuración de retención a nivel del contenedor al contenido de ese contenedor, que lo hereda de forma automática. Por ejemplo, todos los elementos de los sitios de SharePoint, todos los mensajes de correo electrónico de los buzones de Exchange de los usuarios, todos los mensajes de canal de los equipos que se usan con Microsoft Teams. Si no está seguro sobre si debe usar una directiva de retención o una etiqueta de retención, consulte [Directivas de retención y etiquetas de retención](retention.md#retention-policies-and-retention-labels).

Para obtener más información sobre las directivas de retención y cómo funciona la retención en Microsoft 365, vea [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).

> [!NOTE]
> La información de esta página es para los administradores de cumplimiento normativo. Si no es administrador y quiere entender cómo se configuraron las directivas de retención para las aplicaciones que usa, póngase en contacto con el departamento de soporte técnico, el departamento de TI o el administrador. Si ve mensajes sobre directivas de retención en los chats de Teams y en los mensajes de canal, puede serle útil revisar [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y modificar directivas de retención. Si no está iniciando sesión como administrador global, consulte la [información de permisos de administración del ciclo de vida de datos](get-started-with-data-lifecycle-management.md#permissions-for-retention-policies-and-retention-labels).

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

Cuando tiene más de una directiva de retención y cuando también usa etiquetas de retención, consulte [Los principios de retención o ¿qué tiene prioridad?](retention.md#the-principles-of-retention-or-what-takes-precedence) para comprender el resultado cuando se aplican varias configuraciones de retención al mismo contenido.

### <a name="retention-policy-for-teams-locations"></a>Directiva de retención para ubicaciones de Teams

> [!NOTE]
> Las directivas de retención son compatibles con [canales compartidos](/MicrosoftTeams/shared-channels). Cuando se configuran las opciones de retención para la ubicación de los **mensajes del canal de Teams**, si un equipo tiene canales compartidos, éstos heredan las opciones de retención de su equipo primario.
> 
> Las directivas de retención también admiten registros de datos de llamada recién creados, que son mensajes generados por el sistema que contienen [metadatos para reuniones y llamadas](/MicrosoftTeams/ediscovery-investigation#teams-metadata). Sin embargo, los registros de datos de llamada para mensajes de canal privado se incluyen en la ubicación de **chats de Teams** , en lugar de en la ubicación de **mensajes de canal privado de Teams** .

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), seleccione **Administración** >  del ciclo de vida de datos **Directivas de retención** de **Microsoft 365** > .

2. Seleccione **Nueva directiva de retención** para iniciar la configuración de **Crear directiva de retención** y asigne un nombre a la nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar **chats de Teams** , pero no mensajes de **canal de Teams**. 
    
    - Si ha elegido **Estática**: en la página **Elegir ubicaciones para aplicar la directiva**, seleccione una o más ubicaciones para Teams:
        - **mensajes de canal de Teams**: mensajes de chats de canales estándar y compartidos, y reuniones de canales estándar y compartidos, pero no de [canales privados](/microsoftteams/private-channels) que tienen su propia ubicación de directiva.
        - **Chats de Teams**: mensajes de chats privados 1:1, chats de grupo, chats de reuniones y chat con usted mismo.
        - **Mensajes del canal privado de Teams**: Mensajes de chats de canales privados y reuniones de canales privados. Si selecciona esta opción, no podrá seleccionar las demás ubicaciones de Teams en la misma directiva de retención.
        
       De forma predeterminada, [se seleccionan todos los equipos y todos los usuarios](retention-settings.md#a-policy-that-applies-to-entire-locations), pero puede refinar esto al seleccionar la [**Elegir** y **Excluir** opciones](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions).

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

   You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](retention-settings.md#settings-for-retaining-and-deleting-content).

6. Complete la configuración y guarde los ajustes.

Para obtener instrucciones sobre cuándo usar directivas de retención para Teams y conocer la experiencia del usuario final, vea [Administrar directivas de retención para Microsoft Teams](/microsoftteams/retention-policies) en la documentación de Teams.

Para obtener detalles técnicos sobre el funcionamiento de la retención de Teams, incluidos los elementos de los mensajes admitidos para la retención e información sobre los períodos de tiempo con tutoriales de ejemplo, vea [Más información sobre la retención de Microsoft Teams](retention-policies-teams.md).

#### <a name="known-configuration-issues-for-teams-retention-policies"></a>Problemas de configuración conocidos para las directivas de retención de Teams

- Aunque puede seleccionar la opción para iniciar el período de retención en el que se modificaron los elementos por última vez, siempre se usa el valor **Cuando se crearon los elementos**. Para los mensajes que se editan, se guarda una copia del mensaje original con la marca de tiempo original para identificar cuándo se creó este mensaje antes de editar, y el mensaje después de editar tiene una marca de tiempo más reciente.

- Al seleccionar **Editar** para la ubicación de los chats de Teams puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

- Para incluir los registros de datos de llamada recién creados para los mensajes de canal privado de Teams, debe seleccionar la ubicación de **chats de Teams** , en lugar de la ubicación de **mensajes de canal privado de Teams** .


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

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), seleccione **Administración** >  del ciclo de vida de datos **Directivas de retención** de **Microsoft 365** > .

2. Seleccione **Nueva directiva de retención** para crear una nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar mensajes de usuario de **Yammer** , pero no **mensajes de la comunidad de Yammer**. 
    
    - Si ha elegido **Estática**: en la página **Elegir ubicaciones para aplicar la directiva**, alterne entre una o ambas ubicaciones para Yammer: **mensajes de la comunidad de Yammer** y **mensajes de usuario de Yammer**.
        
        De forma predeterminada se seleccionan todas las comunidades y los usuarios, pero también puede restringir los resultados al especificar qué comunidades y usuarios desea incluir o excluir.
        
        Para los mensajes del usuario de Yammer: 
        - Si deja la opción predeterminada en **Todos los usuarios**, no se incluirá a los usuarios invitados de Azure B2B. 
        - Si selecciona **Editar** para **Todos los usuarios**, puede aplicar una directiva de retención a los usuarios externos si conoce sus cuentas.

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido. 
    
    You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](retention-settings.md#settings-for-retaining-and-deleting-content).

6. Complete la configuración y guarde los ajustes.

Para obtener detalles técnicos sobre cómo funciona la retención para Yammer, incluidos los elementos de los mensajes que se admiten para la información de retención y tiempo con tutoriales de ejemplo, consulte [Información sobre la retención para Yammer](retention-policies-yammer.md).

#### <a name="known-configuration-issues-for-yammer-retention-policies"></a>Problemas de configuración conocidos para las directivas de retención de Yammer

- Aunque puede seleccionar la opción para iniciar el período de retención en el que se modificaron los elementos por última vez, siempre se usa el valor **Cuando se crearon los elementos**. Para los mensajes que se editan, se guarda una copia del mensaje original con la marca de tiempo original para identificar cuándo se creó este mensaje antes de editar, y el mensaje después de editar tiene una marca de tiempo más reciente.

- Al seleccionar **Editar** para la ubicación de los mensajes del usuario de Yammer, es posible que pueda ver a los invitados y a los usuarios sin buzón de correo. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Directivas de retención adicionales que se necesitan para admitir Yammer

Yammer is more than just community messages and private messages. To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.

Esta ubicación también incluirá archivos que se cargan en comunidades de Yammer. Estos archivos se almacenan en el sitio de SharePoint conectado a grupos para la comunidad de Yammer.

Es posible que una directiva de retención que se aplique a los sitios de SharePoint pueda eliminar un archivo al que se haga referencia en un mensaje de Yammer antes de que dicho mensaje sean eliminado. En este caso, el archivo seguirá mostrándose en el mensaje de Yammer, pero cuando los usuarios lo seleccionen, obtendrán el error "Archivo no encontrado". Este comportamiento no es específico para las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Directivas de retención para otras ubicaciones fuera de Teams y Yammer

Use las siguientes instrucciones para crear directivas de retención que apliquen a cualquiera de estos servicios:

- Correo electrónico y carpetas públicas de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), seleccione **Administración** >  del ciclo de vida de datos **Directivas de retención** de **Microsoft 365** > .

2. Seleccione **Nueva directiva de retención** para iniciar la configuración de **Crear directiva de retención** y asigne un nombre a la nueva directiva de retención.

3. En la página **Elegir el tipo de directiva de retención que quiere crear**, seleccione **Adaptable** o **Estática**, en función de lo que haya elegido en las instrucciones de [Antes de empezar](#before-you-begin). Si aún no ha creado ámbitos adaptables, podrá seleccionar **Adaptable**, pero no habrá ámbitos adaptables que seleccionar, por lo tanto no podrá acabar de configurar con esta opción. Las directivas adaptables no admiten las ubicaciones de las carpetas públicas de Exchange o Skype Empresarial.

4. Según el ámbito seleccionado:
    
    - Si ha elegido **Adaptable**: en la página **Elegir ámbitos y ubicaciones de directivas adaptables**, seleccione **Agregar ámbitos** y seleccione uno o varios ámbitos adaptables que se hayan creado. A continuación, seleccione una o más ubicaciones. Las ubicaciones que podrá seleccionar dependen de los [tipos de ámbito](retention-settings.md#configuration-information-for-adaptive-scopes) que se hayan agregado. Por ejemplo, si solo ha agregado un tipo de ámbito de **Usuario**, podrá seleccionar **correo electrónico de Exchange** , pero no **sitios de SharePoint**. 
    
    - Si ha elegido **Estático**: en la página **Elegir ubicaciones**, active o desactive cualquiera de las ubicaciones excepto las de Teams y Yammer. Para cada ubicación, puede dejar de forma predeterminada [aplicar la directiva a toda la ubicación](retention-settings.md#a-policy-that-applies-to-entire-locations), o [especificar lo que se incluye y excluye](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions).
    
    Información específica de las ubicaciones:
    - [Correo electrónico de Exchange y carpetas públicas de Exchange](retention-settings.md#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Sitios de SharePoint y cuentas de OneDrive](retention-settings.md#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Grupos de Microsoft 365](retention-settings.md#configuration-information-for-microsoft-365-groups)
    - [Skype Empresarial](retention-settings.md#configuration-information-for-skype-for-business)

5. En la página **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.
    
    You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](retention-settings.md#settings-for-retaining-and-deleting-content) on this page.

6. Complete la configuración y guarde los ajustes.

## <a name="how-long-it-takes-for-retention-policies-to-take-effect"></a>Tiempo que tardan en aplicarse las directivas de retención

Cuando se crea y envía una directiva de retención, ésta puede tardar hasta siete días en aplicarse:
  
![Diagrama de cuándo surte efecto la directiva de retención.](../media/retention-policy-timings.png)

En primer lugar, la directiva de retención debe distribuirse a las ubicaciones seleccionadas y luego aplicarse al contenido. Se puede comprobar el estado de distribución de la directiva de retención seleccionándola en la página **Directivas de retención** del portal del centro de cumplimiento de Microsoft Purview. En el panel flotante, si el estado es **(Error)** y en los detalles de las ubicaciones aparece un mensaje que indica que se está tardando más de lo esperado en implementar la directiva o en intentar volver a implementarla, intente ejecutar el comando de PowerShell [Set-AppRetentionCompliancePolicy](/powershell/module/exchange/set-appretentioncompliancepolicy)o el [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) para volver a intentar la distribución de directivas:

1. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

2. Ejecute uno de los siguientes comandos:
    
    - Para las ubicaciones de directiva **mensajes de canal privado de Teams**, **mensajes de usuario de Yammer** y **mensajes de la comunidad Yammer**:
    
        ```PowerShell
        Set-AppRetentionCompliancePolicy -Identity <policy name> -RetryDistribution
        ```
    
    - Para todas las demás ubicaciones de directiva, como **correo electrónico de Exchange**, **sitios de SharePoint**, y **mensajes de canal de Teams**:
    
        ```PowerShell
        Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
        ```

## <a name="updating-retention-policies"></a>Actualización de las directivas de retención

Cuando la configuración de la directiva de retención ya se haya aplicado al contenido, se aplicará automáticamente un cambio en la configuración de la directiva a este contenido y al contenido nuevo.

Algunas opciones de configuración no se pueden cambiar después de crear y guardar la directiva, entre las que se incluyen el nombre de la directiva de retención, el tipo de ámbito (adaptable o estático) y la configuración de retención, excepto el período de retención.

## <a name="next-steps"></a>Pasos siguientes

Si algunos elementos de Exchange, SharePoint, OneDrive o Grupos de Microsoft 365 necesitan una configuración de retención diferente de la configuración de directiva de retención que ha configurado, [crear etiquetas de retención para estas excepciones](create-retention-labels-data-lifecycle-management.md).

Sin embargo, si busca gestionar elementos de gran valor para requisitos empresariales, legales o de mantenimiento de registros normativos, [use el plan de archivos para crear y administrar etiquetas de retención](file-plan-manager.md).
