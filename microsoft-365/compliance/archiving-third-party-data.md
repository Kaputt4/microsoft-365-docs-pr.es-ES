---
title: Uso de conectores de datos para importar y archivar datos de terceros en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos en buzones de Microsoft 365.
ms.openlocfilehash: 41a7b37980919e28ecb4dbfd6e28b5d08b905a3d
ms.sourcegitcommit: 61df6377a6185a8b55e668cfb81adbd8462a9cce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2022
ms.locfileid: "67071665"
---
# <a name="learn-about-connectors-for-third-party-data"></a>Más información sobre los conectores para datos de terceros

Microsoft 365 permite a los administradores usar conectores de datos para importar y archivar datos que no son de Microsoft, datos de terceros de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, en buzones de su organización de Microsoft 365. Una ventaja principal del uso de conectores de datos para importar y archivar datos de terceros en Microsoft 365 es que puede aplicar varias soluciones de Microsoft Purview a los datos después de importarlos. Esto le ayuda a asegurarse de que los datos de su organización que no son de Microsoft cumplen con las regulaciones y estándares que afectan a su organización.

Vea esta guía interactiva que muestra cómo crear conectores de datos para importar y archivar datos de terceros y ejemplos de aplicación de soluciones de cumplimiento a los datos después de importarlos a Microsoft 365.

> [!VIDEO https://mslearn.cloudguides.com/guides/Archive%20data%20from%20non-Microsoft%20sources%20in%20Microsoft%20365]

## <a name="third-party-data-connectors"></a>Conectores de datos de terceros

El portal de cumplimiento Microsoft Purview proporciona conectores de datos nativos de microsoft de terceros para importar datos de varios orígenes de datos, como LinkedIn, Instant Bloomberg y Twitter, y conectores de datos que admiten la solución de administración de riesgos Insider. Además de estos conectores de datos, Microsoft trabaja con los siguientes asociados para proporcionar muchos más conectores de datos de terceros en el portal de cumplimiento. Su organización trabaja con estos asociados para configurar su servicio de archivado antes de crear un conector de datos correspondiente en el portal de cumplimiento.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

Los datos de terceros enumerados en las secciones siguientes (excepto los datos de RR. HH. y los datos físicos incorrectos que se usan para la solución Administración de riesgos internos de Microsoft Purview) se importan en buzones de usuario. Las soluciones de Microsoft Purview que admiten datos de terceros se aplican al buzón de usuario donde se almacenan los datos.

### <a name="microsoft-data-connectors"></a>Conectores de datos de Microsoft

En la tabla siguiente se enumeran los conectores de datos nativos de terceros disponibles en el portal de cumplimiento. En la tabla también se resumen las soluciones de cumplimiento que puede aplicar después de importar y archivar datos de terceros en Microsoft 365. Consulte la sección [Introducción a las soluciones de cumplimiento que admiten datos de terceros](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Haga clic en el vínculo de la columna **datos de terceros** para seguir las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Suspensión por litigio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Mensaje de Bloomberg](archive-bloomberg-message-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||
|[Atención sanitaria de EHR épica](import-epic-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Atención sanitaria de EHR genérica](import-healthcare-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Recursos humanos (RR. HH.)](import-hr-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Chat ICE](archive-icechat-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Bloomberg instantáneo](archive-instant-bloomberg-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Linkedin](archive-linkedin-data.md)   |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Mal estado físico](import-physical-badging-data.md) ||||||![Marca de verificación](../media/checkmark.png)|
|[Margen de demora eDiscovery](archive-slack-data-microsoft.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Conectores de datos de Veritas

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con Veritas. En la tabla también se resumen las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Consulte la sección [Introducción a las soluciones de cumplimiento que admiten datos de terceros](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, tiene que trabajar con Veritas para configurar su servicio de archivado (denominado *Merge1*) para su organización. Para obtener más información, haga clic en el vínculo de la columna **Datos de terceros** para seguir las instrucciones paso a paso para crear un conector para ese tipo de datos.

|Datos de terceros  |Suspensión por litigio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en MS SQL](archive-ciscojabberonmssql-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en Oracle](archive-ciscojabberonoracle-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber en PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Conectar FX](archive-fxconnect-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Base de datos SQL MS](archive-mssqldatabaseimporter-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Área dinámica](archive-pivot-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Skype Empresarial](archive-skypeforbusiness-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Margen de demora eDiscovery](archive-slack-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Texto delimitado](archive-text-delimited-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Twitter](archive-veritas-twitter-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Teams de Webex](archive-webexteams-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Páginas web](archive-webpagecapture-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Área de trabajo de Facebook](archive-workplacefromfacebook-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[YouTube](archive-youtube-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|||
|[Reuniones de Zoom](archive-zoommeetings-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>Conectores de datos de telemensaje

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con TeleMessage. En la tabla también se resumen las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Consulte la sección [Introducción a las soluciones de cumplimiento que admiten datos de terceros](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, tiene que trabajar con TeleMessage para configurar su servicio de archivado para su organización. Para obtener más información, haga clic en el vínculo de la columna **Datos de terceros** para seguir las instrucciones paso a paso para crear un conector para ese tipo de datos.

Los conectores de datos de TeleMessage también están disponibles en entornos GCC en la nube de Microsoft 365 US Government. Para obtener más información, consulte la sección [Conectores de datos en la nube del Gobierno de EE. UU](#data-connectors-in-the-us-government-cloud) . en este artículo.

|Datos de terceros  |Suspensión por litigio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[AT&T Network](archive-att-network-archiver-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red Bell](archive-bell-network-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Número de empresa](archive-enterprise-number-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red O2](archive-o2-network-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red Rogers](archive-rogers-network-archiver-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Señal](archive-signal-archiver-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Telegrama](archive-telegram-archiver-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red TELUS](archive-telus-network-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Red Verizon](archive-verizon-network-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 conectores de datos

En la tabla de esta sección se enumeran los conectores de datos de terceros disponibles en asociación con 17a-4 LLC. En la tabla también se resumen las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Consulte la sección [Introducción a las soluciones de cumplimiento que admiten datos de terceros](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, tiene que trabajar con 17a-4 LLC para configurar su servicio de archivado (denominado *DataParser*) para su organización. Para obtener más información, haga clic en el vínculo de la columna **Datos de terceros** para seguir las instrucciones paso a paso para crear un conector para ese tipo de datos.

Los conectores de datos 17a-4 también están disponibles en entornos GCC en la nube de Microsoft 365 US Government. Para obtener más información, consulte la sección [Conectores de datos en la nube del Gobierno de EE. UU](#data-connectors-in-the-us-government-cloud) . en este artículo.

|Datos de terceros  |Suspensión por litigio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Fusible](archive-17a-4-fuze-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Conectar FX](archive-17a-4-fxconnect-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Chat ICE](archive-17a-4-ice-im-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[LivePerson Conversational Cloud](archive-17a-4-liveperson-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
[Skype Empresarial Server](archive-17a-4-skype-for-business-server-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Margen de demora](archive-17a-4-slack-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
|[Zoom](archive-17a-4-zoom-data.md)    |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>Conectores de datos de CellTrust

En la tabla de esta sección se muestra el conector de datos de terceros disponible en asociación con CellTrust. En la tabla también se resumen las soluciones de cumplimiento que puede aplicar a datos de terceros después de importarlos y archivarlos en Microsoft 365. Consulte la sección [Introducción a las soluciones de cumplimiento que admiten datos de terceros](#overview-of-compliance-solutions-that-support-third-party-data) para obtener una descripción más detallada de cada solución de cumplimiento y cómo admite datos de terceros.

Para poder archivar datos de terceros en Microsoft 365, tiene que trabajar con CellTrust para configurar su servicio de archivado (llamado *CellTrust SL2*) para su organización. Para obtener más información, haga clic en el vínculo de la columna **de datos de terceros** para seguir las instrucciones paso a paso para crear un conector CellTrust SL2.

|Datos de terceros  |Suspensión por litigio|eDiscovery  |Configuración de retención  |Administración de registros  |Cumplimiento de comunicaciones  |Administración de riesgos internos  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)||
||||||||

El conector de datos CellTrust SL2 también está disponible en entornos GCC en la nube de Microsoft 365 US Government. Para obtener más información, consulte la sección [Conectores de datos en la nube del Gobierno de EE. UU](#data-connectors-in-the-us-government-cloud) . en este artículo.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Introducción a las soluciones de cumplimiento que admiten datos de terceros

En las secciones siguientes se describen algunas de las cosas que las soluciones de Microsoft Purview pueden ayudarle a administrar los datos de terceros enumerados en la tabla anterior.

### <a name="litigation-hold"></a>Suspensión por litigio

Coloca una [suspensión por juicio](create-a-litigation-hold.md) en un buzón de usuario para conservar los datos de terceros. Al crear una suspensión, puede especificar una duración de suspensión (también denominada *suspensión basada en tiempo*) para que los datos de terceros eliminados y modificados se conserven durante un período especificado y, a continuación, se eliminen permanentemente del buzón. O bien, puede conservar el contenido indefinidamente (denominada *suspensión infinita*) o hasta que se quite la suspensión por litigio.

### <a name="ediscovery"></a>eDiscovery

Las tres herramientas de exhibición de documentos electrónicos principales de Microsoft 365 son Búsqueda de contenido, Microsoft Purview eDiscovery (estándar) y Microsoft Purview eDiscovery (Premium).

- **[Búsqueda de contenido](content-search.md).** Puede usar la herramienta de búsqueda de contenido para buscar en buzones datos de terceros que haya importado. Puede usar consultas y condiciones de búsqueda para restringir los resultados de la búsqueda y exportar los resultados de la búsqueda.

- **[eDiscovery (Estándar).](get-started-core-ediscovery.md)** Esta herramienta se basa en la funcionalidad básica de búsqueda y exportación, ya que le permite crear casos que le permiten controlar quién puede acceder a los datos de casos, colocar una suspensión en buzones de usuario o contenido de buzón que coincida con los criterios de búsqueda. Esto significa que puede colocar una suspensión de eDiscovery en los datos de terceros que se importaron a los buzones de usuario.

- **[eDiscovery (Premium)](overview-ediscovery-20.md).** Esta eficaz herramienta expande la funcionalidad de casos de eDiscovery (Estándar) al permitirle agregar custodios a un caso, colocar los datos del custodio en espera y, a continuación, cargar los datos de terceros de un custodio en una revisión para un análisis adicional, como temas y detección de duplicados. Después de cargar datos de terceros en un conjunto de revisión, puede consultarlos y filtrarlos por un conjunto de resultados estrecho.

   Tanto eDiscovery (Estándar) como eDiscovery (Premium) le permiten administrar datos de terceros que pueden ser relevantes para las investigaciones legales o internas de su organización.

### <a name="retention-settings"></a>Configuración de retención

Puede aplicar una [directiva de retención](retention.md) a los buzones de usuario para conservar y eliminar datos de terceros (y otro contenido de buzón) después de que expire el período de retención. También puede usar directivas de retención para eliminar datos de terceros de una edad determinada o [usar etiquetas de retención para desencadenar una revisión de eliminación](disposition.md) cuando expire el período de retención de datos de terceros.

### <a name="records-management"></a>Administración de registros

La característica [de administración de registros](records-management.md) de Microsoft 365 le permite declarar datos de terceros como un registro. Esto lo pueden hacer manualmente los usuarios que aplican una etiqueta de retención que marca los datos de terceros en su buzón como registro. También puede aplicar automáticamente etiquetas de retención mediante la identificación de información confidencial, palabras clave o tipos de contenido en datos de terceros.

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

Puede usar [cumplimiento de comunicaciones](communication-compliance.md) para examinar datos de terceros a fin de asegurarse de que cumplen los estándares de datos de su organización. Para ello, detecte, capture y tome medidas correctivas para los mensajes inadecuados de su organización. Por ejemplo, puede supervisar los datos de terceros que importa para el lenguaje ofensivo, la información confidencial y el cumplimiento normativo.

### <a name="insider-risk-management"></a>Administración de riesgos internos

La solución de [administración de riesgos Insider](insider-risk-management.md) puede usar señales de datos de terceros, como datos de RR. HH. selectivos, para minimizar los riesgos internos, ya que le permite detectar, investigar y actuar sobre actividades de riesgo en su organización. Por ejemplo, los datos importados por el conector de datos de RR. HH. se usan como indicadores de riesgo para ayudar a detectar el robo de datos de los empleados que abandonan.

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>Uso de herramientas de eDiscovery para buscar datos de terceros

Después de usar conectores de datos para importar y archivar datos de terceros en buzones de usuario, puede usar las herramientas de eDiscovery de Microsoft 365 para buscar datos de terceros. También puede usar herramientas de eDiscovery para crear retenciones basadas en consultas asociadas a casos de eDiscovery (Estándar) y eDiscovery (Premium) para conservar datos de terceros. Para obtener más información sobre las herramientas de eDiscovery, consulte [soluciones de exhibición de documentos electrónicos en Microsoft 365](ediscovery.md).

Para buscar (o mantener) cualquier tipo de datos de terceros que haya importado a buzones de usuario mediante un conector de datos, puede usar la siguiente consulta de búsqueda. Asegúrese de limitar la búsqueda a los buzones de usuario.

```powershell
kind:externaldata
```

Puede usar esta consulta en el cuadro **Palabras clave** para una búsqueda de contenido, una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar) o una colección en eDiscovery (Premium).

![Consulta para buscar datos de terceros.](..\media\SearchThirdPartyData1.png)

También puede usar el `kind:externaldata` par property:value para restringir el ámbito de las búsquedas a datos de terceros. Por ejemplo, para buscar elementos importados desde cualquier origen de datos de terceros que contenga la palabra *contoso* en la propiedad **Subject** del elemento importado, use la siguiente consulta en el cuadro **Palabras clave** :

```powershell
subject:contoso AND kind:externaldata
```

Como alternativa, puede usar la condición **Tipo de** mensaje para configurar la misma consulta.

![Use la condición de tipo mensaje para restringir las búsquedas a datos de terceros.](..\media\SearchThirdPartyData2.png)

Para buscar un tipo específico de datos de terceros archivados, use la propiedad **itemclass** mailbox en una consulta de búsqueda. Use el siguiente formato property:value:

```powershell
itemclass:ipm.externaldata.<third-party data type>
```

Cada elemento importado por un conector de datos de terceros incluye la propiedad **itemclass** con un valor que corresponde al tipo de datos de terceros. Por ejemplo, para buscar datos de Facebook que contengan la palabra *contoso*, en la propiedad **Subject** del elemento importado, use la siguiente consulta:

```powershell
subject:contoso AND itemclass:ipm.externaldata.facebook*
```

Estos son algunos ejemplos de valores **itemclass** para diferentes tipos de datos de terceros.

| **Tipo de datos de terceros** | **Valor de la propiedad itemclass**   |
|---------------------------|-------------------------------------|
| Mensaje de Bloomberg         | ipm.externaldata.bloombergmessage* |
| CellTrust                 | ipm.externaldata.celltrust*        |
| Documento principal                     | ipm.externaldata.pivot*            |
| Archivador de WhatsApp         | ipm.externaldata.whatsapparchiver* |
|||

Los valores de la propiedad *itemclass* no distinguen mayúsculas de minúsculas. En general, use el nombre del tipo de datos de terceros (sin espacios) seguido de un carácter comodín ( * ).

Para obtener más información sobre cómo crear consultas de búsqueda de eDiscovery, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

## <a name="data-connectors-in-the-us-government-cloud"></a>Conectores de datos en la nube del Gobierno de EE. UU.

Algunos conectores de datos están disponibles en la nube del Gobierno de EE. UU. En las secciones siguientes se indican los entornos gubernamentales específicos que admiten conectores de datos de terceros. Para obtener más información sobre las nubes de US Government, consulte [Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy).

### <a name="veritas-data-connectors-in-the-us-government-cloud-preview"></a>Conectores de datos de Veritas en la nube del Gobierno de EE. UU. (versión preliminar)

|Conector de datos  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust| Sí | No | No |
|Cisco Jabber en MS SQL| Sí | No | No |
|Cisco Jabber en Oracle| Sí | No | No |
|Cisco Jabber en PostgreSQL| Sí | No | No |
|EML| Sí | No | No |
|Conectar FX| Sí | No | No |
|Jive| Sí | No | No |
|Base de datos SQL MS| Sí | No | No |
|Documento principal| Sí | No | No |
|Redtail Speak| Sí | No | No |
|Reuters Dealing| Sí | No | No |
|Reuters Eikon| Sí | No | No |
|Reuters FX| Sí | No | No |
|RingCentral| Sí | No | No |
|Salesforce Chatter| Sí | No | No |
|ServiceNow| Sí | No | No |
|Skype for Business| Sí | No | No |
|Margen de demora eDiscovery| Sí | No | No |
|Symphony| Sí | No | No |
|Texto delimitado| Sí | No | No |
|Twitter| Sí | No | No |
|Teams de Webex| Sí | No | No |
|Páginas web| Sí | No | No |
|Área de trabajo de Facebook| Sí | No | No |
|XIP| Sí | No | No |
|XSLT/XML| Sí | No | No |
|Yieldbroker| Sí | No | No |
|YouTube| No | No | No |
|Reuniones de Zoom| Sí | No | No |
|||||

### <a name="telemessage-data-connectors-in-the-us-government-cloud"></a>Conectores de datos de TeleMessage en la nube del Gobierno de EE. UU.

|Conector de datos  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Archivador de Android | Sí | No | No |
|Archivador de red AT&T SMS/MMS | Sí | No | No |
|Archivador de red SMS/MMS de Bell | Sí | No | No |
|Archivador de números de empresa | Sí | No | No |
|Archivo de red de voz y SMS de O2 | Sí         | No | No |
|Archivador de red social | Sí         | No | No |
|Archivador de Signal | Sí | No | No |
|Archivador de Telegram | Sí | No | No |
|Archivador de red de SMS de TELUS | Sí | No | No |
|Archivador de red SMS/MMS de Verizon | Sí | No | No |
|Archivador de WeChat | Sí | No | No |
|Archivador de WhatsApp | Sí | No | No |
|||||

### <a name="17a-4-data-connectors-in-the-us-government-cloud"></a>Conectores de datos 17a-4 en la nube del Gobierno de EE. UU.

|Conector de datos  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|BlackBerry DataParser | Sí | No | No |
|Bloomberg DataParser  | Sí | No | No |
|Cisco Jabber DataParser  | Sí | No | No |
|Cisco Webex DataParser  | Sí | No | No |
|FactSet DataParser  | Sí | No | No |
|Fuze DataParser  | Sí | No | No |
|FX Connect DataParser  | Sí | No | No |
|ICE DataParser  | Sí | No | No |
|InvestEdge DataParser  | Sí | No | No |
|DataParser de la Nube conversacional de LivePerson  | Sí | No | No |
|Quip DataParser  | Sí | No | No |
|DataParser de Refinitiv Eikon Messenger  | Sí | No | No |
|ServiceNow DataParser  | Sí | No | No |
|DataParser de Skype Empresarial Server | Sí | No | No |
|Slack DataParser | Sí | No | No |
|SQL DataParser  | Sí | No | No |
|DataParser de Symphony | Sí | No | No |
|Zoom DataParser | Sí | No | No |
|||||

### <a name="celltrust-data-connectors-in-the-us-government-cloud"></a>Conectores de datos de CellTrust en la nube del Gobierno de EE. UU.

|Conector de datos  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | Sí | No | No |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabajar con un asociado de Microsoft para archivar datos de terceros

Otra opción para importar y archivar datos de terceros es que su organización trabaje con un asociado de Microsoft. Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el Centro de cumplimiento de Microsoft, puede trabajar con un asociado que pueda proporcionar un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma regular y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar esos elementos a Microsoft 365. El conector de asociado también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón de correo de Microsoft 365.

Para obtener una lista de asociados con los que puede trabajar y el proceso paso a paso para este método, consulte [Trabajo con un asociado para archivar datos de terceros en Microsoft 365](work-with-partner-to-archive-third-party-data.md).
