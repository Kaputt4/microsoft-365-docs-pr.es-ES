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
ms.openlocfilehash: 099487279482385760e05d9b166ae80c665d931e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054744"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos

Cuando su organización configura una solución de administración de contratos, necesita una ubicación central en la que las partes interesadas puedan revisar y administrar contratos. Para ello, puede usar [Microsoft Teams](/microsoftteams/) para configurar un canal de Teams y usar las características de Teams para:

- **Cree una ubicación para que las partes interesadas puedan ver fácilmente todos los contratos que requieren acción.** Por ejemplo, en Teams puede crear una pestaña Contratos en el canal de administración de **contratos** en la que los miembros pueden ver una vista de icono útil de todos los contratos que necesitan aprobación. También puede configurar la vista para que cada "tarjeta" enumera los datos importantes que le importan (como *El* *cliente,* el contratista y el importe de *la cuota).*

     ![Ficha Contratos.](../media/content-understanding/tile-view.png)

- **Tener una ubicación para que los miembros interactúen entre sí y vean eventos importantes.** Por ejemplo, en Teams, la pestaña **Publicaciones** se puede usar para tener conversaciones, obtener actualizaciones y ver acciones (como un miembro que rechaza un contrato). Cuando ha ocurrido algo (como un nuevo contrato  enviado para su aprobación), la pestaña Publicaciones se puede usar no solo para anunciarlo, sino también para mantener un registro de él. Y si los miembros se suscriben a las notificaciones, se les notificará siempre que haya una actualización.

     ![Pestaña Publicaciones.](../media/content-understanding/posts.png)

- **Tener una ubicación para que los miembros vean los contratos aprobados para saber cuándo se pueden enviar para el pago.** En SharePoint, deberá crear una lista  De pago e incluir columnas para el importe de  **cliente,** contratista y **tarifa,** seleccionando Línea única de texto como tipo de columna. Deberá agregar la pestaña  Para pago como un Teams en el canal administración de [ **contratos,**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab)de forma similar a lo que hará para la pestaña Contratos . La **pestaña Para pago** enumerará todos los contratos que tendrán que enviarse para el pago. Puede extender fácilmente esta solución para escribir esta información directamente en una aplicación financiera de terceros (por ejemplo, Dynamics CRM). 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Adjuntar la SharePoint de documentos a la pestaña Contratos

Después de crear una **pestaña Contratos** en el canal de administración de contratos, debe adjuntar la biblioteca de documentos SharePoint a [él.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) La SharePoint de documentos que desea adjuntar es la a la que aplicó el modelo de SharePoint Syntex de documentos en la sección anterior.

Después de adjuntar la SharePoint de documentos, podrá ver los contratos clasificados a través de una vista de lista predeterminada.

   ![Vista de lista de SharePoint biblioteca.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>Personalizar la vista de icono de pestaña Contratos

> [!NOTE]
> En esta sección se hace referencia a ejemplos de código incluidos en [ el archivoContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) que se incluye en el repositorio de activos de solución de administración de [contratos](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).

Aunque Teams permite ver los contratos en una vista de icono, es posible que desee personalizarlo para ver los datos del contrato que desea hacer visibles en la tarjeta de contrato. Por ejemplo, para la pestaña **Contratos,** es importante que los miembros vean el cliente, el contratista y el importe de la cuota en la tarjeta de contrato. Todos estos campos se extrajeron de cada contrato SharePoint Syntex modelo que se aplicó a la biblioteca de documentos. También desea poder cambiar la barra de encabezado de icono a diferentes colores para cada estado para que los miembros puedan ver fácilmente dónde se encuentra el contrato en el proceso de aprobación. Por ejemplo, todos los contratos aprobados tendrán una barra de encabezado azul.

   ![Vista de icono de SharePoint biblioteca.](../media/content-understanding/tile.png)

La vista de icono personalizada que use requiere que realice cambios en el archivo JSON usado para dar formato a la vista de mosaico actual. Para hacer referencia al archivo JSON usado para crear la vista de tarjeta, consulte el [ContractTileFormatting.jsarchivo on.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) En las secciones siguientes, verá secciones específicas del código para las características que están en las tarjetas de contrato.

Si desea ver o realizar cambios en el código JSON de la vista en el canal de Teams, en el canal Teams, seleccione el menú desplegable ver y, a continuación, seleccione Formato de vista **actual.**

   ![Captura de pantalla del formato json en Teams canal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>Tamaño y forma de la tarjeta

En el [ContractTileFormatting.jsen,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) vea la sección siguiente para ver el código de cómo se da formato al tamaño y la forma de la tarjeta.

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

## <a name="contract-status"></a>Estado del contrato

El siguiente código le permite definir el estado de cada tarjeta de título. Tenga en cuenta que cada valor de estado (*New*, *In review*, *Approved* y *Rejected*) mostrará un código de color diferente para cada uno. En el [ContractTileFormatting.jsen](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) archivo, vea la sección que define el estado.

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

## <a name="extracted-fields"></a>Campos extraídos

Cada tarjeta de contrato mostrará tres campos que se extrajeron para cada contrato (*Client*, *Contractor* y *Fee Amount*). Además, también desea mostrar la hora/fecha en que el archivo se clasificó mediante el SharePoint Syntex usado para identificarlo.

En el [ContractTileFormatting.jsarchivo on,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) las siguientes secciones definen cada una de ellas.

### <a name="client"></a>Cliente

En esta sección se define cómo se mostrará "Cliente" en la tarjeta y se usará el valor para el contrato específico.

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

### <a name="contractor"></a>Contratista

En esta sección se define cómo se mostrará el "contratista" en la tarjeta y se usará el valor para el contrato específico.

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

### <a name="fee-amount"></a>Importe de la cuota

En esta sección se define cómo se mostrará el "Importe de tarifa" en la tarjeta y se usará el valor para el contrato específico.

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

### <a name="classification-date"></a>Fecha de clasificación

En esta sección se define cómo se mostrará "Clasificación" en la tarjeta y se usará el valor para el contrato específico.

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

## <a name="next-step"></a>Paso siguiente

[Paso 3. Usar Power Automate para crear el flujo para procesar los contratos](solution-manage-contracts-step3.md)
