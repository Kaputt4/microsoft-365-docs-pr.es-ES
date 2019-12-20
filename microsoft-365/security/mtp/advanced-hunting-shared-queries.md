---
title: Utilice las consultas compartidas en la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: Búsqueda, avanzada, de amenazas, de amenazas cibernéticas, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de Github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fb8addc7bc9e8ab01cc72bbdf02c12559d263196
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808695"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Utilice las consultas compartidas en la búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización. También puede buscar las consultas compartidas de forma pública en GitHub. Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.

![Imagen de las consultas compartidas](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Guardar, modificar y compartir la consulta
Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización. 

1. Crear o modificar una consulta. 

2. Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.
    
3. Escriba un nombre para la consulta. 

   ![Imagen de una consulta guardada](../images/advanced-hunting-save-query.png)

4. Seleccione la carpeta en la que desea guardar la consulta.
    - **Consultas compartidas** — compartidas con todos los usuarios de su organización
    - **Mis consultas** — accesibles sólo para usted.
    
5. Seleccione **Guardar**. 

## <a name="delete-or-rename-a-query"></a>Eliminar o cambiar el nombre de la consulta
1. Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.

    ![Imagen de una consulta eliminada](../images/advanced_hunting_delete_rename.png)

2. Seleccione **Eliminar** y confirme su eliminación. O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.

## <a name="access-queries-in-the-github-repository"></a>Acceder a las consultas en el repositorio de GitHub  
Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://github.com/microsoft/MTP-AHQ). Este repositorio está abierto a contribuciones. Para contribuir, [únete a GitHub gratis](https://github.com/).

>[!tip]
>Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes. Estas consultas son proporcionadas en los informes del [análisis de amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)