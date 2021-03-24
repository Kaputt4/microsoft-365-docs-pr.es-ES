---
title: Transmitir eventos de Microsoft Defender para endpoint a su cuenta de almacenamiento
description: Obtén información sobre cómo configurar ATP de Microsoft Defender para transmitir eventos de búsqueda avanzada a tu cuenta de almacenamiento.
keywords: Exportación de datos sin procesar, API de streaming, API, Centros de eventos, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: 9f1eb79bbf617afad58b7e4d70e1f40e422f9046
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071888"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="b10ef-104">Configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a su cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="b10ef-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b10ef-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b10ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="b10ef-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b10ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="b10ef-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b10ef-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b10ef-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b10ef-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="b10ef-109">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="b10ef-109">Before you begin:</span></span>

1. <span data-ttu-id="b10ef-110">Cree una [cuenta de almacenamiento](https://docs.microsoft.com/azure/storage/common/storage-account-overview) en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="b10ef-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="b10ef-111">Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="b10ef-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="b10ef-112">Habilitar la transmisión de datos sin procesar:</span><span class="sxs-lookup"><span data-stu-id="b10ef-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="b10ef-113">Inicie sesión en [el portal de Microsoft Defender para endpoint](https://securitycenter.windows.com) como \* Administrador **global** _ o _\* Administrador _de seguridad_\*\*.</span><span class="sxs-lookup"><span data-stu-id="b10ef-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="b10ef-114">Vaya a [la página Configuración de exportación de datos](https://securitycenter.windows.com/interoperability/dataexport) en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b10ef-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="b10ef-115">Haga clic en **Agregar configuración de exportación de datos.**</span><span class="sxs-lookup"><span data-stu-id="b10ef-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="b10ef-116">Elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="b10ef-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="b10ef-117">Elija **Reenviar eventos a Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="b10ef-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="b10ef-118">Escriba el **identificador de recurso de la cuenta de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="b10ef-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="b10ef-119">Para obtener el identificador de recurso de la cuenta de **almacenamiento,** vaya a la página Cuenta de almacenamiento de [Azure Portal](https://ms.portal.azure.com/) > pestaña propiedades > copiar el texto en Id. de recurso de cuenta de **almacenamiento:**</span><span class="sxs-lookup"><span data-stu-id="b10ef-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Imagen del id. de recurso del centro de eventos1](images/storage-account-resource-id.png)

7. <span data-ttu-id="b10ef-121">Elija los eventos que desea transmitir y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b10ef-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="b10ef-122">Esquema de los eventos de la cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="b10ef-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="b10ef-123">Se creará un contenedor de blobs para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="b10ef-123">A blob container will be created for each event type:</span></span> 

  ![Imagen del id. de recurso del centro de eventos2](images/storage-account-event-schema.png)

- <span data-ttu-id="b10ef-125">El esquema de cada fila de un blob es el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="b10ef-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="b10ef-126">Cada blob contiene varias filas.</span><span class="sxs-lookup"><span data-stu-id="b10ef-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="b10ef-127">Cada fila contiene el nombre del evento, la hora en que Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "propiedades".</span><span class="sxs-lookup"><span data-stu-id="b10ef-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="b10ef-128">Para obtener más información sobre el esquema de eventos de Microsoft Defender para endpoint, vea [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b10ef-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="b10ef-129">En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b10ef-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="b10ef-130">Aquí todos los eventos también se decorarán con esta columna.</span><span class="sxs-lookup"><span data-stu-id="b10ef-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="b10ef-131">Consulta [Grupos de dispositivos](machine-groups.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b10ef-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="b10ef-132">Asignación de tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="b10ef-132">Data types mapping:</span></span>

<span data-ttu-id="b10ef-133">Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b10ef-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="b10ef-134">Inicie sesión en el [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com) y vaya a la página Búsqueda [avanzada](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="b10ef-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="b10ef-135">Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="b10ef-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="b10ef-136">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="b10ef-136">Here is an example for Device Info event:</span></span> 

  ![Imagen del id. de recurso del centro de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="b10ef-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b10ef-138">Related topics</span></span>
- [<span data-ttu-id="b10ef-139">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="b10ef-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b10ef-140">API de Streaming de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="b10ef-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="b10ef-141">Transmitir eventos de Microsoft Defender para endpoint a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b10ef-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="b10ef-142">Documentación de la cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b10ef-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
