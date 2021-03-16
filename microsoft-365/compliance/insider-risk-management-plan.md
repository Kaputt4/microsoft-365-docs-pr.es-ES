---
title: Planificar la administración de riesgos internos
description: Obtenga información sobre cómo planear el uso de directivas de administración de riesgos de insider en su organización.
keywords: Microsoft 365, riesgo interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 8cd9e9a72cd7643238d118fe0aed519db9159470
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820152"
---
# <a name="plan-for-insider-risk-management"></a>Planificar la administración de riesgos internos

Antes de empezar con la administración de riesgos de [insider](insider-risk-management.md) en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de tecnología de la información y cumplimiento. El conocimiento exhaustivo y la planeación de la implementación en las siguientes áreas ayudarán a garantizar que la implementación y el uso de las características de administración de riesgos de insider funcionen correctamente y se alineen con los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas apropiadas de su organización para colaborar en la toma de acciones en casos y alertas de administración de riesgos de insider. Algunas partes interesadas recomendadas que deben considerar incluir [](insider-risk-management.md#workflow) en la planeación inicial y el flujo de trabajo de administración de riesgos interno completo son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="determine-any-regional-compliance-requirements"></a>Determinar los requisitos de cumplimiento regional

Las diferentes áreas geográficas y organizativas pueden tener requisitos de cumplimiento y privacidad diferentes de otras áreas de la organización. Trabaje con las partes interesadas en estas áreas para asegurarse de que comprendan el cumplimiento y los controles de privacidad en la administración de riesgos internos y cómo deben usarse en diferentes áreas de su organización. En algunos escenarios, los requisitos de cumplimiento y privacidad pueden requerir directivas que designan o restringen a algunas partes interesadas de investigaciones y casos basados en el caso de un usuario o los requisitos normativos o de directiva para el área.

Si tiene requisitos para que determinadas partes interesadas participen en investigaciones de casos que impliquen a usuarios [](insider-risk-management-policies.md) de determinadas regiones, roles o divisiones, es posible que desee implementar directivas de administración de riesgos internas independientes (aunque idénticas) dirigidas a las diferentes regiones y poblaciones. Esta configuración facilitará a las partes interesadas correctas el triaje y la administración de casos relevantes para sus roles y regiones. Además, es posible que desee considerar la posibilidad de crear procesos y directivas para regiones donde los investigadores y revisores hablan el mismo idioma que los usuarios para ayudar a simplificar el proceso de escalado para casos y alertas de administración de riesgos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planear el flujo de trabajo de revisión e investigación

Seleccione partes interesadas dedicadas para supervisar y revisar las alertas y los casos en una cadencia regular en el Centro de cumplimiento de [Microsoft 365](https://compliance.microsoft.com/). Asegúrese de comprender cómo asignará diferentes partes interesadas a los diferentes grupos de roles disponibles en la administración de riesgos de insider.

Según la estructura del equipo de administración de cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos insider. Para ver  la pestaña Permisos en el Centro de cumplimiento de Office 365 Security &  y administrar grupos de roles, debe estar asignado al grupo de roles Administración de la organización o debe tener asignado el rol Administración de *roles.* Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :------------- | :------------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos de insider para su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y auditores designados, puede configurar los permisos de administración de riesgos de insider en un solo grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos insider y los permisos asociados. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de insider y es una buena opción para organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. |
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para segregar los administradores de riesgos de insider en un grupo definido. Los usuarios de este grupo de roles pueden habilitar y ver información de análisis y crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuración global y asignaciones de grupos de roles. |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a usuarios que actuarán como analistas de casos de riesgo interno. Los usuarios de este grupo de roles pueden acceder y ver todas las alertas de administración de riesgos, casos, información de análisis y plantillas de avisos. No pueden acceder al explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo interno. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos, casos, plantillas de avisos y el explorador de contenido para todos los casos. |
| **Auditores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que auditarán las actividades de administración de riesgos internas. Los usuarios de este grupo de roles pueden tener acceso al registro de auditoría de riesgos de insider. |

## <a name="understand-requirements-and-dependencies"></a>Comprender los requisitos y dependencias

En función de cómo planee implementar directivas de administración de riesgos internas, debe tener las suscripciones de licencias de Microsoft 365 adecuadas y comprender y planear algunos requisitos previos de la solución.

**Licencias:** La administración de riesgos de Insider está disponible como parte de una amplia selección de suscripciones de licencias de Microsoft 365. Para obtener más información, consulte [el artículo Introducción a la administración de riesgos de insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de insider, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una versión de prueba de Microsoft 365 Enterprise E5.

**Requisitos de plantilla de directiva:** Según la plantilla de directiva que elija, hay requisitos que debe comprender y planear antes de configurar la administración de riesgos de insider en su organización:

- Al usar la **plantilla Robo** de datos al salir de usuarios, debe configurar un conector de RRHH de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de Recursos humanos de Microsoft 365 para su organización.
- Al usar plantillas de pérdida de datos, debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir información confidencial en su organización y recibir **alertas** de riesgo de información interna para alertas de directivas DLP de alta gravedad. Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización.
- Al usar **plantillas de infracción** de directivas de seguridad, debe habilitar Microsoft Defender para endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Consulta el [artículo Configurar características avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) en Microsoft Defender para obtener instrucciones paso a paso para habilitar la integración de Defender for Endpoint con la administración de riesgos de insider.
- Al usar **plantillas de** usuario no congruentes, debe configurar un conector de RRHH de Microsoft 365 para importar periódicamente información de estado de rendimiento o degradación para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de Recursos humanos de Microsoft 365 para su organización.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Probar con un pequeño grupo de usuarios en un entorno de producción

Antes de habilitar la solución de forma general en su entorno de producción, puede considerar la posibilidad de probar las directivas con un pequeño conjunto de usuarios de producción mientras realiza las revisiones legales, privacidad y cumplimiento necesarias en su organización. Evaluar la administración de riesgos de insider en un entorno de prueba requeriría generar acciones de usuario simuladas y otras señales para crear alertas de evaluación y casos de procesamiento. Este enfoque no es práctico para la mayoría de las organizaciones, por lo que se prefiere probar la administración de riesgos internas con un pequeño grupo de usuarios en un entorno de producción.

Mantenga la característica de anonimización en la configuración de directiva habilitada para anonimizar los nombres de usuario para mostrar en la consola de administración de riesgos de insider durante estas pruebas para mantener la privacidad dentro de la herramienta. Esta configuración ayuda a proteger la privacidad de los usuarios que tienen coincidencias de directiva y puede ayudar a promover la objetividad en las revisiones de análisis y investigación de datos para alertas de riesgo de insider.

Si no ve ninguna alerta inmediatamente después de configurar una directiva de administración de riesgos de insider, puede significar que aún no se ha cumplido el umbral de riesgo mínimo. Una buena forma de comprobar si la directiva se desencadena y funciona según lo esperado es ver si el usuario está en el ámbito de la directiva en la **página** Usuarios.

## <a name="resources-for-stakeholders"></a>Recursos para partes interesadas

Comparta documentación de administración de riesgos con las partes interesadas de la organización que se incluyen en el flujo de trabajo de administración y corrección:

- [Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgos internos](insider-risk-management-alerts.md)
- [Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)
- [Revisar los datos de casos con el explorador de contenido de riesgo interno](insider-risk-management-content-explorer.md)
- [Crear plantillas de aviso de riesgos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

¿Listo para configurar la administración de riesgos de insider para su organización? Revise los artículos siguientes:

- [Introducción a las opciones de administración de riesgos](insider-risk-management-settings.md) de insider para configurar la configuración de directiva global.
- [Introducción a la administración de riesgos de insider](insider-risk-management-configure.md) para configurar requisitos previos, crear directivas y empezar a recibir alertas.
