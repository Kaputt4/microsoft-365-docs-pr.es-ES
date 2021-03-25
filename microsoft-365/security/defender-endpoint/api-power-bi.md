---
title: Conexión de las API de ATP de Microsoft Defender a Power BI
ms.reviewer: ''
description: Cree un informe de Power Business Intelligence (BI) sobre las API de Microsoft Defender para endpoints.
keywords: apis, api admitidas, Power BI, informes
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167036"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="420bd-104">Crear informes personalizados con Power BI</span><span class="sxs-lookup"><span data-stu-id="420bd-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="420bd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="420bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="420bd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="420bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="420bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="420bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="420bd-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="420bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="420bd-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="420bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="420bd-110">En esta sección aprenderá a crear un informe de Power BI sobre las API de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="420bd-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="420bd-111">El primer ejemplo muestra cómo conectar Power BI a la API de búsqueda avanzada y el segundo ejemplo muestra una conexión a nuestras API de OData, como acciones de máquina o alertas.</span><span class="sxs-lookup"><span data-stu-id="420bd-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="420bd-112">Conectar Power BI a la API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="420bd-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="420bd-113">Abrir Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="420bd-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="420bd-114">Haga **clic en Obtener consulta en** blanco de  >  **datos**</span><span class="sxs-lookup"><span data-stu-id="420bd-114">Click **Get Data** > **Blank Query**</span></span>

    ![Imagen de crear consulta en blanco](images/power-bi-create-blank-query.png)

- <span data-ttu-id="420bd-116">Haga **clic en Editor avanzado**</span><span class="sxs-lookup"><span data-stu-id="420bd-116">Click **Advanced Editor**</span></span>

    ![Imagen del editor avanzado abierto](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="420bd-118">Copie lo siguiente y péguelo en el editor:</span><span class="sxs-lookup"><span data-stu-id="420bd-118">Copy the below and paste it in the editor:</span></span>

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- <span data-ttu-id="420bd-119">Haga clic **en Listo**</span><span class="sxs-lookup"><span data-stu-id="420bd-119">Click **Done**</span></span>

- <span data-ttu-id="420bd-120">Haga clic **en Editar credenciales**</span><span class="sxs-lookup"><span data-stu-id="420bd-120">Click **Edit Credentials**</span></span>

    ![Imagen de las credenciales de edición0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="420bd-122">Seleccionar **Inicio de sesión de cuenta**  >  **organizativa**</span><span class="sxs-lookup"><span data-stu-id="420bd-122">Select **Organizational account** > **Sign in**</span></span>

    ![Imagen de set credentials1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="420bd-124">Escriba sus credenciales y espere a que se haya iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="420bd-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="420bd-125">Haga clic **en Conectar**</span><span class="sxs-lookup"><span data-stu-id="420bd-125">Click **Connect**</span></span>

    ![Imagen de set credentials2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="420bd-127">Ahora los resultados de la consulta aparecerán como tabla y puedes empezar a crear visualizaciones encima de ella.</span><span class="sxs-lookup"><span data-stu-id="420bd-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="420bd-128">Puedes duplicar esta tabla, cambiar el nombre y editar la consulta de búsqueda avanzada dentro para obtener los datos que quieras.</span><span class="sxs-lookup"><span data-stu-id="420bd-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="420bd-129">Conectar Power BI a las API de OData</span><span class="sxs-lookup"><span data-stu-id="420bd-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="420bd-130">La única diferencia con respecto al ejemplo anterior es la consulta dentro del editor.</span><span class="sxs-lookup"><span data-stu-id="420bd-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="420bd-131">Copie lo siguiente y péguelo en el editor para extraer todas las **acciones de máquina** de su organización:</span><span class="sxs-lookup"><span data-stu-id="420bd-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="420bd-132">Puede hacer lo mismo para **Alerts** and **Machines**.</span><span class="sxs-lookup"><span data-stu-id="420bd-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="420bd-133">También puede usar consultas OData para filtros de consultas, vea [Using OData Queries](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="420bd-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="420bd-134">Ejemplos de panel de Power BI en GitHub</span><span class="sxs-lookup"><span data-stu-id="420bd-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="420bd-135">Para obtener más información, vea las plantillas [de informe de Power BI](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span><span class="sxs-lookup"><span data-stu-id="420bd-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="420bd-136">Informes de ejemplo</span><span class="sxs-lookup"><span data-stu-id="420bd-136">Sample reports</span></span>
<span data-ttu-id="420bd-137">Vea los ejemplos de informes de Power BI de ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="420bd-137">View the Microsoft Defender ATP Power BI report samples.</span></span> <span data-ttu-id="420bd-138">Para obtener más información, vea [Examinar ejemplos de código](https://docs.microsoft.com/samples/browse/?products=mdatp).</span><span class="sxs-lookup"><span data-stu-id="420bd-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="420bd-139">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="420bd-139">Related topic</span></span>
- [<span data-ttu-id="420bd-140">Defender para api de extremo</span><span class="sxs-lookup"><span data-stu-id="420bd-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="420bd-141">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="420bd-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="420bd-142">Uso de consultas de OData</span><span class="sxs-lookup"><span data-stu-id="420bd-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
