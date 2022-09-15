---
title: conexión de api de Microsoft Defender para punto de conexión a Power BI
ms.reviewer: ''
description: Cree un informe de Power Business Intelligence (BI) sobre las API de Microsoft Defender para punto de conexión.
keywords: apis, api admitidas, Power BI, informes
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: ca156b12909b3bce27375f35a5fbfab16e6ca579
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701552"
---
# <a name="create-custom-reports-using-power-bi"></a>Creación de informes personalizados mediante Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta sección aprenderá a crear un informe de Power BI sobre las API de Defender para punto de conexión.

En el primer ejemplo se muestra cómo conectar Power BI a Advanced Hunting API y en el segundo ejemplo se muestra una conexión a nuestras API de OData, como Acciones de máquina o Alertas.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Conexión de Power BI a Advanced Hunting API

1. Abra Microsoft Power BI.

2. Seleccione Obtener **consulta en blanco** **de datos**\>.
   :::image type="content" source="images/power-bi-create-blank-query.png" alt-text="La opción Consulta en blanco en el elemento de menú Obtener datos" lightbox="images/power-bi-create-blank-query.png":::

3. Seleccione **Editor avanzado**.
   :::image type="content" source="images/power-bi-open-advanced-editor.png" alt-text="Elemento de menú Editor avanzado" lightbox="images/power-bi-open-advanced-editor.png":::

4. Copie lo siguiente y péguelo en el editor:

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

5. Seleccione **Listo**.

6. Seleccione **Editar credenciales**.
   :::image type="content" source="images/power-bi-edit-credentials.png" alt-text="Elemento de menú Editar credenciales" lightbox="images/power-bi-edit-credentials.png":::

7. Seleccione **Cuenta organizativa** \> **Iniciar sesión**.
   :::image type="content" source="images/power-bi-set-credentials-organizational.png" alt-text="La opción Iniciar sesión en el elemento de menú Cuenta organizativa" lightbox="images/power-bi-set-credentials-organizational.png":::

8. Escriba sus credenciales y espere a iniciar sesión.

9. Seleccione **Conectar**. </br>
   :::image type="content" source="images/power-bi-set-credentials-organizational-cont.png" alt-text="Mensaje de confirmación de inicio de sesión en el elemento de menú Cuenta organizativa" lightbox="images/power-bi-set-credentials-organizational-cont.png":::

Ahora los resultados de la consulta aparecerán como una tabla y puede empezar a crear visualizaciones encima de ella.

Puede duplicar esta tabla, cambiarle el nombre y editar la consulta búsqueda avanzada dentro para obtener los datos que desee.

## <a name="connect-power-bi-to-odata-apis"></a>Conexión de Power BI a las API de OData

La única diferencia con respecto al ejemplo anterior es la consulta dentro del editor. Siga los pasos del 1 al 3 anterior. 

En el paso 4, en lugar del código de ese ejemplo, copie el código siguiente y péguelo en el editor para extraer todas las **acciones de máquina** de su organización:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

Puede hacer lo mismo para **alertas** y **máquinas**.
También puede usar consultas OData para filtros de consultas, consulte [Uso de consultas de OData](exposed-apis-odata-samples.md).

## <a name="power-bi-dashboard-samples-in-github"></a>Ejemplos de panel de Power BI en GitHub

Para obtener más información, consulte las [plantillas de informe de Power BI](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).

## <a name="sample-reports"></a>Informes de ejemplo

Vea los ejemplos de informes de Microsoft Defender para punto de conexión Power BI. Para obtener más información, vea [Examinar ejemplos de código](/samples/browse/?products=mdatp).

## <a name="related-topics"></a>Temas relacionados

- [API de Defender para punto de conexión](apis-intro.md) 
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md) 
- [Uso de consultas OData](exposed-apis-odata-samples.md)
