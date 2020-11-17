---
title: Eliminar un calendario de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use el centro de administración de Microsoft 365 o Windows PowerShell para eliminar calendarios de reservas.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126654"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="e3935-103">Eliminar un calendario de reserva en las reservas</span><span class="sxs-lookup"><span data-stu-id="e3935-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="e3935-104">En este artículo se explica cómo se puede eliminar un calendario de reserva no deseado.</span><span class="sxs-lookup"><span data-stu-id="e3935-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="e3935-105">Puede eliminar el calendario de reserva en el centro de administración de Microsoft 365 o puede usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3935-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="e3935-106">El calendario de reservas es un buzón de correo en Exchange Online, por lo que se elimina la cuenta de usuario correspondiente para eliminar el calendario de reserva.</span><span class="sxs-lookup"><span data-stu-id="e3935-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3935-107">Todos los calendarios de reserva que creó en 2017 o antes deben eliminarse con las instrucciones de PowerShell de este tema.</span><span class="sxs-lookup"><span data-stu-id="e3935-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="e3935-108">Todos los calendarios de reserva creados en 2018 o posteriores pueden eliminarse en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3935-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e3935-109">El calendario de reserva es donde se almacena toda la información relevante sobre el calendario y los datos de reserva, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e3935-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="e3935-110">Información de la empresa, logotipo y horas laborales agregadas al crear el calendario de reserva</span><span class="sxs-lookup"><span data-stu-id="e3935-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="e3935-111">Personal y servicios relevantes agregados cuando se creó el calendario de reserva</span><span class="sxs-lookup"><span data-stu-id="e3935-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="e3935-112">Todas las reservas y las citas de tiempo libre agregadas al calendario de reserva una vez que se creó.</span><span class="sxs-lookup"><span data-stu-id="e3935-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="e3935-113">Una vez que se elimina un calendario de reserva, esta información adicional también se elimina permanentemente y no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="e3935-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3935-114">Eliminar un calendario de reserva en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3935-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e3935-115">Vaya al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3935-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="e3935-116">En el Centro de administración, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e3935-116">In the Admin center, select **Users**.</span></span>

   ![Imagen de la interfaz de usuario de Microsoft en el centro de administración de 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="e3935-118">En la página **Usuarios activos**, elija los nombres de los usuarios que quiera eliminar y después seleccione **Eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="e3935-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Imagen de la interfaz de usuario de eliminación en el centro de administración de Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="e3935-120">Eliminar un calendario de reserva con Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3935-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="e3935-121">Consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) para obtener los requisitos previos y las instrucciones para conectarse a PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3935-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="e3935-122">Para realizar estos pasos, debe usar una ventana de comandos de PowerShell de Microsoft que haya ejecutado eligiendo la opción "ejecutar como administrador".</span><span class="sxs-lookup"><span data-stu-id="e3935-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="e3935-123">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e3935-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="e3935-124">Cuando se le pida, inicie sesión con las credenciales de administrador de inquilinos en el inquilino de Microsoft 365 que hospeda el calendario de reserva que desea eliminar de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="e3935-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="e3935-125">En el símbolo del sistema de PowerShell, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="e3935-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="e3935-126">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e3935-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="e3935-127">Una vez que este comando haya terminado el procesamiento, escriba el siguiente comando para obtener una lista de los buzones de reserva del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="e3935-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="e3935-128">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e3935-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="e3935-129">Tenga cuidado de escribir el nombre exacto del alias del buzón de reserva que desea eliminar de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="e3935-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="e3935-130">Para comprobar que el calendario se ha eliminado, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e3935-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="e3935-131">El calendario eliminado no aparecerá en el resultado.</span><span class="sxs-lookup"><span data-stu-id="e3935-131">The deleted calendar will not appear in the output.</span></span>
