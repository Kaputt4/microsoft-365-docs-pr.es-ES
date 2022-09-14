---
title: Hoja de ruta de fin de soporte técnico de Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
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
description: La compatibilidad con Project Server 2010 finaliza el 13 de abril de 2021. Use este artículo como guía para actualizar a Project Online o una versión más reciente de Project Server local.
ms.openlocfilehash: ccf65987547304df5527cca862dbd0467d2f52a4
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670783"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Project Server 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Project Server 2010 finalizará el soporte técnico el **13 de abril de 2021**. Esta fecha se amplió a partir de la fecha de finalización del soporte técnico anterior del 13 de octubre de 2020. Si actualmente usa Project Server 2010, tenga en cuenta que estos productos relacionados tienen las siguientes fechas de finalización de soporte técnico:

|Producto |Fecha de finalización del soporte técnico|
|---|---|
|Project 2010 Standard|13 de octubre de 2020|
|Project 2010 Professional|13 de octubre de 2020|

Para obtener más información sobre cómo llegar al final del soporte técnico, consulte [Actualización desde servidores y productos cliente de Office 2010](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

Casi todos los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores y actualizaciones de seguridad. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Después de que Project Server 2010 finalice el soporte técnico el 13 de abril de 2021, Microsoft ya no proporcionará:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para los problemas que se detectan y que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades detectadas y que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

La instalación de Project Server 2010 continuará ejecutándose después de esta fecha. Pero, debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2010 lo antes posible.

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Las opciones de migración son:

- Migración a Project Online

- Migrar a una versión local más reciente de Project Server (preferiblemente a Project Server 2019)

Estas son las dos rutas de acceso que puede tomar para evitar el fin de la compatibilidad con Project Server 2010.

![Rutas de actualización de Project Server 2010.](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|¿Por qué preferiría migrar a Project Server 2019?|¿Por qué preferiría migrar a Project Online?|
|---|---|
|Las reglas de negocios me impiden operar mi negocio en la nube.  <br/><br/>  Necesito el control de las actualizaciones de mi entorno.|Tengo usuarios móviles o remotos.<br/><br/>  Los costos de migración de servidores locales son una preocupación importante (hardware, software, tiempo y esfuerzo para implementar, etc.). <br/><br/>  Después de la migración, los costos para mantener mi entorno son un problema (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).|

> [!NOTE]
> Para obtener más información sobre las opciones de migración, vea [Recursos para ayudarle a actualizar desde clientes y servidores de Office 2010](upgrade-from-office-2010-servers-and-products.md). Tenga en cuenta que Project Server no admite la configuración híbrida porque Project Server y Project Online no pueden compartir el mismo grupo de recursos.

### <a name="what-are-my-options-for-project-client"></a>¿Cuáles son mis opciones para el cliente de Project?

Si usa Project Profesional 2010 o Project Standard 2010, las opciones son:

- Pasar a una versión más reciente de Project Profesional o Project Standard
- Pasar a una solución en línea, como Project Online o Project para la web

#### <a name="move-to-a-newer-version-of-project-client"></a>Traslado a una versión más reciente del cliente de Project

Si va a migrar desde Project Standard 2010, puede pasar a una versión más reciente de Project Standard (Project Standard 2016 o Project Standard 2019). Se recomienda pasar a la versión más reciente para aprovechar las características más recientes. Migrar a una versión menos actual (Project Standard 2016) también significa que tendrá que volver a migrar antes.

De forma similar, si va a migrar desde Project Profesional 2010, puede pasar a una versión más reciente (Project Profesional 2019 o Project Profesional 2016). De nuevo, pase a la versión más reciente si es posible. Si usa Project Profesional para conectarse a Project Server, asegúrese de migrar a una versión de Project Profesional que se conecte con la versión de Project Server que use.

Project Profesional 2010 los usuarios también pueden migrar al cliente de Project Online Desktop, que es una versión basada en suscripciones de Project Profesional 2019. Se incluye en las suscripciones de Project Plan 3 y Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Traslado a una solución en línea

También puede migrar desde Project Profesional 2010 o Project Standard 2010 a una solución en línea basada en suscripciones de Project. Tanto Project Plan 3 como Plan 5 incluyen Project Online y la oferta en la nube más reciente, [Project for the Web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ambos ofrecen nuevas características y ventajas que merece la pena explorar.

Para obtener más información sobre las características y las licencias, consulte [Descripción del servicio Microsoft Project](/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Consideraciones importantes para migrar desde Project Server 2010

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2010:

- **Obtener ayuda de un proveedor de soluciones de Microsoft** : una actualización de Project Server 2010 puede ser un desafío. Requiere mucha preparación y planificación. Puede ser especialmente difícil si no fuera la persona que configuró originalmente Project Server 2010. Los proveedores de soluciones de Microsoft están disponibles para ayudarle, tanto si tiene previsto migrar a Project Server 2019 como a Project Online. Busque un proveedor de soluciones en el [Centro de proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planear las personalizaciones**: es posible que las personalizaciones del entorno de Project Server 2010 no funcionen al migrar a Project Server 2019 o Project Online. Hay diferencias significativas en la arquitectura de Project Server entre versiones. Además, los sistemas operativos necesarios, los servidores de base de datos y los exploradores web que funcionan con las versiones difieren. Tenga un plan sobre cómo probar o recompilar las personalizaciones en el nuevo entorno. Aproveche esta oportunidad para determinar si todavía se necesitan personalizaciones específicas. Para más información, vea [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tiempo y paciencia** : el planeamiento, la ejecución y las pruebas de actualización tardarán mucho tiempo y esfuerzo, especialmente para una actualización a Project Server 2019. Si va a migrar de Project Server 2010 a Project Server 2019, primero debe migrar a Project Server 2013, comprobar los datos, migrar a Project Server 2016 y, a continuación, a Project Server 2019. Es posible que quiera consultar con un proveedor de soluciones de Microsoft un período de tiempo y un costo estimado para que le ayuden.

## <a name="migrate-to-project-online"></a>Migración a Project Online

Si decide migrar de Project Server 2010 a Project Online, puede seguir estos pasos para migrar manualmente los datos del plan de proyecto:

1. Guarde los planes de proyecto de Project Server 2010 en formato .mpp.

2. Con Project Profesional 2016, Project Profesional 2019 o el cliente de escritorio de Project Online, abra cada archivo .mpp y guárdelo y publíquelo en Project Online.

Puede crear manualmente la configuración de PWA en Project Online (por ejemplo, volver a crear los campos personalizados o calendarios empresariales necesarios). Los proveedores de soluciones de Microsoft también pueden ayudar con este proceso.

Recursos clave:

|Recurso|Descripción|
|---|---|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Configuración y uso de Project Online|
|[Descripción del servicio Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Información sobre los diferentes planes de Project Online disponibles|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migración a una versión local más reciente de Project Server

Creemos firmemente que obtiene el mejor valor y la experiencia del usuario mediante la migración a Project Online. Pero también entendemos que algunas organizaciones necesitan mantener los datos del proyecto en el entorno local. Si decide mantener los datos del proyecto en el entorno local, puede migrar el entorno de Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.

Si no puede migrar a Project Online, se recomienda migrar a Project Server 2019. Project Server 2019 incluye la mayoría de las características clave de las versiones anteriores de Project Server. Y coincide más estrechamente con la experiencia disponible con Project Online, aunque algunas características solo están disponibles en Project Online.

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

> [!NOTE]
> Si está limitado a una solución local y considera la posibilidad de migrar solo a Project Server 2013, tenga en cuenta que esta versión solo tiene unos años más de soporte técnico. Fecha de finalización del soporte técnico para Project Server 2013 con Service Pack 2 13 de octubre de 2023. Para obtener más información sobre las fechas de finalización del soporte técnico, consulte [Directiva de ciclo de vida de productos de Microsoft](/lifecycle/).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Cómo migrar a Project Server 2019?

Las diferencias arquitectónicas entre Project Server 2010 y Project Server 2019 impiden una ruta de migración directa. Por lo tanto, tendrá que migrar los datos de Project Server 2010 a cada versión sucesiva de Project Server hasta que llegue a Project Server 2019. Pasos para actualizar Project Server 2010 a Project Server 2019:

1. Migre a Project Server 2013.

2. Migre de Project Serve 2013 a Project Server 2016.

3. Migre de Project Server 2016 a Project Server 2019.

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

### <a name="step-1-migrate-to-project-server-2013"></a>Paso 1: Migración a Project Server 2013

Para obtener información completa sobre la actualización de Project Server 2010 a Project Server 2013, consulte [Actualización a Project Server 2013](/project/upgrade-to-project-server-2016).

Recursos clave:

- [Introducción al proceso de actualización de Project Server 2013](/project/upgrade-to-project-server-2016)

  Obtenga información general de alto nivel sobre cómo actualizar de Project Server 2010 a Project Server 2013.
- [Planeamiento de la actualización a Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Examine las consideraciones de planeamiento al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema.

- [Las novedades de la actualización de Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) cubren cambios importantes para esta versión, entre los que se incluyen:

  - No hay ninguna actualización local a Project Server 2013. El método de asociación de base de datos es la única manera admitida de actualizar de Project Server 2010 a Project Server 2013.

  - El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una sola base de datos de Project Web App.

  - Tanto SharePoint Server 2013 como Project Server 2013 han cambiado a la autenticación basada en notificaciones de la versión anterior. Si usa la autenticación clásica, tendrá que tener en cuenta esto al actualizar. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Recursos clave:

- [Introducción al proceso de actualización a Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Diagrama del proceso de actualización de Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [La gran consolidación de bases de datos, migración de Project Server 2010 a 2013 en 8 sencillos pasos](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Paso 2: Migración a Project Server 2016

Después de pasar a Project Server 2013 y comprobar que los datos se han migrado correctamente, el siguiente paso es migrar a Project Server 2016.

Para obtener más información, consulte [Actualización a Project Server 2016](/Project/upgrade-to-project-server-2016).

Recursos clave:

- [Introducción al proceso de actualización a Project Server 2016](/Project/overview-of-the-project-server-2016-upgrade-process)

  Comprenda lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Planeación de la actualización a Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Examine las consideraciones de planeamiento que se deben tener en cuenta al actualizar de Project Server 2013 a Project Server 2016.

[Las cosas que debe saber sobre Project Server 2016 actualización](/project/plan-for-upgrade-to-project-server-2016#thingknow) cubren cambios importantes para actualizar a esta versión, entre los que se incluyen:

- Al crear el entorno de Project Server 2016, tenga en cuenta que los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, consulte [Implementación de Project Server 2016](/project/deploy-project-server-2016).

- Los planes de recursos están en desuso en Project Server 2016. Los planes de recursos de Project Server 2013 se migrarán a Resource Engagements en Project Server 2016 y en Project Online. Consulte [Información general: Interacciones de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obtener más información.

### <a name="step-3-migrate-to-project-server-2019"></a>Paso 3: Migración a Project Server 2019

Después de migrar a Project Server 2016 y comprobar que los datos se migraron correctamente, el siguiente paso es migrar los datos a Project Server 2019.

Para obtener información sobre lo que debe hacer para actualizar de Project Server 2016 a Project Server 2019, consulte [Actualización a Project Server 2019](/Project/upgrade-to-project-server-2016).

Recursos clave:

- [Introducción al proceso de actualización de Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Obtenga un conocimiento de alto nivel de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Plan de actualización a Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Examine las consideraciones de planeamiento para actualizar de Project Server 2016 a Project Server 2019.

- [Cosas que necesita saber sobre la actualización de Project Server 2019](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Obtenga información sobre los cambios importantes para actualizar a esta versión, entre los que se incluyen:

  - El proceso de actualización migrará los datos de la base de datos de Project Server 2016 a la base de datos de contenido de SharePoint Server 2019.  Project Server 2019 ya no creará su propia base de datos de Project Server en la granja de servidores de SharePoint Server.

  - Después de la actualización, tenga en cuenta varios cambios en Project Web App.  Para obtener más información, consulte [Novedades de Project Server 2019](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Otros recursos**:

- [Project Online Descripciones del servicio](/office365/servicedescriptions/project-online-service-description/project-online-service-description): consulte las características de administración de carteras incluidas con Project Server 2016 y Project Online Premium.

- [Guía de migración de Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de las opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7.](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster se muestran las distintas rutas de acceso que puede tomar para evitar el fin de la compatibilidad con los productos de cliente y servidor de Office 2010 y Windows 7, con rutas de acceso preferidas y compatibilidad con opciones en Microsoft 365 Enterprise resaltadas.

También puede [descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este póster e imprimirlo en formato de letra, legal o tabloide (11 x 17).

## <a name="related-topics"></a>Temas relacionados

[Actualización desde SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Actualizar los clientes y servidores de Office 2010](upgrade-from-office-2010-servers-and-products.md)
