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
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924873"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de SharePoint Server 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El **10 de octubre de 2017,** Microsoft Office SharePoint Server 2007 llegó al final de la compatibilidad. Si no ha migrado de SharePoint Server 2007 a Microsoft 365 o una versión más reciente de SharePoint Server local, ahora es el momento de empezar a planear. En este artículo se proporcionan recursos para ayudarle a migrar datos a SharePoint Online o actualizar el servidor SharePoint local.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

SharePoint El servidor, como la mayoría de los productos de Microsoft, tiene un ciclo de vida de soporte técnico, durante el cual Microsoft proporciona nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Después del fin de la compatibilidad, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La granja de servidores de SharePoint Server 2007 seguirá funcionando después del 10 de octubre de 2017, pero no se lanzarán más actualizaciones, revisiones o correcciones para el producto, incluidas revisiones y correcciones de seguridad. El soporte técnico de Microsoft ha cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes del producto. Dado que la instalación ya no es compatible ni se ha parcheado, debe actualizar el producto o migrar datos importantes.
  
> [!TIP]
> Si aún no ha planeado la actualización o migración, vea: SharePoint opciones de migración de [2007](sharepoint-2007-migration-options.md) para ver algunos ejemplos de dónde empezar. También puede buscar socios de [Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que puedan ayudarle con la actualización o Microsoft 365 migración (o ambas).
  
Para obtener más información sobre Office servidores de 2007 y el fin de la compatibilidad, vea Recursos para ayudarle a actualizar desde Office servidores y clientes de [2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

La primera parada debe ser el sitio [ciclo de vida del producto](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007). Si tiene un producto de Microsoft local que está envejeciendo, compruebe su fecha de finalización de soporte técnico para que tenga un año o más para programar una actualización o migración. Cuando elija el siguiente paso, considere qué características del producto serían lo suficientemente buenas, mejores y mejores. Aquí le mostramos un ejemplo: 
  
|**Good**|**Mejor**|**Procedimientos**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Híbrido de SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Híbrido de SharePoint  <br/> |
   
Si elige una opción "lo suficientemente buena", pronto tendrá que empezar a planear otra actualización después de completar la migración de SharePoint Server 2007. 

>[!NOTE] 
>Las fechas de fin de soporte técnico están sujetas a cambios. Compruebe el [sitio ciclo de vida del producto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>¿Qué puedo hacer a continuación?

SharePoint El servidor se puede instalar localmente en sus propios servidores. O puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Las opciones son:
  
- Migrar a SharePoint Online.
    
- Actualice SharePoint servidor local.
    
- Realice las dos cosas anteriores.
    
- Implemente una [SharePoint híbrida.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Tenga en cuenta los costos ocultos asociados con el mantenimiento de una granja de servidores, el mantenimiento o la migración de personalizaciones y la actualización del hardware que necesita SharePoint servidor. Tener una granja de servidores SharePoint local es gratificante si es necesario. Pero si ejecuta la granja de servidores en servidores SharePoint heredados sin una personalización intensa, puede beneficiarse de la migración a SharePoint Online.
  
> [!IMPORTANT]
> Hay otra opción si el contenido de SharePoint 2007 se usa con poca frecuencia. Algunos administradores de SharePoint deciden crear una suscripción Microsoft 365, configurar un nuevo sitio de SharePoint Online y, a continuación, quitarse de SharePoint 2007 limpiamente, llevando solo documentos esenciales a los nuevos sitios de SharePoint Online. A continuación, los datos se pueden vaciar SharePoint sitio de 2007 en archivos. Tenga en cuenta el modo en que los usuarios trabajan con datos de SharePoint instalación de 2007. Puede haber formas creativas de administrar sus necesidades.
  
|**SharePoint Online (SPO)**|**SharePoint Servidor local**|
|:-----|:-----|
|Alto costo en el tiempo (plan/ ejecución/verificación)  <br/> |Alto costo en el tiempo (plan/ ejecución/verificación)  <br/> |
|Menor costo en fondos (sin compras de hardware)  <br/> |Mayor costo en fondos (hardware + desarrolladores/administradores)  <br/> |
|Costo único en la migración  <br/> |Costo único repetido por migración futura  <br/> |
|Bajo costo total de propiedad/mantenimiento  <br/> |Alto costo total de propiedad/mantenimiento  <br/> |
   
Al migrar a Microsoft 365, el movimiento de una sola vez tendrá un costo más elevado por adelantado, mientras organiza los datos y decide qué llevar a la nube y qué dejar atrás. Pero las actualizaciones futuras serán automáticas y ya no necesitará administrar las actualizaciones de hardware y software. Además, el tiempo de espera de la granja de servidores estará aprobado por un Contrato de nivel de servicio de Microsoft ([SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)).
  
### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online tiene todas las características que necesita. Vea [Microsoft 365 y Office 365 de los servicios](/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
No puede migrar directamente desde SharePoint 2007 a SharePoint Online. El movimiento a SharePoint Online se haría manualmente. Si actualiza a SharePoint Server 2013 o SharePoint Server 2016, puede usar la API de migración de SharePoint (por ejemplo, para migrar información a OneDrive para la Empresa).
  
|**Profesional en línea**|**Con en línea**|
|:-----|:-----|
|Microsoft proporciona hardware SPO y toda la administración de hardware.  <br/> |Las características disponibles pueden diferir entre SharePoint server local y SPO.  <br/> |
|Es el administrador global de la suscripción y puede asignar administradores a sitios de SPO.  <br/> |Algunas acciones disponibles para un administrador de la granja de servidores en SharePoint Server local no existen o no se incluyen necesariamente en el rol administrador de SharePoint en Microsoft 365.  <br/> |
|Microsoft aplica revisiones, correcciones y actualizaciones al hardware y software subyacentes. <br/> |Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.  <br/> |
|Microsoft publica contratos [de nivel de](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) servicio y se mueve rápidamente para resolver incidentes de nivel de servicio. <br/> |La copia de seguridad y restauración y otras opciones de recuperación son automatizadas por el servicio en SharePoint Online. Las copias de seguridad se sobrescriben si no se usan. <br/> |
|Microsoft realiza continuamente pruebas de seguridad y optimización del rendimiento del servidor en el servicio. <br/> |El servicio instala cambios en la interfaz de usuario y otras características de SharePoint se instalan y es posible que deban activarse o desactivarse. <br/> |
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft.](/compliance/regulatory/offering-home)  <br/> |[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tendrán acceso de administrador sin restricciones a su suscripción. <br/> |Puede haber costos adicionales si es necesario actualizar el hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.  <br/> |
|Los partners pueden ayudar con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente. Aunque las características pueden desuso, no hay ningún fin real de compatibilidad. <br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las [Microsoft 365 opciones](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint servidor local

No hay forma de omitir versiones en SharePoint actualizaciones. Las actualizaciones se van en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Para pasar de SharePoint 2007 a SharePoint Server 2016 significa una inversión significativa de tiempo e implicará costos en hardware (los servidores SQL también deben actualizarse), software y administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de fin de vida de SharePoint 2007, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero tenga cuidado con algunos de los problemas de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta de última modificación con el alias de la cuenta que hace el movimiento manual. Considere también el trabajo que debe realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Tenga en cuenta de antemano qué datos puede mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Es importante limpiar el entorno antes de actualizar. Asegúrese de que la granja de servidores existente es funcional antes de actualizar y, desde luego, antes de retirarse.
  
Recuerde revisar las rutas *de actualización admitidas y no admitidas:* 
  
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
|Control total de todos los aspectos de la granja SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todos los descansos y correcciones son responsabilidad de su empresa (puede contratar el soporte técnico de Microsoft de pago si su producto no está pasado el final del soporte técnico).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción SharePoint Online a través de híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint servidor administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |[Las ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente localmente.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones (bajo su control).  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint servidor local.  <br/> |
|Los partners pueden ayudar con la migración de datos a la siguiente versión de SharePoint Server (y más allá).  <br/> |Los SharePoint server no usarán automáticamente certificados [SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como se ve en SharePoint Online.  <br/> |
|Control total de convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint servidor local.  <br/> |SharePoint El servidor local es confidencial para los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que el entorno cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware/software para**: 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Límites y límites de software para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Información general sobre el proceso de actualización para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una SharePoint híbrida entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol ofrecido por el entorno local y el menor costo de propiedad ofrecido por SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información SharePoint soluciones híbridas.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja de servidores de SharePoint híbrida beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de servidores SharePoint local y su suscripción Microsoft 365.
  
| Opción | Descripción |
|:-----|:-----|
[Oferta de cumplimiento de Microsoft](/compliance/regulatory/offering-home)  <br/> |[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).  <br/> |
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a la suscripción.<br/> |Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.  <br/> |
|Los partners pueden ayudar con el trabajo único de migrar los datos a SharePoint Online.  <br/> ||
|Los productos en línea se actualizan automáticamente en todo el servicio. Aunque las características pueden desuso, no hay ningún fin real de compatibilidad.<br/> ||
   
Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las [Microsoft 365 opciones](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint servidor local

No hay forma de omitir versiones en SharePoint actualizaciones. Las actualizaciones se van en serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Pasar de SharePoint 2007 a SharePoint Server 2016 supondrá una inversión significativa de tiempo e implicará costos para el hardware (los servidores SQL también deben actualizarse), el software y la administración. Las personalizaciones tendrán que actualizarse o abandonarse.
  
> [!NOTE]
> Es posible mantener la granja de servidores de fin de vida de SharePoint 2007, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero tenga cuidado con los posibles problemas de los movimientos manuales, como los movimientos de documentos que reemplazan la cuenta de última modificación por el alias de la cuenta que realiza el movimiento manual, y el trabajo que debe realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Ten en cuenta los datos que puedes mover al almacenamiento o eliminar para reducir el impacto de la migración.
  
Limpiar el entorno antes de la actualización. Asegúrese de que la granja de servidores existente es funcional antes de actualizar y ciertamente antes de retirarse. 
  
Recuerde revisar las rutas *de actualización admitidas y no admitidas:* 
  
- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Si tiene *personalizaciones,* es fundamental que tenga un plan de actualización para cada paso de la ruta de migración: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Servicios locales Pro**|**Con local**|
|:-----|:-----|
|Control total de todos los aspectos de la granja SharePoint, desde el hardware del servidor hacia arriba.  <br/> |Todas las interrupciones y correcciones son responsabilidad de su empresa. (Puede contratar el soporte técnico de Microsoft de pago si el producto no está pasado el final del soporte técnico).  <br/> |
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción SharePoint Online a través de híbrido.  <br/> |Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint servidor administrado localmente.  <br/> |
|Acceso completo para una mayor personalización.  <br/> |[Las ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente localmente.  <br/> |
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.  <br/> |Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local  <br/> |
|Los partners pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y más allá).  <br/> |Los SharePoint server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como se ve en SharePoint Online.  <br/> |
|Control total de convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint servidor local.  <br/> |SharePoint El servidor local es confidencial para los ciclos de vida del producto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de actualización

Asegúrese de que el entorno cumple los requisitos de hardware y software. A continuación, siga los métodos de actualización admitidos.
  
- **Requisitos de hardware/software para:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Límites y límites de software para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Introducción al proceso de actualización para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una SharePoint híbrida entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el autocontrol ofrecido por el entorno local y el menor costo de propiedad ofrecido por SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Si decide que una granja de servidores de SharePoint híbrida beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de servidores SharePoint local y su suscripción Microsoft 365.
  
Una buena forma de ver cómo funciona esto es crear un entorno de desarrollo Microsoft 365 pruebas, que puede configurar con guías del laboratorio [de pruebas.](m365-enterprise-test-lab-guides.md) Después de obtener una suscripción de prueba o de Microsoft 365, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si desea migrar el contenido de Mi sitio a OneDrive para la Empresa, a través del asistente híbrido.
  
> [!NOTE]
> Recuerde que para usar la opción híbrida, la granja de servidores de SharePoint 2007 tendrá que actualizarse localmente a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Temas relacionados

[Solucionar problemas y reanudar la actualización (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Solucionar problemas de actualización (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Solucionar problemas de actualización de bases de datos en SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Buscar partners de Microsoft para ayudar con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos para ayudarle a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)
