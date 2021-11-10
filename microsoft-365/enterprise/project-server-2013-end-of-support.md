---
title: Project Guía básica de fin de soporte técnico de Server 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.prod: project-server-itpro
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: La compatibilidad finaliza Project Server 2013 el 11 de abril de 2023. Use este artículo como guía para actualizar a Project Online o una versión más reciente de Project server local.
ms.openlocfilehash: 5a9ae38e819dfdb8f9cc2ca3719dccea2d33fa3e
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889891"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>Project Guía básica de fin de soporte técnico de Server 2013

Project Server 2013 llegará al final de la compatibilidad el **11 de abril de 2023**. Si actualmente usas Project Server 2013, ten en cuenta que Project aplicación de escritorio de 2013 también tiene las mismas fechas de fin de soporte técnico.

## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

Casi todos los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores y actualizaciones de seguridad. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Después de Project Server 2013 llega a su fin de soporte técnico el 11 de abril de 2023, Microsoft ya no proporcionará:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas detectados y que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para vulnerabilidades que se detectan y que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

La instalación de Project Server 2013 seguirá en ejecución después de esta fecha. Pero, debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Project Server 2013 tan pronto como sea posible.

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Las opciones de migración son:

- Migrar a Project Online

- Migrar a una versión local más reciente de Project Server (preferiblemente Project Server Subscription Edition)

|¿Por qué prefería migrar a Project Server 2019?|¿Por qué prefería migrar a Project Online?|
|---|---|
|Las reglas de negocio me restringen el funcionamiento de mi negocio en la nube.  <br/><br/>  Necesito controlar las actualizaciones de mi entorno.|Tengo usuarios móviles o remotos.<br/><br/>  Los costos para migrar servidores locales son una preocupación importante (hardware, software, tiempo y esfuerzo para implementar, y así sucesivamente). <br/><br/>  Después de la migración, los costos para mantener mi entorno son una preocupación (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, y así sucesivamente).|

> [!NOTE]
> Project El servidor no admite la configuración híbrida porque Project server y Project Online no pueden compartir el mismo grupo de recursos.

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>Consideraciones importantes para migrar desde Project Server 2013

Tenga en cuenta lo siguiente cuando planee migrar desde Project Server 2013:

- **Obtener ayuda de un proveedor de soluciones de Microsoft:** una actualización de Project Server 2013 puede ser un desafío. Requiere mucha preparación y planeación. Puede ser especialmente difícil si no fuera la persona que estableció originalmente Project Server 2013. Los proveedores de soluciones de Microsoft están disponibles para ayudarle, ya sea que planee migrar a Project Server Subscription Edition o a Project Online. Busque un proveedor de soluciones en el [Centro de proveedores de soluciones de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Tiempo y paciencia:** la planeación, la ejecución y las pruebas de actualización llevará mucho tiempo y esfuerzo, especialmente para una actualización a Project Server Subscription Edition. Si está migrando de Project Server 2013 a Project Server Subscription Edition, primero debe migrar a Project Server 2016, comprobar los datos y, a continuación, Project Server Subscription Edition. Es posible que desee comprobar con un proveedor de soluciones de Microsoft un período de tiempo y el costo estimado para que le ayuden.

## <a name="migrate-to-project-online"></a>Migrar a Project Online

Si decide migrar de Project Server 2013 a Project Online, puede seguir estos pasos para migrar manualmente los datos del plan de proyecto:

1. Guarde los planes de proyecto de Project Server 2013 al formato .mpp.

2. Con Project Profesional 2016, Project Profesional 2019 o el cliente de escritorio de Project Online, abra cada archivo .mpp y, a continuación, guárdelo y publirálo en Project Online.

Puede crear manualmente la configuración de PWA en Project Online (por ejemplo, volver a crear los campos personalizados o los calendarios de empresa necesarios). Los proveedores de soluciones de Microsoft también pueden ayudarle con este proceso.

Recursos clave:

|Recurso|Descripción|
|---|---|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Cómo configurar y usar Project Online|
|[Descripción del servicio Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Información sobre los diferentes planes Project Online disponibles|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar a una versión local más reciente de Project Server

Creemos firmemente que obtiene el mejor valor y experiencia de usuario mediante la migración a Project Online. Pero también entendemos que algunas organizaciones necesitan mantener los datos del proyecto localmente. Si decide mantener los datos del proyecto localmente, puede migrar el entorno de Project Server 2013 a Project Server 2016, Project Server 2019 o Project Server Subscription Edition.

Si no puede migrar a Project Online, se recomienda migrar a Project Server Subscription Edition, que incluye la mayoría de las características clave de versiones anteriores de Project Server. Y coincide más estrechamente con la experiencia disponible con Project Online, aunque algunas características solo están disponibles en Project Online. Factores adicionales a tener en cuenta son:

- Project Server Subscription Edition presenta un modelo de actualización continua que elimina la necesidad de lanzar nuevas versiones principales de Project Server en adelante.
- Tanto Project Server 2016 como 2019 llegarán al final del soporte técnico el 14 de julio de 2026. Si migra a cualquiera de las dos versiones, deberá planear otra actualización en un plazo de tres años. Para obtener más información, vea las páginas del ciclo de vida de soporte técnico para [2016](/lifecycle/products/project-server-2016) y [2019](/lifecycle/products/project-server-2019).

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>¿Cómo puedo migrar a Project Server Subscription Edition?

Las diferencias de arquitectura entre Project Server 2013 y Project Server Subscription Edition impiden una ruta de migración directa. Por lo tanto, deberá migrar los datos de Project Server 2013 primero a Project Server 2016 y, a continuación, a Project Server Subscription Edition. 

1. Migre a Project Server 2016.

2. Migre de Project Server 2016 a Project Server Subscription Edition.

Después de completar cada migración, asegúrese de que los datos se migraron correctamente.

### <a name="step-1-migrate-to-project-server-2016"></a>Paso 1: Migrar a Project Server 2016

Para obtener información completa acerca de la actualización de Project Server 2013 a Project Server 2016, vea [Upgrade to Project Server 2016](/project/upgrade-to-project-server-2016).

Recursos clave:

- [Información general sobre el Project Server 2016](/project/upgrade-to-project-server-2016)de actualización: obtenga una introducción de alto nivel sobre cómo actualizar de Project Server 2013 a Project Server 2016.
- [Plan to upgrade to Project Server 2016:](/project/plan-for-upgrade-to-project-server-2016)Look at planning considerations when upgrading from Project Server 2013 to Project Server 2016, including system requirements.
- [Actualización a Project Server 2016:](/project/upgrading-to-project-server-2016)vea las instrucciones detalladas sobre el proceso de actualización.

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>Paso 2: Migrar a Project Server Subscription Edition

Después de pasar a Project Server 2016 y comprobar que los datos se han migrado correctamente, el siguiente paso es migrar a Project Server Subscription Edition.

Para obtener más información, vea [Upgrade to Project Server Subscription Edition](/project/upgrade-project-server-subscription-edition).

Recursos clave:

- Información general sobre el proceso de actualización [de Project Server Subscription Edition:](/project/overview-project-server-subscription-edition-upgrade-process)comprenda lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016.
- [Planear la actualización a Project Server Subscription Edition:](/Project/plan-upgrade-project-server-subscription-edition)consulte las consideraciones de planeación que debe tener en cuenta al actualizar de Project Server 2013 a Project Server 2016.
- [Actualización a Project Server Subscription Edition:](/project/how-to-upgrade-project-server-subscription-edition)consulta las instrucciones detalladas sobre el proceso de actualización.


