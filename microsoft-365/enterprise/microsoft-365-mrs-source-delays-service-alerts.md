---
title: Alertas del servicio MRS
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
description: Use avisos del servicio de migración de buzones para supervisar los retrasos en las solicitudes de migración de buzones de correo en su organización.
ms.openlocfilehash: fe6f60b75fb7d27781d442faf82ff981ac54808a
ms.sourcegitcommit: aff1732dfa21e9283b173d8e5ca5bcbeeaaa26d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65810745"
---
# <a name="service-advisories-for-mrs-source-delays-in-exchange-online-monitoring"></a>Avisos de servicio para retrasos de origen MRS en la supervisión de Exchange Online

Los avisos de servicio de retraso de origen del Servicio de replicación de buzones de correo (MRS) le informan de las limitaciones de almacenamiento o de los problemas de uso elevado del procesador en el inquilino (origen de migración) que podrían retrasar las migraciones de buzones en la organización de Microsoft 365. Estos avisos de servicio también incluyen vínculos a recursos de Microsoft para ayudarle a resolver estos problemas.

Estos avisos de servicio se muestran en el Centro de administración de Microsoft 365. Para ver estos avisos de servicio, vaya a **Estado** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**Estado del servicio**</a> >  **Exchange Online** y, a continuación, haga clic en la pestaña **Problemas activos**.

## <a name="what-do-these-service-advisories-indicate"></a>¿Qué indican estos avisos de servicio?

Este aviso de servicio le informa de posibles retrasos en las migraciones de buzones de correo en su organización. Esto incluye migraciones entre bosques, migraciones de incorporación y migraciones fuera del panel. El aviso de servicio contiene una tabla con información sobre las migraciones actuales en su organización. Este es un ejemplo de la tabla con información sobre los retrasos en la migración.

| BatchGuid | ExchangeGuid | RequestGuid | DelayReason |QueuedHours | DelayInHours | SourceServer | RemoteDatabaseName |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|12345678-1234-1234-1234-1234567891011|246c21f7-ca3c-4bba-ab5d-23456558c52a|3d7fab16-7d8e-4c81-a849-e0795054292a|DiskLatency|35.2|27.3|RD1GBL01EXCH003|GBL01EDAG001-db002|
|87654321-4321-4321-4321-1101987654321|21e9a608-78c3-44ef-a4dd-d5e7222aae82|9974aeb4-2aa4-4a2c-aeb6-d94d78cc25c9|DiskLatency|0.4|0.9|RD1GBL01EXCH010|GBL01EDAG010-db003|

En la lista siguiente se describe cada columna del ejemplo anterior.

- **BatchGuid**: GUID único para el trabajo de migración.

- **ExchangeGuid**: identificador único global (GUID) del buzón de usuario que se va a migrar.

- **RequestGuid**: guid de la solicitud de migración.

- **DelayReason**: el motivo de la migración retrasada.

- **QueueHours**: la duración de la migración se ha puesto en cola y en espera.

- **DelayInHours**: la duración de la migración se ha retrasado.

- **SourceServer**: el servidor local desde el que se origina la migración.

- **RemoteDatabaseName**: nombre de la base de datos desde el que se origina la migración.

## <a name="more-information"></a>Más información

Para obtener más información sobre MRS y las migraciones de buzones de correo, consulte los artículos siguientes:

- [El buzón se mueve en Exchange](/exchange/recipients/mailbox-moves)

- [procedimientos recomendados y rendimiento de migración de Microsoft 365 y Office 365](/exchange/mailbox-migration/office-365-migration-best-practices)

- [Análisis de rendimiento de la migración de buzones](https://techcommunity.microsoft.com/t5/exchange-team-blog/mailbox-migration-performance-analysis/ba-p/587134)

- [Solución de problemas de migraciones lentas](https://techcommunity.microsoft.com/t5/exchange-team-blog/troubleshooting-slow-migrations/ba-p/1795706)

- [Formas de migrar varias cuentas de correo electrónico a Microsoft 365](/exchange/mailbox-migration/mailbox-migration)
