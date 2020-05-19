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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Obtenga información sobre cómo permitir que los usuarios compartan sus calendarios con usuarios externos para reuniones y citas. '
ms.openlocfilehash: f305505a9000b86c2c190e92f4c744c95f553e61
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280527"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="16660-103">Compartir calendarios con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="16660-103">Share calendars with external users</span></span>

<span data-ttu-id="16660-104">En muchas ocasiones, resulta necesario programar reuniones con personas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="16660-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="16660-105">Para simplificar el proceso de búsqueda de horas de reunión aceptables en todos los casos, Microsoft 365 permite que los calendarios estén disponibles para "usuarios externos", quienes necesitan ver el tiempo de disponibilidad pero no tienen cuentas de usuario para el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16660-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="16660-106">El uso compartido del calendario es una configuración global, lo que significa que el administrador puede habilitarla para todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="16660-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="16660-107">Una vez que el uso compartido está habilitado, los usuarios pueden usar Outlook Web App para compartir sus calendarios con cualquier persona dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="16660-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="16660-108">Las personas de la organización podrán ver el calendario compartido en paralelo con el suyo propio.</span><span class="sxs-lookup"><span data-stu-id="16660-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="16660-109">Las personas de fuera de la organización recibirán una dirección URL que pueden usar para ver el calendario.</span><span class="sxs-lookup"><span data-stu-id="16660-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="16660-110">Los usuarios deciden cuándo compartir, cuánto compartir y cuándo mantener sus calendarios privados.</span><span class="sxs-lookup"><span data-stu-id="16660-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16660-p103">Si quiere compartir calendarios con una organización que usa Exchange Server 2013 (una solución local), el administrador de Exchange tendrá que configurar una relación de autenticación con la nube. Esto se conoce como "federación" y debe cumplir unos requisitos mínimos de software. Vea [Uso compartido](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="16660-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="16660-114">Habilitar el uso compartido de calendarios mediante el centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="16660-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="16660-115">En el centro de administración, vaya a **configuración** de la \> **organización**configuración.</span><span class="sxs-lookup"><span data-stu-id="16660-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="16660-116">En la pestaña **servicios** , seleccione **calendario**.</span><span class="sxs-lookup"><span data-stu-id="16660-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="16660-117">En la página **calendario** que se abre, elija si desea permitir que los usuarios compartan sus calendarios con personas de fuera de la organización que tienen Microsoft 365 o Exchange.</span><span class="sxs-lookup"><span data-stu-id="16660-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="16660-118">Elija si desea permitir que los usuarios anónimos (usuarios sin credenciales de inicio de sesión) obtengan acceso a los calendarios mediante una invitación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="16660-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="16660-119">Elija qué tipo de información de calendario desea poner a disposición de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="16660-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="16660-120">Puede permitir toda la información o limitarla solo a la hora o la hora, el asunto y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="16660-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="16660-121">Invitar a personas a acceder a los calendarios</span><span class="sxs-lookup"><span data-stu-id="16660-121">Invite people to access calendars</span></span>

<span data-ttu-id="16660-p105">Una vez que está habilitado el uso compartido para el inquilino, los propietarios del calendario pueden invitar a usuarios específicos. Consulte [Compartir su calendario en Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="16660-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  
