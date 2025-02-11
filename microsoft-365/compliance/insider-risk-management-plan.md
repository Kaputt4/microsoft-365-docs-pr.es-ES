---
title: Planificar la administración de riesgos internos
description: Obtenga información sobre cómo planear el uso de directivas de administración de riesgos internos en su organización.
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 6c49afa544e72110ff6646fc68f6ea3da498547d
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68767670"
---
# <a name="plan-for-insider-risk-management"></a>Planificar la administración de riesgos internos

> [!IMPORTANT]
> Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Antes de empezar a trabajar con [la administración de riesgos](insider-risk-management.md) internos en su organización, hay importantes actividades y consideraciones de planeamiento que deben revisar los equipos de administración de cumplimiento y tecnología de la información. Comprender y planear exhaustivamente la implementación en las siguientes áreas ayudará a garantizar que la implementación y el uso de las características de administración de riesgos internos funcionen sin problemas y se alineen con los procedimientos recomendados. 

Para obtener más información y una introducción al proceso de planeación para abordar las actividades de riesgo en su organización, consulte [Inicio de un programa de administración de riesgos internos](https://download.microsoft.com/download/b/2/0/b208282a-2482-4986-ba07-15a9b9286df0/pwc-starting-an-insider-risk-management-program-with-pwc-and-microsoft.pdf).

Vea el vídeo siguiente para obtener información sobre cómo el flujo de trabajo de administración de riesgos internos puede ayudar a su organización a prevenir, detectar y contener riesgos al tiempo que prioriza los valores, la cultura y la experiencia del usuario de la organización:


>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

Consulte el [vídeo de Microsoft Mechanics](https://www.youtube.com/watch?v=Ynkfu8OF0wQ) sobre cómo funcionan conjuntamente la administración de riesgos internos y el cumplimiento de comunicaciones para ayudar a minimizar los riesgos de datos de los usuarios de su organización.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas adecuadas de su organización para colaborar para realizar acciones en casos y alertas de administración de riesgos internos. Algunas partes interesadas recomendadas para considerar la posibilidad de incluir en el planeamiento inicial y el [flujo de trabajo de administración de riesgos internos](insider-risk-management.md#workflow) de un extremo a otro son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="determine-any-regional-compliance-requirements"></a>Determinación de los requisitos de cumplimiento regional

Las distintas áreas geográficas y organizativas pueden tener requisitos de cumplimiento y privacidad diferentes de otras áreas de la organización. Trabaje con las partes interesadas en estas áreas para asegurarse de que comprenden los controles de cumplimiento y privacidad en la administración de riesgos internos y cómo se deben usar en diferentes áreas de la organización. En algunos escenarios, los requisitos de cumplimiento y privacidad pueden requerir directivas que designan o restrinjan a algunas partes interesadas de investigaciones y casos basados en el caso de un usuario o requisitos normativos o de directiva para el área.

Si tiene requisitos para que determinadas partes interesadas participen en investigaciones de casos que impliquen a usuarios en determinadas regiones, roles o divisiones, es posible que quiera implementar [directivas de administración de riesgos internos](insider-risk-management-policies.md) independientes (incluso si idénticas) destinadas a las distintas regiones y poblaciones. Esta configuración facilita a las partes interesadas adecuadas evaluar y administrar los casos que son relevantes para sus roles y regiones. Es posible que quiera considerar la posibilidad de crear procesos y directivas para regiones en las que investigadores y revisores hablan el mismo idioma que los usuarios, lo que puede ayudar a simplificar el proceso de escalado de alertas y casos de administración de riesgos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planear el flujo de trabajo de revisión e investigación

En función de cómo quiera administrar las directivas y alertas de administración de riesgos internos, deberá asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de administración de riesgos internos. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar distintas áreas de las características de administración de riesgos internos. O bien, puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles Administración de riesgos internos. Use un único grupo de roles o varios grupos de roles para adaptarse mejor a los requisitos de administración de cumplimiento.

Elija entre las siguientes opciones de grupo de roles y acciones de solución al trabajar con la administración de riesgos internos:

|**Acciones**|**Administración de riesgos internos**|**Administración de riesgos internos Administración**|**Analistas de administración de riesgos internos**|**Investigadores de administración de riesgos internos**|**Auditores de administración de riesgos internos**|**Aprobadores de administración de riesgos internos**|
|---|---|---|---|---|---|---|
|Configuración de directivas y opciones|Sí|Sí|No|No|No|No|
|Información de análisis de acceso|Sí|Sí|Sí|No|No|No|
|Acceso e investigación de alertas|Yes|No|Sí|Sí|No|No|
|Acceso e investigación de casos|Sí|No|Sí|Sí|No|No|
|Acceso y visualización del Explorador de contenido|Sí|No|No|Sí|No|No|
|Configuración de plantillas de aviso|Sí|No|Sí|Sí|No|No|
|Visualización y exportación de registros de auditoría|Sí|No|No|No|Sí|No|
|Acceso y visualización de capturas de pruebas forenses|Yes|No|No|Sí|No|No|
|Creación de una solicitud de captura de pruebas forenses|Sí|Sí|No|No|No|No|
|Aprobación de solicitudes de captura de pruebas forenses|Yes|No|No|No|No|Sí|
|Visualización del informe de estado del dispositivo|Sí|Sí|No|No|No|No|

> [!IMPORTANT]
> Asegúrese de que siempre tiene al menos un usuario en *insider Risk Management* o *Insider Risk Management Administración* grupos de roles (según la opción que elija) para que la configuración de administración de riesgos internos no entre en un escenario de "administrador cero" si determinados usuarios abandonan la organización.

Los miembros de los siguientes roles pueden asignar usuarios a grupos de roles de administración de riesgos internos y tener los mismos permisos de solución incluidos en el grupo de roles *insider Risk Management Administración*:

- *Administrador global* de Azure Active Directory
- *Administrador de cumplimiento de* Azure Active Directory
- administración de la *organización* portal de cumplimiento Microsoft Purview
- *Administrador de cumplimiento de* portal de cumplimiento Microsoft Purview

## <a name="understand-requirements-and-dependencies"></a>Descripción de los requisitos y las dependencias

En función de cómo planee implementar directivas de administración de riesgos internos, debe tener las suscripciones de licencias de Microsoft 365 adecuadas y comprender y planear algunos requisitos previos de la solución.

**Licencias:** La administración de riesgos internos está disponible como parte de una amplia selección de suscripciones de licencias de Microsoft 365. Para obtener más información, consulte el artículo [Introducción a la administración de riesgos internos](insider-risk-management-configure.md#subscriptions-and-licensing) .

> [!IMPORTANT]
> La administración de riesgos internos está disponible actualmente en inquilinos hospedados en regiones geográficas y países compatibles con las dependencias del servicio de Azure. Para comprobar que la administración de riesgos internos es compatible con su organización, consulte [Disponibilidad de dependencias de Azure por país o región](/troubleshoot/azure/general/dependency-availability-by-country).

Si no tiene un plan E5 Microsoft 365 Enterprise existente y quiere probar la administración de riesgos internos, puede [agregar Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a su suscripción existente o [registrarse para obtener una prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.

**Requisitos de plantilla de directiva:** En función de la plantilla de directiva que elija, debe asegurarse de comprender los siguientes requisitos y planear en consecuencia antes de configurar la administración de riesgos internos en su organización:

- Al usar la plantilla **Robo de datos por parte de los usuarios** , debe configurar un conector de RR. HH. de Microsoft 365 para importar periódicamente información de fecha de renuncia y finalización para los usuarios de su organización. Consulte el artículo [Importación de datos con el conector de RR. HH](import-hr-data.md) . para obtener instrucciones paso a paso para configurar el conector de RR. HH. de Microsoft 365.
- Al usar la plantilla **Pérdidas de datos**, debe configurar al menos una directiva de Prevención de pérdida de datos de Microsoft Purview (DLP) para definir información confidencial en su organización y recibir alertas de riesgo interno para alertas de directiva DLP de gravedad alta. Consulte el artículo [Creación, prueba y optimización de una directiva DLP](create-test-tune-dlp-policy.md) para obtener instrucciones paso a paso para configurar directivas DLP.
- Al usar la plantilla Infracción de directiva de **seguridad**, debe habilitar Microsoft Defender para punto de conexión para la integración de administración de riesgos internos en El Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener instrucciones paso a paso para habilitar la integración de Defender para punto de conexión con la administración de riesgos internos, consulte [Configuración de características avanzadas en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features).
- Al usar la plantilla **de usuario De riesgo** , debe configurar un conector de RR. HH. de Microsoft 365 para importar periódicamente información de rendimiento o de estado de degradación para los usuarios de su organización. Consulte el artículo [Importación de datos con el conector de RR. HH](import-hr-data.md) . para obtener instrucciones paso a paso para configurar el conector de RR. HH. de Microsoft 365.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Prueba con un pequeño grupo de usuarios en un entorno de producción

Antes de habilitar esta solución ampliamente en el entorno de producción, debe considerar la posibilidad de probar las directivas con un pequeño conjunto de usuarios de producción mientras realiza las revisiones legales, de privacidad y de cumplimiento necesarias en su organización. La evaluación de la administración de riesgos internos en un entorno de prueba requiere que se generen acciones de usuario simuladas y otras señales para crear alertas para la evaluación de prioridades y los casos para el procesamiento. Este enfoque puede no ser práctico para muchas organizaciones, por lo que se recomienda probar la administración de riesgos internos con un pequeño grupo de usuarios en un entorno de producción.

Mantenga habilitada la característica de anonimización en la configuración de directiva para anonimizar los nombres para mostrar de los usuarios en la consola de administración de riesgos internos durante estas pruebas para mantener la privacidad dentro de la herramienta. Esta configuración ayuda a proteger la privacidad de los usuarios que tienen coincidencias de directivas y puede ayudar a promover la objetividad en la investigación de datos y las revisiones de análisis de alertas de riesgo internos.

Si no ve ninguna alerta inmediatamente después de configurar una directiva de administración de riesgos internos, puede significar que aún no se ha alcanzado el umbral mínimo de riesgo. Compruebe la página **Usuarios** para comprobar que la directiva se desencadena y funciona según lo esperado y para ver si los usuarios están en el ámbito de la directiva.

## <a name="resources-for-stakeholders"></a>Recursos para las partes interesadas

Comparta la documentación de administración de riesgos internos con las partes interesadas de su organización que se incluyen en el flujo de trabajo de administración y corrección:

- [Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgo interno](insider-risk-management-activities.md)
- [Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)
- [Revisión de datos de casos con el explorador de contenido de riesgo interno](insider-risk-management-content-explorer.md)
- [Crear plantillas de aviso de riesgos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

¿Está listo para configurar la administración de riesgos internos para su organización? Se recomienda revisar los artículos siguientes:

- [Empiece a trabajar con la configuración de administración de riesgos](insider-risk-management-settings.md) internos para configurar las opciones de directiva global.
- [Empiece a trabajar con la administración de riesgos internos](insider-risk-management-configure.md) para configurar los requisitos previos, crear directivas y empezar a recibir alertas.
- [Comience con las pruebas forenses de administración de riesgos](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) internos para obtener instrucciones paso a paso para configurar la captura de pruebas forenses en su organización.
