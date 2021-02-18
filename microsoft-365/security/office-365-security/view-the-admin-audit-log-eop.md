---
title: Ver el registro de auditoría de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Los administradores pueden aprender a ver y buscar en el registro de auditoría de administración en Exchange Online Protection (EOP) independiente.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286482"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Ver el registro de auditoría de administrador en EOP independiente

**Se aplica a**
- [Exchange Online Protection independiente](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el Centro de administración de Exchange (EAC) o EOP PowerShell independiente para buscar y ver entradas en el registro de auditoría de administración.

El registro de auditoría de administración registra acciones específicas, basadas en cmdlets de PowerShell de EOP independientes, realizadas por administradores y usuarios a los que se han asignado privilegios administrativos. Las entradas del registro de auditoría de administración proporcionan información sobre qué cmdlet se ejecutó, qué parámetros se usaron, quién ejecutó el cmdlet y qué objetos se vieron afectados.

> [!NOTE]
>
> - El registro de auditoría de administración está habilitado de forma predeterminada y no se puede deshabilitar.
>
> - El registro de auditoría de administración no registra acciones basadas en cmdlets que comienzan con los verbos **Get**, **Search** o **Test**.
>
> - Las entradas de los registros de auditoría se conservan durante 90 días. Cuando una entrada tiene más de 90 días, se elimina

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el Centro de administración de Exchange, consulte [El Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. Específicamente, necesita  el rol  Registros de auditoría o Registros de auditoría de solo  vista, que se asignan de forma predeterminada a los grupos de roles Administración de la **organización,** Administración de cumplimiento y Administrador de seguridad. Para obtener más información, vea [Permisos en EOP](feature-permissions-in-eop.md) independiente y Usar el EAC modificar la lista [de miembros en grupos de roles.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obtener información acerca de los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este artículo, consulte [Métodos abreviados](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online.

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Usar el EAC para ver el registro de auditoría de administración

1. En el EAC, vaya a Auditoría **de** administración de cumplimiento y, a continuación, elija \> Ejecutar el informe de registro de auditoría **de administración.**

2. En la **página Buscar** cambios en grupos de roles de administrador que se abre, elija una fecha de inicio y una fecha de finalización **(el** intervalo predeterminado son las últimas dos semanas) y, **a** continuación, **elija Buscar**. Todos los cambios de configuración realizados durante el período de tiempo especificado se muestran y se pueden ordenar, mediante la siguiente información:

   - **Fecha:** fecha y hora en que se realizó el cambio de configuración. La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).

   - **Cmdlet:** el nombre del cmdlet que se usó para realizar el cambio de configuración.

   - **Usuario:** nombre de la cuenta de usuario del usuario que realizó el cambio de configuración.

     Se mostrarán hasta 5000 entradas en varias páginas. Especifique un intervalo de fechas menor si necesita limitar los resultados. Si selecciona un resultado de la búsqueda individual, se mostrará la siguiente información adicional en el panel de detalles:

   - **Objeto modificado:** el objeto modificado por el cmdlet.

   - **Parámetros (Parameter:Value):** los parámetros de cmdlet que se usaron y cualquier valor especificado con el parámetro.

3. Si desea imprimir una entrada específica del registro de auditoría, elija el botón **Imprimir** en el panel de detalles.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Usar EOP PowerShell independiente para ver el registro de auditoría de administración

Puede usar EOP PowerShell independiente para buscar entradas de registro de auditoría que cumplan los criterios especificados. Utilice la sintaxis siguiente:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Notas**:

- Solo puede usar el _parámetro Parameters_ junto con el _parámetro Cmdlets._

- El _parámetro ObjectIds_ filtra los resultados por el objeto modificado por el cmdlet. Un valor válido depende de cómo se represente el objeto en el registro de auditoría. Por ejemplo:

  - Nombre
  - Nombre distintivo canónico (por ejemplo, contoso.com/Users/Akia Al-Zuhairi)

  Es probable que necesite usar otros parámetros de filtrado en este cmdlet para restringir los resultados e identificar los tipos de objetos que le interesan.

- El _parámetro UserIds_ filtra los resultados por el usuario que realizó el cambio (que ejecutó el cmdlet).

- Para los _parámetros StartDate_ y _EndDate,_ si especifica un valor de fecha y hora sin una zona horaria, el valor se encuentra en hora universal coordinada (UTC). Para especificar un valor de fecha y hora para este parámetro, use una de las siguientes opciones:

  - Especifique el valor de fecha y hora en UTC; por ejemplo, "2016-05-06 14:30:00z".

  - Especifique el valor de fecha y hora como una fórmula que convierta la fecha y hora de la zona horaria local a UTC: por ejemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Para obtener más información, vea [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).

- El cmdlet devuelve un máximo de 1.000 entradas de registro de forma predeterminada. Use el _parámetro ResultSize_ para especificar hasta 250 000 entradas de registro. O bien, use el valor `Unlimited` para devolver todas las entradas.

En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:

- **Fecha de inicio:** 4 de agosto de 2019
- **Fecha de** finalización: 3 de octubre de 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Ver los detalles de las entradas del registro de auditoría

El cmdlet **Search-AdminAuditLog** devuelve los [](#audit-log-contents) campos descritos en la sección contenido del registro de auditoría más adelante en este artículo. De los campos devueltos por el cmdlet, dos campos, **CmdletParameters** y **ModifiedProperties**, contienen información adicional que no se devuelve de forma predeterminada.

Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.

1. Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Cada entrada del registro de auditoría se almacena como un elemento de matriz en la variable `$Results` . Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz. Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz. Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.

    ```PowerShell
    $Results[4]
    ```

3. El comando anterior devuelve la entrada de registro almacenada en el elemento de matriz 4. Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** para esta entrada de registro, utilice los siguientes comandos.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Para ver el contenido de los campos **CmdletParameters** o **ModifiedParameters** en otra entrada de registro, cambie el índice del elemento de matriz.

## <a name="audit-log-contents"></a>Contenido del registro de auditoría

Todas las entradas del registro de auditoría contienen la información que se describe en la tabla siguiente. El registro de auditoría contiene una o varias entradas de registro de auditoría.

****

|Field|Descripción|
|---|---|
|`RunspaceId`|EOP usa este campo internamente.|
|`ObjectModified`|Este campo contiene el objeto modificado por el cmdlet especificado en el `CmdletName` campo.|
|`CmdletName`|Este campo contiene el nombre del cmdlet ejecutado por el usuario en el `Caller` campo.|
|`CmdletParameters`|Este campo contiene los parámetros que se especificaron al ejecutar el cmdlet `CmdletName` del campo. En este campo también se almacena (aunque no es visible en la salida predeterminada) el valor especificado con el parámetro (si existe).|
|`ModifiedProperties`|Este campo contiene las propiedades que se modificaron en el objeto del `ObjectModified` campo. Además, en este campo se almacenan el valor anterior de la propiedad y el nuevo valor almacenado, aunque no están visibles en los resultados predeterminados.|
|`Caller`|Este campo contiene la cuenta de usuario del usuario que ejecutó el cmdlet en el `CmdletName` campo.|
|`ExternalAccess`|EOP usa este campo internamente.|
|`Succeeded`|Este campo especifica si el cmdlet del campo `CmdletName` se ejecutó correctamente. El valor es uno `True` o `False` .|
|`Error`|Este campo contiene el mensaje de error generado si el cmdlet del campo no se pudo `CmdletName` completar correctamente.|
|`RunDate`|Este campo contiene la fecha y la hora en que se ha ejecutado el cmdlet `CmdletName` del campo. La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).|
|`OriginatingServer`|Este campo indica el servidor en el que se ha ejecutado el cmdlet especificado `CmdletName` en el campo.|
|`ClientIP`|EOP usa este campo internamente.|
|`SessionId`|EOP usa este campo internamente.|
|`AppId`|EOP usa este campo internamente.|
|`ClientAppId`|EOP usa este campo internamente.|
|`Identity`|EOP usa este campo internamente.|
|`IsValid`|EOP usa este campo internamente.|
|`ObjectState`|EOP usa este campo internamente.|
|
