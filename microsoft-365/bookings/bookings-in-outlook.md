---
title: Bookings en Outlook
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ROBOTS: NO INDEX, NO FOLLOW
description: Use Bookings en Outlook para permitir que otros usuarios programe reuniones con usted en Outlook.
ms.openlocfilehash: fb74b345a9c1985388ed4754b3f9913a46e5d9de
ms.sourcegitcommit: 570c3be37b6ab1d59a4988f7de9c9fb5ca38028f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65363047"
---
# <a name="bookings-in-outlook"></a>Bookings en Outlook

Bookings en Outlook es una página de programación personal basada en web que se integra con la información de disponibilidad del calendario de Outlook. Bookings en Outlook permite a los usuarios programar una reunión o una cita con usted. Puede crear tipos de reunión personalizados para compartirlos con otros usuarios para que puedan programar fácilmente tiempo con usted en función de su disponibilidad y preferencias. Ambos reciben una confirmación por correo electrónico y los asistentes pueden actualizar o cancelar reuniones programadas con usted desde su Bookings en Outlook página.

> [!NOTE]
> Bookings en Outlook solo está disponible en versión preliminar.

Bookings en Outlook tiene dos vistas diferentes:

- **Vista organizador** Una página de reserva personal donde puede crear tipos de reunión que otros usuarios pueden reservar con usted. Los tipos de reunión personalizados le ofrecen la capacidad de personalizar cuándo desea reunirse y cómo se comparte ese tipo de reunión con otros usuarios. Puede controlar si cada tipo de reunión es público en la página de programación o si es privado y solo puede acceder a él un grupo de personas seleccionado. También puede elegir agregar una reunión de Teams a todas las reuniones reservadas a través de su Bookings en Outlook página. Puede acceder a la Bookings en Outlook página a través de Outlook en la Web o yendo a [https://outlook.office.com/bookwithme/](https://outlook.office.com/bookwithme/). Después de configurar la página y publicarla, puede compartirla con otros usuarios. Por ejemplo, puede agregarlo a la firma de Outlook.

- **Vista programación** Cuando comparta su Bookings en Outlook página con otros usuarios, verán la vista de programación. Las reuniones que se muestran en la vista de programación dependen de si ha compartido el vínculo a la Bookings en Outlook página con reuniones públicas o si ha compartido un vínculo privado para una reunión individual.
    - Cualquier persona que tenga su Bookings en Outlook vínculo de página puede ver y programar reuniones públicas. Tiene el control de con quién comparte ese vínculo. Todos los tipos de reuniones públicas serán visibles para cualquier persona que tenga el Bookings en Outlook vínculo de página.
    - Las reuniones privadas solo las pueden ver las personas que tienen el vínculo para ese tipo de reunión. La diferencia entre las reuniones públicas y las privadas es que las reuniones privadas pueden tener vínculos diferentes y los vínculos expiran después de 90 días. También puede establecer vínculos privados para que expiren después de una reserva única. Al acceder a la vista de programación de una reunión privada, solo estará visible ese tipo de reunión.

## <a name="before-you-begin"></a>Antes de empezar

Bookings en Outlook está disponible en las siguientes suscripciones:

- Office 365: A3, A5, E1, E3, E5, F1, F3
- Microsoft 365: A3, A5, E1, E3, E5, F1, F3, Business Basic, Business Standard, Business Premium

Bookings en Outlook está activado de forma predeterminada para los usuarios con estas suscripciones.

Para obtener más información, consulte el [Bookings en Outlook Microsoft 365 elemento Hoja de ruta](https://go.microsoft.com/fwlink/?linkid=328648).

## <a name="turn-bookings-in-outlook-on-or-off"></a>Activar o desactivar Bookings en Outlook  

Bookings en Outlook se puede activar o desactivar para toda la organización o usuarios específicos. Cuando se activa Bookings en Outlook, los usuarios pueden crear un Bookings en Outlook página y compartir vínculos con otros usuarios dentro o fuera de la organización.

### <a name="turn-bookings-in-outlook-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar Bookings en Outlook para su organización mediante PowerShell

Tendrá que ejecutar los siguientes comandos mediante Exchange Online PowerShell. Para obtener más información sobre cómo ejecutar cmdlets de Exchange Online, consulte [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para activar o desactivar Bookings en Outlook para su organización mediante el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) de PowerShell, [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecutar los comandos siguientes.

Use los comandos **Get-OrganizationConfig** y **Set-OrganizationConfig** para averiguar el estado y activar o desactivar Bookings en Outlook para su organización.

> [!NOTE]
> Normalmente, los comandos de Set-OrganizationConfig tardan entre 30 y 60 minutos en surtir efecto para los usuarios.

1. Compruebe el acceso de control de EWS mediante la ejecución del siguiente comando.

   ```PowerShell
   Get-Organizationconfig | Format-List EwsEnabled
   ```

    Si el comando devuelve "EwsEnabled: **$true**", continúe con el paso 2.

    Si el comando devuelve "EwsEnabled:" (vacío es el valor predeterminado), habilite y continúe con el paso 2.

   ```PowerShell
   Set-OrganizationConfig -EwsEnabled: $true
   ```

2. Para comprobar el valor de EwsApplicationAccessPolicy, ejecute el siguiente comando:

   ```PowerShell
   Get-OrganizationConfig | Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceAllowList**, solo las aplicaciones especificadas en **EwsAllowList** pueden acceder a EWS y REST.

    - Para desactivar Bookings en Outlook de su organización, quite **MicrosoftOWSPersonalBookings**, si está presente, de **EwsAllowList** mediante la ejecución del siguiente comando:  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings en Outlook para su organización, agregue **MicrosoftOWSPersonalBookings** a **EwsAllowList** mediante la ejecución del siguiente comando:  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceBlockList**, todas las aplicaciones pueden acceder a EWS y REST, excepto los especificados en **EwsBlockList**.

    - Para desactivar Bookings en Outlook para su organización, agregue **MicrosoftOWSPersonalBookings** mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings en Outlook si se bloquea, quite **MicrosoftOWSPersonalBookings** ejecutando el siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. Si el valor  **deEwsApplicationAccessPolicyis**  está vacío, todas las aplicaciones pueden acceder a EWS y REST.

    - Para desactivar Bookings en Outlook de su organización, establezca la directiva **EnforceBlockList** y agregue **MicrosoftOWSPersonalBookings** a la lista de bloques mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsApplicationAccessPolicy EnforceBlockList -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

### <a name="turn-bookings-in-outlook-off-or-on-for-individual-users"></a>Desactivar o activar Bookings en Outlook para usuarios individuales

Use los comandos **Get-CASMailbox** y **Set-CASMailbox** para comprobar el estado del usuario y activar o desactivar Bookings en Outlook para usuarios individuales de su organización.

1. Compruebe la propiedad EwsApplicationAccessPolicy de una persona mediante la ejecución del siguiente comando:

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsEnabled
   ```

    **A**. Si el comando devuelve "**EwsEnabled: $true**", continúe con el paso 2.

2. Compruebe el **valor de EwsApplicationAccessPolicy** de la persona ejecutando el siguiente comando:

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com| Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceAllowList**, solo las aplicaciones especificadas en EwsAllowList pueden acceder a EWS y REST.

    - Para desactivar Bookings en Outlook para este usuario, quite **MicrosoftOWSPersonalBookings**, si está presente en **EwsAllowList** mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - Active Bookings en Outlook para este usuario, agregue **MicrosoftOWSPersonalBookings** a **EwsAllowList** ejecutando el siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceBlockList**, todas las aplicaciones pueden acceder a EWS y REST, excepto los especificados en **EwsBlockList**.  

    - Para desactivar Bookings en Outlook para este usuario, agregue **MicrosoftOWSPersonalBookings** a **EnforceBlockList** mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsApplicationAccessPolicy  EnforceBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings en Outlook para este usuario, quite **MicrosoftOWSPersonalBookings**, si está presente en EnforceBlockList mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. Si el valor de EwsApplicationAccessPolicy está vacío, todas las aplicaciones pueden acceder a EWS y REST.

    - Para desactivar Bookings en Outlook para este usuario, establezca la directiva **EnforceBlockList** y  **agregueMicrosoftOWSPersonalBookingsto**  EWSBlockList mediante la ejecución del siguiente comando:

    ```PowerShell
   Set-CASMailbox -Identity Adam -EwsApplicationAccessPolicy  EnforceBlockList -EWSBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
