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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Obtenga información sobre cómo administrar usuarios de correo en Exchange Online Protection (EOP), incluido el uso de la sincronización de directorios, el EAC y PowerShell para administrar usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658838"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Administrar usuarios de correo en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los usuarios de correo son el tipo fundamental de cuenta de usuario. Un usuario de correo tiene credenciales de cuenta en su organización de EOP independiente y puede tener acceso a los recursos (tener permisos asignados). La dirección de correo electrónico de un usuario de correo es externa (por ejemplo, en su entorno de correo electrónico local).

> [!NOTE]
> Al crear un usuario de correo, la cuenta de usuario correspondiente está disponible en el centro de administración de Microsoft 365. Cuando se crea una cuenta de usuario en el centro de administración de Microsoft 365, no se puede usar esa cuenta para crear un usuario de correo.

El método recomendado para crear y administrar usuarios de correo en EOP independiente es usar la sincronización de directorios, tal como se describe en la sección [usar la sincronización de directorios para administrar usuarios de correo](#use-directory-synchronization-to-manage-mail-users) , más adelante en este artículo.

Para organizaciones independientes de EOP con un pequeño número de usuarios, puede Agregar y administrar usuarios de correo en el centro de administración de Exchange (EAC) o en PowerShell independiente de EOP, tal como se describe en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el centro de administración de Exchange (EAC), consulte [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Al crear usuarios de correo en el PowerShell de EOP, es posible que se encuentre con limitaciones. Además, los cmdlets de PowerShell de EOP usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.

- Debe tener asignados permisos en Exchange Online Protection para poder realizar los procedimientos descritos en este artículo. En concreto, necesita los roles **creación de destinatarios de correo** (crear) y **destinatarios de correo** (modificar), que se asignan a los grupos de roles administración de destinatarios (administrador global) y  **destinatarios** de forma predeterminada. Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en los foros de Exchange. Visite el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Usar el centro de administración de Exchange para administrar usuarios de correo

### <a name="use-the-eac-to-create-mail-users"></a>Usar el EAC para crear usuarios de correo

1. En el EAC, vaya a contactos de **destinatarios** \>  .

2. Haga clic en **nuevo** ![ icono nuevo ](../../media/ITPro-EAC-AddIcon.png) . En la página **nuevo usuario de correo** que se abre, configure las siguientes opciones. La configuración marcada con un <sup>\*</sup> es obligatorio.

   - **Nombre**

   - **Iniciales**: inicial del segundo nombre de la persona.

   - **Apellidos**

   - <sup>\*</sup>**Nombre para mostrar**: de forma predeterminada, este cuadro muestra los valores de los cuadros **nombre**, **iniciales** y **Apellido** . Puede aceptar este valor o cambiarlo. El valor debe ser único y tener una longitud máxima de 64 caracteres.

   - <sup>\*</sup>**Alias**: escriba un alias único, con un máximo de 64 caracteres, para el usuario

   - **Dirección de correo electrónico externa**: escriba la dirección de correo electrónico del usuario. El dominio debe ser externo a su organización basada en la nube.

   - <sup>\*</sup>**Identificador de usuario**: escriba la cuenta que usará la persona para iniciar sesión en el servicio. El identificador de usuario consta de un nombre de usuario en el lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho.

   - <sup>\*</sup>**Nueva contraseña** y <sup>\*</sup> **Confirmar contraseña**: escriba y vuelva a escribir la contraseña de la cuenta. Compruebe que la contraseña cumple con los requisitos de longitud de la contraseña, complejidad e historial de la organización.

3. Cuando haya terminado, haga clic en **Guardar** para crear el usuario de correo.

### <a name="use-the-eac-to-modify-mail-users"></a>Usar el EAC para modificar usuarios de correo

1. En el EAC, vaya a **Destinatarios** \> **Contactos**.

2. Seleccione el usuario de correo que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-AddIcon.png) .

3. En la página de propiedades del usuario de correo que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.

   Cuando haya terminado, haga clic en **Guardar**.

#### <a name="general"></a>General

Use la ficha **General** para ver o cambiar la información básica sobre el usuario de correo.

- **Nombre**

- **Iniciales**

- **Apellidos**

- **Nombre para mostrar**: este nombre aparece en la libreta de direcciones de la organización, en las líneas para: y de: del correo electrónico, y en la lista de contactos del EAC. Este nombre no puede contener espacios en blanco antes o después del nombre para mostrar.

- **User ID**: es la cuenta de usuario de Microsoft 365. Este valor no se puede modificar aquí.

#### <a name="contact-information"></a>Información de contacto

Use la ficha **información de contacto** para ver o cambiar la información de contacto del usuario. La información de esta página se muestra en la libreta de direcciones.

- **Drogas**
- **Ciudad**
- **Estado o provincia**
- **Código postal**
- **País o región**
- **Teléfono del trabajo**
- **Teléfono móvil**
- **Fax**
- **Más opciones**

  - **Office**
  - **Teléfono particular**
  - **Página web**
  - **Notas**

#### <a name="organization"></a>Organización

Use la pestaña **organización** para registrar información detallada sobre el rol del usuario en la organización.

- **Cargo**
- **Departamento**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Usar el EAC para quitar usuarios de correo

1. En el EAC, vaya a **Destinatarios** \> **Contactos**.

2. Seleccione el usuario de correo que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Usar PowerShell para administrar usuarios de correo

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usar PowerShell independiente de EOP para ver los usuarios de correo

Para devolver una lista de Resumen de todos los usuarios de correo en EOP independiente, ejecute el siguiente comando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Para ver información detallada sobre un usuario de correo específico, reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute los siguientes comandos:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) y [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Usar PowerShell independiente de EOP para crear usuarios de correo

Para crear usuarios de correo en un PowerShell de EOP independiente, use la siguiente sintaxis:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Notas**:

- El parámetro _Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único. Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.
- Si no usa el parámetro _alias_ , el lado izquierdo del parámetro _MicrosoftOnlineServicesID_ se usa para el alias.
- Si no usa el parámetro _ExternalEmailAddress_ , el valor _MicrosoftOnlineServicesID_ se usa para la dirección de correo electrónico externa.

En este ejemplo se crea un usuario de correo con la siguiente configuración:

- El nombre es JeffreyZeng y el nombre para mostrar es Jeffrey Zeng.
- El nombre es Jeffrey y el apellido es Zeng.
- El alias es jeffreyz.
- La dirección de correo electrónico externa es jzeng@tailspintoys.com.
- El nombre de la cuenta es jeffreyz@contoso.onmicrosoft.com.
- La contraseña es Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Usar PowerShell independiente de EOP para modificar usuarios de correo

Para modificar los usuarios de correo existentes en PowerShell de EOP independiente, use la siguiente sintaxis:

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Usar PowerShell independiente de EOP para quitar usuarios de correo

Para quitar usuarios de correo en un PowerShell de EOP independiente, reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute el siguiente comando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

En este ejemplo se quita el usuario de correo de Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que los usuarios de correo se han creado, modificado o quitado correctamente en EOP independiente, use uno de los procedimientos siguientes:

- En el EAC, vaya a **Destinatarios** \> **Contactos**. Compruebe que el usuario de correo aparece (o no aparece en la lista). Seleccione el usuario de correo y vea la información en el panel de detalles o haga clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-AddIcon.png) para ver la configuración.

- En PowerShell independiente de EOP, ejecute el siguiente comando para comprobar que el usuario de correo aparece (o no aparece en la lista):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute los siguientes comandos para comprobar la configuración:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Usar la sincronización de directorios para administrar usuarios de correo

En EOP independiente, la sincronización de directorios está disponible para los clientes con Active Directory local. Puede sincronizar esas cuentas con Azure Active Directory (Azure AD), donde las copias de las cuentas se almacenan en la nube. Al sincronizar las cuentas de usuario existentes con Azure Active Directory, puede ver a esos usuarios en el panel **destinatarios** del centro de administración de Exchange (EAC) o en un PowerShell independiente de EOP.

**Notas**:

- Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local. Esto se debe a que la sincronización de directorios solo sincroniza los destinatarios de Active Directory local con la nube.

- Se recomienda usar la sincronización de directorios con las siguientes características:

  - Listas de remitentes **seguros de Outlook y listas de remitentes bloqueados**: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre el filtrado de correo no deseado en el servicio. Esto permite a los usuarios administrar su propia lista de remitentes seguros y la lista de remitentes bloqueados con entradas individuales de remitente y dominio. Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [use Directory based Edge blocking to Reject messages sent to invalid Recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Acceso de usuario final a cuarentena**: para obtener acceso a los mensajes en cuarentena, los destinatarios deben tener un identificador de usuario y una contraseña válidos en el servicio. Para obtener más información acerca de la cuarentena, vea [Buscar y liberar mensajes en cuarentena como un usuario](find-and-release-quarantined-messages-as-a-user.md).

  - **Reglas de flujo de correo (también conocidas como reglas de transporte)**: cuando se usa la sincronización de directorios, los usuarios y grupos existentes de Active Directory se cargan automáticamente en la nube y, a continuación, se pueden crear reglas de flujo de correo dirigidas a usuarios o grupos específicos sin tener que agregarlos manualmente en el servicio. Tenga en cuenta que los [grupos de distribución dinámicos](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) no se pueden sincronizar mediante la sincronización de directorios.

Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [¿Qué es la identidad híbrida con Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronización de directorios con Azure Active Directory Connect (AAD Connect)

1. Active la sincronización de directorios como se describe en [Azure ad Connect Sync: comprender y personalizar la sincronización](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Instale y configure un equipo local para ejecutar la conexión de AAD como se describe en [requisitos previos para Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Seleccione el tipo de instalación que se va a usar para Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizados](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticación de paso a través](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.

Una vez configurada la sincronización, asegúrese de comprobar que AAD Connect se está sincronizando correctamente. En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.
