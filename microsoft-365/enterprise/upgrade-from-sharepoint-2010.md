---
title: Actualización desde SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Busque información y recursos para actualizar desde SharePoint 2010 y Sharepoint Server 2010. La compatibilidad con ambos finaliza el 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925337"
---
# <a name="upgrading-from-sharepoint-2010"></a>Actualización desde SharePoint 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft SharePoint 2010 y SharePoint Server 2010 llegarán al final del soporte técnico el 13 de abril de **2021**. En este artículo se proporcionan recursos que le ayudarán a migrar los datos existentes de SharePoint Server 2010 a SharePoint Online en Microsoft 365 o actualizar el entorno local de SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin de la compatibilidad?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Después de la fecha de finalización de la compatibilidad, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá más actualizaciones, revisiones o correcciones para el producto (incluidas revisiones o correcciones de seguridad). El soporte técnico de Microsoft habrá cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes.

Cuando finalice la compatibilidad con SharePoint Server 2010, elimine los datos que ya no necesite antes de actualizar el producto y migrar los datos importantes.

> [!NOTE]
> Un ciclo de vida de software suele durar diez años desde la versión inicial. [Los proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) pueden ayudarle a actualizar a la siguiente versión del software o migrar a Microsoft 365 migración (o ambas). Asegúrese de que conoce las fechas de fin de soporte técnico para las tecnologías subyacentes críticas, especialmente para la versión de Microsoft SQL Server que está usando con SharePoint. Para obtener más información, consulte [Fixed Lifecycle Policy](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en que finaliza la compatibilidad en el [sitio ciclo de vida del producto.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planee las actualizaciones o las migraciones con estas fechas en mente. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se parchea después de esa fecha, querrá planear una transición sin problemas a la siguiente versión del producto.

Esta matriz ayuda a trazar un curso entre las opciones de migración:

|Fin del producto de soporte técnico|Bueno |Procedimientos|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||SharePoint Server 2013 híbrido con SharePoint Online|SharePoint Server 2016 (local)|
|||SharePoint Búsqueda híbrida en la nube|

Si elige una opción en el extremo bajo de la escala (buena), deberá empezar a planear otra actualización poco después de la migración desde SharePoint Server 2010.

Estas son las tres rutas de acceso que puede tomar para evitar el fin de la compatibilidad con SharePoint Server 2010.

![SharePoint Rutas de actualización de Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> El fin de la compatibilidad con SharePoint Server 2010 y SharePoint Foundation 2010 está programado actualmente para el 13 de abril de 2021. Pero asegúrese de comprobar el sitio [del ciclo de](https://support.microsoft.com/lifecycle) vida del producto para las fechas más actuales.

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

SharePoint Server 2013 y SharePoint Foundation 2013 se pueden instalar localmente en sus propios servidores. O puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Hay varias opciones:

- Migrar a SharePoint Online.

- Actualice SharePoint server o SharePoint Foundation local.

- Realice las dos cosas anteriores.

- Implemente una [SharePoint híbrida.](/sharepoint/hybrid/hybrid)

Tenga en cuenta los costos ocultos del mantenimiento de una granja de servidores, incluido el mantenimiento o la migración de personalizaciones y actualización de hardware. Si ha tenido en cuenta estos factores, será más fácil actualizar localmente. Si ejecuta la granja de servidores en servidores SharePoint heredados sin una personalización intensa, podría beneficiarse de una migración planeada a SharePoint Online. Para un entorno de servidor SharePoint local, también puede considerar la posibilidad de mover algunos datos en SharePoint Online para reducir la sobrecarga de administración de hardware.

> [!NOTE]
> SharePoint administradores pueden crear una suscripción de Microsoft 365, configurar nuevos sitios de SharePoint Online y, a continuación, alejarse de SharePoint Server 2010 de forma limpia, llevando solo documentos esenciales a los sitios nuevos. A continuación, los datos restantes se pueden drenar del sitio SharePoint Server 2010 en archivos locales.

|SharePoint Online|SharePoint Servidor local|
|---|---|
|Alto costo en el tiempo (plan/ejecución/verificación)|Alto costo en el tiempo (plan/ejecución/verificación)|
|Menor costo en fondos (sin compras de hardware)|Mayor costo en fondos (compras de hardware)|
|Costo único en la migración|Costo único repetido por migración futura|
|Bajo costo total de propiedad/mantenimiento|Alto costo total de propiedad/mantenimiento|

Un movimiento único a Microsoft 365 tendrá un costo más alto mientras organiza los datos y decide qué llevar a la nube y qué dejar atrás. Pero después de migrar los datos, las actualizaciones futuras serán automáticas, ya que ya no necesitará administrar las actualizaciones de hardware y software. Además, el tiempo de espera de la granja de servidores se hará con el respaldo de un contrato de nivel de [servicio (SLA)](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)de Microsoft.

### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrate de SharePoint Online ofrece todas las características que necesitas. Vea [SharePoint descripción del servicio](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

No puede migrar directamente de SharePoint Server 2010 (o SharePoint Foundation 2010) a SharePoint Online. Gran parte del trabajo de migración es manual. Pero esta fase le ofrece la oportunidad de podar datos y sitios que ya no son necesarios antes del movimiento. Puede archivar otros datos en el almacenamiento. 

Recuerde que SharePoint Server 2010 y SharePoint Foundation 2010 no dejarán de funcionar al final del soporte técnico. Por lo tanto, los administradores pueden tener un período SharePoint todavía se está ejecutando si sus clientes olvidan mover algunos de sus datos.

Si actualiza a SharePoint Server 2013 o SharePoint Server 2016 y decide colocar datos en SharePoint Online, puede usar la API de migración de [SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) para migrar información a OneDrive para la Empresa.

|SharePoint Ventaja en línea|SharePoint Desventaja en línea|
|---|---|
|Microsoft proporciona hardware SPO y toda la administración de hardware.|Las características disponibles pueden diferir entre SharePoint server local y SPO.|
|Es el administrador global de la suscripción y puede asignar administradores a sitios de SPO.|Algunas acciones disponibles para un administrador de granja de servidores en SharePoint Server local no existen (o no son necesarias) en el rol administrador de SharePoint en Microsoft 365. Pero SharePoint administración, administración de colecciones de sitios y propiedad del sitio son locales en su organización.|
|Microsoft aplica revisiones, correcciones y actualizaciones al hardware y software subyacentes, incluidos los servidores SQL en los que se ejecuta SharePoint Online.|Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.|
|Microsoft publica contratos [de nivel de](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) servicio y se mueve rápidamente para resolver incidentes de nivel de servicio.|La copia de seguridad y restauración y otras opciones de recuperación son automatizadas por el servicio en SharePoint Online. Las copias de seguridad se sobrescriben si no se usan.|
|Microsoft realiza continuamente pruebas de seguridad y optimización del rendimiento del servidor en el servicio.|El servicio instala cambios en la interfaz de usuario y otras características de SharePoint se instalan y es posible que deban activarse o desactivarse.|
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft.](/compliance/regulatory/offering-home)|[La asistencia de FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).|
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.|
|Los proveedores de soluciones pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.|No todos los cambios en SharePoint Online están dentro de su control. Después de la migración, las diferencias de diseño en menús, bibliotecas y otras características pueden afectar temporalmente a la facilidad de uso.|
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden desuso, pero no hay un verdadero final del ciclo de vida de soporte técnico.|Hay un ciclo de vida de fin de soporte técnico para SharePoint Server o SharePoint Foundation, así como servidores SQL base.|

Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las [Microsoft 365 opciones](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint servidor local

A SharePoint Server 2019, las actualizaciones deben ir *en serie*. No hay ninguna forma de actualizar de SharePoint Server 2010 a SharePoint Server 2016 o a SharePoint 2019 directamente. Ruta de actualización en serie:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Llevará tiempo y planea seguir toda la ruta de acceso de SharePoint 2010 a SharePoint Server 2016. Las actualizaciones implican costos de hardware (SQL también deben actualizarse los servidores), software y administración. Además, es posible que las personalizaciones deban actualizarse o incluso abandonarse. Asegúrese de documentar personalizaciones críticas antes de actualizar la granja SharePoint server.

> [!NOTE]
> Es posible mantener la granja de servidores de fin de soporte técnico de SharePoint 2010, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero hay posibles problemas en estos movimientos manuales, como los documentos procedentes de 2010 que tienen una cuenta actual de última modificación con el alias de la cuenta que realiza el movimiento manual. Y algunos trabajos deben realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Asegúrese de limpiar el entorno antes de la actualización. Ten en cuenta los datos que puedes mover al almacenamiento o ya no necesitas. Esto puede reducir el impacto de la migración. Asegúrese de que la granja de servidores existente es funcional antes de actualizar y (ciertamente) antes de retirarse.

Recuerde revisar las rutas *de actualización admitidas y no admitidas:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Si tiene *personalizaciones,* es fundamental que planee cada paso de la ruta de migración:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Ventaja local|Desventaja local|
|---|---|
|Control total de todos los aspectos de la granja SharePoint (y su SQL), desde el hardware del servidor hacia arriba.|Todas las interrupciones y correcciones son responsabilidad de su empresa. Sin embargo, puedes contratar el soporte técnico de Microsoft de pago si el producto no está pasado el final del soporte técnico.|
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción SharePoint Online a través de híbrido.|Las actualizaciones, revisiones, correcciones de seguridad, actualizaciones de hardware y todo el mantenimiento de SharePoint Server y su granja de servidores SQL se administran localmente.|
|Acceso total para obtener más opciones de personalización que con SharePoint Online.|[Las ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente localmente.|
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.|Microsoft 365 que las características estén disponibles para SharePoint Online que no interoperan con SharePoint server local.|
|Los proveedores de soluciones pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y más allá).|Los SharePoint server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como se ve en SharePoint Online.|
|Control total de convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint servidor local.|SharePoint El servidor local es confidencial para los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Recursos de actualización

Comience comparando los requisitos de hardware y software. Si el entorno actual no cumple los requisitos básicos, es posible que primero tenga que actualizar el hardware de la granja de servidores o SQL servidores. 

Puede decidir mover algunos de sus sitios al hardware "evergreen" de SharePoint Online. Una vez que haya realizado la evaluación, siga los métodos y rutas de actualización admitidos.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Límites y límites de software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Introducción al proceso de actualización para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Crear una solución híbrida con SharePoint Online y SharePoint Server local

Una configuración híbrida proporciona lo mejor de local y en línea para algunas necesidades de migración. Puede conectar granjas de servidores de SharePoint Server 2013, 2016 o 2019 a SharePoint Online para crear un SharePoint híbrido: obtenga información sobre SharePoint [soluciones](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)híbridas .

Si una granja de servidores SharePoint servidor híbrido es su objetivo de migración, figure qué sitios y usuarios deben moverse en línea y qué deben permanecer locales. Clasificar el SharePoint de la granja de servidores como de impacto alto, mediano o bajo para su empresa puede ayudarle con esta decisión. Es posible que solo necesite compartir cuentas de usuario para el inicio de sesión y el índice de búsqueda de SharePoint server con SharePoint Online. Pero es posible que este factor no esté claro hasta que vea cómo se usan los sitios. Si su empresa decide más adelante migrar todo el contenido a SharePoint Online, puede mover todas las cuentas y datos restantes en línea y retirar la granja de servidores local. La administración y administración de SharePoint granja de servidores se realizará a través Microsoft 365 consolas desde ese momento.

Asegúrese de familiarizarse con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de servidores SharePoint local y la Microsoft 365 suscripción.

|Opción|Descripción|
|---|---|
|[Ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home).|[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.<br/><br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).|
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria.|
|Los partners pueden ayudar con el trabajo único de migrar los datos a SharePoint Online.||
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden desuso, pero no existe un verdadero final de compatibilidad.||

Si ha decidido crear un nuevo sitio Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las [Microsoft 365 opciones](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint servidor local

No hay forma de omitir versiones en SharePoint actualizaciones. Esto significa que las actualizaciones se van en serie:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

To take the entire path from SharePoint 2007 to SharePoint Server 2016 will mean a significant investment of time and will involve hardware (SQL servers must also be upgraded), software, and administration costs. Las personalizaciones tendrán que actualizarse o abandonarse, según la crítica de la característica.

> [!NOTE]
> Es posible mantener la granja de servidores de fin de vida de SharePoint 2007, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas de servidores independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero hay algunos inconvenientes en estos movimientos manuales, como los movimientos de documentos que reemplazan la última cuenta modificada por el alias de la cuenta que realiza el movimiento manual. Y es necesario realizar mucho trabajo con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. En cualquier caso, considera qué datos puedes mover al almacenamiento o ya no necesitas reducir el impacto de la migración.

Asegúrese de limpiar el entorno antes de la actualización. Asegúrese de que la granja de servidores existente es funcional antes de actualizar y, desde luego, antes de retirarse.

Recuerde revisar las rutas *de actualización admitidas y no admitidas:*

- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Si tiene *personalizaciones,* es fundamental planear la actualización para cada paso de la ruta de migración:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Profesional local|Con local|
|---|---|
|Control total de todos los aspectos de la granja SharePoint, desde el hardware del servidor hacia arriba.|Todas las interrupciones y correcciones son responsabilidad de su empresa. (Pero puedes contratar el soporte técnico de Microsoft de pago si el producto no está pasado el final del soporte técnico).|
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción SharePoint Online a través de híbrido.|Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint servidor administrado localmente.|
|Acceso completo para una mayor personalización.|[Las ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente localmente.|
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.|Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint servidor local.|
|Los partners pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y más allá).|Los SharePoint server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como se ve en SharePoint Online.|
|Control total de convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint servidor local.|SharePoint El servidor local es confidencial para los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Recursos de actualización

Empiece por saber que cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.

- *Requisitos de hardware/software para*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Límites y límites de software para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Información general sobre el proceso de actualización para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una SharePoint híbrida entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el control ofrecido por el entorno local y el menor costo de propiedad ofrecido por SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Obtenga información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Si decide que una granja de servidores de SharePoint híbrida beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de servidores SharePoint local y su suscripción Microsoft 365.

Es posible que desee crear un Microsoft 365 de desarrollo y pruebas, que puede configurar con guías [del laboratorio de pruebas](m365-enterprise-test-lab-guides.md). Después de obtener una suscripción de prueba o de Microsoft 365, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si desea migrar el contenido de Mi sitio a OneDrive para la Empresa, a través del asistente híbrido.

> [!NOTE]
> Para usar la opción híbrida, la granja de servidores de SharePoint Server 2010 debe actualizarse primero localmente a SharePoint Server 2013 o 2016. SharePoint Foundation 2010 y SharePoint Foundation 2013 no admiten conexiones híbridas con SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de opciones para Office cliente y servidores de 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin de la compatibilidad con Office clientes y servidores de 2010 y Windows póster de 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este póster ilustra las distintas rutas de acceso que puede tomar para evitar Office productos de cliente y servidor de 2010 y un Windows 7 final de soporte técnico, con rutas de acceso preferidas y compatibilidades de opciones en Microsoft 365 Enterprise resaltado.

También puede descargar [este](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) póster e imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="related-articles"></a>Artículos relacionados

[Recursos que le ayudarán a actualizar desde Office servidores y clientes de 2007 o 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Procedimientos recomendados para actualizar de SharePoint 2010 a SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Solucionar problemas de actualización de bases de datos en SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Buscar proveedores de soluciones de Microsoft para ayudarle con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)

[Directiva de servicio del producto actualizada para SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Directiva de servicio del producto actualizada para SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)