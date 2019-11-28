---
title: Información general del administrador de cumplimiento de Microsoft
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: f8683fd3b3462a44856266ec0e3bef96829b032c
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633659"
---
# <a name="microsoft-compliance-manager-preview"></a>Administrador de cumplimiento de Microsoft (versión preliminar)

> [!IMPORTANT]
> El Administrador de cumplimiento no está disponible en Office 365 ofrecido por 21Vianet, Office 365 Germany, Office 365 U.S. Government Community High (GCC High) u Office 365 Department of Defense.

El [Administrador de cumplimiento de Microsoft (versión preliminar)](https://servicetrust.microsoft.com/ComplianceManager) es una herramienta gratuita de evaluación de riesgos basada en el flujo de trabajo que le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft. Como parte de su suscripción a Microsoft 365, Office 365 o Azure Active Directory, el administrador de cumplimiento le ayuda a administrar el cumplimiento de normativas dentro del modelo de responsabilidad compartida para los servicios en la nube de Microsoft. El administrador de cumplimiento ofrece un panel centralizado para ver los estándares, las regulaciones y los detalles de implementación de los controles y los resultados de pruebas de las evaluaciones de servicios de Microsoft. También incluye herramientas que le permiten administrar las implementaciones de controles personalizados y el seguimiento de cumplimiento específico de su organización.

Con el administrador de cumplimiento, su organización puede:
  
- Combinar información de cumplimiento detallada que Microsoft ha proporcionado a los auditores y los responsables de sus servicios en la nube con su autoevaluación de cumplimiento para los estándares y regulaciones aplicables a su organización. Entre ellas se incluyen normas y regulaciones descritas por la organización internacional de normalización (ISO), el Instituto Nacional de normas y tecnología (NIST), la ley de transferencia y responsabilidad de seguros de salud (HIPAA), los datos generales Reglamento de protección (RGPD) y muchas otras.
- Permiten asignar, realizar un seguimiento y registrar actividades relacionadas con las evaluaciones y el cumplimiento, lo que puede ayudar a su organización a cruzar las barreras de los equipos para alcanzar los objetivos de cumplimiento.
- Proporcionar una puntuación de cumplimiento para ayudarle a realizar un seguimiento del progreso y priorizar los controles de auditoría que ayudan a reducir la exposición de la organización al riesgo.
- Proporcionar un repositorio seguro para que cargue y administre las pruebas y otros artefactos relacionados con sus actividades de cumplimiento.
- Genere informes detallados de Microsoft Excel que documentan las actividades de cumplimiento realizadas por Microsoft y su organización para auditores, reguladores y otros revisores de cumplimiento.

> [!NOTE]
> Las acciones del cliente que se proporcionan en el administrador de cumplimiento son recomendaciones; para evaluar la efectividad de estas recomendaciones en su entorno de reglamentación respectivo antes de la implementación, depende de su organización. Las recomendaciones que se encuentran en el administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento.

## <a name="compliance-manager-relationships"></a>Relaciones del administrador de cumplimiento

El administrador de cumplimiento usa varios componentes para ayudarle con las actividades de administración de cumplimiento. Estos componentes funcionan de forma conjunta para proporcionar un flujo de trabajo de administración completo y informes de cumplimiento sin complicaciones para los auditores.

El diagrama muestra las relaciones entre los componentes principales del administrador de cumplimiento:

![Relaciones en el administrador de cumplimiento versión 3](media/compliance-manager-relationships.png)

## <a name="groups"></a>Grupos

Los [grupos](working-with-compliance-manager.md#groups) son contenedores que permiten organizar las evaluaciones y compartir información común y tareas de flujo de trabajo entre evaluaciones que tienen los mismos controles administrados por el cliente u otros relacionados. Cuando dos evaluaciones distintas en el mismo grupo comparten el control administrado por el cliente, la finalización de los detalles de implementación, las pruebas y el estado del control se sincronizan automáticamente con el mismo control en cualquier otra evaluación del grupo. Esto unifica los elementos de acción asignados para cada control en el grupo y reduce el trabajo de duplicación. También puede optar por usar grupos para organizar. Evaluaciones por año, área, estándar de cumplimiento u otros grupos para ayudar a organizar el trabajo de cumplimiento.

## <a name="assessments"></a>Evaluaciones

Las [evaluaciones](working-with-compliance-manager.md#assessments) son contenedores que permiten organizar los controles para las responsabilidades que comparten Microsoft y su organización para evaluar los riesgos de seguridad y cumplimiento de los servicios en la nube. Las evaluaciones le ayudan a implementar protecciones de protección de datos especificadas por un estándar de cumplimiento normativo, normas o leyes de protección de datos aplicables. Le ayudarán a distinguir la postura de protección y cumplimiento de datos con respecto al estándar de la industria seleccionado para el servicio de nube de Microsoft seleccionado. Las evaluaciones se completan mediante la implementación de controles incluidos en la evaluación que se asignan a un estándar de certificación.

De forma predeterminada, el administrador de cumplimiento crea las siguientes evaluaciones para su organización:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 RGPD

Las evaluaciones incluyen varios componentes:
  
- **Servicios en el ámbito**: cada evaluación se aplica a un conjunto específico de servicios de Microsoft.
- **Controles administrados por Microsoft**: para cada servicio en la nube, Microsoft implementa y administra un conjunto de controles de cumplimiento para los estándares y regulaciones aplicables.
- **Controles administrados**por el cliente: esta es la colección de controles implementada por la organización cuando se toman acciones para cada control.
- **Puntuación**de la evaluación: porcentaje de la puntuación total posible para los controles administrados por el cliente en la evaluación. Esto le ayudará a realizar un seguimiento de la implementación de las acciones asignadas a cada control.

## <a name="controls"></a>Controles

[Los controles](working-with-compliance-manager.md#controls-and-actions) son contenedores de procesos de cumplimiento en el administrador de cumplimiento que definen cómo se administran las actividades de cumplimiento. Estos controles están organizados en familias de controles que se alinean con la estructura de la evaluación de las certificaciones o regulaciones correspondientes.

- **Identificador de control**: el nombre del control seleccionado de la certificación o reglamentación correspondiente.
- **Título del control**: el título del identificador de control de la certificación o reglamentación correspondiente.
- **Identificador de artículo**: este campo es solo para evaluaciones de RGPD y especifica el número de artículo de RGPD correspondiente.
- **Descripción**: texto de control de la certificación o reglamentación correspondiente. Debido a restricciones de copyright, se incluye un vínculo a la información relevante para los estándares ISO.

![Controles de la versión 3 del administrador de cumplimiento](media/compliance-manager-controls.png)

Hay tres tipos de controles en el administrador de cumplimiento, **controles administrados por el**cliente, controles **administrados por el cliente**y **controles de administración compartidos**

### <a name="microsoft-managed-controls"></a>Controles administrados por Microsoft

Para cada servicio en la nube, Microsoft implementa y administra un conjunto de controles como parte del cumplimiento de Microsoft con los distintos estándares y regulaciones. Cada control proporciona detalles sobre cómo Microsoft implementó el control y cómo y cuándo ha sido probado y validado por Microsoft o por un auditor independiente de terceros.

### <a name="customer-managed-controls"></a>Controles administrados por el cliente

Esta es la colección de controles que administra la organización. Su organización es responsable de la implementación de controles administrados por el cliente como parte del proceso de cumplimiento de un estándar o una reglamentación determinada. Los controles administrados por el cliente están organizados en familias de control para la certificación o el Reglamento correspondiente. Use los controles administrados por el cliente para implementar las acciones recomendadas sugeridas por Microsoft como parte de las actividades de cumplimiento. Su organización puede usar las instrucciones preceptivas y las acciones recomendadas para el cliente en cada control administrado por el cliente para administrar el proceso de implementación y evaluación de dicho control.

Los controles administrados por el cliente en evaluaciones también tienen funciones integradas de administración de flujo de trabajo que puede usar para administrar y realizar un seguimiento de su progreso hacia la finalización de la evaluación. Con esta funcionalidad de flujo de trabajo, puede:

- Asignar elementos de acción para cada control
- Seguimiento de elementos de acción asignados
- Cargar pruebas de la implementación del control
- Documentar las pruebas y la validación del control
- Marcar los elementos de acción como implementados y probados

Por ejemplo, un funcionario de cumplimiento de su organización asigna un elemento de acción a un administrador de TI con la responsabilidad y los permisos necesarios para llevar a cabo la acción recomendada. El administrador de ti carga pruebas de las tareas de implementación (capturas de seguridad de la configuración o de la configuración de la Directiva) y asigna el elemento de acción al responsable de cumplimiento cuando se completa. El responsable de cumplimiento evalúa la prueba recopilada, comprueba la implementación del control y registra la fecha de implementación y los resultados de las pruebas en el administrador de cumplimiento.

### <a name="shared-management-controls"></a>Controles de administración compartidos

Un control compartido hace referencia a cualquier control en el que Microsoft y los clientes compartan responsabilidades para la implementación. Por ejemplo, los controles relacionados con el filtrado de personal, la administración de cuentas y contraseñas y el cifrado requieren acciones por parte de Microsoft y los clientes.

## <a name="action-items"></a>Elementos de acción

Los [elementos de acciones](working-with-compliance-manager.md#controls-and-actions) se incluyen en los controles administrados por el cliente como parte de las funciones integradas de administración de flujos de trabajo que puede usar para administrar y realizar un seguimiento del progreso de la realización de la evaluación.

Los usuarios de su organización pueden usar el administrador de cumplimiento para revisar los controles administrados por el cliente de todas las evaluaciones para las que están asignados. Cuando un usuario inicia sesión en Administrador de cumplimiento y abre el panel **Elementos de acción**, ve una lista de los que tiene asignados. Según el rol de Administrador de cumplimiento asignado al usuario, este podrá proporcionar detalles sobre la prueba o la implementación, actualizar el estado o asignar elementos de acción.

Los controles de certificación suelen ser implementados por una persona y comprobados por otro. Por ejemplo, después de que se completen los elementos de acción inicialmente asignados a una persona para su implementación, esos elementos de acción se asignan a la siguiente persona para probar y cargar las pruebas. Cualquier usuario con permisos suficientes para las asignaciones de control puede asignar y reasignar elementos de acción. Esto permite la administración central de las asignaciones de control y el enrutamiento descentralizado de elementos de acción entre implementadores y evaluadores.

## <a name="permissions"></a>Permisos

El administrador de cumplimiento utiliza un modelo de permisos de control de acceso basado en roles. Solo los usuarios a los que se les asigne un rol pueden acceder al administrador de cumplimiento, y las acciones permitidas por cada usuario están restringidas según el tipo de rol. [Ver una tabla](working-with-compliance-manager.md#permissions) que muestra las acciones permitidas para cada permiso.

El administrador del portal del administrador de cumplimiento puede establecer permisos para otros usuarios en el administrador de cumplimiento siguiendo estos pasos:

1. En el menú desplegable **más** arriba, seleccione **Administrador**y, a continuación, **configuración**.
2. Desde aquí, seleccione el rol que desea asignar y, a continuación, agregue el empleado que desee asignar a ese rol. A continuación, los usuarios podrán realizar determinadas acciones.

Además, los usuarios a los que se ha asignado el [rol lector global en Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader) tienen permiso de solo lectura para obtener acceso al administrador de cumplimiento. Sin embargo, no pueden modificar datos ni realizar ninguna acción dentro del administrador de cumplimiento.

Ya no existe un rol de **acceso de invitado** predeterminado. Se debe asignar un rol a cada usuario para que tenga acceso y trabaje en administrador de cumplimiento
  
## <a name="manage-evidence"></a>Administrar pruebas

El administrador de cumplimiento puede almacenar pruebas de las tareas de implementación para realizar pruebas y validar los controles administrados por el cliente. La evidencia incluye documentos, hojas de cálculo, capturas de pantallas, imágenes, scripts, archivos de salida de script y otros archivos. El administrador de cumplimiento también recibe automáticamente telemetría y crea un registro de evidencia para los elementos de acción integrados con calificación segura. Los datos cargados como pruebas en el administrador de cumplimiento se almacenan en Estados Unidos en los sitios de almacenamiento en la nube de Microsoft. Estos datos se replican en regiones de Azure ubicadas en el sudeste asiático y en Europa occidental.

## <a name="templates"></a>Plantillas

El administrador de cumplimiento proporciona [plantillas](working-with-compliance-manager.md#templates) preconfiguradas para las evaluaciones y le permite crear plantillas personalizadas para los controles administrados por el cliente para sus necesidades de cumplimiento. Las plantillas nuevas se crean mediante la importación de información de controles desde un archivo de Excel o bien se puede crear una plantilla a partir de una copia de una plantilla existente.

Las plantillas preconfiguradas incluidas con el administrador de cumplimiento son:

1. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
4. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
5. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
6. [Matriz de controles de nube (CCM) de Cloud Security Alliance (CSA) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [Instituciones financieras federales centro de examen (FFIEC) folleto de seguridad de la información](https://go.microsoft.com/fwlink/?linkid=2109077) 
8. [](https://go.microsoft.com/fwlink/?linkid=2109078) / [tecnología](https://go.microsoft.com/fwlink/?linkid=2109079) HIPAA
9. [Moderado FedRAMP](https://go.microsoft.com/fwlink/?linkid=2108869)
10. [RGPD de la Unión Europea](https://go.microsoft.com/fwlink/?linkid=2108870)
11. [Ley de privacidad del consumidor de California (CCPA)-Preview](https://go.microsoft.com/fwlink/?linkid=2108871)
12. [Línea base de protección de datos 365 de Microsoft](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

## <a name="compliance-score"></a>Puntuación de cumplimiento

La [puntuación de cumplimiento de Microsoft (versión preliminar)](compliance-score.md) es una característica del centro de cumplimiento de Microsoft 365 que le ayuda a comprender la postura de cumplimiento de la organización. Calcula una puntuación basada en riesgos que mide su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos. Conocer la puntuación de cumplimiento general ayuda a su organización a comprender y administrar el cumplimiento. Comprenda [cómo se calcula la puntuación de cumplimiento](compliance-score-methodology.md).
  
> [!IMPORTANT]
> La puntuación de cumplimiento no expresa una medida absoluta de cumplimiento organizacional con cualquier norma o reglamentación en particular. Expresa hasta qué punto ha adoptado los controles que pueden reducir los riesgos para los datos personales y la privacidad individual. Ningún servicio puede garantizar que cumple un estándar o una regla, y la puntuación de cumplimiento no debe interpretarse como una garantía de ninguna manera.

## <a name="secure-score-integration"></a>Integración de la puntuación segura

El administrador de cumplimiento se integra con la [calificación segura de Microsoft](../security/mtp/microsoft-secure-score.md) para aplicar automáticamente el crédito de la puntuación segura a la puntuación de cumplimiento para los elementos de acción sincronizados. Esto se puede configurar para elementos de acción individuales o para todas las acciones de forma global y proporciona actualizaciones de la puntuación segura.

Por ejemplo, tiene un requisito relacionado con la seguridad para activar Azure Rights Management en su organización que también se aplica a un elemento de acción relacionado con el cumplimiento. Cuando Azure Rights Management se activa y se procesa con una puntuación segura, el administrador de cumplimiento recibe la notificación de la actualización y la puntuación del elemento de acción se actualiza automáticamente con crédito de finalización.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Empiece a [trabajar con el administrador de cumplimiento](working-with-compliance-manager.md) para administrar las actividades de cumplimiento normativo de su organización.

## <a name="resources"></a>Recursos

- [Guía interactiva: evaluación y mejora de los controles de protección de datos con el administrador de cumplimiento](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Comunidad tecnológica de seguridad, privacidad y cumplimiento de Microsoft](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
