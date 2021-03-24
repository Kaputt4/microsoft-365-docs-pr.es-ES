---
title: Transmitir eventos de Microsoft Defender para endpoint a Azure Event Hubs
description: Obtén información sobre cómo configurar ATP de Microsoft Defender para transmitir eventos de búsqueda avanzada a tu Centro de eventos.
keywords: Exportación de datos sin procesar, API de streaming, API, Azure Event Hubs, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071907"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="fdcbb-104">Configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a los centros de eventos de Azure</span><span class="sxs-lookup"><span data-stu-id="fdcbb-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fdcbb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fdcbb-105">**Applies to:**</span></span>

- [<span data-ttu-id="fdcbb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="fdcbb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="fdcbb-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fdcbb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fdcbb-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="fdcbb-109">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-109">Before you begin:</span></span>

1. <span data-ttu-id="fdcbb-110">Cree un [centro de eventos](https://docs.microsoft.com/azure/event-hubs/) en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-110">Create an [event hub](https://docs.microsoft.com/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="fdcbb-111">Inicie sesión en su inquilino de [Azure](https://ms.portal.azure.com/), vaya a \*\*Suscripciones > Su suscripción > proveedores de recursos > Registrarse en **Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to **Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="fdcbb-112">Habilitar la transmisión de datos sin procesar:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="fdcbb-113">Inicie sesión en el Centro de [seguridad de Microsoft Defender](https://securitycenter.windows.com) como \* Administrador **global** _ o _\* Administrador _de seguridad_\*\*.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="fdcbb-114">Vaya a la [página Configuración de exportación de datos](https://securitycenter.windows.com/interoperability/dataexport) en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="fdcbb-115">Haga clic en **Agregar configuración de exportación de datos.**</span><span class="sxs-lookup"><span data-stu-id="fdcbb-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="fdcbb-116">Elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="fdcbb-117">Elija **Reenviar eventos a Azure Event Hubs**.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="fdcbb-118">Escriba el **nombre de event hubs** y el **identificador de recurso de Event Hubs**.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="fdcbb-119">Para obtener el identificador de recurso **de Event Hubs,** vaya a la página de espacio de nombres de Azure Event Hubs en la pestaña propiedades de [Azure](https://ms.portal.azure.com/) > para > el texto en Id. de **recurso:**</span><span class="sxs-lookup"><span data-stu-id="fdcbb-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Imagen del recurso del centro de eventos Id1](images/event-hub-resource-id.png)

7. <span data-ttu-id="fdcbb-121">Elija los eventos que desea transmitir y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="fdcbb-122">Esquema de los eventos de Azure Event Hubs:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-122">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="fdcbb-123">Cada mensaje del centro de eventos de Azure Event Hubs contiene una lista de registros.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="fdcbb-124">Cada registro contiene el nombre del evento, la hora en que Microsoft Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="fdcbb-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="fdcbb-125">Para obtener más información sobre el esquema de eventos de Microsoft Defender para endpoint, vea [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fdcbb-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="fdcbb-126">En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="fdcbb-127">Aquí todos los eventos también se decorarán con esta columna.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="fdcbb-128">Consulta [Grupos de dispositivos](machine-groups.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="fdcbb-129">Asignación de tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-129">Data types mapping:</span></span>

<span data-ttu-id="fdcbb-130">Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="fdcbb-131">Inicie sesión en el [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com) y vaya a la página Búsqueda [avanzada](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="fdcbb-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="fdcbb-132">Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="fdcbb-133">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="fdcbb-133">Here is an example for Device Info event:</span></span> 

  ![Imagen del recurso del centro de eventos Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="fdcbb-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fdcbb-135">Related topics</span></span>
- [<span data-ttu-id="fdcbb-136">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="fdcbb-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fdcbb-137">API de streaming de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="fdcbb-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="fdcbb-138">Transmitir eventos de Microsoft Defender para endpoint a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="fdcbb-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="fdcbb-139">Documentación de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fdcbb-139">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="fdcbb-140">Solucionar problemas de conectividad: Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fdcbb-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
