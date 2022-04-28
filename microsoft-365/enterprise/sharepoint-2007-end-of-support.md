---
title: Plan de fin del soporte técnico de SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: scotv
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
ms.localizationpriority: medium
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
ms.openlocfilehash: 260949f73fbb4530436484e70ca39d4e2f99bbcf
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098238"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de SharePoint Server 2007

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

El **10 de octubre de 2017**, Microsoft Office SharePoint Server 2007 llegó al final del soporte técnico. Si no ha migrado de SharePoint Server 2007 a Microsoft 365 o a una versión más reciente de SharePoint Server local, ahora es el momento de empezar a planear. En este artículo se proporcionan recursos que le ayudarán a migrar datos a SharePoint Online o a actualizar el SharePoint Server local.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

SharePoint Server, como la mayoría de los productos de Microsoft, tiene un ciclo de vida de soporte técnico, durante el cual Microsoft proporciona nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Una vez finalizado el soporte técnico, Microsoft ya no proporciona lo siguiente:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La granja de servidores de SharePoint Server 2007 seguirá funcionando después del 10 de octubre de 2017, pero no se publicarán más actualizaciones, revisiones o correcciones para el producto, incluidas revisiones o correcciones de seguridad. Soporte técnico de Microsoft ha desplazado por completo sus esfuerzos de apoyo a versiones más recientes del producto. Dado que la instalación ya no se admite ni se aplica una revisión, debe actualizar el producto o migrar datos importantes.
  
> [!TIP]
> Si aún no ha planeado la actualización o migración, consulte: [SharePoint opciones de migración de 2007 para ver](sharepoint-2007-migration-options.md) algunos ejemplos de dónde empezar. También puede buscar [asociados de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que puedan ayudar con la actualización o Microsoft 365 migración (o ambas).
  
Para obtener más información sobre Office servidores de 2007 y el final del soporte técnico, consulte [Recursos para ayudarle a actualizar desde Office 2007 servidores y clientes](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

La primera parada debe ser el [sitio del ciclo de vida del producto](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007). Si tiene un producto de Microsoft local que está envejeciendo, compruebe su fecha de finalización del soporte técnico para que tenga un año más o menos para programar una actualización o migración. Cuando elija el paso siguiente, considere qué características del producto serían lo suficientemente buenas, mejores y mejores. Aquí le mostramos un ejemplo: 
  
|**Good**|**Mejor**|**Procedimientos**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Híbrido de SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Híbrido de SharePoint  <br/> |
   
Si elige una opción "lo suficientemente buena", pronto tendrá que empezar a planear otra actualización después de que se complete la migración desde SharePoint Server 2007. 

>[!NOTE] 
>Las fechas de finalización del soporte técnico están sujetas a cambios. Consulte el [sitio ciclo de vida del producto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>¿Qué puedo hacer a continuación?

SharePoint Server se puede instalar localmente en sus propios servidores. También puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Las opciones son:
  
- Migre a SharePoint Online.
    
- Actualice SharePoint Server localmente.
    
- Realice las dos acciones anteriores.
    
- Implemente una solución [híbrida SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
    
Tenga en cuenta los costos ocultos asociados con el mantenimiento de una granja de servidores, el mantenimiento o la migración de personalizaciones y la actualización del hardware que SharePoint Server necesita. Tener una granja de servidores de SharePoint Server local es una recompensa si es necesario. Pero si ejecuta la granja en servidores de SharePoint heredados sin una personalización intensiva, puede beneficiarse de la migración a SharePoint Online.
  
> [!IMPORTANT]
> Hay otra opción si el contenido de SharePoint 2007 se usa con poca frecuencia. Algunos administradores de SharePoint deciden crear una suscripción de Microsoft 365, configurar un nuevo sitio de SharePoint Online y, a continuación, apartarse de SharePoint 2007 de forma limpia, llevando solo documentos esenciales a los nuevos sitios de SharePoint Online. A continuación, los datos se pueden purgar del sitio de SharePoint 2007 en archivos. Considere cómo funcionan los usuarios con los datos de la instalación de SharePoint 2007. Puede haber formas creativas de administrar sus necesidades.
  
|**SharePoint Online (SPO)**|**SharePoint Server local**|
|:-----|:-----|
|Alto costo en el tiempo (plan, ejecución o verificación)  <br/> |Alto costo en el tiempo (plan, ejecución o verificación)  <br/> |
|Menor costo en fondos (sin compras de hardware)  <br/> |Mayor costo en fondos (hardware + desarrolladores/administradores)  <br/> |
|Costo único en la migración  <br/> |Costo único repetido por migración futura  <br/> |
|Bajo costo total de propiedad/mantenimiento  <br/> |Alto costo total de propiedad/mantenimiento  <br/> |
   
Al migrar a Microsoft 365, el traslado único tendrá un costo más costoso por adelantado, mientras organiza los datos y decide qué llevar a la nube y qué dejar atrás. Pero las actualizaciones futuras serán automáticas y ya no necesitará administrar las actualizaciones de hardware y software. Además, el tiempo de actividad de la granja de servidores estará respaldado por un Contrato de nivel de servicio ([SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)) de Microsoft.
  
### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online tiene todas las características que necesita. Consulte [las descripciones del servicio Microsoft 365 y Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
No se puede migrar directamente de SharePoint 2007 a SharePoint Online. El traslado a SharePoint Online se realizaría manualmente. Si actualiza a SharePoint Server 2013 o SharePoint Server 2016, puede usar SharePoint Migration API (por ejemplo, para migrar información a OneDrive para la Empresa).
  
|**Profesional en línea**|**Con en línea**|
|:-----|:-----|
|Microsoft proporciona hardware SPO y toda la administración de hardware.  <br/> |Las características disponibles pueden diferir entre SharePoint Server local y SPO.  <br/> |
|Es el administrador de Sharepoint o el administrador global de la suscripción y puede asignar administradores a sitios de SPO.  <br/> |Algunas acciones disponibles para un administrador de granja de servidores en SharePoint Server local no existen o no se incluyen necesariamente en el rol de administrador de SharePoint en Microsoft 365.  <br/> |
|Microsoft aplica revisiones, correcciones y actualizaciones al hardware y software subyacentes. <br/> |Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.  <br/> |
|Microsoft publica [contratos de nivel de](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) servicio y se mueve rápidamente para resolver incidentes de nivel de servicio. <br/> |El servicio automatiza la copia de seguridad y restauración y otras opciones de recuperación en SharePoint Online. Las copias de seguridad se sobrescriben si no se usan. <br/> |
|Microsoft realiza pruebas de seguridad y optimización del rendimiento del servidor de forma continuada en el servicio. <br/> |El servicio instala los cambios en la interfaz de usuario y otras características de SharePoint y es posible que tenga que activarse o desactivarse. <br/> |
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home).  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) asistencia para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).  <br/> |
|Soporte técnico de Microsoft ingenieros y empleados del centro de datos no tendrán acceso de administrador sin restricciones a la suscripción. <br/> |Puede haber costos adicionales si es necesario actualizar el hardware para admitir la versión más reciente de SharePoint o si se requiere una granja secundaria para la actualización.  <br/> |
|Los asociados pueden ayudar con el trabajo único de migración de los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente. Aunque las características pueden dejar de estar en desuso, no hay un verdadero final de soporte técnico. <br/> ||
   
Si ha decidido crear un nuevo sitio Microsoft 365 y migrará manualmente los datos a él según sea necesario, compruebe las [opciones de Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualización local de SharePoint Server

No hay ninguna manera de omitir las versiones de las actualizaciones de SharePoint. Las actualizaciones van en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Pasar de SharePoint 2007 a SharePoint Server 2016 significa una inversión significativa de tiempo y implicará costos en hardware (SQL servidores también deben actualizarse), software y administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener el SharePoint granja de servidores de SharePoint 2007, instalar una granja de SharePoint Server 2016 en hardware nuevo (para que las granjas independientes se ejecuten en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero tenga cuidado con algunas de las dificultades de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta modificada por el alias de la cuenta que realiza el movimiento manual. Tenga en cuenta también el trabajo que debe realizarse con antelación, como volver a crear sitios, subsitios, permisos y estructuras de lista. Considere de antemano qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Es importante limpiar el entorno antes de actualizar. Asegúrese de que la granja existente es funcional antes de actualizar y, sin duda, antes de retirarse.
  
No olvide revisar las *rutas de actualización admitidas y no admitidas*: 
  
- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Si tiene personalizaciones, es fundamental tener un plan para cada paso de la ruta de migración: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Profesional local**|**Con local**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de SharePoint, desde el hardware del servidor hasta.  <br/> |Todos los descansos y correcciones son responsabilidad de su empresa (puede contratar a Soporte técnico de Microsoft de pago si su producto no ha superado el final del soporte técnico).  <br/> |
|Conjunto de características completo de SharePoint Server local con la opción de conectar la granja local a una suscripción SharePoint Online a través de híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |Las [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente en el entorno local.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se realizan en el entorno local (bajo su control).  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.  <br/> |
|Los asociados pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016), como se muestra en SharePoint Online.  <br/> |
|Control total de convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Actualizar recursos

Asegúrese de que el entorno cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware y software para**: 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Límites y límites de software para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Introducción al proceso de actualización para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creación de una solución híbrida SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol que ofrece el entorno local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar SharePoint granjas de servidores de Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de SharePoint local y la suscripción de Microsoft 365.
  
| Opción | Descripción |
|:-----|:-----|
[Ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home)  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) asistencia para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [En línea y OneDrive hoja de ruta del contenido de migración](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).  <br/> |
|Soporte técnico de Microsoft ingenieros y empleados del centro de datos no tienen acceso de administrador sin restricciones a la suscripción.<br/> |Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.  <br/> |
|Los asociados pueden ayudar con el trabajo único de migración de los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente en todo el servicio. Aunque las características pueden dejar de estar en desuso, no hay un verdadero final de soporte técnico.<br/> ||
   
Si ha decidido crear un nuevo sitio Microsoft 365 y migrará manualmente los datos a él según sea necesario, compruebe las [opciones de Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualización local de SharePoint Server

No hay ninguna manera de omitir las versiones de las actualizaciones de SharePoint. Las actualizaciones van en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Pasar de SharePoint 2007 a SharePoint Server 2016 supondrá una inversión significativa de tiempo e implicará costos de hardware (SQL servidores también deben actualizarse), software y administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener el SharePoint granja de servidores de SharePoint 2007, instalar una granja de SharePoint Server 2016 en hardware nuevo (para que las granjas independientes se ejecuten en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero tenga cuidado con los posibles problemas de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta modificada por el alias de la cuenta que realiza el movimiento manual y el trabajo que debe realizarse con antelación, como la recreación de sitios, subsitios, permisos y estructuras de lista. Tenga en cuenta qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Limpie el entorno antes de la actualización. Asegúrese de que la granja existente es funcional antes de actualizar y, sin duda, antes de retirarse. 
  
No olvide revisar las *rutas de actualización admitidas y no admitidas*: 
  
- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Si tiene *personalizaciones*, es fundamental que tenga un plan de actualización para cada paso de la ruta de migración: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Pro locales**|**Con local**|
|:-----|:-----|
|Control total de todos los aspectos de la granja de SharePoint, desde el hardware del servidor hasta.  <br/> |Todos los descansos y correcciones son responsabilidad de su empresa. (Puede interactuar con Soporte técnico de Microsoft de pago si su producto no ha superado el fin del soporte técnico).  <br/> |
|Conjunto de características completo de SharePoint Server local con la opción de conectar la granja local a una suscripción SharePoint Online a través de híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |Las [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente en el entorno local.  <br/> |
|Las pruebas de seguridad y la optimización del rendimiento del servidor se realizan en el entorno local bajo su control.  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local  <br/> |
|Los asociados pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).  <br/> |Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016), como se muestra en SharePoint Online.  <br/> |
|Control total de convenciones de nomenclatura, copia de seguridad y restauración, y otras opciones de recuperación en SharePoint Server local.  <br/> |SharePoint Server local es sensible a los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Actualizar recursos

Asegúrese de que el entorno cumple los requisitos de hardware y software. A continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware y software para:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Límites y límites de software para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Introducción al proceso de actualización para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creación de una solución híbrida SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol que ofrece el entorno local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar SharePoint granjas de servidores de Server 2013 o 2016 a SharePoint Online a través de híbridos. [Más información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de SharePoint local y la suscripción de Microsoft 365.
  
Una buena manera de ver cómo funciona es crear un entorno de desarrollo y pruebas Microsoft 365, que puede configurar con [guías de laboratorio de pruebas](m365-enterprise-test-lab-guides.md). Después de obtener una versión de prueba o comprar Microsoft 365 suscripción, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si quiere migrar el contenido de Mi sitio a OneDrive para la Empresa, mediante el asistente híbrido.
  
> [!NOTE]
> Recuerde que para usar la opción híbrida, la granja de SharePoint 2007 deberá actualizarse localmente a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Temas relacionados

[Solución de problemas y reanudación de la actualización (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Solución de problemas de actualización (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Solucionar problemas de actualización de bases de datos en SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Buscar asociados de Microsoft para ayudar con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos que le ayudarán a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)
