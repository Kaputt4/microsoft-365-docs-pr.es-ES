---
title: Residencia avanzada de datos en Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.reviewer: dmwmsft
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre las opciones avanzadas de residencia de datos en Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f770faaf96de604fa9d190f538006f67242b227
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806143"
---
# <a name="advanced-data-residency-in-microsoft-365"></a>Data Residency avanzada en Microsoft 365

## <a name="overview-of-advanced-data-residency"></a>Introducción a las Data Residency avanzadas

El complemento de Data Residency avanzada de Microsoft 365 ("ADR") proporciona a los clientes aptos una cobertura ampliada de las cargas de trabajo de Microsoft 365 y los datos del cliente, la residencia de datos confirmada para las regiones del centro de datos de país local y los servicios de migración de inquilinos prioritarios.  Con advanced Data Residency, los clientes empresariales pueden abordar mejor sus requisitos de cumplimiento de residencia de datos y ubicación del inquilino.

Las siguientes cargas de trabajo se incluyen en ADR. Para obtener más información, consulte:

- [Exchange Online](m365-dr-workload-exo.md)
- [SharePoint Online y OneDrive para la Empresa](m365-dr-workload-spo.md)
- [Microsoft Teams](m365-dr-workload-teams.md)
- [Microsoft Defender para Office P1 y Exchange Online Protection](m365-dr-workload-mdo-p1.md)
- [Office para la Web](m365-dr-workload-office-for-web.md)
- [Conexiones Viva](m365-dr-workload-viva-connections.md)
- [Temas Viva](m365-dr-workload-viva-topics.md)
- [Microsoft Purview](m365-dr-workload-purview.md)
  - [Auditoría (Estándar)](m365-dr-workload-purview.md#purview-audit-standard)
  - [Auditoría (Premium)](m365-dr-workload-purview.md#purview-audit-premium)
  - [Retención de datos](m365-dr-workload-purview.md#data-lifecycle-management---data-retention)
  - [Administración de registros de Microsoft Purview](m365-dr-workload-purview.md#data-lifecycle-management---records-management)
  - [Etiquetas de confidencialidad](m365-dr-workload-purview.md#information-protection---sensitivity-labels)
  - [Prevención de pérdida de datos](m365-dr-workload-purview.md#information-protection---data-loss-prevention-dlp)
  - [Cifrado de mensajes de Office](m365-dr-workload-purview.md#information-protection---office-message-encryption)
  - [Barreras de la información](m365-dr-workload-purview.md#insider-risk-management---information-barriers)

## <a name="licensing-and-purchase"></a>Licencias y compras

### <a name="licensing-requirements"></a>Requisitos de licencia

- Microsoft 365 F1, F3, E3 o E5
- Office 365 F3, E1, E3 o E5
- Exchange Online (plan 1 o plan 2)
- OneDrive para la Empresa (plan 1 o plan 2)
- SharePoint Online (plan 1 o plan 2)

### <a name="eligibility"></a>Requisitos de idoneidad

El complemento advanced Data Residency ("ADR") está pensado para clientes empresariales de Microsoft 365 que tienen requisitos completos de residencia de datos.  Para poder comprar ADR, los clientes deben cumplir dos requisitos previos:

- Las suscripciones del _inquilino_ se compran a través de Microsoft Enterprise Agreement ("EA") o el canal Web Direct.
- La _geografía predeterminada_ del _inquilino_ debe ser uno de los países incluidos en la geografía de la _región local_.
  
La disponibilidad geográfica y del canal se actualizará según esté disponible.

Los clientes deben cubrir el 100 % de los usuarios de pago anteriores con licencia de complemento adr para que el inquilino reciba la residencia de datos para las cargas de trabajo de ADR.

### <a name="mixedhybrid-tenants"></a>Inquilinos mixtos o híbridos:

Un cliente se define como "mixto" o "híbrido" si tiene varios tipos de licencia, incluidas las licencias de sector comercial/público (por ejemplo, E3, E5) **y** Educación (por ejemplo, A1, A3, etc.) en su suscripción.

Los clientes híbridos o mixtos tienen derechos para comprar un complemento adr completo solo para la parte de pago de las SKU de Microsoft 365 y no están obligados a cubrir los tipos de suscripción gratuitos. Sin embargo, deben cubrir los puestos de educación pagados con ADR (Microsoft 365 A3/A5, Office 365 A3/A5).

## <a name="data-migration-management"></a>Administración de migración de datos

Si todos los datos de inquilino de un cliente cubiertos por la característica advanced Data Residency no están almacenados en reposo dentro de su geografía de _región local_ apta, se necesitará una migración de datos a la _geografía de la región local_.  Si todos los datos de inquilino de un cliente cubiertos por la característica advanced Data Residency ya están almacenados en reposo dentro de su _geografía de región local_ apta, no se requerirá ninguna migración de datos a la _geografía de la región local_.

### <a name="starting-data-migration"></a>Inicio de la migración de datos

Después de que un cliente haya recibido sus licencias avanzadas de Data Residency, el cliente deberá indicar que está listo para que comience la migración de datos, si es necesario. Para indicar que el inquilino está listo para la migración de datos, el administrador del cliente visitará la sección Ubicación de datos de la consola de Administración de Microsoft 365 en el área Configuración -> Configuración de la organización -> Perfil de organización. Desde aquí, el administrador del cliente podrá ver la ubicación actual de sus datos en reposo y a qué _región local_ se migrarán los datos del cliente, tenga en cuenta que la migración de datos no comenzará hasta que el administrador del cliente haya ejecutado esta tarea. Además, la expectativa de migración que se describe en otra parte de esta documentación no comenzará a realizarse un seguimiento hasta que el administrador del cliente haya ejecutado esta tarea.

Una vez recibida la señal del cliente, se le proporcionará su fecha de participación y la fecha de finalización de destino.

Además de una notificación publicada en el Centro de mensajes al finalizar, la sección Ubicación de datos de la consola de Administración de Microsoft 365 también se actualizará a medida que se complete cada carga de trabajo que requiera una migración de datos.

### <a name="migration-expectations"></a>Expectativas de migración

Microsoft usará los esfuerzos razonables para intentar completar una migración avanzada de clientes de Data Residency complemento en un plazo de doce (12) meses a partir del momento en que el administrador del cliente haya señalado que está listo para la migración. Sin embargo, es posible que Microsoft no pueda completar la migración dentro de este período de tiempo para todos los clientes. Por ejemplo, los clientes o situaciones más grandes o más complejos fuera del control de Microsoft pueden requerir tiempo adicional para completar la migración. Los clientes avanzados de Data Residency complemento también reciben servicios de migración con prioridad para sus inquilinos a través de la opción de migración de Move Program heredada. Estas expectativas de migración también se aplican a todos los clientes de ADR EDU. Los clientes que usan el programa de traslado heredado para una migración de datos que no tienen la característica advanced Data Residency, en su lugar seguirán [las expectativas de migración del programa de traslado heredado](m365-dr-legacy-move-program.md#migration-expectations).

Los movimientos de datos son una operación de servicio back-end con un impacto mínimo para los usuarios finales. Nos adherimos al [Contrato de nivel de servicio (SLA) de Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=523897) para la disponibilidad, por lo que no hay nada para lo que los clientes necesitan prepararse o supervisar durante el traslado. La notificación de cualquier mantenimiento del servicio se realiza si es necesario.

Durante el proceso de migración, Microsoft copia temporalmente los datos de la libreta de direcciones en recursos globales de Microsoft donde se cifran y solo se usan para admitir operaciones de continuidad empresarial y recuperación ante desastres (BCDR). Una vez que Microsoft ha completado el movimiento de los datos del buzón, Microsoft elimina esos datos temporales de los recursos globales. Microsoft continúa invirtiendo en recursos globales y regionales con regularidad. En el año natural 2023, Microsoft planea usar recursos regionales con fines BCDR durante el proceso de migración.

### <a name="during-and-after-your-migration"></a>Durante y después de la migración

Los movimientos de datos son una operación de back-end con un impacto mínimo si afecta a los usuarios finales. No se requiere ninguna acción mientras Microsoft mueve cada servicio y los datos de cliente asociados del inquilino a la geografía aplicable.

> [!NOTE]
> Los movimientos se producen en momentos diferentes para cada servicio. Como resultado, verá lo que se describe a continuación sobre la funcionalidad reducida para cada servicio que se produce en momentos diferentes.

Vea el Centro de mensajes de Microsoft 365 para obtener confirmación cuando se completen los movimientos de cada servicio de carga de trabajo.

### <a name="impact-on-end-users-and-workloads"></a>Impacto en los usuarios finales y las cargas de trabajo

Los movimientos de datos son una operación de servicio back-end con un impacto mínimo para los usuarios finales. Las características que pueden verse afectadas aparecen en la página Durante y después del movimiento de datos. Nos adherimos al [Contrato de nivel de servicio (SLA) de Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=523897) para la disponibilidad, por lo que no hay nada para lo que los clientes necesitan prepararse o supervisar durante el traslado. La notificación de cualquier mantenimiento del servicio se realiza si es necesario.

### <a name="features-impacted"></a>Características afectadas

Debido a la naturaleza compleja de los cientos de servicios (estándar y personalizables) que están disponibles dentro de las muchas cargas de trabajo para las que los clientes se registran y usan dentro de una licencia E3 o E5 típica, la migración de datos de clientes de un centro de datos a otro podría provocar interrupciones menores o una indisponibilidad temporal de determinados servicios que usan los clientes. Consulte las secciones de migración de cada carga de trabajo en la [sección Funcionalidades de Data Residency de carga](m365-dr-workload-exo.md) de trabajo para obtener más información.

### <a name="status-notification"></a>Notificación de estado

Para los clientes que requieren una migración de datos, pueden supervisar el Centro de mensajes para que se proporcionen actualizaciones a medida que cada carga de trabajo complete su migración de datos. También se puede hacer referencia a la sección Ubicación de datos de la consola de Administración de Microsoft 365 para ver si una carga de trabajo ha completado su migración.
Debido a la naturaleza del funcionamiento de las migraciones, no se proporciona ningún estado pormenorizada para indicar lo cerca que puede estar la finalización de una migración.

### <a name="faq"></a>Preguntas más frecuentes

#### <a name="how-do-enterprise-customers-purchase-the-microsoft-365-advanced-data-residency-add-on"></a>¿Cómo compran los clientes empresariales el complemento microsoft 365 Advanced Data Residency?
<details><summary>Haga clic para expandir</summary>

Los clientes empresariales aptos deben ponerse en contacto con el equipo de su cuenta Microsoft o Enterprise Agreement asociado de licencias para facilitar la compra del complemento advanced Data Residency. Los clientes de Web Direct deben comprar a través de su cuenta en línea.
</details>

#### <a name="what-does-the-launch-of-adr-mean-for-the-move-program"></a>¿Qué significa el lanzamiento de ADR para el programa Move?
<details><summary>Haga clic para expandir</summary>

Los esfuerzos avanzados de Data Residency y mover programa existirán simultáneamente durante un tiempo limitado y tendrán compromisos diferentes con los clientes. El programa move está limitado a Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams. ADR incluye estas y más cargas de trabajo.  El programa Move finalizó con el lanzamiento del centro de datos local de Qatar y no estará disponible para ningún centro de datos local futuro.  Los clientes avanzados Data Residency reciben servicios de migración con prioridad sobre los clientes del Programa de traslado. Consulte la sección Expectativa de migración para obtener más detalles.
</details>

#### <a name="how-can-i-move-my-data-to-my-country-with-advanced-data-residency-what-does-the-process-look-like"></a>¿Cómo puedo mover mis datos a mi país con advanced Data Residency? ¿Cómo es el proceso?
<details><summary>Haga clic para expandir</summary>

El primer paso es comprar la SKU de ADR, consulte [Elegibilidad de ADR](advanced-data-residency.md#eligibility).  Una vez que haya adquirido ADR, recibirá una notificación a través del Centro de mensajes (en el centro de administración de inquilinos) que describa la confirmación de compra.  Después de confirmar la preparación para comenzar las migraciones, se iniciará la expectativa de 12 meses de migrar todos los datos en reposo del cliente, como se refiere a las cargas de trabajo enumeradas anteriormente. Desde allí, todas las cargas de trabajo que migran datos de clientes proporcionarán notificaciones al administrador de inquilinos a través del Centro de mensajes (dos mensajes cada uno; uno al principio y al final del proceso de migración).
</details>

## <a name="related-articles"></a>Artículos relacionados

[Programa de traslado heredado](m365-dr-legacy-move-program.md)
  
[Nuevas zonas geográficas del centro de datos para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions?branch=main)
  
[Servicios de Azure por región](https://azure.microsoft.com/regions/)

[Experiencia de Teams en un inquilino habilitado para varias zonas geográficas de Microsoft 365](/microsoftteams/teams-experience-o365odb-spo-multi-geo?branch=main)
