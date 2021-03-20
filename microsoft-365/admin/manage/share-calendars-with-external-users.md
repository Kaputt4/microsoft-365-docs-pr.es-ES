---
title: Compartir calendarios con usuarios externos
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Obtenga información sobre cómo permitir que los usuarios compartan sus calendarios con usuarios externos para reuniones y citas.
ms.openlocfilehash: 5fc80965ae277e66dfbf73de80618dec03d26759
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915055"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="a7422-103">Compartir calendarios con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a7422-103">Share calendars with external users</span></span>

<span data-ttu-id="a7422-104">A veces es necesario que los usuarios programe reuniones con personas ajenas a la organización.</span><span class="sxs-lookup"><span data-stu-id="a7422-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="a7422-105">Para simplificar el proceso de búsqueda de horas de reunión comunes, Microsoft 365 permite que los calendarios estén disponibles para estas personas.</span><span class="sxs-lookup"><span data-stu-id="a7422-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="a7422-106">Se trata de personas que necesitan ver tiempos de disponibilidad para los usuarios de la organización, pero que no tienen cuentas de usuario para su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7422-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="a7422-107">Puede habilitar el uso compartido de calendarios para todos los usuarios de su organización en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7422-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a7422-108">Una vez habilitado el uso compartido, los usuarios pueden usar Outlook Web App para compartir sus calendarios con cualquier persona dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7422-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="a7422-109">Los usuarios de la organización pueden ver el calendario compartido junto con su propio calendario.</span><span class="sxs-lookup"><span data-stu-id="a7422-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="a7422-110">Las personas de fuera de la organización recibirán una dirección URL que pueden usar para ver el calendario.</span><span class="sxs-lookup"><span data-stu-id="a7422-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="a7422-111">Los usuarios de la organización deciden cuándo compartir y cuánto compartir.</span><span class="sxs-lookup"><span data-stu-id="a7422-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="a7422-112">Si quiere compartir calendarios con una organización que usa Exchange Server 2013 (una solución local), el administrador de Exchange tendrá que configurar una relación de autenticación con la nube.</span><span class="sxs-lookup"><span data-stu-id="a7422-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="a7422-113">Esto se conoce como federación y debe cumplir los requisitos mínimos de software.</span><span class="sxs-lookup"><span data-stu-id="a7422-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="a7422-114">Vea [Uso compartido](/exchange/sharing-exchange-2013-help) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7422-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a7422-115">Habilitar el uso compartido de calendarios con el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7422-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a7422-116">En el Centro de administración, vaya a **Configuración configuración** de \> **la organización**.</span><span class="sxs-lookup"><span data-stu-id="a7422-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="a7422-117">En la **pestaña Servicios,** seleccione **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="a7422-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="a7422-118">En la **página** Calendario, elija si desea permitir que los usuarios compartan sus calendarios con personas fuera de su organización que tengan Microsoft 365 o Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7422-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="a7422-119">Elige si quieres permitir que los usuarios anónimos (usuarios sin credenciales) accedan a los calendarios a través de una invitación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7422-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="a7422-120">Elija qué tipo de información de calendario desea que esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a7422-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="a7422-121">Puede permitir toda la información o limitarla solo a tiempo o solo tiempo, asunto y ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7422-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="a7422-122">Invitar a personas a acceder a los calendarios</span><span class="sxs-lookup"><span data-stu-id="a7422-122">Invite people to access calendars</span></span>

<span data-ttu-id="a7422-123">Una vez habilitado el uso compartido, los propietarios del calendario pueden extender invitaciones a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a7422-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="a7422-124">Consulte [Compartir su calendario en Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="a7422-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>