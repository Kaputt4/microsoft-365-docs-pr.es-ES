---
title: Planificar la administración de riesgos internos
description: Obtenga información sobre cómo planear el uso de directivas de administración de riesgos de Insider en su organización.
keywords: Microsoft 365, riesgo para Insiders, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: b2aa72dea55d4c75f6e73161e07cf0a9bb5ecf1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846278"
---
# <a name="plan-for-insider-risk-management"></a>Planificar la administración de riesgos internos

Antes de empezar con la [Administración de riesgos de Insider](insider-risk-management.md) en su organización, hay importantes actividades y consideraciones de planeación que deben ser revisadas por los equipos de administración de la tecnología de la información y el cumplimiento. La comprensión y planeación exhaustiva de la implementación en las siguientes áreas le ayudarán a garantizar que la implementación y el uso de las características de administración de riesgos de Insider se ajustan correctamente y se alinean con los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identificar a las partes interesadas adecuadas de la organización para colaborar para emprender acciones en las alertas y casos de administración de riesgos de la Insider. Algunas partes interesadas recomendadas que se deben considerar incluir en la planeación inicial y el [flujo de trabajo de administración de riesgos de Insider](insider-risk-management.md#workflow) de extremo a extremo son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="determine-any-regional-compliance-requirements"></a>Determinación de los requisitos de cumplimiento regionales

Las diferentes áreas geográficas y organizativas pueden tener requisitos de privacidad y cumplimiento que sean diferentes de otras áreas de la organización. Trabaje con las partes interesadas en estas áreas para asegurarse de que comprenden los controles de cumplimiento y privacidad de la administración de riesgos de Insider y cómo deben usarse en diferentes áreas de la organización. En algunos escenarios, los requisitos de cumplimiento y privacidad pueden requerir directivas que designen o restrinjan algunas partes interesadas de investigaciones y casos basados en el caso de un usuario o requisitos de normativa o normativas para el área.

Si tiene requisitos para que las partes interesadas específicas participen en investigaciones de casos en las que participen usuarios en determinadas regiones, roles o divisiones, es posible que quiera implementar directivas de [Administración de riesgos de Insider](insider-risk-management-policies.md) independientes (incluso idénticas) destinadas a distintas regiones y poblaciones. Esta configuración facilitará a las partes interesadas adecuadas clasificar y administrar los casos relevantes para sus roles y regiones. Además, es posible que desee considerar la creación de procesos y directivas para regiones en las que los investigadores y revisores hablan el mismo idioma que los usuarios para ayudar a simplificar el proceso de escalamiento para las alertas y casos de administración de riesgos de Insider.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planeación del flujo de trabajo de revisión e investigación

Seleccione las partes interesadas dedicadas para supervisar y revisar las alertas y los casos en una cadencia regular en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). Asegúrese de comprender cómo asignará diferentes participantes a los distintos grupos de roles disponibles en la administración de riesgos de Insider.

En función de la estructura del equipo de administración del cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos de Insider. Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de Insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :---- | :---------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos de internación para su organización en un único grupo. Al agregar todas las cuentas de usuario para los administradores, analistas e investigadores designados, puede configurar los permisos de administración de riesgos de Insider en un único grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos de Insider. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de Insider y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes.|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de Insiders y más adelante para separar los administradores de riesgos de Insider en un grupo definido.  Los usuarios de este grupo de roles pueden crear, leer, actualizar y eliminar directivas de administración de riesgos de Insider, la configuración global y las asignaciones de grupos de roles. |
| **Analistas de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de riesgo de Insider. Los usuarios de este grupo de roles pueden obtener acceso a todas las plantillas de alertas de administración de riesgos de Insider, casos y notificaciones. No pueden acceder al explorador de contenido de riesgo de Insider. |
| **Investigadores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo de Insider. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos de Insider, casos, plantillas y el explorador de contenido para todos los casos. |

## <a name="understand-requirements-and-dependencies"></a>Descripción de los requisitos y las dependencias

En función de cómo planee implementar las directivas de administración de riesgos de Insider, necesitará tener las suscripciones de licencias de Microsoft 365 adecuadas y comprender y planear algunos requisitos previos de la solución.

**Licencias:** La administración de riesgos de Insider está disponible como parte de la amplia selección de suscripciones de licencias de Microsoft 365. Para obtener más información, vea el artículo [Introducción a la administración de riesgos de Insider](insider-risk-management-configure.md#before-you-begin) .

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de Insider, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a la suscripción existente o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.

**Requisitos de plantillas de directivas:** Según la plantilla de directiva que elija, hay requisitos que debe conocer y planear antes de configurar la administración de riesgos del Insider en su organización:

- Cuando se usa la plantilla de **robo de datos mediante el robo de datos** , se debe configurar un conector de Microsoft 365 de RRHH para que importe periódicamente información sobre la retirada y la fecha de finalización de los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.
- Cuando se usan plantillas de **pérdida de datos** , debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir la información confidencial de la organización y recibir alertas de riesgo de Insider para alertas de directiva DLP de gravedad alta. Consulte el artículo sobre cómo [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para su organización.
- Al usar plantillas de **infracción de directivas de seguridad** , debe habilitar Microsoft defender for Endpoint for Insider Management Management en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Consulte el artículo [Configure Advanced Features in Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features) para obtener instrucciones paso a paso sobre cómo habilitar defender para la integración de extremos con la administración de riesgos de Insider.
- Al usar plantillas de **usuario descontentos** , debe configurar un conector de Microsoft 365 de RRHH para que importe periódicamente información de estado de disminución de rendimiento o degradación para los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Probar con un grupo pequeño de usuarios en un entorno de producción

Antes de habilitar la soluci? a general en su entorno de producción, puede considerar la posibilidad de probar las directivas con un pequeño conjunto de usuarios de producción mientras realiza el cumplimiento necesario, privacidad y revisiones legales en la organización. La evaluación de la administración de riesgos de Insider en un entorno de prueba requeriría la generación de acciones de usuario simuladas y otras señales para crear alertas para las clasificaciones de clasificación y los casos para el procesamiento. Este enfoque no es práctico para la mayoría de las organizaciones, por lo que se prefiere probar la administración de riesgos de Insider con un grupo pequeño de usuarios en un entorno de producción.

Mantenga la característica anonymization en la configuración de directiva habilitada para anonimia los nombres para mostrar del usuario en la consola de administración de riesgos de Insider durante esta prueba para mantener la privacidad dentro de la herramienta. Esta configuración ayuda a proteger la privacidad de los usuarios que tienen coincidencias de directivas y pueden ayudar a promover la objetividad en la investigación de datos y las revisiones de análisis para las alertas de riesgos de Insider.

Si no ve ninguna alerta inmediatamente después de configurar una directiva de administración de riesgos de Insider, puede significar que aún no se ha alcanzado el umbral de riesgo mínimo. Una buena forma de comprobar si la Directiva se desencadena y funciona del modo previsto es ver si el usuario está en el ámbito de la Directiva en la página **usuarios** .

## <a name="resources-for-stakeholders"></a>Recursos para las partes interesadas

Compartir la documentación de administración de riesgos de Insiders con las partes interesadas de su organización que se incluyen en el flujo de trabajo de administración y corrección:

- [Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgos internos](insider-risk-management-alerts.md)
- [Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)
- [Revisar los datos de casos con el explorador de contenido de riesgo de Insider](insider-risk-management-content-explorer.md)
- [Crear plantillas de aviso de riesgos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

¿Está preparado para configurar la administración de riesgos de Insiders para su organización? Revise los artículos siguientes:

- Introducción a la configuración de la [Administración de riesgos de Insider](insider-risk-management-settings.md) para establecer la configuración de directivas globales.
- Empiece a [trabajar con la administración de riesgos de insideres](insider-risk-management-configure.md) para configurar los requisitos previos, crear directivas y empezar a recibir alertas.
