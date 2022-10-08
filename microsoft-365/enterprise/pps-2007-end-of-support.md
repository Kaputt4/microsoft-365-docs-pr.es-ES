---
title: Plan de fin del soporte técnico de PerformancePoint Server 2007
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007, ProClarity y SharePoint Server 2007 han llegado al final del soporte técnico. Lea este artículo para ayudar a planear la actualización de la solución de BI.
ms.openlocfilehash: 59b1833c4c740b7be92bd01befbd4f85dd38a670
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207696"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de PerformancePoint Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Los servidores y aplicaciones de Office 2007 han llegado a su fin de soporte técnico, incluidos los servidores y las aplicaciones que podría usar como parte de las soluciones de inteligencia empresarial (BI). En la tabla siguiente se enumeran las aplicaciones de BI que se ven afectadas:
  
|**Aplicaciones de Microsoft BI**|**Fecha de finalización del soporte técnico**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 de julio de 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 de octubre de 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 de enero de 2018  <br/> |
   
Para obtener más información, vea [Recursos para ayudarle a actualizar desde servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

Al igual que la mayoría de los productos de Microsoft, PerformancePoint Server 2007 SP3, el software ProClarity y SharePoint Server 2007 SP3 tienen un ciclo de vida de soporte técnico, durante el cual Microsoft proporciona nuevas características, correcciones de errores y actualizaciones de seguridad. El ciclo de vida de un producto suele durar 10 años a partir de la versión inicial del producto. El final de ese ciclo de vida se conoce como el fin del soporte técnico del producto. Como ProClarity, PerformancePoint Server y SharePoint Server 2007 han llegado a su fin de soporte técnico, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para los problemas que se detectan y que pueden afectar a la estabilidad y facilidad de uso de los servidores.
    
- Correcciones de seguridad para las vulnerabilidades que se detectan y que pueden hacer que los servidores o las aplicaciones sean vulnerables a las infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de ProClarity, SharePoint Server 2007 SP3 y PerformancePoint Server 2007 SP3 seguirá ejecutándose aunque haya finalizado el soporte técnico. Sin embargo, se recomienda encarecidamente migrar desde estas aplicaciones lo antes posible.
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Desde 2007 ha habido muchos cambios en las aplicaciones de Microsoft BI y tiene varias opciones que tener en cuenta, como se resume en la tabla siguiente.
  
|**Si estuviera usando este ...**|**Explore estas opciones...**|**Y ten esto en cuenta...**|
|:-----|:-----|:-----|
| Supervisión &amp; de PerformancePoint Server 2007 Funcionalidades de análisis, entre las que se incluyen:<br/>- PerformancePoint Monitoring Server <br/>- Diseñador de paneles de PerformancePoint<br/>- Visor de paneles para SharePoint Services (se usa para representar paneles, cuadros de mandos e informes de PerformancePoint)<br/> |**Excel con Excel en un explorador** (en la nube o en el entorno local). Para obtener información general, consulte [Funcionalidades de BI en Excel y Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (en la nube o en el entorno local). Para obtener información general, consulte [¿Qué es Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (local). Para obtener información general, consulte [SQL Server Reporting Services (SSRS): Creación, implementación y administración de informes paginados y móviles](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports). <br/><br/> **PerformancePoint Services** (local). Para obtener información general, vea [Novedades de PerformancePoint Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)) <br/> |Excel está disponible como una solución en línea (basada en la nube) o local. Se pueden satisfacer muchas necesidades de informes y paneles con Excel.  <br/><br/> Power BI está disponible como una solución en línea o local. Power BI no se incluye en Microsoft 365. Pero puede empezar a usar Power BI de forma gratuita. Más adelante, en función del uso de datos y las necesidades empresariales, puede actualizar a Power BI Pro con Microsoft 365 E5.<br/> <br/> Reporting Services y PerformancePoint Services son soluciones locales. <br/><br/> PerformancePoint Services está disponible en SharePoint Server 2010, SharePoint Server 2013 y SharePoint Server 2016. <br/> <br/> Algunas características y tipos de informe que estaban disponibles en PerformancePoint Server 2007 no están disponibles en Excel, Power BI, Reporting Services o PerformancePoint Services. Revise las características disponibles para determinar la mejor solución para sus necesidades empresariales. <br/> |
| Software ProClarity, que incluye:<br/>- ProClarity Desktop Professional<br/> - Servidor de ProClarity Analytics<br/>- Visor de SharePoint de ProClarity<br/> |**Trabaje con un asociado de Microsoft** para identificar una solución que mejor se adapte a sus necesidades. Visite el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> También puede considerar el uso de Excel con Excel en un explorador, Power BI, SQL Server Reporting Services o PerformancePoint Services.  <br/> |Varias características del software ProClarity, pero no todas, están disponibles en otras ofertas de Microsoft, como Excel, Power BI, Reporting Services y PerformancePoint Services.  <br/> |
|KPI de SharePoint Server 2007 (también denominadoS KPI de MOSS)  <br/> |**Excel con Excel Services**. Para obtener información general, vea [Inteligencia empresarial en Excel y Excel Services (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |Los KPI de MOSS creados con SharePoint Server 2007 se pueden usar en SharePoint Server 2010, SharePoint Server 2013 y SharePoint Server 2016. Pero no puede crear nuevos KPI de MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (en la nube o en el entorno local). Para obtener información general, consulte [Funcionalidades de BI en Excel y Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (en la nube o en el entorno local). Para obtener información general, consulte [¿Qué es Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Tanto Excel como Power BI ofrecen soluciones locales y basadas en la nube de su organización, con compatibilidad con una amplia variedad de orígenes de datos.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Ayuda para seleccionar una solución

Con tantas opciones de BI disponibles, podría parecer abrumador determinar qué opción es la mejor. Tenemos una guía en línea disponible para ayudarle. Consulte [Elección de herramientas de Microsoft Business Intelligence (BI) para el análisis y los informes](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting).
  
### <a name="what-if-i-dont-upgrade-now"></a>¿Qué ocurre si no actualo ahora?

Puede optar por no actualizar inmediatamente. Los servidores y aplicaciones existentes seguirán ejecutándose. Pero no recibirá más actualizaciones, incluidas las actualizaciones de seguridad, ya que el soporte técnico ha finalizado. Y si algo sale mal con las aplicaciones de servidor, no podrá obtener ayuda del soporte técnico de Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>Cómo planear mi actualización?

Después de explorar las opciones de actualización, el siguiente paso es preparar un plan de actualización. Las secciones siguientes incluyen información y recursos adicionales para ayudar. Tiene cuatro opciones principales, incluidas dos que funcionan tanto en la nube como en el entorno local, y dos que son solo locales:
  
|**Opción**|**¿En la nube o en el entorno local?**|
|:-----|:-----|
|[Excel con SharePoint Server (local)](#excel-with-sharepoint-server-on-premises) <br/> |Ambas  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Ambas  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Solo en el entorno local  <br/> |
|[Servicios PerformancePoint](#use-performancepoint-services-on-premises) <br/> |Solo en el entorno local  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Uso de Excel (en la nube o en el entorno local)

Con Excel, que también se conoce como *Excel Services* en SharePoint Server, puede ver y usar libros en una ventana del explorador, incluso si Excel no está instalado en el equipo. Puede usar Excel para crear informes, cuadros de mandos y paneles. A continuación, comparta los libros con otros usuarios, que pueden usar Excel en un explorador, independientemente de si usan SharePoint Online como parte de Microsoft 365 o SharePoint Server local. Puede usar datos almacenados en el entorno local o en la nube, lo que le permite usar una amplia variedad de orígenes de datos.
  
En la tabla siguiente se comparan las principales ventajas del uso de Excel con Microsoft 365 con el uso de Excel con SharePoint Server. A continuación se muestra más información.
  
|**Excel con Microsoft 365 (en la nube)**|**Excel con SharePoint Server (local)**|
|:-----|:-----|
|**Obtiene la versión más reciente y más grande de Excel**. Con Microsoft 365, obtiene la versión más reciente de Excel, que incluye nuevos y eficaces tipos de gráficos, la capacidad de crear gráficos y tablas de forma rápida y sencilla, y compatibilidad con más orígenes de datos. <br/> <br/> **La configuración es mucho más sencilla**. Excel se incluye con Microsoft 365 para empresas, por lo que no hay ningún trabajo pesado por su parte. Regístrese e inicie sesión, y estará en funcionamiento de forma más rápida y eficaz que si actualiza los servidores locales. <br/> <br/> **Personas tener acceso a sus libros en todas partes**. Personas puede ver de forma segura los libros desde cualquier lugar, usando su computadora, teléfono inteligente y tableta. <br/> <br/> **¡Hay más!** Consulte [Funcionalidades de BI en Excel y Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Administra la configuración global**. Como administrador de SharePoint, puede especificar la configuración global, como la seguridad, el equilibrio de carga, la administración de sesiones, el almacenamiento en caché de libros y las conexiones de datos externos. <br/> <br/> **Puede usar Excel Services con PerformancePoint Services**. Puede configurar Excel Services y PerformancePoint Services como parte de la instalación de SharePoint Server e incluir informes de Excel Services en los paneles de PerformancePoint. <br/> <br/> **¡Hay más!** Vea [Inteligencia empresarial en Excel y Excel Services (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel con Microsoft 365 (en la nube)

Si se traslada a Microsoft 365, tendrá los servicios y aplicaciones más actualizados, incluidos los Excel 2016. PerformancePoint Services no está disponible en Microsoft 365, por lo que reemplazará el contenido del panel de PerformancePoint por libros de Excel u otros informes. La buena noticia es que Excel 2016 tiene muchos tipos de gráficos nuevos y es más fácil que nunca crear paneles impresionantes en Excel. Y las nuevas características se agregan con regularidad. Para obtener más información, consulta [Novedades de Excel 2016 para Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Además, si compra 50 puestos o más de Microsoft 365, el equipo de Microsoft FastTrack puede ayudarle a configurarse. Para más información, visite [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365).
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel con SharePoint Server (local)

Si actualiza a una versión más reciente de SharePoint, puede usar Excel con Excel Services o en un explorador, como se indica a continuación:
  
- Excel Services en SharePoint Server 2010
    
- Servicios de Excel en SharePoint Server 2013
    
- Excel, que forma parte de Office Online Server, se instala por separado de SharePoint Server 2016
    
También puede configurar PerformancePoint Services en la nueva versión de SharePoint Server y usarlo junto con Excel.
  
Para obtener más información sobre las opciones de actualización de [SharePoint, consulte Hoja de ruta de fin de soporte técnico de SharePoint Server 2007](sharepoint-2007-end-of-support.md).
  
Para más información sobre Excel Services, consulte [introducción a Excel Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Uso de Power BI (en la nube o en el entorno local)

Power BI es un conjunto de herramientas de análisis empresarial para analizar datos y compartir información. Con Power BI, puede usar orígenes de datos locales o en línea para crear informes y paneles interactivos. Personas puede ver y usar los informes y paneles en sus equipos o dispositivos móviles.
  
Power BI no forma parte de Microsoft 365 o SharePoint Server. Se trata de una oferta independiente que incluye Power BI Desktop, puertas de enlace de Power BI y el servicio Power BI. Power BI también se integra con SharePoint Online. Puede empezar a trabajar con Power BI de forma gratuita. En función del uso de datos y las necesidades empresariales, puede actualizar más adelante a Power BI Pro con Microsoft 365 E5. Para más información, consulte [¿Qué es Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Uso de Reporting Services (local)

SQL Server Reporting Services proporciona una solución de informes sólida. Puede configurar Reporting Services en modo nativo o en modo integrado de SharePoint. Puede usar varias herramientas diferentes para crear informes, como Diseñador de informes, Report Builder y Power View. Con la versión más reciente de SQL Server, también puede usar SQL Server Publicador de informes móviles para entregar informes que se escalan a cualquier tamaño de pantalla. Esto permite a los espectadores consumir informes en sus dispositivos móviles. Para obtener más información, consulte [SQL Server Reporting Services (SSRS): Creación, implementación y administración de informes paginados y móviles](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports).
  
### <a name="use-performancepoint-services-on-premises"></a>Uso de PerformancePoint Services (local)

PerformancePoint Server 2007 se vendió por separado de SharePoint Server 2007. A partir de SharePoint Server 2010, PerformancePoint Services es una aplicación de servicio en SharePoint Server. Por lo tanto, no es necesario comprar licencias de servidor o hardware independientes para usar PerformancePoint Services.
  
Para pasar de PerformancePoint Server 2007 a PerformancePoint Services, vaya a una versión más reciente de SharePoint Server y configure PerformancePoint Services. La versión de SharePoint Server a la que se mueve determina si puede importar el contenido del panel existente de PerformancePoint Server 2007 a PerformancePoint Services.
  
- Si actualiza a SharePoint Server 2010, puede importar el contenido del panel de PerformancePoint de PerformancePoint Server 2007 a PerformancePoint Services en SharePoint Server 2010. Para obtener más información, vea [Asistente para importación: PerformancePoint Server contenido de 2007 a SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14)).
    
- Si se mueve a SharePoint Server 2013 o SharePoint Server 2016, lo más probable es que tenga que crear nuevo contenido de panel (orígenes de datos, informes, cuadros de mandos y páginas de panel).
    
Para empezar a trabajar en el plan de actualización de PerformancePoint Services, consulte los siguientes recursos:
  
- [Hoja de ruta de finalización del soporte técnico de SharePoint Server 2007](sharepoint-2007-end-of-support.md)
    
- Cuando sepa a qué versión de SharePoint va a migrar, consulte el artículo correspondiente para PerformancePoint Services:
    
  - [Planeación de PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [introducción a PerformancePoint Services en SharePoint Server 2013](/sharepoint/administration/performancepoint-services-overview)
    
  - [Información general sobre PerformancePoint Services en SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
Al actualizar a PerformancePoint Services, se obtienen varias características y mejoras nuevas. PerformancePoint Services ofrece cuadros de mandos mejorados; nuevas visualizaciones, como el informe Descomposición del árbol y detalles de KPI, más tipos de gráficos, mejores funcionalidades de filtrado de Time Intelligence y un mejor cumplimiento de accesibilidad. Para obtener más información, vea [Novedades de PerformancePoint Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>¿Dónde puedo obtener ayuda con mi actualización?

Tanto si actualiza localmente como si se mueve a Microsoft 365, se recomienda trabajar con un asociado de Microsoft. Un asociado cualificado puede ayudarle a identificar la solución que mejor se adapte a sus necesidades empresariales y a ayudar con la implementación. Visite el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) y use los filtros de búsqueda para buscar un proveedor de soluciones.
  
## <a name="related-topics"></a>Temas relacionados

[Recursos para ayudarle a actualizar desde servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md)