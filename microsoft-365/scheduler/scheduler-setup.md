---
title: Configuración del programador para Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Configuración del programador para Microsoft 365.
ms.openlocfilehash: ef377393134e4d8028ab0e6e40ddcc3647f60695
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953856"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configuración del Planificador para Microsoft 365

Los administradores de inquilinos deben configurar un buzón del asistente de Scheduler y obtener licencias de Scheduler para los organizadores de reuniones a fin de habilitar scheduler para Microsoft 365 servicio. 

## <a name="licensing"></a>Licencias

Más información: [Programador para licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)

> [!NOTE]
> Los asistentes a la reunión no necesitan una licencia de Scheduler o Microsoft 365.
>
> El buzón del asistente de Scheduler no requiere una Microsoft 365 ni una licencia de Scheduler.

## <a name="prerequisites"></a>Requisitos previos

|Requisito previo|Descripción|
|---|---|
|Un buzón del asistente de Scheduler para el inquilino |Un buzón de recursos de tipo de equipo Exchange que actúa como buzón del asistente de Scheduler para que el inquilino envíe y reciba correos electrónicos hacia y desde Cortana. Todos los correos electrónicos enviados a Cortana se conservan en el buzón Cortana del inquilino en función de la directiva de retención. El buzón del asistente de Scheduler se denomina normalmente "Cortana" o "programador de Cortana", ya que todos los correos electrónicos del asistente se firmarán Cortana. <ul><li>Creación de un tipo de equipo Exchange buzón de recursos</li><li>Asigne al buzón el nombre para mostrar y la dirección `Cortana <cortana@yourdomain.com>` SMTP principal o `Cortana Scheduler <cortana.scheduler@yourdomain.com>`.</li></ul> <br/> **Nota:** El buzón del asistente de Scheduler no requiere una Microsoft 365 ni una licencia de Scheduler.|
|Buzón de correo Exchange Online |Los organizadores de reuniones deben tener un buzón de Exchange Online y un calendario normalmente como parte de su licencia de Microsoft 365. Además, los organizadores de reuniones deben tener una licencia de Scheduler. La licencia de Scheduler permite al asistente de Scheduler usar el buzón y el calendario del organizador de la reunión para programar reuniones para ellos. <br/><br/> Consulte Scheduler para obtener Microsoft 365 para obtener información sobre licencias y precios. <br/><br/> **Nota:** Los asistentes a la reunión no necesitan una licencia de Scheduler o Microsoft 365. Los asistentes a la reunión pueden ser internos o externos al inquilino. Los asistentes a la reunión solo necesitan acceso a una dirección de correo electrónico.|

## <a name="setting-up-the-scheduler-assistant-mailbox"></a>Configuración del buzón del asistente de Scheduler

El buzón del asistente del programador es un buzón de correo de tipo de equipo Exchange que no requiere una licencia adicional de Microsoft 365 o programador. El nombre para mostrar y la dirección SMTP principal del buzón de correo deben contener Cortana, ya que todos los correos electrónicos del asistente de Scheduler se firmarán Cortana (es decir, `Cortana <cortana@yourdomain.com>` o `Cortana Scheduler <cortana.scheduler@yourdomain.com>`). Una vez creado el buzón del asistente de Scheduler, debe designar el buzón como buzón del asistente de Scheduler. Después de designar el buzón del asistente de Scheduler, Cortana estarán disponibles para programar reuniones en nombre de los usuarios.

- Use el Centro de administración de Microsoft 365 para crear un buzón de usuario. Se recomienda una directiva de retención de 30 días. 
- Use el nombre Cortana en la dirección SMTP principal del buzón. Se recomiendan nombres como `Cortana@yourdomain.com`, `CortanaScheduler@contoso.com`o `Cortana.Scheduler@yourdomain.com` .

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designe el buzón como Asistente para programadores.

Una vez creado un buzón único para Cortana Scheduler, debe designar el buzón para Microsoft 365 formalmente. Después de designar el buzón de Cortana Scheduler, estará disponible para programar reuniones en nombre de los usuarios.

### <a name="connect-to-powershell"></a>Conectar a PowerShell

Use el Centro de administración de Microsoft 365 para crear un buzón de usuario. Se recomienda una directiva de retención de 30 días.
Use el nombre Cortana en la dirección SMTP principal del buzón. Se recomiendan nombres como `Cortana@yourdomain.com`, `CortanaScheduler@contoso.com`o `Cortana.Scheduler@yourdomain.com` .

```PowerShell
$domain="yourdomain.com"
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin
```

### <a name="create-the-scheduler-assistant-mailbox"></a>Creación del buzón del Asistente para programadores

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 
```

### <a name="designate-the-scheduler-assistant-mailbox"></a>Designar el buzón del Asistente para programadores

```PowerShell
Set-mailbox cortana@$domain -SchedulerAssistant:$true
```

Después de ejecutar este comando "set" en el buzón del asistente de Scheduler Cortana, se establece un nuevo "PersistedCapability" en el buzón para tener en cuenta que este buzón es "SchedulerAssistant".

> [!NOTE]
> Para obtener información sobre cómo conectar su organización a PowerShell, consulte[: Conectar a Microsoft 365 con PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell).

### <a name="verifying-the-scheduler-assistant-mailbox"></a>Comprobación del buzón del asistente de Scheduler

Para comprobar que se ha creado el buzón del asistente del programador

```PowerShell
Get-CalendarProcessing cortana@$domain | fl DeleteNonCalendarItems
```

El resultado debe ser "false".

```PowerShell
Get-Mailbox -Identity cortana@$domain | fl *type*
```

El resultado debe ser

- ResourceType: Equipo
- RecipientType remoto: Ninguno
- RecipientType: UserMailbox
- RecipientTypeDetails: EquipmentMailbox

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>Para detectar qué buzón es el buzón del asistente del programador

```PowerShell
Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> El buzón del asistente de Scheduler puede tardar varias horas en completar el aprovisionamiento completo para establecer la funcionalidad SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Buzón de correo Exchange Online

Una licencia de Scheduler es un complemento para Microsoft 365, que permite al organizador de la reunión delegar sus tareas de programación de reuniones en su asistente de Scheduler. Además de designar un buzón como buzón del asistente de Scheduler, los organizadores de reuniones también necesitarán una licencia de Scheduler y Exchange Online buzón y calendario, normalmente a través de Microsoft 365 licencia para que Scheduler funcione. Los asistentes a la reunión no necesitan una licencia de Scheduler ni una licencia de Microsoft 365.

Para comprar el complemento Scheduler, necesita una de las siguientes licencias:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online licencia plan 1 o plan 2.

> [!NOTE]
> Scheduler para Microsoft 365 solo está disponible en entornos multiinquilino en todo el mundo en inglés. **Scheduler para Microsoft 365** no está disponible para los usuarios de:
>
> - Microsoft 365 opera 21Vianet en China
> - Microsoft 365 con la nube alemana que usa el administrador de datos Telekom alemán
> - Nube gubernamental que incluye GCC, Consumidor, GCC Alto o DoD
>
> Scheduler admite usuarios en Alemania cuya ubicación de datos no es el centro de datos alemán.
