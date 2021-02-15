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
description: Busque información y recursos para actualizar desde SharePoint 2010 y SharePoint Server 2010. El soporte técnico para ambos finaliza el 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519768"
---
# <a name="upgrading-from-sharepoint-2010"></a>Actualización desde SharePoint 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft SharePoint 2010 y SharePoint Server 2010 finalizarán el soporte técnico el 13 de abril de **2021.** En este artículo se proporcionan recursos para ayudarle a migrar los datos existentes de SharePoint Server 2010 a SharePoint Online en Microsoft 365 o actualizar el entorno local de SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>¿Qué *es el final del soporte?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, entre otros. Después de la fecha de finalización del soporte técnico, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá más actualizaciones, revisiones o correcciones para el producto (incluidas revisiones o correcciones de seguridad). El Soporte técnico de Microsoft habrá cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes.

Cuando finalice la compatibilidad con SharePoint Server 2010, elimine los datos que ya no necesite antes de actualizar el producto y migrar los datos importantes.

> [!NOTE]
> El ciclo de vida del software suele durar diez años desde la versión inicial. [Los proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) pueden ayudarle a actualizar a la siguiente versión del software o migrar a la migración de Microsoft 365 (o ambos). Asegúrese de conocer también las fechas de finalización del soporte técnico para las tecnologías subyacentes críticas, especialmente para la versión de Microsoft SQL Server que está usando con SharePoint. Para obtener más información, consulte [Directiva de ciclo de vida fijo.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en las que finaliza el soporte técnico en el sitio [ciclo de vida del producto.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planee las actualizaciones o migraciones pensando en estas fechas. Recuerda que el *producto no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se revisión después de esa fecha, querrás planear una transición sin problemas a la siguiente versión del producto.

Esta matriz ayuda a trazar un curso entre las opciones de migración:

|Producto de fin de soporte técnico|Bueno |Procedimientos|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||Entorno híbrido de SharePoint Server 2013 con SharePoint Online|SharePoint Server 2016 (local)|
|||Búsqueda híbrida en la nube de SharePoint|

Si elige una opción en el extremo bajo de la escala (buena), tendrá que empezar a planear otra actualización poco después de la migración desde SharePoint Server 2010.

Estas son las tres rutas que puede seguir para evitar el fin de la compatibilidad con SharePoint Server 2010.

![Rutas de actualización de SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> El fin de soporte técnico para SharePoint Server 2010 y SharePoint Foundation 2010 está programado actualmente para el 13 de abril de 2021. Pero asegúrese de comprobar el sitio ciclo [de vida del producto](https://support.microsoft.com/lifecycle) para las fechas más actuales.

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

SharePoint Server 2013 y SharePoint Foundation 2013 se pueden instalar localmente en sus propios servidores. También puede usar SharePoint Online, que es un servicio en línea que forma parte de Microsoft 365. Puede elegir:

- Migrar a SharePoint Online.

- Actualice SharePoint Server o SharePoint Foundation localmente.

- Realice las dos cosas anteriores.

- Implementar una [solución híbrida de SharePoint.](https://docs.microsoft.com/sharepoint/hybrid/hybrid)

Tenga en cuenta los costos ocultos del mantenimiento de una granja de servidores, incluido el mantenimiento o la migración de personalizaciones y actualización de hardware. Si ha tenido en cuenta estos factores, será más fácil actualizar localmente. Si ejecuta la granja de servidores en servidores de SharePoint heredados sin una personalización intensa, podría beneficiarse de una migración planeada a SharePoint Online. Para un entorno local de SharePoint Server, también puede considerar mover algunos datos en SharePoint Online para reducir la sobrecarga de administración de hardware.

> [!NOTE]
> Los administradores de SharePoint pueden crear una suscripción a Microsoft 365, configurar nuevos sitios de SharePoint Online y, a continuación, cortar de SharePoint Server 2010 de forma limpia, llevando solo documentos esenciales a los sitios nuevos. A continuación, los datos restantes se pueden purgar del sitio de SharePoint Server 2010 en archivos locales.

|SharePoint Online|SharePoint Server local|
|---|---|
|Alto costo en el tiempo (plan/ejecución/verificación)|Alto costo en el tiempo (plan/ejecución/verificación)|
|Menor coste en fondos (sin compras de hardware)|Mayor coste en fondos (compras de hardware)|
|Costo único en la migración|Costo único repetido por migración futura|
|Bajo costo total de propiedad/mantenimiento|Alto costo total de propiedad/mantenimiento|

Un cambio único a Microsoft 365 tendrá un costo mayor mientras organiza los datos y decide qué ir a la nube y qué dejar. Pero después de migrar los datos, las actualizaciones futuras serán automáticas, ya que ya no tendrás que administrar las actualizaciones de hardware y software. Además, el tiempo de espera de la granja de servidores se realizará mediante un contrato de nivel de [servicio (SLA) de Microsoft.](https://go.microsoft.com/fwlink/?linkid=843153)

### <a name="migrate-to-sharepoint-online"></a>Migrar a SharePoint Online

Asegúrese de que SharePoint Online ofrece todas las características que necesita. Vea [la descripción del servicio de SharePoint.](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)

No puede migrar directamente de SharePoint Server 2010 (o SharePoint Foundation 2010) a SharePoint Online. Gran parte del trabajo de migración es manual. Pero esta fase le ofrece la oportunidad de podar datos y sitios que ya no son necesarios antes del traslado. Puede archivar otros datos en el almacenamiento. 

Recuerde que SharePoint Server 2010 y SharePoint Foundation 2010 no dejarán de funcionar al final del soporte técnico. Por lo tanto, los administradores pueden tener un período en el que SharePoint aún se está ejecutando si sus clientes olvidan mover algunos de sus datos.

Si actualiza a SharePoint Server 2013 o SharePoint Server 2016 y decide colocar datos en SharePoint Online, puede usar la API de migración de [SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) para migrar información a OneDrive para la Empresa.

|Ventaja de SharePoint Online|Desventaja de SharePoint Online|
|---|---|
|Microsoft proporciona hardware SPO y toda la administración de hardware.|Las características disponibles pueden diferir entre SharePoint Server local y SPO.|
|Es el administrador global de la suscripción y puede asignar administradores a sitios de SPO.|Algunas acciones disponibles para un administrador de la granja de servidores en SharePoint Server local no existen (o no son necesarias) en el rol de administrador de SharePoint en Microsoft 365. Sin embargo, Administración de SharePoint, Administración de la colección de sitios y Propiedad del sitio son locales para su organización.|
|Microsoft aplica revisiones, correcciones y actualizaciones a hardware y software subyacentes, incluidos los SQL en los que se ejecuta SharePoint Online.|Dado que no hay acceso al sistema de archivos subyacente en el servicio, la personalización es limitada.|
|Microsoft publica contratos [de nivel de servicio](https://go.microsoft.com/fwlink/?linkid=843153) y se mueve rápidamente para resolver incidentes de nivel de servicio.|El servicio de SharePoint Online automatiza las opciones de copia de seguridad y restauración y otras opciones de recuperación. Las copias de seguridad se sobrescriben si no se usan.|
|Microsoft lleva a cabo continuamente las pruebas de seguridad y el ajuste del rendimiento del servidor en el servicio.|El servicio instala los cambios en la interfaz de usuario y otras características de SharePoint y es posible que deba activarse o desactivarse.|
|Microsoft 365 cumple muchos estándares del sector: [ofertas de cumplimiento de Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)|[La asistencia de FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para la migración es limitada.  <br/> Gran parte de la actualización será manual o a través de la API de migración de SPO descrita en la guía básica de contenido de migración de [SharePoint Online y OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)|
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria para la actualización.|
|Los proveedores de soluciones pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.|No todos los cambios en SharePoint Online están bajo su control. Después de la migración, las diferencias de diseño en menús, bibliotecas y otras características pueden afectar temporalmente a la facilidad de uso.|
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden estar en desuso, pero no existe un verdadero final del ciclo de vida de soporte técnico.|Hay un ciclo de vida de fin de soporte técnico para SharePoint Server o SharePoint Foundation, así como servidores SQL subyacentes.|

Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las opciones [de Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

A partir de SharePoint Server 2019, las actualizaciones deben *realizarse en serie.* No hay ninguna forma de actualizar de SharePoint Server 2010 a SharePoint Server 2016 o a SharePoint 2019 directamente. Ruta de actualización en serie:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Llevará tiempo y planeación seguir la ruta completa de SharePoint 2010 a SharePoint Server 2016. Las actualizaciones implican costos de hardware (SQL también deben actualizarse), software y administración. Además, es posible que las personalizaciones deban actualizarse o incluso abandonarse. Asegúrese de documentar personalizaciones críticas antes de actualizar la granja de servidores de SharePoint Server.

> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2010 de fin de soporte técnico, instalar una granja de servidores de SharePoint Server 2016 en nuevo hardware (por lo que las granjas independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (para descargar y volver a cargar contenido, por ejemplo). Pero hay posibles dificultades para estos movimientos manuales, como documentos procedentes de 2010 que tienen una cuenta actual de última modificación con el alias de la cuenta que realiza el movimiento manual. Y parte del trabajo debe realizarse con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. Asegúrese de limpiar el entorno antes de la actualización. Ten en cuenta qué datos puedes mover al almacenamiento o ya no necesitas. Esto puede reducir el impacto de la migración. Asegúrese de que la granja de servidores existente funciona antes de actualizar y (ciertamente) antes de retirarla.

Recuerde revisar las rutas de actualización admitidas *y no admitidas:*

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Si tiene *personalizaciones,* es fundamental que planee cada paso de la ruta de migración:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Ventaja local|Desventaja local|
|---|---|
|Control total de todos los aspectos de la granja de servidores de SharePoint (y su SQL), desde el hardware del servidor hacia arriba.|Todas las interrupciones y correcciones son responsabilidad de su empresa. Pero puedes participar en el soporte técnico de Microsoft de pago si tu producto no ha pasado el final del soporte técnico.|
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción de SharePoint Online a través de una implementación híbrida.|Las actualizaciones, revisiones, correcciones de seguridad, actualizaciones de hardware y todo el mantenimiento de SharePoint Server y su granja de servidores SQL se administran localmente.|
|Acceso completo para obtener más opciones de personalización que con SharePoint Online.|[Las ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.|
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.|Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.|
|Los proveedores de soluciones pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).|Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.|
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint Server local.|SharePoint Server local es sensible a los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Recursos de actualización

Comience por comparar los requisitos de hardware y software. Si el entorno actual no cumple los requisitos básicos, es posible que primero deba actualizar el hardware de la granja de servidores o de SQL servidores. 

Es posible que decida mover algunos de sus sitios al hardware "perenní" de SharePoint Online. Una vez que haya realizado la evaluación, siga los métodos y rutas de actualización admitidos.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Límites y límites del software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Información general sobre el proceso de actualización para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Crear una solución híbrida con SharePoint Online y SharePoint Server local

Una configuración híbrida proporciona lo mejor de local y en línea para algunas necesidades de migración. Puede conectar granjas de servidores de SharePoint Server 2013, 2016 o 2019 a SharePoint Online para crear un entorno híbrido de SharePoint: obtenga información sobre las soluciones híbridas de [SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Si una granja de servidores híbrida de SharePoint Server es su objetivo de migración, figure qué sitios y usuarios se moverá en línea y cuáles deben permanecer en el entorno local. Clasificar el contenido de la granja de servidores de SharePoint Server como impacto alto, medio o bajo en su empresa puede ayudarle con esta decisión. Es posible que solo necesite compartir cuentas de usuario para el inicio de sesión y el índice de búsqueda de SharePoint Server con SharePoint Online. Sin embargo, es posible que este factor no sea claro hasta que vea cómo se usan los sitios. Si su empresa decide más adelante migrar todo el contenido a SharePoint Online, puede mover todas las cuentas y datos restantes en línea y retirar la granja de servidores local. La administración y administración de la granja de servidores de SharePoint se realizará a través de las consolas de Microsoft 365 a partir de ese momento.

Asegúrese de familiarizarse con los tipos de híbridos existentes y de configurar la conexión entre la granja de servidores de SharePoint local y la suscripción de Microsoft 365.

|Opción|Description|
|---|---|
|[Ofertas de cumplimiento de Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)|[La asistencia de FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para la migración es limitada.<br/><br/> Gran parte de la actualización será manual o a través de la API de migración de SPO descrita en la guía básica de contenido de migración de [SharePoint Online y OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)|
|Los ingenieros de soporte técnico de Microsoft y los empleados del centro de datos no tienen acceso de administrador sin restricciones a su suscripción.|Puede haber costos adicionales si es necesario actualizar la infraestructura de hardware para admitir la versión más reciente de SharePoint o si se requiere una granja de servidores secundaria.|
|Los asociados pueden ayudarle con el trabajo único de migrar los datos a SharePoint Online.||
|Los productos en línea se actualizan automáticamente en todo el servicio. Las características pueden estar en desuso, pero no existe un verdadero final de soporte técnico.||

Si ha decidido crear un nuevo sitio de Microsoft 365 y migrar manualmente los datos a él según sea necesario, compruebe las opciones de [Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Actualizar SharePoint Server local

No hay ninguna forma de omitir versiones en las actualizaciones de SharePoint. Esto significa que las actualizaciones se realizarán en serie:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Tomar toda la ruta de SharePoint 2007 a SharePoint Server 2016 supondrá una gran inversión de tiempo e implicará hardware (los servidores SQL también deben actualizarse), software y costos de administración. Las personalizaciones tendrán que actualizarse o abandonarse, según la importancia de la característica.

> [!NOTE]
> Es posible mantener la granja de servidores de SharePoint 2007 de fin de vida, instalar una granja de servidores de SharePoint Server 2016 en hardware nuevo (por lo que las granjas independientes se ejecutan en paralelo) y, a continuación, planear y ejecutar una migración manual de contenido (para descargar y volver a cargar contenido, por ejemplo). Pero hay algunos inconvenientes en estos movimientos manuales, como los movimientos de documentos que reemplazan la cuenta modificada por el alias de la cuenta que realiza el movimiento manual. Y es necesario realizar mucho trabajo con antelación, como recrear sitios, subsitios, permisos y estructuras de lista. En cualquier caso, considere qué datos puede mover al almacenamiento o ya no necesita reducir el impacto de la migración.

Asegúrese de limpiar el entorno antes de la actualización. Asegúrese de que la granja de servidores existente funciona antes de actualizar y, desde luego, antes de retirarla.

Recuerde revisar las rutas de actualización admitidas *y no admitidas:*

- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Si tiene *personalizaciones,* es fundamental planear la actualización para cada paso de la ruta de migración:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Profesional local|Con local|
|---|---|
|Control total de todos los aspectos de la granja de servidores de SharePoint, desde el hardware del servidor hacia arriba.|Todas las interrupciones y correcciones son responsabilidad de su empresa. (Pero puedes participar en el soporte técnico de Microsoft de pago si el producto no ha pasado el final del soporte técnico).|
|Conjunto completo de características de SharePoint Server local con la opción de conectar la granja de servidores local a una suscripción de SharePoint Online a través de una implementación híbrida.|Actualización, revisiones, correcciones de seguridad y todo el mantenimiento de SharePoint Server administrado localmente.|
|Acceso completo para una mayor personalización.|[Las ofertas de cumplimiento de Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) deben configurarse manualmente de forma local.|
|Las pruebas de seguridad y el ajuste del rendimiento del servidor se llevan a cabo en las instalaciones bajo su control.|Microsoft 365 puede hacer que las características estén disponibles para SharePoint Online que no interoperan con SharePoint Server local.|
|Los asociados pueden ayudar a migrar datos a la siguiente versión de SharePoint Server (y versiones posteriores).|Los sitios de SharePoint Server no usarán automáticamente certificados [SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como se ve en SharePoint Online.|
|Control total de las convenciones de nomenclatura, copia de seguridad y restauración y otras opciones de recuperación en SharePoint Server local.|SharePoint Server local es sensible a los ciclos de vida del producto.|

### <a name="upgrade-resources"></a>Recursos de actualización

Empiece por saber que cumple los requisitos de hardware y software y, a continuación, siga los métodos de actualización admitidos.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Límites y límites del software para:*

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Información general sobre el proceso de actualización para:*

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Crear una solución híbrida de SharePoint entre SharePoint Online y local

Si la respuesta a sus necesidades de migración está en algún lugar entre el control que ofrece la implementación local y el menor costo de propiedad que ofrece SharePoint Online, puede conectar granjas de servidores de SharePoint Server 2013 o 2016 a SharePoint Online a través de entornos híbridos. [Obtenga información sobre las soluciones híbridas de SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Si decide que una granja híbrida de SharePoint Server beneficiará a su empresa, familiarícese con los tipos de híbridos existentes y cómo configurar la conexión entre la granja de Servidores de SharePoint local y su suscripción a Microsoft 365.

Es posible que desee crear un entorno de desarrollo y pruebas de Microsoft 365, que puede configurar con guías [del entorno de pruebas.](m365-enterprise-test-lab-guides.md) Después de obtener una suscripción de prueba o de adquirir Microsoft 365, puede crear las colecciones de sitios, webs y bibliotecas de documentos en SharePoint Online a las que puede migrar datos. Puede migrar manualmente, mediante la API de migración o, si desea migrar el contenido de Mi sitio a OneDrive para la Empresa, a través del asistente híbrido.

> [!NOTE]
> Para usar la opción híbrida, la granja de servidores de SharePoint Server 2010 primero debe actualizarse localmente a SharePoint Server 2013 o 2016. SharePoint Foundation 2010 y SharePoint Foundation 2013 no admiten conexiones híbridas con SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de las opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster se muestran las distintas rutas que puede seguir para evitar los productos de cliente y servidor de Office 2010 y el final de soporte técnico de Windows 7, con las rutas de acceso preferidas y los soportes de opción resaltados en Microsoft 365 Enterprise.

También puede descargar [este](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) póster e imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="related-articles"></a>Artículos relacionados

[Recursos para ayudarle a actualizar desde clientes y servidores de Office 2007 o 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Procedimientos recomendados para actualizar de SharePoint 2010 a SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Solucionar problemas de actualización de bases de datos en SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Buscar proveedores de soluciones de Microsoft para ayudarle con la actualización](https://go.microsoft.com/fwlink/?linkid=841249)

[Directiva de servicio del producto actualizada para SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Directiva de servicio del producto actualizada para SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
