---
title: Administrar reglas de supresión de Microsoft Defender para puntos de conexión
description: Es posible que necesite evitar que las alertas aparezcan en el portal mediante reglas de supresión. Obtén información sobre cómo administrar las reglas de supresión en ATP de Microsoft Defender.
keywords: administrar supresión, reglas, nombre de regla, ámbito, acción, alertas, activar, desactivar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072003"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="6b5e0-105">Administrar reglas de supresión</span><span class="sxs-lookup"><span data-stu-id="6b5e0-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6b5e0-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6b5e0-106">**Applies to:**</span></span>
- [<span data-ttu-id="6b5e0-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6b5e0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6b5e0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b5e0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6b5e0-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6b5e0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b5e0-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="6b5e0-111">Puede haber escenarios en los que necesite suprimir las alertas para que no aparezcan en el portal.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="6b5e0-112">Puede crear reglas de supresión para alertas específicas que se sabe que son inocuas, como herramientas o procesos conocidos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="6b5e0-113">Para obtener más información sobre cómo suprimir alertas, vea [Suprimir alertas](manage-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="6b5e0-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="6b5e0-114">Puede ver una lista de todas las reglas de supresión y administrarlas en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="6b5e0-115">También puede activar o desactivar una regla de supresión de alertas.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="6b5e0-116">En el panel de navegación, seleccione **Configuración**  >  **supresión de alertas**.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="6b5e0-117">Se muestra la lista de reglas de supresión que los usuarios de la organización han creado.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="6b5e0-118">Seleccione una regla haciendo clic en la casilla situada junto al nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="6b5e0-119">Haga **clic en Activar regla,** Editar **regla** o  **Eliminar regla**.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="6b5e0-120">Al realizar cambios en una regla, puede elegir liberar alertas que ya ha suprimido, independientemente de si estas alertas coinciden o no con los nuevos criterios.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="6b5e0-121">Ver detalles de una regla de supresión</span><span class="sxs-lookup"><span data-stu-id="6b5e0-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="6b5e0-122">En el panel de navegación, seleccione **Configuración**  >  **supresión de alertas**.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="6b5e0-123">Se muestra la lista de reglas de supresión que los usuarios de la organización han creado.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="6b5e0-124">Haga clic en un nombre de regla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-124">Click on a rule name.</span></span> <span data-ttu-id="6b5e0-125">Se muestran los detalles de la regla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-125">Details of the rule is displayed.</span></span> <span data-ttu-id="6b5e0-126">Verá los detalles de la regla, como el estado, el ámbito, la acción, el número de alertas de coincidencia, creadas por y la fecha en que se creó la regla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="6b5e0-127">También puede ver las alertas asociadas y las condiciones de regla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b5e0-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6b5e0-128">Related topics</span></span>

- [<span data-ttu-id="6b5e0-129">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="6b5e0-129">Manage alerts</span></span>](manage-alerts.md)
