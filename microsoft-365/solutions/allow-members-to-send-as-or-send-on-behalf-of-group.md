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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Obtenga información sobre cómo permitir a los miembros del grupo enviar correo electrónico como un grupo de Microsoft 365 o enviar correo electrónico en nombre de un grupo de Microsoft 365.
ms.openlocfilehash: cc0a9472f127fae94d77f618ed7347d844879ba8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904749"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="740de-103">Permitir que los miembros envíen como o envíen en nombre de un grupo</span><span class="sxs-lookup"><span data-stu-id="740de-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="740de-104">Un miembro de un grupo de Microsoft  365 al que se han concedido permisos Enviar como o Enviar en nombre puede enviar correo electrónico como grupo o en nombre del grupo. </span><span class="sxs-lookup"><span data-stu-id="740de-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="740de-105">(No se pueden conceder estos permisos a los invitados del grupo).</span><span class="sxs-lookup"><span data-stu-id="740de-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="740de-106">En este artículo se explica cómo un administrador global o de Exchange puede establecer estos permisos.</span><span class="sxs-lookup"><span data-stu-id="740de-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="740de-107">Por ejemplo, si Megan Bowen forma parte del grupo **De** aprendizaje de Microsoft 365 y tiene permisos Enviar como  en el grupo, si envía un correo electrónico como grupo, parecerá que el grupo de aprendizaje envió el correo electrónico. </span><span class="sxs-lookup"><span data-stu-id="740de-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="740de-108">El **permiso Enviar en nombre** permite a un usuario enviar correo electrónico en nombre de un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="740de-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="740de-109">Por ejemplo, si Alex Wilber forma parte del grupo **marketing**  de Microsoft 365 y tiene permisos Enviar en nombre y envía un correo electrónico como grupo, el correo electrónico parece que lo envió **Alex Wilber en** nombre de Marketing .</span><span class="sxs-lookup"><span data-stu-id="740de-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="740de-110">Puede configurar **Enviar como** o Enviar en **nombre** de un usuario determinado, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="740de-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="740de-111">Si configura ambos, se establecerá de forma predeterminada **en Enviar como**.</span><span class="sxs-lookup"><span data-stu-id="740de-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="740de-112">Consulte Enviar correo electrónico desde o en nombre de un grupo de [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para obtener información sobre cómo usar Outlook y Outlook en la Web para enviar correo electrónico desde un grupo.</span><span class="sxs-lookup"><span data-stu-id="740de-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="740de-113">Permitir que los miembros envíen correo electrónico como grupo</span><span class="sxs-lookup"><span data-stu-id="740de-113">Allow members to send email as a group</span></span>

<span data-ttu-id="740de-114">En esta sección se explica cómo permitir a los usuarios enviar correo electrónico como grupo en el Centro de administración de [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="740de-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="740de-115">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange,</a>vaya a Grupos de  \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="740de-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="740de-116">Seleccione **Editar icono** editar grupo en el grupo que desea permitir que los usuarios envíen ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) como.  </span><span class="sxs-lookup"><span data-stu-id="740de-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="740de-117">Seleccione **delegación de grupo**.</span><span class="sxs-lookup"><span data-stu-id="740de-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="740de-118">En la **sección Enviar como,** seleccione el signo para agregar los **+** usuarios que desea enviar como grupo.</span><span class="sxs-lookup"><span data-stu-id="740de-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Captura de pantalla del cuadro de diálogo Enviar como](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="740de-120">Escriba para buscar o seleccionar un usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="740de-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="740de-121">Seleccione **Aceptar** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="740de-121">Select **OK** and **Save**.</span></span>
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="740de-123">Permitir que los miembros envíen correo electrónico en nombre de un grupo</span><span class="sxs-lookup"><span data-stu-id="740de-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="740de-124">En esta sección se explica cómo permitir a los usuarios enviar correo electrónico en nombre de un grupo en el Centro de administración de Exchange (EAC) en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="740de-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="740de-125">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange,</a>vaya a Grupos de  \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="740de-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="740de-126">Seleccione **Editar icono** editar grupo en el grupo que desea permitir que los usuarios envíen ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) como.</span><span class="sxs-lookup"><span data-stu-id="740de-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="740de-127">Seleccione **delegación de grupo**.</span><span class="sxs-lookup"><span data-stu-id="740de-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="740de-128">En la sección Enviar en nombre, seleccione el signo para agregar los **+** usuarios que desea enviar como grupo.</span><span class="sxs-lookup"><span data-stu-id="740de-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Captura de pantalla del envío en nombre del cuadro de diálogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="740de-130">Escriba para buscar o seleccionar un usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="740de-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="740de-131">Seleccione **Aceptar** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="740de-131">Select **OK** and **Save**.</span></span>
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="740de-133">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="740de-133">Related articles</span></span>

[<span data-ttu-id="740de-134">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="740de-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="740de-135">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="740de-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="740de-136">Más información sobre los grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="740de-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="740de-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="740de-137">Add-RecipientPermission</span></span>](/powershell/module/exchange/add-recipientpermission)

[<span data-ttu-id="740de-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="740de-138">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup)