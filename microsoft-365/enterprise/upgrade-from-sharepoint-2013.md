---
title: Actualización desde SharePoint 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.collection:
- scotvorg
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Busque información y recursos para actualizar desde SharePoint Server 2013 y SharePoint Foundation 2013. Compatibilidad con ambos extremos el 11 de abril de 2023.
ms.openlocfilehash: cd2c9b233685aeeee329b5ebeafcb3ff3a27f4b3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193287"
---
# <a name="upgrading-from-sharepoint-2013"></a>Actualización desde SharePoint 2013

Microsoft SharePoint Server 2013 y SharePoint Foundation 2013 finalizarán el soporte técnico el **11 de abril de 2023**. En este artículo se proporcionan recursos que le ayudarán a migrar los datos de SharePoint Server existentes a SharePoint Online en Microsoft 365 o a actualizar el entorno local de SharePoint 2013. En el resto de este artículo, usaremos SharePoint 2013 para hacer referencia a SharePoint Server 2013 y SharePoint Foundation 2013.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin del soporte técnico*?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Después de la fecha de finalización del soporte técnico, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá actualizaciones, revisiones ni correcciones adicionales para el producto (incluidas revisiones o correcciones de seguridad). Soporte técnico de Microsoft habrá cambiado por completo sus esfuerzos de soporte técnico a versiones más recientes.

> [!NOTE]
> Un ciclo de vida de software suele durar cinco años de soporte estándar desde la versión inicial y, potencialmente, hasta 5 años adicionales de soporte extendido. [Los proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) pueden ayudarle a actualizar a la siguiente versión del software o a migrar a Microsoft 365 (o ambos). Asegúrese de tener en cuenta las fechas de finalización del soporte técnico para las tecnologías subyacentes críticas, especialmente para la versión de Microsoft SQL Server que usa con SharePoint. Para obtener más información, consulte [Directiva de ciclo de vida fijo](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas que finalizan en el sitio ciclo de vida del producto para [SharePoint Server 2013](/lifecycle/products/sharepoint-server-2013) y [SharePoint Foundation 2013](/lifecycle/products/sharepoint-foundation-2013). Planee las actualizaciones o migraciones teniendo en cuenta estas fechas. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se aplicará una revisión después de esa fecha, querrá planear una transición fluida a la siguiente versión del producto. En la tabla siguiente se enumeran las opciones disponibles.

|Producto de fin de soporte técnico|Good|Mejor|Procedimientos|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|Actualización a SharePoint Server 2016 o 2019|Versión preliminar de SharePoint Server Edición de Suscripción|Migración a SharePoint en Microsoft 365

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

Se recomienda migrar a SharePoint en Microsoft 365 para aprovechar las últimas soluciones de colaboración, inteligencia y seguridad de Microsoft 365. Las características de la experiencia moderna de Microsoft 365 están diseñadas para ser atractivas, flexibles y eficaces.

Si necesita mantener una implementación local de SharePoint, se recomienda una implementación híbrida que le permita migrar tanta funcionalidad de SharePoint como pueda a SharePoint en Microsoft 365. Consulte [SharePoint hybrid (Híbrido de SharePoint](/sharepoint/hybrid/hybrid) ) para obtener información sobre una implementación híbrida y planearla.

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>Migración a SharePoint en Microsoft 365

Puede usar la Herramienta de migración de SharePoint (SPMT) para migrar los sitios y el contenido a SharePoint en Microsoft 365. Tenemos una amplia biblioteca de contenido que puede ayudarle a planear con antelación, realizar la migración y solucionar cualquier problema que pueda surgir. [La información general de la herramienta de migración de SharePoint](/sharepointmigration/introducing-the-sharepoint-migration-tool) es un buen lugar para empezar.

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>Versión preliminar de SharePoint Server Edición de Suscripción

Aunque no hay una ruta de acceso directa para actualizar de SharePoint 2013 a subscription Edition, esta sigue siendo la segunda mejor opción. La razón principal es que SharePoint Server Edición de Suscripción presenta un modelo de actualización continua que elimina la necesidad de publicar nuevas versiones principales de SharePoint Server en el futuro.

Para actualizar a Subscription Edition, debe ejecutar SharePoint Server 2016 o 2019. Dado que tampoco hay una ruta de acceso directa de SharePoint 2013 a 2019, la mejor opción es actualizar primero a 2016 y, a continuación, actualizar a Subscription Edition. Consulte los vínculos siguientes para obtener más información sobre y planear la actualización a Subscription Edition:

- [Actualizar a SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [Versión preliminar de SharePoint Server Edición de Suscripción](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

Incluso si tiene la necesidad de mantener una implementación local de SharePoint, se recomienda migrar partes de sus sitios o contenido a Microsoft 365 con implementación [híbrida de SharePoint](/sharepoint/hybrid/hybrid) para empezar a aprovechar las experiencias de colaboración modernas, las características de seguridad y cumplimiento de Microsoft 365.  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>Actualización a SharePoint Server 2016 o 2019

SharePoint Server 2016 y 2019 son plataformas compatibles si tiene previsto mantener la implementación de SharePoint local más allá del final de la compatibilidad para 2013. Sin embargo, **ambas versiones llegarán al final del soporte técnico el 14 de julio de 2026**. Esto significa que tendrá que planear otra actualización en un plazo de 3 años después de la fecha de finalización del soporte técnico para 2013. Estas son las páginas del ciclo de vida de soporte técnico para ambos productos:

- [Fechas de ciclo de vida de soporte técnico de SharePoint Server 2016](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019 fechas del ciclo de vida de soporte técnico](/lifecycle/products/sharepoint-server-2019)

Para más información y planear la actualización, consulte los artículos siguientes:

- [Actualizar a SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [Actualizar a SharePoint Server 2019](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

Incluso si tiene la necesidad de mantener una implementación local de SharePoint, se recomienda migrar partes de sus sitios o contenido a Microsoft 365 con implementación [híbrida de SharePoint](/sharepoint/hybrid/hybrid) para empezar a aprovechar las experiencias de colaboración modernas, las características de seguridad y cumplimiento de Microsoft 365.  
