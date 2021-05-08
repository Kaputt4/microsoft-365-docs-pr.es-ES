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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286253"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configuración del programador para Microsoft 365

Para configurar el Programador para Microsoft 365, a continuación se indican los requisitos previos:

|**¿Qué necesito?** |**Descripción** |
|-------------------|-------------|
|Buzón de Cortana |Los administradores de inquilinos tendrán que establecer un buzón para que sirva como buzón "Cortana" (es decir, cortana@yourdomain.com).         |
|Buzón de correo Exchange Online |Los usuarios deben tener un Exchange Online correo electrónico y un calendario         |
|Licencia del programador |Para obtener información sobre licencias y precios, vea [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Crear un buzón para Cortana
Un Exchange en el inquilino actúa como el buzón de Cortana para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana. Todos los correos electrónicos enviados a Cortana se conservan en el buzón de Cortana del inquilino en función de la directiva de retención.

- Use el centro Microsoft 365 administración para crear un buzón nuevo. Se recomienda una directiva de retención de 30 días. Use el nombre Cortana en la dirección SMTP principal del buzón. Se recomiendan nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".
- Póngase en contacto con Microsoft (scheduler_m365@microsoft.com) para habilitar el buzón de Cortana. 

> [!IMPORTANT]
> Debe ponerse en contacto con Microsoft para configurar el buzón de Cortana para que use el servicio Scheduler mediante correo electrónico scheduler_m365@microsoft.com. Habilitar el buzón de Cortana puede tardar hasta dos semanas.

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
> **El programador Microsoft 365** no está disponible para usuarios de Office 365 operado por 21Vianet en China. Tampoco está disponible para los usuarios de Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom. Sin embargo, es compatible con los usuarios de Alemania cuya ubicación de datos no se encuentre en el centro de datos alemán.
>
>Esta característica tampoco es compatible con los usuarios de la nube para administración pública, incluidos GCC, Consumidor, GCC High o DoD.
