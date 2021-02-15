---
title: Plan de fin del soporte técnico de SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: La compatibilidad con SharePoint Server 2007 finalizó en octubre de 2017. En este artículo, obtenga información sobre las opciones de actualización, migración y soporte técnico.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519639"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de SharePoint Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El **10 de octubre de 2017,** Microsoft Office SharePoint Server 2007 alcanzó el fin del soporte técnico. Si no ha migrado de SharePoint Server 2007 a Microsoft 365 o a una versión más reciente de SharePoint Server local, ahora es el momento de empezar a planear. En este artículo se proporcionan recursos para ayudarle a migrar datos a SharePoint Online o actualizar SharePoint Server localmente.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del* soporte técnico?

SharePoint Server, como la mayoría de los productos de Microsoft, tiene un ciclo de vida de soporte técnico, durante el cual Microsoft proporciona nuevas características, correcciones de errores, correcciones de seguridad, entre otros. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Después de finalizar el soporte técnico, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La granja de servidores de SharePoint Server 2007 seguirá funcionando después del 10 de octubre de 2017, pero no se lanzarán más actualizaciones, revisiones o correcciones para el producto, incluidas revisiones y correcciones de seguridad. El Soporte técnico de Microsoft ha cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes del producto. Dado que la instalación ya no es compatible ni se ha parcheado, debe actualizar el producto o migrar datos importantes.
  
> [!TIP]
> Si aún no ha planeado la actualización o migración, vea: Opciones de migración de [SharePoint 2007](sharepoint-2007-migration-options.md) que se deben tener en cuenta para ver algunos ejemplos de dónde empezar. También puede buscar partners de [Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que puedan ayudarle con la actualización o la migración de Microsoft 365 (o ambos).
  
Para obtener más información acerca de los servidores de Office 2007 y el final del soporte técnico, vea Recursos para ayudarle a actualizar desde clientes y servidores [de Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

La primera detenerse debe ser el sitio [ciclo de vida del producto.](https://go.microsoft.com/fwlink/?linkid=843148) Si tiene un producto local de Microsoft que está en proceso de caducidad, compruebe la fecha de finalización del soporte técnico para que tenga un año o más para programar una actualización o migración. Cuando elija el siguiente paso, tenga en cuenta qué características de producto serían lo suficientemente buenas, mejores y mejores. Aquí le mostramos un ejemplo: 
  
|**Good**|**Mejor**|**Procedimientos**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Híbrido de SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Híbrido de SharePoint  <br/> |
   
Si elige una opción "suficientemente buena", pronto tendrá que empezar a planear otra actualización después de que se complete la migración de SharePoint Server 2007. 

>[!NOTE] 
>Las fechas de finalización del soporte técnico están sujetas a cambios. Compruebe el sitio [ciclo de vida del producto.](https://support.microsoft.com/lifecycle)
  
## <a name="where-can-i-go-next"></a>¿Qué puedo hacer a continuación?

SharePoint Server puede instalarse localmente en sus propios servidores. También puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Las opciones son:
  
- Migrar a SharePoint Online.
    
- Actualice SharePoint Server localmente.
    
- Realice las dos cosas anteriores.
    
- Implementar una [solución híbrida de SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Tenga en cuenta los costos ocultos asociados con el mantenimiento de una granja de servidores, el mantenimiento o la migración de personalizaciones y la actualización del hardware que SharePoint Server necesita. Tener una granja de servidores de SharePoint Server local es una recompensa si es necesario. Pero si ejecuta la granja de servidores en servidores de SharePoint heredados sin una personalización intensa, puede beneficiarse de la migración a SharePoint Online.
  
> [!IMPORTANT]
> Hay otra opción si el contenido de SharePoint 2007 se usa con poca frecuencia. Algunos administradores de SharePoint eligen crear una suscripción a Microsoft 365, configurar un nuevo sitio de SharePoint Online y, a continuación, cortar de SharePoint 2007 limpiamente, llevando solo documentos esenciales a los sitios de SharePoint Online nuevos. A continuación, los datos se pueden purgar del sitio de SharePoint 2007 en archivos. Tenga en cuenta cómo trabajan los usuarios con los datos de la instalación de SharePoint 2007. Puede haber formas creativos de administrar sus necesidades.
  
|**SharePoint Online (SPO)**|**SharePoint Server local**|
|:-----|:-----|
|Alto costo en el tiempo (plan/ ejecución/verificación)  <br/> |Alto costo en el tiempo (plan/ ejecución/verificación)  <br/> |
|Menor coste en fondos (sin compras de hardware)  <br/> |Mayor coste en fondos (hardware + desarrolladores/administradores)  <br/> |
|Costo único en la migración  <br/> |Costo único repetido por migración futura  <br/> |
|Bajo costo total de propiedad/mantenimiento  <br/> |Alto costo total de propiedad/mantenimiento  <br/> |
   
Al migrar a Microsoft 365, el movimiento único tendrá un mayor costo por adelantado, mientras organiza los datos y decide qué llevar a la nube y qué dejar atrás. Pero las actualizaciones futuras serán automáticas y ya no tendrás que administrar las actualizaciones de hardware y software. Además, el tiempo de espera de la granja de servidores se realizará mediante un Contrato de nivel de servicio de Microsoft[(SLA).](https://go.microsoft.com/fwlink/?linkid=843153)
  
### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online tiene todas las características que necesita. Vea [las descripciones del servicio de Microsoft 365 y Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
No puede migrar directamente de SharePoint 2007 a SharePoint Online. El traslado a SharePoint Online se realizaría manualmente. Si actualiza a SharePoint Server 2013 o SharePoint Server 2016, puede usar la API de migración de SharePoint (para migrar información a OneDrive para la Empresa, por ejemplo).
  
|**Online pro**|**Con en línea**|
|:-----|:-----|
|Microsoft proporciona hardware SPO y toda la administración de hardware.  <br/> |Las características disponibles pueden diferir entre SharePoint Server local y SPO.  <br/> |
|Es el administrador global de su suscripción y puede asignar administradores a sitios de SPO.  <br/> |Algunas acciones disponibles para un administrador de la granja de servidores en SharePoint Server local no existen o no se incluyen necesariamente en el rol de administrador de SharePoint en Microsoft 365.  <br/> |
|Microsoft aplica revisiones, correcciones y actualizaciones al hardware y software subyacentes. <br/> |Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.  <br/> |
|Microsoft publica contratos [de nivel de servicio](https://go.microsoft.com/fwlink/?linkid=843153) y se mueve rápidamente para resolver incidentes de nivel de servicio. <br/> |El servicio de SharePoint Online automatiza las opciones de copia de seguridad y restauración y otras opciones de recuperación. Las copias de seguridad se sobrescriben si no se usan. <br/> |
|Microsoft lleva a cabo continuamente las pruebas de seguridad y el ajuste del rendimiento del servidor en el servicio. <br/> |El servicio instala los cambios en la interfaz de usuario y otras características de SharePoint y es posible que deba activarse o desactivarse. <br/> |
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO descrita en la guía básica de contenido de migración de [SharePoint Online y OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tendrán acceso de administrador sin restricciones a su suscripción. <br/> |Puede haber costos adicionales si es necesario actualizar el hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.  <br/> |
|Los asociados pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente. Aunque las características pueden desuso, no hay ningún fin real de soporte técnico. <br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las opciones [de Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

No hay ninguna forma de omitir versiones en las actualizaciones de SharePoint. Las actualizaciones se realizarán en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Pasar de SharePoint 2007 a SharePoint Server 2016 implica una gran inversión de tiempo e implicará costos en hardware (los servidores SQL también deben actualizarse), software y administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2007 de fin de vida, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (para descargar y volver a cargar contenido, por ejemplo). Pero tenga en cuenta algunas de las dificultades de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta de última modificación con el alias de la cuenta que hace el movimiento manual. Tenga en cuenta también el trabajo que debe realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Considere de antemano qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Es importante limpiar el entorno antes de actualizar. Asegúrese de que la granja de servidores existente funciona antes de actualizar y, desde luego, antes de retirarla.
  
Recuerde revisar las rutas de actualización admitidas *y no admitidas:* 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Si tiene personalizaciones, es fundamental tener un plan para cada paso de la ruta de migración: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Profesional local**|**Con local**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de servidores de SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todas las interrupciones y correcciones son responsabilidad de su empresa (puede usar el Soporte técnico de Microsoft de pago si su producto no ha pasado el final del soporte técnico).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción de SharePoint Online a través de una implementación híbrida.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |[Las ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones (bajo su control).  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.  <br/> |
|Los asociados pueden ayudarle con la migración de datos a la próxima versión de SharePoint Server (y versiones posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.  <br/> |
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que su entorno cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware/software para:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Límites y límites del software para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Información general sobre el proceso de actualización para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una solución híbrida de SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol que ofrece la implementación local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información sobre las soluciones híbridas de SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de SharePoint local y su suscripción a Microsoft 365.
  
| Opción | Description |
|:-----|:-----|
[Oferta de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO descrita en la guía básica de contenido de migración de [SharePoint Online y OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.<br/> |Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.  <br/> |
|Los asociados pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente en todo el servicio. Aunque las características pueden estar en desuso, no hay ningún fin real de soporte técnico.<br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las opciones [de Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

No hay ninguna forma de omitir versiones en las actualizaciones de SharePoint. Las actualizaciones se realizarán en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Pasar de SharePoint 2007 a SharePoint Server 2016 supondrá una importante inversión de tiempo e implicará costes de hardware (los servidores SQL también deben actualizarse), software y administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2007 de fin de vida, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (para descargar y volver a cargar contenido, por ejemplo). Pero tenga cuidado con las posibles dificultades de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta de última modificación por el alias de la cuenta que realiza el movimiento manual y el trabajo que debe realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Tenga en cuenta qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Limpie el entorno antes de la actualización. Asegúrese de que la granja de servidores existente funciona antes de actualizar y, desde luego, antes de retirarla. 
  
Recuerde revisar las rutas de actualización admitidas *y no admitidas:* 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Si tiene *personalizaciones,* es fundamental que tenga un plan de actualización para cada paso de la ruta de migración: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Profesional local**|**Local Con**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de servidores de SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todas las interrupciones y correcciones son responsabilidad de su empresa. (Puede usar el Soporte técnico de Microsoft de pago si su producto no ha pasado el final del soporte técnico).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción de SharePoint Online a través de una implementación híbrida.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |[Las ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local  <br/> |
|Los asociados pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.  <br/> |
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que su entorno cumple los requisitos de hardware y software. A continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware/software para:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Límites y límites del software para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Información general sobre el proceso de actualización para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una solución híbrida de SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol que ofrece la implementación local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información sobre las soluciones híbridas de SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de SharePoint local y su suscripción a Microsoft 365.
  
Una buena manera de ver cómo funciona esto es crear un entorno de desarrollo y pruebas de Microsoft 365, que puede configurar con guías del entorno [de pruebas.](m365-enterprise-test-lab-guides.md) Después de obtener una suscripción de prueba o de adquirir Microsoft 365, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si desea migrar el contenido de Mi sitio a OneDrive para la Empresa, a través del asistente híbrido.
  
> [!NOTE]
> Recuerde que para usar la opción híbrida, la granja de servidores de SharePoint 2007 tendrá que actualizarse, localmente, a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Temas relacionados

[Solución de problemas y reanudación de la actualización (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Solución de problemas de actualización (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Solucionar problemas de actualización de bases de datos en SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Buscar partners de Microsoft para ayudar con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos para ayudarle a actualizar desde clientes y servidores de Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
