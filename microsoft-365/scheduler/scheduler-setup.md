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
ms.openlocfilehash: f09d1f51ed8a868712c22fbd7a641b35f5d29073
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309351"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configuración del Planificador para Microsoft 365


Para configurar el Programador para Microsoft 365, a continuación se indican los requisitos previos:

|**¿Qué necesito?** |**Descripción** |
|-------------------|-------------|
|Cortana buzón de correo |Los administradores de inquilinos tendrán que establecer un buzón para que sirva como buzón de correo "Cortana" (es decir, cortana@yourdomain.com).         |
|Buzón de correo Exchange Online |Los usuarios deben tener un Exchange Online correo electrónico y un calendario         |
|Licencia del programador |Para obtener información sobre licencias y precios, vea [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Crear un buzón para Cortana
Un Exchange en el espacio empresarial actúa como el buzón de correo Cortana para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana. Todos los correos electrónicos enviados Cortana se conservan en el buzón de correo Cortana del inquilino en función de la directiva de retención.

- Use el Centro de administración de Microsoft 365 para crear un buzón de usuario. Se recomienda una directiva de retención de 30 días. 
- Use el nombre Cortana en la dirección SMTP principal del buzón. Nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' se recomiendan.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designar el buzón como asistente del programador

Después de crear un buzón único para Cortana scheduler, debe designar el buzón Microsoft 365 forma formal. Después de designar el buzón Cortana programador, estará disponible para programar reuniones en nombre de los usuarios.

Para designar el buzón Cortana Scheduler, un administrador autorizado debe ejecutar un comando de PowerShell de una línea. 

1. Conectar para Microsoft 365 espacio de ejecución remoto de PowerShell para la organización.
2. Ejecute el siguiente script de PowerShell para designar el buzón para scheduler:

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Después de ejecutar este comando "set" en el buzón del Programador de Cortana, se establece un nuevo "PersistedCapability" en el buzón para tener en cuenta que este buzón es el "SchedulerAssistant".

> [!NOTE]
> Siga estos pasos para conectar su organización a PowerShell si no lo ha hecho anteriormente: Conectar a Microsoft 365 [PowerShell : Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

Para descubrir qué buzón de correo de la organización está configurado actualmente como asistente Cortana programador, ejecute la función get:
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> El buzón del programador puede tardar hasta dos horas en completar el aprovisionamiento completo para establecer la funcionalidad SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Buzón de correo Exchange Online
Scheduler es un complemento para Microsoft 365. Los organizadores de reuniones deben tener un Exchange Online y un calendario para que el Programador funcione.

## <a name="exchange-requirements"></a>Requisitos de Exchange

Además del Programador de licencias, debe tener una de las siguientes licencias:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Licencia del Plan 1 o plan 2. 

> [!Note]
> **El programador Microsoft 365** está disponible actualmente para varios inquilinos en todo el mundo, solo en inglés.</br>
>
>No está disponible para usuarios de Office 365 operados por 21Vianet en China o usuarios de Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom. Sin embargo, es compatible con los usuarios de Alemania cuya ubicación de datos no se encuentre en el centro de datos alemán.
>
>Esta característica tampoco es compatible con los usuarios de la nube para administración pública, incluidos GCC, Consumidor, GCC High o DoD.
