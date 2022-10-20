---
title: Crear una regla de notificación de incorporación o retirada
description: Obtenga una notificación cuando se use un script de incorporación o eliminación local.
keywords: onboarding, offboarding, local, script, notification, rule
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 1ff70c961a8598465634525928b994e2e310c0ea
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626081"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Creación de una regla de notificación cuando se usa un script de incorporación o eliminación local

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Cree una regla de notificación para que cuando se use un script local de incorporación o eliminación, se le notifique.

## <a name="before-you-begin"></a>Antes de empezar

Tendrá que tener acceso a:

- Power Automate (plan por usuario como mínimo). Para obtener más información, consulte la [página de precios de Power Automate](https://flow.microsoft.com/pricing/).
- Tabla de Azure o lista de SharePoint o biblioteca/BASE de datos SQL.

## <a name="create-the-notification-flow"></a>Creación del flujo de notificación

1. En [flow.microsoft.com](https://flow.microsoft.com/).

2. Vaya a **Mis flujos > Nuevo > Programado: desde cero**.

   :::image type="content" source="images/new-flow.png" alt-text="El flujo" lightbox="images/new-flow.png":::


3. Cree un flujo programado.
   1. Escriba un nombre de flujo.
   2. Especifique el inicio y la hora.
   3. Especifique la frecuencia. Por ejemplo, cada 5 minutos.

   :::image type="content" source="images/build-flow.png" alt-text="Flujo de notificación" lightbox="images/build-flow.png":::

4. Seleccione el botón + para agregar una nueva acción. La nueva acción será una solicitud HTTP a la API del centro de seguridad de Defender para punto de conexión. También puede reemplazarlo por el "Conector WDATP" (acción: "Máquinas : Obtener lista de máquinas").

   :::image type="content" source="images/recurrence-add.png" alt-text="La acción de periodicidad y adición" lightbox="images/recurrence-add.png":::

5. Escriba los siguientes campos HTTP:

   - Método: "GET" como valor para obtener la lista de dispositivos.
   - URI: escriba `https://api.securitycenter.microsoft.com/api/machines`.
   - Autenticación: seleccione "OAuth de Active Directory".
   - Inquilino: inicie sesión y vaya a https://portal.azure.com **Azure Active Directory > Registros de aplicaciones** y obtenga el valor de Identificador de inquilino.
   - Audiencia: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - Id. de cliente: inicie sesión en https://portal.azure.com **Azure Active Directory > registros de aplicaciones** y obtenga el valor de Id. de cliente.
   - Tipo de credencial: seleccione "Secreto".
   - Secreto: inicie sesión y vaya a https://portal.azure.com **Azure Active Directory > Registros de aplicaciones** y obtenga el valor de Identificador de inquilino.

    :::image type="content" source="images/http-conditions.png" alt-text="Condiciones HTTP" lightbox="images/http-conditions.png":::

6. Para agregar un nuevo paso, seleccione **Agregar nueva acción** , busque **Operaciones de datos** y seleccione **Analizar JSON**.

   :::image type="content" source="images/data-operations.png" alt-text="Entrada de operaciones de datos" lightbox="images/data-operations.png":::

7. Agregue Cuerpo en el campo **Contenido** .

   :::image type="content" source="images/parse-json.png" alt-text="La sección analizar JSON" lightbox="images/parse-json.png":::

8. Seleccione el vínculo **Usar carga de ejemplo para generar esquema** .

   :::image type="content" source="images/parse-json-schema.png" alt-text="El archivo JSON de análisis con carga" lightbox="images/parse-json-schema.png":::

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

10. Extraiga los valores de la llamada JSON y compruebe si los dispositivos incorporados ya están registrados en la lista de SharePoint como ejemplo:

    - Si es así, no se desencadenará ninguna notificación.
    - Si no es así, registrará los nuevos dispositivos incorporados en la lista de SharePoint y se enviará una notificación al administrador de Defender para punto de conexión.

    :::image type="content" source="images/flow-apply.png" alt-text="Aplicación del flujo a cada elemento" lightbox="images/flow-apply.png":::

    :::image type="content" source="images/apply-to-each.png" alt-text="Aplicación del flujo al elemento Get items" lightbox="images/apply-to-each.png":::

11. En **Condición**, agregue la siguiente expresión: "length(body('Get_items')?[' value'])" y establezca la condición en igual a 0.

    :::image type="content" source="images/apply-to-each-value.png" alt-text="Aplicación del flujo a cada condición" lightbox="images/apply-to-each-value.png":::
    :::image type="content" source="images/conditions-2.png" alt-text="La condición 1" lightbox="images/conditions-2.png":::
    :::image type="content" source="images/condition3.png" alt-text="La condición 2" lightbox="images/condition3.png":::
    :::image type="content" source="images/send-email.png" alt-text="La sección Enviar un correo electrónico" lightbox="images/send-email.png":::

## <a name="alert-notification"></a>Notificación de alerta

La siguiente imagen es un ejemplo de una notificación por correo electrónico.

:::image type="content" source="images/alert-notification.png" alt-text="Pantalla de notificación por correo electrónico" lightbox="images/alert-notification.png":::

## <a name="tips"></a>Sugerencias

- Puede filtrar aquí solo con lastSeen:
  - Cada 60 minutos:
    - Tome todos los dispositivos que se han visto por última vez en los últimos 7 días.

- Para cada dispositivo:
  - Si la propiedad vista por última vez está en el intervalo de una hora de [-7 días, -7 días + 60 minutos ] -> Alerta de posibilidad de retirada.
  - Si se ve por primera vez en la última hora, > alerta para la incorporación.

En esta solución no tendrá alertas duplicadas: hay inquilinos que tienen numerosos dispositivos. La obtención de todos esos dispositivos podría ser muy costosa y podría requerir paginación.

Puede dividirlo en dos consultas:

1. Para la eliminación, tome solo este intervalo mediante el $filter OData y solo notifique si se cumplen las condiciones.
2. Tome todos los dispositivos vistos por última vez en la última hora y compruebe la primera propiedad vista para ellos (si la primera propiedad vista es en la última hora, la última vista debe estar allí también).
