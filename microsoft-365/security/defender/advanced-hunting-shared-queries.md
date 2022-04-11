---
title: Uso de consultas compartidas en Microsoft 365 Defender búsqueda avanzada
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2e86d733304eeaa0e5e16f3ce1bfde87c21258d4
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761636"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Utilice las consultas compartidas en la búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización. También puede guardar consultas que solo sean accesibles para usted. También puede encontrar consultas de la comunidad que se comparten públicamente en GitHub. Estas consultas guardadas permiten buscar rápidamente escenarios específicos de búsqueda de amenazas sin tener que escribir consultas desde cero.

En la pestaña Consultas de la búsqueda avanzada, puede encontrar los menús desplegables para **consultas compartidas**, **Mis consultas** y **Community consultas**. Puede seleccionar una flecha hacia abajo para expandir un menú.


:::image type="content" source="../../media/advanced-hunting-shared-queries-1.png" alt-text="Consultas compartidas, Mis consultas y consultas de Community en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-shared-queries-1.png":::



## <a name="save-modify-and-share-a-query"></a>Guardar, modificar y compartir la consulta
Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización. 

1. Crear o modificar una consulta. 

2. Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.
    
3. Escriba un nombre para la consulta. 

   :::image type="content" source="../../media/shared-query-2.png" alt-text="La nueva consulta que está a punto de guardarse en el portal de Microsoft 365 Defender" lightbox="../../media/shared-query-2.png":::

4. Seleccione la carpeta en la que desea guardar la consulta.
    - **Consultas compartidas** — compartidas con todos los usuarios de su organización
    - **Mis consultas** — accesibles sólo para usted.
    
5. Seleccione **Guardar**. 

## <a name="delete-or-rename-a-query"></a>Eliminar o cambiar el nombre de la consulta
1. Seleccione los tres puntos situados a la derecha de una consulta que desea cambiar de nombre o eliminar.

    :::image type="content" source="../../media/advanced-hunting-del-save-query.png" alt-text="Cambiar el nombre o eliminar una consulta en la página Búsqueda avanzada del portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-del-save-query.png":::

2. Seleccione **Eliminar** y confirme su eliminación. O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.

## <a name="create-a-direct-link-to-a-query"></a>Creación de un vínculo directo a una consulta
Para generar un vínculo que abra la consulta directamente en el editor de consultas de búsqueda avanzada, finalice la consulta y seleccione **Compartir vínculo**.

## <a name="access-community-queries-in-the-github-repo"></a>Acceso a consultas de la comunidad en el repositorio de GitHub  
Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/Microsoft%20365%20Defender). Las contribuciones a este repositorio se revisan antes de publicarse. Para contribuir, [únete a GitHub gratis](https://github.com/).

Puede encontrar fácilmente estas consultas en el menú desplegable **Community consultas**.

:::image type="content" source="../../media/advanced-hunting-shared-queries-2.png" alt-text="Community consultas organizadas por carpeta en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-shared-queries-2.png":::

Community consultas se agrupan en carpetas como *Campañas*, *Colección*, *Evasión de defensa* y similares. Se proporciona más información sobre la consulta como comentarios en línea en la propia consulta. 

>[!tip]
>Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes. Estas consultas se proporcionan como parte de los informes de [análisis de amenazas](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) en Microsoft 365 Defender.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)