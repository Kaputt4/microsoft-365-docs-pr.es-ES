---
title: Regulación de la información sujeta a la normativa de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Use etiquetas y directivas de retención de Microsoft 365 para administrar datos personales en su entorno de Microsoft 365.
ms.openlocfilehash: 5445998958ec611a2bef113925c35be145cc96bf
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985639"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Regulación de la información sujeta a la normativa de privacidad de datos

Los controles de gobernanza de la información se pueden emplear en su entorno para ayudar a abordar las necesidades de cumplimiento de la privacidad de los datos, incluido un número específico del Reglamento General de Protección de Datos (RGPD), HIPAA-HITECH (el Estados Unidos ley de privacidad del cuidado de la salud), la Ley de protección del consumidor de California (CCPA) y la Ley de protección de datos de Brasil (LGPD). 

Estos controles se dividen principalmente en las siguientes áreas de solución:

- Directivas de retención
- Etiquetas de retención
- Administración de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Normativas de privacidad de datos que afectan a los controles de gobernanza de la información

Esta es una lista de ejemplo de las regulaciones de privacidad de datos que pueden estar relacionadas con los controles de gobernanza de la información:

- Artículo del RGPD (13)(2)(a)
- Artículo del RGPD (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- Artículo 46 de la LGPD

Para obtener más información sobre estas regulaciones, consulte el [artículo evaluación de riesgos de privacidad de datos e identificación de información confidencial](information-protection-deploy-assess.md).

Para la gobernanza de la información, las regulaciones de privacidad de datos suelen llamar a lo siguiente:

- Debe emplear un esquema técnico para la retención y eliminación de datos personales almacenados en Microsoft 365.
- Si va a almacenar datos personales, informe al interesado de cuánto tiempo se almacenarán los datos, lo que es una práctica estándar ahora en los sistemas front-end web.
- Los datos personales deben protegerse contra el procesamiento, la pérdida o la alteración accidentales mediante métodos verificables.
- Cualquier acción ejecutada en los datos personales debe documentarse y esa documentación debe conservarse durante un período especificado.

Dado que las regulaciones de privacidad de datos no son muy específicas en lo que respecta a la retención y eliminación de datos, es necesario tener en cuenta otros factores que pueden dictar directrices de gobernanza de la información para la información personal almacenada en su suscripción de Microsoft 365. Estos son algunos ejemplos:

- El envejecimiento de las cuentas de consumidor después de 5 años de inactividad y requiere la eliminación o anonimización de los datos de la cuenta después de ese punto, lo que requiere la orquestación entre el sistema que almacena los datos y los flujos de trabajo relacionados con las notificaciones y otras automatizaciones.
- Configurar reglas para mantener directivas y procedimientos relacionados con el RGPD durante tres años después de su sustitución, lo que se alinea con la programación de retención de directivas y procedimientos de la organización.
- Mantener una suscripción independiente para comunicarse con los consumidores a través de su organización de soporte técnico. Todas las comunicaciones por correo electrónico se conservaron y eliminaron después de dos semanas para reducir la acumulación de deudas de privacidad en el sistema.

Una pregunta clave a responder es: 

- ¿Cuánto tiempo necesita mantenerse la información que contiene datos personales por motivos empresariales válidos para evitar prácticas de "conservarlos para siempre"? Esto debe equilibrarse con las necesidades de retención para la continuidad empresarial.

Independientemente de las razones legales y empresariales para mantener la información personal o eliminarla, Microsoft proporciona una serie de funcionalidades para implementar el esquema de gobernanza de datos en Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Administración de la gobernanza de la información en Microsoft 365

Para empezar, consulte [Control de los datos con Microsoft Purview](../compliance/manage-data-governance.md) y [Retención, eliminación y destrucción de datos en Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desarrollo de programaciones de retención de datos para contenedores, correo electrónico y contenido

Tenga en cuenta lo siguiente:

- El establecimiento de una programación de retención de datos para los tipos de información definidos debe considerarse un requisito previo para implementar cualquier esquema de retención o eliminación.

- Dado el número de tipos de información que la mayoría de las organizaciones consideran importantes y las programaciones de retención de registros grandes correspondientes que acompañan a ellos, la implementación de una estrategia de retención de datos y administración de registros requiere planeamiento. 

- La clave para establecer una estrategia de gobernanza de datos eficaz de este tipo es centrarse en las funciones empresariales y los tipos de información más prioritarios que requieren una administración más formal. Algunos ejemplos son los contratos legales, los estados financieros y la documentación de cumplimiento normativo. Intente evitar tener una programación de retención independiente para cada tipo de información. Intente usar categorías generales tanto como sea posible, por ejemplo, con programaciones de retención de 7 años para el contenido empresarial general.

- Una vez que se conozcan mejor los tipos de información personal de su entorno, establezca programaciones de retención y eliminación para este tipo de contenido y ajuste la arquitectura de información para facilitar la gobernanza de este tipo de información. Por ejemplo, aísle la información personal en sitios, bibliotecas o carpetas independientes con acceso controlado.

### <a name="retention-policies-and-retention-labels"></a>Directivas y etiquetas de retención

Use [directivas de retención y etiquetas de retención](../compliance/retention.md) para conservar o eliminar contenido de Microsoft 365 que contenga o se espera que contenga datos personales.

### <a name="records-management"></a>Administración de registros

Use etiquetas de retención que declaren contenido de un registro para implementar una [solución de administración de registros](../compliance/records-management.md) para los datos de Microsoft 365.

Para la privacidad de los datos, las solicitudes de interesados (DSR) recibidas por el departamento legal se declaran un registro y se pueden almacenar indefinidamente o eliminarse con prueba, para cumplir con las especificaciones de retención de actividad normativa.