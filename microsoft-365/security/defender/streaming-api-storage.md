---
title: Transmitir Microsoft 365 Defender eventos a su Almacenamiento cuenta
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu Almacenamiento cuenta.
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029662"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="9abec-104">Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a su Almacenamiento cuenta</span><span class="sxs-lookup"><span data-stu-id="9abec-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9abec-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9abec-105">**Applies to:**</span></span>
- [<span data-ttu-id="9abec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9abec-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="9abec-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="9abec-107">Before you begin</span></span>

1. <span data-ttu-id="9abec-108">Cree una [Almacenamiento en](/azure/storage/common/storage-account-overview) el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="9abec-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="9abec-109">Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Ideas**.</span><span class="sxs-lookup"><span data-stu-id="9abec-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="9abec-110">Habilitar la transmisión de datos sin procesar</span><span class="sxs-lookup"><span data-stu-id="9abec-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="9abec-111">Inicie sesión en el portal de Microsoft 365 Defender ( <https://security.microsoft.com> ) como \* Administrador **global** _ o _\* Administrador _de seguridad_\*\*.</span><span class="sxs-lookup"><span data-stu-id="9abec-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="9abec-112">Vaya a **Configuración** \> **Microsoft 365 Defender** \> **API de streaming**.</span><span class="sxs-lookup"><span data-stu-id="9abec-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="9abec-113">Para ir directamente a la página **de la API de streaming,** use <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="9abec-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="9abec-114">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9abec-114">Click **Add**.</span></span>

4. <span data-ttu-id="9abec-115">En el **menú desplegable Agregar nueva configuración de la API** de streaming que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9abec-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="9abec-116">**Nombre:** elija un nombre para la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9abec-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="9abec-117">Seleccione **Reenviar eventos para Almacenamiento de Azure**.</span><span class="sxs-lookup"><span data-stu-id="9abec-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="9abec-118">En el **Almacenamiento id. de** recurso de cuenta que aparece, escriba el **Almacenamiento de recurso de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="9abec-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="9abec-119">Para obtener el identificador **de recurso** Almacenamiento cuenta, abra Azure Portal en , haga clic en Almacenamiento cuentas vaya a la pestaña propiedades copie el texto en <https://portal.azure.com> Almacenamiento  \> \> **Id.** de recurso de cuenta .</span><span class="sxs-lookup"><span data-stu-id="9abec-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Imagen del id. de recurso del centro de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="9abec-121">En el menú desplegable Agregar nueva configuración de la API de **streaming,** elija los tipos de **eventos** que desea transmitir.</span><span class="sxs-lookup"><span data-stu-id="9abec-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="9abec-122">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9abec-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="9abec-123">El esquema de los eventos de la cuenta Almacenamiento cuenta</span><span class="sxs-lookup"><span data-stu-id="9abec-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="9abec-124">Se creará un contenedor de blobs para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="9abec-124">A blob container will be created for each event type:</span></span>

  ![Imagen del id. de recurso del centro de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="9abec-126">El esquema de cada fila de un blob es el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="9abec-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="9abec-127">Cada blob contiene varias filas.</span><span class="sxs-lookup"><span data-stu-id="9abec-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="9abec-128">Cada fila contiene el nombre del evento, la hora en que Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "propiedades".</span><span class="sxs-lookup"><span data-stu-id="9abec-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="9abec-129">Para obtener más información sobre el esquema de Microsoft 365 Defender eventos, vea [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9abec-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="9abec-130">Asignación de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9abec-130">Data types mapping</span></span>

<span data-ttu-id="9abec-131">Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9abec-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="9abec-132">Inicie sesión en el portal de Microsoft 365 Defender ( <https://security.microsoft.com> ) y vaya a **Búsqueda** avanzada \> **de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="9abec-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="9abec-133">Para ir directamente a la **página Búsqueda avanzada,** use <security.microsoft.com/advanced-hunting>.</span><span class="sxs-lookup"><span data-stu-id="9abec-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="9abec-134">En la **pestaña Consulta,** ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:</span><span class="sxs-lookup"><span data-stu-id="9abec-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="9abec-135">Este es un ejemplo para el evento Device Info:</span><span class="sxs-lookup"><span data-stu-id="9abec-135">Here is an example for Device Info event:</span></span>

  ![Imagen del id. de recurso del centro de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="9abec-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9abec-137">Related topics</span></span>

- [<span data-ttu-id="9abec-138">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9abec-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="9abec-139">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="9abec-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="9abec-140">Transmitir Microsoft 365 Defender eventos a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="9abec-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="9abec-141">Almacenamiento de Azure Documentación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9abec-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
