---
title: Ejecutar un informe de grupo de roles de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP) independiente. Este informe registra cuándo un administrador agrega miembros a grupos de roles de administrador o los quita.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166632"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Ejecutar un informe de grupo de roles de administrador en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](https://go.microsoft.com/fwlink/?linkid=2148611)

En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, cuando un administrador agrega o quita miembros de grupos de roles administrativos, el servicio registra cada repetición. Para obtener más información acerca de los grupos de roles en EOP independiente, vea [Permisos en EOP independiente.](feature-permissions-in-eop.md)

Al ejecutar un informe de grupo de roles de administrador en el Centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de roles afectados, quién cambió la pertenencia al grupo de roles y cuándo y qué actualizaciones de pertenencia se realizaron. Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el Centro de administración de Exchange, consulte [El Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Deberá tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. Específicamente, necesita  el rol  Registros de auditoría o Registros de auditoría de solo  vista, que se asignan de forma predeterminada a los grupos de roles Administración de la **organización,** Administración de cumplimiento y Administrador de seguridad. Para obtener más información, vea [Permisos en EOP](feature-permissions-in-eop.md) independiente y Usar el EAC modificar la lista [de miembros en grupos de roles.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obtener información acerca de los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este artículo, vea [Métodos abreviados](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online.

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar el EAC para ejecutar un informe de grupo de roles de administrador

Ejecute el informe del grupo de roles de administrador para buscar los cambios en los grupos de roles de administración dentro de un período de tiempo determinado.

1. En el EAC, vaya a Auditoría **de** administración de cumplimiento y, a continuación, elija Ejecutar un informe de \> grupo de roles de **administrador.**

2. En la **página Buscar cambios en grupos de roles** de administrador que se abre, configure las siguientes opciones:

   - **Fecha de inicio** y **fecha de finalización:** escriba un intervalo de fechas. De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.

   - **Seleccionar grupos de roles:** de forma predeterminada, se buscan todos los grupos de roles. Para filtrar los resultados por grupos de roles específicos, haga clic **en Seleccionar grupos de roles.** En el cuadro de diálogo que aparece, seleccione un grupo de roles y haga clic **en agregar ->**. Repita este paso tantas veces como sea necesario y, a continuación, haga clic en **Aceptar** cuando haya terminado.

3. Cuando haya terminado, haga clic en **Buscar.**

Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.

## <a name="monitor-changes-to-role-group-membership"></a>Supervisión de cambios en la pertenencia a grupos de funciones

Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.

Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:

> 27/1/2018 16:43 <br> Administrador <br> Miembros actualizados: Administrator;annb,florencef;pilarp <br> 06/2/2018 10:09 AM <br> Administrador <br> Miembros actualizados: Administrator;annb;florencef;pilarp;tonip <br> 19/2/2018 14:12 <br> Administrador <br> Miembros actualizados: Administrator;annb;florencef;tonip

En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:

- El 06/2/2018, agregaron el usuario tonip.
- El 19/2/2018, quitaron al usuario pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Usar Exchange Online PowerShell independiente para buscar entradas de registro de auditoría

Puede usar Exchange Online PowerShell para buscar entradas de registro de auditoría que cumplan los criterios especificados. Para obtener una lista de criterios de búsqueda, vea criterios de búsqueda [Search-AdminAuditLog](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Este procedimiento usa el cmdlet **Search-AdminAuditLog** y muestra los resultados de la búsqueda en Exchange Online PowerShell. Utilice este cmdlet cuando tenga que devolver un conjunto de resultados que supera los límites definidos en el cmdlet **New-AdminAuditLogSearch** o en los Informes de auditoría de la EAC.

Para buscar en el registro de auditoría los criterios que especifique, utilice la siguiente sintaxis.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> De manera predeterminada, el cmdlet **Search-AdminAuditLog** devuelve un máximo de 1.000 entradas de registro. Use el _parámetro ResultSize_ para especificar hasta 250 000 entradas de registro. O bien, use el valor `Unlimited` para devolver todas las entradas.

En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:

- **Fecha de** inicio: 08/04/2018
- **Fecha de** finalización: 03/10/2018
- **Id. de usuario:** `davids` , `chrisd` , `kima`
- **Cmdlets**: **Set-Mailbox**
- **Parámetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

En este ejemplo se buscan los cambios realizados en un buzón específico. Esto resulta útil si está resolviendo problemas o necesita proporcionar información para una investigación. Se utilizan los siguientes criterios:

- **Fecha de** inicio: 01/05/2018
- **Fecha de** finalización: 03/10/2018
- **Id. de** objeto: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Si las búsquedas devuelven muchas entradas de registro, se recomienda usar el procedimiento proporcionado en **Usar Exchange Online PowerShell** para buscar entradas de registro de auditoría y enviar resultados a un destinatario más adelante en este artículo. El procedimiento de esta sección envía un archivo XML como dato adjunto de correo electrónico a los destinatarios que especifique, de modo que será más fácil extraer los datos que interesan.

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Ver los detalles de las entradas del registro de auditoría

El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en [el contenido del registro de auditoría.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Entre los campos que devuelve el cmdlet, **CmdletParameters** y **ModifiedProperties** contienen información adicional que no se puede ver de manera predeterminada.

Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación. O bien, puede usar el procedimiento de Usar **Exchange Online PowerShell** para buscar entradas de registro de auditoría y enviar resultados a un destinatario más adelante en este artículo para crear un archivo XML.

En este procedimiento se aplican los siguientes conceptos:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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
