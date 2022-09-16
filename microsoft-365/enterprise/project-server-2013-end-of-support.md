---
title: Hoja de ruta de fin de soporte técnico de Project Server 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: El soporte técnico finaliza para Project Server 2013 el 11 de abril de 2023. Use este artículo como guía para actualizar a Project Online o una versión más reciente de Project Server local.
ms.openlocfilehash: 5d7a31ebcb43cb157383ab0faf5ecfe5dd7c5940
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67736374"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>Hoja de ruta de finalización del soporte técnico de Project Server 2013

Project Server 2013 finalizará el soporte técnico el **11 de abril de 2023**. Si actualmente usa Project Server 2013, tenga en cuenta que la aplicación de escritorio de Project 2013 también tiene las mismas fechas de finalización de soporte técnico.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

Casi todos los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores y actualizaciones de seguridad. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Después de que Project Server 2013 finalice el soporte técnico el 11 de abril de 2023, Microsoft ya no proporcionará:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para los problemas que se detectan y que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades detectadas y que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

La instalación de Project Server 2013 continuará ejecutándose después de esta fecha. Sin embargo, debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2013 lo antes posible.

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Las opciones de migración son:

- Migración a Project Online

- Migración a una versión local más reciente de Project Server (preferiblemente Project Server Edición de Suscripción)

|¿Por qué preferiría migrar a Project Server 2019?|¿Por qué preferiría migrar a Project Online?|
|---|---|
|Las reglas de negocios me impiden operar mi negocio en la nube.  <br/><br/>  Necesito el control de las actualizaciones de mi entorno.|Tengo usuarios móviles o remotos.<br/><br/>  Los costos de migración de servidores locales son una preocupación importante (hardware, software, tiempo y esfuerzo para implementar, etc.). <br/><br/>  Después de la migración, los costos para mantener mi entorno son un problema (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).|

> [!NOTE]
> Project Server no admite la configuración híbrida porque Project Server y Project Online no pueden compartir el mismo grupo de recursos.

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>Consideraciones importantes para migrar desde Project Server 2013

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2013:

- **Obtener ayuda de un proveedor de soluciones de Microsoft** : una actualización de Project Server 2013 puede ser un desafío. Requiere mucha preparación y planificación. Puede ser especialmente difícil si no fuera la persona que configuró originalmente Project Server 2013. Los proveedores de soluciones de Microsoft están disponibles para ayudarle, ya sea que planee migrar a Project Server Edición de Suscripción o a Project Online. Busque un proveedor de soluciones en el [Centro de proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Tiempo y paciencia**: el planeamiento, la ejecución y las pruebas de actualización tardarán mucho tiempo y esfuerzo, especialmente para una actualización a Project Server Edición de Suscripción. Si va a migrar de Project Server 2013 a Project Server Edición de Suscripción, primero debe migrar a Project Server 2016, comprobar los datos y, a continuación, Project Server Edición de Suscripción. Es posible que quiera consultar con un proveedor de soluciones de Microsoft un período de tiempo y un costo estimado para que le ayuden.

## <a name="migrate-to-project-online"></a>Migración a Project Online

Si decide migrar de Project Server 2013 a Project Online, puede seguir estos pasos para migrar manualmente los datos del plan de proyecto:

1. Guarde los planes de proyecto de Project Server 2013 en formato .mpp.

2. Con Project Profesional 2016, Project Profesional 2019 o el cliente de escritorio de Project Online, abra cada archivo .mpp y guárdelo y publíquelo en Project Online.

Puede crear manualmente la configuración de PWA en Project Online (por ejemplo, volver a crear los campos personalizados o calendarios empresariales necesarios). Los proveedores de soluciones de Microsoft también pueden ayudar con este proceso.

Recursos clave:

|Recurso|Descripción|
|---|---|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Configuración y uso de Project Online|
|[Descripción del servicio Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Información sobre los diferentes planes de Project Online disponibles|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migración a una versión local más reciente de Project Server

Creemos firmemente que obtiene el mejor valor y la experiencia del usuario mediante la migración a Project Online. Pero también entendemos que algunas organizaciones necesitan mantener los datos del proyecto en el entorno local. Si decide mantener los datos del proyecto en el entorno local, puede migrar el entorno de Project Server 2013 a Project Server 2016, Project Server 2019 o Project Server Edición de Suscripción.

Si no puede migrar a Project Online, se recomienda migrar a Project Server Edición de Suscripción que incluye la mayoría de las características clave de las versiones anteriores de Project Server. Y coincide más estrechamente con la experiencia disponible con Project Online, aunque algunas características solo están disponibles en Project Online. Los factores adicionales que se deben tener en cuenta son:

- Project Server Edición de Suscripción presenta un modelo de actualización continua que elimina la necesidad de publicar nuevas versiones principales de Project Server en el futuro.
- Tanto Project Server 2016 como 2019 finalizarán el soporte técnico el 14 de julio de 2026. Si migra a cualquiera de las versiones, deberá planear otra actualización en un plazo de tres años. Para obtener más información, consulte las páginas del ciclo de vida de soporte técnico para [2016](/lifecycle/products/project-server-2016) y [2019](/lifecycle/products/project-server-2019).

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>Cómo migrar a Project Server Edición de Suscripción?

Las diferencias arquitectónicas entre Project Server 2013 y Project Server Edición de Suscripción impiden una ruta de migración directa. Por lo tanto, primero tendrá que migrar los datos de Project Server 2013 a Project Server 2016 y, a continuación, a Project Server Edición de Suscripción. 

1. Migre a Project Server 2016.

2. Migre de Project Server 2016 a Project Server Edición de Suscripción.

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

### <a name="step-1-migrate-to-project-server-2016"></a>Paso 1: Migración a Project Server 2016

Para obtener información completa sobre la actualización de Project Server 2013 a Project Server 2016, consulte [Actualización a Project Server 2016](/project/upgrade-to-project-server-2016).

Recursos clave:

- [Información general del proceso de actualización de Project Server 2016](/project/upgrade-to-project-server-2016): obtenga información general de alto nivel sobre cómo actualizar de Project Server 2013 a Project Server 2016.
- [Planear la actualización a Project Server 2016](/project/plan-for-upgrade-to-project-server-2016): examine las consideraciones de planeamiento al actualizar de Project Server 2013 a Project Server 2016, incluidos los requisitos del sistema.
- [Actualización a Project Server 2016](/project/upgrading-to-project-server-2016): consulte las instrucciones detalladas sobre el proceso de actualización.

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>Paso 2: Migración a Project Server Edición de Suscripción

Después de pasar a Project Server 2016 y comprobar que los datos se han migrado correctamente, el siguiente paso es migrar a Project Server Edición de Suscripción.

Para obtener más información, consulte [Actualización a Project Server Edición de Suscripción](/project/upgrade-project-server-subscription-edition).

Recursos clave:

- [Información general sobre el proceso de actualización de Project Server Edición de Suscripción](/project/overview-project-server-subscription-edition-upgrade-process): comprenda lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016.
- [Planear la actualización a Project Server Edición de Suscripción](/Project/plan-upgrade-project-server-subscription-edition): examine las consideraciones de planeamiento que debe tener en cuenta al actualizar de Project Server 2013 a Project Server 2016.
- [Actualización a Project Server Edición de Suscripción](/project/how-to-upgrade-project-server-subscription-edition): consulte las instrucciones detalladas sobre el proceso de actualización.


