---
title: Configurar las opciones de versión estándar o dirigida
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de lanzamiento para actualizaciones de nuevos productos y características en el centro de administración Microsoft 365 de administración.
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593950"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="a56d1-103">Configurar las opciones de versión estándar o dirigida</span><span class="sxs-lookup"><span data-stu-id="a56d1-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a56d1-104">Las Microsoft 365 que se describen en este artículo se aplican a Microsoft 365, SharePoint Online y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a56d1-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="a56d1-105">Estas opciones de versión son formas dirigidas y de mayor esfuerzo para liberar cambios en Microsoft 365 pero no se pueden garantizar en todo momento ni para todas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a56d1-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="a56d1-106">No se aplican a Aplicaciones Microsoft 365, Skype Empresarial, Microsoft Teams y servicios relacionados.</span><span class="sxs-lookup"><span data-stu-id="a56d1-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="a56d1-107">Para obtener información acerca de las opciones de Aplicaciones Microsoft 365, vea [Overview of update channels for Aplicaciones Microsoft 365](/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="a56d1-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="a56d1-108">Con Microsoft 365, recibirá nuevas actualizaciones de productos y características a medida que estén disponibles en lugar de realizar actualizaciones costosas cada pocos años.</span><span class="sxs-lookup"><span data-stu-id="a56d1-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="a56d1-109">Puede administrar cómo su organización recibe estas actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a56d1-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="a56d1-110">Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a56d1-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="a56d1-111">Puede elegir que solo determinados individuos reciban las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a56d1-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="a56d1-112">También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde.</span><span class="sxs-lookup"><span data-stu-id="a56d1-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="a56d1-113">En este artículo se explican las distintas opciones de versión y cómo puede usarlas para su organización.</span><span class="sxs-lookup"><span data-stu-id="a56d1-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="a56d1-114">Cómo funciona: validación de versiones</span><span class="sxs-lookup"><span data-stu-id="a56d1-114">How it works - release validation</span></span>

<span data-ttu-id="a56d1-115">Cualquier nueva versión primero se prueba y valida por el equipo de características, después por todo el Microsoft 365 de características, seguido de todo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a56d1-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="a56d1-116">Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar.</span><span class="sxs-lookup"><span data-stu-id="a56d1-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="a56d1-117">En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves.</span><span class="sxs-lookup"><span data-stu-id="a56d1-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="a56d1-118">Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a56d1-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="a56d1-119">Las versiones se representan en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a56d1-119">The releases are pictured in the following figure.</span></span> 
  
![Liberar anillos de validación para Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="a56d1-121">Para actualizaciones significativas, los clientes son notificados inicialmente por [el Microsoft 365 guía básica](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="a56d1-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="a56d1-122">A medida que una actualización está más cerca de implementarse, se comunica a través Microsoft 365 [centro de mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="a56d1-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="a56d1-123">Necesita una cuenta Microsoft 365 o azure AD para tener acceso a su Centro de mensajes a través del [Centro de administración.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="a56d1-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="a56d1-124">Microsoft 365 usuarios del plan principal no tienen un centro de administración.</span><span class="sxs-lookup"><span data-stu-id="a56d1-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="a56d1-125">Versión estándar</span><span class="sxs-lookup"><span data-stu-id="a56d1-125">Standard release</span></span>

<span data-ttu-id="a56d1-126">Esta es la opción predeterminada en la que usted y sus usuarios reciben las actualizaciones más recientes cuando se lanzan ampliamente a todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="a56d1-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="a56d1-127">Una buena práctica es dejar a  la mayoría de los usuarios  en la versión estándar y a los profesionales de IT y usuarios avanzados en la versión dirigida para evaluar nuevas características y preparar equipos para admitir a los usuarios y ejecutivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="a56d1-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a56d1-128">Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar.</span><span class="sxs-lookup"><span data-stu-id="a56d1-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="a56d1-129">Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="a56d1-129">Targeted release</span></span>

<span data-ttu-id="a56d1-p106">Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.</span><span class="sxs-lookup"><span data-stu-id="a56d1-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a56d1-p107">Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="a56d1-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="a56d1-134">Versión dirigida para toda la organización</span><span class="sxs-lookup"><span data-stu-id="a56d1-134">Targeted release for entire organization</span></span>

<span data-ttu-id="a56d1-135">Si configura [la opción de versión en](#set-up-the-release-option-in-the-admin-center) el Centro de administración para esta opción, todos los usuarios tendrán la experiencia de versión dirigida.</span><span class="sxs-lookup"><span data-stu-id="a56d1-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="a56d1-136">Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción.</span><span class="sxs-lookup"><span data-stu-id="a56d1-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="a56d1-137">Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a56d1-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="a56d1-138">Versión dirigida para usuarios seleccionados</span><span class="sxs-lookup"><span data-stu-id="a56d1-138">Targeted release for selected users</span></span>

<span data-ttu-id="a56d1-139">Si configura [la opción de](#set-up-the-release-option-in-the-admin-center) versión en el Centro de administración para esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para recibir acceso anticipado a características y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="a56d1-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="a56d1-140">Ventajas de la Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="a56d1-140">Benefits of Targeted release</span></span>

<span data-ttu-id="a56d1-141">La versión dirigida permite a los administradores, los administradores de cambios o cualquier otra persona responsable de Microsoft 365 actualizaciones prepararse para los próximos cambios al permitirles:</span><span class="sxs-lookup"><span data-stu-id="a56d1-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="a56d1-142">Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a56d1-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="a56d1-143">Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a56d1-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="a56d1-144">Preparación de asistencia interna para los próximos cambios.</span><span class="sxs-lookup"><span data-stu-id="a56d1-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="a56d1-145">Revisión de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a56d1-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="a56d1-146">Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="a56d1-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="a56d1-147">Configurar la opción de versión en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="a56d1-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="a56d1-148">Puede cambiar el modo en que su organización recibe Microsoft 365 actualizaciones siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a56d1-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="a56d1-149">Debes ser un administrador global en Microsoft 365 participar.</span><span class="sxs-lookup"><span data-stu-id="a56d1-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a56d1-150">Los cambios siguientes pueden tardar hasta 24 horas en tener efecto en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a56d1-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="a56d1-151">Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada.</span><span class="sxs-lookup"><span data-stu-id="a56d1-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="a56d1-152">En el Centro de administración, vaya a la configuración Configuración organización y, en la pestaña Perfil de la  >  organización, elija **Preferencias de versión.** </span><span class="sxs-lookup"><span data-stu-id="a56d1-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="a56d1-153">Para deshabilitar la versión dirigida, seleccione **Versión estándar** y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a56d1-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="a56d1-154">Para habilitar la versión dirigida para todos los usuarios de la organización, seleccione **Versión dirigida** para todos los usuarios y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a56d1-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="a56d1-155">Para habilitar la versión dirigida para algunas personas de la organización, seleccione **Versión dirigida** para usuarios seleccionados y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a56d1-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="a56d1-156">Elija **Seleccionar usuarios** para agregar usuarios de uno en uno, o Upload **usuarios** para agregarlos en masa.</span><span class="sxs-lookup"><span data-stu-id="a56d1-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="a56d1-157">Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a56d1-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a56d1-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a56d1-158">Next steps</span></span>

<span data-ttu-id="a56d1-159">Descubra cómo administrar [mensajes en](/office365/admin/manage/message-center) su centro de [Microsoft 365 mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones acerca de las próximas Microsoft 365 actualizaciones y versiones.</span><span class="sxs-lookup"><span data-stu-id="a56d1-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="a56d1-160">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a56d1-160">Related content</span></span>

<span data-ttu-id="a56d1-161">[Unirse al Office Insider Program](https://insider.office.com/join/windows) (artículo)</span><span class="sxs-lookup"><span data-stu-id="a56d1-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
