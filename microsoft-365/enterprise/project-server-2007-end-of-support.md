---
title: Plan de fin del soporte técnico de Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: El 10 de octubre de 2017, se finalizó la compatibilidad con Project Server 2007, Project Portfolio Server y Project 2007. Use este artículo para planear la actualización ahora.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519804"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Project Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El soporte técnico finalizó para los servidores y aplicaciones de Office 2007 en el 2017 y debe tener en cuenta los planes para la migración. Si actualmente usa Project Server 2007 y productos relacionados, tenga en cuenta las siguientes fechas de finalización de soporte:
  
|**Producto**|**Fecha de finalización del soporte técnico**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Proyecto 2007 estándar  <br/> |10 de octubre de 2017  <br/> |
|Proyecto 2007 Professional  <br/> |10 de octubre de 2017  <br/> |
   
Para obtener más información acerca de los servidores de Office 2007 que alcanzan la jubilación, consulte [upgrade from office 2007 Servers and Client Products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa el *fin de soporte* ?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico en el que obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar diez años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Dado que Project Server 2007 ha llegado al final del soporte técnico el 10 de octubre de 2017, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden surgir.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y la usabilidad del servidor.
    
- Revisiones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
    
- Las actualizaciones de zona horaria.
    
La instalación de Project Server 2007 seguirá ejecutándose después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente que migre desde Project Server 2007 tan pronto como sea práctico.
  
## <a name="what-are-my-options"></a>¿Qué opciones tengo?

Si está usando Project Server 2007, debe explorar las opciones de migración, que son:
  
- Migrar a Project online
    
- Migrar a una versión local más reciente de Project Server (preferiblemente Project Server 2016)
    
|**Por qué preferiría migrar a Project online**|**Por qué preferiría migrar a Project Server 2016**|
|:-----|:-----|
| Tengo usuarios móviles.  <br/> <br/>Los costos de migración son una preocupación importante (hardware, software, horas y esfuerzo de implementación). <br/><br/>  Después de la migración, los costos de mantenimiento de mi entorno son una preocupación importante (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).  <br/> | Las reglas de negocios delimitan el funcionamiento de mi empresa en la nube.<br/><br/>  Necesito el control de las actualizaciones de mi entorno.  |
   
> [!NOTE]
> Para obtener más información acerca de las opciones para mover desde los servidores de Office 2007, vea [recursos para ayudarle a actualizar desde office 2007 servidores y clientes](upgrade-from-office-2007-servers-and-products.md). Tenga en cuenta que Project Server no admite una configuración híbrida, ya que Project Server y Project online no pueden compartir el mismo grupo de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Consideraciones importantes al migrar desde Project Server 2007

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2007:
  
- **Obtener ayuda de un socio de Microsoft** : la actualización desde Project Server 2007 puede ser compleja y requiere una mayor preparación y planeación. Puede que sea especialmente difícil si no es la persona que configuró Project Server 2007 en un principio. Afortunadamente, hay asociados de Microsoft que pueden ayudarle, tanto si planea migrar a Project Server 2016 como a Project online. Busque un socio de Microsoft para ayudarle con la migración en el [centro de Partners de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249). Busque el término  *Gold Project Management y la administración de cartera* para ver una lista de todos los socios de Microsoft que tienen experiencia en Project. 
    
- **Planeación de las personalizaciones** : muchas de las personalizaciones realizadas en el entorno de Project Server 2007 podrían no funcionar al migrar a project Server 2016 o Project online. Existen diferencias significativas en la arquitectura de Project Server entre versiones. Los sistemas operativos, los servidores de bases de datos y los exploradores Web de cliente que se admiten también son distintos. Planee cómo probar o volver a crear las personalizaciones para el nuevo entorno. La planeación también proporciona una buena oportunidad para tener en cuenta si todavía es necesaria cada personalización. Para más información, vea [Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- La planeación, ejecución y pruebas de actualización del **tiempo y la paciencia** le ocuparán tiempo y esfuerzo, especialmente si actualiza a Project Server 2016. Por ejemplo, si migra de Project Server 2007 a Project Server 2016, primero debe migrar a Project Server 2010, comprobar los datos y, a continuación, hacer lo mismo al migrar a cada versión sucesiva. Es posible que quiera consultar con un socio de Microsoft para obtener estimaciones del tiempo que tardará y su coste.
    
## <a name="migrate-to-project-online"></a>Migrar a Project online

Si elige migrar de Project Server 2007 a Project online, puede hacer lo siguiente para migrar manualmente los datos del plan del proyecto:
  
1. Guarde los planes del proyecto de Project Server 2003 en formato. MPP.
    
2. En Project Professional 2013, Project Professional 2016 o el cliente de escritorio de Project online, abra cada archivo. MPP y, a continuación, guárdelo y publíquelo en Project online.
    
Puede crear manualmente la configuración de Microsoft Project Web App (PWA) en Project online. Por ejemplo, vuelva a crear los campos personalizados o los calendarios de empresa que sean necesarios. Los socios de Microsoft también pueden ayudarle con este proceso.
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Cómo configurar y usar Project online <br/> |
|[Descripciones del servicio Project online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Información acerca de los diferentes planes de Project online que tiene a su disposición <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar a una versión local más reciente de Project Server

Creemos que se obtiene el mejor valor y la mejor experiencia del usuario al migrar a Project online. Pero también sabemos que algunas organizaciones necesitan mantener los datos de Project en un entorno local. Si opta por mantener los datos de proyecto locales, puede migrar el entorno de Project Server 2007 a Project Server 2010, Project Server 2013 o Project Server 2016.
  
Si no puede migrar a Project online, le recomendamos que migre a Project Server 2016. Project Server 2016 incluye todas las características de versiones anteriores de Project Server. Se asemeja más a la experiencia disponible en Project online, aunque algunas características solo están disponibles en Project online.
  
Después de cada migración, debe comprobar que los datos se han migrado correctamente.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>¿Cómo migro a Project Server 2016?

Las diferencias de arquitectura entre Project Server 2007 y Project Server 2016 impiden una ruta de migración directa. Por lo tanto, tiene que migrar los datos de Project Server 2007 a cada una de las versiones sucesivas de Project Server hasta llegar a Project Server 2016.
  
Siga estos pasos para Project Server 2016:
  
1. Migrar de Project Server 2007 a Project Server 2010.
    
2. Migrar desde Project atender 2010 a Project Server 2013.
    
3. Migrar de Project Server 2013 a Project Server 2016.
    
Después de cada migración, asegúrese de que los datos se han migrado correctamente.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Paso 1: migrar de Project Server 2007 a Project Server 2010

Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010, consulte [Upgrade to Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a la actualización de Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Una vista de alto nivel de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010 <br/> |
|[Planeación de la actualización a Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Consideraciones de planeación al actualizar de Project Server 2007 a Project Server 2010, incluidos los requisitos del sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>¿Cómo se realiza la actualización?

Para obtener más información, vea [actualizar a Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Pero es importante comprender que hay dos métodos distintos que puede usar para actualizar:
  
- **Actualización de base de datos adjunta:** Este método solo actualiza el contenido de su entorno, no los valores de configuración. Es necesario si va a actualizar desde Office Project Server 2007 implementado en hardware que solo admite un sistema operativo de servidor de 32 bits. Hay dos tipos de métodos de actualización de base de datos adjunta:
    
  - ***Actualización completa* de base** de datos adjunta: migra los datos del proyecto almacenados en las bases de datos de Office Project Server 2007, además de los datos del sitio de Microsoft Project Web App almacenados en una base de datos de contenido de SharePoint.
    
  - ***Actualización principal* de base de datos adjunta** : migra solo los datos del proyecto almacenados en las bases de datos de Project Server.
    
- **Actualización local**: los datos de configuración de la granja de servidores y todo el contenido de la granja de servidores se actualizan en el hardware existente en un orden fijo. Cuando se inicia el proceso de actualización, el programa de instalación desconecta toda la granja de servidores. Los sitios web y los sitios de Microsoft Project Web App no estarán disponibles hasta que finalice la actualización y, a continuación, el programa de instalación reiniciará el servidor. Después de comenzar una actualización inmediata, no puede pausar la actualización ni volver a la versión anterior. Es mejor crear una imagen reflejada de su entorno de producción y realizar la actualización en el lugar a este entorno, no en su entorno de producción. 
    
Recursos adicionales:
  
- [Superflow para la actualización de Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migración de Project Server 2007 a Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Consideraciones sobre la actualización de elementos web de Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Kit de desarrollo de software (SDK) de Project](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Paso 2: migrar a Project Server 2013

Después de comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar a Project Server 2013.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013, consulte [Upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Información general sobre el proceso de actualización de Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Información general de lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013  <br/> |
|[Planeación de la actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Consideraciones de planeación al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Cosas que debe saber sobre la actualización a esta versión

[What's New in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) describe cambios importantes para la actualización de esta versión. Los más destacables son: 
  
- No hay una actualización inmediata a Project Server 2013. El método de base de datos adjunta es el único método admitido para actualizar de Project Server 2010 a Project Server 2013.
    
- El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una sola base de datos de Project Web App.
    
- En las versiones de 2013, SharePoint Server y Project Server cambiaron a la autenticación basada en notificaciones. Si está usando la autenticación clásica, debe tener en cuenta este factor para la actualización. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Recursos adicionales:
  
- [Introducción al proceso de actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagrama del proceso de actualización de Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [La gran consolidación de la base de datos, la migración de Project Server 2010 a 2013 en 8 pasos sencillos](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Paso 3: migrar a Project Server 2016

Después de comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar a Project Server 2016.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016, consulte [Upgrade to Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción al proceso de actualización a Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Información general de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016 <br/> |
|[Planeación de la actualización a Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Consideraciones de planeación para actualizar de Project Server 2013 a Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Cosas que debe saber sobre la actualización a esta versión

Lo [que debe saber sobre la actualización de Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) le indica algunos cambios importantes para la actualización de esta versión, que incluyen:
  
- Al crear su entorno de Project Server 2016 en el que va a migrar los datos de Project Server 2013, los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, vea [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Los planes de recursos están en desuso en Project Server 2016. Los planes de recursos de Project Server 2013 se migrarán a las negociaciones de recursos en Project Server 2016 y Project online. Para obtener más información, vea [información general: negociaciones de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrar desde el servidor de cartera 2007

Project Portfolio Server 2007 se usó con Project Server 2007 para la estrategia de cartera, la priorización y la optimización. No se han creado versiones adicionales del servidor de la cartera de proyectos después de esta versión. Sin embargo, las características de administración de cartera están disponibles en Project Server 2016 y la versión Premium de Project online. Pero los datos de Project Portfolio Server 2007 no se pueden migrar a ninguno de los dos. Se tendrán que volver a crear los datos, como los impulsores de negocios.
  
Otros recursos:
  
- [Descripciones del servicio Project online:](https://go.microsoft.com/fwlink/p/?linkid=841280) Vea las características de administración de cartera incluidas en Project Server 2016 y Project online Premium.
    
- [Guía de migración de Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Temas relacionados

[Mapa de ruta de fin de soporte para SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Recursos que le ayudarán a actualizar desde los servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
