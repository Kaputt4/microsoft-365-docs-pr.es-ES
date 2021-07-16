---
title: Usar Microsoft Teams clases con Canvas
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
description: Integrar Microsoft Teams clases con Canvas
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454690"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="bc9e6-103">Usar Microsoft Teams clases con Canvas</span><span class="sxs-lookup"><span data-stu-id="bc9e6-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="bc9e6-104">Microsoft Teams clases es una aplicación Learning Tools Interoperability (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="bc9e6-105">Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="bc9e6-106">Requisitos previos antes de la implementación</span><span class="sxs-lookup"><span data-stu-id="bc9e6-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="bc9e6-107">La clase actual Teams LTI solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="bc9e6-108">El inquilino debe tener una coincidencia exacta entre un campo canvas (correo electrónico, id. de usuario o id. de SIS) y el UPN en Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="bc9e6-109">Estamos trabajando para ampliar la flexibilidad a la funcionalidad de sincronización, pero mientras tanto, los usuarios de Canvas que no coincidan con un UPN en AAD no se agregarán a la clase Teams sincronizada con Canvas.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="bc9e6-110">Solo se puede usar un único espacio empresarial de Microsoft para asignar usuarios entre Canvas y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="bc9e6-111">Tendrá que desactivar SDS antes de usar la clase Teams LTI para evitar la duplicación de grupos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="bc9e6-112">Microsoft Office 365 Administrador</span><span class="sxs-lookup"><span data-stu-id="bc9e6-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="bc9e6-113">Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="bc9e6-114">Inicie sesión en Canvas.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="bc9e6-115">Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="bc9e6-116">En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="bc9e6-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="bc9e6-117">Habilite Microsoft Teams sincronización activando la alternancia.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="bc9e6-119">Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="bc9e6-120">El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="bc9e6-121">Seleccione **Actualizar Configuración** una vez que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="bc9e6-122">Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="bc9e6-123">Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permisos](media/permissions.png)

8. <span data-ttu-id="bc9e6-125">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="bc9e6-126">Administrador de Canvas</span><span class="sxs-lookup"><span data-stu-id="bc9e6-126">Canvas Admin</span></span>

<span data-ttu-id="bc9e6-127">Configure la integración Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="bc9e6-128">Como administrador de Canvas, tendrás que agregar la aplicación LTI de Microsoft Teams clases en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="bc9e6-129">Anote el id. de cliente de LTI para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="bc9e6-130">Microsoft Teams : 170000000000570</span><span class="sxs-lookup"><span data-stu-id="bc9e6-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="bc9e6-131">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="bc9e6-132">Selecciona **+ Aplicación** para agregar las Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="bc9e6-134">Seleccione **Por identificador de cliente** para el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-134">Select **By Client ID** for configuration type.</span></span>

   ![agregar aplicación](media/add-app.png)

4. <span data-ttu-id="bc9e6-136">Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="bc9e6-137">Observarás el nombre de la aplicación Microsoft Teams clases LTI para el identificador de cliente para confirmación.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="bc9e6-138">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-138">Select **Install**.</span></span>

   <span data-ttu-id="bc9e6-139">La Microsoft Teams clases de aplicación LTI se agregará a la lista de aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="bc9e6-140">Habilitar la aplicación LTI para cursos de Canvas</span><span class="sxs-lookup"><span data-stu-id="bc9e6-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="bc9e6-141">Para usar la aplicación LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree un equipo correspondiente; no hay ningún mecanismo global para la creación de equipos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="bc9e6-142">Esto está diseñado como una medida de precaución para evitar que se creen equipos no deseados.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="bc9e6-143">Consulte la documentación [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) del profesor para habilitar la aplicación LTI para cada curso y completar la configuración de integración.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
