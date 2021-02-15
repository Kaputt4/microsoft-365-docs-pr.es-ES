---
title: Paso 1. Sus inquilinos de Microsoft 365 para empresas
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
ms.custom:
- Ent_Solutions
description: Implemente y administre uno o varios inquilinos de Microsoft 365, con opciones para ubicaciones multige geográficas y móviles.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908720"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="6ded1-104">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="6ded1-104">Step 1.</span></span> <span data-ttu-id="6ded1-105">Sus inquilinos de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6ded1-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="6ded1-106">Una de las primeras decisiones del espacio empresarial es cuántas deben tener.</span><span class="sxs-lookup"><span data-stu-id="6ded1-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="6ded1-107">Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="6ded1-108">Su inquilino de Azure AD correspondiente también es distinto, único e independiente de todos los demás inquilinos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="6ded1-109">Inquilino único</span><span class="sxs-lookup"><span data-stu-id="6ded1-109">Single tenant</span></span>
<span data-ttu-id="6ded1-110">Tener un único inquilino simplifica muchos aspectos del uso de Microsoft 365 por parte de su organización.</span><span class="sxs-lookup"><span data-stu-id="6ded1-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="6ded1-111">Un único inquilino significa un único inquilino de Azure AD con un único conjunto de cuentas, grupos y directivas.</span><span class="sxs-lookup"><span data-stu-id="6ded1-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="6ded1-112">Los permisos y el uso compartido de recursos en toda la organización se pueden realizar a través de este proveedor de identidades central.</span><span class="sxs-lookup"><span data-stu-id="6ded1-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="6ded1-113">Un único espacio empresarial proporciona la experiencia de productividad y colaboración más completa y simplificada de características para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ded1-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="6ded1-114">Este es un ejemplo que muestra la ubicación predeterminada y el inquilino de Azure AD de un inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Un único inquilino de Microsoft 365 con su inquilino de Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="6ded1-116">Varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="6ded1-116">Multiple tenants</span></span>

<span data-ttu-id="6ded1-117">Hay muchas razones por las que su organización podría tener varios inquilinos:</span><span class="sxs-lookup"><span data-stu-id="6ded1-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="6ded1-118">Aislamiento administrativo</span><span class="sxs-lookup"><span data-stu-id="6ded1-118">Administrative isolation</span></span>
- <span data-ttu-id="6ded1-119">IT descentralizada</span><span class="sxs-lookup"><span data-stu-id="6ded1-119">Decentralized IT</span></span>
- <span data-ttu-id="6ded1-120">Decisiones históricas</span><span class="sxs-lookup"><span data-stu-id="6ded1-120">Historical decisions</span></span>
- <span data-ttu-id="6ded1-121">Fusiones, adquisiciones o desinsticiones</span><span class="sxs-lookup"><span data-stu-id="6ded1-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="6ded1-122">Separación clara de la personalción de marca para organizaciones conglomerados</span><span class="sxs-lookup"><span data-stu-id="6ded1-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="6ded1-123">Inquilinos de espacio aislado, pruebas o preproducción</span><span class="sxs-lookup"><span data-stu-id="6ded1-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="6ded1-124">Este es un ejemplo de una organización que tiene dos inquilinos (Inquilino A y Inquilino B) en la misma ubicación geográfica predeterminada del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="6ded1-125">Cada inquilino como un inquilino de Azure AD independiente.</span><span class="sxs-lookup"><span data-stu-id="6ded1-125">Each tenant as a separate Azure AD tenant.</span></span>

![Varios inquilinos de Microsoft 365 con sus propios inquilinos de Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="6ded1-127">Cuando tiene varios inquilinos, existen restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ded1-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="6ded1-128">Colaboración entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="6ded1-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="6ded1-129">Si desea que los usuarios colaboren de forma más eficaz en diferentes inquilinos de Microsoft 365 de forma segura, las opciones de colaboración entre inquilinos incluyen el uso de una ubicación central para archivos y conversaciones, el uso compartido de calendarios, el uso de mensajería instantánea, llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6ded1-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="6ded1-130">Para obtener más información, consulte [Colaboración entre inquilinos de Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="6ded1-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="6ded1-131">Migración de buzones entre inquilinos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6ded1-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="6ded1-132">Antes de la migración de buzones entre inquilinos (en versión preliminar), al mover buzones de Exchange Online entre inquilinos, debe quitar completamente un buzón de usuario de su inquilino actual (el inquilino de origen) a local y, a continuación, incorporarlos a un nuevo inquilino (el inquilino de destino).</span><span class="sxs-lookup"><span data-stu-id="6ded1-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="6ded1-133">Con la nueva característica de migración de buzones entre inquilinos, los administradores de inquilinos de los inquilinos de origen y de destino pueden mover buzones entre los inquilinos con dependencias de infraestructura mínimas en sus sistemas locales.</span><span class="sxs-lookup"><span data-stu-id="6ded1-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="6ded1-134">Esto elimina la necesidad de incorporar buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="6ded1-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="6ded1-135">Estos son dos inquilinos de ejemplo y sus buzones antes de la migración de buzones entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Varios inquilinos de Microsoft 365 y sus buzones](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="6ded1-137">En esta ilustración, dos inquilinos independientes tienen sus propios dominios y un conjunto de buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6ded1-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="6ded1-138">Este es el inquilino de destino (inquilino A) después de la migración de buzones entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![El inquilino de destino después de la migración de buzones entre inquilinos](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="6ded1-140">En esta ilustración, un único inquilino tiene dominios y ambos conjuntos de buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6ded1-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="6ded1-141">Para obtener más información, consulte [Migración de buzones entre inquilinos.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="6ded1-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="6ded1-142">Migraciones de espacio empresarial a espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="6ded1-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="6ded1-143">Existen varios enfoques arquitectónicos para fusiones, adquisiciones, desintecciones y otros escenarios que pueden llevar a migrar un inquilino de Microsoft 365 existente a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="6ded1-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="6ded1-144">Para obtener instrucciones detalladas, consulte Migraciones de inquilino a inquilino [de Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="6ded1-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="6ded1-145">Multi-Geo para un inquilino</span><span class="sxs-lookup"><span data-stu-id="6ded1-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="6ded1-146">Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que haya elegido para cumplir los requisitos de residencia de datos y, al mismo tiempo, desbloquear la implementación global de experiencias de productividad modernas para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6ded1-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="6ded1-147">En un entorno Multi-Geo, su espacio empresarial de Microsoft 365 consta de una ubicación central o predeterminada donde se creó originalmente su suscripción a Microsoft 365 y una o más ubicaciones satélite.</span><span class="sxs-lookup"><span data-stu-id="6ded1-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="6ded1-148">En un inquilino multigemico, la información sobre las ubicaciones geográficas, los grupos y la información de usuario se masterizó en un inquilino global de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6ded1-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="6ded1-149">Dado que la información del espacio empresarial se masterizó de forma centralizada y se sincroniza en cada ubicación geográfica, las experiencias de colaboración en las que participan todos los usuarios de su empresa se comparten entre las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="6ded1-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="6ded1-150">Este es un ejemplo de una organización que tiene su ubicación predeterminada en Europa y una ubicación satélite en Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="6ded1-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="6ded1-151">Ambas ubicaciones comparten el mismo inquilino global de Azure AD para el único inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Ejemplo de un inquilino multigemico de Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="6ded1-153">Para más información, vea [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="6ded1-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="6ded1-154">Mover datos principales a una nueva ubicación geográfica de centro de datos</span><span class="sxs-lookup"><span data-stu-id="6ded1-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="6ded1-155">Microsoft continúa abierto nuevas ubicaciones geográficas de centro de datos para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="6ded1-156">Estas nuevas ubicaciones geográficas de centro de datos agregan capacidad y recursos de cálculo para admitir nuestra demanda continuada de clientes y el crecimiento del uso.</span><span class="sxs-lookup"><span data-stu-id="6ded1-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="6ded1-157">Además, las nuevas ubicaciones geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.</span><span class="sxs-lookup"><span data-stu-id="6ded1-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="6ded1-158">Aunque la apertura de una nueva ubicación geográfica de centro de datos no afecta a usted y a los datos principales almacenados en una ubicación geográfica de centro de datos ya existente, Microsoft le permite solicitar una migración anticipada de los datos principales del cliente de su organización en reposo a una nueva ubicación geográfica del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="6ded1-159">Este es un ejemplo en el que un inquilino de Microsoft 365 se movió de la ubicación geográfica del centro de datos de la Unión Europea (UE) a la ubicada en el Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="6ded1-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Ejemplo de mover un espacio empresarial de Microsoft 365 entre las ubicaciones geográficas del centro de datos](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="6ded1-161">Para obtener más información, vea Mover los datos principales a las nuevas ubicaciones geográficas del centro de datos [de Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="6ded1-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="6ded1-162">Productos y licencias para un inquilino</span><span class="sxs-lookup"><span data-stu-id="6ded1-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="6ded1-163">El espacio empresarial de Microsoft 365 se crea al comprar el primer producto, como Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="6ded1-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="6ded1-164">Junto con el producto se encuentran las licencias, a las que se les cobra una tarifa mensual o anual.</span><span class="sxs-lookup"><span data-stu-id="6ded1-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="6ded1-165">A continuación, un administrador asigna una licencia disponible de uno de los productos a una cuenta de usuario, ya sea directamente o a través de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="6ded1-166">Según las necesidades empresariales de su organización, es posible que tenga un conjunto de productos, cada uno con su propio grupo de licencias.</span><span class="sxs-lookup"><span data-stu-id="6ded1-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="6ded1-167">La determinación del conjunto de productos y el número de licencias de cada uno de ellos requiere cierta planeación para:</span><span class="sxs-lookup"><span data-stu-id="6ded1-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="6ded1-168">Asegúrese de que tiene suficientes licencias para las cuentas de usuario que necesitan características avanzadas.</span><span class="sxs-lookup"><span data-stu-id="6ded1-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="6ded1-169">Impedir que se quedas sin licencias o que tenga demasiadas licencias sinsignar, en función de los cambios en el personal de la organización.</span><span class="sxs-lookup"><span data-stu-id="6ded1-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="6ded1-170">Resultado del paso 1</span><span class="sxs-lookup"><span data-stu-id="6ded1-170">Results of Step 1</span></span>

<span data-ttu-id="6ded1-171">Para los inquilinos de Microsoft 365 para empresas, ha determinado:</span><span class="sxs-lookup"><span data-stu-id="6ded1-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="6ded1-172">Cuántos inquilinos tiene o necesita.</span><span class="sxs-lookup"><span data-stu-id="6ded1-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="6ded1-173">Para cada inquilino, qué productos y licencias se deben comprar.</span><span class="sxs-lookup"><span data-stu-id="6ded1-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="6ded1-174">Si un inquilino debe ser Multi-Geo para cumplir con los requisitos de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="6ded1-175">Si necesita configurar la colaboración entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="6ded1-176">Si necesita migrar un inquilino a otro.</span><span class="sxs-lookup"><span data-stu-id="6ded1-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="6ded1-177">Si necesita mover los datos principales de una ubicación geográfica de centro de datos a uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="6ded1-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="6ded1-178">Este es un ejemplo de un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="6ded1-178">Here is an example of a new tenant.</span></span>

![Ejemplo de un nuevo inquilino](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="6ded1-180">En esta ilustración, el inquilino tiene:</span><span class="sxs-lookup"><span data-stu-id="6ded1-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="6ded1-181">Ubicación predeterminada correspondiente a una ubicación geográfica de centro de datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="6ded1-182">Un conjunto de productos y licencias.</span><span class="sxs-lookup"><span data-stu-id="6ded1-182">A set of products and licenses.</span></span>
- <span data-ttu-id="6ded1-183">El conjunto de aplicaciones de productividad en la nube, algunas de las cuales son específicas de los productos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="6ded1-184">Un inquilino de Azure AD que contiene cuentas de administrador global y un nombre de dominio DNS inicial.</span><span class="sxs-lookup"><span data-stu-id="6ded1-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="6ded1-185">A medida que avancemos en los pasos adicionales de esta solución, crearemos esta figura.</span><span class="sxs-lookup"><span data-stu-id="6ded1-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="6ded1-186">Mantenimiento continuo para inquilinos</span><span class="sxs-lookup"><span data-stu-id="6ded1-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="6ded1-187">De forma continua, es posible que deba:</span><span class="sxs-lookup"><span data-stu-id="6ded1-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="6ded1-188">Agregue un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="6ded1-188">Add a new tenant.</span></span>
- <span data-ttu-id="6ded1-189">Agregar nuevos productos a un inquilino con un número inicial de licencias.</span><span class="sxs-lookup"><span data-stu-id="6ded1-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="6ded1-190">Cambiar el conjunto de licencias de un producto en un espacio empresarial para ajustarse a los requisitos de personal cambiantes.</span><span class="sxs-lookup"><span data-stu-id="6ded1-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="6ded1-191">Mueva los datos principales de un espacio empresarial a una nueva ubicación geográfica del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="6ded1-192">Agregar Multi-Geo para requisitos de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="6ded1-193">Configurar la colaboración entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="6ded1-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="6ded1-194">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6ded1-194">Next step</span></span>

<span data-ttu-id="6ded1-195">[![Paso 2. Optimizar el espacio empresarial para la red para el acceso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="6ded1-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="6ded1-196">Continúe con [las redes](tenant-management-networking.md) para proporcionar redes óptimas de sus trabajadores a los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ded1-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
