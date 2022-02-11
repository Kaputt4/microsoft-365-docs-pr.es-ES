---
title: Microsoft 365 Lighthouse y Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre cómo Se integra Microsoft Defender para empresas (versión preliminar) con Microsoft 365 Lighthouse
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 22a625bbdcbb754880804722fd0261845ae9243c
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62463501"
---
# <a name="microsoft-365-lighthouse-and-microsoft-defender-for-business-preview"></a>Microsoft 365 Lighthouse y Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

## <a name="microsoft-defender-for-business-integrates-with-microsoft-365-lighthouse"></a>Microsoft Defender para empresas se integra con Microsoft 365 Lighthouse

Si es un Proveedor de soluciones en la nube de Microsoft (CSP) y tiene [Microsoft 365 Lighthouse, puede](../../lighthouse/m365-lighthouse-overview.md) administrar la seguridad de sus clientes (pequeñas y medianas empresas). Microsoft Defender para empresas (versión preliminar) está diseñado para integrarse con Microsoft 365 Lighthouse. Cuando estas funcionalidades estén disponibles, podrá ver incidentes de seguridad entre inquilinos en su portal de Microsoft 365 Lighthouse ([https://lighthouse.microsoft.com](https://lighthouse.microsoft.com)). 

:::image type="content" source="media/lighthouse-incidents.png" alt-text="captura de pantalla de la lista de incidentes en Microsoft 365 Lighthouse":::

Para obtener acceso a la lista de incidentes, en Microsoft 365 Lighthouse, en la página principal, busque la tarjeta Incidentes **de** seguridad y, a continuación, seleccione Ver **todos los incidentes**.

> [!IMPORTANT]
> Durante la vista previa, Microsoft 365 Lighthouse solo extraerá incidentes de seguridad de Defender para empresas (versión preliminar) cuando se usan con inquilinos de clientes que también tienen Microsoft 365 Empresa Premium. Esta funcionalidad se está implementando gradualmente en Microsoft 365 Lighthouse (versión preliminar) y Defender para empresas (versión preliminar0, y puede que no esté disponible inmediatamente como escenario de prueba).

## <a name="learn-more-about-microsoft-365-lighthouse"></a>Obtenga más información sobre Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite a los proveedores de Microsoft Cloud Service proteger y administrar dispositivos, datos y usuarios a escala para los clientes de pequeñas y medianas empresas que usan una de las siguientes suscripciones:

- [Microsoft 365 Empresa Premium](../../admin/admin-overview/what-is-microsoft-365.md)
- [Microsoft 365 E3](../../enterprise/microsoft-365-overview.md) (que ahora incluye [Microsoft Defender para el plan de extremo 1](../defender-endpoint/defender-endpoint-plan-1.md))

Para obtener más información, vea [Overview of Microsoft 365 Lighthouse](../../lighthouse/m365-lighthouse-overview.md).