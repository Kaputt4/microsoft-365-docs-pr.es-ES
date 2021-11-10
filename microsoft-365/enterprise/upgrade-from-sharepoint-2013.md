---
title: Actualización desde SharePoint 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: sharepoint-server-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Busque información y recursos para actualizar desde SharePoint Server 2013 y SharePoint Foundation 2013. Compatibilidad con ambos fines del 11 de abril de 2023.
ms.openlocfilehash: 05f545b67d60d6bcc45587049e49a5f5c1f6d654
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889924"
---
# <a name="upgrading-from-sharepoint-2013"></a>Actualización desde SharePoint 2013

Both Microsoft SharePoint Server 2013 and SharePoint Foundation 2013 will reach end of support on **April 11, 2023**. En este artículo se proporcionan recursos que le ayudarán a migrar los datos de SharePoint Server existentes a SharePoint Online en Microsoft 365 o actualizar el entorno local SharePoint 2013. Para el resto de este artículo, usaremos SharePoint 2013 para hacer referencia a SharePoint Server 2013 y SharePoint Foundation 2013.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin de la compatibilidad?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Después de la fecha de finalización de la compatibilidad, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá más actualizaciones, revisiones o correcciones para el producto (incluidas revisiones o correcciones de seguridad). El soporte técnico de Microsoft habrá cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes.

> [!NOTE]
> Un ciclo de vida de software suele durar cinco años de soporte estándar desde la versión inicial y potencialmente hasta 5 años adicionales de soporte extendido. [Los proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) pueden ayudarle a actualizar a la siguiente versión del software o migrar a Microsoft 365 (o ambos). Asegúrese de que conoce las fechas de fin de soporte técnico para las tecnologías subyacentes críticas, especialmente para la versión de Microsoft SQL Server que está usando con SharePoint. Para obtener más información, consulte [Fixed Lifecycle Policy](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en que finaliza la compatibilidad en el sitio ciclo de vida del producto [para SharePoint Server 2013](/lifecycle/products/sharepoint-server-2013) [y SharePoint Foundation 2013](/lifecycle/products/sharepoint-foundation-2013). Planee las actualizaciones o las migraciones con estas fechas en mente. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se parchea después de esa fecha, querrá planear una transición sin problemas a la siguiente versión del producto. En la tabla siguiente se enumeran las opciones disponibles.

|Fin del producto de soporte técnico|Good|Mejor|Procedimientos|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|Actualización a SharePoint Server 2016 o 2019|Versión preliminar de SharePoint Server Edición de Suscripción|Migrar a SharePoint en Microsoft 365

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

Se recomienda migrar a SharePoint en Microsoft 365 aprovechar las últimas soluciones de colaboración, inteligencia y seguridad en Microsoft 365. Las características de la experiencia moderna Microsoft 365 están diseñadas para ser atractivas, flexibles y de rendimiento.

Si necesita mantener una implementación de SharePoint local, se recomienda una implementación híbrida que le permita migrar la mayor cantidad de funcionalidad SharePoint que pueda SharePoint en Microsoft 365. Vea [SharePoint híbrido para](/sharepoint/hybrid/hybrid) obtener información sobre una implementación híbrida y planearla.

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>Migrar a SharePoint en Microsoft 365

Puede usar la herramienta de SharePoint migración (SPMT) para migrar los sitios y el contenido a SharePoint en Microsoft 365. Tenemos una amplia biblioteca de contenido que puede ayudarle a planear con antelación, realizar la migración y solucionar los problemas que pueda encontrar. [Información general sobre la SharePoint de migración es](/sharepointmigration/introducing-the-sharepoint-migration-tool) un buen punto de inicio.

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>Versión preliminar de SharePoint Server Edición de Suscripción

Aunque no hay una ruta directa para actualizar de SharePoint 2013 a subscription Edition, esta sigue siendo la segunda mejor opción. El motivo principal es que SharePoint Server Subscription Edition presenta un modelo de actualización continua que elimina la necesidad de lanzar nuevas versiones principales de SharePoint Server en el futuro.

Para actualizar a Subscription Edition, debe ejecutar SharePoint Server 2016 o 2019. Dado que tampoco hay una ruta de acceso directa de SharePoint 2013 a 2019, la mejor opción es actualizar primero a 2016 y, a continuación, actualizar a Subscription Edition. Consulta los vínculos siguientes para obtener más información y planear la actualización a Subscription Edition:

- [Actualizar a SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [Versión preliminar de SharePoint Server Edición de Suscripción](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

Incluso si necesita mantener una implementación de SharePoint local, le recomendamos que migre partes de sus sitios o contenido [Microsoft 365 SharePoint](/sharepoint/hybrid/hybrid) con una implementación híbrida para empezar SharePoint aprovechar las características modernas de colaboración, seguridad y cumplimiento en Microsoft 365.  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>Actualización a SharePoint Server 2016 o 2019

Tanto SharePoint Server 2016 como 2019 son plataformas compatibles si tiene previsto mantener la implementación SharePoint local más allá del final de la compatibilidad para 2013. Sin embargo, ambas versiones llegarán al final de la compatibilidad **el 14 de julio de 2026**. Esto significa que tendrá que planear otra actualización dentro de 3 años después de la fecha de finalización del soporte técnico para 2013. Estas son las páginas de ciclo de vida de soporte técnico para ambos productos:

- [SharePoint Fechas de ciclo de vida de soporte técnico de Server 2016](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019 de ciclo de vida de soporte técnico](/lifecycle/products/sharepoint-server-2019)

Para obtener más información y planear la actualización, consulte los artículos siguientes:

- [Actualizar a SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [Actualizar a SharePoint Server 2019](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

Incluso si necesita mantener una implementación de SharePoint local, le recomendamos que migre partes de sus sitios o contenido [Microsoft 365 SharePoint](/sharepoint/hybrid/hybrid) con una implementación híbrida para empezar SharePoint aprovechar las características modernas de colaboración, seguridad y cumplimiento en Microsoft 365.  
