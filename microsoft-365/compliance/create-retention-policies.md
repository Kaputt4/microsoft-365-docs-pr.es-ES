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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Utilice una directiva de retención para decidir de forma pro activa si desea retener el contenido, eliminarlo o ambas cosas, retener y luego eliminar el contenido, aplicar una única directiva a toda la organización o a lugares o usuarios específicos, y aplicar una directiva a todo el contenido o a los contenidos que cumplan determinadas condiciones.
ms.openlocfilehash: b509c1581f3b4120e9cf70e7603e56da86126539
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45092000"
---
# <a name="create-and-configure-retention-policies"></a>Crear y configurar directivas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Utilice una directiva de retención para decidir de forma pro activa si desea retener el contenido, eliminarlo o ambas cosas, retener y luego eliminar el contenido. 

Para obtener información sobre el funcionamiento de las directivas de retención, consulte [Más información sobre las directivas de retención.](retention-policies.md).

## <a name="before-you-begin"></a>Antes de empezar

Los miembros de su equipo de cumplimiento que crearán y administrarán las directivas de retención necesitan permisos para el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede conceder a los responsables de cumplimiento y a otros usuarios el acceso sin concederles todos los permisos de un administrador de espacio empresarial. Para conceder permisos para esta administración limitada, le recomendamos que agregue usuarios al grupo de roles **Administrador de cumplimiento normativo**. Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Estos permisos sólo son necesarios para crear y aplicar una directiva de retención. La persona que configura la directiva de retención no requiere acceso al contenido.

## <a name="create-and-configure-a-retention-policy"></a>Crear y configurar una directiva de retención

1. En el[centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione**Directivas d3** > **retención**.

2. Seleccione **Nueva directiva de retención**o edite una directiva de retención existente.

3. Para **Configuración**, especifique primero las opciones de configuración para retener y borrar el contenido. Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para obtener más información, consulte [Configuración para conservar y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página:
    
    A continuación, decida si la directiva de retención debe aplicarse a todos los contenidos o a los que cumplan determinadas condiciones. Para obtener más información sobre esta configuración avanzada de retención, consulte[Ajustes avanzados para identificar el contenido que cumple con condiciones específicas](#advanced-settings-to-identify-content-that-meets-specific-conditions)en esta página. 

4. En la página**Elegir ubicaciones**, seleccione si la directiva de retención debe aplicarse a todas las ubicaciones admitidas en su organización o si desea especificar las ubicaciones. Si escoge lugares específicos, también puede especificar las inclusiones y exclusiones. 
    
    Para Microsoft Teams: 
    - Debe seleccionar la opción de elegir lugares específicos si quiere borrar o retener los mensajes de los canales de los chats de Teams. Cuando seleccione cualquiera de estas opciones como ubicación, las otras ubicaciones se excluyen automáticamente porque una directiva de retención que incluye estos datos de Teams no puede incluir otras ubicaciones. 
    - Tenga en cuenta que**que para los mensajes de los canales de Teams**, se incluyen los mensajes de los canales estándar pero no de los[canales privados.](https://docs.microsoft.com/microsoftteams/private-channels). Actualmente, los canales privados no son compatibles con las directivas de retención.
    
    Para obtener más información sobre cómo elegir entre una directiva de retención para la organización o para lugares específicos, consulte[Aplicación de una directiva de retención a toda una organización o a lugares específicos en esta página.](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).
    
    Para obtener información específica sobre los **grupos de Office 365** y**Skype Empresarial** consulte las siguientes secciones,[Información de configuración de los grupos de Microsoft 365](#configuration-information-for-microsoft-365-groups) e [Información de configuración de Skype Empresarial](#configuration-information-for-skype-for-business).

5. Complete el asistente para guardar la configuración.

Cuando tiene más de una directiva de retención, consulte [Los principios de la retención, o ¿qué tiene prioridad? ](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)

### <a name="configuration-information-for-microsoft-365-groups"></a>Información de configuración para los grupos de Microsoft 365

Para conservar o eliminar el contenido de un grupo de Microsoft 365 (antes grupo Office 365), seleccione la ubicación de los **grupos de Office 365** cuando elija las ubicaciones para su directiva de conservación. Aunque un grupo Microsoft 365 tiene un buzón de Exchange, una directiva de retención que incluya toda la ubicación de**correo electrónico de Exchange** no incluirá el contenido de los buzones del grupo Microsoft 365. Además, aunque la ubicación **de correo electrónico de Exchangl** le permite inicialmente especificar un buzón de grupo para incluirlo o excluirlo, cuando intente guardar la directiva de retención, recibe un error que indique que "RemoteGroupMailbox" no es una selección válida para la ubicación de Exchange.

Una directiva de retención aplicada a un grupo de Microsoft 365 incluye tanto el buzón como el sitio del grupo. Una directiva de retención aplicada a un grupo Microsoft 365 protege los recursos creados por un grupo Microsoft 365, que incluye a Microsoft Teams.

### <a name="configuration-information-for-skype-for-business"></a>Información de configuración de Skype Empresarial

Al contrario que el correo electrónico de Exchange, no puede cambiar el estado de la ubicación de Skype en para incluir todos los usuarios, pero cuando active dicha ubicación y, elegirá manualmente los usuarios cuyas conversaciones quiera conservar:

![Elegir la ubicación de Skype para las directivas de retención](../media/skype-location-retention-policies.png)
  
Cuando seleccione **Elegir usuarios**, puede incluir rápidamente todos los usuarios seleccionando el cuadro **Nombre** en el encabezado de columna. Sin embargo, es importante entender que cada usuario tiene que contar con una inclusión específica en la Directiva. Por lo tanto, si incluye más de 1 000 usuarios, se aplicarán los límites señalados en la sección anterior. Seleccionar aquí todos los usuarios de Skype no es lo mismo que usar una directiva para toda la organización que pudiera incluir todos los usuarios de Skype de forma predeterminada. 
  
![Página Elegir usuarios de Skype](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.


## <a name="settings-for-retaining-and-deleting-content"></a>Configuración para retener y borrar el contenido

Al elegir las configuraciones para retener y eliminar contenido en su directiva de retención, ésta tendrá una de las siguientes configuraciones durante un período de tiempo determinado:

- Sólo para retención
- Retener y luego eliminar
- Sólo eliminar

### <a name="retaining-content-for-a-specific-period-of-time"></a>Retención del contenido durante un período de tiempo determinado

Cuando se configura una directiva de retención, se elige retener el contenido de forma indefinida o durante un número determinado de días, meses o años. El período de tiempo que se retiene el contenido se calcula en la antigüedad del contenido, no en el momento en que se aplica la Directiva de retención. Puede elegir si la antigüedad se basa en el momento en que se creó el contenido o (para OneDrive y SharePoint) en el momento en que se modificó por última vez.

Ejemplos:
  
- SharePoint: si desea conservar el contenido de una colección de sitios durante siete años desde que se modificó por última vez, y un documento de esa colección de sitios no se ha modificado en seis años, el documento se conservará sólo durante otro año si no se modifica. Si el documento se edita de nuevo, la edad del documento se calcula a partir de la nueva fecha de la última modificación, y se conservará durante otros siete años.
  
- Exchange: si desea conservar el contenido de un buzón durante siete años, y se envió un mensaje hace seis años, el mensaje se conservará sólo durante un año. En el caso del contenido de Exchange, la edad se basa en la fecha de recepción del correo electrónico entrante o en la fecha de envío del correo electrónico saliente. La conservación del contenido en función de la fecha de la última modificación sólo se aplica al contenido del sitio en OneDrive y SharePoint.
  
Al final del período de retención, usted elige si desea que el contenido se elimine de forma permanente:
  
![Página de configuración de retenciones](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminar el contenido que supera una antigüedad determinada

Una directiva de retención puede retener y, a continuación, eliminar contenido o eliminar contenido antiguo sin retenerlo.
  
Si su directiva de retención elimina contenido, es importante entender que el período de tiempo especificado para una directiva de retención se calcula a partir del tiempo desde que se creó o modificó el documento, no el tiempo desde que se asignó la directiva.
  
![Configuración de eliminación](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
Por ejemplo, supongamos que se crea una directiva de retención que borra el contenido después de tres años, y luego se asigna esa directiva a todas las cuentas de OneDrive, que contienen mucho contenido que fue creado hace cuatro o cinco años. En este caso, una gran cantidad de contenido se eliminará poco después de asignar la directiva de retención por primera vez. Por esta razón, es importante entender que una directiva de retención que borre el contenido puede tener un impacto considerable en su contenido. 
  
Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.
  
![Advertencia sobre la eliminación de contenido](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>Configuración avanzada para identificar el contenido que cumple con condiciones específicas

Puede aplicar una directiva de retención a todo el contenido de las ubicaciones que incluya, o bien, puede aplicar una directiva de retención solo al contenido que contenga determinadas palabras clave o [determinados tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
![Opciones avanzadas de retención](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>Identificar el contenido que contiene palabras clave específicas

Puede aplicar una directiva de retención sólo a los contenidos que cumplan con condiciones específicas, y luego tomar acciones de retención sólo sobre ese contenido. Las condiciones disponibles apoyan la aplicación de una directiva de retención de contenidos que contengan palabras o frases específicas. Puede restringir su consulta usando operadores de búsqueda como AND, OR y NOT. Para obtener más información sobre los operadores, vea [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
La compatibilidad para agregar propiedades susceptibles de búsqueda (por ejemplo, **asunto:**) estará disponible próximamente.
  
La retención basada en consultas usa el índice de búsqueda para identificar el contenido.
  
![Editor de consultas](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>Identificar el contenido que contiene información sensible

You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personal information, such as taxpayer identification numbers, social security numbers, or passport numbers.
  
![Página de tipos de información confidencial](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
Notas:
  
- La retención avanzada de información confidencial no se aplica a las carpetas públicas de Exchange o Skype Empresarial porque estas ubicaciones no admiten tipos de información confidencial.
    
- Exchange Online utiliza reglas de flujo de correo (también conocidas como reglas de transporte) para identificar la información confidencial, por lo que esto funciona sólo en los mensajes en tránsito, no en todos los artículos ya almacenados en un buzón. En el caso de Exchange Online, esto significa que las directivas de retención solo pueden identificar la información confidencial y realizar acciones de retención en los mensajes que se reciben **después** de que se aplique la directiva al buzón de correo. La retención basada en la consulta descrita en la sección anterior no tiene esta limitación porque utiliza el índice de búsqueda para identificar el contenido. 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>Aplicar una directiva de retención a toda la organización o a ubicaciones específicas

Puede aplicar fácilmente una directiva de retención a toda la organización, a ubicaciones completas o solo a determinados usuarios o ubicaciones.
  
### <a name="org-wide-policy"></a>Directiva para toda la organización

Una de las características más poderosas de una directiva de retención es que puede aplicarse a las ubicaciones a través de Microsoft 365, incluyendo:
  
- Correo electrónico de Exchange
    
- Colecciones de sitios de SharePoint
    
- Cuentas de OneDrive
    
- Grupos Microsoft 365 (se aplica al contenido del buzón del grupo y del sitio SharePoint asociado).
    
- Carpetas públicas de Exchange
    

![Opción Todas las ubicaciones](../media/retention-policies-all-locations.png)

Otras características importantes de una directiva de retención para toda la organización son:
  
- No hay ningún límite en el número de buzones o sitios que puede incluir la directiva.
    
- Para Exchange, todos los buzones creados tras la aplicación de la directiva la heredarán automáticamente.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>Una directiva para ubicaciones completas

Al elegir ubicaciones, puede incluir o excluir fácilmente una ubicación completa, como correo electrónico de Exchange o cuentas de OneDrive. Para ello, active o desactive el **estado** de esa ubicación. 
  
Al igual que una directiva para toda la organización, si una directiva se aplica a cualquier combinación de lugares enteros, no hay límite en el número de buzones o sitios que la directiva puede incluir. 

Por ejemplo, si la directiva incluye todo el correo electrónico de Exchange y todos los sitios de SharePoint, se incluirán todos los sitios y buzones, sea cual sea la cantidad. Y para Exchange, todos los buzones que se creen una vez que la directiva se haya aplicado, heredarán automáticamente la directiva.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Una directiva con inclusiones o exclusiones específicas

También puede aplicar una directiva de retención a usuarios específicos, grupos específicos de Microsoft 365 o sitios específicos. Para ello, active el **Estado** de esa ubicación y luego utilice los enlaces para incluir o excluir a usuarios específicos, grupos o sitios de Microsoft 365. 
  
Sin embargo, usando esta configuración, hay algunos límites cuando su directiva de retención incluye o excluye más de 1 000 ubicaciones específicas:
  
- Números máximos para la directiva de retención:
    - 1 000 buzones de usuario
    - Grupos de Microsoft 365 1 000.
    - 1 000 usuarios para chats privados de Teams
    - 100 sitios (OneDrive o SharePoint)

Hay un número máximo de directivas que se apoyan para un inquilino: 10 000. Estos elementos incluyen directivas de retención, directivas de etiquetas de retención y directivas de retención de aplicación automática.

Si es probable que sus directivas de retención estén sujetas a estas limitaciones, elija las opciones de configuración que se aplican a lugares enteros, o utilice una directiva para toda la organización.

## <a name="updating-retention-policies"></a>Actualización de las directivas de retención

Si edita una directiva de retención y el contenido ya está sujeto a la configuración original de su directiva de retención, la configuración actualizada se aplicará automáticamente a este contenido, además del contenido recién identificado.

Por lo general, esta actualización es bastante rápida, pero puede tardar varios días. Cuando la replicación de la directiva en todas las ubicaciones de Microsoft 365 se haya completado, verá que el estado de la directiva de retención en el centro de cumplimiento de Microsoft 365 cambia de **Activado (Pendiente)** a **Activado (Éxito)**.

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>Buscar los cmdlets de PowerShell para directivas de retención

Para usar los cmdlets de directivas de retención:
  
1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use estos cmdlets del Centro de seguridad y cumplimiento de Office 365:
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a>Bloquear una directiva de retención con PowerShell

Debe usar PowerShell si necesita usar el [Bloqueo de conservación](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) para cumplir con los requerimientos reglamentarios.

1. [Conéctese al Centro de seguridad y cumplimiento de Office 365 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Enumere sus directivas de retención y encuentre el nombre de la directiva que desea bloquear ejecutando`Get-RetentionCompliancePolicy`.
    
   ![Lista de las directivas de retención en PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. Para colocar un Bloqueo de conservación en una directiva de retención, ejecute`Set-RetentionCompliancePolicy` con el`RestrictiveRetention`parámetro fijado en true. Por ejemplo:

   ```powershell
   Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
   ```
   
   ![Parámetro RestrictiveRetention de PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
   Después de ejecutar ese cmdlet, elija**Sí a todo**:
    
   ![Preguntar para confirmar que desea bloquear una directiva de retención en PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Ahora, se coloca un bloqueo de preservación en la Directiva de retención. Si ejecuta `Get-RetentionCompliancePolicy`, el parámetro `RestrictiveRetention` se establece en True. Por ejemplo:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

![Directiva bloqueada con todos los parámetros visibles en PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

