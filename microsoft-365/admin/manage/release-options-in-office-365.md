---
title: Configurar las opciones estándar o de lanzamiento de destino
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de lanzamiento de actualizaciones de productos y características nuevas en el centro de administración de Microsoft 365.
ms.openlocfilehash: 648be8ca5d3c7aae93ed868972bc59b32ba87987
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560720"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="a7905-103">Configurar las opciones estándar o de lanzamiento de destino</span><span class="sxs-lookup"><span data-stu-id="a7905-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a7905-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="a7905-104">The admin center is changing.</span></span> <span data-ttu-id="a7905-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a7905-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="a7905-106">Las actualizaciones de Microsoft 365 descritas en este artículo se aplican a Microsoft 365, SharePoint Online y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7905-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="a7905-107">Estas opciones de versión están dirigidas a los mejores esfuerzos para publicar cambios en Microsoft 365, pero no se pueden garantizar en todo momento ni para todas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a7905-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="a7905-108">No se aplican a Skype empresarial, Microsoft Teams y los servicios relacionados.</span><span class="sxs-lookup"><span data-stu-id="a7905-108">They do not apply to Skype for Business, Microsoft Teams, and related services.</span></span>

<span data-ttu-id="a7905-109">Con Microsoft 365, recibirá nuevas actualizaciones de productos y características a medida que estén disponibles en lugar de realizar actualizaciones costosas cada pocos años.</span><span class="sxs-lookup"><span data-stu-id="a7905-109">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="a7905-110">Puede administrar cómo su organización recibe estas actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a7905-110">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="a7905-111">Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a7905-111">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="a7905-112">Puede elegir que solo determinados individuos reciban las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a7905-112">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="a7905-113">También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde.</span><span class="sxs-lookup"><span data-stu-id="a7905-113">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="a7905-114">En este artículo se explican las diferentes opciones de versión y cómo se pueden usar para la organización.</span><span class="sxs-lookup"><span data-stu-id="a7905-114">This article explains the different release options and how you can use them for your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="a7905-115">Para obtener información sobre los canales de actualización para aplicaciones, vea [información general sobre los canales de actualización para las aplicaciones de Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="a7905-115">For information about update channels for applications, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="a7905-116">Cómo funciona: validación de versiones</span><span class="sxs-lookup"><span data-stu-id="a7905-116">How it works - release validation</span></span>

<span data-ttu-id="a7905-117">Las nuevas versiones se prueban y validan por primera vez por el equipo de características y, a continuación, por todo el equipo de características de Microsoft 365, seguidos de todo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7905-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="a7905-118">Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar.</span><span class="sxs-lookup"><span data-stu-id="a7905-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="a7905-119">En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves.</span><span class="sxs-lookup"><span data-stu-id="a7905-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="a7905-120">Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a7905-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="a7905-121">Las versiones se representan en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a7905-121">The releases are pictured in the following figure.</span></span> 
  
![Liberar timbres de validación para Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="a7905-123">Para las actualizaciones importantes, el [plan de desarrollo de 365 Microsoft](https://products.office.com/business/office-365-roadmap)notificará inicialmente a los clientes.</span><span class="sxs-lookup"><span data-stu-id="a7905-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="a7905-124">A medida que se acerca la actualización, se comunica a través del centro de [mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="a7905-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="a7905-125">Necesita una cuenta de Microsoft 365 o de Azure AD para obtener acceso al centro de mensajes a través del [centro de administración](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a7905-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="a7905-126">Los usuarios del plan de inicio de Microsoft 365 no tienen un centro de administración.</span><span class="sxs-lookup"><span data-stu-id="a7905-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="a7905-127">Versión estándar</span><span class="sxs-lookup"><span data-stu-id="a7905-127">Standard release</span></span>

<span data-ttu-id="a7905-128">Esta es la opción predeterminada en la que usted y sus usuarios reciben las actualizaciones más recientes cuando se publican ampliamente para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="a7905-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="a7905-129">Un procedimiento recomendado es dejar la mayoría de los usuarios en **versiones estándar** y profesionales de ti y usuarios avanzados en el **lanzamiento de destino** para evaluar nuevas características y preparar a Microsoft Teams para que admitan usuarios y ejecutivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="a7905-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a7905-130">Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar.</span><span class="sxs-lookup"><span data-stu-id="a7905-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="a7905-131">Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="a7905-131">Targeted release</span></span>

<span data-ttu-id="a7905-p107">Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.</span><span class="sxs-lookup"><span data-stu-id="a7905-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a7905-p108">Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="a7905-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="a7905-136">Versión dirigida para toda la organización</span><span class="sxs-lookup"><span data-stu-id="a7905-136">Targeted release for entire organization</span></span>

<span data-ttu-id="a7905-137">Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, todos los usuarios obtendrán la experiencia de la versión de destino.</span><span class="sxs-lookup"><span data-stu-id="a7905-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="a7905-138">Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción.</span><span class="sxs-lookup"><span data-stu-id="a7905-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="a7905-139">Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7905-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="a7905-140">Versión dirigida para usuarios seleccionados</span><span class="sxs-lookup"><span data-stu-id="a7905-140">Targeted release for selected users</span></span>

<span data-ttu-id="a7905-141">Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para que obtengan acceso anticipado a características y funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a7905-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="a7905-142">Ventajas de la Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="a7905-142">Benefits of Targeted release</span></span>

<span data-ttu-id="a7905-143">La versión dirigida permite que los administradores, administradores de cambios o cualquier otra persona responsable de las actualizaciones de Microsoft 365 se prepare para preparar los próximos cambios al permitirles:</span><span class="sxs-lookup"><span data-stu-id="a7905-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="a7905-144">Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7905-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="a7905-145">Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a7905-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="a7905-146">Preparación de asistencia interna para los próximos cambios.</span><span class="sxs-lookup"><span data-stu-id="a7905-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="a7905-147">Revisión de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a7905-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="a7905-148">Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="a7905-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="a7905-149">Configurar la opción de lanzamiento en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="a7905-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="a7905-150">Puede cambiar el modo en que su organización recibe las actualizaciones de Microsoft 365 mediante los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="a7905-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="a7905-151">Debe ser un administrador global de Microsoft 365 para participar.</span><span class="sxs-lookup"><span data-stu-id="a7905-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a7905-152">Los cambios siguientes pueden tardar hasta 24 horas en surtir efecto en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7905-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="a7905-153">Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada.</span><span class="sxs-lookup"><span data-stu-id="a7905-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="a7905-154">En el centro de administración, vaya a la configuración de la organización de **configuración**  >  **Org Setting**y, en la pestaña Perfil de la **organización** , elija **Opciones de lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="a7905-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="a7905-155">Para deshabilitar la versión dirigida, seleccione **versión estándar**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a7905-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="a7905-156">Para habilitar la versión dirigida para todos los usuarios de su organización, seleccione **versión dirigida para todos**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a7905-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="a7905-157">Para habilitar la versión dirigida para algunas personas de su organización, seleccione **versión dirigida para los usuarios seleccionados**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a7905-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="a7905-158">Elija **Seleccionar usuarios** para agregar usuarios de uno en uno o **cargar usuarios** para agregarlos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="a7905-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="a7905-159">Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a7905-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="a7905-160">Más información</span><span class="sxs-lookup"><span data-stu-id="a7905-160">Learn more</span></span>

<span data-ttu-id="a7905-161">Descubra cómo [administrar mensajes](https://docs.microsoft.com/office365/admin/manage/message-center) en el [centro de mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones sobre próximas actualizaciones y versiones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7905-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
