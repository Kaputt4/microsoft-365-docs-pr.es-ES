---
title: Ver y administrar reglas de detección personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Obtenga información sobre cómo ver y administrar reglas de detección personalizadas
keywords: detecciones personalizadas, ver, administrar, alertas, editar, ejecutar a petición, reglas de detección, búsqueda avanzada, búsqueda, búsqueda, consulta, acciones de respuesta, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165782"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="74e0f-104">Ver y administrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="74e0f-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74e0f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="74e0f-105">**Applies to:**</span></span>
- [<span data-ttu-id="74e0f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="74e0f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74e0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74e0f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="74e0f-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="74e0f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="74e0f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="74e0f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="74e0f-110">Administre las reglas de [detección personalizadas existentes](custom-detection-rules.md) para asegurarse de que están detectando amenazas y llevando a cabo acciones de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="74e0f-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="74e0f-111">Explore cómo ver la lista de reglas, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="74e0f-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="74e0f-112">También puede ejecutar una regla a petición y modificarla.</span><span class="sxs-lookup"><span data-stu-id="74e0f-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="74e0f-113">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="74e0f-113">Required permissions</span></span>

<span data-ttu-id="74e0f-114">Para crear o administrar detecciones personalizadas, [el rol](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) debe tener el permiso administrar la **configuración de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="74e0f-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="74e0f-115">Ver reglas existentes</span><span class="sxs-lookup"><span data-stu-id="74e0f-115">View existing rules</span></span>

<span data-ttu-id="74e0f-116">Para ver todas las reglas de detección personalizadas existentes, vaya **a Configuración**  >  **Detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="74e0f-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="74e0f-117">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="74e0f-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="74e0f-118">**Última ejecución:** cuando se ejecuta por última vez una regla para comprobar si hay coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="74e0f-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="74e0f-119">**Estado de la última ejecución:** si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="74e0f-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="74e0f-120">**Siguiente ejecución**: la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="74e0f-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="74e0f-121">**Estado:** si se ha activado o desactivado una regla</span><span class="sxs-lookup"><span data-stu-id="74e0f-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="74e0f-122">Ver detalles de regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="74e0f-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="74e0f-123">Para ver información completa acerca de una regla de detección personalizada, seleccione el nombre de la regla de la lista de reglas en **Configuración**  >  **Detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="74e0f-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="74e0f-124">Una página sobre la regla seleccionada muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="74e0f-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="74e0f-125">Información general sobre la regla, incluidos los detalles de la alerta, el estado de ejecución y el ámbito</span><span class="sxs-lookup"><span data-stu-id="74e0f-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="74e0f-126">Lista de alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="74e0f-126">List of triggered alerts</span></span>
- <span data-ttu-id="74e0f-127">Lista de acciones desencadenadas</span><span class="sxs-lookup"><span data-stu-id="74e0f-127">List of triggered actions</span></span>

<span data-ttu-id="74e0f-128">![Página de regla de detección personalizada](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="74e0f-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="74e0f-129">*Página de regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="74e0f-129">*Custom detection rule page*</span></span>

<span data-ttu-id="74e0f-130">También puede realizar las siguientes acciones en la regla desde esta página:</span><span class="sxs-lookup"><span data-stu-id="74e0f-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="74e0f-131">**Ejecutar**: ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="74e0f-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="74e0f-132">Esta acción también restablece el intervalo de la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="74e0f-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="74e0f-133">**Editar**: modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="74e0f-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="74e0f-134">**Modificar consulta**: editar la consulta en búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="74e0f-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="74e0f-135">**Activar**  /  **Desactivar :** habilitar la regla o impedir que se ejecute</span><span class="sxs-lookup"><span data-stu-id="74e0f-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="74e0f-136">**Eliminar**: desactivar la regla y quitarla</span><span class="sxs-lookup"><span data-stu-id="74e0f-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="74e0f-137">Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="74e0f-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="74e0f-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="74e0f-138">Related topics</span></span>
- [<span data-ttu-id="74e0f-139">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="74e0f-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="74e0f-140">Crear reglas de detección</span><span class="sxs-lookup"><span data-stu-id="74e0f-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="74e0f-141">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="74e0f-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="74e0f-142">Ver y organizar alertas</span><span class="sxs-lookup"><span data-stu-id="74e0f-142">View and organize alerts</span></span>](alerts-queue.md)
