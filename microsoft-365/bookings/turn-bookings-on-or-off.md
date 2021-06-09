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
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913771"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Activa o desactiva Microsoft Bookings

Las reservas pueden estar activadas o desactivadas para toda la organización o para usuarios específicos. Cuando activas Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.

> [!NOTE]
> Los controles de administración que se describen en estas secciones no están disponibles Office 365 los clientes de 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Activar o desactivar Bookings para su organización mediante el Centro Microsoft 365 administración

1. Inicie sesión en el centro Microsoft 365 de administración como administrador global.

2. En el Centro de administración, vaya  **a Configuración**   \> **Org Configuración** y seleccione **Bookings**.

3. Active la casilla **Permitir que su organización use Bookings** para habilitar o deshabilitar Bookings para su organización.

   > [!NOTE]
   > Desactivar Bookings deshabilitará todo el acceso al servicio, incluida la creación y administración de páginas de Bookings.

4. Seleccione **Guardar cambios**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar Bookings para su organización con PowerShell

Para activar o desactivar Bookings para su organización con el cmdlet de PowerShell [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), Conectar a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Activar o desactivar Bookings para usuarios individuales

Puedes deshabilitar Bookings para usuarios individuales.

1. Vaya al Centro Microsoft 365 administración y, a continuación, seleccione **Usuarios** \> **usuarios activos.**

1. Seleccione el usuario deseado y, a continuación, **seleccione Licencias y aplicaciones.**

1. Expanda **Aplicaciones** y desactive la casilla de Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Requerir aprobaciones de personal antes de compartir información de disponibilidad

Los administradores pueden exigir a los empleados de su organización que opten por participar antes de compartir su información de disponibilidad a través de Bookings y antes de poder reservar a través de una página de reserva. Esta configuración está disponible en el Centro Microsoft 365 administración en **Configuración** \> **Configuración** \> **Bookings**.

Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva encontrarán un vínculo Aprobar o rechazar en la notificación de correo electrónico que reciben.

Esta característica se está implementando gradualmente en todo el mundo para Microsoft 365 clientes. Si no ve esta opción en el centro de administración de Microsoft 365, vuelva pronto.

## <a name="block-social-sharing-options"></a>Bloquear opciones de uso compartido social

Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales. Esta configuración está disponible en el Centro Microsoft 365 administración en **Configuración** \> **Configuración** \> **Bookings**.

Esta característica se está implementando gradualmente en todo el mundo para Microsoft 365 clientes. Si no ve esta opción en el centro de administración de Microsoft 365, vuelva pronto.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que solo los usuarios seleccionados creen calendarios de Bookings

Al usar restricciones de directiva, puede restringir a los usuarios con licencia la posibilidad de crear calendarios de Bookings. Primero debe habilitar Bookings para toda la organización. Todos los usuarios de la organización tendrán licencias de Bookings, pero solo los incluidos en la directiva pueden crear calendarios de Bookings y tener control total sobre quién puede acceder a los calendarios que creen.

Los usuarios incluidos en esta directiva pueden crear nuevos calendarios de Bookings y pueden agregarse como personal con cualquier capacidad (incluido el rol de administrador) a los calendarios de Bookings existentes. Los usuarios que no están incluidos en esta directiva no podrán crear nuevos calendarios de Bookings y recibirán un mensaje de error si intentan hacerlo.

Deberá ejecutar los siguientes comandos con Exchange Online PowerShell. Para obtener más información sobre cómo Exchange Online cmdlets, vea [Conectar to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> Los pasos siguientes suponen que no se han creado otras Outlook Web App de buzones de correo (OWA) en su organización.

1. Cree una nueva directiva de buzón de correo para los usuarios que deben tener permiso para crear calendarios de Bookings. (La creación de calendario de Bookings está permitida de forma predeterminada por las nuevas directivas de buzón).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obtener más información, [vea New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Para asignar esta directiva a los usuarios relevantes, ejecute este comando para cada usuario que desee conceder permiso para crear calendarios de Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obtener más información, vea [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Opcional: ejecute este comando si desea deshabilitar Bookings para todos los demás usuarios de la organización.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para más información, vea [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Para obtener más información sobre las directivas de buzones de OWA, consulte los siguientes temas:

- [Crear una Outlook en la directiva de buzón de correo web en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar o quitar una Outlook en la directiva de buzón de correo web en un buzón en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)