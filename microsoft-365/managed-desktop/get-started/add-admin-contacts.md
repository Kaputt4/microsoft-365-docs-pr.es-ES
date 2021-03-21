---
title: Agregar y verificar los contactos de administración en el portal de administración
description: Díganos con quién ponerse en contacto para cada área de enfoque.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925897"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="9c82f-104">Agregar y verificar los contactos de administración en el portal de administración</span><span class="sxs-lookup"><span data-stu-id="9c82f-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="9c82f-105">Hay varias formas en que el servicio de Escritorio administrado de Microsoft se comunica con los clientes.</span><span class="sxs-lookup"><span data-stu-id="9c82f-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="9c82f-106">Para simplificar la comunicación y asegurarnos de que estamos comprobando con las personas correctas, debe proporcionar un conjunto de contactos de administrador.</span><span class="sxs-lookup"><span data-stu-id="9c82f-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="9c82f-107">Las operaciones de TI de Escritorio administrado de Microsoft se pondrán en contacto con estas personas para obtener asistencia para solucionar problemas de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="9c82f-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c82f-108">Es posible que ya haya agregado estos contactos en el portal de administración.</span><span class="sxs-lookup"><span data-stu-id="9c82f-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="9c82f-109">Si es así, tómese un momento para comprobar que la lista de contactos es precisa, ya que Microsoft Managed **Desktop** debe poder comunicarse con ellos si se produce un incidente grave.</span><span class="sxs-lookup"><span data-stu-id="9c82f-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="9c82f-110">Acceso de Azure Active Directory para el portal de administración de escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c82f-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="9c82f-111">El portal de administración de escritorio administrado de Microsoft requiere que las personas que accedan al portal tengan uno de estos roles de Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="9c82f-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="9c82f-112">Administrador global</span><span class="sxs-lookup"><span data-stu-id="9c82f-112">Global Administrator</span></span>
- <span data-ttu-id="9c82f-113">Administrador de servicios de Intune</span><span class="sxs-lookup"><span data-stu-id="9c82f-113">Intune Service Administrator</span></span>
- <span data-ttu-id="9c82f-114">Lector global</span><span class="sxs-lookup"><span data-stu-id="9c82f-114">Global Reader</span></span>
- <span data-ttu-id="9c82f-115">Administrador de soporte técnico de servicio</span><span class="sxs-lookup"><span data-stu-id="9c82f-115">Service Support Administrator</span></span>

<span data-ttu-id="9c82f-116">El administrador global debe ser el que inscriba su organización en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c82f-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c82f-117">Los cinco roles tienen el mismo acceso en el portal de administración para iniciar y ver tareas.</span><span class="sxs-lookup"><span data-stu-id="9c82f-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="9c82f-118">Para obtener más información sobre la asignación de estos roles en Azure AD, vea [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9c82f-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="9c82f-119">Áreas de contacto de administración de foco</span><span class="sxs-lookup"><span data-stu-id="9c82f-119">Admin contact areas of focus</span></span>

<span data-ttu-id="9c82f-120">Los contactos de administrador deben ser la mejor persona o grupo que pueda responder preguntas y tomar decisiones para diferentes áreas de enfoque.</span><span class="sxs-lookup"><span data-stu-id="9c82f-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="9c82f-121">**Las operaciones de escritorio administrado de Microsoft se pondrán en contacto con estos contactos de administrador para obtener preguntas relacionadas con las solicitudes de soporte técnico que el cliente ha presentado.**</span><span class="sxs-lookup"><span data-stu-id="9c82f-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="9c82f-122">Estos contactos de administrador recibirán notificaciones de actualizaciones de solicitudes de soporte técnico y mensajes nuevos.</span><span class="sxs-lookup"><span data-stu-id="9c82f-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="9c82f-123">Estas áreas incluyen:</span><span class="sxs-lookup"><span data-stu-id="9c82f-123">These areas include:</span></span>

<span data-ttu-id="9c82f-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="9c82f-124">Area of focus</span></span> | <span data-ttu-id="9c82f-125">Para preguntas sobre</span><span class="sxs-lookup"><span data-stu-id="9c82f-125">For questions about</span></span>
--- | ---
<span data-ttu-id="9c82f-126">Empaquetado de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9c82f-126">App packaging</span></span> | <span data-ttu-id="9c82f-127">Solución de problemas de empaquetado de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9c82f-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="9c82f-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="9c82f-128">Devices</span></span> | <span data-ttu-id="9c82f-129">Estado del dispositivo, solución de problemas con dispositivos de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c82f-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="9c82f-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9c82f-130">Security</span></span> | <span data-ttu-id="9c82f-131">Solución de problemas de seguridad con dispositivos de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c82f-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="9c82f-132">Servicio de ayuda de IT</span><span class="sxs-lookup"><span data-stu-id="9c82f-132">IT help desk</span></span> | <span data-ttu-id="9c82f-133">en los casos en que nuestro personal de soporte técnico entrega los vales de usuario fuera de las áreas de soporte técnico de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c82f-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="9c82f-134">Otros</span><span class="sxs-lookup"><span data-stu-id="9c82f-134">Other</span></span> | <span data-ttu-id="9c82f-135">Para problemas no cubiertos por otras áreas</span><span class="sxs-lookup"><span data-stu-id="9c82f-135">For issues not covered by other areas</span></span>

<span data-ttu-id="9c82f-136">**Quien elija para estos contactos debe tener el conocimiento y la autoridad para tomar decisiones para su entorno de Escritorio administrado de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="9c82f-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="9c82f-137">Al incorporar el entorno de Escritorio administrado de Microsoft, se le pedirá que agregue contactos para el departamento de soporte técnico y seguridad local.</span><span class="sxs-lookup"><span data-stu-id="9c82f-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="9c82f-138">Los contactos de administrador son necesarios al [enviar una solicitud de soporte técnico.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="9c82f-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="9c82f-139">Tendrás que tener un contacto de administrador para el área de enfoque de la solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="9c82f-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="9c82f-140">**Para agregar contactos de administrador**</span><span class="sxs-lookup"><span data-stu-id="9c82f-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="9c82f-141">Inicie sesión en [el portal de administración de Microsoft Managed Desktop](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="9c82f-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="9c82f-142">En **Soporte** técnico, seleccione **Contactos de administrador**.</span><span class="sxs-lookup"><span data-stu-id="9c82f-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menú Soporte técnico, Contactos de administrador cerca de la parte superior seleccionada](../../media/admincontacts.png)

3. <span data-ttu-id="9c82f-144">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c82f-144">Select **Add**.</span></span>

    ![Portal de administración, botón Agregar, a la izquierda de Exportar y actualizar](../../media/adminadd.png)

4.  <span data-ttu-id="9c82f-146">Selecciona un **área de foco** y escribe la información del contacto.</span><span class="sxs-lookup"><span data-stu-id="9c82f-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![la lista de áreas de foco, como Otras, Aplicaciones y Seguridad](../../media/areaoffocus.png)

5. <span data-ttu-id="9c82f-148">Repita cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="9c82f-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="9c82f-149">Pasos para empezar con Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="9c82f-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="9c82f-150">Agregar y comprobar contactos de administrador en el portal de administración (este tema)</span><span class="sxs-lookup"><span data-stu-id="9c82f-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="9c82f-151">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="9c82f-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="9c82f-152">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="9c82f-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="9c82f-153">Instalar el Portal de empresa de Intune en dispositivos</span><span class="sxs-lookup"><span data-stu-id="9c82f-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="9c82f-154">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9c82f-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="9c82f-155">Configurar dispositivos del Escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c82f-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="9c82f-156">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="9c82f-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="9c82f-157">Implementar aplicaciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="9c82f-157">Deploy apps to devices</span></span>](deploy-apps.md)