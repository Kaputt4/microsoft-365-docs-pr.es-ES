---
title: Uso del registro de administración para conectores de datos para ver el estado de la importación de datos
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo acceder y ver los registros de administración de los conectores de datos para obtener información de estado de los datos importados por el conector.
ms.openlocfilehash: 6caaebab80878f5a209ddeb57f59527f45ef0f93
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67826783"
---
# <a name="view-admin-logs-for-data-connectors"></a>Visualización de registros de administración de conectores de datos

Después de crear un conector de datos para importar datos que no son de Microsoft a Microsoft Purview, puede supervisar el estado de importación diario del conector descargando los registros de administración del conector de datos.

> [!IMPORTANT]
> El registro de auditoría debe estar habilitado para que su organización vea el registro de administración. Está habilitado de forma predeterminada para Las organizaciones de Microsoft 365 y Office 365, pero se recomienda comprobar el estado de auditoría de la organización. Para obtener instrucciones para comprobar el estado de la auditoría, haga clic aquí. Para obtener instrucciones para activar la auditoría manualmente, haga clic aquí. Una vez activada la auditoría, los eventos de importación pueden tardar hasta 48 horas en registrarse. Se recomienda encarecidamente habilitar la auditoría antes de configurar un conector. Una vez configurado un conector, podría tardar hasta 72 horas en generar registros que contengan el resumen del estado de importación.

## <a name="before-you-view-admin-logs"></a>Antes de ver los registros de administrador

- La auditoría debe estar habilitada para que su organización genere y vea el registro de administrador de la organización. La auditoría está habilitada de forma predeterminada en Microsoft Purview. Sin embargo, se recomienda comprobar el estado de auditoría de la organización. Para obtener instrucciones, consulte [Comprobación del estado de auditoría de su organización](turn-audit-log-search-on-or-off.md#verify-the-auditing-status-for-your-organization). Si necesita habilitar la auditoría para su organización, consulte [Activación de la auditoría](turn-audit-log-search-on-or-off.md#turn-on-auditing).

- Una vez activada la auditoría, podría tardar hasta 48 horas en generar registros de administrador para los conectores de datos. Se recomienda habilitar la auditoría antes de crear conectores de datos.

- Una vez creado un conector de datos, puede tardar hasta 72 horas en generar registros de administración que contengan el resumen de estado de importación.

- Administración registros están disponibles durante los siete días anteriores.

## <a name="download-admin-logs-for-data-connectors"></a>Descarga de registros de administración para conectores de datos

1. Vaya a y, a <https://compliance.microsoft.com/> continuación, haga clic en **Conectores de datos**.

2. Haga clic en la pestaña **Mis conectores** y, a continuación, seleccione un conector de datos para mostrar la página flotante, que contiene información y propiedades sobre el conector de datos.

3. En **Administración registros**, haga clic en el vínculo **Descargar registro** para abrir un registro de administrador.

   ![Los registros de administradores se muestran en la página de control flotante del conector de datos.](..\media\Data-connector-admin-logs1.png)

4. Vea la siguiente información de estado de importación en el registro de administración:

    - Hora de finalización de la **importación**: marca de tiempo (en UTC) cuando el conector completa la importación desde el origen de datos y todos los eventos siguientes se calculan o actualizan con la importación.
    - **Elementos disponibles desde el origen**: recuento de elementos descargados por Connector desde el origen de datos.
    - **Elementos disponibles para la importación**: recuento de elementos que estaban disponibles para la importación por parte del conector después del fanout. Fanout representa el acto de escribir un mensaje a todos los participantes asociados (remitente, receptor, etc.).
    - **Elementos importados correctamente**: recuento de elementos importados correctamente por El conector en buzones de usuario después del fanout.
    - **Elementos importados parcialmente**: recuento de elementos importados correctamente por El conector en buzones de usuario después del fanout, pero que tenían datos adjuntos eliminados.
    - **Elementos omitidos**: recuento de elementos que se omitieron de la importación en buzones de usuario después del fanout debido a que son elementos duplicados.
    - **Error en los elementos**: recuento de elementos que no se pudieron importar en buzones de usuario después del fanout debido a errores (como la asignación de usuarios, el tamaño del elemento superado, etc.). El evento se registra una vez por usuario para los errores de asignación de usuarios.

    > [!NOTE]
    > Los elementos disponibles para la importación deben ser una suma de elementos importados correctamente, parcialmente importados, omitidos y con errores.

    - Resumen de los detalles del elemento con errores:
      - **Id. de elemento** : identificador único del elemento
      - **Id. de usuario de origen** : id. de usuario en la aplicación de origen
      - **Id. de usuario de M365** : nombre principal de usuario en M365
      - **Motivo del error** : indica el motivo por el que el conector no pudo importar el elemento.

      Si no hay elementos ingeridos en un día determinado, el mensaje siguiente estará presente en el archivo de registro:

      No se ingieren elementos en la fecha en *mm/dd/aaaa*.

> [!NOTE]
> Si no se importa ningún elemento en un día determinado, el registro de administración contiene el siguiente mensaje: `No items ingested on mm/dd/yyyy.`
