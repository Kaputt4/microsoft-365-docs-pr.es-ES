---
title: Paso 2. Uso de Microsoft Teams para crear el canal de administración de contratos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: Obtenga información sobre cómo usar Microsoft Teams para crear el canal de administración de contratos mediante una solución de Microsoft 365.
ms.openlocfilehash: 6020b6e57af285e96c7998454dc46e5eb19bc5f9
ms.sourcegitcommit: 344a254ca268a2f65cf199d9158a47e08861ffa5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65368053"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Paso 2. Uso de Microsoft Teams para crear el canal de administración de contratos

Cuando su organización configura una solución de administración de contratos, necesita una ubicación central en la que las partes interesadas puedan revisar y administrar los contratos. Para ello, puede usar [Microsoft Teams](/microsoftteams/) para configurar un canal de Teams y usar las características de Teams para:

- **Cree una ubicación para que las partes interesadas vean fácilmente todos los contratos que requieren acción.** Por ejemplo, en Teams puede crear una pestaña **Contratos** en el canal Administración de contratos en la que los miembros pueden ver una vista de icono útil de todos los contratos que necesitan aprobación. También puede configurar la vista para que cada "tarjeta" muestre los datos importantes que le importan (como *cliente*, *contratista* y *importe de cuota*).

     ![Pestaña Contratos.](../media/content-understanding/tile-view.png)

- **Tener una ubicación para que los miembros interactúen entre sí y vean eventos importantes.** Por ejemplo, en Teams, la pestaña **Publicaciones** se puede usar para tener conversaciones, obtener actualizaciones y ver acciones (como un miembro que rechaza un contrato). Cuando ha ocurrido algo (como un nuevo contrato enviado para su aprobación), la pestaña **Publicaciones** se puede usar no solo para anunciarlo, sino también para mantener un registro del mismo. Y si los miembros se suscriben a las notificaciones, se les notificará cada vez que haya una actualización.

     ![Pestaña Publicaciones.](../media/content-understanding/posts.png)

- **Tener una ubicación para que los miembros vean los contratos aprobados para saber cuándo se pueden enviar para el pago.** En SharePoint, deberá crear una lista **De pago** e incluir columnas para **el cliente**, **el contratista** y **el importe de la tarifa**, seleccionando **Línea única de texto** como tipo de columna. Tendrá que agregar la lista **Para pago** como una pestaña de Teams en el canal Administración de contratos, de forma similar a [lo que hará para la pestaña **Contratos**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab). La pestaña **Para pago** enumerará todos los contratos que deberán enviarse para el pago. Puede ampliar fácilmente esta solución para escribir esta información directamente en una aplicación financiera de terceros (por ejemplo, Dynamics CRM). 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Adjuntar la biblioteca de documentos de SharePoint a la pestaña Contratos

Después de crear una pestaña **Contratos** en el canal De administración de contratos, debe [adjuntar su biblioteca de documentos de SharePoint a ella](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b). La biblioteca de documentos SharePoint que desea adjuntar es la que aplicó el modelo de comprensión de documentos SharePoint Syntex en la sección anterior.

Después de adjuntar la biblioteca de documentos SharePoint, podrá ver los contratos clasificados a través de una vista de lista predeterminada.

   ![Vista de lista de SharePoint biblioteca.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>Personalizar la vista de icono de la pestaña Contratos

> [!NOTE]
> Esta sección hace referencia a ejemplos de código incluidos en el archivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20samples/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) que se incluye en el [repositorio Recursos de solución de administración de contratos](https://github.com/pnp/syntex-samples/tree/main/scenario%20samples/Contracts%20Management).

Aunque Teams permite ver los contratos en una vista de icono, es posible que quiera personalizarlos para ver los datos de contrato que desea que sean visibles en la tarjeta de contrato. Por ejemplo, en la pestaña **Contratos** , es importante que los miembros vean el cliente, el contratista y el importe de la tarifa en la tarjeta del contrato. Todos estos campos se extrajeron de cada contrato a través del modelo de SharePoint Syntex que se aplicó a la biblioteca de documentos. También quiere poder cambiar la barra de encabezado del icono a colores diferentes para cada estado para que los miembros puedan ver fácilmente dónde está el contrato en el proceso de aprobación. Por ejemplo, todos los contratos aprobados tendrán una barra de encabezado azul.

   ![Vista de mosaico de SharePoint biblioteca.](../media/content-understanding/tile.png)

La vista de icono personalizada que use requiere que realice cambios en el archivo JSON que se usa para dar formato a la vista de icono actual. Puede hacer referencia al archivo JSON usado para crear la vista de tarjeta examinando el archivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20samples/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) . En las secciones siguientes, verá secciones específicas del código para las características que se encuentran en las tarjetas de contrato.

Si desea ver o realizar cambios en el código JSON de la vista en el canal de Teams, en el canal Teams, seleccione el menú desplegable vista y, a continuación, seleccione **Dar formato a la vista actual**.

   ![Captura de pantalla del formato json en Teams canal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>Tamaño y forma de la tarjeta

En el archivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20samples/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) , examine la sección siguiente para ver el código de cómo se da formato al tamaño y la forma de la tarjeta.

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

El código siguiente le permite definir el estado de cada tarjeta de título. Tenga en cuenta que cada valor de estado (*Nuevo*, *En revisión*, *Aprobado* y *Rechazado*) mostrará un código de color diferente para cada uno. En el archivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20samples/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) , examine la sección que define el estado.

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

Cada tarjeta de contrato mostrará tres campos que se extrajeron para cada contrato (*Cliente*, *Contratista* y *Importe de cuota*). Además, también desea mostrar la hora y la fecha en que el modelo de SharePoint Syntex ha clasificado el archivo para identificarlo.

En el archivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20samples/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) , las secciones siguientes definen cada una de ellas.

### <a name="client"></a>Cliente

En esta sección se define cómo se mostrará "Client" en la tarjeta y se usa el valor para el contrato específico.

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

En esta sección se define cómo se mostrará el "Contratista" en la tarjeta y se usa el valor para el contrato específico.

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

### <a name="fee-amount"></a>Importe de la cuota

En esta sección se define cómo se mostrará el "Importe de cuota" en la tarjeta y se usa el valor para el contrato específico.

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

En esta sección se define cómo se mostrará "Clasificación" en la tarjeta y se usa el valor para el contrato específico.

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
