---
title: Eliminación de un calendario de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use el Centro de administración de Microsoft 365 o Windows PowerShell para eliminar calendarios de Bookings.
ms.openlocfilehash: 1f8df15eafac7867f7ae852e344e1c5730362598
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454210"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="44b1d-103">Eliminar un calendario de reserva en Bookings</span><span class="sxs-lookup"><span data-stu-id="44b1d-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="44b1d-104">En este artículo se explica cómo eliminar un calendario de reserva no deseado.</span><span class="sxs-lookup"><span data-stu-id="44b1d-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="44b1d-105">Puede eliminar el calendario de reserva en el Centro de administración de Microsoft 365 o puede usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44b1d-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="44b1d-106">El calendario de Bookings es un buzón en Exchange Online por lo que se elimina la cuenta de usuario correspondiente para eliminar el calendario de reserva.</span><span class="sxs-lookup"><span data-stu-id="44b1d-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44b1d-107">Todos los calendarios de reserva que creó en 2017 o antes deben eliminarse con las instrucciones de PowerShell de este tema.</span><span class="sxs-lookup"><span data-stu-id="44b1d-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="44b1d-108">Todos los calendarios de reserva creados en 2018 o después se pueden eliminar en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44b1d-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="44b1d-109">El calendario de reserva es donde se almacena toda la información relevante sobre ese calendario de reserva y los datos, incluidos:</span><span class="sxs-lookup"><span data-stu-id="44b1d-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="44b1d-110">Información empresarial, logotipo y horas laborables agregadas cuando se creó el calendario de reserva</span><span class="sxs-lookup"><span data-stu-id="44b1d-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="44b1d-111">Personal y servicios relevantes agregados al crear el calendario de reserva</span><span class="sxs-lookup"><span data-stu-id="44b1d-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="44b1d-112">Todas las citas de reserva y tiempo libre agregados al calendario de reserva una vez creadas.</span><span class="sxs-lookup"><span data-stu-id="44b1d-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="44b1d-113">Una vez eliminado un calendario de reserva, esta información adicional también se elimina permanentemente y no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="44b1d-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="44b1d-114">Eliminar un calendario de reserva en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44b1d-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="44b1d-115">Vaya al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44b1d-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="44b1d-116">En el Centro de administración, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="44b1d-116">In the Admin center, select **Users**.</span></span>

   ![Imagen de la interfaz de usuario de usuarios en el Centro de administración de Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="44b1d-118">En la página **Usuarios activos**, elija los nombres de los usuarios que quiera eliminar y después seleccione **Eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="44b1d-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Imagen de Eliminar interfaz de usuario en el Centro de administración de Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="44b1d-120">Eliminar un calendario de reserva con Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="44b1d-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="44b1d-121">Consulte [Conectarse a Exchange Online PowerShell para](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) obtener requisitos previos y instrucciones para conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44b1d-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="44b1d-122">Para realizar estos pasos, debe usar una ventana de comandos activa de PowerShell de Microsoft que ejecutó seleccionando la opción "Ejecutar como administrador".</span><span class="sxs-lookup"><span data-stu-id="44b1d-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="44b1d-123">En una ventana de PowerShell, cargue el módulo EXO V2 ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="44b1d-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="44b1d-124">Si ya [instaló el módulo EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), el comando anterior funcionará como está escrito.</span><span class="sxs-lookup"><span data-stu-id="44b1d-124">If you've already [installed the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="44b1d-125">El comando que necesita ejecutar usa la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="44b1d-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="44b1d-126">_\<UPN\>_ es su cuenta en el formato del nombre principal de usuario (por ejemplo, `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="44b1d-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="44b1d-127">Cuando se le pida, inicie sesión con las credenciales de administrador de inquilinos en el inquilino de Microsoft 365 que hospeda el calendario de reserva que desea eliminar permanentemente.</span><span class="sxs-lookup"><span data-stu-id="44b1d-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="44b1d-128">Una vez que este comando haya terminado de procesarse, escriba el siguiente comando para obtener una lista de los buzones de reserva en su inquilino:</span><span class="sxs-lookup"><span data-stu-id="44b1d-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. <span data-ttu-id="44b1d-129">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="44b1d-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="44b1d-130">Tenga cuidado de escribir el nombre exacto del alias del buzón de reserva que desea eliminar permanentemente.</span><span class="sxs-lookup"><span data-stu-id="44b1d-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="44b1d-131">Para comprobar que el calendario se ha eliminado, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="44b1d-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="44b1d-132">El calendario eliminado no aparecerá en el resultado.</span><span class="sxs-lookup"><span data-stu-id="44b1d-132">The deleted calendar will not appear in the output.</span></span>
