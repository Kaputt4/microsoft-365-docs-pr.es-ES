---
title: Actualización desde SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: Busque información y recursos para actualizar desde SharePoint 2010 y SharePoint Server 2010. La compatibilidad con ambos finaliza el 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eba7c6739aef420bc90ef866dbd6f3becbccd8ff
ms.sourcegitcommit: 18bc521a88b7b521bccb0e69d02deac764218087
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2022
ms.locfileid: "66115969"
---
# <a name="upgrading-from-sharepoint-2010"></a>Actualización desde SharePoint 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft SharePoint 2010 y SharePoint Server 2010 finalizarán el soporte técnico el **13 de abril de 2021**. En este artículo se proporcionan recursos que le ayudarán a migrar los datos existentes de SharePoint Server 2010 a SharePoint Online en Microsoft 365 o a actualizar el entorno local SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin del soporte técnico*?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Después de la fecha de finalización del soporte técnico, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá actualizaciones, revisiones ni correcciones adicionales para el producto (incluidas revisiones o correcciones de seguridad). Soporte técnico de Microsoft habrá cambiado por completo sus esfuerzos de soporte técnico a versiones más recientes.

A medida que finalice la compatibilidad con SharePoint Server 2010, elimine los datos que ya no necesite antes de actualizar el producto y migrar los datos importantes.

> [!NOTE]
> Un ciclo de vida de software suele durar diez años a partir de la versión inicial. [Los proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) pueden ayudarle a actualizar a la siguiente versión del software o migrar a Microsoft 365 migración (o ambas). Asegúrese de conocer también las fechas de finalización del soporte técnico para las tecnologías subyacentes críticas, especialmente para la versión de Microsoft SQL Server que usa con SharePoint. Para obtener más información, consulte [Directiva de ciclo de vida fijo](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en las que finaliza el soporte técnico en el [sitio ciclo de vida del producto](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010). Planee las actualizaciones o migraciones teniendo en cuenta estas fechas. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se aplicará una revisión después de esa fecha, querrá planear una transición fluida a la siguiente versión del producto.

Esta matriz ayuda a trazar un curso entre las opciones de migración:

|Producto de fin de soporte técnico|Bueno |Procedimientos|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||SharePoint Server 2013 híbrido con SharePoint Online|SharePoint Server 2016 (local)|
|||SharePoint Búsqueda híbrida en la nube|

Si elige una opción en el extremo inferior de la escala (buena), deberá empezar a planear otra actualización poco después de la migración desde SharePoint Server 2010.

Estas son las tres rutas de acceso que puede tomar para evitar el fin de la compatibilidad con SharePoint Server 2010.

![rutas de actualización de SharePoint Server 2010.](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> El fin de la compatibilidad con SharePoint Server 2010 y SharePoint Foundation 2010 está programado actualmente para el 13 de abril de 2021. Pero asegúrese de comprobar las fechas más actuales en el [sitio ciclo de vida del producto](https://support.microsoft.com/lifecycle) .

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

SharePoint Server 2013 y SharePoint Foundation 2013 se pueden instalar de forma local en sus propios servidores. También puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Hay varias opciones:

- Migre a SharePoint Online.

- Actualice SharePoint Server o SharePoint Foundation local.

- Realice las dos acciones anteriores.

- Implemente una solución [híbrida SharePoint](/sharepoint/hybrid/hybrid).

Tenga en cuenta los costos ocultos de mantener una granja de servidores, incluido el mantenimiento o la migración de personalizaciones y la actualización de hardware. Si ha tenido en cuenta estos factores, será más fácil actualizar localmente. Si ejecuta la granja en servidores SharePoint heredados sin una personalización intensiva, podría beneficiarse de una migración planeada a SharePoint Online. Para un entorno de SharePoint Server local, también puede considerar la posibilidad de mover algunos datos de SharePoint Online para reducir la sobrecarga de administración de hardware.

> [!NOTE]
> SharePoint los administradores pueden crear una suscripción de Microsoft 365, configurar nuevos sitios de SharePoint Online y, a continuación, eliminar de SharePoint Server 2010 de forma limpia, llevando solo documentos esenciales a los sitios nuevos. A continuación, los datos restantes se pueden purgar del sitio de SharePoint Server 2010 en archivos locales.

|SharePoint Online|SharePoint Server local|
|---|---|
|Alto costo en el tiempo (plan,ejecución/verificación)|Alto costo en el tiempo (plan,ejecución/verificación)|
|Menor costo en fondos (sin compras de hardware)|Mayor costo en fondos (compras de hardware)|
|Costo único en la migración|Costo único repetido por migración futura|
|Bajo costo total de propiedad/mantenimiento|Alto costo total de propiedad/mantenimiento|

Un traslado único a Microsoft 365 tendrá un costo mayor mientras organiza los datos y decide qué llevar a la nube y qué dejar atrás. Pero después de migrar los datos, las actualizaciones futuras serán automáticas, ya que ya no necesitará administrar las actualizaciones de hardware y software. Y el tiempo de actividad de la granja estará respaldado por un [contrato de nivel de servicio (SLA) de Microsoft](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement).

### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online ofrece todas las características que necesita. Consulte [SharePoint descripción del servicio](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

No se puede migrar directamente de SharePoint Server 2010 (o SharePoint Foundation 2010) a SharePoint Online. Gran parte del trabajo de migración es manual. Pero esta fase le ofrece la oportunidad de eliminar los datos y los sitios que ya no son necesarios antes del traslado. Puede archivar otros datos en el almacenamiento. 

Recuerde que SharePoint Server 2010 y SharePoint Foundation 2010 no dejarán de funcionar al final del soporte técnico. Por lo tanto, los administradores pueden tener un período en el que SharePoint sigue ejecutándose si sus clientes se olvidan de mover algunos de sus datos.

Si actualiza a SharePoint Server 2013 o SharePoint Server 2016 y decide colocar datos en SharePoint Online, puede usar [la API de migración de SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) para migrar información a OneDrive para la Empresa.

|SharePoint ventaja en línea|SharePoint desventaja en línea|
|---|---|
|Microsoft proporciona hardware SPO y toda la administración de hardware.|Las características disponibles pueden diferir entre SharePoint Server local y SPO.|
|Es el administrador SharePoint o administrador global de la suscripción y puede asignar administradores a sitios de SPO.|Algunas acciones disponibles para un administrador de granja de servidores en SharePoint Server local no existen (o no son necesarias) en el rol de administrador de SharePoint en Microsoft 365. Sin embargo, SharePoint Administración, Administración de colecciones de sitios y Propiedad del sitio son locales para su organización.|
|Microsoft aplica revisiones, correcciones y actualizaciones al hardware y software subyacentes, incluidos SQL servidores en los que se ejecuta SharePoint Online.|Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.|
|Microsoft publica [contratos de nivel de servicio](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) y se mueve rápidamente para resolver incidentes de nivel de servicio.|El servicio automatiza la copia de seguridad y restauración y otras opciones de recuperación en SharePoint Online. Las copias de seguridad se sobrescriben si no se usan.|
|Microsoft realiza continuamente pruebas de seguridad y optimización del rendimiento del servidor en el servicio.|El servicio instala los cambios en la interfaz de usuario y otras características de SharePoint y es posible que tenga que activarse o desactivarse.|
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home).|[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) asistencia para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).|
|Soporte técnico de Microsoft ingenieros y empleados del centro de datos no tienen acceso de administrador sin restricciones a la suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.|
|Los proveedores de soluciones pueden ayudar con el trabajo único de migrar los datos a SharePoint Online.|No todos los cambios en SharePoint Online están dentro de su control. Después de la migración, las diferencias de diseño en menús, bibliotecas y otras características pueden afectar temporalmente a la facilidad de uso.|
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden dejar de usarse, pero no hay un final verdadero del ciclo de vida de soporte técnico.|Hay un ciclo de vida de fin de soporte técnico para SharePoint Server o SharePoint Foundation, así como para los servidores de SQL subyacentes.|

Si ha decidido crear un nuevo sitio Microsoft 365 y migrará manualmente los datos a él según sea necesario, compruebe las [opciones de Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualización local de SharePoint Server

A partir de SharePoint Server 2019, las actualizaciones deben realizarse *en serie*. No hay ninguna manera de actualizar de SharePoint Server 2010 a SharePoint Server 2016 o a SharePoint 2019 directamente. Ruta de actualización serie:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Tardará tiempo y planeará seguir toda la ruta de acceso de SharePoint 2010 a SharePoint Server 2016. Las actualizaciones implican costos de hardware (SQL servidores también deben actualizarse), software y administración. Además, es posible que sea necesario actualizar o incluso abandonar las personalizaciones. Asegúrese de documentar personalizaciones críticas antes de actualizar la granja de servidores de SharePoint Server.

> [!NOTE]
> Es posible mantener el final del soporte técnico SharePoint granja de servidores de 2010, instalar una granja de SharePoint Server 2016 en hardware nuevo (para que las granjas independientes se ejecuten en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero hay posibles dificultades para estos movimientos manuales, como documentos procedentes de 2010 que tienen una cuenta actual modificada por última vez con el alias de la cuenta que realiza el movimiento manual. Y algunos trabajos deben realizarse con antelación, como volver a crear sitios, subsitios, permisos y estructuras de lista. Asegúrese de limpiar el entorno antes de la actualización. Tenga en cuenta los datos que puede mover al almacenamiento o que ya no necesitan. Esto puede reducir el impacto de la migración. Asegúrese de que la granja existente es funcional antes de actualizar y (ciertamente) antes de retirarse.

No olvide revisar las *rutas de actualización admitidas y no admitidas*:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Si tiene *personalizaciones*, es fundamental planear cada paso de la ruta de migración:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Ventaja local|Desventaja local|
|---|---|
|Control total de todos los aspectos de la granja de SharePoint (y su SQL), desde el hardware del servidor hacia arriba.|Todos los descansos y correcciones son responsabilidad de su empresa. Sin embargo, puede interactuar con Soporte técnico de Microsoft de pago si el producto no ha superado el soporte técnico.|
|Conjunto de características completo de SharePoint Server local con la opción de conectar la granja local a una suscripción SharePoint Online a través de híbrido.|La actualización, las revisiones, las correcciones de seguridad, las actualizaciones de hardware y todo el mantenimiento de SharePoint Server y su granja de SQL se administran de forma local.|
|Acceso completo para obtener más opciones de personalización que con SharePoint Online.|Las [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente en el entorno local.|
|Las pruebas de seguridad y la optimización del rendimiento del servidor se realizan en el entorno local bajo su control.|Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.|
|Los proveedores de soluciones pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).|Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016), como se muestra en SharePoint Online.|
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint Server local.|SharePoint Server local es sensible a los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Actualizar recursos

Empiece comparando los requisitos de hardware y software. Si el entorno actual no cumple los requisitos básicos, es posible que primero tenga que actualizar el hardware de la granja de servidores o los servidores de SQL. 

Puede decidir mover algunos de sus sitios al hardware "evergreen" de SharePoint Online. Una vez que haya realizado la evaluación, siga las rutas de actualización y los métodos admitidos.

- *Requisitos de hardware y software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2013](/sharepoint/install/hardware-software-requirements-2013) |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Límites y límites de software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) |  [SharePoint Server 2016](/sharepoint/install/software-boundaries-limits-2019)

- *Introducción al proceso de actualización para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Creación de una solución híbrida con SharePoint Online y SharePoint Server local

Una configuración híbrida proporciona lo mejor tanto en el entorno local como en línea para algunas necesidades de migración. Puede conectar SharePoint Server 2013, 2016 o 2019 a SharePoint Online para crear una SharePoint híbrida: [obtenga información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Si una granja de servidores SharePoint híbrida es el objetivo de migración, determine qué sitios y usuarios se deben mover en línea y cuáles deben permanecer en el entorno local. Clasificar el contenido de la granja de servidores de SharePoint Server como un impacto alto, medio o bajo para su empresa puede ayudar con esta decisión. Es posible que solo necesite compartir cuentas de usuario para el inicio de sesión y el índice de búsqueda de SharePoint Server con SharePoint Online. Pero es posible que este factor no esté claro hasta que examine cómo se usan los sitios. Si su empresa decide migrar más adelante todo el contenido a SharePoint Online, puede mover todas las cuentas y datos restantes en línea y retirar la granja local. La administración o administración de la granja de SharePoint se realizará a través de Microsoft 365 consolas a partir de ese momento.

Asegúrese de familiarizarse con los tipos de híbridos existentes y de cómo configurar la conexión entre la granja de SharePoint local y la suscripción de Microsoft 365.

|Opción|Descripción|
|---|---|
|[Ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home).|[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) asistencia para la migración es limitada.<br/><br/> Gran parte de la actualización será manual o a través de la API de migración de SPO que se describe en SharePoint [Online y OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).|
|Soporte técnico de Microsoft ingenieros y empleados del centro de datos no tienen acceso de administrador sin restricciones a la suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria.|
|Los asociados pueden ayudar con el trabajo único de migración de los datos a SharePoint Online.||
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden dejar de usarse, pero no hay ningún extremo de soporte técnico verdadero.||

Si ha decidido crear un nuevo sitio Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las [opciones de Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualización local de SharePoint Server

No hay ninguna manera de omitir las versiones de las actualizaciones de SharePoint. Esto significa que las actualizaciones van en serie:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Para tomar toda la ruta de acceso de SharePoint 2007 a SharePoint Server 2016 significará una inversión significativa de tiempo e implicará hardware (también se deben actualizar los servidores de SQL), software y costos de administración. Las personalizaciones tendrán que actualizarse o abandonarse, según la importancia de la característica.

> [!NOTE]
> Es posible mantener el SharePoint granja de servidores de SharePoint 2007, instalar una granja de SharePoint Server 2016 en hardware nuevo (para que las granjas independientes se ejecuten en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (por ejemplo, para descargar y volver a cargar contenido). Pero hay algunos inconvenientes en estos movimientos manuales, como los movimientos de documentos que reemplazan la cuenta de última modificación por el alias de la cuenta que realiza el movimiento manual. Además, se debe realizar mucho trabajo con antelación, como volver a crear sitios, subsitios, permisos y estructuras de lista. En cualquier caso, tenga en cuenta qué datos se pueden mover al almacenamiento o ya no es necesario reducir el impacto de la migración.

Asegúrese de limpiar el entorno antes de la actualización. Asegúrese de que la granja existente es funcional antes de actualizar y, sin duda, antes de retirarse.

No olvide revisar las *rutas de actualización admitidas y no admitidas*:

- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Si tiene *personalizaciones*, es fundamental planear la actualización para cada paso de la ruta de migración:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Profesional local|Con local|
|---|---|
|Control total de todos los aspectos de la granja de SharePoint, desde el hardware del servidor hasta.|Todos los descansos y correcciones son responsabilidad de su empresa. (Pero puede interactuar con Soporte técnico de Microsoft de pago si su producto no ha superado el final del soporte técnico).|
|Conjunto de características completo de SharePoint Server local con la opción de conectar la granja local a una suscripción SharePoint Online a través de híbrido.|Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.|
|Acceso completo para una mayor personalización.|Las [ofertas de cumplimiento de Microsoft](/compliance/regulatory/offering-home) deben configurarse manualmente en el entorno local.|
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se realizan en el entorno local bajo su control.|Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.|
|Los asociados pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).|Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016), como se muestra en SharePoint Online.|
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint Server local.|SharePoint Server local es sensible a los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Actualizar recursos

Empiece sabiendo que cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.

- *Requisitos de hardware y software para*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2013](/sharepoint/install/hardware-software-requirements-2013) |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Límites y límites de software para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) |  [SharePoint Server 2016](/sharepoint/install/software-boundaries-limits-2019)

- *Introducción al proceso de actualización para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creación de una solución híbrida SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el control que ofrece el entorno local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar SharePoint Server 2013 o 2016 a SharePoint Online a través de híbridos. [Más información sobre SharePoint soluciones híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de SharePoint local y la suscripción de Microsoft 365.

Es posible que desee crear un entorno de desarrollo y pruebas de Microsoft 365, que puede configurar con [guías de laboratorio de pruebas](m365-enterprise-test-lab-guides.md). Después de obtener una versión de prueba o comprar Microsoft 365 suscripción, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si quiere migrar el contenido de Mi sitio a OneDrive para la Empresa, mediante el asistente híbrido.

> [!NOTE]
> Para usar la opción híbrida, la granja de SharePoint Server 2010 debe actualizarse primero localmente a SharePoint Server 2013 o 2016. SharePoint Foundation 2010 y SharePoint Foundation 2013 no admiten conexiones híbridas con SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de las opciones para Office cliente y servidores de 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin de la compatibilidad con clientes y servidores de Office 2010 y Windows póster 7.](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster se muestran las distintas rutas de acceso que puede tomar para evitar Office productos de cliente y servidor de 2010 y Windows 7 extremos de soporte técnico, con rutas de acceso preferidas y compatibilidad con opciones en Microsoft 365 Enterprise resaltadas.

También puede [descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este póster e imprimirlo en formato de letra, legal o tabloide (11 x 17).

## <a name="related-articles"></a>Artículos relacionados

[Recursos que le ayudarán a actualizar desde servidores y clientes de Office 2007 o 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Procedimientos recomendados para actualizar de SharePoint 2010 a SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Solucionar problemas de actualización de bases de datos en SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Búsqueda de proveedores de soluciones de Microsoft para ayudar con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)

[Directiva de servicio del producto actualizada para SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Directiva de servicio del producto actualizada para SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)
