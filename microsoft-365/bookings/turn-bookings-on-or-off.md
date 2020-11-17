---
title: Activar o desactivar Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Obtenga información sobre cómo obtener acceso a Microsoft bookings en Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126605"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Activar o desactivar Microsoft bookings

Las reservas pueden activarse o desactivarse para toda la organización o para usuarios específicos. Cuando se activan las reservas para los usuarios, se puede crear una página de reservas, crear un calendario y permitir que otras personas dispongan de tiempo con ellos.

> [!NOTE]
> Los controles de administración descritos en estas secciones no están disponibles para los clientes de Office 365 operado por 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Activar o desactivar las reservas para su organización mediante el centro de administración de Microsoft 365

1. Inicie sesión en el centro de administración de Microsoft 365 como administrador global.

2. En el centro de administración, vaya a  **configuración** de   \> la **organización** y seleccione **reservas**.

3. Marque la casilla de verificación **permitir a su organización usar reservas** para habilitar o deshabilitar reservas para su organización.

   > [!NOTE]
   > La desactivación de reservas deshabilitará todo el acceso al servicio, incluida la creación y la administración de las páginas de reservas.

4. Seleccione **Guardar cambios**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar las reservas para su organización mediante PowerShell

Para activar o desactivar las reservas para su organización mediante el cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)de PowerShell, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Activar o desactivar las reservas para usuarios individuales

Puede deshabilitar las reservas para usuarios individuales.

1. Vaya al centro de administración de Microsoft 365 **y seleccione usuarios** \> **activos**.

1. Seleccione el usuario que desee y, a continuación, seleccione **licencias y aplicaciones**.

1. Expanda **aplicaciones** y desactive la casilla de verificación de Microsoft bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Requerir aprobaciones del personal antes de compartir la información de disponibilidad

Los administradores pueden requerir que los empleados de su organización se puedan suscribir antes de que la información de disponibilidad se comparta a través de reservas y antes de que se puedan bookable a través de una página de reserva. Esta opción está disponible en el centro de administración de Microsoft **365 en configuración de** \> **Settings** \> **reservas**.

Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva buscarán un vínculo aprobar o rechazar en la notificación de correo electrónico que reciban.

Esta característica se encuentra gradualmente en todo el mundo a los clientes de Microsoft 365. Si no ve esta opción en el centro de administración de Microsoft 365, vuelva a consultar pronto.

## <a name="block-social-sharing-options"></a>Bloquear opciones de uso compartido social

Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales. Esta opción está disponible en el centro de administración de Microsoft **365 en configuración de** \> **Settings** \> **reservas**.

Esta característica se encuentra gradualmente en todo el mundo a los clientes de Microsoft 365. Si no ve esta opción en el centro de administración de Microsoft 365, vuelva a consultar pronto.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir solo a los usuarios seleccionados crear calendarios de reservas

Mediante el uso de restricciones de Directiva, puede restringir que los usuarios con licencia puedan crear calendarios de reservas. Primero debe habilitar las reservas para toda la organización. Todos los usuarios de la organización tendrán licencias de reservas, pero solo los que se incluyan en la Directiva pueden crear calendarios de reservas y tener control total sobre quién puede tener acceso a los calendarios que crean.

Los usuarios que se incluyen en esta Directiva pueden crear nuevos calendarios de reservas y se pueden agregar como personal de cualquier capacidad (incluido el rol de administrador) a calendarios de reservas existentes. Los usuarios que no estén incluidos en esta Directiva no podrán crear calendarios de reservas y recibirán un mensaje de error si intentan hacerlo.

Deberá ejecutar los siguientes comandos con Exchange Online PowerShell. Para obtener más información sobre cómo ejecutar los cmdlets de Exchange Online, vea [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> En los pasos siguientes se da por sentado que no se ha creado ninguna otra directiva de buzón de Outlook Web App (OWA) en la organización.

1. Cree una nueva Directiva de buzón para los usuarios a los que se les permitirá crear calendarios de reservas. (Las nuevas directivas de buzón de correo permiten la creación de calendarios de Books de forma predeterminada).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obtener más información, vea [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Asigne esta directiva a los usuarios pertinentes; para ello, ejecute este comando para cada usuario al que desee conceder permisos para crear calendarios de reservas.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obtener más información, vea [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Opcional: ejecute este comando si desea deshabilitar las reservas para todos los demás usuarios de la organización.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para más información, vea [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Para obtener más información sobre las directivas de buzón de OWA, consulte los siguientes temas:

- [Crear una directiva de buzón de correo de Outlook en la web en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar o quitar una directiva de buzón de Outlook en la web en un buzón de Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
