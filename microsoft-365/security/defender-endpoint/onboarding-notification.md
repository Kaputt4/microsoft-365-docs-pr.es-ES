---
title: Crear una regla de notificación de incorporación o retirada
description: Obtener una notificación cuando se usa un script local de incorporación o offboarding.
keywords: incorporación, offboarding, local, script, notificación, regla
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 0208e21394e350c2b5ffffdca6f8e14ebba227c8
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476057"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Crear una regla de notificación cuando se usa un script local de incorporación o offboarding

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Cree una regla de notificación para que cuando se utilice un script local de incorporación o offboarding, se le notificará.

## <a name="before-you-begin"></a>Antes de empezar

Tendrás que tener acceso a:

- Power Automate (plan por usuario como mínimo). Para obtener más información, [vea Power Automate de precios](https://flow.microsoft.com/pricing/).
- Azure Table o SharePoint List or Library /SQL DB.

## <a name="create-the-notification-flow"></a>Crear el flujo de notificaciones

1. En [flow.microsoft.com](https://flow.microsoft.com/).

2. Vaya a **Mis flujos > Nuevo > Programado: desde en blanco**.

   :::image type="content" source="images/new-flow.png" alt-text="El flujo" lightbox="images/new-flow.png":::


3. Cree un flujo programado.
   1. Escriba un nombre de flujo.
   2. Especifique el inicio y la hora.
   3. Especifique la frecuencia. Por ejemplo, cada 5 minutos.

   :::image type="content" source="images/build-flow.png" alt-text="Flujo de notificaciones" lightbox="images/build-flow.png":::

4. Seleccione el botón + para agregar una nueva acción. La nueva acción será una solicitud HTTP a la API del Centro de seguridad de Defender para puntos de conexión. También puede reemplazarlo por el "Conector WDATP" (acción: "Máquinas- Obtener lista de máquinas").

   :::image type="content" source="images/recurrence-add.png" alt-text="La periodicidad y la acción agregar" lightbox="images/recurrence-add.png":::

5. Escriba los siguientes campos HTTP:

   - Método: "GET" como valor para obtener la lista de dispositivos.
   - URI: escriba `https://api.securitycenter.microsoft.com/api/machines`.
   - Autenticación: seleccione "OAuth de Active Directory".
   - Inquilino: inicie sesión y https://portal.azure.com vaya a **Azure Active Directory > registros de aplicaciones** y obtenga el valor de Identificador de inquilino.
   - Audiencia: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - Id. de cliente: inicie sesión y https://portal.azure.com vaya **a Azure Active Directory > registros de aplicaciones** y obtenga el valor id. de cliente.
   - Tipo de credencial: seleccione "Secreto".
   - Secreto: inicie sesión y https://portal.azure.com vaya a **Azure Active Directory > registros de aplicaciones** y obtenga el valor de Identificador de inquilino.

    :::image type="content" source="images/http-conditions.png" alt-text="Las condiciones HTTP" lightbox="images/http-conditions.png":::

6. Agrega un paso nuevo seleccionando Agregar **nueva** acción, luego busca **Operaciones de datos** y selecciona **Analizar JSON**.

   :::image type="content" source="images/data-operations.png" alt-text="Entrada de operaciones de datos" lightbox="images/data-operations.png":::

7. Agregue Body en el **campo Contenido** .

   :::image type="content" source="images/parse-json.png" alt-text="Sección JSON de análisis" lightbox="images/parse-json.png":::

8. Seleccione el **vínculo Usar carga de ejemplo para generar el** esquema.

   :::image type="content" source="images/parse-json-schema.png" alt-text="Json de análisis con carga" lightbox="images/parse-json-schema.png":::

9. Copie y pegue el siguiente fragmento de código JSON:

    ```json
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10. Extraiga los valores de la llamada JSON y compruebe si los dispositivos incorporados ya están registrados en la lista SharePoint como ejemplo:

    - Si es así, no se activará ninguna notificación
    - Si no, registrará los nuevos dispositivos incorporados en la lista de SharePoint y se enviará una notificación al administrador de Defender for Endpoint

    :::image type="content" source="images/flow-apply.png" alt-text="La aplicación del flujo a cada elemento" lightbox="images/flow-apply.png":::

    :::image type="content" source="images/apply-to-each.png" alt-text="La aplicación del flujo al elemento Get items" lightbox="images/apply-to-each.png":::

11. En **Condición**, agregue la siguiente expresión: "length(body('Get_items')?[' value'])" y establece la condición en igual a 0.

    :::image type="content" source="images/apply-to-each-value.png" alt-text="La aplicación del flujo a cada condición" lightbox="images/apply-to-each-value.png":::
    :::image type="content" source="images/conditions-2.png" alt-text="La condición-1" lightbox="images/conditions-2.png":::
    :::image type="content" source="images/condition3.png" alt-text="La condición-2" lightbox="images/condition3.png":::
    :::image type="content" source="images/send-email.png" alt-text="Sección Enviar un correo electrónico" lightbox="images/send-email.png":::

## <a name="alert-notification"></a>Notificación de alerta

La siguiente imagen es un ejemplo de una notificación por correo electrónico.

:::image type="content" source="images/alert-notification.png" alt-text="Pantalla de notificación de correo electrónico" lightbox="images/alert-notification.png":::

## <a name="tips"></a>Sugerencias

- Puede filtrar aquí solo con lastSeen:
  - Cada 60 minutos:
    - Toma todos los dispositivos vistos por última vez en los últimos 7 días.

- Para cada dispositivo:
  - Si la propiedad vista por última vez se encuentra en el intervalo de una hora de [-7 días, -7 días + 60 minutos ] -> alerta para la posibilidad de fuera deborde.
  - Si se ve por primera vez en la última hora, > alerta para la incorporación.

En esta solución no tendrá alertas duplicadas: hay inquilinos que tienen numerosos dispositivos. Obtener todos esos dispositivos puede ser muy caro y puede requerir paginación.

Puede dividirlo en dos consultas:

1. Para la offboarding, tome solo este intervalo mediante el $filter OData y notifique únicamente si se cumplen las condiciones.
2. Tome todos los dispositivos vistos por última vez en la última hora y compruebe la propiedad vista por primera vez para ellos (si la primera propiedad vista está en la última hora, la última vista también debe estar allí).
