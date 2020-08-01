---
title: Agregar y verificar los contactos de administración en el portal de administración
description: Indíquenos con quién ponerse en contacto para cada área de enfoque.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8a5775d90f592aa5f64dd5f379fb37278032d87
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529808"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="39ac0-104">Agregar y verificar los contactos de administración en el portal de administración</span><span class="sxs-lookup"><span data-stu-id="39ac0-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="39ac0-105">Hay varias formas en las que el servicio de escritorio administrado de Microsoft se comunica con los clientes.</span><span class="sxs-lookup"><span data-stu-id="39ac0-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="39ac0-106">Para simplificar la comunicación y asegurarse de que estamos comprobando con las personas adecuadas, debe proporcionar un conjunto de contactos de administración.</span><span class="sxs-lookup"><span data-stu-id="39ac0-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="39ac0-107">Las operaciones de TI de escritorio administradas por Microsoft se contactan con estas personas para obtener ayuda para solucionar problemas relacionados con el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="39ac0-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39ac0-108">Es posible que ya haya agregado estos contactos en el portal de administración.</span><span class="sxs-lookup"><span data-stu-id="39ac0-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="39ac0-109">Si es así, dedique un momento a comprobar que la lista de contactos es precisa, ya que el escritorio administrado de Microsoft **debe** poder llegar a ellos si se produce un incidente grave.</span><span class="sxs-lookup"><span data-stu-id="39ac0-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="39ac0-110">Portal de Azure Active Directory Access para la administración del escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="39ac0-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="39ac0-111">El portal de administración de escritorio administrado de Microsoft requiere que las personas que accedan al portal tengan uno de estos roles de Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="39ac0-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="39ac0-112">Administrador global</span><span class="sxs-lookup"><span data-stu-id="39ac0-112">Global Administrator</span></span>
- <span data-ttu-id="39ac0-113">Administrador de servicios de Intune</span><span class="sxs-lookup"><span data-stu-id="39ac0-113">Intune Service Administrator</span></span>
- <span data-ttu-id="39ac0-114">Lector global</span><span class="sxs-lookup"><span data-stu-id="39ac0-114">Global Reader</span></span>
- <span data-ttu-id="39ac0-115">Administrador de soporte de servicio</span><span class="sxs-lookup"><span data-stu-id="39ac0-115">Service Support Administrator</span></span>

<span data-ttu-id="39ac0-116">El administrador global debe ser el único que inscriba a su organización en el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39ac0-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="39ac0-117">Los cinco roles tienen el mismo acceso dentro del portal de administración para iniciar y ver las tareas.</span><span class="sxs-lookup"><span data-stu-id="39ac0-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="39ac0-118">Para obtener más información sobre la asignación de estos roles en Azure AD, vea [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="39ac0-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="39ac0-119">Áreas de contacto del administrador enfocadas</span><span class="sxs-lookup"><span data-stu-id="39ac0-119">Admin contact areas of focus</span></span>

<span data-ttu-id="39ac0-120">Los contactos de administrador deben ser la mejor persona o grupo que pueda responder preguntas y tomar decisiones para diferentes áreas de interés.</span><span class="sxs-lookup"><span data-stu-id="39ac0-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="39ac0-121">**Las operaciones de escritorio administradas de Microsoft se comunicarán con estos contactos de administrador para obtener preguntas relacionadas con las solicitudes de soporte técnico que haya archivado el cliente.**</span><span class="sxs-lookup"><span data-stu-id="39ac0-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="39ac0-122">Estos contactos de administración recibirán notificaciones de actualizaciones de solicitud de soporte y mensajes nuevos.</span><span class="sxs-lookup"><span data-stu-id="39ac0-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="39ac0-123">Estas áreas incluyen:</span><span class="sxs-lookup"><span data-stu-id="39ac0-123">These areas include:</span></span>

<span data-ttu-id="39ac0-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="39ac0-124">Area of focus</span></span> | <span data-ttu-id="39ac0-125">Para preguntas sobre</span><span class="sxs-lookup"><span data-stu-id="39ac0-125">For questions about</span></span>
--- | ---
<span data-ttu-id="39ac0-126">Empaquetado de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="39ac0-126">App packaging</span></span> | <span data-ttu-id="39ac0-127">Solución de problemas de empaquetado de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="39ac0-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="39ac0-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="39ac0-128">Devices</span></span> | <span data-ttu-id="39ac0-129">Estado del dispositivo, solución de problemas con dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="39ac0-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="39ac0-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="39ac0-130">Security</span></span> | <span data-ttu-id="39ac0-131">Solución de problemas de seguridad de los dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="39ac0-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="39ac0-132">Departamento de soporte técnico de ti</span><span class="sxs-lookup"><span data-stu-id="39ac0-132">IT help desk</span></span> | <span data-ttu-id="39ac0-133">en los casos en los que el personal de soporte técnico pasa a través de los vales de usuario final fuera de las áreas de soporte técnico de Microsoft administradas</span><span class="sxs-lookup"><span data-stu-id="39ac0-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="39ac0-134">Otros</span><span class="sxs-lookup"><span data-stu-id="39ac0-134">Other</span></span> | <span data-ttu-id="39ac0-135">Para problemas no cubiertos por otras áreas</span><span class="sxs-lookup"><span data-stu-id="39ac0-135">For issues not covered by other areas</span></span>

<span data-ttu-id="39ac0-136">**La persona que elija para estos contactos debe tener el conocimiento y la autoridad para tomar decisiones en su entorno de escritorio administrado por Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="39ac0-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="39ac0-137">Cuando incorpore su entorno de escritorio administrado de Microsoft, se le pedirá que agregue contactos para el Departamento de soporte técnico y la seguridad locales.</span><span class="sxs-lookup"><span data-stu-id="39ac0-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="39ac0-138">Los contactos de administración son necesarios cuando [envía una solicitud de soporte técnico](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="39ac0-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="39ac0-139">Necesitará tener un contacto de administrador para el área de enfoque de la solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="39ac0-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="39ac0-140">**Para agregar contactos de administrador**</span><span class="sxs-lookup"><span data-stu-id="39ac0-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="39ac0-141">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="39ac0-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="39ac0-142">En **soporte**, seleccione **contactos de administración**.</span><span class="sxs-lookup"><span data-stu-id="39ac0-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menú soporte, contactos de administración cerca de la parte superior seleccionada](../../media/admincontacts.png)

3. <span data-ttu-id="39ac0-144">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="39ac0-144">Select **Add**.</span></span>

    ![Portal de administración, botón Agregar, a la izquierda de exportar y actualizar](../../media/adminadd.png)

4.  <span data-ttu-id="39ac0-146">Seleccione un **área de enfoque** y escriba la información del contacto.</span><span class="sxs-lookup"><span data-stu-id="39ac0-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![la lista de áreas de foco, como otras, aplicaciones y seguridad](../../media/areaoffocus.png)

5. <span data-ttu-id="39ac0-148">Repita este procedimiento para cada área de enfoque.</span><span class="sxs-lookup"><span data-stu-id="39ac0-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="39ac0-149">Pasos para empezar a trabajar con el escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="39ac0-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="39ac0-150">Agregar y comprobar los contactos de administrador en el portal de administración (este tema)</span><span class="sxs-lookup"><span data-stu-id="39ac0-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="39ac0-151">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="39ac0-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="39ac0-152">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="39ac0-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="39ac0-153">Instalar el Portal de empresa de Intune en dispositivos</span><span class="sxs-lookup"><span data-stu-id="39ac0-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="39ac0-154">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="39ac0-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="39ac0-155">Configurar dispositivos del Escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="39ac0-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="39ac0-156">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="39ac0-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="39ac0-157">Implementar aplicaciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="39ac0-157">Deploy apps to devices</span></span>](deploy-apps.md)
