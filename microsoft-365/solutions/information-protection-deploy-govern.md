---
title: Control de la información sujeta a la normativa de privacidad de datos
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
ms.custom: ''
description: Use las directivas y etiquetas de retención de 365 de Microsoft para administrar datos personales en su entorno de Microsoft 365.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522306"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Control de la información sujeta a la normativa de privacidad de datos

Los controles de gobierno de la información se pueden usar en su entorno para ayudar a satisfacer las necesidades de cumplimiento de la privacidad de datos, incluido un número que es específico del Reglamento General de protección de datos (RGPD), HIPAA-up (la ley de privacidad de salud de Estados Unidos), la ley de protección de los consumidores (CCPA) y la ley de protección de datos de Brasil. 

Estos controles se dividen principalmente en las siguientes áreas de solución:

- Directivas de retención
- Etiquetas de retención
- Administración de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Normas de privacidad de datos que afectan los controles de gobierno de información

A continuación, se incluye una lista de muestra de las normas de privacidad de datos que pueden relacionarse con controles de gobierno de información:

- Artículo de RGPD (13) (2) (a)
- Artículo de RGPD (5) (1) (f)
- HIPAA-tecnología (45 CFR 164.312 (c) (2))
- HIPAA-tecnología (45 CFR 164.316 (b) (1) (i))
- HIPAA-tecnología (45 CFR 164.316 (b) (1) (II))
- Artículo 46 de LGPD

Para obtener más información sobre estas regulaciones, consulte el [artículo evaluar los riesgos de privacidad de datos e identificar información confidencial](information-protection-deploy-assess.md).

Para el control de la información, las regulaciones de privacidad de datos suelen llamar a lo siguiente:

- Debe usar un esquema técnico para la retención y eliminación de datos personales almacenados en Microsoft 365.
- Si va a almacenar datos personales, informe al asunto de cuánto tiempo se almacenarán los datos, que es una práctica estándar ahora en los sistemas web Front-end.
- Los datos personales deben protegerse contra el procesamiento, la pérdida o la alteración accidentales con métodos comprobables.
- Cualquier acción que se ejecute contra datos personales debe documentarse y la documentación debe conservarse durante un período específico.

Debido a que la normativa sobre privacidad de datos no es muy específica en lo que respecta a la retención y eliminación de datos, se deben tener en cuenta otros factores que pueden dictar directrices de gobierno de información para la información personal almacenada en su suscripción a Microsoft 365. Estos son algunos ejemplos:

- Calcular la antigüedad de las cuentas de consumidor tras 5 años de inactividad y requiere la eliminación o anonymization de datos de la cuenta después de ese punto, lo que requiere orquestación entre el sistema que almacena los datos y los flujos de trabajo relacionados con las notificaciones y otras automatizaciones.
- Configuración de reglas para mantener directivas y procedimientos relacionados con la RGPD durante tres años después de haber sido reemplazado, que se alinea con la programación de retención de la organización para directivas y procedimientos.
- Mantener una suscripción independiente para comunicarse con los consumidores a través de su organización de soporte técnico. Todas las comunicaciones de correo electrónico se conservan y se eliminan después de dos semanas para reducir la acumulación de la deuda de privacidad en el sistema.

Una pregunta clave que debe responder es: 

- ¿Durante cuánto tiempo debe conservarse la información que contiene datos personales por motivos empresariales válidos para evitar las prácticas de "mantener siempre"? Esto debe equilibrarse con las necesidades de retención de continuidad del negocio.

Independientemente de las razones legales y empresariales para mantener la información personal o eliminarla, Microsoft proporciona una serie de capacidades para implementar el esquema de gobierno de datos en Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Administración del gobierno de la información en Microsoft 365

Para empezar, vea [administrar el gobierno de información](../compliance/manage-information-governance.md) y la [retención, eliminación y destrucción de datos en Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desarrollar programaciones de retención de datos para contenedores, correo electrónico y contenido

Tenga en cuenta lo siguiente:

- El establecimiento de un programa de retención de datos para tipos de información definidos debe considerarse como un requisito previo para implementar cualquier esquema de retención o eliminación.

- Dado el número de tipos de información que la mayoría de las organizaciones considera importantes y las programaciones de retención de registros grandes correspondientes que acompañan a ellas, la implementación de una estrategia de administración de registros y retención de datos requiere la planeación. 

- La clave para establecer una estrategia eficaz de gobierno de datos de este tipo es centrarse en las funciones empresariales de mayor prioridad y los tipos de información que requieren una administración más formal. Algunos ejemplos son los contratos legales, los informes financieros y la documentación de cumplimiento normativo. Intente evitar tener una programación de retención separada para cada tipo de información única. Intente utilizar categorías generales tanto como sea posible, por ejemplo, con programaciones de retención de 7 años para contenido empresarial general.

- Una vez que se conozcan mejor los tipos de información personal de su entorno, establezca las programaciones de retención y eliminación de este tipo de contenido y ajuste la arquitectura de la información para facilitar el gobierno de este tipo de información. Por ejemplo, aísle la información personal en sitios, bibliotecas o carpetas independientes con acceso controlado.

### <a name="retention-policies"></a>Directivas de retención

Cree e implemente [directivas de retención](../compliance/retention-policies.md) para el contenido de los sitios que se aplican automáticamente.

Para la privacidad de los datos de los sitios que contengan o se espere que contengan datos personales, especifique reglas de retención o eliminación para abordar los estándares de la organización.

### <a name="retention-labels"></a>Etiquetas de retención

Cree e implemente [etiquetas de retención](../compliance/labels.md) para contenido y correo electrónico.

Para la privacidad de los datos para sitios, bibliotecas, carpetas y correo electrónico que contengan o se espera que contengan datos personales, especifique las reglas de retención o eliminación automática para dirigirse a los estándares de la organización.

### <a name="records-management"></a>Administración de registros

Cree e implemente etiquetas de retención para la administración de registros en función de una programación de retención de registros y un plan de archivos.

Para la privacidad de los datos, las solicitudes de sujetos de datos (interesado) recibidas por el departamento jurídico se declaran como registro y se almacenan indefinidamente para cumplir con las especificaciones de retención de actividades regulatorias.

Consulte estos recursos para obtener más información: 

- [Administración de registros](../compliance/records-management.md)
- [Administrador del plan de archivos](../compliance/file-plan-manager.md)
- [Retención basada en eventos para la administración de registros](../compliance/automate-event-driven-retention.md)
- [Disposición del contenido](../compliance/disposition-reviews.md)
