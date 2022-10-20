---
title: Propiedades y métodos de software
description: Recupera las alertas más recientes.
keywords: apis, graph api, api admitidas, get, alerts, recent
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: b59d7d8f243483debcdeeea2ad4037ebf2cd1b15
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621436"
---
# <a name="software-resource-type"></a>Tipo de recurso de software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

<br>

****

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Enumerar software](get-software.md)|Colección de software|Enumeración del inventario de software de la organización|
|[Obtener software por identificación](get-software-by-id.md)|Software|Obtención de un software específico por su identificador de software|
|[Enumerar distribución de versión de software](get-software-ver-distribution.md)|Colección de distribución|Enumeración de la distribución de versiones de software por identificador de software|
|[Enumerar máquinas por software](get-machines-by-software.md)|Colección MachineRef|Recuperar una lista de dispositivos asociados al identificador de software|
|[Enumerar vulnerabilidades por software](get-vuln-by-software.md)|[Colección de vulnerabilidades](vulnerability.md)|Recuperar una lista de vulnerabilidades asociadas al identificador de software|
|[Obtener los kB que faltan](get-missing-kbs-software.md)|Colección KB|Obtener una lista de los KB que faltan asociados con el identificador de software|
|

## <a name="properties"></a>Propiedades

<br>

****

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|Cadena|Identificador de software|
|Nombre|Cadena|Nombre del software|
|Proveedor|Cadena|Nombre del publicador de software|
|Debilidades|Long|Número de vulnerabilidades detectadas|
|publicExploit|Boolean|Existe una vulnerabilidad de seguridad pública para algunas de las vulnerabilidades|
|activeAlert|Boolean|La alerta activa está asociada a este software|
|exposedMachines|Long|Número de dispositivos expuestos|
|impactScore|Doble|Impacto de la puntuación de exposición de este software|
|
