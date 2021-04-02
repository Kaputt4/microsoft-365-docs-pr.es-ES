---
title: Usar consultas compartidas en la búsqueda avanzada de Microsoft 365 Defender
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de github, mis consultas, consultas compartidas
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fbc5b4c53487bceab5786a7ce75a56741a3c9cb2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499713"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Utilice las consultas compartidas en la búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización. También puede buscar las consultas compartidas de forma pública en GitHub. Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.

![Imagen de las consultas compartidas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Guardar, modificar y compartir la consulta
Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización. 

1. Crear o modificar una consulta. 

2. Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.
    
3. Escriba un nombre para la consulta. 

   ![Imagen de una consulta guardada](../../media/advanced-hunting-save-query.png)

4. Seleccione la carpeta en la que desea guardar la consulta.
    - **Consultas compartidas** — compartidas con todos los usuarios de su organización
    - **Mis consultas** — accesibles sólo para usted.
    
5. Seleccione **Guardar**. 

## <a name="delete-or-rename-a-query"></a>Eliminar o cambiar el nombre de la consulta
1. Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.

    ![Imagen de una consulta eliminada](../../media/advanced_hunting_delete_rename.png)

2. Seleccione **Eliminar** y confirme su eliminación. O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.

## <a name="create-a-direct-link-to-a-query"></a>Crear un vínculo directo a una consulta
Para generar un vínculo que abra la consulta directamente en el editor de consultas de búsqueda avanzada, finalizar la consulta y seleccionar **Compartir vínculo**.

## <a name="access-queries-in-the-github-repository"></a>Acceder a las consultas en el repositorio de GitHub  
Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://aka.ms/hunting-queries). Este repositorio está abierto a contribuciones. Para contribuir, [únete a GitHub gratis](https://github.com/).

>[!tip]
>Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes. Estas consultas son proporcionadas en los informes del [análisis de amenazas](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)