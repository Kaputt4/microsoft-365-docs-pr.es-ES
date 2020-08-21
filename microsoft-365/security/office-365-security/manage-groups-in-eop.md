---
title: Administrar grupos en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Los administradores de organizaciones independientes de Exchange Online Protection (EOP) pueden obtener información sobre cómo crear, modificar y quitar grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange (EAC) y en PowerShell de Exchange Online Protection (EOP) independientes.
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826558"
---
# <a name="manage-groups-in-eop"></a>Administrar grupos en EOP

En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede crear, modificar y quitar los siguientes tipos de grupos:

- **Grupos de distribución**: una colección de usuarios de correo u otros grupos de distribución. Por ejemplo, Microsoft Teams u otros grupos ad hoc que necesiten recibir o enviar correo electrónico en un área común de interés. Los grupos de distribución están exclusivamente destinados a la distribución de mensajes de correo electrónico y no son entidades de seguridad (no pueden tener permisos asignados).

- **Grupos de seguridad habilitados para correo**: una colección de usuarios de correo y otros grupos de seguridad que necesitan permisos de acceso para los roles de administrador. Por ejemplo, es posible que desee conceder a un grupo específico de permisos de administrador de usuarios para que puedan configurar las opciones de protección contra correo electrónico no deseado y antimalware.

    > [!NOTE]
    >
    > - De forma predeterminada, los grupos de seguridad habilitados para correo nuevos rechazan los mensajes de remitentes externos (sin autenticar).
    >
    > - No agregue grupos de distribución a grupos de seguridad habilitados para correo.

Puede administrar los grupos en el centro de administración de Exchange (EAC) y en PowerShell independiente de EOP.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Al administrar grupos en PowerShell independiente de EOP, puede encontrarse con limitaciones. Los procedimientos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. En concreto, necesita el rol grupos de distribución, que se asigna a los grupos de roles OrganizationManagement (administradores globales) y RecipientManagement de forma predeterminada. Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Usar el centro de administración de Exchange para administrar grupos de distribución

### <a name="use-the-eac-to-create-groups"></a>Usar el EAC para crear grupos

1. En el EAC, vaya a grupos de **destinatarios** \> **Groups**.

2. Haga clic en **nuevo** ![ icono nuevo ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione una de las siguientes opciones:

   - **Grupo de distribución**

   - **Grupo de seguridad habilitado para correo**

3. En la página nuevo grupo que se abre, configure las siguientes opciones. La configuración marcada con un <sup>\*</sup> es obligatorio.

   - <sup>\*</sup>**Nombre para mostrar**: este nombre aparece en la libreta de direcciones de la organización, en la línea para: cuando se envía un correo electrónico a este grupo y en la lista **grupos** del EAC. El nombre para mostrar es obligatorio, debe ser único y debe ser fácil de usar para que los usuarios reconozcan lo que es.

   - <sup>\*</sup>**Alias**: Use este cuadro para escribir el nombre del alias para el grupo. El alias no puede superar los 64 caracteres y debe ser único. Cuando un usuario escribe el alias en la línea para de un mensaje de correo electrónico, se resuelve en el nombre para mostrar del grupo.

   - <sup>\*</sup>**Dirección de correo electrónico**: la dirección de correo electrónico consta del alias del lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho. De forma predeterminada, el valor de **alias** se usa para el valor de alias, pero puede cambiarlo. Para el valor dominio, haga clic en la lista desplegable y seleccione el dominio y el aceptado en su organización.

   - **Descripción**: esta descripción aparece en la libreta de direcciones y en el panel de detalles del EAC.

   - <sup>\*</sup>**Propietarios**: un propietario de grupo puede administrar la pertenencia a grupos. De forma predeterminada, la persona que crea un grupo pasa a ser el propietario. Todos los grupos deben tener al menos un propietario.

     Para agregar propietarios, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

     Para quitar un propietario, seleccione el propietario y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Miembros**: agregar y quitar miembros del grupo.

     Para agregar miembros, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

     Para quitar un miembro, selecciónelo y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Cuando haya terminado, haga clic en **Guardar** para crear el grupo de distribución.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Usar el EAC para modificar grupos de distribución

1. En el EAC, vaya a grupos de **destinatarios** \> **Groups**.

2. En la lista de grupos, seleccione el grupo de distribución o grupo de seguridad habilitado para correo que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-AddIcon.png) .

3. En la página de propiedades del grupo de distribución que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.

   Cuando haya terminado, haga clic en **Guardar**.

#### <a name="general"></a>General

Use esta ficha para ver o cambiar la información básica sobre el grupo.

- **Nombre para mostrar**: este nombre aparece en la libreta de direcciones, en la línea para cuando se envía un correo electrónico a este grupo, y en la **lista grupos**. El nombre para mostrar es obligatorio y debe ser sencillo para que los usuarios puedan identificarlo. También tiene que ser único en su dominio.

  Si ha implementado una directiva de nomenclatura de grupo, el nombre para mostrar tiene que cumplir al formato de nomenclatura definido por la directiva.

- **Alias**: es la parte de la dirección de correo electrónico que aparece a la izquierda del símbolo arroba (@). Si cambia el alias, la dirección SMTP primaria para el grupo también cambiará y contendrá el nuevo alias. Además, la dirección de correo electrónico con el alias anterior se mantendrá como dirección proxy para el grupo.

- **Dirección de correo electrónico**: la dirección de correo electrónico consta del alias del lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho. De forma predeterminada, el valor de **alias** se usa para el valor de alias, pero puede cambiarlo. Para el valor dominio, haga clic en la lista desplegable y seleccione el dominio y el aceptado en su organización.

- **Descripción**: esta descripción aparece en la libreta de direcciones y en el panel de detalles del EAC.

#### <a name="ownership"></a>Ownership

Use esta ficha para asignar propietarios de grupo. Un propietario de grupo puede administrar la pertenencia a grupos. De forma predeterminada, la persona que crea un grupo pasa a ser el propietario. Todos los grupos deben tener al menos un propietario.

Para agregar propietarios, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario y, a continuación, haga clic en **agregar >**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

Para quitar un propietario, seleccione el propietario y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Pertenencia

Use esta ficha para agregar o quitar miembros del grupo. No es necesario que los propietarios del grupo sean miembros del grupo.

Para agregar miembros, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

Para quitar un miembro, selecciónelo y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Usar el EAC para quitar grupos

1. En el EAC, vaya a grupos de **destinatarios** \> **Groups**.

2. En la lista de grupos, seleccione el grupo de distribución que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Usar PowerShell para administrar grupos

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Usar PowerShell independiente de EOP para ver grupos

Para obtener una lista resumida de todos los grupos de distribución y grupos de seguridad habilitados para correo en el PowerShell independiente de EOP, ejecute el siguiente comando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Para devolver la lista de miembros del grupo, reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) y [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Usar un PowerShell independiente de EOP para crear grupos

Para crear grupos de distribución o grupos de seguridad habilitados para correo en el PowerShell independiente de EOP, use la siguiente sintaxis:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Notas**:

- El parámetro _Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único. Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.

- Si no usa el parámetro _alias_ , se usa el parámetro _Name_ para el valor alias. Los espacios se quitan y los caracteres no admitidos se convierten en signos de interrogación (?).

- Si no usa el parámetro _PrimarySmtpAddress_ , el valor de alias se usa en el parámetro _PrimarySmtpAddress_ .

- Si no usa el parámetro _Type_ , el valor predeterminado es Distribution.

En este ejemplo se crea un grupo de distribución denominado administradores de TI con las propiedades especificadas.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Usar PowerShell independiente de EOP para modificar grupos

Para modificar grupos en PowerShell independiente de EOP, use la siguiente sintaxis:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

En este ejemplo se usan los cambios en la dirección SMTP principal (también denominada dirección de respuesta) del grupo empleados de Seattle en sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

En este ejemplo se reemplazan los miembros actuales del grupo de equipo de seguridad por Kitty Petersen y Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

En este ejemplo se agrega un nuevo usuario denominado Tyson Fawcett al grupo denominado equipo de seguridad y se conservan los miembros actuales del grupo.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) y [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Quitar un grupo mediante Windows PowerShell remoto

En este ejemplo se quita el grupo de distribución denominado administradores de ti.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente un grupo de distribución o un grupo de seguridad habilitado para correo, siga uno de estos pasos:

- En el EAC, vaya a grupos de **destinatarios** \> **Groups**. Compruebe que el grupo aparece (o no aparece en la lista) y compruebe el valor del **tipo de grupo** . Seleccione el grupo y vea la información en el panel de detalles o haga clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-AddIcon.png) para ver la configuración.

- En PowerShell independiente de EOP, ejecute el siguiente comando para comprobar que el grupo aparece (o no aparece en la lista):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando para comprobar la configuración:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Para ver los miembros del grupo, reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
