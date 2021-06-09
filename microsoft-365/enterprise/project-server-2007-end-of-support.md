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
description: El 10 de octubre de 2017, la compatibilidad finalizó para Project Server 2007, Project Portfolio Server y Project 2007. Use este artículo para planear la actualización ahora.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927353"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Project Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La compatibilidad finalizó Office servidores y aplicaciones de 2007 en 2017 y debe tener en cuenta los planes de migración. Si actualmente usa Project Server 2007 y productos relacionados, tenga en cuenta las siguientes fechas de fin de soporte técnico:
  
|**Producto**|**Fecha de finalización del soporte técnico**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de octubre de 2017  <br/> |
|Project 2007 Standard  <br/> |10 de octubre de 2017  <br/> |
|Project 2007 Professional  <br/> |10 de octubre de 2017  <br/> |
   
Para obtener más información acerca Office servidores de 2007 que llegan a la retirada, [vea Upgrade from Office 2007 servers and client products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Dado que Project Server 2007 llegó a su fin de soporte técnico el 10 de octubre de 2017, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de Project Server 2007 seguirá en ejecución después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2007 tan pronto como sea práctico.
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Si usa Project Server 2007, debe explorar las opciones de migración, que son:
  
- Migrar a Project Online
    
- Migrar a una versión local más reciente de Project Server (preferiblemente Project Server 2016)
    
|**¿Por qué prefería migrar a Project Online**|**¿Por qué prefería migrar a Project Server 2016**|
|:-----|:-----|
| Tengo usuarios móviles.  <br/> <br/>Los costos de migración son una preocupación importante (hardware, software, horas y esfuerzo para implementar). <br/><br/>  Después de la migración, los costos para mantener mi entorno son una preocupación importante (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, y así sucesivamente).  <br/> | Las reglas de negocio me restringen el funcionamiento de mi negocio en la nube.<br/><br/>  Necesito controlar las actualizaciones de mi entorno.  |
   
> [!NOTE]
> Para obtener más información acerca de las opciones para mover desde los servidores de Office 2007, vea Recursos para ayudarle a actualizar desde Office servidores y clientes de [2007](upgrade-from-office-2007-servers-and-products.md). Tenga en cuenta que Project Server no admite una configuración híbrida, ya que Project Server y Project Online no pueden compartir el mismo grupo de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Consideraciones importantes al migrar desde Project Server 2007

Tenga en cuenta lo siguiente al planear la migración desde Project Server 2007:
  
- **Obtener ayuda de un** partner de Microsoft: actualizar desde Project Server 2007 puede ser un desafío y requiere mucha preparación y planeación. Puede ser especialmente difícil si no fuera la persona que estableció Project Server 2007 originalmente. Afortunadamente, hay partners de Microsoft que pueden ayudarle, ya sea que planee migrar a Project Server 2016 o a Project Online. Busque un partner de Microsoft para ayudarle con la migración en el [Centro de partners de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249). Busque en el término *Gold Project y Portfolio Management* para ver una lista de todos los partners de Microsoft que tienen experiencia en Project. 
    
- **Planear las personalizaciones:** es posible que muchas de las personalizaciones realizadas en el entorno de Project Server 2007 no funcionen al migrar a Project Server 2016 o Project Online. Existen diferencias significativas en la Project server entre versiones. Los sistemas operativos necesarios, los servidores de bases de datos y los exploradores web cliente que se admiten también difieren. Planee cómo probar o recompilar las personalizaciones para el nuevo entorno. La planeación también proporciona una buena oportunidad para considerar si cada personalización aún es necesaria. Para más información, vea [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013). 
    
- **Tiempo y paciencia:** la planeación, la ejecución y las pruebas de actualización llevará tiempo y esfuerzo, especialmente si actualiza a Project Server 2016. Por ejemplo, si migra de Project Server 2007 a Project Server 2016, primero debe migrar a Project Server 2010, comprobar los datos y, a continuación, hacer lo mismo al migrar a cada versión sucesiva. Es posible que quieras consultar con un partner de Microsoft para obtener estimaciones de cuánto tiempo llevará y cuánto costará.
    
## <a name="migrate-to-project-online"></a>Migrar a Project Online

Si decide migrar de Project Server 2007 a Project Online, puede hacer lo siguiente para migrar manualmente los datos del plan de proyecto:
  
1. Guarde los planes de proyecto de Project Server 2003 a formato .mpp.
    
2. En Project Profesional 2013, Project Profesional 2016, o el cliente de escritorio de Project Online, abra cada archivo .mpp y, a continuación, guárdelo y publirálo en Project Online.
    
Puede crear manualmente la configuración Microsoft Project Web App (PWA) en Project Online. Por ejemplo, vuelva a crear los campos personalizados o los calendarios de empresa necesarios. Los partners de Microsoft también pueden ayudarle con este proceso.
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Cómo configurar y usar Project Online <br/> |
|[Project Online Descripciones del servicio](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Información sobre los distintos planes Project Online que están disponibles <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar a una versión local más reciente de Project Server

Creemos firmemente que obtiene el mejor valor y experiencia de usuario mediante la migración a Project Online. Pero también entendemos que algunas organizaciones necesitan mantener los datos del proyecto en un entorno local. Si decide mantener los datos del proyecto localmente, puede migrar el entorno de Project Server 2007 a Project Server 2010, Project Server 2013 o Project Server 2016.
  
Si no puede migrar a Project Online, se recomienda migrar a Project Server 2016. Project Server 2016 incluye todas las características de versiones anteriores de Project Server. Coincide más estrechamente con la experiencia disponible con Project Online, aunque algunas características solo están disponibles en Project Online.
  
Después de cada migración, debe comprobar que los datos se migraron correctamente.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>¿Cómo puedo migrar a Project Server 2016?

Las diferencias de arquitectura entre Project Server 2007 y Project Server 2016 impedir una ruta de migración directa. Por lo tanto, debe migrar los datos de Project Server 2007 a cada versión sucesiva de Project Server hasta que llegue Project Server 2016.
  
Siga estos pasos para Project Server 2016:
  
1. Migre de Project Server 2007 a Project Server 2010.
    
2. Migrar de Project Serve 2010 a Project Server 2013.
    
3. Migre de Project Server 2013 a Project Server 2016.
    
Después de cada migración, asegúrese de que los datos se migraron correctamente.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Paso 1: Migrar de Project Server 2007 a Project Server 2010

Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010, vea [Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Project Introducción a la actualización de Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Una vista de alto nivel de lo que debe hacer para actualizar de Project Server 2007 a Project Server 2010 <br/> |
|[Planear la actualización a Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Consideraciones de planeación al actualizar de Project Server 2007 a Project Server 2010, incluidos los requisitos del sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>¿Cómo puedo actualizar?

Para obtener más información, [vea Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)). Pero es importante comprender que hay dos métodos distintos que puede usar para actualizar:
  
- **Actualización de base de datos adjunta:** Este método solo actualiza el contenido del entorno, no las opciones de configuración. Es necesario si está actualizando desde Office Project Server 2007 implementado en hardware que solo admite un sistema operativo de servidor de 32 bits. Existen dos tipos de métodos de actualización de base de datos adjunta:
    
  - **Actualización** completa de base de datos adjunta: migra los datos del proyecto almacenados en las bases de datos de Office Project Server 2007, además de los datos del sitio de Microsoft Project Web App almacenados en una base de datos SharePoint de contenido.
    
  - **Actualización principal de *base*** de datos adjunta: migra solo los datos del proyecto almacenados en las bases de datos Project servidor.
    
- **Actualización local:** los datos de configuración de la granja de servidores y todo el contenido de la granja de servidores se actualizan en el hardware existente en un orden fijo. Al iniciar el proceso de actualización, el programa de instalación desconecta toda la granja de servidores. Los sitios web y Microsoft Project web app no están disponibles hasta que finaliza la actualización y, a continuación, el programa de instalación reinicia el servidor. Después de comenzar una actualización local, no puede pausar la actualización ni revertirla a la versión anterior. Es mejor crear una imagen reflejada del entorno de producción y realizar la actualización local a este entorno, no en el entorno de producción. 
    
Recursos adicionales:
  
- [Actualización de SuperFlow Microsoft Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migración de Project Server 2007 a Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Consideraciones sobre la actualización de elementos web de Project Web App](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Kit de desarrollo de software (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Paso 2: Migrar a Project Server 2013

Después de comprobar que los datos se migraron correctamente, el siguiente paso es migrar a Project Server 2013.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013, vea [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016). 
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción al proceso de actualización Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Información general sobre lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013  <br/> |
|[Planear la actualización a Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Consideraciones de planeación al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Cosas que debe saber acerca de la actualización a esta versión

[Las novedades de la actualización Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) describen los cambios importantes para la actualización de esta versión. Los más notables son: 
  
- No hay ninguna actualización local a Project Server 2013. El método de base de datos adjunta es el único método admitido para actualizar de Project Server 2010 a Project Server 2013.
    
- El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una única base de datos de Project Web App.
    
- En las versiones de 2013, tanto SharePoint Server como Project Server cambiaron a autenticación basada en notificaciones. Si usa la autenticación clásica, debe tener en cuenta este factor para la actualización. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Recursos adicionales:
  
- [Introducción al proceso de actualización a Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project Diagrama de proceso de actualización del servidor](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [La gran consolidación de bases de datos, Project Server 2010 a 2013 migración en 8 pasos fáciles](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Paso 3: Migrar a Project Server 2016

Después de comprobar que los datos se migraron correctamente, el siguiente paso es migrar a Project Server 2016.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016, vea [Upgrade to Project Server 2016](//project/upgrading-to-project-server-2016).
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción al proceso de actualización a Project Server 2016](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Información general sobre lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016 <br/> |
|[Planeación de la actualización a Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Consideraciones de planeación que actualice de Project Server 2013 a Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Cosas que debe saber acerca de la actualización a esta versión

[Las cosas que necesita saber acerca de Project Server 2016 actualización](/project/plan-for-upgrade-to-project-server-2016) le indica algunos cambios importantes para la actualización de esta versión, que incluyen:
  
- Al crear el entorno Project Server 2016 al que migrará los datos de Project Server 2013, los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, vea [Deploy Project Server 2016](/project/deploy-project-server-2016).
    
- Los planes de recursos están en desuso en Project Server 2016. Los Project de recursos de Server 2013 se migrarán a Interacciones de recursos en Project Server 2016 y en Project Online. Vea [Overview: Resource engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obtener más información. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrar desde Portfolio Server 2007

Project Portfolio Server 2007 se usó con Project Server 2007 para estrategia de cartera, priorización y optimización. Después de esta versión, no se Project versiones adicionales de portfolio server. Sin embargo, las características de administración de cartera están disponibles en Project Server 2016 y la Premium de Project Online. Pero los datos de Project Portfolio Server 2007 no se pueden migrar a ninguno de los dos. Los datos, como los impulsores de negocios, tendrán que volver a crearse.
  
Otros recursos:
  
- [Project Online de servicio:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Vea las características de administración de cartera que se incluyen con Project Server 2016 y Project Online Premium.
    
- [Microsoft Office Project de migración de Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Temas relacionados

[SharePoint Guía básica de fin de soporte técnico de Server 2007](sharepoint-2007-end-of-support.md)
  
[Recursos para ayudarle a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)
