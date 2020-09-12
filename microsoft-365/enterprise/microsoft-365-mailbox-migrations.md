---
title: Migraciones de buzones de Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artículo contiene un breve resumen sobre las migraciones de buzones de correo de Microsoft 365 y una lista de los cmdlets que se usan para las migraciones.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546803"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="0a75c-103">Migraciones de buzones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a75c-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="0a75c-104">Con una implementación híbrida basada en Exchange, los clientes pueden elegir entre mover buzones de Exchange locales a una organización de [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o mover buzones de correo de Exchange Online a una organización [local de Exchange](https://docs.microsoft.com/Exchange/exchange-server) .</span><span class="sxs-lookup"><span data-stu-id="0a75c-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="0a75c-105">Los lotes de migración se usan cuando se mueven buzones de correo entre organizaciones locales y de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0a75c-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="0a75c-106">Los clientes pueden revisar las estadísticas y otra información sobre las migraciones de buzones de correo con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0a75c-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="0a75c-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): proporciona estadísticas predeterminadas para un buzón de usuario, que incluye el estado, el tamaño del buzón, el tamaño del buzón de archivo y el porcentaje completado.</span><span class="sxs-lookup"><span data-stu-id="0a75c-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="0a75c-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): proporciona una lista resumida de los objetos de buzón y los atributos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0a75c-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="0a75c-109">[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): proporciona una lista de objetos existentes habilitados para correo, como buzones de correo, usuarios de correo, contactos y grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="0a75c-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="0a75c-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): proporciona un estado detallado de una migración de buzones de correo en curso.</span><span class="sxs-lookup"><span data-stu-id="0a75c-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="0a75c-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): proporciona información sobre los usuarios de migración y movimiento de buzones.</span><span class="sxs-lookup"><span data-stu-id="0a75c-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="0a75c-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): proporciona información sobre el estado del lote de migración actual.</span><span class="sxs-lookup"><span data-stu-id="0a75c-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="0a75c-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): proporciona información detallada sobre el estado de la migración de un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="0a75c-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="0a75c-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): proporciona información acerca de los buzones de correo, como el tamaño, el número de mensajes y la hora del último acceso.</span><span class="sxs-lookup"><span data-stu-id="0a75c-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="0a75c-115">Para obtener más información acerca de los cmdlets, consulte [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0a75c-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
