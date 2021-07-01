---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226100"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="ea638-103">Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea638-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="ea638-p101">Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ea638-p101">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea638-106">A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de las retenciones de In-Place en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ea638-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ea638-107">A partir del 1 de julio de 2020 no podrá crear nuevas retenciones In-Place en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea638-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ea638-108">Pero aún podrá administrar las In-Place en el EAC o mediante el cmdlet **Set-MailboxSearch** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea638-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="ea638-109">Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar las In-Place retenciones.</span><span class="sxs-lookup"><span data-stu-id="ea638-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="ea638-110">Solo se quitarán en el EAC o mediante el cmdlet **Remove-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="ea638-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="ea638-111">Para obtener más información acerca de la retirada de In-Place, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="ea638-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

<span data-ttu-id="ea638-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="ea638-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="ea638-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="ea638-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="ea638-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="ea638-114">What can you do?</span></span> <span data-ttu-id="ea638-115">Si el período de retención de buzones eliminados no ha expirado, puede colocar una retención de In-Place en el buzón eliminado (denominado buzón eliminado temporalmente) y convertirlo en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ea638-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a soft-deleted mailbox) and make it an inactive mailbox.</span></span> <span data-ttu-id="ea638-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="ea638-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="ea638-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="ea638-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="ea638-118">Una vez inactivo el buzón, puede buscar en el buzón mediante la exhibición de documentos electrónicos de In-Place en Exchange Online, la búsqueda de contenido en el Centro de cumplimiento de & de seguridad o el Centro de exhibición de documentos electrónicos en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ea638-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span>

> [!NOTE]
> <span data-ttu-id="ea638-p104">En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo.</span><span class="sxs-lookup"><span data-stu-id="ea638-p104">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span>

## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="ea638-123">Requisitos para In-Place retenciones</span><span class="sxs-lookup"><span data-stu-id="ea638-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="ea638-p105">Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ea638-p105">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span>

- <span data-ttu-id="ea638-126">Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea638-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ea638-127">Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="ea638-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="ea638-128">Para obtener más información acerca de los buzones inactivos, vea [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ea638-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="ea638-129">Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ea638-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="ea638-p106">Use el cmdlet **New-MailboxSearch** para convertir un buzón eliminado temporalmente en un buzón inactivo. Para obtener más información, vea [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span><span class="sxs-lookup"><span data-stu-id="ea638-p106">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>

1. <span data-ttu-id="ea638-132">Cree una variable que contenga las propiedades del buzón eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="ea638-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="ea638-p107">En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGuid** para identificar el buzón eliminado temporalmente. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo y un buzón eliminado temporalmente tengan la misma dirección SMTP principal.</span><span class="sxs-lookup"><span data-stu-id="ea638-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="ea638-p108">Cree una conservación local y colóquela en el buzón eliminado temporalmente. En este ejemplo, no se especifica ninguna duración de la conservación. Esto significa que los elementos se conservarán de manera indefinida o hasta que la conservación se quite del buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ea638-p108">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="ea638-p109">También puede especificar una duración de la conservación cuando cree la conservación local. En este ejemplo se conservan elementos en el buzón inactivo durante aproximadamente 7 años.</span><span class="sxs-lookup"><span data-stu-id="ea638-p109">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="ea638-140">Después de unos minutos, ejecute uno de los siguientes comandos para comprobar que el buzón eliminado temporalmente es un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ea638-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="ea638-141">O bien</span><span class="sxs-lookup"><span data-stu-id="ea638-141">Or</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="ea638-142">Más información</span><span class="sxs-lookup"><span data-stu-id="ea638-142">More information</span></span>

<span data-ttu-id="ea638-p110">Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="ea638-p110">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>

- [<span data-ttu-id="ea638-145">Cambiar la duración de retención para un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ea638-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="ea638-146">Recuperar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ea638-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="ea638-147">Restaurar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ea638-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="ea638-148">[Eliminar un buzón inactivo](delete-an-inactive-mailbox.md) (quitando la retención)</span><span class="sxs-lookup"><span data-stu-id="ea638-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>