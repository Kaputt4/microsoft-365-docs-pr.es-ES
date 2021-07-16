---
title: Administrar reglas de supresión de Microsoft Defender para puntos de conexión
description: Es posible que necesite evitar que las alertas aparezcan en el portal mediante reglas de supresión. Obtenga información sobre cómo administrar las reglas de supresión en Microsoft Defender para endpoint.
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
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454762"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="71655-105">Administrar reglas de supresión</span><span class="sxs-lookup"><span data-stu-id="71655-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71655-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="71655-106">**Applies to:**</span></span>
- [<span data-ttu-id="71655-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="71655-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71655-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71655-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71655-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="71655-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71655-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="71655-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="71655-111">Puede haber escenarios en los que necesite suprimir las alertas para que no aparezcan en el portal.</span><span class="sxs-lookup"><span data-stu-id="71655-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="71655-112">Puede crear reglas de supresión para alertas específicas que se sabe que son inocuas, como herramientas o procesos conocidos de la organización.</span><span class="sxs-lookup"><span data-stu-id="71655-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="71655-113">Para obtener más información sobre cómo suprimir alertas, vea [Suprimir alertas](manage-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="71655-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="71655-114">Puede ver una lista de todas las reglas de supresión y administrarlas en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="71655-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="71655-115">También puede activar o desactivar una regla de supresión de alertas.</span><span class="sxs-lookup"><span data-stu-id="71655-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="71655-116">En el panel de navegación, seleccione **Configuración**  >  **de alerta de reglas**  >  **de** extremos  >  .</span><span class="sxs-lookup"><span data-stu-id="71655-116">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Alert suppression**.</span></span> <span data-ttu-id="71655-117">Se muestra la lista de reglas de supresión que los usuarios de la organización han creado.</span><span class="sxs-lookup"><span data-stu-id="71655-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="71655-118">Seleccione una regla haciendo clic en la casilla situada junto al nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="71655-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="71655-119">Haga **clic en Activar regla,** Editar **regla** o  **Eliminar regla**.</span><span class="sxs-lookup"><span data-stu-id="71655-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="71655-120">Al realizar cambios en una regla, puede elegir liberar alertas que ya ha suprimido, independientemente de si estas alertas coinciden o no con los nuevos criterios.</span><span class="sxs-lookup"><span data-stu-id="71655-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="71655-121">Ver detalles de una regla de supresión</span><span class="sxs-lookup"><span data-stu-id="71655-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="71655-122">En el panel de navegación, seleccione **Configuración**  >  **de alerta de reglas**  >  **de** extremos  >  .</span><span class="sxs-lookup"><span data-stu-id="71655-122">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Alert suppression**.</span></span> <span data-ttu-id="71655-123">Se muestra la lista de reglas de supresión que los usuarios de la organización han creado.</span><span class="sxs-lookup"><span data-stu-id="71655-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="71655-124">Haga clic en un nombre de regla.</span><span class="sxs-lookup"><span data-stu-id="71655-124">Click on a rule name.</span></span> <span data-ttu-id="71655-125">Se muestran los detalles de la regla.</span><span class="sxs-lookup"><span data-stu-id="71655-125">Details of the rule is displayed.</span></span> <span data-ttu-id="71655-126">Verá los detalles de la regla, como el estado, el ámbito, la acción, el número de alertas de coincidencia, creadas por y la fecha en que se creó la regla.</span><span class="sxs-lookup"><span data-stu-id="71655-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="71655-127">También puede ver las alertas asociadas y las condiciones de regla.</span><span class="sxs-lookup"><span data-stu-id="71655-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71655-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="71655-128">Related topics</span></span>

- [<span data-ttu-id="71655-129">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="71655-129">Manage alerts</span></span>](manage-alerts.md)
