---
title: Permitir que los miembros envíen como o envíen en nombre de un grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Obtenga información sobre cómo permitir a los miembros enviar correo electrónico como un grupo de Microsoft 365 o enviar correo electrónico en nombre de un grupo de Microsoft 365.
ms.openlocfilehash: b660131798e60182435a69f479411cdec948bc99
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662815"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="dbf56-103">Permitir que los miembros envíen como o envíen en nombre de un grupo</span><span class="sxs-lookup"><span data-stu-id="dbf56-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="dbf56-104">Un miembro de un grupo de Microsoft 365 al que se hayan concedido permisos para **Enviar como** o **enviar en nombre** de puede enviar correo electrónico como grupo o en nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="dbf56-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="dbf56-105">En este artículo se explica cómo un administrador puede establecer estos permisos.</span><span class="sxs-lookup"><span data-stu-id="dbf56-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="dbf56-106">Por ejemplo, si Nuria Bowen forma parte del grupo **Training** de Microsoft 365 y tiene permisos **Enviar como** en el grupo, si envía un correo electrónico como grupo, tendrá el mismo aspecto que el grupo de **formación** envió el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dbf56-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="dbf56-107">El permiso **enviar en nombre** de permite a un usuario enviar correo electrónico en nombre de un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbf56-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="dbf56-108">Por ejemplo, si Alex Wilber forma parte del grupo **marketing** de Microsoft 365 y tiene permisos **enviar en nombre** de y envía un correo electrónico como grupo, el correo electrónico parece enviado por **Alex Wilber en nombre de marketing**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf56-109">Puede configurar **Enviar como** o **enviar en nombre** de un usuario determinado, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="dbf56-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="dbf56-110">Si configura ambos, tendrá **como predeterminado enviar como**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="dbf56-111">Vea [Enviar correo electrónico desde o en nombre de un grupo de Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para obtener información sobre cómo usar Outlook y Outlook en la web para enviar correo electrónico desde un grupo.</span><span class="sxs-lookup"><span data-stu-id="dbf56-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="dbf56-112">Permitir que los miembros envíen correo electrónico como un grupo</span><span class="sxs-lookup"><span data-stu-id="dbf56-112">Allow members to send email as a group</span></span>

<span data-ttu-id="dbf56-113">En esta sección se explica cómo permitir que los usuarios envíen correo electrónico como un grupo en el [centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dbf56-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="dbf56-114">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="dbf56-115">Seleccione **Editar** ![ el icono editar grupo ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) en el grupo que desea permitir que los usuarios envíen como.  </span><span class="sxs-lookup"><span data-stu-id="dbf56-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="dbf56-116">Seleccione **delegación de grupo**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="dbf56-117">En la sección **Enviar como** , seleccione el **+** signo para agregar los usuarios que desea enviar como grupo.</span><span class="sxs-lookup"><span data-stu-id="dbf56-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Seleccione el signo más para agregar los usuarios que desee enviar como grupo de Microsoft 365](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="dbf56-119">Escriba para buscar o seleccionar un usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="dbf56-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="dbf56-120">Seleccione **Aceptar** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-120">Select **OK** and **Save**.</span></span>
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="dbf56-122">Permitir que los miembros envíen correo electrónico en nombre de un grupo</span><span class="sxs-lookup"><span data-stu-id="dbf56-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="dbf56-123">En esta sección se explica cómo permitir que los usuarios envíen correo electrónico en nombre de un grupo en el centro de administración de Exchange (EAC) en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dbf56-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="dbf56-124">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="dbf56-125">Seleccione **Editar** ![ el icono editar grupo ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) en el grupo que desea permitir que los usuarios envíen como.</span><span class="sxs-lookup"><span data-stu-id="dbf56-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="dbf56-126">Seleccione **delegación de grupo**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="dbf56-127">En la sección enviar en nombre de, seleccione el **+** signo para agregar los usuarios que desea enviar como grupo.</span><span class="sxs-lookup"><span data-stu-id="dbf56-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Seleccione el signo más para agregar los usuarios que desee enviar como grupo de Microsoft 365](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="dbf56-129">Escriba para buscar o seleccionar un usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="dbf56-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="dbf56-130">Seleccione **Aceptar** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dbf56-130">Select **OK** and **Save**.</span></span>
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="dbf56-132">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dbf56-132">Related articles</span></span>

[<span data-ttu-id="dbf56-133">Obtenga más información sobre los grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dbf56-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="dbf56-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="dbf56-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="dbf56-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="dbf56-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
