---
title: Plan de fin del soporte técnico de PerformancePoint Server 2007
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007, ProClarity y SharePoint Server 2007 han llegado al final de la compatibilidad. Lea este artículo para ayudar a planear la actualización de la solución de BI.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927341"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de PerformancePoint Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Office servidores y aplicaciones de 2007 han llegado a su fin de soporte técnico, incluidos los servidores y aplicaciones que podría usar como parte de las soluciones de inteligencia empresarial (BI). En la tabla siguiente se enumeran las aplicaciones de BI que se ven afectadas:
  
|**Aplicaciones de Microsoft BI**|**Fecha de finalización del soporte técnico**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 de julio de 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 de octubre de 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 de enero de 2018  <br/> |
   
Para obtener más información, vea [Resources to help you upgrade from Office 2007 servers and clients](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

Al igual que la mayoría de los productos de Microsoft, PerformancePoint Server 2007 SP3, software ProClarity y SharePoint Server 2007 SP3, tienen un ciclo de vida de soporte técnico, durante el cual Microsoft proporciona nuevas características, correcciones de errores y actualizaciones de seguridad. El ciclo de vida de un producto suele durar 10 años desde la versión inicial del producto. El final de ese ciclo de vida se conoce como el final del soporte técnico del producto. Como ProClarity, PerformancePoint Server y SharePoint Server 2007 han llegado a su fin de soporte técnico, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas detectados y que pueden afectar a la estabilidad y facilidad de uso de los servidores.
    
- Correcciones de seguridad para vulnerabilidades que se detectan y que pueden hacer que los servidores o aplicaciones sean vulnerables a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de ProClarity, SharePoint Server 2007 SP3 y PerformancePoint Server 2007 SP3 seguirán funcionando aunque la compatibilidad haya finalizado. Sin embargo, se recomienda encarecidamente migrar desde estas aplicaciones tan pronto como sea posible.
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Ha habido muchos cambios en las aplicaciones de Microsoft BI desde 2007 y tiene varias opciones que tener en cuenta, como se resume en la tabla siguiente.
  
|**Si estaba usando este ...**|**Explore estas opciones ...**|**Y ten esto en cuenta ...**|
|:-----|:-----|:-----|
| PerformancePoint Server de análisis de supervisión de 2007, &amp; incluidas:<br/>- Servidor de supervisión de PerformancePoint <br/>- Diseñador de paneles de PerformancePoint<br/>- Visor de paneles para SharePoint Services (se usa para representar paneles de PerformancePoint, cuadros de mandos e informes)<br/> |**Excel con Excel en un explorador** (en la nube o local). Para obtener información general, vea [Funcionalidades de BI en Excel y Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (en la nube o local). Para obtener información general, vea [What is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (local). Para obtener información general, [vea SQL Server Reporting Services (SSRS): Crear, implementar y administrar informes móviles y paginados.](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports) <br/><br/> **PerformancePoint Services** (local). Para obtener información general, vea [Novedades de PerformancePoint Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)) <br/> |Excel está disponible como una solución en línea (basada en la nube) o local. Muchas necesidades de informes y paneles se pueden satisfacer con Excel.  <br/><br/> Power BI está disponible como una solución local o en línea. Power BI no se incluye en Microsoft 365. Pero puedes empezar a usar Power BI de forma gratuita. Más adelante, según el uso de datos y las necesidades empresariales, puede actualizar a Power BI Pro con Microsoft 365 E5.<br/> <br/> Reporting Services y PerformancePoint Services son soluciones locales. <br/><br/> PerformancePoint Services está disponible en SharePoint Server 2010, SharePoint Server 2013 y SharePoint Server 2016. <br/> <br/> Algunas características y tipos de informes que estaban disponibles en PerformancePoint Server 2007 no están disponibles en Excel, Power BI, Reporting Services o PerformancePoint Services. Revise las características disponibles para determinar la mejor solución para sus necesidades empresariales. <br/> |
| Software ProClarity, que incluye:<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- Visor de SharePoint ProClarity<br/> |**Trabaje con un partner de Microsoft** para identificar una solución que mejor se adapte a sus necesidades. Visite el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> También puede considerar el uso de Excel con Excel en un explorador, Power BI, SQL Server Reporting Services o PerformancePoint Services.  <br/> |Varias, pero no todas las características del software ProClarity, están disponibles en otras ofertas de Microsoft, como Excel, Power BI, Reporting Services y PerformancePoint Services.  <br/> |
|SharePoint KPI de Server 2007 (también denominados KPI de MOSS)  <br/> |**Excel con Excel Services**. Para obtener información general, vea [Business intelligence in Excel and Excel Services (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |Los KPI de MOSS creados con SharePoint Server 2007 se pueden usar en SharePoint Server 2010, SharePoint Server 2013 y SharePoint Server 2016. Pero no puede crear nuevos KPI de MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (en la nube o local). Para obtener información general, vea [Funcionalidades de BI en Excel y Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (en la nube o local). Para obtener información general, vea [What is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Tanto Excel como Power BI soluciones locales y basadas en la nube de su organización, con compatibilidad con una amplia variedad de orígenes de datos.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Ayuda para seleccionar una solución

Con tantas opciones de BI disponibles, puede parecer abrumador determinar cuál es la mejor opción. Tenemos una guía en línea disponible para ayudarle. Vea [Elegir herramientas de Microsoft Business Intelligence (BI) para análisis e informes.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>¿Qué ocurre si no actualizo ahora?

Puede elegir no actualizar inmediatamente. Los servidores y aplicaciones existentes seguirán en ejecución. Pero no recibirá más actualizaciones, incluidas las actualizaciones de seguridad, ya que el soporte técnico ha finalizado. Y si algo sale mal con las aplicaciones de servidor, no podrá obtener ayuda del soporte técnico de Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>¿Cómo planeo mi actualización?

Después de explorar las opciones de actualización, el siguiente paso es preparar un plan de actualización. Las secciones siguientes incluyen información y recursos adicionales para ayudar. Tiene cuatro opciones principales, incluidas dos que funcionan en la nube o local, y dos que son solo locales:
  
|**Opción**|**¿En la nube o local?**|
|:-----|:-----|
|[Excel con SharePoint server (local)](#excel-with-sharepoint-server-on-premises) <br/> |Ambas  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Ambas  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Solo local  <br/> |
|[Servicios PerformancePoint](#use-performancepoint-services-on-premises) <br/> |Solo local  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Use Excel (en la nube o local)

Con Excel, que también se conoce como *Excel Services* en SharePoint Server, puede ver y usar libros en una ventana del explorador, incluso si Excel no está instalado en el equipo. Puede usar Excel para crear informes, cuadros de mandos y paneles. A continuación, comparta los libros con otros usuarios, que pueden usar Excel en un explorador, ya sea que usen SharePoint Online como parte de Microsoft 365 o SharePoint Server local. Puede usar datos almacenados localmente o en la nube, lo que le permite usar una amplia variedad de orígenes de datos.
  
En la tabla siguiente se comparan las ventajas clave de usar Excel con Microsoft 365 usar Excel con SharePoint Server. A continuación se proporciona más información.
  
|**Excel con Microsoft 365 (en la nube)**|**Excel con SharePoint server (local)**|
|:-----|:-----|
|**Obtiene la versión más reciente y más grande de Excel**. Con Microsoft 365, obtiene la versión más reciente de Excel, que incluye nuevos y eficaces tipos de gráficos, la capacidad de crear gráficos y tablas de forma rápida y sencilla, y la compatibilidad con más orígenes de datos. <br/> <br/> **El programa de instalación es mucho más sencillo.** Excel se incluye con Microsoft 365 para empresas, por lo que no hay trabajo pesado por su parte. Regístrese e inicie sesión y estará en funcionamiento más rápido y eficientemente que si actualiza los servidores locales. <br/> <br/> **Las personas tienen acceso en todas partes a sus libros**. Las personas pueden ver libros de forma segura desde cualquier lugar, con su equipo, teléfono inteligente y tableta. <br/> <br/> **¡Hay más!** Vea [Funcionalidades de BI en Excel y Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Puede administrar la configuración global**. Como administrador SharePoint, puede especificar la configuración global, como la seguridad, el equilibrio de carga, la administración de sesiones, el almacenamiento en caché del libro y las conexiones de datos externos. <br/> <br/> **Puede usar Excel Services con PerformancePoint Services**. Puede configurar Excel Services y PerformancePoint Services como parte de la instalación de SharePoint Server e incluir informes Excel Services en los paneles de PerformancePoint. <br/> <br/> **¡Hay más!** Vea [Business intelligence in Excel and Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel con Microsoft 365 (en la nube)

Si pasa a Microsoft 365, tendrá los servicios y aplicaciones más actualizados, incluidos Excel 2016. PerformancePoint Services no está disponible en Microsoft 365, por lo que reemplazará el contenido del panel de PerformancePoint por Excel libros u otros informes. La buena noticia es que Excel 2016 tiene muchos tipos de gráficos nuevos y es más fácil que nunca crear paneles impresionantes en Excel. Y las nuevas características se agregan con regularidad. Para obtener más información, vea [What's New in Excel 2016 for Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Además, si compra 50 puestos o más de Microsoft 365, el equipo de Microsoft FastTrack puede ayudarle a configurarse. Para obtener más información, visite [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365).
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel con SharePoint server (local)

Si actualiza a una versión más reciente de SharePoint, puede usar Excel con Excel Services o en un explorador, como se muestra a continuación:
  
- Excel Services en SharePoint Server 2010
    
- Servicios de Excel en SharePoint Server 2013
    
- Excel, que forma parte de Office Online Server, se instala por separado de SharePoint Server 2016
    
También puede configurar PerformancePoint Services en la nueva versión de SharePoint Server y usarla junto con Excel.
  
Para obtener más información acerca de las SharePoint de actualización, consulte [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md).
  
Para obtener más información Excel Services, [vea Excel Services overview (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Usar Power BI (en la nube o local)

Power BI es un conjunto de herramientas de análisis empresarial para analizar datos y compartir información. Con Power BI, puede usar orígenes de datos locales o en línea para crear informes y paneles interactivos. Los usuarios pueden ver y usar sus informes y paneles en sus equipos o dispositivos móviles.
  
Power BI no forma parte de Microsoft 365 o SharePoint server. Se trata de una oferta independiente que incluye Power BI Desktop, Power BI puertas de enlace y el servicio Power BI cliente. Power BI también se integra con SharePoint Online. Puede empezar a usar Power BI de forma gratuita. En función del uso de datos y las necesidades empresariales, más adelante puede actualizar a Power BI Pro con Microsoft 365 E5. Para obtener más información, vea [What is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Usar Reporting Services (local)

SQL Server Reporting Services proporciona una solución de informes sólida. Puede configurar Reporting Services en modo nativo o SharePoint modo integrado. Puede usar varias herramientas diferentes para crear informes, incluidos el Diseñador de informes, Report Builder y Power View. Con la última versión de SQL Server, también puedes usar SQL Server mobile report Publisher para entregar informes que escalan a cualquier tamaño de pantalla. Esto permite a los visores consumir informes en sus dispositivos móviles. Para obtener más información, [vea SQL Server Reporting Services (SSRS): Crear, implementar y administrar informes](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)móviles y paginados .
  
### <a name="use-performancepoint-services-on-premises"></a>Usar PerformancePoint Services (local)

PerformancePoint Server 2007 se vendió por separado de SharePoint Server 2007. A partir de SharePoint Server 2010, PerformancePoint Services es una aplicación de servicio en SharePoint Server. Por lo tanto, no es necesario comprar licencias de servidor o hardware independientes para usar PerformancePoint Services.
  
Para pasar de PerformancePoint Server 2007 a PerformancePoint Services, pase a una versión más reciente de SharePoint Server y configure PerformancePoint Services. La versión de SharePoint Server a la que se mueve determina si puede importar el contenido del panel existente de PerformancePoint Server 2007 a PerformancePoint Services.
  
- Si actualiza a SharePoint Server 2010, puede importar el contenido del panel de PerformancePoint de PerformancePoint Server 2007 a PerformancePoint Services en SharePoint Server 2010. Para obtener más información, vea [Import Wizard: PerformancePoint Server 2007 content to SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14)).
    
- Si pasa a SharePoint Server 2013 o SharePoint Server 2016, lo más probable es que necesite crear nuevo contenido de panel (orígenes de datos, informes, cuadros de mandos y páginas de panel).
    
Para empezar a usar el plan PerformancePoint Services actualización, vea los siguientes recursos:
  
- [SharePoint Guía básica de fin de soporte técnico de Server 2007](sharepoint-2007-end-of-support.md)
    
- Cuando sepa a qué versión SharePoint a la que se está moviendo, consulte el artículo correspondiente para PerformancePoint Services:
    
  - [Planeación de PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [PerformancePoint Services información general SharePoint Server 2013](/sharepoint/administration/performancepoint-services-overview)
    
  - [Información general sobre PerformancePoint Services en SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
Al actualizar a PerformancePoint Services, obtiene varias características y mejoras nuevas. PerformancePoint Services ofrece cuadros de mandos mejorados; nuevas visualizaciones, como el informe Decomposition Tree y KPI Details; más tipos de gráficos; mejores capacidades de filtrado de inteligencia de tiempo; y mejora del cumplimiento de la accesibilidad. Para obtener más información, vea [Novedades de PerformancePoint Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>¿Dónde puedo obtener ayuda con mi actualización?

Tanto si actualiza localmente como si se mueve a Microsoft 365, le recomendamos que trabaje con un partner de Microsoft. Un partner cualificado puede ayudarle a identificar la solución que mejor se adapte a sus necesidades empresariales y le ayudará con la implementación. Visite el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249)y use los filtros de búsqueda para buscar un proveedor de soluciones.
  
## <a name="related-topics"></a>Temas relacionados

[Recursos para ayudarle a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)