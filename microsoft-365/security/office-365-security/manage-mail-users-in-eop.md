---
title: Administrar usuarios de correo en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Obtenga información sobre cómo administrar usuarios de correo en Exchange Online Protection (EOP), incluido el uso de la sincronización de directorios, EAC y PowerShell para administrar usuarios.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a0dc1c0c343be77c6d6f713ee6b68a08a4fe5be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289918"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Administrar usuarios de correo en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los usuarios de correo son el tipo fundamental de cuenta de usuario. Un usuario de correo tiene credenciales de cuenta en su organización independiente de EOP y puede tener acceso a los recursos (tener permisos asignados). La dirección de correo electrónico de un usuario de correo es externa (por ejemplo, en su entorno de correo electrónico local).

> [!NOTE]
> Al crear un usuario de correo, la cuenta de usuario correspondiente está disponible en el Centro de administración de Microsoft 365. Al crear una cuenta de usuario en el Centro de administración de Microsoft 365, no puede usar esa cuenta para crear un usuario de correo.

El método recomendado para crear y administrar usuarios de correo en [](#use-directory-synchronization-to-manage-mail-users) EOP independiente es usar la sincronización de directorios como se describe en la sección Usar sincronización de directorios para administrar usuarios de correo más adelante en este artículo.

Para las organizaciones de EOP independientes con un número reducido de usuarios, puede agregar y administrar usuarios de correo en el Centro de administración de Exchange (EAC) o en EOP PowerShell independiente, como se describe en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el Centro de administración de Exchange (EAC), consulte Centro de administración [de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Al crear usuarios de correo en PowerShell de EOP, es posible que se encuentre con una limitación. Además, los cmdlets de PowerShell de EOP usan un método de procesamiento por lotes que provoca un retraso de propagación de unos minutos antes de que se puedan ver los resultados de los comandos.

- Deberá tener asignados permisos en Exchange Online Protection para poder realizar los procedimientos descritos en este artículo. En concreto, necesita los roles Creación de destinatarios de correo **(crear)** y Destinatarios de correo **(modificar),** que se asignan a los grupos de roles Administración de la organización **(administradores** globales) y Administración de destinatarios de forma predeterminada.  Para obtener más información, vea [Permisos en EOP](feature-permissions-in-eop.md) independiente y Usar el EAC modificar la lista [de miembros en grupos de roles.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obtener información acerca de los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este artículo, vea [Métodos abreviados](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online.

> [!TIP]
> ¿Problemas? Solicite ayuda en los foros de Exchange. Visite el foro [de Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Usar el Centro de administración de Exchange para administrar usuarios de correo

### <a name="use-the-eac-to-create-mail-users"></a>Usar el EAC para crear usuarios de correo

1. En el EAC, vaya a **Contactos de** \> **destinatarios**

2. Haga **clic en el** icono Nuevo ![ ](../../media/ITPro-EAC-AddIcon.png) nuevo. En la **página Nuevo usuario de** correo que se abre, configure las siguientes opciones. Se requiere una configuración <sup>\*</sup> marcada con una.

   - **Nombre**

   - **Iniciales:** inicial del medio de la persona.

   - **Apellidos**

   - <sup>\*</sup>**Nombre para** mostrar: de forma predeterminada, este cuadro muestra los valores de los cuadros **Nombre,** Iniciales **y Apellidos.** Puede aceptar este valor o cambiarlo. El valor debe ser único y tiene una longitud máxima de 64 caracteres.

   - <sup>\*</sup>**Alias:** escriba un alias único, con hasta 64 caracteres, para el usuario

   - **Dirección de correo electrónico externa:** escriba la dirección de correo electrónico del usuario. El dominio debe ser externo a la organización basada en la nube.

   - <sup>\*</sup>**Id. de** usuario: escriba la cuenta que usará la persona para iniciar sesión en el servicio. El identificador de usuario consta de un nombre de usuario en el lado izquierdo del símbolo (@) (@) y un dominio en el lado derecho.

   - <sup>\*</sup>**Nueva contraseña y** <sup>\*</sup> **Confirmar contraseña:** escriba y vuelva a escribir la contraseña de la cuenta. Compruebe que la contraseña cumple con los requisitos de longitud, complejidad e historial de la contraseña de su organización.

3. Cuando haya terminado, haga clic en **Guardar** para crear el usuario de correo.

### <a name="use-the-eac-to-modify-mail-users"></a>Usar el EAC para modificar usuarios de correo

1. En el EAC, vaya a **Destinatarios** \> **Contactos**.

2. Seleccione el usuario de correo que desea modificar y, a continuación, haga clic **en el icono** Editar ![ ](../../media/ITPro-EAC-AddIcon.png) edición.

3. En la página de propiedades de usuario de correo que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.

   Cuando haya terminado, haga clic en **Guardar**.

#### <a name="general"></a>General

Use la **pestaña General** para ver o cambiar información básica sobre el usuario de correo.

- **Nombre**

- **Iniciales**

- **Apellidos**

- **Nombre para** mostrar: este nombre aparece en la libreta de direcciones de su organización, en las líneas Para: y De: del correo electrónico y en la lista de contactos del EAC. Este nombre no puede contener espacios en blanco antes o después del nombre para mostrar.

- **Identificador de** usuario: esta es la cuenta del usuario en Microsoft 365. Este valor no se puede modificar aquí.

#### <a name="contact-information"></a>Información de contacto

Use la **pestaña Información de** contacto para ver o cambiar la información de contacto del usuario. La información de esta página se muestra en la libreta de direcciones.

- **Street**
- **Ciudad**
- **Estado o provincia**
- **Código postal**
- **País o región**
- **Teléfono del trabajo**
- **Teléfono móvil**
- **Fax**
- **Más opciones**

  - **Office**
  - **Teléfono del hogar**
  - **Página web**
  - **Notas**

#### <a name="organization"></a>Organización

Use la **pestaña** Organización para registrar información detallada sobre el rol del usuario en la organización.

- **Cargo**
- **Departamento**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Usar el EAC para quitar usuarios de correo

1. En el EAC, vaya a **Destinatarios** \> **Contactos**.

2. Seleccione el usuario de correo que desea quitar y, a continuación, haga clic **en el icono** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Quitar.

## <a name="use-powershell-to-manage-mail-users"></a>Usar PowerShell para administrar usuarios de correo

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usar EOP PowerShell independiente para ver usuarios de correo

Para devolver una lista resumida de todos los usuarios de correo en EOP PowerShell independiente, ejecute el siguiente comando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Para ver información detallada sobre un usuario de correo específico, reemplace por el nombre, alias o nombre de cuenta del usuario de correo y ejecute \<MailUserIdentity\> los siguientes comandos:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) y [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Usar EOP PowerShell independiente para crear usuarios de correo

Para crear usuarios de correo en PowerShell de EOP independiente, use la siguiente sintaxis:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Notas**:

- El _parámetro Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único. Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.
- Si no usa el parámetro _Alias,_ se usa el lado izquierdo del parámetro _MicrosoftOnlineServicesID_ para el alias.
- Si no usa el parámetro _ExternalEmailAddress,_ se usa el valor _MicrosoftOnlineServicesID_ para la dirección de correo electrónico externa.

En este ejemplo se crea un usuario de correo con la siguiente configuración:

- El nombre es JeffreyZeng y el nombre para mostrar es Jeffrey Zeng.
- El nombre es Jeffrey y el apellido es Zeng.
- El alias es jeffreyz.
- La dirección de correo electrónico externa es jzeng@tailspintoys.com.
- El nombre de cuenta es jeffreyz@contoso.onmicrosoft.com.
- La contraseña es Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Usar EOP PowerShell independiente para modificar usuarios de correo

Para modificar usuarios de correo existentes en EOP PowerShell independiente, use la siguiente sintaxis:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Usar EOP PowerShell independiente para quitar usuarios de correo

Para quitar usuarios de correo en PowerShell de EOP independiente, reemplace por el nombre, alias o nombre de cuenta del usuario de correo \<MailUserIdentity\> y ejecute el siguiente comando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

En este ejemplo se quita el usuario de correo de Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente usuarios de correo en EOP independiente, use uno de los procedimientos siguientes:

- En el EAC, vaya a **Destinatarios** \> **Contactos**. Compruebe que el usuario de correo aparece (o no aparece). Seleccione el usuario de correo y vea la  información en el panel Detalles o haga clic en el icono Editar ![ para ver la ](../../media/ITPro-EAC-AddIcon.png) configuración.

- En EOP PowerShell independiente, ejecute el siguiente comando para comprobar que el usuario de correo aparece (o no aparece):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Reemplace por el nombre, alias o nombre de cuenta del usuario de correo y ejecute los siguientes \<MailUserIdentity\> comandos para comprobar la configuración:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Usar la sincronización de directorios para administrar usuarios de correo

En EOP independiente, la sincronización de directorios está disponible para los clientes con Active Directory local. Puede sincronizar esas cuentas con Azure Active Directory (Azure AD), donde las copias de las cuentas se almacenan en la nube. Cuando sincronice sus cuentas de usuario **existentes** con Azure Active Directory, puede ver esos usuarios en el panel Destinatarios del Centro de administración de Exchange (EAC) o en EOP PowerShell independiente.

**Notas**:

- Si usa la sincronización de directorios para administrar los destinatarios, aún puede agregar y administrar usuarios en el Centro de administración de Microsoft 365, pero no se sincronizarán con su Active Directory local. Esto se debe a que la sincronización de directorios solo sincroniza destinatarios de su Active Directory local con la nube.

- Se recomienda usar la sincronización de directorios con las siguientes características:

  - **Listas de remitentes seguros de Outlook** y listas de remitentes bloqueados: cuando se sincronizan con el servicio, estas listas tendrán prioridad sobre el filtrado de correo no deseado en el servicio. Esto permite a los usuarios administrar su propia lista de remitentes seguros y la lista de remitentes bloqueados con entradas individuales de remitente y dominio. Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Bloqueo perimetral basado en directorios (DBEB):** para obtener más información acerca de DBEB, vea Usar bloqueo perimetral basado en directorios para rechazar mensajes [enviados a destinatarios no válidos.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Acceso de usuario final a** cuarentena: para obtener acceso a sus mensajes en cuarentena, los destinatarios deben tener un identificador de usuario y una contraseña válidos en el servicio. Para obtener más información acerca de la cuarentena, vea Buscar y [liberar mensajes en cuarentena como un usuario.](find-and-release-quarantined-messages-as-a-user.md)

  - Reglas de flujo de correo (también conocidas como reglas de **transporte):** al usar la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, a continuación, puede crear reglas de flujo de correo destinadas a usuarios o grupos específicos sin tener que agregarlos manualmente al servicio. Tenga en cuenta que los [grupos de distribución dinámicos](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) no se pueden sincronizar mediante la sincronización de directorios.

Obtenga los permisos necesarios y prepárese para la sincronización de directorios, como se describe en ¿Qué es la identidad [híbrida con Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizar directorios con Azure Active Directory Connect (AAD Connect)

1. Active la sincronización de directorios tal como se describe en [la sincronización de Azure AD Connect: comprenda y personalice la sincronización.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Instale y configure un equipo local para ejecutar AAD Connect como se describe en [Requisitos previos para Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Seleccione el tipo de instalación que se va a usar para Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizados](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticación de paso a través](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.

Después de configurar la sincronización, asegúrese de comprobar que AAD Connect se está sincronizando correctamente. En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.
