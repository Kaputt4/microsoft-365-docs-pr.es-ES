---
title: Características de vista previa de la protección contra amenazas de Microsoft
description: Obtenga información sobre las nuevas características de la seguridad de Microsoft 365
keywords: vista previa, nueva M365 Security, Security, 365, Capabilities
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6287e7c56f79b09a79c75d7e8b8273dbd5569057
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005895"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="8ce8c-104">Características preliminares de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8ce8c-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="8ce8c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8ce8c-105">**Applies to:**</span></span>
- <span data-ttu-id="8ce8c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ce8c-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="8ce8c-107">El servicio de protección contra amenazas de Microsoft se actualiza constantemente para incluir nuevas funciones y mejoras de características.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="8ce8c-108">Obtenga información sobre las nuevas características de la versión preliminar de Microsoft Threat Protection y realice una de las primeras características para probar la experiencia de vista previa.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="8ce8c-109">Para obtener más información sobre las nuevas funciones disponibles de forma general, consulte la sección de [Novedades en la Protección contra amenazas de Microsoft](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="8ce8c-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="8ce8c-110">Activar las características de vista previa</span><span class="sxs-lookup"><span data-stu-id="8ce8c-110">Turn on preview features</span></span>
<span data-ttu-id="8ce8c-111">Tendrá acceso a las próximas características en las que puede enviar comentarios para ayudar a mejorar la experiencia general antes de que las características estén disponibles para el público en general.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="8ce8c-112">Active la configuración de la experiencia de vista previa para que sea una de las primeras y pruebe las características futuras.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="8ce8c-113">En el panel de navegación, seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="8ce8c-114">Seleccione **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="8ce8c-115">Opciones de **vista previa**Active las  >  **características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="8ce8c-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-116">Select **Save**.</span></span>

<span data-ttu-id="8ce8c-117">Sabrá que tiene características de vista previa activadas cuando vea que está activada la casilla **de verificación Activar las características de vista previa** .</span><span class="sxs-lookup"><span data-stu-id="8ce8c-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="8ce8c-118">Versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="8ce8c-118">Preview features</span></span>
<span data-ttu-id="8ce8c-119">Las siguientes características y mejoras están disponibles actualmente en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="8ce8c-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="8ce8c-120">**[Tablas de identidad y aplicación](advanced-hunting-schema-tables.md)** : obtenga visibilidad de los eventos de autenticación, las consultas de Active Directory y la actividad relacionada con la aplicación con las tablas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)y [AppFileEvents](advanced-hunting-appfileevents-table.md) en el esquema de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-120">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="8ce8c-121">**[Go Hunt](advanced-hunting-go-hunt.md)** — rápidamente dinamizando desde la investigación de un incidente hasta la inspección de un evento específico, un usuario, un dispositivo u otros tipos de entidad mediante funciones de [búsqueda avanzada](advanced-hunting-overview.md) basadas en consultas.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-121">**[Go hunt](advanced-hunting-go-hunt.md)** — quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>

- <span data-ttu-id="8ce8c-122">**[Función FileProfile ()](advanced-hunting-fileprofile-function.md)** : Úsela en las consultas de [búsqueda avanzada](advanced-hunting-overview.md) para incorporar información de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="8ce8c-122">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
