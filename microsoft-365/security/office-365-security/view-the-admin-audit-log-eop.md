---
title: Ver el registro de auditoría de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Los administradores pueden obtener información sobre cómo ver y buscar el registro de auditoría de administración en Exchange Online Protection (EOP) independiente.
ms.openlocfilehash: 171f3ec531b232ca796232ab26caefbee8afc75c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653502"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Ver el registro de auditoría de administrador en EOP independiente

En las organizaciones independientes de Exchange Online Protection (EOP) que no tienen buzones de Exchange Online, puede usar el centro de administración de Exchange (EAC) o PowerShell independiente de EOP para buscar y ver las entradas en el registro de auditoría de administrador.

El registro de auditoría de administrador registra acciones específicas, basadas en los cmdlets de PowerShell independientes de EOP, realizadas por administradores y usuarios a los que se les han asignado privilegios administrativos. Las entradas del registro de auditoría de administración proporcionan información sobre el cmdlet que se ejecutó, los parámetros que se usaron, quién ejecutó el cmdlet y qué objetos se vieron afectados.

> [!NOTE]
>
> - El registro de auditoría de administración está habilitado de forma predeterminada y no se puede deshabilitar.
>
> - El registro de auditoría de administrador no registra las acciones basadas en los cmdlets que comienzan con los verbos **Get**, **Search**o **Test**.
>
> - Las entradas de los registros de auditoría se conservan durante 90 días. Cuando una entrada tiene más de 90 días, se elimina

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. En concreto, necesita el rol registros de auditoría o registros de auditoría con permiso de vista, que se asignan a los grupos de roles ComplianceManagement, OrganizationManagement (administradores globales) y SecurityAdministrator de forma predeterminada. Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Usar el EAC para ver el registro de auditoría de administración

1. En el EAC, vaya a auditoría de **Administración de cumplimiento** \> **Auditing**y, a continuación, elija **ejecutar el registro de auditoría de administrador**.

2. En la página **Buscar cambios en los grupos de roles de administrador** que se abre, elija una fecha de **Inicio** y una **fecha de finalización** (el intervalo predeterminado es las últimas dos semanas) y, a continuación, elija **Buscar**. Todos los cambios de configuración realizados durante el período de tiempo especificado se muestran y se pueden ordenar, mediante la siguiente información:

   - **Fecha**: la fecha y la hora en que se realizó el cambio de configuración. La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).

   - **Cmdlet**: el nombre del cmdlet que se usó para realizar el cambio en la configuración.

   - **User**: el nombre de la cuenta de usuario del usuario que realizó el cambio en la configuración.

     Se mostrarán hasta 5000 entradas en varias páginas. Especifique un intervalo de fechas menor si necesita limitar los resultados. Si selecciona un resultado de la búsqueda individual, se mostrará la siguiente información adicional en el panel de detalles:

   - **Objeto modificado**: el objeto modificado por el cmdlet.

   - **Parameters (parámetro: valor)**: los parámetros del cmdlet que se usaron y cualquier valor especificado con el parámetro.

3. Si desea imprimir una entrada específica del registro de auditoría, elija el botón **Imprimir** en el panel de detalles.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Usar PowerShell independiente de EOP para ver el registro de auditoría de administrador

Puede usar la PowerShell independiente de EOP para buscar entradas de registro de auditoría que cumplan los criterios especificados. Utilice la sintaxis siguiente:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Notas**:

- Solo puede usar el parámetro _Parameters_ junto con el parámetro _cmdlets_ .

- El parámetro _ObjectIds_ filtra los resultados por el objeto modificado por el cmdlet. Un valor válido depende de cómo se representa el objeto en el registro de auditoría. Por ejemplo:

  - Nombre
  - Nombre distintivo canónico (por ejemplo, contoso.com/Users/Akia al-Zuhairi)

  Es probable que necesite usar otros parámetros de filtrado en este cmdlet para restringir los resultados e identificar los tipos de objetos que le interesan.

- El parámetro _userid_ filtra los resultados por el usuario que realizó el cambio (que ejecutó el cmdlet).

- Para los parámetros _startDate_ y _EndDate_ , si especifica un valor de fecha y hora sin una zona horaria, el valor es la hora universal coordinada (UTC). Para especificar un valor de fecha y hora para este parámetro, use una de las siguientes opciones:

  - Especifique el valor de fecha y hora en UTC; por ejemplo, "2016-05-06 14:30:00z".

  - Especifique el valor de fecha y hora como una fórmula que convierte la fecha y hora de la zona horaria local en UTC: por ejemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Para obtener más información, vea [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).

- De forma predeterminada, el cmdlet devuelve un máximo de 1.000 entradas de registro. Use el parámetro _resultsize_ para especificar hasta 250.000 entradas de registro. O bien, use el valor `Unlimited` para devolver todas las entradas.

En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:

- **Fecha de inicio**: 4 de agosto de 2019
- **Fecha de finalización**: 3 de octubre de 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Ver los detalles de las entradas del registro de auditoría

El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en la sección [contenido del registro de auditoría](#audit-log-contents) , más adelante en este tema. De los campos devueltos por el cmdlet, dos campos, **CmdletParameters** y **ModifiedProperties**, contienen información adicional que no se devuelve de forma predeterminada.

Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.

1. Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Cada entrada de registro de auditoría se almacena como un elemento de matriz en la variable `$Results` . Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz. Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz. Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.

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

|Field|Description|
|---|---|
|`RunspaceId`|Este campo se usa de forma interna en EOP.|
|`ObjectModified`|Este campo contiene el objeto modificado por el cmdlet especificado en el `CmdletName` campo.|
|`CmdletName`|Este campo contiene el nombre del cmdlet ejecutado por el usuario en el `Caller` campo.|
|`CmdletParameters`|Este campo contiene los parámetros que se especificaron cuando se ejecutó el cmdlet en el `CmdletName` campo. En este campo también se almacena (aunque no es visible en la salida predeterminada) el valor especificado con el parámetro (si existe).|
|`ModifiedProperties`|Este campo contiene las propiedades que se modificaron en el objeto en el `ObjectModified` campo. Además, en este campo se almacenan el valor anterior de la propiedad y el nuevo valor almacenado, aunque no están visibles en los resultados predeterminados.|
|`Caller`|Este campo contiene la cuenta de usuario del usuario que ejecutó el cmdlet en el `CmdletName` campo.|
|`ExternalAccess`|Este campo se usa de forma interna en EOP.|
|`Succeeded`|Este campo especifica si el cmdlet del `CmdletName` campo se ejecutó correctamente. El valor es `True` o `False` .|
|`Error`|Este campo contiene el mensaje de error generado si el cmdlet del `CmdletName` campo no se pudo completar correctamente.|
|`RunDate`|Este campo contiene la fecha y la hora en que se ejecutó el cmdlet en el `CmdletName` campo. La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).|
|`OriginatingServer`|Este campo indica el servidor en el que se ejecutó el cmdlet especificado en el `CmdletName` campo.|
|`ClientIP`|Este campo se usa de forma interna en EOP.|
|`SessionId`|Este campo se usa de forma interna en EOP.|
|`AppId`|Este campo se usa de forma interna en EOP.|
|`ClientAppId`|Este campo se usa de forma interna en EOP.|
|`Identity`|Este campo se usa de forma interna en EOP.|
|`IsValid`|Este campo se usa de forma interna en EOP.|
|`ObjectState`|Este campo se usa de forma interna en EOP.|
|
