---
title: Configurar las opciones de las versiones estándar o dirigida de Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de lanzamiento de actualizaciones de productos y características nuevas en el centro de administración de Microsoft 365.
ms.openlocfilehash: d6c2eab340f4401fb31e4d9e814fbd326573569a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361805"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="6dfc8-103">Configurar las opciones de las versiones estándar o dirigida de Office 365</span><span class="sxs-lookup"><span data-stu-id="6dfc8-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="6dfc8-p101">Con Office 365, recibe actualizaciones de productos y características nuevas desde que se encuentran disponibles en vez de realizar costosas actualizaciones cada pocos años. Puede administrar cómo su organización recibe estas actualizaciones. Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar. Puede elegir que solo determinados individuos reciban las actualizaciones. También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde. En este artículo se explican las diferentes opciones de versiones y cómo puede usarlas para su organización.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6dfc8-p102">Las actualizaciones de Office 365 descritas en este artículo se aplican a Office 365, a SharePoint Online y a Exchange Online. No se aplican a Skype Empresarial ni a los servicios relacionados. Estas opciones de versiones son la forma más eficaz y precisa de publicar cambios para Office 365, pero no pueden garantizarse en todas las ocasiones ni en todas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="6dfc8-113">Cómo funciona: validación de versiones</span><span class="sxs-lookup"><span data-stu-id="6dfc8-113">How it works - release validation</span></span>

<span data-ttu-id="6dfc8-114">Las nuevas versiones se prueban y validan por primera vez por el equipo de características y, a continuación, por todo el equipo de características de Office 365, seguidos de todo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="6dfc8-115">Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="6dfc8-116">En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="6dfc8-117">Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="6dfc8-118">Las versiones se representan en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-118">The releases are pictured in the following figure.</span></span> 
  
![Liberar timbres de validación para Office 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="6dfc8-120">Para las actualizaciones importantes, los clientes de Office se notifican inicialmente mediante el [plan de desarrollo de Microsoft 365](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="6dfc8-121">A medida que se acerca la actualización, se comunica a través de su [centro de mensajes de Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="6dfc8-122">Necesita una cuenta de Office 365 o de Azure AD para obtener acceso al centro de mensajes a través del [centro de administración](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="6dfc8-123">Los usuarios del plan de inicio de Office 365 no tienen un centro de administración.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="6dfc8-124">Versión estándar</span><span class="sxs-lookup"><span data-stu-id="6dfc8-124">Standard release</span></span>

<span data-ttu-id="6dfc8-125">Esta es la opción predeterminada en la que usted y sus usuarios reciben las actualizaciones más recientes cuando se publican ampliamente para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="6dfc8-126">Un procedimiento recomendado es dejar la mayoría de los usuarios en **versiones estándar** y profesionales de ti y usuarios avanzados en el **lanzamiento de destino** para evaluar nuevas características y preparar a Microsoft Teams para que admitan usuarios y ejecutivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6dfc8-127">Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="6dfc8-128">Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="6dfc8-128">Targeted release</span></span>

<span data-ttu-id="6dfc8-p106">Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6dfc8-p107">Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="6dfc8-133">Versión dirigida para toda la organización</span><span class="sxs-lookup"><span data-stu-id="6dfc8-133">Targeted release for entire organization</span></span>

<span data-ttu-id="6dfc8-134">Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, todos los usuarios obtendrán la experiencia de la versión de destino.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="6dfc8-135">Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="6dfc8-136">Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="6dfc8-137">Versión dirigida para usuarios seleccionados</span><span class="sxs-lookup"><span data-stu-id="6dfc8-137">Targeted release for selected users</span></span>

<span data-ttu-id="6dfc8-138">Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para que obtengan acceso anticipado a características y funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="6dfc8-139">Ventajas de la Versión dirigida</span><span class="sxs-lookup"><span data-stu-id="6dfc8-139">Benefits of Targeted release</span></span>

<span data-ttu-id="6dfc8-140">La Versión dirigida permite que los administradores o cualquier otro cargo responsable de actualizaciones de Office 365 puedan preparar los próximos cambios mediante los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="6dfc8-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="6dfc8-141">Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="6dfc8-142">Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="6dfc8-143">Preparación de asistencia interna para los próximos cambios.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="6dfc8-144">Revisión de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="6dfc8-145">Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="6dfc8-146">Configurar la opción de lanzamiento en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="6dfc8-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="6dfc8-p109">Puede cambiar el modo en que la organización recibe actualizaciones de Office 365 siguiendo estos pasos. Debe ser administrador global en Office 365 para poder participar.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6dfc8-p110">Puede que los cambios siguientes tarden hasta 24 horas en surtir efecto en Office 365. Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="6dfc8-151">En el centro de administración, vaya a \*\*\*\* > configuración y **, en**la pestaña **perfil** de la organización, elija **Opciones de lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="6dfc8-152">Para deshabilitar la versión dirigida, seleccione **versión estándar**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="6dfc8-153">Para habilitar la versión dirigida para todos los usuarios de su organización, seleccione **versión dirigida para todos**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="6dfc8-154">Para habilitar la versión dirigida para algunas personas de su organización, seleccione **versión dirigida para los usuarios seleccionados**y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="6dfc8-155">Elija **Seleccionar usuarios** para agregar usuarios de uno en uno o **cargar usuarios** para agregarlos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="6dfc8-156">Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="6dfc8-157">Obtener la versión de lanzamiento de Office dirigida</span><span class="sxs-lookup"><span data-stu-id="6dfc8-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="6dfc8-p111">Para instalar una compilación de la versión dirigida de Office, [siga estos pasos](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). De esta manera obtendrá acceso previo a las nuevas características de Office 2016 para escritorios de Windows.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="6dfc8-160">Más información</span><span class="sxs-lookup"><span data-stu-id="6dfc8-160">Learn more</span></span>

<span data-ttu-id="6dfc8-161">Descubra cómo [administrar mensajes](https://docs.microsoft.com/office365/admin/manage/message-center) en el [centro de mensajes de Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones sobre próximas actualizaciones y versiones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
