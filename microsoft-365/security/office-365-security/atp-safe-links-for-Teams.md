---
title: Vínculos seguros de Office 365 ATP para equipos, safelinks, vínculos seguros, bloquear vínculos malintencionados, Office 365 ATP, equipos vínculos seguros, impedir que los usuarios haga clic en vínculos no válidos, vínculos malintencionados
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Los equipos ahora tendrán acceso a vínculos seguros en el momento de hacer clic. Si usa chats 1-en-1 chats, entre grupos o en canales y pestañas, si tiene una suscripción a Office 365 ATP, tendrá la posibilidad de habilitar y usar esta característica de seguridad.
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212550"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="ea2b2-104">Vínculos seguros de Office 365 en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea2b2-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea2b2-105">Esta característica se encuentra en **versión preliminar pública** para los clientes del programa de adopción de tecnología de Microsoft Teams (TAP) a partir del 28 de febrero de 2020.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="ea2b2-106">Esta nota se quitará del artículo cuando vínculos seguros para Teams esté más disponible.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="ea2b2-107">Microsoft Teams, una aplicación basada en la nube de Office 365 para administrar el trabajo, ya usa datos adjuntos seguros (para Office 365), pero ahora tendrá acceso a vínculos seguros en el momento de hacer clic.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="ea2b2-108">Si usa chats 1-en-1 chats, entre grupos o en canales y pestañas, si tiene una suscripción a Office 365 ATP, tendrá la posibilidad de habilitar y usar esta medida de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="ea2b2-109">Aquí se muestra cómo funciona:</span><span class="sxs-lookup"><span data-stu-id="ea2b2-109">Here's how it works:</span></span> 

1. <span data-ttu-id="ea2b2-110">Al iniciar la aplicación Teams, Office 365 se asegurará de que el usuario pertenece a una organización que tiene Office 365 ATP y que el usuario forma parte de una directiva de vínculos seguros activa con la protección habilitada para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="ea2b2-111">Si las opciones anteriores son verdaderas, las direcciones URL se validarán en el momento de hacer clic en chats, chats de grupo, canales y en las pestañas para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

> [!NOTE]
> <span data-ttu-id="ea2b2-112">Vínculos seguros protege a los usuarios de los vínculos enviados por los usuarios invitados, los usuarios federados y los usuarios del inquilino.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-112">Safe links safeguards users from links sent by Guest users, Federated users, tenant users.</span></span> <span data-ttu-id="ea2b2-113">Si el usuario que ha iniciado sesión tiene vínculos seguros habilitados para Microsoft Teams, se aplicarán protecciones de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-113">If the user logged in has safe links for Teams enabled, then safe links protections will apply.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="ea2b2-114">¿Qué van a experimentar los usuarios?</span><span class="sxs-lookup"><span data-stu-id="ea2b2-114">What will users experience?</span></span> 

<span data-ttu-id="ea2b2-115">Todos los usuarios protegidos tendrán esta experiencia con direcciones URL peligrosas:</span><span class="sxs-lookup"><span data-stu-id="ea2b2-115">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="ea2b2-116">Si se hizo clic en el vínculo desde una conversación de Microsoft Teams, un chat de grupo o desde canales, una página se representará en el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-116">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="ea2b2-117">Si se hizo clic en el vínculo desde una pestaña anclada, la página aparecerá en la interfaz gráfica de usuario de Microsoft Teams dentro de esa pestaña y la opción para abrirla en el explorador se deshabilitará por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-117">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="ea2b2-118">Este usuario se bloqueará para continuar con el sitio de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-118">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="ea2b2-119">Si el usuario que envió el vínculo no está protegido por Office 365 ATP, es libre de hacer clic en la dirección URL de su equipo y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-119">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="ea2b2-120">Esto hace que sea doblemente importante para que los administradores de Office 365 sepan que sus usuarios protegidos son y deben ser.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-120">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Una página vínculos seguros para equipos que informa de un vínculo malintencionado y bloquea el tránsito a la página.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="ea2b2-122">Si hace clic en el botón *volver atrás* de esta página en Microsoft Teams, se cerrará (o puede dar como resultado una página en blanco que los usuarios pueden cerrar).</span><span class="sxs-lookup"><span data-stu-id="ea2b2-122">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="ea2b2-123">Sin embargo, si vuelve a hacer clic en el vínculo, tendrá que volver a evaluar la reputación del sitio para que vuelva a aparecer esta página.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-123">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="ea2b2-124">Algunos administradores de Office 365 habilitarán el mensaje **continuar de todas formas** en la página de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-124">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="ea2b2-125">Sin embargo, si vínculos seguros mide la reputación de un sitio y descubre que carece de él, no se debe emprender ningún otro clic.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-125">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="ea2b2-126">No se recomienda que los usuarios omitan las medidas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-126">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="ea2b2-127">Valore esto en sus consideraciones antes de habilitar la continuación de todas formas.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-127">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

