---
title: Enviar correo electrónico como una lista de distribución
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Envíe correo electrónico como una lista de distribución en Microsoft 365 para que cuando un miembro responda a un mensaje parezca que es de la lista de distribución.
ms.openlocfilehash: 01bff7e1d2515670c5a6faa199355e7de591f1fb
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624542"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="8cdfd-103">Enviar correo electrónico como una lista de distribución</span><span class="sxs-lookup"><span data-stu-id="8cdfd-103">Send email as a distribution list</span></span>

<span data-ttu-id="8cdfd-104">En Microsoft 365, puede enviar correo electrónico como una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="8cdfd-105">Cuando una persona que es miembro de la lista de distribución responde a un mensaje enviado a la lista de distribución, el correo electrónico parece ser de la lista de distribución, no del usuario individual.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="8cdfd-106">En este tema se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8cdfd-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8cdfd-107">Before you begin</span></span>

<span data-ttu-id="8cdfd-108">Antes de realizar estos pasos, asegúrese de que se ha agregado a una lista de distribución Microsoft 365 y de que se le ha concedido permiso Enviar como permiso.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="8cdfd-109">**Administradores:** asegúrese de que ha seguido los pasos descritos en los temas Agregar un usuario o contacto de [Microsoft 365 a](../email/add-user-or-contact-to-distribution-list.md) una lista y Permitir que los miembros envíen correo electrónico como un grupo de [Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) y agregue las personas correctas a la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="8cdfd-110">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="8cdfd-110">Outlook on the web</span></span>

1. <span data-ttu-id="8cdfd-111">Abra Outlook en la web y vaya a la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="8cdfd-112">Abra un mensaje que se envió a la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="8cdfd-113">Seleccione **Responder**.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="8cdfd-114">En la parte inferior del mensaje, seleccione **Más** \> **mostrar de**.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="8cdfd-115">![Seleccione Más y, a continuación, elija Mostrar desde](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="8cdfd-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="8cdfd-116">Haga clic con el botón secundario en la dirección De , como `Ina@weewalter.me` - y elija **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="8cdfd-117">![Quitar el alias FROM](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="8cdfd-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="8cdfd-118">A continuación, escriba la dirección de la lista de distribución como support@contoso.com y envíe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="8cdfd-119">La próxima vez que responda desde la lista de distribución, su dirección aparecerá como una opción en la **lista** De.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="8cdfd-120">![Aparece el alias del buzón compartido](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="8cdfd-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="8cdfd-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="8cdfd-121">Outlook</span></span>

1. <span data-ttu-id="8cdfd-122">Abra Outlook cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="8cdfd-123">Redacción de un nuevo correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-123">Compose a New Email.</span></span> <span data-ttu-id="8cdfd-124">Haga clic en **el campo De** y seleccione Otra dirección de correo **electrónico**.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="8cdfd-125">Si no ve el campo De, vaya a **Opciones** y seleccione **De en** la sección Mostrar campos.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="8cdfd-126">Seleccione la **dirección lista de** distribución de la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="8cdfd-127">Envíe el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8cdfd-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="8cdfd-128">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="8cdfd-128">Related content</span></span>

<span data-ttu-id="8cdfd-129">[Crear, editar o eliminar un grupo](../email/create-edit-or-delete-a-security-group.md) de seguridad en el centro Microsoft 365 administración (artículo)</span><span class="sxs-lookup"><span data-stu-id="8cdfd-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="8cdfd-130">[Colaboración de correo](../email/email-collaboration.md) electrónico (artículo)</span><span class="sxs-lookup"><span data-stu-id="8cdfd-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
[<span data-ttu-id="8cdfd-131">Agregar un usuario o contacto a un grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="8cdfd-131">Add a user or contact to a distribution group</span></span>](../email/add-user-or-contact-to-distribution-list.md)