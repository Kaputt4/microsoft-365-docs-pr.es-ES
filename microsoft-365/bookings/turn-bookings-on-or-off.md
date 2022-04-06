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
ms.openlocfilehash: 09fba96265bc3d2b67db9152f0c6020e10183314
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634809"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Activa o desactiva Microsoft Bookings

Bookings puede estar activado o desactivado para toda la organización o para usuarios específicos. Al activar el Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.

> [!NOTE]
> Los controles de administración que se describen en estas secciones no están disponibles para Office 365 operados por 21 clientes deVianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Active Bookings o desactive la organización mediante el Centro de administración de Microsoft 365

1. Inicie sesión en el Centro de administración de Microsoft 365 como administrador global.

2. En el Centro de administración, vaya a  **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**configuración de la organización**</a>.

3. Active la casilla **permitir que la organización use** Bookings para habilitar o deshabilitar Bookings para su organización.

   > [!NOTE]
   > Al desactivar Bookings se deshabilitará todo el acceso al servicio, incluida la creación y administración de Bookings páginas.

4. Seleccione **Guardar cambios**.

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Activar Bookings activar o desactivar la organización con PowerShell

Para activar Bookings para la organización mediante el cmdlet de PowerShell [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), Conectar para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

Usa la configuración siguiente para controlar quién puede usar Bookings, decidir qué información Bookings se comparte y si el personal necesita aprobación antes de que se pueda agregar a un calendario de Booking.

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="Captura de pantalla: Configuración que te permiten controlar quién puede usar Bookings, decidir qué información Bookings es compartida y la aprobación del personal":::

### <a name="block-bookings-from-outside-your-organization"></a>Bloquear reservas desde fuera de la organización

Puede configurar los Bookings para que solo los usuarios de su organización puedan reservar citas. Solo los usuarios de la organización que han iniciado sesión y están autenticados pueden reservar citas.

### <a name="block-social-sharing-options"></a>Bloquear opciones de uso compartido social

Puedes controlar cómo se comparten las páginas de reserva en las redes sociales. Esta configuración está disponible en el Centro de administración de Microsoft 365 en **Configuración** ->  **Configuración deorg** ->  **Bookings**.

### <a name="block-sharing-staff-details-with-customers"></a>Bloquear el uso compartido de los detalles del personal con los clientes

Los detalles del personal, como la información de contacto, nunca se enviarán a los clientes por correo electrónico o cualquier otra comunicación.

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Requerir aprobaciones de personal antes de compartir información de disponibilidad

Puede requerir que los empleados de su organización opten por participar antes de que su información de disponibilidad se comparta a través de Bookings y antes de que se puedan reservar a través de una página de reserva.

Cuando esta configuración está habilitada, las personas agregadas como personal en los calendarios de reserva recibirán un correo electrónico con un vínculo a **Aprobar o rechazar** la solicitud.

## <a name="restrict-collection-of-customer-data"></a>Restringir la recopilación de datos de clientes

Por motivos de cumplimiento, es posible que no quiera recopilar información de clientes. Si selecciona una casilla para cualquiera de estas opciones, estos campos no se incluirán en ningún formulario que se muestra a sus clientes o clientes.

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="Captura de pantalla: selecciona las casillas para evitar que los clientes compartan datos confidenciales contigo":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Activar Bookings o desactivar para usuarios individuales

Puede deshabilitar los Bookings usuarios individuales.

1. Vaya a la Centro de administración de Microsoft 365 y, a continuación, seleccione **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**usuarios activos**</a>.

1. Seleccione el usuario deseado y, a continuación, **seleccione Licencias y aplicaciones**.

1. Expanda **Aplicaciones** y desactive la casilla para Microsoft Bookings.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que solo los usuarios seleccionados creen Bookings calendarios

Mediante el uso de restricciones de directiva, puede restringir a los usuarios con licencia la posibilidad de crear Bookings calendarios. En primer lugar, debe habilitar Bookings para toda la organización. Todos los usuarios de la organización tendrán Bookings licencias, pero solo las incluidas en la directiva pueden crear calendarios Bookings y tener control total sobre quién puede tener acceso a los calendarios que crean.

Los usuarios que se incluyen en esta directiva pueden crear nuevos calendarios de Bookings y se pueden agregar como personal en cualquier capacidad (incluido el rol de administrador) a los calendarios de Bookings existentes. Los usuarios que no están incluidos en esta directiva no podrán crear nuevos calendarios de Bookings y recibirán un mensaje de error si intentan hacerlo.

Deberá ejecutar los siguientes comandos con Exchange Online PowerShell. Para obtener más información sobre cómo Exchange Online cmdlets, [vea Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> Los pasos siguientes suponen que no se han creado Outlook Web App directivas de buzones de correo (OWA) en la organización.

1. Cree una nueva directiva de buzón de correo para los usuarios a los que se les debe permitir crear Bookings calendarios. (Bookings la creación de calendario está permitida de forma predeterminada por las nuevas directivas de buzón).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obtener más información, [vea New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Para asignar esta directiva a los usuarios relevantes, ejecute este comando para cada usuario que desee conceder permiso para crear Bookings calendarios.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obtener más información, vea [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Opcional: ejecute este comando si desea deshabilitar el Bookings para todos los demás usuarios de la organización.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para más información, vea [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Para obtener más información sobre las directivas de buzones de OWA, consulte los siguientes temas:

- [Crear una directiva Outlook na Web buzón de correo en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar o quitar una directiva Outlook na Web buzón de correo en un buzón de Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
