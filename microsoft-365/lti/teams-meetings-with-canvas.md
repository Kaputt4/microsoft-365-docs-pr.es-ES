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
ms.openlocfilehash: 946abaec52cb1c5060d5490b409758cf230a4e5a
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256884"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="dac67-103">Usar Microsoft Teams reuniones con Canvas</span><span class="sxs-lookup"><span data-stu-id="dac67-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dac67-104">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="dac67-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dac67-105">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="dac67-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="dac67-106">Microsoft Teams reuniones es una aplicación de interoperabilidad de Learning Tools (LTI) que ayuda a los formadores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams.</span><span class="sxs-lookup"><span data-stu-id="dac67-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="dac67-107">Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.</span><span class="sxs-lookup"><span data-stu-id="dac67-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="dac67-108">Microsoft Office 365 Administrador</span><span class="sxs-lookup"><span data-stu-id="dac67-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="dac67-109">Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.</span><span class="sxs-lookup"><span data-stu-id="dac67-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="dac67-110">Inicie sesión en Canvas.</span><span class="sxs-lookup"><span data-stu-id="dac67-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="dac67-111">Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="dac67-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="dac67-112">En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**</span><span class="sxs-lookup"><span data-stu-id="dac67-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="dac67-113">Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dac67-113">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="dac67-114">El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario.</span><span class="sxs-lookup"><span data-stu-id="dac67-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="dac67-115">Seleccione **Actualizar Configuración** una vez que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="dac67-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="dac67-116">Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="dac67-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="dac67-117">Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dac67-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permisos](media/permissions.png)

7. <span data-ttu-id="dac67-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dac67-119">Select **Accept**.</span></span>

8. <span data-ttu-id="dac67-120">Habilite la Microsoft Teams sincronización activando la alternancia.</span><span class="sxs-lookup"><span data-stu-id="dac67-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="dac67-122">Administrador de Canvas</span><span class="sxs-lookup"><span data-stu-id="dac67-122">Canvas Admin</span></span>

<span data-ttu-id="dac67-123">Configure la integración Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="dac67-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="dac67-124">Como administrador de Canvas, tendrás que agregar la aplicación LTI Microsoft Teams reuniones en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="dac67-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="dac67-125">Anote el id. de cliente de LTI para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dac67-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="dac67-126">Microsoft Teams - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="dac67-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="dac67-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="dac67-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="dac67-128">Selecciona **+ Aplicación** para agregar las Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="dac67-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="dac67-130">Seleccione **Por identificador de cliente** para el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="dac67-130">Select **By Client ID** for configuration type.</span></span>

   ![agregar aplicación](media/add-app.png)

4. <span data-ttu-id="dac67-132">Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dac67-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="dac67-133">Verás el nombre de la aplicación LTI Microsoft Teams reuniones para el identificador de cliente para confirmación.</span><span class="sxs-lookup"><span data-stu-id="dac67-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="dac67-134">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="dac67-134">Select **Install**.</span></span>

   <span data-ttu-id="dac67-135">La Microsoft Teams LTI de reuniones de reuniones se agregará a la lista de aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="dac67-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
