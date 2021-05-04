---
title: Archivar datos de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo importar datos de terceros desde plataformas de redes sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a Microsoft 365 buzones de correo.
ms.openlocfilehash: 22a2e6dbadc3c259896348fc89754882db85cfb4
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764115"
---
# <a name="archive-third-party-data"></a>Archivar datos de terceros

Microsoft 365 permite a los administradores usar conectores de datos para importar y archivar datos de terceros desde plataformas de redes sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a buzones de correo de su Microsoft 365 organización. Una ventaja principal del uso de conectores de datos para importar y archivar datos de terceros en Microsoft 365 es que puede aplicar varias soluciones de cumplimiento de Microsoft 365 después de importarlos. Esto le ayuda a asegurarse de que los datos que no son de Microsoft de su organización cumplen con las normativas y estándares que afectan a su organización.

## <a name="third-party-data-connectors"></a>Conectores de datos de terceros

En la tabla siguiente se enumeran los conectores de datos de terceros disponibles en el Microsoft 365 de cumplimiento. La tabla también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importar y archivar en Microsoft 365. Vea la [siguiente sección para](#overview-of-compliance-solutions-that-support-third-party-data) obtener una descripción más detallada de cada solución de cumplimiento y cómo puede beneficiar a los datos de terceros.

> [!TIP]
> Haga clic en  el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red de Bell <sup>1</sup>](archive-bell-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Mensaje de Bloomberg](archive-bloomberg-message-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en MS SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en PostgreSQL <sup>2</sup>](archive-ciscojabberonpostgresql-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Enterprise Número <sup>1</sup>](archive-enterprise-number-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[FX Conectar <sup>2</sup>](archive-fxconnect-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Recursos humanos (RRHH)](import-hr-data.md) ||||||![Marca de verificación](../media/checkmark.png)
|[Chat ICE](archive-icechat-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Bloomberg instantáneo](archive-instant-bloomberg-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Linkedin](archive-linkedin-data.md)   |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Red O2 <sup>1</sup>](archive-o2-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Problemas físicos](import-physical-badging-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[<sup>Sinfonía 2</sup>](archive-symphony-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red TELUS <sup>1</sup>](archive-telus-network-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Delimitado por texto <sup>2</sup>](archive-text-delimited-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Red De Verizon <sup>1</sup>](archive-verizon-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Páginas web <sup>2</sup>](archive-webpagecapture-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Workplace de Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuniones de zoom <sup>2</sup>](archive-zoommeetings-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Conector de datos proporcionado por TeleMessage. Para poder archivar datos en Microsoft 365, debe trabajar con TeleMessage para configurar su servicio de archivado para su organización. Para obtener más información, vea la sección de requisitos previos en las instrucciones paso a paso para este tipo de datos.<br/><br/><sup>2</sup> Conector de datos proporcionado por Veritas. Para poder archivar datos en Microsoft 365, debe trabajar con Veritas para configurar su servicio de archivado para su organización. Para obtener más información, vea la sección de requisitos previos en las instrucciones paso a paso para este tipo de datos.

Los datos de terceros enumerados en la tabla anterior (excepto los datos de recursos humanos y los datos de pérdida física) se importan a los buzones de usuario. Las soluciones de cumplimiento correspondientes que admiten datos de terceros se aplican al buzón de usuario donde se almacenan los datos.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Información general sobre las soluciones de cumplimiento que admiten datos de terceros

En las secciones siguientes se describen algunas de las cosas que las soluciones de cumplimiento Microsoft 365 pueden ayudarle a administrar los datos de terceros enumerados en la tabla anterior.

### <a name="litigation-hold"></a>Retención por juicio

Se coloca una retención [por juicio](create-a-litigation-hold.md) en un buzón de usuario para conservar datos de terceros. Al crear una retención, puede especificar una duración de retención (también denominada retención basada en *tiempo)* para que los datos de terceros eliminados y modificados se conserven durante un período especificado y, a continuación, se eliminen permanentemente del buzón. O puede conservar el contenido indefinidamente (denominado retención *infinita)* o hasta que se quite la retención por juicio.

### <a name="ediscovery"></a>eDiscovery

Las tres herramientas principales de exhibición de documentos electrónicos Microsoft 365 búsqueda de contenido, eDiscovery principal y Advanced eDiscovery.

- **[Búsqueda de contenido](content-search.md).** Puede usar la herramienta de búsqueda de contenido para buscar en buzones de correo datos de terceros que importó. Puede usar las consultas y condiciones de búsqueda para restringir los resultados de búsqueda y exportar los resultados de la búsqueda.

- **[EDiscovery principal](get-started-core-ediscovery.md).** Esta herramienta se basa en la funcionalidad básica de búsqueda y exportación, ya que permite crear casos que le permitan controlar quién puede tener acceso a los datos de casos, colocar una retención en los buzones de usuario o contenido de buzones de correo que coincida con los criterios de búsqueda. Esto significa que puede colocar una retención de exhibición de documentos electrónicos en los datos de terceros que se importaron a los buzones de usuario.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Esta eficaz herramienta amplía la funcionalidad de casos de eDiscovery principal, ya que permite agregar custodios a un caso, poner los datos del custodio en espera y, a continuación, cargar los datos de terceros de un custodio en una revisión para análisis adicionales, como temas y detección de duplicados. Después de cargar datos de terceros en un conjunto de revisión, puede consultarlo y filtrarlo a un conjunto de resultados estrecho.

   Tanto la exhibición de documentos electrónicos principales como Advanced eDiscovery permiten administrar datos de terceros que pueden ser relevantes para las investigaciones legales o internas de su organización.

### <a name="retention-settings"></a>Configuración de retención

Puede aplicar una [directiva](retention.md) de retención a los buzones de usuario para conservar y, a continuación, eliminar datos de terceros (y otro contenido de buzón) después de que expire el período de retención. También puede usar directivas de retención para eliminar datos [](disposition.md) de terceros de cierta antigüedad o usar etiquetas de retención para desencadenar una revisión de eliminación cuando expire el período de retención de datos de terceros.

### <a name="records-management"></a>Administración de registros

La [característica de administración](records-management.md) de registros Microsoft 365 permite declarar datos de terceros como un registro. Esto lo pueden hacer manualmente los usuarios que aplican una etiqueta de retención que marca los datos de terceros en su buzón como registro. También puede aplicar automáticamente etiquetas de retención identificando información confidencial, palabras clave o tipos de contenido en datos de terceros.

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

Puede usar el [cumplimiento de la comunicación](communication-compliance.md) para examinar los datos de terceros para asegurarse de que son compatibles con los estándares de datos de su organización. Puede hacerlo detectando, capturando y llevando a cabo acciones de corrección para mensajes inapropiados en su organización. Por ejemplo, puede supervisar los datos de terceros que importa para el lenguaje ofensivo, la información confidencial y el cumplimiento normativo.

### <a name="insider-risk-management"></a>Administración de riesgos internos

Las señales de datos de terceros, como los datos de recursos humanos selectivos, pueden ser usadas por la solución de administración de riesgos [insider](insider-risk-management.md) para minimizar los riesgos internos, ya que le permite detectar, investigar y actuar en actividades de riesgo en su organización. Por ejemplo, los datos importados por el conector de datos de RECURSOS humanos se usan como indicadores de riesgo para ayudar a detectar el robo de datos de empleados que salen.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabajar con un partner de Microsoft para archivar datos de terceros

Otra opción para importar y archivar datos de terceros es que su organización trabaje con un partner de Microsoft. Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el Centro de cumplimiento de Microsoft, puede trabajar con un partner que pueda proporcionar un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma regular y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar esos elementos a Microsoft 365. El conector de asociado también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Microsoft 365.

Para obtener una lista de socios con los que puede trabajar y el proceso paso a paso para este método, vea Trabajar con un partner para archivar datos de terceros en [Microsoft 365](work-with-partner-to-archive-third-party-data.md).
