---
title: Activa o desactiva Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Obtenga información sobre cómo obtener acceso a Microsoft Bookings en Microsoft 365.
ms.openlocfilehash: 28398faba7c21b6d3cce84063934268dad11fd64
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823088"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Activa o desactiva Microsoft Bookings

> [!NOTE]
> Este artículo le ayuda a interactuar con la versión más reciente de Microsoft Bookings. Las versiones anteriores se retirarán en los próximos meses.

Este artículo está destinado a los administradores. 

Bookings se pueden activar o desactivar para toda la organización o para usuarios específicos. Al activar Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.

> [!NOTE]
> Los controles de administración descritos en estas secciones no están disponibles para los clientes de Office 365 operados por 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Active o desactive Bookings para su organización mediante el Centro de administración de Microsoft 365

1. Inicie sesión en el Centro de administración de Microsoft 365 como administrador global.

2. En el centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**configuración de la organización**</a>.

3. Active la casilla **Permitir que la organización use Bookings** para habilitar o deshabilitar Bookings para su organización.

   > [!NOTE]
   > Al desactivar Bookings se deshabilitará todo el acceso al servicio, incluida la creación y administración de Bookings páginas.

4. Seleccione **Guardar cambios**.

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar Bookings para su organización mediante PowerShell

Para activar o desactivar Bookings para su organización mediante el cmdlet de PowerShell [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="granular-controls"></a>Controles granulares

Use la configuración siguiente para controlar quién puede usar Bookings, decidir qué información de Bookings se comparte y si el personal necesita aprobación antes de que se pueda agregar a un calendario de Booking.

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="Captura de pantalla: Configuración que le permiten controlar quién puede usar Bookings, decidir qué información de Bookings se comparte y la aprobación del personal":::

### <a name="block-bookings-from-outside-your-organization"></a>Bloquear reservas desde fuera de la organización

Puede configurar Bookings para que solo los usuarios de su organización puedan reservar citas. Solo los usuarios de la organización que han iniciado sesión y se han autenticado pueden reservar citas.

### <a name="block-social-sharing-options"></a>Bloquear opciones de uso compartido de redes sociales

Puede controlar cómo se comparten las páginas de reserva en las redes sociales. Esta configuración está disponible en la Centro de administración de Microsoft 365 en **configuración de Configuración** ->  **Org** ->  **Bookings**.

### <a name="block-sharing-staff-details-with-customers"></a>Bloquear el uso compartido de los detalles del personal con los clientes

Los detalles del personal, como la información de contacto, nunca se enviarán a los clientes por correo electrónico ni a ninguna otra comunicación.

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Requerir aprobaciones del personal antes de compartir información de disponibilidad

Puede requerir que los empleados de su organización opten por participar antes de que su información de disponibilidad se comparta a través de Bookings y antes de que puedan reservar a través de una página de reserva.

Cuando esta configuración está habilitada, las personas agregadas como personal en los calendarios de reserva recibirán un correo electrónico con un vínculo a **Aprobar o rechazar** la solicitud.

## <a name="restrict-collection-of-customer-data"></a>Restricción de la recopilación de datos de clientes

Por motivos de cumplimiento, es posible que no quiera recopilar información de los clientes. Si selecciona una casilla para cualquiera de estas opciones, estos campos no se incluirán en ningún formulario que se muestre a los clientes o clientes.

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="Captura de pantalla: active las casillas para evitar que los clientes compartan datos confidenciales con usted":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Activar o desactivar Bookings para usuarios individuales

Puede deshabilitar Bookings para usuarios individuales.

1. Vaya a la Centro de administración de Microsoft 365 y, a continuación, seleccione **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**usuarios activos**</a>.

1. Seleccione el usuario deseado y, a continuación, seleccione **Licencias y aplicaciones**.

1. Expanda **Aplicaciones** y desactive la casilla de Microsoft Bookings.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que solo los usuarios seleccionados creen calendarios Bookings

Mediante el uso de restricciones de directiva, puede restringir que los usuarios con licencia puedan crear calendarios Bookings. Primero debe habilitar Bookings para toda la organización. Todos los usuarios de su organización tendrán licencias de Bookings, pero solo los incluidos en la directiva pueden crear calendarios Bookings y tener control total sobre quién puede acceder a los calendarios que crean.

Los usuarios que se incluyen en esta directiva pueden crear nuevos calendarios de Bookings y se pueden agregar como personal en cualquier capacidad (incluido el rol de administrador) a los calendarios Bookings existentes. Los usuarios que no están incluidos en esta directiva no podrán crear nuevos calendarios Bookings y recibirán un mensaje de error si intentan hacerlo.

Tendrá que ejecutar los siguientes comandos mediante Exchange Online PowerShell. Para obtener más información sobre cómo ejecutar cmdlets de Exchange Online, consulte [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> En los pasos siguientes se supone que no se ha creado ninguna otra directiva de buzón de Outlook Web App (OWA) en su organización.

1. Cree una nueva directiva de buzón de correo para los usuarios que deben tener permiso para crear calendarios Bookings. (de forma predeterminada, las nuevas directivas de buzón permiten la creación de Bookings calendario).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obtener más información, vea [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Asigne esta directiva a los usuarios pertinentes mediante la ejecución de este comando para cada usuario al que quiera conceder permiso para crear Bookings calendarios.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obtener más información, vea [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Opcional: ejecute este comando si desea deshabilitar Bookings para todos los demás usuarios de la organización.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para más información, vea [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Para obtener más información sobre las directivas de buzón de OWA, consulte los temas siguientes:

- [Cree una directiva de buzón de Outlook en la Web en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar o quitar una directiva de buzón de Outlook en la Web en un buzón de Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
