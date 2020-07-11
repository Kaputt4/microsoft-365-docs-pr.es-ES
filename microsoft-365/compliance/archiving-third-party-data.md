---
title: Archivar datos de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a buzones de correo de Microsoft 365.
ms.openlocfilehash: a8dc69e7e4c7061e048fe49d1e51fd8867654454
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101641"
---
# <a name="archive-third-party-data"></a>Archivar datos de terceros

Microsoft 365 permite que los administradores usen conectores de datos para importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a los buzones de la organización 365 de Microsoft. Una de las principales ventajas de usar conectores de datos para importar y archivar datos de terceros en Microsoft 365 es que puede aplicar diversas soluciones de cumplimiento de Microsoft 365 a esa una vez que se ha importado. Esto le ayudará a asegurarse de que los datos que no son de Microsoft de la organización cumplen con las normativas y los estándares que afectan a su organización.

## <a name="third-party-data-connectors"></a>Conectores de datos de terceros

En la siguiente tabla se enumeran los conectores de datos de terceros disponibles en el centro de cumplimiento de Microsoft 365. En la tabla también se resumen las soluciones de cumplimiento que se pueden aplicar a los datos de terceros después de importar y archivar en Microsoft 365. Consulte la [siguiente sección](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y de la forma en que puede beneficiarse de datos de terceros.

> [!TIP]
> Haga clic en el vínculo de la columna de **datos de terceros** para seguir las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Retención por juicio|eDiscovery  |Directivas de retención  |Administración de registros  |Cumplimiento de las comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Mensaje de Bloomberg](archive-bloomberg-message-data.md)     |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Datos de recursos humanos](import-hr-data.md) ||||||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[Chat de ICE](archive-icechat-data.md)     |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bloomberg instantáneo](archive-instant-bloomberg-data.md)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
||||||||

Los datos de terceros enumerados en la tabla anterior (excepto los datos de recursos humanos) se importan a los buzones de usuario. Las soluciones de cumplimiento correspondientes que admiten datos de terceros se aplican al buzón de usuario en el que se almacenan los datos.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Información general sobre las soluciones de cumplimiento que admiten datos de terceros

En las secciones siguientes se describen algunas de las cosas que las soluciones de cumplimiento de Microsoft 365 pueden ayudarle a administrar los datos de terceros enumerados en la tabla anterior.

### <a name="litigation-hold"></a>Retención por juicio

Debe realizar una [retención por juicio](create-a-litigation-hold.md) en un buzón de usuario para conservar los datos de terceros. Al crear una suspensión, puede especificar una duración de retención (también denominada *suspensión basada en tiempo*) para que los datos de terceros eliminados y modificados se conserven durante un período específico y, a continuación, se eliminen de forma permanente del buzón. O bien solo puede retener el contenido indefinidamente (denominado una *retención infinita*) o hasta que se quite la retención por juicio.

### <a name="ediscovery"></a>eDiscovery

Las tres herramientas de eDiscovery principales de Microsoft 365 son la búsqueda de contenido, la exhibición de documentos electrónicos principal y la exhibición avanzada de documentos electrónicos.

- **[Búsqueda de contenido](content-search.md).** Puede usar la herramienta de búsqueda de contenido para buscar en los buzones de correo de los datos de terceros que importó. Puede usar las condiciones y consultas de búsqueda para restringir los resultados de la búsqueda y la exportación de los resultados de la búsqueda.

- **[Exhibición](get-started-core-ediscovery.md)de documentos electrónicos principal.** Esta herramienta se basa en la funcionalidad básica de búsqueda y exportación, lo que permite crear casos que le permiten controlar quién puede tener acceso a los datos de los casos, retener los buzones de usuario o el contenido de los buzones de correo que coincidan con los criterios de búsqueda. Esto significa que puede poner una retención de eDiscovery en los datos de terceros que se importaron a los buzones de usuario.

- **[Exhibición avanzada](overview-ediscovery-20.md)de documentos electrónicos.** Esta eficaz herramienta amplía la funcionalidad de la exhibición de documentos electrónicos principal al permitirle agregar custodios a un caso, colocar los datos de custodios en espera y, a continuación, cargar los datos de terceros de un custodio en una revisión para un análisis más completo, como temas y detección de duplicados. Después de cargar los datos de terceros en un conjunto de revisiones, puede realizar consultas y filtrarlos para obtener un conjunto de resultados estrecho.

   La exhibición de documentos electrónicos principal y la exhibición de documentos electrónicos avanzada le permiten administrar los datos de terceros que pueden ser relevantes para las investigaciones legales o internas de su organización.

### <a name="retention-policies"></a>Directivas de retención

Puede aplicar una [Directiva de retención](retention-policies.md) a los buzones de usuario para conservar y, a continuación, eliminar los datos de terceros (y el contenido de otros buzones) una vez que expire el período de retención. También puede usar directivas de retención para eliminar datos de terceros de una antigüedad determinada o desencadenar una revisión de disposición cuando expire el período de retención.

### <a name="records-management"></a>Administración de registros

La característica de [Administración de registros](records-management.md) de Microsoft 365 permite declarar datos de terceros como un registro. Esto lo puede hacer manualmente los usuarios que apliquen una etiqueta de retención que marque los datos de terceros en su buzón como registro. O puede aplicar automáticamente etiquetas de retención mediante la identificación de información confidencial, palabras clave o tipos de contenido de datos de terceros.

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

Puede usar el [cumplimiento](communication-compliance.md) de la comunicación para examinar datos de terceros para asegurarse de que cumple con los estándares de datos de la organización. Puede hacerlo si detecta, captura y toma acciones de corrección para los mensajes inapropiados de la organización. Por ejemplo, puede supervisar los datos de terceros que importe para el lenguaje ofensivo, la información confidencial y el cumplimiento normativo.

### <a name="insider-risk-management"></a>Administración de riesgos internos

La solución de [Administración de riesgos de Insider](insider-risk-management.md) puede usar las señales de datos de terceros, como datos de recursos humanos selectivos, para minimizar los riesgos internos, ya que permite detectar, investigar y actuar en actividades arriesgadas de su organización. Por ejemplo, los datos importados por el conector de datos de recursos humanos se usan como indicadores de riesgo para ayudar a detectar el robo de datos de los empleados.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabajar con un socio de Microsoft para archivar datos de terceros

Otra opción para importar y archivar datos de terceros es que su organización trabaje con un socio de Microsoft. Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el centro de cumplimiento de Microsoft, puede trabajar con un socio que pueda proporcionar un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma periódica y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar dichos elementos a Microsoft 365. El conector de asociados también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Microsoft 365.

Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros en Microsoft 365](work-with-partner-to-archive-third-party-data.md).
