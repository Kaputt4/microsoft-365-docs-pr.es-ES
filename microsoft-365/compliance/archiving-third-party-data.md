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
ms.openlocfilehash: de4c3c6454809cc1b7f78c0e5790fcbe8b3887c0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096173"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>Archivar datos de terceros en Microsoft 365

Microsoft 365 permite a los administradores usar conectores de datos para importar y archivar datos de terceros desde plataformas de redes sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a buzones de correo de su Microsoft 365 organización. Una ventaja principal del uso de conectores de datos para importar y archivar datos de terceros en Microsoft 365 es que puede aplicar varias soluciones de cumplimiento de Microsoft 365 después de importarlos. Esto le ayuda a asegurarse de que los datos que no son de Microsoft de su organización cumplen con las normativas y estándares que afectan a su organización.

## <a name="third-party-data-connectors"></a>Conectores de datos de terceros

El Centro de cumplimiento de Microsoft 365 proporciona conectores de datos de terceros nativos de Microsoft para importar datos de varios orígenes de datos, como LinkedIn, Instant Bloomberg y Twitter y conectores de datos que admiten la solución de administración de riesgos insider. Además de estos conectores de datos, Microsoft trabaja con los siguientes partners para proporcionar muchos más conectores de datos de tercera parte en el Centro de cumplimiento de Microsoft 365. Su organización trabaja con estos partners para configurar su servicio de archivado antes de crear un conector de datos correspondiente en el Centro de cumplimiento de Microsoft 365.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

Los datos de terceros que aparecen en las secciones siguientes (excepto los datos de recursos humanos y los datos de pérdida física que se usan para la solución de administración de riesgos de Microsoft 365 Insider) se importan a los buzones de usuario. Las Microsoft 365 de cumplimiento que admiten datos de terceros se aplican al buzón de usuario donde se almacenan los datos.

### <a name="microsoft-data-connectors"></a>Conectores de datos de Microsoft

En la tabla siguiente se enumeran los conectores de datos de terceros nativos disponibles en el Centro de cumplimiento de Microsoft 365. La tabla también resume las soluciones de cumplimiento que puede aplicar después de importar y archivar datos de terceros en Microsoft 365. Vea la sección Información general [sobre las](#overview-of-compliance-solutions-that-support-third-party-data) soluciones de cumplimiento que admiten datos de terceros para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Haga clic en  el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Mensaje de Bloomberg](archive-bloomberg-message-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Recursos humanos (RRHH)](import-hr-data.md) ||||||![Marca de verificación](../media/checkmark.png)
|[Chat ICE](archive-icechat-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Bloomberg instantáneo](archive-instant-bloomberg-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Linkedin](archive-linkedin-data.md)   |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Problemas físicos](import-physical-badging-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Conectores de datos de Veritas

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con Veritas. La tabla también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Vea la sección Información general [sobre las](#overview-of-compliance-solutions-that-support-third-party-data) soluciones de cumplimiento que admiten datos de terceros para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, debe trabajar con Veritas para configurar su servicio de archivado (denominado *Merge1*) para su organización. Para obtener más información,  haga clic en el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en MS SQL](archive-ciscojabberonmssql-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en Oracle](archive-ciscojabberonoracle-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Conectar FX](archive-fxconnect-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Base de datos SQL MS](archive-mssqldatabaseimporter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Área dinámica](archive-pivot-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Margen de demora eDiscovery](archive-slack-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Texto delimitado](archive-text-delimited-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Teams de Webex](archive-webexteams-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Páginas web](archive-webpagecapture-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Área de trabajo de Facebook](archive-workplacefromfacebook-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuniones de Zoom](archive-zoommeetings-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>Conectores de datos de telemensaje

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con TeleMessage. La tabla también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Vea la sección Información general [sobre las](#overview-of-compliance-solutions-that-support-third-party-data) soluciones de cumplimiento que admiten datos de terceros para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, debe trabajar con TeleMessage para configurar su servicio de archivado para su organización. Para obtener más información,  haga clic en el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector para ese tipo de datos.

Los conectores de datos de TeleMessage también están disponibles en GCC entornos en la Microsoft 365 us government cloud. Para obtener más información, vea la sección Conectores de datos en la nube del Gobierno de Estados Unidos en este artículo.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android ](archive-android-archiver-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[AT&T Network ](archive-att-network-archiver-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red de Bell ](archive-bell-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Enterprise Número](archive-enterprise-number-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red O2 ](archive-o2-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red TELUS ](archive-telus-network-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red De Verizon ](archive-verizon-network-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[WeChat ](archive-wechat-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[WhatsApp ](archive-whatsapp-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>Conectores de datos de 17a-4

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con 17a-4 LLC. La tabla también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Vea la sección Información general [sobre las](#overview-of-compliance-solutions-that-support-third-party-data) soluciones de cumplimiento que admiten datos de terceros para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, debe trabajar con Veritas para configurar su servicio de archivado (denominado *DataParser)* para su organización. Para obtener más información,  haga clic en el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Bloomberg ](archive-17a-4-bloomberg-data.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber ](archive-17a-4-cisco-jabber-data.md)   |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Webex ](archive-17a-4-webex-teams-data.md)   |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[FactSet ](archive-17a-4-factset-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Fuze ](archive-17a-4-fuze-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Fx Conectar](archive-17a-4-fxconnect-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Chat ICE](archive-17a-4-ice-im-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[InvestEdge ](archive-17a-4-investedge-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[LivePerson Conversational Cloud ](archive-17a-4-liveperson-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Quip ](archive-17a-4-quip-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[ServiceNow ](archive-17a-4-servicenow-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Slack ](archive-17a-4-slack-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Sinfónico ](archive-17a-4-symphony-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Zoom ](archive-17a-4-zoom-data.md)    |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>Conectores de datos cellTrust

En la tabla de esta sección se muestra el conector de datos de terceros disponible en asociación con CellTrust. La tabla también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Vea la sección Información general [sobre las](#overview-of-compliance-solutions-that-support-third-party-data) soluciones de cumplimiento que admiten datos de terceros para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, debe trabajar con CellTrust para configurar su servicio de archivado (denominado *CellTrust SL2)* para su organización. Para obtener más información,  haga clic en el vínculo de la columna de datos de terceros para ir a las instrucciones paso a paso para crear un conector CellTrust SL2.

|Datos de terceros  |Retención por juicio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

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

## <a name="data-connectors-in-the-us-government-cloud"></a>Conectores de datos en la nube de Us Government

Como se mencionó anteriormente, los conectores de datos proporcionados por TeleMessage están disponibles en la nube de Us Government. En la tabla siguiente se indican los entornos gubernamentales específicos que admiten cada conector de datos de TeleMessage. Para obtener más información acerca de las nubes de us government, [vea Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy).

|Conector de datos de TeleMessage  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Archivador de Android | Sí | No | No |
|AT&T SMS/MMS Network Archiver | Sí | No | No |
|Archivador de red DE SMS/MMS de Bell | Sí | No | No |
|Enterprise Archivador de números | Sí | No | No |
|SMS de O2 y archivador de red de voz | Sí         | No | No |
|Archivador de red DE SMS TELUS | Sí | No | No |
|Archivador de red DE SMS/MMS de Verizon | Sí | No | No |
|Archivador de WhatsApp | Sí | No | No |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabajar con un partner de Microsoft para archivar datos de terceros

Otra opción para importar y archivar datos de terceros es que su organización trabaje con un partner de Microsoft. Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el Centro de cumplimiento de Microsoft, puede trabajar con un partner que pueda proporcionar un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma regular y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar esos elementos a Microsoft 365. El conector de asociado también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Microsoft 365.

Para obtener una lista de socios con los que puede trabajar y el proceso paso a paso para este método, vea Trabajar con un partner para archivar datos de terceros en [Microsoft 365](work-with-partner-to-archive-third-party-data.md).
