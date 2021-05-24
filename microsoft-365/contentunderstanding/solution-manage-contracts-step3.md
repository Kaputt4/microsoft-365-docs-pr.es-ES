---
title: Paso 3. Usar Power Automate para crear el flujo para procesar los contratos
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
description: Obtenga información sobre cómo usar Power Automate para crear el flujo para procesar los contratos mediante una Microsoft 365 solución.
ms.openlocfilehash: 0ddcbeff6c8bd119850e3e4ea45db2513e774433
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636259"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>Paso 3. Usar Power Automate para crear el flujo para procesar los contratos

Ha creado el canal de administración de contratos y ha adjuntado su SharePoint de documentos. El siguiente paso es crear un flujo Power Automate para procesar los contratos que el SharePoint Syntex identifica y clasifica. Puede realizar este paso creando [un flujo de Power Automate en la SharePoint de documentos](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).

Para la solución de administración de contratos, desea crear un flujo Power Automate para realizar las siguientes acciones:

-  Después de clasificar un contrato por su SharePoint syntex, cambie el estado del contrato a **En revisión**.
- A continuación, se revisa el contrato y se aprueba o se rechaza.
- Para los contratos aprobados, la información del contrato se publica en una pestaña para el procesamiento de pagos.
- En el caso de los contratos rechazados, se notifica al equipo para su análisis posterior. 

En el siguiente diagrama se muestra el Power Automate de la solución de administración de contratos.

![Flow diagrama que muestra toda la solución.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>Preparar el contrato para revisión

Cuando el modelo SharePoint de comprensión de documentos de Syntex identifica y clasifica un contrato, el flujo de Power Automate cambiará primero el estado a **En revisión**.

![Estado de actualización.](../media/content-understanding/flow-overview.png)

Después de desaltear el archivo, cambie el valor de estado a **En revisión**.

![En estado de revisión.](../media/content-understanding/in-review.png)

El siguiente paso es crear una tarjeta adaptable que indique que el contrato está esperando su revisión y publicarla en el canal de administración de contratos.

![Publicación de revisión de contratos.](../media/content-understanding/contract-approval-post.png)


![Cree una tarjeta adaptable para su revisión.](../media/content-understanding/adaptive-card.png)

El siguiente código es el JSON usado para este paso en el flujo Power Automate datos.

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a>Condicional

En su flujo, a continuación, debe crear una condición en la que se aprobará o rechazará el contrato.

![Condicional.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>Si se aprueba el contrato

Cuando se ha aprobado un contrato, se producen los siguientes aspectos:

- En la **pestaña Contratos,** el estado de la tarjeta de contrato cambiará a **Aprobado**.

   ![Estado de la tarjeta aprobado.](../media/content-understanding/approved-contracts-tab.png)

- En el flujo, el estado cambia a **Aprobado**.

   ![Flow estado aprobado.](../media/content-understanding/status-approved.png)

- En esta solución, los datos del contrato se agregarán a la pestaña **Para** pago para que se puedan administrar los pagos. Este proceso se puede extender para permitir que el flujo envíe los contratos para su pago mediante una aplicación financiera de terceros (por ejemplo, Dynamics CRM).

   ![El contrato se movió a Pay Out.](../media/content-understanding/for-payout.png)

- En el flujo, se crea el siguiente elemento para mover los contratos aprobados a la **pestaña Para pago.**

   ![Flow elemento que se moverá a Pay Out.](../media/content-understanding/ready-for-payout.png)

- Se crea una tarjeta adaptable que indica que el contrato se ha aprobado y se publica en el canal de administración de contratos.

   ![Aprobación del contrato publicada.](../media/content-understanding/adaptive-card-approval.png)

   ![Aprobación de tarjeta adaptable.](../media/content-understanding/adaptive-card.png)


   El siguiente código es el JSON usado para este paso en el flujo Power Automate datos.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a>Si se rechaza el contrato

Cuando se rechaza un contrato, se producen lo siguiente:

- En la **pestaña Contratos,** el estado de la tarjeta de contrato cambiará a **Rechazado**.

   ![Se ha rechazado el estado de la tarjeta.](../media/content-understanding/rejected-contracts-tab.png)

- En el flujo, se desvía el archivo de contrato, se cambia el estado a **Rechazado** y, a continuación, se vuelve a comprobar el archivo.

   ![Flow estado rechazado.](../media/content-understanding/reject-flow.png)

- En el flujo, se crea una tarjeta adaptable que indica que se ha rechazado el contrato.

   ![Flow estado rechazado.](../media/content-understanding/reject-flow-item.png)

El siguiente código es el JSON usado para este paso en el flujo Power Automate datos.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- La tarjeta se publica en el canal de administración de contratos.

   ![Flow tarjeta adaptable para rechazar.](../media/content-understanding/rejected.png)