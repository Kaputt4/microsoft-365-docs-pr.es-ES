---
title: Usar Microsoft Teams clases con Blackboard
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams clases en el sistema de administración de aprendizaje
ms.openlocfilehash: 287b9f1cadfdcf3adafdca91f4a351865bbcf3bc
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821276"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="2f00f-103">Usar Microsoft Teams clases con Blackboard</span><span class="sxs-lookup"><span data-stu-id="2f00f-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f00f-104">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="2f00f-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2f00f-105">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="2f00f-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2f00f-106">Microsoft Teams clases es una aplicación de interoperabilidad de herramientas de aprendizaje (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su Sistema de administración de aprendizaje (LMS) y Teams.</span><span class="sxs-lookup"><span data-stu-id="2f00f-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="2f00f-107">Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.</span><span class="sxs-lookup"><span data-stu-id="2f00f-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="2f00f-108">Aprobar la aplicación en el Microsoft Azure inquilino</span><span class="sxs-lookup"><span data-stu-id="2f00f-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="2f00f-109">El administrador de Microsoft Office 365 y el administrador de Blackboard Learn Ultra completan las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="2f00f-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="2f00f-110">Antes de administrar la integración en Blackboard Learn Ultra, el administrador de Microsoft Office 365 debe aprobar el Teams de **MSFT** de Blackboard para la aplicación Learn Ultra Azure para el inquilino Microsoft Azure la entidad.</span><span class="sxs-lookup"><span data-stu-id="2f00f-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="2f00f-111">Busque su id. de inquilino de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f00f-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="2f00f-112">Vea [cómo encontrar el espacio empresarial](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span><span class="sxs-lookup"><span data-stu-id="2f00f-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="2f00f-113">Redirija el extremo de consentimiento de administrador de la plataforma de identidad de Microsoft según el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f00f-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="2f00f-114">Reemplace {tenant} por el identificador de inquilino de Microsoft de su organización.</span><span class="sxs-lookup"><span data-stu-id="2f00f-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="2f00f-115">Registrar las aplicaciones de integración</span><span class="sxs-lookup"><span data-stu-id="2f00f-115">Register the integration apps</span></span>

<span data-ttu-id="2f00f-116">Como administrador de Blackboard Learn Ultra, deberá registrar 2 aplicaciones de integración de LTI 1.3 en su entorno de prueba:</span><span class="sxs-lookup"><span data-stu-id="2f00f-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="2f00f-117">La clase De Aprendizaje de Blackboard Teams integración para admitir la sincronización de listas</span><span class="sxs-lookup"><span data-stu-id="2f00f-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="2f00f-118">La Microsoft Teams LTI de grupo de clase</span><span class="sxs-lookup"><span data-stu-id="2f00f-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="2f00f-119">Anote los siguientes IDs de cliente LTI para ambas aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="2f00f-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="2f00f-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="2f00f-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="2f00f-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="2f00f-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="2f00f-122">Accede al Panel de administración y, en **Integraciones,** busca los proveedores de herramientas de LTI.</span><span class="sxs-lookup"><span data-stu-id="2f00f-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![este es el cuadro de diálogo Proveedor de herramientas de LTI que muestra una lista de proveedores](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="2f00f-124">Seleccione **Registrar LTI1.3/Advantage Tool**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="2f00f-125">Escriba el primero de los IDs de cliente proporcionados (Ya sea Blackboard o Microsoft) y seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![la herramienta de registro LTI con un campo para especificar el identificador de cliente](../media/lti-media/register-tool.png)

5. <span data-ttu-id="2f00f-127">Revise la configuración rellenada previamente y asegúrese de que el estado de la herramienta esté marcado como aprobado.</span><span class="sxs-lookup"><span data-stu-id="2f00f-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="2f00f-128">Desplácese hasta la parte inferior y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="2f00f-129">Repita los pasos anteriores para registrar la segunda de las aplicaciones de LTI en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2f00f-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="2f00f-130">Configurar la aplicación REST y el uso compartido de recursos entre orígenes</span><span class="sxs-lookup"><span data-stu-id="2f00f-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="2f00f-131">El administrador de Blackboard Learn Ultra también tendrá que configurar la aplicación REST y la configuración de uso compartido de recursos entre orígenes.</span><span class="sxs-lookup"><span data-stu-id="2f00f-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="2f00f-132">Complete lo siguiente para configurar la aplicación REST</span><span class="sxs-lookup"><span data-stu-id="2f00f-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="2f00f-133">Obtenga acceso a Herramientas de administración de Learn y, a continuación, seleccione **Integraciones de API de REST** en la sección **Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="2f00f-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="2f00f-134">Seleccione **Crear integraciones** y escriba el mismo id. de aplicación/cliente que escribió para la herramienta LTI de Teams clase de Aprendizaje de Blackboard.</span><span class="sxs-lookup"><span data-stu-id="2f00f-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="2f00f-135">Escriba el usuario de Learn (podría ser su propio nombre de usuario de administrador de Learn) o **seleccione Examinar** para buscar.</span><span class="sxs-lookup"><span data-stu-id="2f00f-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="2f00f-136">Seleccione **Sí para** acceso de usuario **final**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="2f00f-137">Seleccione **Sí** para **Autorizado para actuar como usuario**</span><span class="sxs-lookup"><span data-stu-id="2f00f-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="2f00f-138">Seleccione **Enviar una** vez completada.</span><span class="sxs-lookup"><span data-stu-id="2f00f-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="2f00f-139">Configurar el uso compartido de recursos entre orígenes</span><span class="sxs-lookup"><span data-stu-id="2f00f-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="2f00f-140">Obtenga acceso a herramientas de administración de Learn y seleccione **Uso** compartido de recursos entre orígenes en la **sección Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="2f00f-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="2f00f-141">Seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="2f00f-142">Escriba `https://bb-ms-teams-ultra-ext.api.blackboard.com` en el origen.</span><span class="sxs-lookup"><span data-stu-id="2f00f-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="2f00f-143">Agregue la palabra **Autorización en** los **encabezados permitidos**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="2f00f-144">Establezca **Disponible** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="2f00f-145">Seleccione **Enviar una** vez completada.</span><span class="sxs-lookup"><span data-stu-id="2f00f-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="2f00f-146">Habilitar la clase Teams en Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="2f00f-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="2f00f-147">Una vez habilitadas las herramientas de LTI, el siguiente paso será configurar la integración de Microsoft Class Teams desde su propio Microsoft Office 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="2f00f-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="2f00f-148">Para ello, siga estos pasos como administrador de Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="2f00f-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="2f00f-149">En **Learn Admin** Tools and  >  **Utilities**, seleccione Microsoft Teams Integration **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![el cuadro de diálogo herramientas y utilidades con una lista de herramientas disponibles](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="2f00f-151">Active la casilla de verificación **Habilitar Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="2f00f-152">Escriba su identificador de inquilino como se hace referencia en la sección de Administración de Microsoft O365</span><span class="sxs-lookup"><span data-stu-id="2f00f-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="2f00f-153">No podrás guardar la configuración hasta que la aplicación haya sido aprobada por el administrador de O365. Consulta [Aprobar la aplicación en Microsoft Azure inquilino](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="2f00f-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="2f00f-154">Cuando el administrador global de O365 haya aprobado la aplicación Teams Desempresa de Blackboard en su inquilino de Microsoft, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2f00f-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
