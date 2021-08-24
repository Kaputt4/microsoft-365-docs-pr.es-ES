---
title: Configuración del Programador para Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configuración del Programador para Microsoft 365.
ms.openlocfilehash: c47c866748fd4635c581acb3737e67bc72658538
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502800"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configuración del Planificador para Microsoft 365

Los administradores de inquilinos deben configurar un buzón del asistente programador y obtener licencias del programador para los organizadores de reuniones para habilitar el Programador para Microsoft 365 servicio. 

## <a name="licensing"></a>Licencias

Más información: [Programador para Microsoft 365 licencias](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)

>[Nota] Los asistentes a la reunión no necesitan un Programador ni Microsoft 365 licencia. <br>El buzón del asistente programador no requiere una Microsoft 365 o una licencia de programador.

## <a name="prerequisites"></a>Requisitos previos

| Requisito previo | Descripción |
|-------------------|-------------|
|Un buzón de asistente de programador para el inquilino |Un Exchange de recursos de tipo de equipo que actúa como buzón del asistente programador para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana. Todos los correos electrónicos enviados Cortana se conservan en el buzón de correo Cortana del inquilino en función de la directiva de retención. El buzón del asistente del programador normalmente se denomina "Cortana" o "programador de Cortana" ya que todos los correos electrónicos del asistente se firmarán Cortana.</br> - Crear un tipo de equipo Exchange buzón de recursos</br> - Asigne al buzón el nombre para mostrar y la dirección SMTP principal "Cortana" o <cortana@yourdomain.com> "Cortana <cortana.scheduler@yourdomain.com> programador".</br>**Nota:** El buzón del asistente programador no requiere una Microsoft 365 o una licencia de programador.|
|Buzón de correo Exchange Online |Los organizadores de reuniones deben tener un buzón Exchange Online y un calendario normalmente como parte de su Microsoft 365 licencia. Además, los organizadores de reuniones deben tener una licencia de Programador. La licencia del programador permite al asistente del programador usar el buzón y el calendario del organizador de la reunión para programar reuniones para ellos.</br></br> Vea Scheduler for Microsoft 365 para obtener información sobre licencias y precios.  </br></br>**Nota:** Los asistentes a la reunión no necesitan un Programador ni Microsoft 365 licencia. Los asistentes a la reunión pueden ser internos o externos al inquilino. Los asistentes a la reunión solo necesitan acceso a una dirección de correo electrónico.|


## <a name="setting-up-the-scheduler-assistant-mailbox"></a>Configurar el buzón del asistente del programador

El buzón del asistente del programador es Exchange de tipo de equipamiento que no requiere una licencia Microsoft 365 o Scheduler. El nombre para mostrar y la dirección SMTP principal del buzón deben contener Cortana ya que todos los correos electrónicos del asistente del programador se firmarán Cortana (es decir, "Cortana" o <cortana@yourdomain.com> "programador de <cortana.scheduler@yourdomain.com> Cortana"). Después de crear el buzón del asistente del programador, debe designar el buzón como buzón del asistente del programador. Después de designar el buzón del asistente del programador, Cortana estará disponible para programar reuniones en nombre de los usuarios.



- Use el Centro de administración de Microsoft 365 para crear un buzón de usuario. Se recomienda una directiva de retención de 30 días. 
- Use el nombre Cortana en la dirección SMTP principal del buzón. Nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' se recomiendan.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designar el buzón como asistente del programador

Después de crear un buzón único para Cortana scheduler, debe designar el buzón Microsoft 365 forma formal. Después de designar el buzón Cortana programador, estará disponible para programar reuniones en nombre de los usuarios.

#### <a name="connect-to-powershell"></a>Conectar a PowerShell

Use el Centro de administración de Microsoft 365 para crear un buzón de usuario. Se recomienda una directiva de retención de 30 días.
Use el nombre Cortana en la dirección SMTP principal del buzón. Nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' se recomiendan.

```PowerShell

$domain="yourdomain.com  "
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin

```

#### <a name="create-the-scheduler-assistant-mailbox"></a>Crear el buzón del asistente del programador

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 

```
    
#### <a name="designate-the-scheduler-assistant-mailbox"></a>Designar el buzón del asistente del programador

```PowerShell

Set-mailbox cortana@$domain -SchedulerAssistant:$true


```
Después de ejecutar este comando "set" en el buzón del asistente del programador de Cortana, se establece un nuevo "PersistedCapability" en el buzón para tener en cuenta que este buzón es el "SchedulerAssistant".

>[!Note]
> Para obtener información sobre cómo conectar la organización a PowerShell, vea: [Conectar a Microsoft 365 con PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell)

### <a name="verifying-the-scheduler-assistant-mailbox"></a>Comprobar el buzón del asistente programador

Para comprobar que se ha creado el buzón del asistente del programador

```PowerShell

Get-CalendarProcessing cortana$domain <cortana>@microsoft.com   | fl DeleteNonCalendarItems`

```

El resultado debe ser "false".

<br>

```PowerShell

Get-Mailbox -Identity <cortana>@microsoft.com$domain -Organization microsoft.com$domain | fl *type*

```

El resultado debe ser
- ResourceType: Equipment
- RecipientType remoto: Ninguno
- RecipientType: UserMailbox
- RecipientTypeDetails: EquipmentMailbox

</br>

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>Para descubrir qué buzón es el buzón del asistente programador

```PowerShell

Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

>[Importante] El buzón del asistente programador puede tardar varias horas en completar el aprovisionamiento completo para establecer la funcionalidad SchedulerAssistant.


## <a name="exchange-online-mailbox"></a>Buzón de correo Exchange Online
Una licencia de Programador es un complemento para Microsoft 365, que permite al organizador de la reunión delegar sus tareas de programación de reuniones en su asistente programador. Además de designar un buzón como buzón de asistente del programador Exchange Online, los organizadores de reuniones también necesitarán una licencia del programador y un buzón y un calendario, normalmente Microsoft 365 través de una licencia para que el Programador funcione. Los asistentes a la reunión no necesitan una licencia del Programador ni una Microsoft 365 de trabajo.

Para comprar el complemento Programador, necesita una de las siguientes licencias:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Licencia del Plan 1 o plan 2. 

> [!Note]

> El programador Microsoft 365 está disponible en entornos multiinquilino en todo el mundo solo en inglés. **El programador Microsoft 365** no está disponible para los usuarios de:

- Microsoft 365 operado por 21Vianet en China
- Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom
- Nube de gobierno, GCC, Consumidor, GCC High o DoD

El programador admite usuarios en Alemania cuya ubicación de datos no es el centro de datos alemán.
