---
title: Planificar la administración de riesgos internos
description: Obtenga información sobre cómo planear el uso de directivas de administración de riesgos de insider en su organización.
keywords: Microsoft 365, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 3a1a2fcebdc097b1402d866a2af59d3caac633d3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315601"
---
# <a name="plan-for-insider-risk-management"></a>Planificar la administración de riesgos internos

Antes de empezar con la administración de riesgos de [insider](insider-risk-management.md) en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de tecnología de la información y cumplimiento. El conocimiento exhaustivo y la planeación de la implementación en las siguientes áreas ayudarán a garantizar que la implementación y el uso de las características de administración de riesgos de insider funcionen correctamente y se alineen con los procedimientos recomendados para la solución.

Vea el vídeo siguiente para obtener información sobre cómo el flujo de trabajo de administración de riesgos de insider puede ayudar a su organización a prevenir, detectar y contener riesgos a la vez que prioriza los valores de la organización, la cultura y la experiencia del usuario:
<br>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas apropiadas de su organización para colaborar en la toma de acciones en casos y alertas de administración de riesgos de insider. Algunas partes interesadas recomendadas que deben considerar incluir en la planeación inicial y el [](insider-risk-management.md#workflow) flujo de trabajo de administración de riesgos interno completo son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="determine-any-regional-compliance-requirements"></a>Determinar los requisitos de cumplimiento regional

Las diferentes áreas geográficas y organizativas pueden tener requisitos de cumplimiento y privacidad diferentes de otras áreas de la organización. Trabaje con las partes interesadas en estas áreas para asegurarse de que comprendan el cumplimiento y los controles de privacidad en la administración de riesgos internos y cómo deben usarse en diferentes áreas de su organización. En algunos escenarios, los requisitos de cumplimiento y privacidad pueden requerir directivas que designan o restringen a algunas partes interesadas de investigaciones y casos basados en el caso de un usuario o los requisitos normativos o de directiva para el área.

Si tiene requisitos para que determinadas partes interesadas participen en investigaciones de casos que impliquen a usuarios de determinadas regiones, roles o divisiones, es posible que desee implementar directivas de administración de riesgos internas independientes (aunque idénticas [)](insider-risk-management-policies.md) dirigidas a las diferentes regiones y poblaciones. Esta configuración facilitará a las partes interesadas correctas el triaje y la administración de casos relevantes para sus roles y regiones. Además, es posible que desee considerar la posibilidad de crear procesos y directivas para regiones donde los investigadores y revisores hablan el mismo idioma que los usuarios para ayudar a simplificar el proceso de escalado para casos y alertas de administración de riesgos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planear el flujo de trabajo de revisión e investigación

Dependiendo de cómo desee administrar las alertas y directivas de administración de riesgos internas, deberá asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de administración de riesgos internas. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de administración de riesgos de insider. También puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles De administración de riesgos de Insider. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elegirá entre estas opciones de grupo de roles y acciones de solución al trabajar con la administración de riesgos de insider:

|**Acciones**|**Administración de riesgos internos**|**Administrador de administración de riesgos de Insider**|**Analistas de administración de riesgos internos**|**Investigadores de administración de riesgos internos**|**Auditores de administración de riesgos de Insider**|
|:----------|:--------------------------|:--------------------------------|:-----------------------------------|:----------------------------------------|:-----------------------------------|
| Configurar directivas y opciones | Sí | Sí | No | No | No |
| Access analytics insights | Sí | Sí | Sí | No | No |
| Obtener & investigar alertas | Sí | No | Sí | Sí | No |
| Acceso & investigar casos | Sí | No | Sí | Sí | No |
| Obtener & ver el Explorador de contenido | Sí | No | No | Sí | No |
| Configurar plantillas de aviso | Sí | No | Sí | Sí | No |
| Ver & de auditoría de exportación | Sí | No | No | No | Sí |

>[!IMPORTANT]
>Asegúrese de que siempre tiene al menos un usuario en los grupos de roles Administración de riesgos de Insider o Administración de riesgos de *Insider* (según la opción que elija) para que la configuración de administración de riesgos de *insider* no llegue a un escenario de "administrador cero" si determinados usuarios abandonan la organización.

Los miembros de los siguientes roles pueden asignar usuarios a grupos de roles de administración de riesgos insider y tener los mismos permisos de solución incluidos en el grupo de roles Administración de riesgos de *Insider* :

- Azure Active Directory *global*
- Azure Active Directory *de cumplimiento*
- Centro de cumplimiento de Microsoft 365 *organización*
- Centro de cumplimiento de Microsoft 365 *de cumplimiento*

## <a name="understand-requirements-and-dependencies"></a>Comprender los requisitos y dependencias

En función de cómo planee implementar directivas de administración de riesgos internas, debe tener las Microsoft 365 de licencias adecuadas y comprender y planear algunos requisitos previos de la solución.

**Licencias:** La administración de riesgos de Insider está disponible como parte de una amplia selección de Microsoft 365 de licencias. Para obtener más información, consulte [el artículo Introducción a la administración de riesgos de insider](insider-risk-management-configure.md#subscriptions-and-licensing) .

> [!IMPORTANT]
> La administración de riesgos de Insider está disponible actualmente en inquilinos hospedados en regiones geográficas y países compatibles con las dependencias de servicio de Azure. Para comprobar que la administración de riesgos de insider es compatible con su organización, consulte [Disponibilidad de dependencia de Azure por país o región](/troubleshoot/azure/general/dependency-availability-by-country).

Si no tienes un plan de Microsoft 365 Enterprise E5 existente y quieres probar la administración de riesgos de insider, puedes agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a la suscripción existente o suscribirte [a](https://www.microsoft.com/microsoft-365/enterprise) una prueba de Microsoft 365 Enterprise E5.

**Requisitos de plantilla de directiva:** Según la plantilla de directiva que elija, hay requisitos que debe comprender y planear antes de configurar la administración de riesgos de insider en su organización:

- Al usar la **plantilla Robo** de datos mediante la salida de usuarios, debe configurar un conector de recursos humanos de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización para los usuarios de la organización. Vea el artículo [Importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de recursos humanos de Microsoft 365 para su organización.
- Al usar plantillas de pérdida de datos, debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir información confidencial en su organización y recibir **alertas** de riesgo de información interna para alertas de directivas DLP de alta gravedad. Vea el artículo [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso para configurar las directivas DLP para su organización.
- Al usar **plantillas de infracción** de directivas de seguridad, debe habilitar Microsoft Defender para endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener instrucciones paso a paso para habilitar la integración de Defender for Endpoint con la administración de riesgos de insider, consulte [Configure advanced features in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features).
- Al usar **plantillas de usuario no** congruentes, debe configurar un conector de recursos humanos de Microsoft 365 para importar periódicamente información de estado de rendimiento o degradación para los usuarios de la organización. Vea el artículo [Importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de recursos humanos de Microsoft 365 para su organización.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Probar con un pequeño grupo de usuarios en un entorno de producción

Antes de habilitar la solución de forma general en su entorno de producción, puede considerar la posibilidad de probar las directivas con un pequeño conjunto de usuarios de producción mientras realiza las revisiones legales, privacidad y cumplimiento necesarias en su organización. Evaluar la administración de riesgos de insider en un entorno de prueba requeriría generar acciones de usuario simuladas y otras señales para crear alertas de evaluación y casos de procesamiento. Este enfoque no es práctico para la mayoría de las organizaciones, por lo que se prefiere probar la administración de riesgos internas con un pequeño grupo de usuarios en un entorno de producción.

Mantenga la característica de anonimización en la configuración de directiva habilitada para anonimizar los nombres de usuario para mostrar en la consola de administración de riesgos de insider durante estas pruebas para mantener la privacidad dentro de la herramienta. Esta configuración ayuda a proteger la privacidad de los usuarios que tienen coincidencias de directiva y puede ayudar a promover la objetividad en las revisiones de análisis y investigación de datos para alertas de riesgo de insider.

If you don't see any alerts immediately after configuring an insider risk management policy, it may mean the minimum risk threshold hasn't been met yet. Una buena forma de comprobar si la directiva se desencadena y funciona según lo esperado es ver si el usuario está en el ámbito de la directiva en la **página** Usuarios.

## <a name="resources-for-stakeholders"></a>Recursos para partes interesadas

Comparta documentación de administración de riesgos con las partes interesadas de la organización que se incluyen en el flujo de trabajo de administración y corrección:

- [Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgo interno](insider-risk-management-activities.md)
- [Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)
- [Revisar los datos de casos con el explorador de contenido de riesgo interno](insider-risk-management-content-explorer.md)
- [Crear plantillas de aviso de riesgos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

¿Listo para configurar la administración de riesgos de insider para su organización? Revise los artículos siguientes:

- [Introducción a las opciones de administración de riesgos de insider](insider-risk-management-settings.md) para configurar la configuración de directiva global.
- [Introducción a la administración de riesgos de insider](insider-risk-management-configure.md) para configurar requisitos previos, crear directivas y empezar a recibir alertas.
