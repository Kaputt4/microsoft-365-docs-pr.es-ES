---
title: Paso 4. Migración para los inquilinos de Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migre los dispositivos Windows, las aplicaciones cliente de Office y los servidores de Office para sus inquilinos de Microsoft 365.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929149"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="b4580-104">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="b4580-104">Step 4.</span></span> <span data-ttu-id="b4580-105">Migración para los inquilinos de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b4580-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="b4580-106">La mayoría de las organizaciones empresariales tienen un entorno heterogéneo que incluye varias versiones de sistemas operativos, software cliente y software de servidor.</span><span class="sxs-lookup"><span data-stu-id="b4580-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="b4580-107">Microsoft 365 para empresas incluye las versiones más seguras de los componentes clave de su infraestructura de TI.</span><span class="sxs-lookup"><span data-stu-id="b4580-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="b4580-108">También incluye características de productividad diseñadas para aprovechar las tecnologías en la nube.</span><span class="sxs-lookup"><span data-stu-id="b4580-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="b4580-109">Para maximizar el valor empresarial del conjunto de productos integrado de Microsoft 365 para empresas, comience a planear e implementar una estrategia para migrar estas versiones:</span><span class="sxs-lookup"><span data-stu-id="b4580-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="b4580-110">From</span><span class="sxs-lookup"><span data-stu-id="b4580-110">From</span></span> | <span data-ttu-id="b4580-111">To</span><span class="sxs-lookup"><span data-stu-id="b4580-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="b4580-112">Windows 7 y Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b4580-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="b4580-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b4580-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="b4580-114">Productos de cliente de Office instalados en los dispositivos del trabajador</span><span class="sxs-lookup"><span data-stu-id="b4580-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="b4580-115">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b4580-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="b4580-116">Productos de servidor de Office instalados en servidores locales</span><span class="sxs-lookup"><span data-stu-id="b4580-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="b4580-117">Sus servicios basados en la nube equivalentes en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4580-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="b4580-118">Migración a Windows 10</span><span class="sxs-lookup"><span data-stu-id="b4580-118">Migrating to Windows 10</span></span>

<span data-ttu-id="b4580-119">Cada licencia de Microsoft 365 para empresas incluye una licencia para Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b4580-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="b4580-120">Para migrar los dispositivos que ejecutan Windows 7 o Windows 8.1, puedes realizar una actualización local.</span><span class="sxs-lookup"><span data-stu-id="b4580-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="b4580-121">El soporte técnico finalizó para Windows 7 *el 14 de enero de 2020*.</span><span class="sxs-lookup"><span data-stu-id="b4580-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="b4580-122">Para obtener métodos adicionales para instalar Windows 10 Enterprise más allá de una actualización local, consulta Escenarios de implementación de [Windows 10](/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="b4580-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="b4580-123">También puede [planear la implementación de Windows 10](/windows/deployment/planning/) por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="b4580-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b4580-124">Migración a Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b4580-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b4580-125">Microsoft 365 para empresas incluye Aplicaciones de Microsoft 365 para empresas, una versión de los productos cliente de Office (Word, PowerPoint, Excel y Outlook) que se instala y actualiza desde la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4580-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="b4580-126">Para obtener más información, vea [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="b4580-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="b4580-127">En lugar de mantener los equipos actuales para Office 2019 o versiones anteriores, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b4580-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="b4580-128">Obtener y asignar una licencia de Microsoft 365 para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b4580-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="b4580-129">Desinstale Office 2013 u Office 2016 en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="b4580-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="b4580-130">Instale Aplicaciones de Microsoft 365 para empresas, ya sea individualmente o durante un lanzamiento de TI.</span><span class="sxs-lookup"><span data-stu-id="b4580-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="b4580-131">Para obtener más información, vea [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="b4580-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="b4580-132">Aplicaciones de Microsoft 365 para empresas instala actualizaciones de seguridad y actualizaciones de nuevas características automáticamente y puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.</span><span class="sxs-lookup"><span data-stu-id="b4580-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="b4580-133">Migración de servidores y datos locales a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4580-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="b4580-134">Microsoft 365 para empresas incluye versiones basadas en la nube de servicios de servidor de Office que usan algunas de las mismas herramientas que las versiones locales del software de servidor de Office, como exploradores web y el cliente de Outlook.</span><span class="sxs-lookup"><span data-stu-id="b4580-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="b4580-135">Estos servicios basados en la nube se actualizan automáticamente para la seguridad y las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="b4580-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="b4580-136">Después de la migración, el departamento de TI puede ahorrar el tiempo necesario para mantener y actualizar los servidores locales.</span><span class="sxs-lookup"><span data-stu-id="b4580-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="b4580-137">Use los siguientes recursos para obtener información sobre la migración de usuarios y datos para cargas de trabajo específicas de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b4580-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="b4580-138">Mover buzones de correo de Exchange Server local a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b4580-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="b4580-139">Migrar datos de SharePoint desde SharePoint Server a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4580-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="b4580-140">Migrar Skype Empresarial Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4580-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="b4580-141">Realizar la transición en toda la organización</span><span class="sxs-lookup"><span data-stu-id="b4580-141">Transition your entire organization</span></span>

<span data-ttu-id="b4580-142">Para obtener una mejor imagen de cómo mover toda la organización a los productos y servicios de Microsoft 365 para empresas, descargue este póster de transición:</span><span class="sxs-lookup"><span data-stu-id="b4580-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="b4580-143">[![Imagen que muestra el póster Transición a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="b4580-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="b4580-144">Este póster de dos páginas es una forma rápida de hacer un inventario de la infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="b4580-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="b4580-145">Úselo para obtener instrucciones para pasar a un producto o servicio en Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="b4580-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="b4580-146">Muestra los productos de Windows y Office y otros elementos de infraestructura y seguridad, como la administración de dispositivos, la protección de identidades y amenazas, y la protección y cumplimiento de la información.</span><span class="sxs-lookup"><span data-stu-id="b4580-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="b4580-147">Resultados del paso 4</span><span class="sxs-lookup"><span data-stu-id="b4580-147">Results of Step 4</span></span>

<span data-ttu-id="b4580-148">Para la migración de su inquilino de Microsoft 365, ha determinado:</span><span class="sxs-lookup"><span data-stu-id="b4580-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="b4580-149">Qué dispositivos ejecutan Windows 7 o Windows 8.1 y el plan para actualizarlos a Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b4580-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="b4580-150">Qué dispositivos ejecutan las aplicaciones cliente de Office y el plan para actualizarlas a las aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="b4580-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="b4580-151">Qué servicios de servidor de Office locales deben migrarse a su equivalente de Microsoft 365 y el plan para migrarlos y sus datos.</span><span class="sxs-lookup"><span data-stu-id="b4580-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="b4580-152">Este es un ejemplo de un inquilino con una migración completada de servidores locales.</span><span class="sxs-lookup"><span data-stu-id="b4580-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Ejemplo de un inquilino con una migración completada de servidores locales](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="b4580-154">En esta ilustración, la organización tiene:</span><span class="sxs-lookup"><span data-stu-id="b4580-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="b4580-155">Migró sus buzones de correo Exchange Server locales a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b4580-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="b4580-156">Migró sus sitios y datos locales de SharePoint Server a SharePoint en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4580-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="b4580-157">Mantenimiento continuo para la migración</span><span class="sxs-lookup"><span data-stu-id="b4580-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="b4580-158">De forma continua, es posible que deba:</span><span class="sxs-lookup"><span data-stu-id="b4580-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="b4580-159">Según el estado de la migración del buzón de Exchange, continúe implementando la transición a Exchange Online a su organización.</span><span class="sxs-lookup"><span data-stu-id="b4580-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="b4580-160">Según el estado de la migración de sitios de SharePoint local, continúe implementando la transición a SharePoint en Microsoft 365 a su organización.</span><span class="sxs-lookup"><span data-stu-id="b4580-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4580-161">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b4580-161">Next step</span></span>

<span data-ttu-id="b4580-162">[![Paso 5. Implementar la administración de dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="b4580-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="b4580-163">Continúe con [la administración de dispositivos y aplicaciones](tenant-management-device-management.md) para implementar la administración de dispositivos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b4580-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>