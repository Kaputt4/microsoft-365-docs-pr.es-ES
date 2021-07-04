---
title: Transmitir Microsoft 365 Defender eventos a Azure Event Hub
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu centro de eventos.
keywords: Exportación de datos sin procesar, API de streaming, API, Centro de eventos de Azure, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: 2e43b75e49d01a05fdacae0adf63ea3337631dfd
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289252"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a su Centro de eventos de Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

1. Cree un [centro de eventos](/azure/event-hubs/) en el espacio empresarial.

2. Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Ideas**.

3. Cree un espacio de nombres de centro de eventos, vaya a **Event Hub > Agregar** y seleccione el nivel de precios, las unidades de rendimiento y la opción Autoinflate adecuada para la carga esperada. Para obtener más información, vea [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

### <a name="add-contributor-permissions"></a>Agregar permisos de colaborador

Una vez creado el espacio de nombres de Event Hub, tendrá que:

1. Defina el usuario que va a iniciar sesión en Microsoft 365 Defender como colaborador.

2. Si se está conectando a una aplicación, agregue la entidad de seguridad del servicio de registro de aplicaciones como Lector, receptor de datos del centro de eventos de Azure (esto también se puede hacer en el nivel de grupo de recursos o suscripción). 

    Vaya al espacio de nombres Event hubs > Control de **acceso (IAM)** > Agregar y comprobar en **Asignaciones de roles**.

## <a name="enable-raw-data-streaming"></a>Habilitar la transmisión de datos sin procesar

1. Inicie sesión en el [centro Microsoft 365 Defender seguridad](https://security.microsoft.com) como un * Administrador **global** _ o _* Administrador _de seguridad_**.

2. Vaya a la página [Configuración de la API de streaming.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Haga clic en **Agregar**.

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos a Azure Event Hub**.

6. Puede seleccionar si desea exportar los datos del evento a un único centro de eventos o exportar cada tabla de eventos a un centro de eventos diferente en el espacio de nombres del Centro de eventos. 

7. Para exportar los datos del evento a un único centro de eventos, escriba el nombre del centro de eventos **y** el identificador de recurso del centro **de eventos**.

   Para obtener el identificador **de** recurso del Centro de eventos, vaya a la página de espacio de nombres del Centro de eventos de Azure en la pestaña Propiedades de [Azure](https://ms.portal.azure.com/)> copiar el texto en  >   **Id. de recurso:**

   ![Imagen del id. de recurso del centro de eventos1](../defender-endpoint/images/event-hub-resource-id.png)

8. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Esquema de los eventos en Azure Event Hub

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Cada mensaje del Centro de eventos de Azure Event Hub contiene una lista de registros.

- Cada registro contiene el nombre del evento, la hora en que Microsoft 365 Defender recibió el evento, el espacio empresarial al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".

- Para obtener más información sobre el esquema de Microsoft 365 Defender eventos, vea [Advanced Hunting overview](advanced-hunting-overview.md).

- En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna. 

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:

1. Inicie sesión en [el Microsoft 365 seguridad y](https://security.microsoft.com) vaya a la página Búsqueda [avanzada](https://security.microsoft.com/hunting-package).

2. Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Este es un ejemplo para el evento Device Info: 

  ![Imagen del id. de recurso del centro de eventos2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Microsoft 365 Defender API de streaming](streaming-api.md)
- [Transmitir Microsoft 365 Defender eventos a su cuenta de Azure Storage](streaming-api-storage.md)
- [Documentación de Azure Event Hub](/azure/event-hubs/)
- [Solucionar problemas de conectividad: Azure Event Hub](/azure/event-hubs/troubleshooting-guide)
