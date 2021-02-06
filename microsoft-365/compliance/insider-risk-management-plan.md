---
title: Planificar la administración de riesgos internos
description: Obtenga información sobre cómo planear el uso de directivas de administración de riesgos internas en su organización.
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
ms.openlocfilehash: f2581c4756a57926ab4a4539be8c383b0479e567
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126629"
---
# <a name="plan-for-insider-risk-management"></a>Planificar la administración de riesgos internos

Antes de empezar a trabajar con la administración de riesgos de [insider](insider-risk-management.md) en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de cumplimiento y tecnología de la información. Comprender y planear exhaustivamente la implementación en las siguientes áreas ayudará a garantizar que la implementación y el uso de las características de administración de riesgos interno se adapten correctamente y se alineen con los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas adecuadas de su organización para colaborar en la toma de medidas en casos y alertas de administración de riesgos interno. Algunas partes interesadas recomendadas que deben considerar incluir [](insider-risk-management.md#workflow) en la planeación inicial y el flujo de trabajo de administración de riesgos interno de un extremo a otro son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="determine-any-regional-compliance-requirements"></a>Determinar los requisitos de cumplimiento regional

Las distintas áreas geográficas y organizativas pueden tener requisitos de cumplimiento y privacidad distintos de otras áreas de la organización. Trabaje con las partes interesadas en estas áreas para asegurarse de que comprenden los controles de cumplimiento y privacidad en la administración de riesgos internos y cómo deben usarse en las distintas áreas de la organización. En algunos escenarios, los requisitos de cumplimiento y privacidad pueden requerir directivas que designan o restringen a algunas partes interesadas de investigaciones y casos en función del caso de un usuario o requisitos normativos o de directivas para el área.

Si tiene requisitos para que determinadas partes interesadas participen en investigaciones de casos en las que participen usuarios [](insider-risk-management-policies.md) de determinadas regiones, roles o divisiones, es posible que desee implementar directivas de administración de riesgos internas independientes (aunque idénticas) destinadas a las distintas regiones y poblaciones. Esta configuración facilitará a las partes interesadas correctas la triage y administre los casos que son relevantes para sus roles y regiones. Además, es posible que desee considerar la creación de procesos y directivas para regiones donde investigadores y revisores hablan el mismo idioma que los usuarios para ayudar a simplificar el proceso de escalación para alertas y casos de administración de riesgos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planeación del flujo de trabajo de revisión e investigación

Seleccione las partes interesadas dedicadas para supervisar y revisar las alertas y los casos con una cadencia regular en el Centro de cumplimiento de [Microsoft 365.](https://compliance.microsoft.com/) Asegúrese de comprender cómo asignará a diferentes partes interesadas a los distintos grupos de roles disponibles en la administración de riesgos interno.

Según la estructura del equipo de administración de cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos interno. Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de Insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :---- | :---------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos interno de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas e investigadores designados, puede configurar los permisos de administración de riesgos de Insider en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de administración de riesgos de Insider. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de Insider y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes.|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para segregar a los administradores de riesgos de insider en un grupo definido.  Los usuarios de este grupo de roles pueden crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuraciones globales y asignaciones de grupos de roles. |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de riesgo interno. Los usuarios de este grupo de roles pueden acceder a todas las alertas, casos y plantillas de avisos de administración de riesgos interno. No pueden acceder al Explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo interno. Los usuarios de este grupo de roles pueden acceder a todas las alertas, casos, plantillas de avisos y el Explorador de contenido de Insider para todos los casos. |

## <a name="understand-requirements-and-dependencies"></a>Comprender los requisitos y dependencias

En función de cómo planee implementar directivas de administración de riesgos internas, debe tener las suscripciones de licencias de Microsoft 365 adecuadas y comprender y planear algunos requisitos previos de la solución.

**Licencias:** La administración de riesgos de Insider está disponible como parte de una amplia selección de suscripciones de licencias de Microsoft 365. Para obtener más información, consulte el artículo Introducción a la administración de [riesgos de Insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos interno, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una prueba de Microsoft 365 Enterprise E5.

**Requisitos de plantilla de directiva:** Según la plantilla de directiva que elija, hay requisitos que debe comprender y planear antes de configurar la administración de riesgos de Insider en su organización:

- Al usar  la plantilla de usuarios que salen de la plantilla de robo de datos, debe configurar un conector de RRHH de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización de los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.
- Al usar plantillas de pérdida de datos, debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir información confidencial en su organización y recibir **alertas** de riesgo interno para alertas de directiva DLP de gravedad alta. Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización.
- Al usar plantillas **de infracción** de directivas de seguridad, debe habilitar Microsoft Defender para Endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Consulta el [artículo Configurar características avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) de Microsoft Defender para obtener instrucciones paso a paso para habilitar la integración de Defender for Endpoint con la administración de riesgos de Insider.
- Al usar **plantillas** de usuario descontentas, debe configurar un conector de Recursos Humanos de Microsoft 365 para importar periódicamente información de estado de rendimiento o degradación para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Prueba con un pequeño grupo de usuarios en un entorno de producción

Antes de habilitar la solución de forma general en su entorno de producción, puede considerar la posibilidad de probar las directivas con un pequeño conjunto de usuarios de producción mientras realiza las revisiones legales, de privacidad y cumplimiento necesarias en su organización. Evaluar la administración de riesgos interno en un entorno de prueba requeriría generar acciones de usuario simuladas y otras señales para crear alertas para evaluación y casos de procesamiento. Este enfoque no es práctico para la mayoría de las organizaciones, por lo que se prefiere probar la administración de riesgos internas con un pequeño grupo de usuarios en un entorno de producción.

Mantenga la característica de anonimización en la configuración de directiva habilitada para anonimizar los nombres para mostrar de los usuarios en la consola de administración de riesgos de Insider durante estas pruebas para mantener la privacidad dentro de la herramienta. Esta configuración ayuda a proteger la privacidad de los usuarios que tienen coincidencias de directiva y puede ayudar a promover la objectividad en la investigación de datos y las revisiones de análisis para alertas de riesgo interno.

Si no ve ninguna alerta inmediatamente después de configurar una directiva de administración de riesgos insider, puede significar que aún no se ha cumplido el umbral de riesgo mínimo. Una buena manera de comprobar si la directiva se desencadena y funciona según lo esperado es ver si el usuario está dentro del ámbito de la directiva en la **página** Usuarios.

## <a name="resources-for-stakeholders"></a>Recursos para las partes interesadas

Comparta documentación de administración de riesgos interno con las partes interesadas de su organización que se incluyen en el flujo de trabajo de administración y corrección:

- [Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgos internos](insider-risk-management-alerts.md)
- [Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)
- [Revisar los datos de casos con el Explorador de contenido de riesgo interno](insider-risk-management-content-explorer.md)
- [Crear plantillas de aviso de riesgos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

¿Está preparado para configurar la administración de riesgos de Insider para su organización? Revise los artículos siguientes:

- [Introducción a las opciones de administración de riesgos de Insider](insider-risk-management-settings.md) para configurar las opciones de directiva global.
- [Introducción a la administración de riesgos de Insider](insider-risk-management-configure.md) para configurar requisitos previos, crear directivas y empezar a recibir alertas.
