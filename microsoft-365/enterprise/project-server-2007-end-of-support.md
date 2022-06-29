---
title: Plan de fin del soporte técnico de Project Server 2007
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: El 10 de octubre de 2017, finalizó la compatibilidad con Project Server 2007, Project Portfolio Server y Project 2007. Use este artículo para planear la actualización ahora.
ms.openlocfilehash: c072daf811ec8e175c830aaa95b2163c80fa2b6f
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66487324"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Project Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El soporte técnico finalizó en 2017 para servidores y aplicaciones de Office 2007 y debe tener en cuenta los planes de migración. Si actualmente usa Project Server 2007 y productos relacionados, tenga en cuenta las siguientes fechas de finalización de soporte técnico:
  
|**Producto**|**Fecha de finalización del soporte técnico**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Project 2007 Standard  <br/> |10 de octubre de 2017  <br/> |
|Project 2007 Professional  <br/> |10 de octubre de 2017  <br/> |
   
Para obtener más información sobre los servidores de Office 2007 que llegan a la retirada, consulte [Actualización desde servidores y productos cliente de Office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Dado que Project Server 2007 llegó a su fin de soporte técnico el 10 de octubre de 2017, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de Project Server 2007 continuará ejecutándose después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2007 tan pronto como sea práctico.
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Si usa Project Server 2007, debe explorar las opciones de migración, que son:
  
- Migración a Project Online
    
- Migración a una versión local más reciente de Project Server (preferiblemente Project Server 2016)
    
|**¿Por qué preferiría migrar a Project Online**|**¿Por qué preferiría migrar a Project Server 2016**|
|:-----|:-----|
| Tengo usuarios móviles.  <br/> <br/>Los costos de migración son una preocupación importante (hardware, software, horas y esfuerzo para implementar). <br/><br/>  Después de la migración, los costos para mantener mi entorno son una preocupación importante (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).  <br/> | Las reglas de negocios me impiden operar mi negocio en la nube.<br/><br/>  Necesito el control de las actualizaciones de mi entorno.  |
   
> [!NOTE]
> Para obtener más información sobre las opciones para moverse desde los servidores de Office 2007, vea [Recursos para ayudarle a actualizar desde clientes y servidores de Office 2007](upgrade-from-office-2007-servers-and-products.md). Tenga en cuenta que Project Server no admite una configuración híbrida, ya que Project Server y Project Online no pueden compartir el mismo grupo de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Consideraciones importantes al migrar desde Project Server 2007

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2007:
  
- **Obtener ayuda de un partner de Microsoft** : la actualización desde Project Server 2007 puede ser difícil y requiere mucha preparación y planeamiento. Podría ser especialmente difícil si no fuera la persona que configuró Project Server 2007 originalmente. Afortunadamente, hay asociados de Microsoft que pueden ayudar, ya sea que planee migrar a Project Server 2016 o a Project Online. Busque un partner de Microsoft que le ayude con la migración en el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249). Busque el término  *Gold Project and Portfolio Management* para ver una lista de todos los asociados de Microsoft que tienen experiencia en Project. 
    
- **Planear las personalizaciones**: es posible que muchas de las personalizaciones realizadas en el entorno de Project Server 2007 no funcionen al migrar a Project Server 2016 o Project Online. Hay diferencias significativas en la arquitectura de Project Server entre versiones. Los sistemas operativos necesarios, los servidores de base de datos y los exploradores web cliente que se admiten también difieren. Planee cómo probar o recompilar las personalizaciones para el nuevo entorno. La planificación también proporciona una buena oportunidad para considerar si cada personalización sigue siendo necesaria. Para más información, vea [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013). 
    
- **Tiempo y paciencia**: el planeamiento, la ejecución y las pruebas de actualización llevarán tiempo y esfuerzo, especialmente si actualiza a Project Server 2016. Por ejemplo, si migra de Project Server 2007 a Project Server 2016, primero debe migrar a Project Server 2010, comprobar los datos y, a continuación, hacer lo mismo al migrar a cada versión sucesiva. Es posible que quiera consultar con un partner de Microsoft para obtener estimaciones del tiempo que tardará y de lo que costará.
    
## <a name="migrate-to-project-online"></a>Migración a Project Online

Si decide migrar de Project Server 2007 a Project Online, puede hacer lo siguiente para migrar manualmente los datos del plan de proyecto:
  
1. Guarde los planes de proyecto de Project Server 2003 en formato .mpp.
    
2. En Project Profesional 2013, Project Profesional 2016 o el cliente de escritorio de Project Online, abra cada archivo .mpp y, a continuación, guárdelo y publíquelo en Project Online.
    
Puede crear manualmente la configuración de Microsoft Project Web App (PWA) en Project Online. Por ejemplo, vuelva a crear los campos personalizados o calendarios empresariales necesarios. Los asociados de Microsoft también pueden ayudar con este proceso.
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Configuración y uso de Project Online <br/> |
|[descripciones del servicio Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Información sobre los diferentes planes de Project Online que están disponibles para usted <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migración a una versión local más reciente de Project Server

Creemos firmemente que obtiene el mejor valor y la experiencia del usuario mediante la migración a Project Online. Pero también entendemos que algunas organizaciones necesitan mantener los datos del proyecto en un entorno local. Si decide mantener los datos del proyecto en el entorno local, puede migrar el entorno de Project Server 2007 a Project Server 2010, Project Server 2013 o Project Server 2016.
  
Si no puede migrar a Project Online, se recomienda migrar a Project Server 2016. Project Server 2016 incluye todas las características de versiones anteriores de Project Server. Coincide con la experiencia disponible con Project Online, aunque algunas características solo están disponibles en Project Online.
  
Después de cada migración, debe comprobar que los datos se migraron correctamente.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Cómo migrar a Project Server 2016?

Las diferencias arquitectónicas entre Project Server 2007 y Project Server 2016 impiden una ruta de migración directa. Por lo tanto, debe migrar los datos de Project Server 2007 a cada versión sucesiva de Project Server hasta que llegue a Project Server 2016.
  
Siga estos pasos para Project Server 2016:
  
1. Migre de Project Server 2007 a Project Server 2010.
    
2. Migre de Project Serve 2010 a Project Server 2013.
    
3. Migre de Project Server 2013 a Project Server 2016.
    
Después de cada migración, asegúrese de que los datos se migraron correctamente.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Paso 1: Migración de Project Server 2007 a Project Server 2010

Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010, consulte [Actualización a Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a la actualización de Project Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Una vista de alto nivel de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010 <br/> |
|[Planeamiento de la actualización a Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Consideraciones de planeamiento al actualizar de Project Server 2007 a Project Server 2010, incluidos los requisitos del sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Cómo actualización?

Para obtener más información, consulte [Actualización a Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)). Pero es importante comprender que hay dos métodos distintos que puede usar para actualizar:
  
- **Actualización de conexión de base de datos:** Este método solo actualiza el contenido de su entorno, no los valores de configuración. Es necesario si va a actualizar desde Office Project Server 2007 implementado en hardware que solo admite un sistema operativo de servidor de 32 bits. Hay dos tipos de métodos de actualización de conexión de base de datos:
    
  - ***Actualización completa* de conexión a base de datos**: migra los datos del proyecto almacenados en las bases de datos de Office Project Server 2007, además de los datos del sitio de Microsoft Project Web App almacenados en una base de datos de contenido de SharePoint.
    
  - ***Actualización del núcleo* de conexión de base** de datos: migra solo los datos del proyecto almacenados en las bases de datos de Project Server.
    
- **Actualización local**: los datos de configuración de la granja de servidores y todo el contenido de la granja de servidores se actualizan en el hardware existente en un orden fijo. Al iniciar el proceso de actualización, el programa de instalación desconecta toda la granja de servidores. Los sitios web y los sitios de Microsoft Project Web App no están disponibles hasta que finaliza la actualización y, a continuación, el programa de instalación reinicia el servidor. Después de comenzar una actualización local, no puede pausar la actualización ni revertirla a la versión anterior. Es mejor crear una imagen reflejada del entorno de producción y realizar la actualización local a este entorno, no en el entorno de producción. 
    
Recursos adicionales:
  
- [Actualización de SuperFlow para Microsoft Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migración de Project Server 2007 a Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Consideraciones sobre la actualización de elementos web de Project Web App](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Kit de desarrollo de software (SDK) de Project](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Paso 2: Migración a Project Server 2013

Después de comprobar que los datos se migraron correctamente, el siguiente paso es migrar a Project Server 2013.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013, consulte [Actualización a Project Server 2013](/project/upgrade-to-project-server-2016). 
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción al proceso de actualización de Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Información general sobre lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013  <br/> |
|[Planeamiento de la actualización a Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Consideraciones de planeamiento al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Aspectos que debe saber sobre la actualización a esta versión

[Las novedades de la actualización de Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) describen cambios importantes para la actualización de esta versión. Los más notables son: 
  
- No hay ninguna actualización local a Project Server 2013. El método de asociación de base de datos es el único método admitido para actualizar de Project Server 2010 a Project Server 2013.
    
- El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una sola base de datos de Project Web App.
    
- En las versiones de 2013, SharePoint Server y Project Server cambiaron a autenticación basada en notificaciones. Si usa la autenticación clásica, debe tener en cuenta este factor para la actualización. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Recursos adicionales:
  
- [Introducción al proceso de actualización a Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Diagrama del proceso de actualización de Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [La gran consolidación de bases de datos, migración de Project Server 2010 a 2013 en 8 sencillos pasos](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Paso 3: Migración a Project Server 2016

Después de comprobar que los datos se migraron correctamente, el siguiente paso es migrar a Project Server 2016.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016, consulte [Actualización a Project Server 2016](/project/upgrading-to-project-server-2016).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción al proceso de actualización a Project Server 2016](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Información general sobre lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016 <br/> |
|[Planeación de la actualización a Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Consideraciones de planeamiento que se actualizan de Project Server 2013 a Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Aspectos que debe saber sobre la actualización a esta versión

[Las cosas que necesita saber sobre Project Server 2016 actualización](/project/plan-for-upgrade-to-project-server-2016) le indican algunos cambios importantes para la actualización de esta versión, entre los que se incluyen:
  
- Al crear el entorno de Project Server 2016 al que migrará los datos de Project Server 2013, los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, consulte [Implementación de Project Server 2016](/project/deploy-project-server-2016).
    
- Los planes de recursos están en desuso en Project Server 2016. Los planes de recursos de Project Server 2013 se migrarán a Resource Engagements en Project Server 2016 y en Project Online. Consulte [Información general: Interacciones de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obtener más información. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migración desde Portfolio Server 2007

Project Portfolio Server 2007 se usó con Project Server 2007 para la estrategia de cartera, la priorización y la optimización. Después de esta versión no se crearon versiones adicionales de Project Portfolio Server. Sin embargo, las características de administración de carteras están disponibles en Project Server 2016 y la versión Premium de Project Online. Pero los datos de Project Portfolio Server 2007 no se pueden migrar a ninguno de los dos. Los datos, como los impulsores de negocio, tendrán que volver a crearse.
  
Otros recursos:
  
- [Project Online Descripciones del servicio:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) consulte las características de administración de carteras que se incluyen con Project Server 2016 y Project Online Premium.
    
- [Guía de migración de Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Temas relacionados

[Hoja de ruta de finalización del soporte técnico de SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Recursos para ayudarle a actualizar desde servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md)
