---
title: Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Obtenga información sobre cómo usar Microsoft Teams para crear el canal de administración de contratos mediante una solución Microsoft 365 contrato.
ms.openlocfilehash: 7c7d3ef30d376e14e033243413637cdb51ba548a
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148979"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="fbf7b-104">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-104">Step 2.</span></span> <span data-ttu-id="fbf7b-105">Usar Microsoft Teams para crear el canal de administración de contratos</span><span class="sxs-lookup"><span data-stu-id="fbf7b-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="fbf7b-106">Cuando su organización configura una solución de administración de contratos, necesita una ubicación central en la que las partes interesadas puedan revisar y administrar contratos.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="fbf7b-107">Para ello, puede usar [Microsoft Teams](/microsoftteams/) para configurar un canal de Teams y usar las características de Teams para:</span><span class="sxs-lookup"><span data-stu-id="fbf7b-107">For this purpose, you can use [Microsoft Teams](/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="fbf7b-108">**Cree una ubicación para que las partes interesadas puedan ver fácilmente todos los contratos que requieren acción.**</span><span class="sxs-lookup"><span data-stu-id="fbf7b-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="fbf7b-109">Por ejemplo, en Teams puede crear una pestaña Contratos en el canal de administración de **contratos** en la que los miembros pueden ver una vista de icono útil de todos los contratos que necesitan aprobación.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="fbf7b-110">También puede configurar la vista para que cada "tarjeta" enumera los datos importantes que le importan (como *El* *cliente,* el contratista y el importe de *la cuota).*</span><span class="sxs-lookup"><span data-stu-id="fbf7b-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Ficha Contratos.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="fbf7b-112">**Tener una ubicación para que los miembros interactúen entre sí y vean eventos importantes.**</span><span class="sxs-lookup"><span data-stu-id="fbf7b-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="fbf7b-113">Por ejemplo, en Teams, la pestaña **Publicaciones** se puede usar para tener conversaciones, obtener actualizaciones y ver acciones (como un miembro que rechaza un contrato).</span><span class="sxs-lookup"><span data-stu-id="fbf7b-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="fbf7b-114">Cuando ha ocurrido algo (como un nuevo contrato  enviado para su aprobación), la pestaña Publicaciones se puede usar no solo para anunciarlo, sino también para mantener un registro de él.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="fbf7b-115">Y si los miembros se suscriben a las notificaciones, se les notificará siempre que haya una actualización.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span>

     ![Pestaña Publicaciones.](../media/content-understanding/posts.png)

- <span data-ttu-id="fbf7b-117">**Tener una ubicación para que los miembros vean los contratos aprobados para saber cuándo se pueden enviar para el pago.**</span><span class="sxs-lookup"><span data-stu-id="fbf7b-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="fbf7b-118">En SharePoint, deberá crear una lista  De pago e incluir columnas para el importe de  **cliente,** contratista y **tarifa,** seleccionando Línea única de texto como tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-118">In SharePoint, you'll need to create a **For Payout** list and include columns for **Client**, **Contractor**, and **Fee amount**, selecting **Single line of text** as the column type.</span></span> <span data-ttu-id="fbf7b-119">Deberá agregar la pestaña  Para pago como un Teams en el canal administración de [ **contratos,**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab)de forma similar a lo que hará para la pestaña Contratos . La **pestaña Para pago** enumerará todos los contratos que tendrán que enviarse para el pago.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-119">You'll need to add the **For Payout** list as a Teams tab in the Contract Management channel, similar to [what you'll do for the **Contracts** tab](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab). The **For Payout** tab will list all contracts that will need to be submitted for payment.</span></span> <span data-ttu-id="fbf7b-120">Puede extender fácilmente esta solución para escribir esta información directamente en una aplicación financiera de terceros (por ejemplo, Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="fbf7b-120">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span> 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="fbf7b-121">Adjuntar la SharePoint de documentos a la pestaña Contratos</span><span class="sxs-lookup"><span data-stu-id="fbf7b-121">Attach your SharePoint document library to the Contracts tab</span></span>

<span data-ttu-id="fbf7b-122">Después de crear una **pestaña Contratos** en el canal de administración de contratos, debe adjuntar la biblioteca de documentos SharePoint a [él.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="fbf7b-122">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="fbf7b-123">La SharePoint de documentos que desea adjuntar es la a la que aplicó el modelo de SharePoint Syntex de documentos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-123">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="fbf7b-124">Después de adjuntar la SharePoint de documentos, podrá ver los contratos clasificados a través de una vista de lista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-124">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Vista de lista de SharePoint biblioteca.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="fbf7b-126">Personalizar la vista de icono de pestaña Contratos</span><span class="sxs-lookup"><span data-stu-id="fbf7b-126">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="fbf7b-127">En esta sección se hace referencia a ejemplos de código incluidos en [ el archivoContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) que se incluye en el repositorio de activos de solución de administración de [contratos](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span><span class="sxs-lookup"><span data-stu-id="fbf7b-127">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="fbf7b-128">Aunque Teams permite ver los contratos en una vista de icono, es posible que desee personalizarlo para ver los datos del contrato que desea hacer visibles en la tarjeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-128">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="fbf7b-129">Por ejemplo, para la pestaña **Contratos,** es importante que los miembros vean el cliente, el contratista y el importe de la cuota en la tarjeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-129">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="fbf7b-130">Todos estos campos se extrajeron de cada contrato SharePoint Syntex modelo que se aplicó a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-130">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="fbf7b-131">También desea poder cambiar la barra de encabezado de icono a diferentes colores para cada estado para que los miembros puedan ver fácilmente dónde se encuentra el contrato en el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-131">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="fbf7b-132">Por ejemplo, todos los contratos aprobados tendrán una barra de encabezado azul.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-132">For example, all approved contracts will have a blue header bar.</span></span>

   ![Vista de icono de SharePoint biblioteca.](../media/content-understanding/tile.png)

<span data-ttu-id="fbf7b-134">La vista de icono personalizada que use requiere que realice cambios en el archivo JSON usado para dar formato a la vista de mosaico actual.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-134">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="fbf7b-135">Para hacer referencia al archivo JSON usado para crear la vista de tarjeta, consulte el [ContractTileFormatting.jsarchivo on.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json)</span><span class="sxs-lookup"><span data-stu-id="fbf7b-135">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="fbf7b-136">En las secciones siguientes, verá secciones específicas del código para las características que están en las tarjetas de contrato.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-136">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="fbf7b-137">Si desea ver o realizar cambios en el código JSON de la vista en el canal de Teams, en el canal Teams, seleccione el menú desplegable ver y, a continuación, seleccione Formato de vista **actual.**</span><span class="sxs-lookup"><span data-stu-id="fbf7b-137">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![Captura de pantalla del formato json en Teams canal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a><span data-ttu-id="fbf7b-139">Tamaño y forma de la tarjeta</span><span class="sxs-lookup"><span data-stu-id="fbf7b-139">Card size and shape</span></span>

<span data-ttu-id="fbf7b-140">En el [ContractTileFormatting.jsen,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) vea la sección siguiente para ver el código de cómo se da formato al tamaño y la forma de la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-140">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a><span data-ttu-id="fbf7b-141">Estado del contrato</span><span class="sxs-lookup"><span data-stu-id="fbf7b-141">Contract status</span></span>

<span data-ttu-id="fbf7b-142">El siguiente código le permite definir el estado de cada tarjeta de título.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-142">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="fbf7b-143">Tenga en cuenta que cada valor de estado (*New*, *In review*, *Approved* y *Rejected*) mostrará un código de color diferente para cada uno.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-143">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="fbf7b-144">En el [ContractTileFormatting.jsen](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) archivo, vea la sección que define el estado.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-144">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a><span data-ttu-id="fbf7b-145">Campos extraídos</span><span class="sxs-lookup"><span data-stu-id="fbf7b-145">Extracted fields</span></span>

<span data-ttu-id="fbf7b-146">Cada tarjeta de contrato mostrará tres campos que se extrajeron para cada contrato (*Client*, *Contractor* y *Fee Amount*).</span><span class="sxs-lookup"><span data-stu-id="fbf7b-146">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="fbf7b-147">Además, también desea mostrar la hora/fecha en que el archivo se clasificó mediante el SharePoint Syntex usado para identificarlo.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-147">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span>

<span data-ttu-id="fbf7b-148">En el [ContractTileFormatting.jsarchivo on,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) las siguientes secciones definen cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-148">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="fbf7b-149">Cliente</span><span class="sxs-lookup"><span data-stu-id="fbf7b-149">Client</span></span>

<span data-ttu-id="fbf7b-150">En esta sección se define cómo se mostrará "Cliente" en la tarjeta y se usará el valor para el contrato específico.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-150">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="fbf7b-151">Contratista</span><span class="sxs-lookup"><span data-stu-id="fbf7b-151">Contractor</span></span>

<span data-ttu-id="fbf7b-152">En esta sección se define cómo se mostrará el "contratista" en la tarjeta y se usará el valor para el contrato específico.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-152">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                        {
                            "elmType": "div",
                            "txtContent": "Contractor",
                            "style": {
                              "color": "#767676",
                              "font-size": "12px",
                              "margin-bottom": "2px"
                            }
                          },
                          {
                            "elmType": "div",
                            "style": {
                              "margin-bottom": "12px",
                              "font-size": "14px"
                            },
                            "txtContent": "[$Contractor]"
                          },
```

### <a name="fee-amount"></a><span data-ttu-id="fbf7b-153">Importe de la cuota</span><span class="sxs-lookup"><span data-stu-id="fbf7b-153">Fee amount</span></span>

<span data-ttu-id="fbf7b-154">En esta sección se define cómo se mostrará el "Importe de tarifa" en la tarjeta y se usará el valor para el contrato específico.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-154">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a><span data-ttu-id="fbf7b-155">Fecha de clasificación</span><span class="sxs-lookup"><span data-stu-id="fbf7b-155">Classification date</span></span>

<span data-ttu-id="fbf7b-156">En esta sección se define cómo se mostrará "Clasificación" en la tarjeta y se usará el valor para el contrato específico.</span><span class="sxs-lookup"><span data-stu-id="fbf7b-156">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="fbf7b-157">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fbf7b-157">Next step</span></span>

[<span data-ttu-id="fbf7b-158">Paso 3. Usar Power Automate para crear el flujo para procesar los contratos</span><span class="sxs-lookup"><span data-stu-id="fbf7b-158">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
