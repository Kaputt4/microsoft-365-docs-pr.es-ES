---
title: Información de gobierno sujeta a la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use las directivas y etiquetas de retención de Microsoft 365 para administrar datos personales en su entorno de Microsoft 365.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377050"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Información de gobierno sujeta a la regulación de privacidad de datos

Los controles de gobierno de la información se pueden usar en su entorno para ayudar a satisfacer las necesidades de cumplimiento de la privacidad de datos, incluido un número específico del Reglamento general de protección de datos (RGPD), HIPAA-HITECH (la ley de privacidad de salud de Estados Unidos), la Ley de Protección de Consumidores de California (CCPA) y la Ley de Protección de Datos de Brasil (LGPD). 

Estos controles están principalmente en las siguientes áreas de solución:

- Directivas de retención
- Etiquetas de retención
- Administración de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Normativas de privacidad de datos que afectan a los controles de gobierno de la información

Esta es una lista de ejemplo de las regulaciones de privacidad de datos que pueden estar relacionadas con los controles de gobierno de la información:

- Artículo del RGPD (13)(2)(a)
- Artículo del RGPD (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- Artículo 46 lgpd

Para obtener más información sobre estas normativas, vea el artículo sobre evaluación de riesgos de privacidad de [datos e identificación de información confidencial.](information-protection-deploy-assess.md)

Para el gobierno de la información, las normativas de privacidad de datos normalmente requieren lo siguiente:

- Debe emplear un esquema técnico para la retención y eliminación de datos personales almacenados en Microsoft 365.
- Si va a almacenar datos personales, informe al interesado de cuánto tiempo se almacenarán los datos, que es una práctica estándar ahora en los sistemas front-end web.
- Los datos personales deben protegerse contra el procesamiento, la pérdida o la alteración accidentales mediante métodos verificables.
- Cualquier acción que se ejecute con datos personales debe documentarse y esa documentación debe conservarse durante un período especificado.

Dado que las regulaciones de privacidad de datos no son muy específicas en lo que respecta a la retención y eliminación de datos, deben tenerse en cuenta otros factores que pueden dictar directrices de gobierno de la información para la información personal almacenada en su suscripción de Microsoft 365. Estos son algunos ejemplos:

- La eliminación de cuentas de consumidor después de 5 años de inactividad y requiere la eliminación o anonimización de los datos de la cuenta después de ese punto, lo que requiere una orquestación entre el sistema que almacena los datos y los flujos de trabajo relacionados con las notificaciones y otra automatización.
- Configurar reglas para mantener las directivas y procedimientos relacionados con el RGPD durante tres años después de su sustitución, lo que se alinea con la programación de retención de directivas y procedimientos de la organización.
- Mantener una suscripción independiente para comunicarse con los consumidores a través de su organización de soporte técnico. Todas las comunicaciones de correo electrónico se conservaron y eliminaron después de dos semanas para reducir cualquier acumulación de la deuda de privacidad en el sistema.

Una pregunta clave para responder es: 

- ¿Cuánto tiempo debe mantenerse la información que contiene datos personales por motivos empresariales válidos para evitar prácticas de "conservarla para siempre"? Esto debe equilibrarse con las necesidades de retención para la continuidad empresarial.

Independientemente de los motivos legales y empresariales para mantener la información personal o eliminarla, Microsoft proporciona una serie de capacidades para implementar el esquema de gobierno de datos en Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Administración del gobierno de la información en Microsoft 365

Para empezar, vea [Administrar el gobierno](../compliance/manage-information-governance.md) de la información y retención, eliminación y destrucción de datos en Microsoft [365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desarrollar programaciones de retención de datos para contenedores, correo electrónico y contenido

Tenga en cuenta lo siguiente:

- Establecer una programación de retención de datos para tipos de información definidos debe considerarse un requisito previo para implementar cualquier esquema de retención o eliminación.

- Dado el número de tipos de información que la mayoría de las organizaciones consideran importantes y las programaciones de retención de registros de gran tamaño correspondientes que van con ellos, la implementación de una estrategia de administración de registros y retención de datos requiere planeación. 

- La clave para establecer una estrategia de gobierno de datos eficaz de este tipo es centrarse en las funciones empresariales de mayor prioridad y en los tipos de información que requieren una administración más formal. Algunos ejemplos son los contratos legales, los estados financieros y la documentación de cumplimiento normativo. Intente evitar tener una programación de retención independiente para cada tipo de información. Intente usar las categorías generales tanto como sea posible, por ejemplo, con programaciones de retención de 7 años para el contenido empresarial general.

- Una vez que los tipos de información personal de su entorno sean más conocidos, establezca programaciones de retención y eliminación para este tipo de contenido y ajuste la arquitectura de la información para facilitar el gobierno de este tipo de información. Por ejemplo, aísle la información personal en sitios, bibliotecas o carpetas independientes con acceso controlado.

### <a name="retention-policies-and-retention-labels"></a>Directivas de retención y etiquetas de retención

Use [directivas de retención y etiquetas](../compliance/retention.md) de retención para retener o eliminar contenido de Microsoft 365 que contenga o se espera que contenga datos personales.

### <a name="records-management"></a>Administración de registros

Use etiquetas de retención que declaren contenido como registro para implementar una solución [de administración](../compliance/records-management.md) de registros para los datos de Microsoft 365.

Para la privacidad de los datos, las solicitudes de interesados (DSR) recibidas por el departamento legal se declaran como un registro y se pueden almacenar indefinidamente o eliminarse con pruebas, para cumplir con las especificaciones de retención de actividades reglamentarias.

