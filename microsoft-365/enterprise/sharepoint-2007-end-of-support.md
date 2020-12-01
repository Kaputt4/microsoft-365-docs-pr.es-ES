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
description: La compatibilidad con SharePoint Server 2007 finalizó en el 2017 de octubre. En este artículo, obtenga información sobre las opciones de actualización, migración y soporte técnico.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519639"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de SharePoint Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El **10 de octubre de 2017**, Microsoft Office SharePoint Server 2007 alcanzó el final del soporte técnico. Si no ha migrado de SharePoint Server 2007 a Microsoft 365 o a una versión más reciente de SharePoint Server local, ahora es el momento de empezar a planear. En este artículo se proporcionan recursos que le ayudarán a migrar datos a SharePoint Online o a actualizar SharePoint Server local.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa el *fin de soporte* ?

SharePoint Server, como la mayoría de los productos de Microsoft, tiene un ciclo de vida de soporte técnico en el que Microsoft proporciona nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar diez años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Una vez finalizado el soporte técnico, Microsoft deja de proporcionar:
  
- Soporte técnico para los problemas que pueden surgir.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y la usabilidad del servidor.
    
- Revisiones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
    
- Las actualizaciones de zona horaria.
    
La granja de servidores de SharePoint Server 2007 seguirá funcionando después del 10 de octubre de 2017, pero no se publicarán más actualizaciones, revisiones ni correcciones para el producto, incluidas las revisiones o correcciones de seguridad. El soporte técnico de Microsoft ha desplazado completamente sus esfuerzos de soporte a versiones más recientes del producto. Debido a que la instalación ya no es compatible o se aplica revisión, debe actualizar el producto o migrar datos importantes.
  
> [!TIP]
> Si aún no ha planeado la actualización o la migración, vea: [Opciones de migración de SharePoint 2007 que hay que tener en cuenta](sharepoint-2007-migration-options.md) para algunos ejemplos de dónde comenzar. También puede buscar asociados de [Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que puedan ayudarle con la actualización o la migración de Microsoft 365 (o ambos).
  
Para obtener más información acerca de los servidores de Office 2007 y el final del soporte técnico, vea [recursos para ayudarle a actualizar desde office 2007 servidores y clientes](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>¿Qué opciones tengo?

El primer punto de interrupción debe ser el [sitio del ciclo de vida del producto](https://go.microsoft.com/fwlink/?linkid=843148). Si tiene un producto de Microsoft local que caduca, Compruebe la fecha de finalización del soporte técnico para que tenga un año o para programar una actualización o migración. Cuando elija el paso siguiente, tenga en cuenta qué características del producto serían lo suficientemente buenas, mejores y mejores. Aquí le mostramos un ejemplo: 
  
|**Good**|**Conseguir**|**Procedimientos**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Entorno híbrido de SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Entorno híbrido de SharePoint  <br/> |
   
Si elige una opción "lo suficientemente buena", pronto deberá empezar a planear otra actualización después de que se complete la migración desde SharePoint Server 2007. 

>[!NOTE] 
>Las fechas de fin de soporte están sujetas a cambios. Compruebe el [sitio de ciclo de vida del producto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>¿Qué puedo hacer a continuación?

SharePoint Server se puede instalar localmente en sus propios servidores. O bien, puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Las opciones son:
  
- Migrar a SharePoint Online.
    
- Actualice SharePoint Server local.
    
- Realice las dos acciones anteriores.
    
- Implementar una solución [híbrida de SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) .
    
Tenga en cuenta los costos ocultos asociados con el mantenimiento de una granja de servidores, el mantenimiento o la migración de personalizaciones y la actualización del hardware que SharePoint Server necesita. Tener una granja de servidores de SharePoint Server local es premiada si es necesario. Pero si ejecuta la granja de servidores de SharePoint heredados sin una gran personalización, puede beneficiarse de la migración a SharePoint Online.
  
> [!IMPORTANT]
> Hay otra opción si el contenido de SharePoint 2007 se usa con poca frecuencia. Algunos administradores de SharePoint eligen crear una suscripción a Microsoft 365, configurar un nuevo sitio de SharePoint Online y, a continuación, quitar SharePoint 2007 sin problemas, tomando solo los documentos fundamentales en los sitios de SharePoint Online nuevos. A continuación, los datos se pueden purgar del sitio de SharePoint 2007 en archivos. Considere la forma en que los usuarios trabajan con datos de su instalación de SharePoint 2007. Puede que haya formas creativas para administrar sus necesidades.
  
|**SharePoint Online (SPO)**|**SharePoint Server local**|
|:-----|:-----|
|Costo elevado en el tiempo (planificación/ejecución/comprobación)  <br/> |Costo elevado en el tiempo (planificación/ejecución/comprobación)  <br/> |
|Menor coste de fondos (no hay compras de hardware)  <br/> |Costo más alto en los fondos (hardware + desarrolladores/administradores)  <br/> |
|Costo de tiempo único en la migración  <br/> |Costo de tiempo único repetido por migración futura  <br/> |
|Bajo costo total de propiedad/mantenimiento  <br/> |Costo total de propiedad/mantenimiento elevado  <br/> |
   
Al migrar a Microsoft 365, el movimiento único tendrá un costo inicial más intenso, mientras que los datos se organizan y se decide qué se va a llevar a la nube y qué se debe dejar atrás. Pero las actualizaciones futuras serán automáticas y ya no necesitará administrar las actualizaciones de hardware y software. Además, el tiempo de actividad de la granja de servidores será respaldado por un contrato de nivel de servicio ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) de Microsoft.
  
### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online tiene todas las características que necesita. Consulte las [descripciones de servicio de Microsoft 365 y Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
No puede migrar directamente de SharePoint 2007 a SharePoint Online. El cambio a SharePoint Online se realizaría manualmente. Si actualiza a SharePoint Server 2013 o SharePoint Server 2016, puede usar la API de migración de SharePoint (para migrar información a OneDrive para la empresa, por ejemplo).
  
|**Online Pro**|**Con en línea**|
|:-----|:-----|
|Microsoft proporciona el hardware de SPO y toda la administración de hardware.  <br/> |Las características disponibles pueden diferir entre SharePoint Server local y SPO.  <br/> |
|Usted es el administrador global de su suscripción y puede asignar administradores a los sitios de SPO.  <br/> |Algunas acciones disponibles para un administrador de la granja de servidores de SharePoint Server local no existen o no necesariamente se incluyen en el rol de administrador de SharePoint en Microsoft 365.  <br/> |
|Microsoft aplica revisiones, revisiones y actualizaciones a hardware y software subyacentes. <br/> |Como no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.  <br/> |
|Microsoft publica [contratos de nivel de servicio](https://go.microsoft.com/fwlink/?linkid=843153) y se mueve rápidamente para resolver incidencias de nivel de servicio. <br/> |La copia de seguridad y restauración y otras opciones de recuperación están automatizadas por el servicio en SharePoint Online. Las copias de seguridad se sobrescriben si no se usan. <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo de manera continua en el servicio de Microsoft. <br/> |El servicio instala los cambios en la interfaz de usuario y en otras características de SharePoint, por lo que es posible que deban activarse o desactivarse. <br/> |
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |La asistencia de [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en la [Guía de contenido de migración de SharePoint Online y OneDrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de administración no tienen acceso de administrador ilimitado a su suscripción. <br/> |Puede haber costos adicionales si es necesario actualizar el hardware para que sea compatible con la versión más reciente de SharePoint o si se requiere una granja secundaria para la actualización.  <br/> |
|Los socios pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente. Aunque las características pueden dejar de estar en desuso, no hay verdaderos extremos del soporte técnico. <br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar los datos de forma manual según sea necesario, compruebe las [Opciones de 365 de Microsoft](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

No hay ninguna forma de omitir las versiones en las actualizaciones de SharePoint. Las actualizaciones se realizan en serie:
  
- SharePoint 2007 \> SharePoint server 2010 SharePoint server \> 2013 \> SharePoint Server 2016
   
Ir de SharePoint 2007 a SharePoint Server 2016 significa una importante inversión de tiempo y implicará costos en el hardware (también deben actualizarse los servidores SQL), el software y la administración. Las personalizaciones deberán actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2007 de final de vida, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual del contenido (para descargar y volver a cargar contenido, por ejemplo). Pero tenga en cuenta algunos de los problemas de movimientos manuales, como los movimientos de documentos que reemplazan la última cuenta modificada por el alias de la cuenta que realiza el movimiento manual. Además, tenga en cuenta el trabajo que se debe realizar antes de tiempo, como volver a crear sitios, subsitios, permisos y estructuras de listas. Tenga en cuenta con antelación qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Es importante limpiar el entorno antes de la actualización. Asegúrese de que la granja de servidores existente es funcional antes de realizar la actualización y ciertamente antes de su retiro.
  
Recuerde revisar las *rutas de actualización admitidas y no admitidas*: 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Si tiene personalizaciones, es fundamental tener un plan para cada paso de la ruta de migración: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro local**|**Local con**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de servidores de SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todos los descansos y las correcciones son responsabilidad de la empresa (puede participar en el soporte de Microsoft si el producto no ha sobrepasado el fin de soporte).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local con una suscripción de SharePoint Online a través de un híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |Las [ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en sus instalaciones (bajo su control).  <br/> |Microsoft 365 puede poner características a disposición de SharePoint Online que no interoperen con SharePoint Server local.  <br/> |
|Los socios pueden ayudarle a migrar datos a la próxima versión de SharePoint Server (y versiones posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente los certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.  <br/> |
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida de los productos.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que el entorno cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware y software para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- Límites **de software para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Información general sobre el proceso de actualización para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una solución híbrida de SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración se encuentra en algún lugar entre el autocontrol ofrecido por el sistema local y el menor costo de propiedad ofrecido por SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de entornos híbridos. [Obtenga información sobre las soluciones híbridas de SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Si decide que una granja de servidores híbrida de SharePoint Server beneficiará su negocio, familiarícese con los tipos existentes de híbridos y cómo configurar la conexión entre su granja de servidores local de SharePoint y la suscripción a Microsoft 365.
  
| Opción | Descripción |
|:-----|:-----|
[Oferta de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |La asistencia de [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> La mayor parte de la actualización será manual o a través de la API de migración de SPO que se describe en la [Guía de contenido de migración de SharePoint Online y OneDrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.<br/> |Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para que sea compatible con la versión más reciente de SharePoint o si se requiere una granja secundaria para la actualización.  <br/> |
|Los socios pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente en el servicio. Aunque las características pueden dejar de estar en desuso, no hay verdaderos extremos del soporte técnico.<br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar los datos de forma manual según sea necesario, compruebe las [Opciones de 365 de Microsoft](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

No hay ninguna forma de omitir las versiones en las actualizaciones de SharePoint. Las actualizaciones se realizan en serie:
  
- SharePoint 2007 \> SharePoint server 2010 SharePoint server \> 2013 \> SharePoint Server 2016
   
Ir de SharePoint 2007 a SharePoint Server 2016 significa una importante inversión de tiempo y implicará costos de hardware (también deben actualizarse los servidores SQL), el software y la administración. Las personalizaciones deberán actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2007 de final de vida, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual del contenido (para descargar y volver a cargar contenido, por ejemplo). Pero tenga en cuenta los posibles problemas de movimientos manuales, como los movimientos de documentos que reemplazan la última cuenta modificada por el alias de la cuenta que realiza el traslado manual y el trabajo que debe realizarse antes de tiempo, como volver a crear sitios, subsitios, permisos y estructuras de listas. Considere qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Limpie su entorno antes de la actualización. Asegúrese de que la granja de servidores existente es funcional antes de realizar la actualización y ciertamente antes de su retiro. 
  
Recuerde revisar las *rutas de actualización admitidas y no admitidas*: 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Si tiene *personalizaciones*, es fundamental que disponga de un plan de actualización para cada paso de la ruta de migración: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro local**|**Local con**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de servidores de SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todas las interrupciones y correcciones son responsabilidad de la empresa. (Puede participar en el servicio de soporte de Microsoft si su producto no supera el final del soporte técnico).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local con una suscripción de SharePoint Online a través de un híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |Las [ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se realizan en sus instalaciones bajo el control.  <br/> |Microsoft 365 puede poner características a disposición de SharePoint Online que no interoperen con SharePoint Server local  <br/> |
|Los socios pueden ayudar a migrar datos a la próxima versión de SharePoint Server (y posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente los certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.  <br/> |
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida de los productos.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que su entorno cumple con los requisitos de hardware y software. A continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware y software para:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Límites de software para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Información general sobre el proceso de actualización para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una solución híbrida de SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración se encuentra en algún lugar entre el autocontrol ofrecido por el sistema local y el menor costo de propiedad ofrecido por SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de entornos híbridos. [Obtenga información sobre las soluciones híbridas de SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja de servidores híbrida de SharePoint Server beneficiará su negocio, familiarícese con los tipos existentes de híbridos y cómo configurar la conexión entre su granja de servidores local de SharePoint y la suscripción a Microsoft 365.
  
Una buena forma de ver cómo funciona esto es crear un entorno de pruebas y desarrollo de Microsoft 365, que puede configurar con guías de entorno de [pruebas](m365-enterprise-test-lab-guides.md). Después de obtener una suscripción de prueba o de Microsoft 365, puede crear las colecciones de sitios, los sitios web y las bibliotecas de documentos en SharePoint Online a los que puede migrar datos. Puede realizar la migración manualmente, mediante la API de migración o, si desea migrar el contenido de mi sitio a OneDrive para la empresa, mediante el Asistente para la implementación híbrida.
  
> [!NOTE]
> Recuerde que para usar la opción híbrida, la granja de servidores de SharePoint 2007 debe actualizarse, de forma local, a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Temas relacionados

[Solución de problemas y reanudación de la actualización (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Solución de problemas de actualización (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Solucionar problemas de actualización de bases de datos en SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Buscar a los socios de Microsoft para ayudarle con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos que le ayudarán a actualizar desde los servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
