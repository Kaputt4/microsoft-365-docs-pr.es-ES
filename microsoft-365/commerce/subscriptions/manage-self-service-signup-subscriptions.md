---
title: Administrar suscripciones de registro de autoservicio
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Obtenga información sobre cómo administrar suscripciones de registro de autoservicio gratuitas para su organización.
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536075"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="a4809-103">Administrar suscripciones de registro de autoservicio</span><span class="sxs-lookup"><span data-stu-id="a4809-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="a4809-104">¿Qué son las suscripciones de registro de autoservicio?</span><span class="sxs-lookup"><span data-stu-id="a4809-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="a4809-105">Hay un número limitado de suscripciones de registro de autoservicio gratuitas disponibles para que los usuarios de su organización puedan registrarse.</span><span class="sxs-lookup"><span data-stu-id="a4809-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="a4809-106">Un usuario solo puede registrarse y usar una suscripción de registro de autoservicio por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="a4809-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="a4809-107">Las suscripciones de registro de autoservicio se administran bloqueando la suscripción de los usuarios y eliminando las suscripciones gratuitas para las que los usuarios se han registrado.</span><span class="sxs-lookup"><span data-stu-id="a4809-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="a4809-108">Para obtener más información sobre el registro de autoservicio y las suscripciones disponibles, vea [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="a4809-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="a4809-109">Ver una lista de suscripciones de registro de autoservicio</span><span class="sxs-lookup"><span data-stu-id="a4809-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="a4809-110">En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="a4809-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a4809-111">En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**.</span><span class="sxs-lookup"><span data-stu-id="a4809-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="a4809-112">Se muestra una lista de todas las suscripciones de registro de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="a4809-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="a4809-113">¿En qué se diferencian estas suscripciones de las suscripciones de compra sin servicio?</span><span class="sxs-lookup"><span data-stu-id="a4809-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="a4809-114">Las suscripciones de registro de autoservicio son gratuitas y están disponibles para una lista más grande de productos que las suscripciones de compra de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="a4809-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="a4809-115">Cuando un usuario se inscribe en una suscripción de compra de autoservicio, es responsable de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="a4809-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="a4809-116">Las suscripciones de compra de autoservicio solo están disponibles para productos de Power Platform (Power BI, Power Apps y Power Automate), Project y Visio.</span><span class="sxs-lookup"><span data-stu-id="a4809-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="a4809-117">Para obtener más información, consulta Preguntas más frecuentes [sobre la compra de autoservicio.](self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="a4809-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.yml).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="a4809-118">Impedir que los usuarios se inscriba</span><span class="sxs-lookup"><span data-stu-id="a4809-118">Block users from signing up</span></span>

<span data-ttu-id="a4809-119">Use el cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) con el parámetro **AllowAdHocSubscriptions** para controlar si los usuarios pueden registrarse en suscripciones de registro de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="a4809-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="a4809-120">Para obtener más información, [vea How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="a4809-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="a4809-121">Eliminar una suscripción de registro de autoservicio</span><span class="sxs-lookup"><span data-stu-id="a4809-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4809-122">Al eliminar una suscripción de registro de autoservicio, se bloquea a todos los usuarios el acceso a sus datos y correo electrónico y se eliminan todos los datos y el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a4809-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="a4809-123">En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="a4809-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a4809-124">En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**.</span><span class="sxs-lookup"><span data-stu-id="a4809-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="a4809-125">Seleccione la suscripción de registro de autoservicio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="a4809-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="a4809-126">En la página detalles de la suscripción, en la sección **Suscripciones y configuración de pago,** seleccione Eliminar **suscripción**.</span><span class="sxs-lookup"><span data-stu-id="a4809-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="a4809-127">En el **panel Eliminar suscripción,** active la casilla y, a continuación, **seleccione Eliminar suscripción.**</span><span class="sxs-lookup"><span data-stu-id="a4809-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="a4809-128">Tengo una suscripción de registro de autoservicio que bloquea la eliminación de directorios</span><span class="sxs-lookup"><span data-stu-id="a4809-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="a4809-129">Los productos de registro de autoservicio para los que los usuarios individuales pueden registrarse también crean un usuario invitado para la autenticación en el directorio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4809-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="a4809-130">Para evitar la pérdida de datos, estos productos de autoservicio bloquean las eliminaciones de directorios hasta que se eliminan completamente del directorio.</span><span class="sxs-lookup"><span data-stu-id="a4809-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="a4809-131">El administrador de Azure AD solo las puede eliminar. Para obtener más información, vea [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="a4809-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
