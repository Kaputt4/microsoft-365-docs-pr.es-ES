---
title: Buscar los datos de chat de Teams de usuarios locales
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Los administradores pueden usar las herramientas de eDiscovery en Microsoft 365 para buscar y exportar datos de chat de Teams para usuarios locales en una implementación híbrida de Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdd142783313418c8c65c04f9b5e344ff325ec2c
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61871459"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Buscar los datos de chat de Teams de usuarios locales

Si su organización tiene una implementación híbrida de Exchange (o si su organización sincroniza una organización de Exchange local con Office 365) y ha habilitado Microsoft Teams, los usuarios locales pueden usar la aplicación de chat de Teams para su comunicación mediante mensajería instantánea. Para un usuario basado en la nube, los datos del chat de Teams (también llamados *chats 1x1 o 1xN*) se guardan en su buzón principal basado en la nube. Cuando un usuario local utiliza la aplicación de chat de Teams, sus mensajes de chat no se pueden almacenar en su buzón principal, el cual se encuentra en el entorno local. Para evitar esta limitación, Microsoft ha lanzado una nueva función que crea un área de almacenamiento basada en la nube, de tal manera que usted pueda usar las herramientas de eDiscovery para buscar y exportar los datos de chat de Teams de usuarios locales.
  
A continuación, se presentan los requisitos y limitaciones para habilitar el almacenamiento basado en la nube para usuarios locales:
  
- Las cuentas de usuario en su servicio de directorio local (como Active Directory) deben estar sincronizadas con Azure Active Directory, el servicio de directorio de Microsoft 365. Esto significa que se crea una cuenta de usuario de correo en Microsoft 365 y se asocia a un usuario cuyo buzón principal se encuentra en la organización local.

- Al usuario cuyo buzón principal se encuentre en la organización local se le debe asignar una licencia de Microsoft Teams y un mínimo de una licencia de Exchange Online Plan 1.

- Si su organización no tiene una implementación híbrida de Exchange, debe sincronizar el esquema de Exchange local con Azure Active Directory. En caso contrario, corre el riesgo de crear buzones duplicados basados en la nube en Exchange Online para aquellos usuarios que tengan un buzón en su organización de Exchange local.

- Solo los datos de chat de Teams asociados a un usuario local se almacenan en el área de almacenamiento basada en la nube. Un usuario local no puede acceder de ninguna manera a esta área de almacenamiento.

> [!NOTE]
> Las conversaciones del canal de Teams siempre se almacenan en el buzón de correo en la nube asociado al equipo, por lo que puede buscar conversaciones del canal. Para obtener más información sobre la búsqueda de conversaciones en los canales de los equipos, consulte [Búsqueda Microsoft Teams y Grupos de Microsoft 365](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Cómo funciona

Si un usuario habilitado para Microsoft Teams tiene un buzón en el entorno local y su cuenta de usuario o identidad se ha sincronizado en la nube, Microsoft crea un almacenamiento basado en la nube para asociarlo a los datos de chat 1xN de Teams del usuario local. Los datos de chat de Teams de los usuarios locales se indexan para la búsqueda. Esto le permite utilizar la Búsqueda de contenido (y las búsquedas asociadas a los casos de Core eDiscovery y eDiscovery avanzado) para buscar, previsualizar y exportar los datos de chat de Teams de los usuarios locales. También puede usar los cmdlets de **\*ComplianceSearch** en el PowerShell del Centro de cumplimiento y seguridad para buscar los datos de charts de Teams de usuarios locales.
  
El siguiente gráfico muestra el flujo de trabajo de cómo los datos del chat de Teams para los usuarios locales están disponibles para buscar, previsualizar y exportar.
  
![Almacenamiento basado en la nube para usuarios locales en Microsoft Teams.](../media/EHAMShard1.png)
  
Además de esta nueva capacidad, también puede usar las herramientas de eDiscovery para buscar, previsualizar y exportar el contenido de Teams en el sitio SharePoint basado en la nube y el buzón de Exchange asociado con los datos de cada equipo de Microsoft y el chat de 1xN Teams en el buzón de Exchange Online para los usuarios basados en la nube.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Buscar el contenido de chat de Teams de los usuarios locales

Aquí le explicamos cómo usar la Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar datos de chat de Teams para usuarios locales. También puede usar la herramienta de búsqueda en el Centro de eDiscovery para buscar datos de chat para usuarios locales.
  
1. En el Centro de cumplimiento de Microsoft 365, vaya a **Búsqueda de contenido**.

2. En la pestaña **Búsquedas**, haga clic en **Nueva búsqueda** y asigne un nombre a la nueva búsqueda.

3. En la página **Ubicaciones**, establezca el botón de alternancia en **Activado** para los buzones de Exchange.

4. Para buscar contenido de Teams para usuarios específicos (incluidos los usuarios locales), seleccione **Elegir usuario, grupos o equipos** y elija usuarios específicos para incluir en la búsqueda. Si no enumera usuarios específicos, la búsqueda incluirá a todos los usuarios, incluidos los usuarios locales.

5. Asegúrese de que la casilla **Agregar contenido de la aplicación para usuarios locales** esté activada. Esto garantiza que se buscará el almacenamiento de bases en la nube para los usuarios locales.

    ![Active la casilla “Agregar contenido de aplicaciones de Office para usuarios locales” en la página Asistente para ubicaciones.](../media/EHAMShardCheckBox.png)

6. En la página **Definir las condiciones de búsqueda**, cree una consulta de palabra clave y agregue condiciones a la consulta de búsqueda si es necesario. Para buscar sólo los datos de los chats de Teams, puede añadir la siguiente consulta en el cuadro **Palabras clave**:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Envíe y ejecute la búsqueda. Se puede obtener una vista previa de cualquier resultado de la búsqueda de usuarios locales como de cualquier otro resultado de búsqueda. También puede exportar los resultados de la búsqueda (incluyendo cualquier dato del chat de los equipos) a un archivo PST. Para más información, consulte lo siguiente:

    - [Crear una búsqueda](content-search.md)

    - [Vista previa de los resultados de búsqueda](preview-ediscovery-search-results.md)

    - [Exportar resultados de la búsqueda](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Usar PowerShell para buscar datos de chat de Teams de usuarios locales

Puede usar los cmdlets **New-ComplianceSearch** en el PowerShell del Centro de seguridad y cumplimiento para buscar datos de chat de Teams de usuarios locales. Como se explicó anteriormente, no es necesario presentar una solicitud de soporte para utilizar PowerShell para buscar datos de chat de Teams para usuarios locales.
  
1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando de PowerShell para crear una búsqueda de contenido que busque datos de chat de Teams de usuarios locales.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    El parámetro *IncludeUserAppContent* se utiliza para especificar el almacenamiento basado en la nube del usuario o los usuarios que se especifican en el parámetro *ExchangeLocation*. El parámetro *AllowNotFoundExchangeLocationsEnabled* permite buscar el almacenamiento basado en la nube de los usuarios locales. Cuando se utiliza el valor `$true` de este parámetro, la búsqueda no intenta validar la existencia del buzón antes de que se ejecute. Esto es necesario para buscar el almacenamiento basado en la nube de los usuarios locales, ya que este almacenamiento basado en la nube no se resuelve como un buzón de correo basado en la nube.

    El siguiente ejemplo busca los chats de Teams que contienen la palabra clave "redstone" en el almacenamiento basado en la nube de Sara Davis, quien es una usuaria local de la organización Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Después de crear una búsqueda, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda.
  
Para más información sobre el uso de estos cmdlets, consulte:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemas conocidos

- Actualmente, puede buscar, previsualizar y exportar los datos de chat de Teams de usuarios locales. También puede poner en retención los datos de chat de Teams de usuarios locales asociados con un caso de Core eDiscovery o eDiscovery avanzado, y aplicar una directiva de retención para los chats o mensajes de canales de Teams de usuarios locales. Sin embargo, en este momento, no se puede aplicar una directiva de retención para otras ubicaciones de contenido (como los buzones de Exchange y los sitios de SharePoint) para los usuarios locales.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Tengo que enviar una solicitud de soporte para buscar mensajes de chat de usuarios locales?**

No. Esta característica está activada para todas las organizaciones. En el pasado, hubiera tenido que ponerse en contacto con el Soporte técnico de Microsoft, pero ya no hace falta.
  
 **¿Pueden las herramientas de eDiscovery buscar datos de chat antiguos de Teams para usuarios locales antes de que esta característica se habilitara de forma predeterminada para todas las organizaciones?**
  
Microsoft comenzó a almacenar los datos de chat de Teams de los usuarios locales el 31 de enero de 2018. Por lo tanto, si la identidad de un usuario local de Teams se ha sincronizado entre su Active Directory local y Azure Active Directory en Microsoft 365 desde esta fecha, sus datos de chat de Teams se almacenarán en la nube y se podrán buscar con herramientas de eDiscovery.

 **¿Los usuarios locales necesitan una licencia para almacenar sus datos de chat de Teams en la nube?**
  
Sí. Para que un usuario local pueda almacenar sus datos de chat de Teams en un almacenamiento basado en la nube, se debe asignar al usuario una licencia de Microsoft Teams y una licencia de un plan de Exchange Online en Office 365 (o Microsoft 365).

**¿Dónde se ubica el almacenamiento en la nube de usuarios locales?**
  
Los datos del chat de Teams se almacenan en la Ubicación de datos preferida (PDL) para un On-Premises User. La PDL respeta tanto los entornos Single-Geo y los Multi-Geo. Para más información, vea [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

**¿Existe el riesgo de perder los datos del chat de los equipos si el buzón del usuario se migra a la nube?**
  
No. Cuando migre el buzón principal de un usuario local a la nube, los datos de chat de Teams de ese usuario se migrarán a su nuevo buzón principal basado en la nube.
  
 **¿Puedo aplicar una retención de eDiscovery o las directivas de retención a los usuarios locales?**
  
Sí. Puede aplicar políticas de retención o retención de eDiscovery a los chats y mensajes de canales de los usuarios locales. Pero para conservar el contenido de Teams para los usuarios locales, se debe asignar una licencia de Exchange Online Plan 2 a un usuario local.
