---
title: Plan de fin de soporte de Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: El soporte técnico finaliza para Project Server 2010 finaliza el 13 de abril de 2021. Use este artículo como guía para actualizar a Project online o a una versión más reciente de Project Server local.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519707"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Project Server 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Project Server 2010 se desplazará al final del soporte técnico el **13 de abril de 2021**. Esta fecha se amplió a partir de la fecha de finalización de soporte previa del 13 de octubre de 2020. Si actualmente usa Project Server 2010, tenga en cuenta que estos productos relacionados tienen las siguientes fechas de finalización de soporte:

|Producto |Fecha de finalización del soporte técnico|
|---|---|
|Proyecto 2010 estándar|13 de octubre de 2020|
|Proyecto 2010 Professional|13 de octubre de 2020|

Para obtener más información acerca de cómo llegar al final del soporte técnico, consulte [actualización de los servidores y productos cliente de Office 2010](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>¿Qué significa el *fin de soporte* ?

Casi todos los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores y actualizaciones de seguridad. Este ciclo de vida suele durar diez años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Después de que Project Server 2010 llegue a su fin de soporte el 13 de abril de 2021, Microsoft dejará de proporcionar:

- Soporte técnico para los problemas que pueden surgir.

- Correcciones de errores para problemas detectados y que pueden afectar a la estabilidad y la usabilidad del servidor.

- Revisiones de seguridad para las vulnerabilidades detectadas y que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.

- Las actualizaciones de zona horaria.

La instalación de Project Server 2010 seguirá ejecutándose después de esta fecha. Pero, debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2010 lo antes posible.

## <a name="what-are-my-options"></a>¿Qué opciones tengo?

Las opciones de migración son:

- Migrar a Project online

- Migrar a una versión local más reciente de Project Server (preferiblemente Project Server 2019)

Estas son las dos rutas que puede realizar para evitar la finalización de la compatibilidad con Project Server 2010.

![Rutas de actualización de Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|¿Por qué preferiría migrar a Project Server 2019?|¿Por qué preferiría migrar a Project online?|
|---|---|
|Las reglas de negocios delimitan el funcionamiento de mi empresa en la nube.  <br/><br/>  Necesito el control de las actualizaciones de mi entorno.|Tengo usuarios móviles o remotos.<br/><br/>  Los costos de migración de los servidores locales son una preocupación importante (hardware, software, tiempo y esfuerzo para implementar, etc.). <br/><br/>  Después de la migración, los costos de mantenimiento de mi entorno son un problema (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).|

> [!NOTE]
> Para obtener más información acerca de las opciones de migración, vea [recursos que le ayudarán a actualizar desde los servidores y clientes de Office 2010](upgrade-from-office-2010-servers-and-products.md). Tenga en cuenta que Project Server no admite la configuración híbrida porque Project Server y Project online no pueden compartir el mismo grupo de recursos.

### <a name="what-are-my-options-for-project-client"></a>¿Cuáles son mis opciones para el cliente de Project?

Si está usando Project Professional 2010 o Project Standard 2010, las opciones son:

- Desplazarse a una versión más reciente de Project Professional o Project Standard
- Mover a una solución en línea, como Project online o Project para la web

#### <a name="move-to-a-newer-version-of-project-client"></a>Pasar a una versión más reciente del cliente de Project

Si va a migrar desde Project Standard 2010, puede pasar a una versión más reciente de Project Standard (Project Standard 2016 o Project Standard 2019). Le recomendamos que se mueva a la versión más reciente para aprovechar las características más recientes. Migrar a una versión menos reciente (el proyecto estándar 2016) también significa que tendrá que migrar de nuevo antes.

De forma similar, si va a migrar desde Project Professional 2010, puede pasar a una versión más reciente (Project Professional 2019 o Project Professional 2016). De nuevo, desplácese a la versión más reciente si es posible. Si usa Project Professional para conectarse a Project Server, asegúrese de migrar a una versión de Project Professional que se conecte con la versión de Project Server que use.

Project Professional 2010 los usuarios también pueden migrar al cliente de escritorio de Project online, que es una versión basada en la suscripción de Project Professional 2019. Se incluye en las suscripciones a Project Plan 3 y Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Mover a una solución en línea

También puede migrar desde Project Professional 2010 o Project Standard 2010 a una solución en línea basada en la suscripción a un proyecto. El plan de proyecto 3 y el plan 5 incluyen Project online y la última oferta [de nube, Project para la web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ambos ofrecen nuevas características y ventajas que merece la pena explorar.

Para obtener más información acerca de las características y licencias, vea [Descripción del servicio de Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Consideraciones importantes para la migración desde Project Server 2010

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2010:

- **Obtener ayuda de un proveedor de soluciones de Microsoft** -una actualización desde Project Server 2010 puede ser un reto. Requiere una mayor preparación y planeación. Puede ser especialmente difícil si no es la persona que configuró Project Server 2010 en un principio. Los proveedores de soluciones de Microsoft están disponibles para ayudarle, independientemente de si planea migrar a Project Server 2019 o a Project online. Busque un proveedor de soluciones en el [centro de Microsoft Solution Provider](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planeación de las personalizaciones** : es posible que las personalizaciones del entorno de project Server 2010 no funcionen al migrar a project Server 2019 o Project online. Existen diferencias significativas en la arquitectura de Project Server entre versiones. Además, los sistemas operativos, los servidores de bases de datos y los exploradores Web que funcionan con las versiones difieren. Tenga un plan sobre cómo probar o volver a crear las personalizaciones en el nuevo entorno. Aproveche esta oportunidad para determinar si todavía se necesitan personalizaciones específicas. Para más información, vea [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- La planeación, ejecución y pruebas de actualización del **tiempo y la paciencia** tendrán un tiempo y un esfuerzo considerables, especialmente para la actualización a Project Server 2019. Si va a migrar de Project Server 2010 a Project Server 2019, primero debe migrar a Project Server 2013, comprobar los datos y, a continuación, migrar a Project Server 2016 y, a continuación, a Project Server 2019. Es posible que desee consultar con un proveedor de soluciones de Microsoft para obtener ayuda sobre un período de tiempo y un costo estimado.

## <a name="migrate-to-project-online"></a>Migrar a Project online

Si elige migrar de Project Server 2010 a Project online, puede seguir estos pasos para migrar manualmente los datos del plan del proyecto:

1. Guarde los planes del proyecto de Project Server 2010 en formato. MPP.

2. Con Project Professional 2016, Project Professional 2019 o el cliente de escritorio de Project online, abra cada archivo. MPP y, a continuación, guárdelo y publíquelo en Project online.

Puede crear manualmente la configuración de PWA en Project online (por ejemplo, volver a crear los campos personalizados o los calendarios de empresa necesarios). Los proveedores de soluciones de Microsoft también pueden ayudarle con este proceso.

Recursos clave:

|Recurso|Descripción|
|---|---|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Cómo configurar y usar Project online|
|[Descripción del servicio Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Información sobre los distintos planes de Project online disponibles|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar a una versión local más reciente de Project Server

Creemos que se obtiene el mejor valor y la mejor experiencia del usuario al migrar a Project online. Pero también sabemos que algunas organizaciones necesitan mantener los datos del proyecto de forma local. Si opta por mantener los datos de proyecto locales, puede migrar el entorno de Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.

Si no puede migrar a Project online, le recomendamos que migre a Project Server 2019. Project Server 2019 incluye la mayoría de las características clave de versiones anteriores de Project Server. Además, se ajusta mejor a la experiencia disponible en Project online, aunque algunas características solo están disponibles en Project online.

Una vez completada cada migración, asegúrese de que los datos se han migrado correctamente.

> [!NOTE]
> Si se limita a una solución local y se considera solo migrar a Project Server 2013, tenga en cuenta que esta versión solo tiene unos cuantos años de ayuda a la izquierda. La fecha de finalización del soporte técnico de Project Server 2013 con Service Pack 2, 13 de octubre de 2023. Para obtener más información acerca de las fechas de fin de soporte, consulte [Directiva de ciclo de vida del producto de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>¿Cómo migro a Project Server 2019?

Las diferencias de arquitectura entre Project Server 2010 y Project Server 2019 impiden una ruta de migración directa. Por lo tanto, tendrá que migrar los datos de Project Server 2010 a cada una de las versiones sucesivas de Project Server hasta llegar a Project Server 2019. Pasos para actualizar Project Server 2010 a Project Server 2019:

1. Migrar a Project Server 2013.

2. Migrar desde Project atender 2013 a Project Server 2016.

3. Migrar de Project Server 2016 a Project Server 2019.

Una vez completada cada migración, asegúrese de que los datos se han migrado correctamente.

### <a name="step-1-migrate-to-project-server-2013"></a>Paso 1: migrar a Project Server 2013

Para obtener información detallada acerca de la actualización de Project Server 2010 a Project Server 2013, consulte [Upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Recursos clave:

- [Información general sobre el proceso de actualización de Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Obtenga información general de alto nivel sobre cómo actualizar de Project Server 2010 a Project Server 2013.
- [Planeación de la actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Consulte consideraciones de planeación al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema.

- Las novedades [de la actualización de Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) cubren los cambios importantes de esta versión, entre los que se incluyen:

   - No hay una actualización inmediata a Project Server 2013. El método de base de datos adjunta es la única forma admitida de actualizar de Project Server 2010 a Project Server 2013.

   - El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una sola base de datos de Project Web App.

   - Tanto SharePoint Server 2013 como Project Server 2013 cambian a la autenticación basada en notificaciones de la versión anterior. Si está usando la autenticación clásica, tendrá que tener esto al actualizar. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Recursos clave:

- [Introducción al proceso de actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagrama del proceso de actualización de Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [La gran consolidación de la base de datos, la migración de Project Server 2010 a 2013 en 8 pasos sencillos](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Paso 2: migrar a Project Server 2016

Después de pasar a Project Server 2013 y comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar a Project Server 2016.

Para obtener más información, vea [actualizar a Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Recursos clave:

- [Introducción al proceso de actualización a Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Comprenda lo que necesita hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Planeación de la actualización a Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Consulte las consideraciones de planeación que se deben tomar al actualizar de Project Server 2013 a Project Server 2016.

Lo [que debe saber sobre la actualización de Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) cubre cambios importantes para actualizar a esta versión, que incluyen:

- Al crear su entorno de Project Server 2016, tenga en cuenta que los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, vea [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Los planes de recursos están en desuso en Project Server 2016. Los planes de recursos de Project Server 2013 se migrarán a las negociaciones de recursos en Project Server 2016 y Project online. Para obtener más información, vea [información general: negociaciones de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) .

### <a name="step-3-migrate-to-project-server-2019"></a>Paso 3: migrar a Project Server 2019

Después de migrar a Project Server 2016 y comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar los datos a Project Server 2019.

Para obtener información sobre lo que necesita hacer para actualizar de Project Server 2016 a Project Server 2019, consulte [Upgrade to Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Recursos clave:

- [Información general sobre el proceso de actualización de Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Obtenga información de alto nivel sobre lo que necesita hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Planeación de la actualización a Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Consulte consideraciones de planeación para la actualización de Project Server 2016 a Project Server 2019.

- [Cosas que debe saber sobre la actualización de Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Obtenga información sobre los cambios importantes para actualizar a esta versión, que incluye:

   - El proceso de actualización migrará los datos de la base de datos de Project Server 2016 a la base de datos de contenido de SharePoint Server 2019.  Project Server 2019 ya no creará su propia base de datos de Project Server en la granja de servidores de SharePoint.

   - Después de la actualización, tenga en cuenta varios cambios en Project Web App.  Para obtener más información, consulte [what's New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Otros recursos**:

- [Descripciones de servicios de Project online](https://go.microsoft.com/fwlink/p/?linkid=841280): vea las características de administración de cartera incluidas en project Server 2016 y Project online Premium.

- [Guía de migración de Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster se ilustran las distintas rutas que puede realizar para evitar el fin de la compatibilidad con productos de cliente y servidor de Office 2010 y Windows 7, con las rutas de preferencia y la compatibilidad con opciones de Microsoft 365 Enterprise resaltado.

También puede [Descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este póster e imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="related-topics"></a>Temas relacionados

[Actualización desde SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Actualizar los clientes y servidores de Office 2010](upgrade-from-office-2010-servers-and-products.md)
