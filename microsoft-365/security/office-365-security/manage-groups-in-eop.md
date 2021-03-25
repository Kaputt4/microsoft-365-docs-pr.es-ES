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
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Los administradores de organizaciones independientes de Exchange Online Protection (EOP) pueden aprender a crear, modificar y quitar grupos de distribución y grupos de seguridad habilitados para correo en el Centro de administración de Exchange (EAC) y en PowerShell independiente de Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205059"
---
# <a name="manage-groups-in-eop"></a>Administrar grupos en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede crear, modificar y quitar los siguientes tipos de grupos:

- **Grupos de distribución:** una colección de usuarios de correo u otros grupos de distribución. Por ejemplo, equipos u otros grupos ad hoc que necesitan recibir o enviar correo electrónico en un área común de interés. Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico y no son entidades de seguridad (no pueden tener permisos asignados).

- **Grupos de seguridad habilitados para correo:** una colección de usuarios de correo y otros grupos de seguridad que necesitan permisos de acceso para roles de administrador. Por ejemplo, es posible que desee conceder permisos de administrador a un grupo específico de usuarios para que puedan configurar la configuración contra correo no deseado y antimalware.

    > [!NOTE]
    >
    > - De forma predeterminada, los nuevos grupos de seguridad habilitados para correo rechazan mensajes de remitentes externos (no autenticados).
    >
    > - No agregue grupos de distribución a grupos de seguridad habilitados para correo.

Puede administrar grupos en el Centro de administración de Exchange (EAC) y en PowerShell independiente de EOP.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de administración de Exchange, vea [Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Al administrar grupos en PowerShell de EOP independiente, es posible que encuentre limitación. Los procedimientos de PowerShell de este artículo usan un método de procesamiento por lotes que da como resultado un retraso de propagación de unos minutos antes de que los resultados de los comandos estén visibles.

- Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol Grupos de  **distribución,** que está asignado a los grupos de roles Administración de la organización y **Administración** de destinatarios de forma predeterminada. Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Usar el Centro de administración de Exchange para administrar grupos de distribución

### <a name="use-the-eac-to-create-groups"></a>Usar el EAC para crear grupos

1. En el EAC, vaya a **Grupos de** \> **destinatarios**.

2. Haga **clic en** Nuevo icono Nuevo ![ ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione una de las siguientes opciones:

   - **Grupo de distribución**

   - **Grupo de seguridad habilitado para correo**

3. En la nueva página de grupo que se abre, configure las siguientes opciones. Se requiere una configuración <sup>\*</sup> marcada con una.

   - <sup>\*</sup>**Nombre para** mostrar: este nombre aparece en la libreta de direcciones de la organización,  en la línea Para: cuando se envía correo electrónico a este grupo y en la lista Grupos del EAC. El nombre para mostrar es obligatorio, debe ser único y debe ser fácil de usar para que las personas reconozcan lo que es.

   - <sup>\*</sup>**Alias:** use este cuadro para escribir el nombre del alias del grupo. El alias no puede superar los 64 caracteres y debe ser único. Cuando un usuario tipos el alias en la línea Para de un mensaje de correo electrónico, se resuelve en el nombre para mostrar del grupo.

   - <sup>\*</sup>**Dirección de correo** electrónico: la dirección de correo electrónico consta del alias en el lado izquierdo del símbolo at (@) y un dominio en el lado derecho. De forma predeterminada, el valor de **Alias** se usa para el valor de alias, pero puede cambiarlo. Para el valor de dominio, haga clic en el menú desplegable y seleccione y acepte el dominio en su organización.

   - **Descripción:** esta descripción aparece en la libreta de direcciones y en el panel Detalles del EAC.

   - <sup>\*</sup>**Propietarios:** un propietario de grupo puede administrar la pertenencia a grupos. De forma predeterminada, la persona que crea un grupo pasa a ser el propietario. Todos los grupos deben tener al menos un propietario.

     Para agregar propietarios, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

     Para quitar un propietario, seleccione el propietario y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Miembros:** agregar y quitar miembros de grupo.

     Para agregar miembros, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

     Para quitar un miembro, seleccione el miembro y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Cuando haya terminado, haga clic en **Guardar** para crear el grupo de distribución.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Usar el EAC para modificar grupos de distribución

1. En el EAC, vaya a **Grupos de** \> **destinatarios**.

2. En la lista de grupos, seleccione el grupo de distribución o el grupo de seguridad habilitado para correo que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-AddIcon.png) .

3. En la página de propiedades del grupo de distribución que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.

   Cuando haya terminado, haga clic en **Guardar**.

#### <a name="general"></a>General

Use esta pestaña para ver o cambiar información básica sobre el grupo.

- **Nombre para** mostrar: este nombre aparece en la libreta de direcciones, en la línea Para cuando se envía correo electrónico a este grupo y en la **lista Grupos**. El nombre para mostrar es obligatorio y debe ser sencillo para que los usuarios puedan identificarlo. También tiene que ser único en su dominio.

  Si ha implementado una directiva de nomenclatura de grupo, el nombre para mostrar tiene que cumplir al formato de nomenclatura definido por la directiva.

- **Alias:** esta es la parte de la dirección de correo electrónico que aparece a la izquierda del símbolo at (@). Si cambia el alias, la dirección SMTP primaria para el grupo también cambiará y contendrá el nuevo alias. Además, la dirección de correo electrónico con el alias anterior se mantendrá como dirección proxy para el grupo.

- **Dirección de correo** electrónico: la dirección de correo electrónico consta del alias en el lado izquierdo del símbolo at (@) y un dominio en el lado derecho. De forma predeterminada, el valor de **Alias** se usa para el valor de alias, pero puede cambiarlo. Para el valor de dominio, haga clic en el menú desplegable y seleccione y acepte el dominio en su organización.

- **Descripción:** esta descripción aparece en la libreta de direcciones y en el panel Detalles del EAC.

#### <a name="ownership"></a>Ownership

Use esta pestaña para asignar propietarios de grupos. Un propietario de grupo puede administrar la pertenencia a grupos. De forma predeterminada, la persona que crea un grupo pasa a ser el propietario. Todos los grupos deben tener al menos un propietario.

Para agregar propietarios, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario y, a continuación, haga clic **en Agregar ->**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

Para quitar un propietario, seleccione el propietario y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Pertenencia

Use esta pestaña para agregar o quitar miembros del grupo. Los propietarios de grupos no necesitan ser miembros del grupo.

Para agregar miembros, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) . En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**. Repita este paso tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

Para quitar un miembro, seleccione el miembro y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Usar el EAC para quitar grupos

1. En el EAC, vaya a **Grupos de** \> **destinatarios**.

2. En la lista de grupos, seleccione el grupo de distribución que desea quitar y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Usar PowerShell para administrar grupos

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Usar PowerShell de EOP independiente para ver grupos

Para devolver una lista resumida de todos los grupos de distribución y grupos de seguridad habilitados para correo en PowerShell de EOP independiente, ejecute el siguiente comando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Para devolver la lista de miembros del grupo, reemplace por el nombre, alias o dirección de correo electrónico del grupo \<GroupIdentity\> y ejecute el siguiente comando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-Recipient](/powershell/module/exchange/get-recipient) y [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Usar PowerShell de EOP independiente para crear grupos

Para crear grupos de distribución o grupos de seguridad habilitados para correo en PowerShell de EOP independiente, use la sintaxis siguiente:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Notas**:

- El _parámetro Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único. Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.

- Si no usa el parámetro _Alias,_ se usará el parámetro _Name_ para el valor de alias. Los espacios se quitan y los caracteres no compatibles se convierten en signos de interrogación (?).

- Si no usa el parámetro _PrimarySmtpAddress,_ el valor de alias se usa en el _parámetro PrimarySmtpAddress._

- Si no usa el parámetro _Type,_ el valor predeterminado es Distribution.

En este ejemplo se crea un grupo de distribución denominado Administradores de TI con las propiedades especificadas.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Usar PowerShell de EOP independiente para modificar grupos

Para modificar grupos en PowerShell de EOP independiente, use la siguiente sintaxis:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

En este ejemplo se cambia la dirección SMTP principal (también denominada dirección de respuesta) del grupo Empleados de Seattle a sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

En este ejemplo se reemplazan los miembros actuales del grupo equipo de seguridad por Kitty Petersen y Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

En este ejemplo, se agrega un nuevo usuario denominado Tyson Fawcett al grupo denominado Equipo de seguridad mientras se conservan los miembros actuales del grupo.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) y [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Quitar un grupo mediante una Windows PowerShell

En este ejemplo se quita el grupo de distribución denominado Administradores de TI.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente un grupo de distribución o un grupo de seguridad habilitado para correo, siga estos pasos:

- En el EAC, vaya a **Grupos de** \> **destinatarios**. Compruebe que el grupo aparece (o no aparece) y compruebe el **valor tipo de** grupo. Seleccione el grupo y vea la información en el panel Detalles o haga clic **en Editar** icono Editar para ver ![ la ](../../media/ITPro-EAC-AddIcon.png) configuración.

- En PowerShell de EOP independiente, ejecute el siguiente comando para comprobar que el grupo aparece (o no aparece):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Reemplace por el nombre, alias o dirección de correo electrónico del grupo y \<GroupIdentity\> ejecute el siguiente comando para comprobar la configuración:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Para ver los miembros del grupo, reemplace por el nombre, alias o dirección de correo electrónico del grupo y \<GroupIdentity\> ejecute el siguiente comando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```