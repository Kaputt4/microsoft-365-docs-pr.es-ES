---
title: Transmitir eventos Microsoft 365 Defender a Azure Event Hub
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu Centro de eventos.
keywords: Exportación de datos sin procesar, API de streaming, API, Centro de eventos de Azure, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: c62f175fc8227f64b9f18de78a2a793b2201691c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782374"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="d6ae8-104">Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a su Centro de eventos de Azure</span><span class="sxs-lookup"><span data-stu-id="d6ae8-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d6ae8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d6ae8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6ae8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6ae8-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="d6ae8-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d6ae8-107">Before you begin</span></span>

1. <span data-ttu-id="d6ae8-108">Cree un [centro de eventos](/azure/event-hubs/) en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="d6ae8-109">Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="d6ae8-110">Cree un espacio de nombres de centro de eventos, vaya a **Event Hub > Agregar** y seleccione el nivel de precios, las unidades de rendimiento y la opción Autoinflate adecuada para la carga esperada.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="d6ae8-111">Para obtener más información, vea [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="d6ae8-112">Agregar permisos de colaborador</span><span class="sxs-lookup"><span data-stu-id="d6ae8-112">Add contributor permissions</span></span> 
<span data-ttu-id="d6ae8-113">Una vez creado el espacio de nombres del Centro de eventos, deberá agregar la entidad de seguridad del servicio de registro de aplicaciones como Lector, el receptor de datos del Centro de eventos de Azure y el usuario que iniciará sesión en Microsoft 365 Defender como colaborador (esto también se puede hacer a nivel de grupo de recursos o suscripción).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-113">Once the Event Hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> 

<span data-ttu-id="d6ae8-114">Vaya al espacio de nombres Event hubs > Control de **acceso (IAM)** > Agregar y comprobar en **Asignaciones de roles**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-114">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="d6ae8-115">Habilitar la transmisión de datos sin procesar</span><span class="sxs-lookup"><span data-stu-id="d6ae8-115">Enable raw data streaming</span></span>

1. <span data-ttu-id="d6ae8-116">Inicie sesión en el [centro de seguridad de Microsoft 365 Defender](https://security.microsoft.com) como administrador **global**\* o administrador de seguridad __\*_\*\*.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-116">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="d6ae8-117">Vaya a la página [Configuración de la API de streaming.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="d6ae8-117">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="d6ae8-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-118">Click on **Add**.</span></span>

4. <span data-ttu-id="d6ae8-119">Elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-119">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="d6ae8-120">Elija **Reenviar eventos a Azure Event Hub**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-120">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="d6ae8-121">Puede seleccionar si desea exportar los datos del evento a un único centro de eventos o exportar cada tabla de eventos a un centro de eventos diferente en el espacio de nombres del Centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-121">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="d6ae8-122">Para exportar los datos del evento a un único centro de eventos, escriba el nombre del centro de eventos **y** el identificador de recurso del centro **de eventos**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-122">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="d6ae8-123">Para obtener el identificador **de** recurso del Centro de eventos, vaya a la página de espacio de nombres del Centro de eventos de Azure en la pestaña Propiedades de [Azure](https://ms.portal.azure.com/)> copiar el texto en  >   **Id. de recurso:**</span><span class="sxs-lookup"><span data-stu-id="d6ae8-123">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Imagen del id. de recurso del centro de eventos1](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="d6ae8-125">Elija los eventos que desea transmitir y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-125">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="d6ae8-126">Esquema de los eventos en Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="d6ae8-126">The schema of the events in Azure Event Hub</span></span>

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="d6ae8-127">Cada mensaje del Centro de eventos de Azure Event Hub contiene una lista de registros.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-127">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="d6ae8-128">Cada registro contiene el nombre del evento, la hora en que Microsoft 365 Defender recibió el evento, el inquilino al que pertenece (solo recibirá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="d6ae8-128">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="d6ae8-129">Para obtener más información sobre el esquema de Microsoft 365 Defender, vea [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="d6ae8-130">En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-130">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="d6ae8-131">Aquí todos los eventos también se decorarán con esta columna.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-131">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="d6ae8-132">Asignación de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d6ae8-132">Data types mapping</span></span>

<span data-ttu-id="d6ae8-133">Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6ae8-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="d6ae8-134">Inicie sesión en [el Microsoft 365 seguridad y](https://security.microsoft.com) vaya a la página Búsqueda [avanzada](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="d6ae8-135">Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="d6ae8-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="d6ae8-136">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="d6ae8-136">Here is an example for Device Info event:</span></span> 

  ![Imagen del id. de recurso del centro de eventos2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="d6ae8-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d6ae8-138">Related topics</span></span>
- [<span data-ttu-id="d6ae8-139">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="d6ae8-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6ae8-140">Microsoft 365 Defender streaming API</span><span class="sxs-lookup"><span data-stu-id="d6ae8-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="d6ae8-141">Transmitir eventos Microsoft 365 Defender a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="d6ae8-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="d6ae8-142">Documentación de Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="d6ae8-142">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="d6ae8-143">Solucionar problemas de conectividad: Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="d6ae8-143">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
