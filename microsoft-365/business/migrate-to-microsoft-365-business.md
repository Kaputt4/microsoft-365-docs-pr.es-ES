---
title: Actualización a Microsoft 365 Business desde Office 365 empresa Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Pasos para actualizar su empresa de Office 365 empresa Premium a Microsoft 365 Business.
ms.openlocfilehash: f3a25746cf123fa471c29084a62a6fcfc1542a02
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231419"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="2e611-103">Actualización a Microsoft 365 Business desde Office 365 empresa Premium</span><span class="sxs-lookup"><span data-stu-id="2e611-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="2e611-104">Si tiene una [suscripción de office 365 para empresas](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), por ejemplo, Office 365 empresa Premium, puede actualizar fácilmente a Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="2e611-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="2e611-105">Actualice a Microsoft 365 Business si desea agregar:</span><span class="sxs-lookup"><span data-stu-id="2e611-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="2e611-106">Windows 10 Pro (para equipos que ejecutan Windows 8 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="2e611-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="2e611-107">Controles sencillos que administran los datos profesionales en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="2e611-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="2e611-108">Capacidades de seguridad avanzadas.</span><span class="sxs-lookup"><span data-stu-id="2e611-108">Advanced security capabilities.</span></span>
<span data-ttu-id="2e611-109">Obtenga más información sobre Microsoft 365 Business en [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="2e611-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="2e611-110">¿Cuál es la diferencia entre Office 365 Business Premium y Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="2e611-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="2e611-111">Hemos agregado una comparación en paralelo de estos dos planes a la descripción del servicio de [negocio de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="2e611-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="2e611-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2e611-112">Before you get started</span></span>

- <span data-ttu-id="2e611-113">**¿Cuándo debe elegirse la actualización?**</span><span class="sxs-lookup"><span data-stu-id="2e611-113">**When should I choose upgrade?**</span></span> <span data-ttu-id="2e611-114">La actualización es la opción correcta cuando desea actualizar **todos los usuarios** asignados a un solo plan.</span><span class="sxs-lookup"><span data-stu-id="2e611-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="2e611-115">Cuando elige actualizar, todos los usuarios del plan se cambian a otro plan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="2e611-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="2e611-116">Si no desea actualizar todos los usuarios asignados a un solo plan, compre licencias para el nuevo plan (en este caso, Microsoft 365 Business) y [asígneles estas licencias individualmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) para cada usuario que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="2e611-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="2e611-117">**Algunos complementos pueden impedir la actualización** Si intenta iniciar una actualización y tiene un complemento que le impide continuar, puede quitar el complemento en primer lugar y, a continuación, volver a agregarlo si todavía lo necesita.</span><span class="sxs-lookup"><span data-stu-id="2e611-117">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="2e611-118">**Si prepagó el plan** No existe una ruta de actualización sencilla para los planes de prepago.</span><span class="sxs-lookup"><span data-stu-id="2e611-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="2e611-119">Sabrá si tiene un plan de prepago porque ha configurado su plan con un identificador de producto que puede haber comprado en una tienda.</span><span class="sxs-lookup"><span data-stu-id="2e611-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="2e611-120">Póngase en contacto con un partner, vaya a Microsoft Store o espere hasta que el plan de prepago expire para cambiar a un nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="2e611-120">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="2e611-121">Actualización a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="2e611-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="2e611-122">Para comprar sus licencias, siga estos pasos en el [nuevo centro de administración](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span><span class="sxs-lookup"><span data-stu-id="2e611-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="2e611-123">Inicie sesión en el centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administración en.</span><span class="sxs-lookup"><span data-stu-id="2e611-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="2e611-124">Vaya al panel de navegación y seleccione productos de **facturación** \> **& servicios**.</span><span class="sxs-lookup"><span data-stu-id="2e611-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="2e611-125">Busque su suscripción a Office 365 y selecciónela para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="2e611-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![Una captura de pantalla que muestra cómo buscar y seleccionar la suscripción en el centro de administración.](media/FindYourSubscription.png)

3. <span data-ttu-id="2e611-127">En la página siguiente, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="2e611-127">On the next page, select **Upgrade**.</span></span> 

      ![Una captura de pantalla muestra dónde seleccionar la actualización en el centro de administración.](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="2e611-129">Si ve un mensaje que indica "no se admite la actualización de la suscripción con licencias basadas en grupos en Azure Active Directory", puede omitirlo sin problemas a menos que tenga una organización muy grande.</span><span class="sxs-lookup"><span data-stu-id="2e611-129">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="2e611-130">Las organizaciones que hayan seleccionado esta opción sabrán que están usando licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="2e611-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="2e611-131">A continuación, puede ver una lista de los planes de Office a los que puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="2e611-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="2e611-132">En este caso, busque el plan de negocio de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e611-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="2e611-133">Puede desplazarse hacia abajo si desea ver todas las aplicaciones y servicios de Office que se incluyen en este plan.</span><span class="sxs-lookup"><span data-stu-id="2e611-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="2e611-134">En **microsoft 365 Business**, seleccione **Actualizar** para agregar un negocio de Microsoft 365 a su carro.</span><span class="sxs-lookup"><span data-stu-id="2e611-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="2e611-135">En el carro:</span><span class="sxs-lookup"><span data-stu-id="2e611-135">In the cart:</span></span>
    1. <span data-ttu-id="2e611-136">Se incluirán automáticamente licencias para todos los usuarios actuales en el carro.</span><span class="sxs-lookup"><span data-stu-id="2e611-136">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="2e611-137">Si necesita más o menos licencias, necesitará [comprar y asignar dichas licencias de forma individual](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="2e611-137">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="2e611-138">Puede ajustar el modo en que desea pagar: mensual o anual.</span><span class="sxs-lookup"><span data-stu-id="2e611-138">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="2e611-139">Seleccione el menú desplegable para elegir.</span><span class="sxs-lookup"><span data-stu-id="2e611-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="2e611-140">Seleccione **ir a la retirada** para ver un resumen de la compra, incluido el método de pago de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="2e611-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="2e611-141">También puede Agregar un código de promoción aquí si tiene uno.</span><span class="sxs-lookup"><span data-stu-id="2e611-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="2e611-142">Seleccione **realizar pedido** para completar la compra.</span><span class="sxs-lookup"><span data-stu-id="2e611-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="2e611-143">Necesita Microsoft unos minutos para configurar los nuevos planes de servicio.</span><span class="sxs-lookup"><span data-stu-id="2e611-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="2e611-144">Para comprobar el progreso, seleccione **comprobar el estado**de la actualización.</span><span class="sxs-lookup"><span data-stu-id="2e611-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="2e611-145">Una vez que el plan esté listo, es posible que deba completar algunos pasos de configuración adicionales en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2e611-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="2e611-146">En el panel de navegación, seleccione **Inicio** para completar los pasos de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="2e611-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="2e611-147">Recibirá una restitución prorrateada para las licencias de Ofifce 365 que ya no necesita.</span><span class="sxs-lookup"><span data-stu-id="2e611-147">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="2e611-148">La cuenta bancaria o la tarjeta de crédito se cargarán dos días después de configurar el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="2e611-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="2e611-149">Proteger los archivos y dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="2e611-149">Protect user devices and files</span></span>

<span data-ttu-id="2e611-150">Ahora que se han asignado las licencias de Microsoft 365 Business, siga los pasos para empezar a proteger dispositivos y archivos.</span><span class="sxs-lookup"><span data-stu-id="2e611-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="2e611-151">Utilizará algunas nuevas opciones incluidas en el panel de navegación del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2e611-151">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="2e611-152">En el panel de navegación del centro de administración, vaya a \*\*\*\* \> **directivas**de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2e611-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="2e611-153">En la página **directivas de dispositivos** , seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2e611-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="2e611-154">En el panel **Agregar Directiva** , asigne un nombre a la Directiva (por ejemplo, proteger archivos de trabajo) y, a continuación, elija un **tipo de directiva** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2e611-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="2e611-155">Puede configurar directivas de aplicación para proteger los archivos en dispositivos Android y iPhone, así como en Windows 10, y puede configurar directivas de configuración de dispositivo para dispositivos Windows 10 que pertenecen a la empresa.</span><span class="sxs-lookup"><span data-stu-id="2e611-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="2e611-156">Consulte los siguientes vínculos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="2e611-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="2e611-157">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="2e611-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="2e611-158">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e611-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="2e611-159">Establecer la configuración de protección de dispositivos para equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e611-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="2e611-160">Una vez configuradas las directivas, usted y sus empleados pueden configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="2e611-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="2e611-161">Si los dispositivos Windows ya no usan la actualización del creador de Windows Pro, tendrás que [actualizarlos a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="2e611-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="2e611-162">Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para conocer los pasos para dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="2e611-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="2e611-163">Consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md) para conocer los pasos para Android Phones y iPhone.</span><span class="sxs-lookup"><span data-stu-id="2e611-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



