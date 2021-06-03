---
title: Transmitir eventos Microsoft 365 Defender a su Storage cuenta
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu cuenta Storage usuario.
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
ms.openlocfilehash: 1a1d6b63bcdf21535f36b23d4a30e5ea01833c36
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729997"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="c01dc-104">Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu cuenta Storage usuario</span><span class="sxs-lookup"><span data-stu-id="c01dc-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c01dc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c01dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="c01dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c01dc-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="c01dc-107">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="c01dc-107">Before you begin:</span></span>

1. <span data-ttu-id="c01dc-108">Cree una [cuenta Storage en](/azure/storage/common/storage-account-overview) el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c01dc-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="c01dc-109">Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="c01dc-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="c01dc-110">Habilitar la transmisión de datos sin procesar:</span><span class="sxs-lookup"><span data-stu-id="c01dc-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="c01dc-111">Inicie sesión en [Microsoft 365 de](https://security.microsoft.com) seguridad de Defender como administrador **global** _ o _\* Administrador _de seguridad_\*\*.</span><span class="sxs-lookup"><span data-stu-id="c01dc-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="c01dc-112">Vaya a [La página Configuración de exportación de](https://security.microsoft.com/settings/mtp_settings/raw_data_export) datos en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c01dc-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="c01dc-113">Haga clic en **Agregar configuración de exportación de datos.**</span><span class="sxs-lookup"><span data-stu-id="c01dc-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="c01dc-114">Elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="c01dc-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="c01dc-115">Elija **Reenviar eventos para Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="c01dc-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="c01dc-116">Escriba su **Storage de recurso de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="c01dc-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="c01dc-117">Para obtener el identificador de recurso de cuenta **de Storage,** vaya a la página de la cuenta de Storage en la pestaña propiedades de [Azure Portal](https://ms.portal.azure.com/) > y > copie el texto en Storage **Id.** de recurso de cuenta:</span><span class="sxs-lookup"><span data-stu-id="c01dc-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Imagen del id. de recurso del centro de eventos1](images/storage-account-resource-id.png)

7. <span data-ttu-id="c01dc-119">Elija los eventos que desea transmitir y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c01dc-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="c01dc-120">El esquema de los eventos de la Storage cuenta:</span><span class="sxs-lookup"><span data-stu-id="c01dc-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="c01dc-121">Se creará un contenedor de blobs para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="c01dc-121">A blob container will be created for each event type:</span></span> 

  ![Imagen del id. de recurso del centro de eventos2](images/storage-account-event-schema.png)

- <span data-ttu-id="c01dc-123">El esquema de cada fila de un blob es el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="c01dc-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="c01dc-124">Cada blob contiene varias filas.</span><span class="sxs-lookup"><span data-stu-id="c01dc-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="c01dc-125">Cada fila contiene el nombre del evento, la hora en que Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "propiedades".</span><span class="sxs-lookup"><span data-stu-id="c01dc-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="c01dc-126">Para obtener más información sobre el esquema de Microsoft 365 Defender, vea [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c01dc-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="c01dc-127">Asignación de tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="c01dc-127">Data types mapping:</span></span>

<span data-ttu-id="c01dc-128">Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c01dc-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="c01dc-129">Inicie sesión en [el Microsoft 365 seguridad y](https://security.microsoft.com) vaya a la página Búsqueda [avanzada](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="c01dc-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="c01dc-130">Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="c01dc-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="c01dc-131">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="c01dc-131">Here is an example for Device Info event:</span></span> 

  ![Imagen del id. de recurso del centro de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="c01dc-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c01dc-133">Related topics</span></span>
- [<span data-ttu-id="c01dc-134">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c01dc-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="c01dc-135">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="c01dc-135">Microsoft 365 Defender Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="c01dc-136">Transmitir eventos Microsoft 365 Defender a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c01dc-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="c01dc-137">Azure Storage Documentación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c01dc-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
