---
title: Ver sus aplicaciones
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Ver sus aplicaciones.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420264"
---
# <a name="view-your-apps"></a><span data-ttu-id="5b2c6-103">Ver sus aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5b2c6-103">View your apps</span></span>

><span data-ttu-id="5b2c6-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="5b2c6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5b2c6-105">La gobernanza de aplicaciones de Microsoft le permite obtener rápidamente información detallada sobre las aplicaciones de Microsoft 365 en su usuario.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="5b2c6-106">Por ejemplo, puede ver:</span><span class="sxs-lookup"><span data-stu-id="5b2c6-106">For example, you can see:</span></span>

- <span data-ttu-id="5b2c6-107">Una lista de aplicaciones habilitadas para OAuth en el usuario que usa la API de Microsoft Graph, junto con los metadatos de aplicación y los datos de uso pertinentes.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="5b2c6-108">Detalles de las aplicaciones con enfoques e información más detallados al seleccionar una aplicación en la lista.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="5b2c6-109">Obtener una lista de todas las aplicaciones de su usuario</span><span class="sxs-lookup"><span data-stu-id="5b2c6-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="5b2c6-110">Para obtener un resumen de las aplicaciones de su usuario, diríjase a **Centro de cumplimiento de Microsoft 365 > Protección de aplicaciones y gobernanza > Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![La página de resumen de la aplicación MAPG en el centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="5b2c6-112">Su cuenta de inicio de sesión debe tener uno de los [estos roles](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="5b2c6-113">Verá una lista de aplicaciones y esta información:</span><span class="sxs-lookup"><span data-stu-id="5b2c6-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="5b2c6-114">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5b2c6-114">App Name</span></span>
- <span data-ttu-id="5b2c6-115">Editorial</span><span class="sxs-lookup"><span data-stu-id="5b2c6-115">Publisher</span></span>
- <span data-ttu-id="5b2c6-116">Certificación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5b2c6-116">App certification</span></span>

  <span data-ttu-id="5b2c6-117">Indica si la aplicación es compatible con las tecnologías de Microsoft, cumple con los procedimientos recomendados de seguridad de aplicaciones en la nube, y es compatible con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="5b2c6-118">Última modificación</span><span class="sxs-lookup"><span data-stu-id="5b2c6-118">Last modified</span></span>

  <span data-ttu-id="5b2c6-119">Muestra la fecha en que se instaló la gobernanza de aplicaciones en el cliente si esa fecha es más reciente que la fecha de la última modificación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="5b2c6-120">Fecha de instalación</span><span class="sxs-lookup"><span data-stu-id="5b2c6-120">Date installed</span></span>
- <span data-ttu-id="5b2c6-121">Nivel de privilegio</span><span class="sxs-lookup"><span data-stu-id="5b2c6-121">Privilege level</span></span>
- <span data-ttu-id="5b2c6-122">Número de usuarios</span><span class="sxs-lookup"><span data-stu-id="5b2c6-122">Number of users</span></span>
- <span data-ttu-id="5b2c6-123">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="5b2c6-123">Data access</span></span>

  <span data-ttu-id="5b2c6-124">La suma de la carga y descarga de datos de esta aplicación en el usuario durante el último día, junto con el cambio respecto al día anterior.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="5b2c6-125">La gobernanza de aplicaciones ordena la lista de aplicaciones por **nombre de aplicación** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="5b2c6-126">Para ordenar la lista por otro atributo de una aplicación, seleccione el nombre del atributo. </span><span class="sxs-lookup"><span data-stu-id="5b2c6-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="5b2c6-127">También puede seleccionar **Buscar** para buscar una aplicación por nombre.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="5b2c6-128">Obtener información detallada sobre una aplicación</span><span class="sxs-lookup"><span data-stu-id="5b2c6-128">Getting detailed information on an app</span></span>

<span data-ttu-id="5b2c6-129">Para obtener información detallada sobre una aplicación específica de su usuario, vaya a \*\*Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Página de aplicaciones > \*nombre de la aplicación\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![El panel de detalles de aplicaciones de gobernanza de aplicaciones en el Cetro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="5b2c6-131">El panel de detalles de la aplicación proporciona información adicional sobre estas pestañas:</span><span class="sxs-lookup"><span data-stu-id="5b2c6-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="5b2c6-132">Nombre de la pestaña</span><span class="sxs-lookup"><span data-stu-id="5b2c6-132">Tab name</span></span> | <span data-ttu-id="5b2c6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b2c6-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5b2c6-134">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b2c6-134">Details</span></span> | <span data-ttu-id="5b2c6-135">Vea datos adicionales en la aplicación, como la fecha en que se consiente por primera vez y el identificador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="5b2c6-136">Para ver las propiedades de la aplicación como registrada en Azure AD, seleccione **Ver aplicación en Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="5b2c6-137">Uso</span><span class="sxs-lookup"><span data-stu-id="5b2c6-137">Usage</span></span> | <span data-ttu-id="5b2c6-138">Vea los datos a los que accede la aplicación en el usuario, trace el uso de datos y muestre el uso por parte de los principales usuarios \<x> y usuarios con [cuentas prioritarias](/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="5b2c6-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="5b2c6-139">Usuarios</span><span class="sxs-lookup"><span data-stu-id="5b2c6-139">Users</span></span> | <span data-ttu-id="5b2c6-140">Vea una lista de los usuarios que usan la aplicación, si son una cuenta prioritaria y la cantidad de datos descargados y cargados.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="5b2c6-141">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b2c6-141">Permissions</span></span> | <span data-ttu-id="5b2c6-142">Vea un resumen de los permisos concedidos y usados por la aplicación y la lista de permisos específicos.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="5b2c6-143">Vea la [referencia de los permisos de Microsoft Graph](/graph/permissions-reference)para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="5b2c6-144">Para una aplicación habilitada, también está el control **Deshabilitar la aplicación** para deshabilitar el uso de la aplicación seleccionada y el control **Habilitar la aplicación** para habilitar el uso de la aplicación deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="5b2c6-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="5b2c6-145">Estas acciones requieren estos [roles de administrador](app-governance-get-started.md#administrator-roles):</span><span class="sxs-lookup"><span data-stu-id="5b2c6-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="5b2c6-146">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5b2c6-146">Compliance Administrator</span></span>
- <span data-ttu-id="5b2c6-147">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5b2c6-147">Global Administrator</span></span>
- <span data-ttu-id="5b2c6-148">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5b2c6-148">Security Administrator</span></span>
- <span data-ttu-id="5b2c6-149">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5b2c6-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="5b2c6-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5b2c6-150">Next step</span></span>

<span data-ttu-id="5b2c6-151">[Determine la posición general de cumplimiento de la aplicación](app-governance-visibility-insights-compliance-posture.md).</span><span class="sxs-lookup"><span data-stu-id="5b2c6-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
