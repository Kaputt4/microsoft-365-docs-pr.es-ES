---
title: Alertas de servicio MRS
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appveyor:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Use alertas de servicio de migración de buzones de correo para supervisar retrasos en las solicitudes de migración de buzones de correo en su organización.
ms.openlocfilehash: 6b4b618bae602c7c06b2d6371e39cc865d0a3407
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64567992"
---
# <a name="service-alerts-for-mrs-source-delays-in-exchange-online-monitoring"></a>Alertas de servicio para retrasos de origen MRS en la supervisión de Exchange Online

Las alertas de servicio de retraso de origen del Servicio de replicación de buzones de correo (MRS) le informan sobre limitaciones de almacenamiento o problemas de uso del procesador alto en el lado del inquilino (origen de migración) que podrían retrasar las migraciones de buzones de correo en su Microsoft 365 organización. Estas alertas de servicio también incluyen vínculos a recursos de Microsoft para ayudarle a resolver estos problemas.

Estas alertas de servicio se muestran en el Centro de administración de Microsoft 365. Para ver estas alertas de servicio, vaya a **Health** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**Estado del servicio**</a> >  **Exchange Online y, a continuación**, haga clic en la **pestaña Problemas activos**.

## <a name="what-do-these-service-alerts-indicate"></a>¿Qué indican estas alertas de servicio?

Esta alerta de servicio le informa de posibles retrasos en las migraciones de buzones de correo en su organización. Esto incluye las migraciones entre bosques, las migraciones de incorporación y las migraciones de salida. La alerta de servicio contiene una tabla con información sobre las migraciones actuales de la organización. Este es un ejemplo de la tabla con información sobre retrasos en la migración.

| BatchName | ExchangeGuid | RequestGuid | DelayReason |QueuedHours | DelayInHours | SourceServer | RemoteDatabaseName |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|Migración MRS|246c21f7-ca3c-4bba-ab5d-23456558c52a|3d7fab16-7d8e-4c81-a849-e0795054292a|DiskLatency|35.2|27.3|RD1GBL01EXCH003|GBL01EDAG001-db002|
|Supervisión de inquilinos MRS|21e9a608-78c3-44ef-a4dd-d5e7222aae82|9974aeb4-2aa4-4a2c-aeb6-d94d78cc25c9|DiskLatency|0.4|0.9|RD1GBL01EXCH010|GBL01EDAG010-db003|

En la siguiente lista se describe cada columna del ejemplo anterior.

- **BatchName**: nombre único para el trabajo de migración.

- **ExchangeGuid**: el identificador único global (GUID) del buzón de usuario que se está migrando.

- **RequestGuid**: GUID de la solicitud de migración.

- **DelayReason**: el motivo de la migración retrasada.

- **QueueHours**: la duración de la migración se ha puesto en cola y en espera.

- **DelayInHours**: la duración de la migración se ha retrasado.

- **SourceServer**: el servidor local desde el que se origina la migración.

- **RemoteDatabaseName**: el nombre de la base de datos del que se origina la migración.

## <a name="more-information"></a>Más información

Para obtener más información acerca de las migraciones mrs y mailbox, consulte los siguientes artículos:

- [El buzón se mueve en Exchange](/exchange/recipients/mailbox-moves)

- [Microsoft 365 y Office 365 de migración y procedimientos recomendados](/exchange/mailbox-migration/office-365-migration-best-practices)

- [Análisis de rendimiento de migración de buzones](https://techcommunity.microsoft.com/t5/exchange-team-blog/mailbox-migration-performance-analysis/ba-p/587134)

- [Solución de problemas de migraciones lentas](https://techcommunity.microsoft.com/t5/exchange-team-blog/troubleshooting-slow-migrations/ba-p/1795706)

- [Formas de migrar varias cuentas de correo electrónico a Microsoft 365](/exchange/mailbox-migration/mailbox-migration)
