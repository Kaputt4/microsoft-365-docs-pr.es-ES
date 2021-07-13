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
ms.openlocfilehash: 7e13052cb029fef369f6386c2039785e40acc4ff
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409097"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="bbdbe-103">Usar Microsoft Teams reuniones con Canvas</span><span class="sxs-lookup"><span data-stu-id="bbdbe-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbdbe-104">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bbdbe-105">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="bbdbe-106">Microsoft Teams reuniones es una aplicación de interoperabilidad de Learning Tools (LTI) que ayuda a los formadores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="bbdbe-107">Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="bbdbe-108">Microsoft Office 365 Administrador</span><span class="sxs-lookup"><span data-stu-id="bbdbe-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="bbdbe-109">Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="bbdbe-110">Inicie sesión en Canvas.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="bbdbe-111">Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="bbdbe-112">En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="bbdbe-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="bbdbe-113">Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-113">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="bbdbe-114">El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="bbdbe-115">Seleccione **Actualizar Configuración** una vez que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="bbdbe-116">Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="bbdbe-117">Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permisos](media/permissions.png)

7. <span data-ttu-id="bbdbe-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-119">Select **Accept**.</span></span>

8. <span data-ttu-id="bbdbe-120">Habilite la Microsoft Teams sincronización activando la alternancia.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="bbdbe-122">Administrador de Canvas</span><span class="sxs-lookup"><span data-stu-id="bbdbe-122">Canvas Admin</span></span>

<span data-ttu-id="bbdbe-123">Configure la integración Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="bbdbe-124">Como administrador de Canvas, tendrás que agregar la aplicación LTI Microsoft Teams reuniones en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="bbdbe-125">Anote el id. de cliente de LTI para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="bbdbe-126">Microsoft Teams - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="bbdbe-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="bbdbe-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="bbdbe-128">Selecciona **+ Aplicación** para agregar las Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="bbdbe-130">Seleccione **Por identificador de cliente** para el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-130">Select **By Client ID** for configuration type.</span></span>

   ![agregar aplicación](media/add-app.png)

4. <span data-ttu-id="bbdbe-132">Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="bbdbe-133">Verás el nombre de la aplicación LTI Microsoft Teams reuniones para el identificador de cliente para confirmación.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="bbdbe-134">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-134">Select **Install**.</span></span>

   <span data-ttu-id="bbdbe-135">La Microsoft Teams LTI de reuniones de reuniones se agregará a la lista de aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="bbdbe-136">Habilitar cursos de Canvas</span><span class="sxs-lookup"><span data-stu-id="bbdbe-136">Enable for Canvas Courses</span></span>

<span data-ttu-id="bbdbe-137">Para poder usar el LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree Teams correspondiente; no hay ningún mecanismo global para la Teams creación.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-137">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="bbdbe-138">Esto está diseñado por precaución para evitar que se cree Teams no deseados.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-138">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="bbdbe-139">Consulte a los instructores la documentación [del](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) profesor para habilitar el LTI para cada curso y finalizar la configuración de integración.</span><span class="sxs-lookup"><span data-stu-id="bbdbe-139">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
