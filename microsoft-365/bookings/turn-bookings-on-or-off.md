---
title: Activa o desactiva Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Obtenga información sobre cómo obtener acceso a Microsoft Bookings en Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126605"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Activa o desactiva Microsoft Bookings

Bookings puede estar activado o desactivado para toda la organización o para usuarios específicos. Cuando activa Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.

> [!NOTE]
> Los controles de administración descritos en estas secciones no están disponibles para los clientes de Office 365 Operado por 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Activar o desactivar Bookings para su organización mediante el Centro de administración de Microsoft 365

1. Inicie sesión en el Centro de administración de Microsoft 365 como administrador global.

2. En el centro de administración, vaya  **a** Configuración de la organización   \> **y** seleccione **Bookings.**

3. Active la casilla permitir **que su organización use Bookings** para habilitar o deshabilitar Bookings para su organización.

   > [!NOTE]
   > Al desactivar Bookings, se deshabilitará todo el acceso al servicio, incluida la creación y administración de páginas de Bookings.

4. Seleccione **Guardar cambios.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar Bookings para su organización con PowerShell

Para activar o desactivar Bookings para su organización con el cmdlet de PowerShell [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Activar o desactivar Bookings para usuarios individuales

Puede deshabilitar Bookings para usuarios individuales.

1. Vaya al Centro de administración de Microsoft 365 y, a continuación, seleccione **Usuarios** \> **activos.**

1. Seleccione el usuario deseado y, a continuación, **seleccione Licencias y aplicaciones.**

1. Expanda **Aplicaciones** y desactive la casilla de Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Requerir aprobaciones del personal antes de compartir información de disponibilidad

Los administradores pueden requerir que los empleados de su organización puedan participar antes de que su información de disponibilidad se comparta a través de Bookings y antes de que se puedan reservar a través de una página de reserva. Esta configuración está disponible en el Centro de administración de Microsoft 365 en **Configuración** \>  \> **de Bookings.**

Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva encontrarán un vínculo Aprobar o Rechazar en la notificación por correo electrónico que reciben.

Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365. Si no ve esta opción en el Centro de administración de Microsoft 365, vuelva a consultarlo pronto.

## <a name="block-social-sharing-options"></a>Bloquear opciones de uso compartido social

Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales. Esta configuración está disponible en el Centro de administración de Microsoft 365 en **Configuración** \>  \> **de Bookings.**

Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365. Si no ve esta opción en el Centro de administración de Microsoft 365, vuelva a consultarlo pronto.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que solo los usuarios seleccionados creen calendarios de Bookings

Mediante el uso de restricciones de directiva, puede restringir a los usuarios con licencia la posibilidad de crear calendarios de Bookings. Primero debe habilitar Bookings para toda la organización. Todos los usuarios de su organización tendrán licencias de Bookings, pero solo los incluidos en la directiva pueden crear calendarios de Bookings y tener control total sobre quién puede acceder a los calendarios que crean.

Los usuarios que se incluyen en esta directiva pueden crear nuevos calendarios de Bookings y pueden agregarse como personal en cualquier capacidad (incluido el rol de administrador) a los calendarios de Bookings existentes. Los usuarios que no se incluyan en esta directiva no podrán crear nuevos calendarios de Bookings y recibirán un mensaje de error si intentan hacerlo.

Deberá ejecutar los siguientes comandos con Exchange Online PowerShell. Para obtener más información sobre cómo ejecutar cmdlets de Exchange Online, consulte [Conectarse a Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> En los pasos siguientes se supone que no se han creado otras directivas de buzón de Outlook Web App (OWA) en su organización.

1. Cree una nueva directiva de buzón para los usuarios que deberían tener permiso para crear calendarios de Bookings. (La creación de calendario de Bookings está permitida de forma predeterminada por las nuevas directivas de buzón).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obtener más información, [vea New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Para asignar esta directiva a los usuarios relevantes, ejecute este comando para cada usuario que desee conceder permiso para crear calendarios de Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obtener más información, vea [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Opcional: ejecute este comando si desea deshabilitar Bookings para todos los demás usuarios de la organización.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para más información, vea [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Para obtener más información sobre las directivas de buzón de OWA, consulte los siguientes temas:

- [Crear una directiva de buzón de Outlook en la Web en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar o quitar una directiva de buzón de Outlook en la Web en un buzón en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
