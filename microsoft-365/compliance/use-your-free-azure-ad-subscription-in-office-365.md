---
title: Usar su suscripción gratuita de Azure Active Directory en Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Obtenga información sobre cómo obtener acceso a Azure Active Directory, que se incluye en la suscripción de pago de Office 365 de su organización.
ms.openlocfilehash: fb1e2586c0b21c72084d7120b8735fccccd1a004
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710499"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="32388-103">Usar su suscripción gratuita de Azure Active Directory en Office 365</span><span class="sxs-lookup"><span data-stu-id="32388-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="32388-p101">Si su organización tiene una suscripción de pago a Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite u otros servicios Microsoft, ya tiene una suscripción gratuita a Microsoft Azure Active Directory. Los administradores pueden usar Azure AD para crear y administrar cuentas de usuario y grupo. Para usar Azure AD, vaya a Azure Portal e inicie sesión con su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32388-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="32388-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="32388-107">Before you begin</span></span>

<span data-ttu-id="32388-p102">Use una sesión de exploración privada (no una sesión normal) para obtener acceso a Azure Portal (en el paso 1 que se muestra a continuación), esto evitará que las credenciales con las que inició sesión se usen en Azure. Para abrir una sesión de navegación privada:</span><span class="sxs-lookup"><span data-stu-id="32388-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this prevents the credentials that you're currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="32388-110">En Microsoft Edge (versión heredada), Internet Explorer o Mozilla FireFox, presione `CTRL+SHIFT+P`.</span><span class="sxs-lookup"><span data-stu-id="32388-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="32388-111">En Microsoft Edge (versión más reciente) o Google Chrome, presione `CTRL+SHIFT+N`.</span><span class="sxs-lookup"><span data-stu-id="32388-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="32388-112">Obtener acceso a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="32388-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="32388-113">Vaya a [portal.azure.com](https://portal.azure.com) e inicie sesión con su cuenta profesional o educativa de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32388-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="32388-114">En el panel de navegación izquierdo de Azure Portal, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="32388-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![En el panel de navegación izquierdo de Azure Portal, haga clic en Azure Active Directory.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="32388-116">Se mostrará el Centro de administración de **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="32388-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="32388-117">Más información</span><span class="sxs-lookup"><span data-stu-id="32388-117">More information</span></span>

- <span data-ttu-id="32388-118">Una suscripción gratuita de Azure Active Directory no incluye el informe de actividad de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="32388-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="32388-119">Para grabar la actividad de inicio de sesión (que puede resultar útil en caso de una violación de datos), necesita una suscripción de Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="32388-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="32388-120">Para obtener más información, consulte [¿Durante cuánto tiempo Azure AD almacena los datos?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)</span><span class="sxs-lookup"><span data-stu-id="32388-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="32388-121">También puede tener acceso al centro de administración de **Azure Active Directory** desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32388-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="32388-122">En el panel de navegación de la izquierda del centro de administración de Microsoft 365, haga clic en **Centros de administración** \> **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="32388-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="32388-123">Para obtener información sobre cómo administrar usuarios y grupos, así como realizar otras tareas de administración de directorio, vea [Administrar el directorio de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span><span class="sxs-lookup"><span data-stu-id="32388-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
