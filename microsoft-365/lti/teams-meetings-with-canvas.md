---
title: Usar Microsoft Teams reuniones con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams reuniones con Canvas
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454678"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="fa49d-103">Usar Microsoft Teams reuniones con Canvas</span><span class="sxs-lookup"><span data-stu-id="fa49d-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="fa49d-104">Microsoft Teams reuniones es una aplicación de interoperabilidad de Learning Tools (LTI) que ayuda a los formadores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams.</span><span class="sxs-lookup"><span data-stu-id="fa49d-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="fa49d-105">Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.</span><span class="sxs-lookup"><span data-stu-id="fa49d-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="fa49d-106">Microsoft Office 365 Administrador</span><span class="sxs-lookup"><span data-stu-id="fa49d-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="fa49d-107">Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.</span><span class="sxs-lookup"><span data-stu-id="fa49d-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="fa49d-108">Inicie sesión en Canvas.</span><span class="sxs-lookup"><span data-stu-id="fa49d-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="fa49d-109">Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="fa49d-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="fa49d-110">En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="fa49d-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="fa49d-111">Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fa49d-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="fa49d-112">El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario.</span><span class="sxs-lookup"><span data-stu-id="fa49d-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="fa49d-113">Seleccione **Actualizar Configuración** una vez que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="fa49d-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="fa49d-114">Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="fa49d-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="fa49d-115">Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa49d-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permisos](media/permissions.png)

7. <span data-ttu-id="fa49d-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-117">Select **Accept**.</span></span>

8. <span data-ttu-id="fa49d-118">Habilite la Microsoft Teams sincronización activando la alternancia.</span><span class="sxs-lookup"><span data-stu-id="fa49d-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="fa49d-120">Administrador de Canvas</span><span class="sxs-lookup"><span data-stu-id="fa49d-120">Canvas Admin</span></span>

<span data-ttu-id="fa49d-121">Configure la integración Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="fa49d-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="fa49d-122">Como administrador de Canvas, tendrás que agregar la aplicación LTI Microsoft Teams reuniones en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="fa49d-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="fa49d-123">Anote el id. de cliente de LTI para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa49d-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="fa49d-124">Microsoft Teams - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="fa49d-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="fa49d-125">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="fa49d-126">Selecciona **+ Aplicación** para agregar las Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="fa49d-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="fa49d-128">Seleccione **Por identificador de cliente** para el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa49d-128">Select **By Client ID** for configuration type.</span></span>

   ![agregar aplicación](media/add-app.png)

4. <span data-ttu-id="fa49d-130">Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="fa49d-131">Verás el nombre de la aplicación LTI Microsoft Teams reuniones para el identificador de cliente para confirmación.</span><span class="sxs-lookup"><span data-stu-id="fa49d-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="fa49d-132">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-132">Select **Install**.</span></span>

   <span data-ttu-id="fa49d-133">La Microsoft Teams LTI de reuniones de reuniones se agregará a la lista de aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="fa49d-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="fa49d-134">Habilitar cursos de Canvas</span><span class="sxs-lookup"><span data-stu-id="fa49d-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="fa49d-135">Para poder usar el LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree Teams correspondiente; no hay ningún mecanismo global para la Teams creación.</span><span class="sxs-lookup"><span data-stu-id="fa49d-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="fa49d-136">Esto está diseñado por precaución para evitar que se cree Teams no deseados.</span><span class="sxs-lookup"><span data-stu-id="fa49d-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="fa49d-137">Consulte a los instructores la documentación [del](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) profesor para habilitar el LTI para cada curso y finalizar la configuración de integración.</span><span class="sxs-lookup"><span data-stu-id="fa49d-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
