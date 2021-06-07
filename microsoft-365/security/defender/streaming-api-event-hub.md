---
title: Transmitir eventos de Microsoft 365 Defender a Azure Event Hubs
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu Centro de eventos.
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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772562"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="4b66b-104">Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a los centros de eventos de Azure</span><span class="sxs-lookup"><span data-stu-id="4b66b-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b66b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4b66b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b66b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b66b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="4b66b-107">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="4b66b-107">Before you begin:</span></span>

1. <span data-ttu-id="4b66b-108">Cree un [centro de eventos](/azure/event-hubs/) en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4b66b-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="4b66b-109">Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="4b66b-110">Cree un espacio de nombres de centro de eventos, vaya a **Event Hubs > Agregar** y seleccione el nivel de precios, las unidades de rendimiento y la opción Autoinflate adecuada para la carga esperada.</span><span class="sxs-lookup"><span data-stu-id="4b66b-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="4b66b-111">Para obtener más información, vea [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="4b66b-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="4b66b-112">Una vez creado el espacio de nombres del centro de eventos, deberá agregar la entidad de seguridad del servicio de registro de aplicaciones como Lector, el receptor de datos de Azure Event Hubs y el usuario que iniciará sesión en Microsoft 365 Defender como colaborador (esto también se puede hacer a nivel de grupo de recursos o suscripción).</span><span class="sxs-lookup"><span data-stu-id="4b66b-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="4b66b-113">Vaya al **espacio de nombres Event hubs > Access control (IAM) > Add** and verify en Role **assignements**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="4b66b-114">Habilitar la transmisión de datos sin procesar:</span><span class="sxs-lookup"><span data-stu-id="4b66b-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="4b66b-115">Inicie sesión en el [centro de seguridad de Microsoft 365 Defender](https://security.microsoft.com) como administrador **global**\* o administrador de seguridad __\*_\*\*.</span><span class="sxs-lookup"><span data-stu-id="4b66b-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="4b66b-116">Vaya a la [página Configuración de exportación de datos](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span><span class="sxs-lookup"><span data-stu-id="4b66b-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="4b66b-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-117">Click on **Add**.</span></span>

4. <span data-ttu-id="4b66b-118">Elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="4b66b-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="4b66b-119">Elija **Reenviar eventos a Azure Event Hubs**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="4b66b-120">Puede seleccionar si desea exportar los datos de eventos a un único centro de eventos o exportar cada tabla de eventos a un concentrador par diferente en el espacio de nombres del centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="4b66b-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="4b66b-121">Para exportar los datos del evento a un único centro de eventos, escriba el nombre del centro de eventos **y** el identificador de recurso del centro **de eventos**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="4b66b-122">Para obtener el identificador de recurso de **Event Hubs,** vaya a la página de espacio de nombres de Azure Event Hubs en la pestaña Propiedades de [Azure](https://ms.portal.azure.com/)> el texto en  >   **Id. de recurso**:</span><span class="sxs-lookup"><span data-stu-id="4b66b-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Imagen del recurso del centro de eventos Id1](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="4b66b-124">Elija los eventos que desea transmitir y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b66b-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="4b66b-125">Esquema de los eventos de Azure Event Hubs:</span><span class="sxs-lookup"><span data-stu-id="4b66b-125">The schema of the events in Azure Event Hubs:</span></span>

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

- <span data-ttu-id="4b66b-126">Cada mensaje del centro de eventos de Azure Event Hubs contiene una lista de registros.</span><span class="sxs-lookup"><span data-stu-id="4b66b-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="4b66b-127">Cada registro contiene el nombre del evento, la hora en que Microsoft 365 Defender recibió el evento, el inquilino al que pertenece (solo recibirá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="4b66b-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="4b66b-128">Para obtener más información sobre el esquema de Microsoft 365 Defender, vea [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b66b-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="4b66b-129">En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b66b-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="4b66b-130">Aquí todos los eventos también se decorarán con esta columna.</span><span class="sxs-lookup"><span data-stu-id="4b66b-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="4b66b-131">Para exportar cada tabla de eventos a  un centro de eventos diferente, simplemente deje el nombre del centro de eventos vacío y Microsoft 365 Defender hará el resto.</span><span class="sxs-lookup"><span data-stu-id="4b66b-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="4b66b-132">Asignación de tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="4b66b-132">Data types mapping:</span></span>

<span data-ttu-id="4b66b-133">Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b66b-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="4b66b-134">Inicie sesión en [el Microsoft 365 seguridad y](https://security.microsoft.com) vaya a la página Búsqueda [avanzada](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="4b66b-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="4b66b-135">Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="4b66b-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="4b66b-136">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="4b66b-136">Here is an example for Device Info event:</span></span> 

  ![Imagen del recurso del centro de eventos Id2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="4b66b-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4b66b-138">Related topics</span></span>
- [<span data-ttu-id="4b66b-139">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="4b66b-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4b66b-140">Microsoft 365 Defender streaming API</span><span class="sxs-lookup"><span data-stu-id="4b66b-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="4b66b-141">Transmitir eventos Microsoft 365 Defender a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="4b66b-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="4b66b-142">Documentación de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="4b66b-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="4b66b-143">Solucionar problemas de conectividad: Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="4b66b-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
