---
title: Crear indicadores
ms.reviewer: ''
description: Cree indicadores para un hash de archivo, una dirección IP, direcciones URL o dominios que definan la detección, prevención y exclusión de entidades.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 481051b74c1be88ba78bbd44e4fc0c174ed0bdad
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470898"
---
# <a name="create-indicators"></a>Crear indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

El indicador de coincidencia de puntos de conexión (IoCs) es una característica esencial en cada solución de protección de puntos de conexión. Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y para el bloqueo (prevención y respuesta).

Cree indicadores que definan la detección, prevención y exclusión de entidades. Puedes definir la acción que se va a realizar, así como la duración de cuándo aplicar la acción, así como el ámbito del grupo de dispositivos al que aplicarla.

Los orígenes compatibles actualmente son el motor de detección en la nube de Defender for Endpoint, el motor automatizado de investigación y corrección y el motor de prevención de puntos de conexión (Antivirus de Microsoft Defender).

**Motor de detección de nube**<br>
El motor de detección en la nube de Defender for Endpoint examina periódicamente los datos recopilados e intenta coincidir con los indicadores que estableces. Cuando haya una coincidencia, se realizará una acción de acuerdo con la configuración especificada para IoC.

**Motor de prevención de extremos**<br>
El agente de prevención respeta la misma lista de indicadores. Es decir, si Microsoft Defender AV es el antivirus principal configurado, los indicadores coincidentes se tratarán de acuerdo con la configuración. Por ejemplo, si la acción es "Alerta y bloqueo", AV de Microsoft Defender impedirá las ejecuciones de archivos (bloquear y corregir) y se genera una alerta correspondiente. Por otra parte, si la acción está establecida en "Permitir", AV de Microsoft Defender no detectará ni bloqueará la ejecución del archivo.

**Motor automatizado de investigación y corrección**<BR>
La investigación automatizada y la corrección se comportan igual. Si un indicador está establecido en "Permitir", la investigación automatizada y la corrección omitirán un veredicto "malo" para él. Si se establece en "Bloquear", la investigación automatizada y la corrección la tratarán como "mala".

> [!NOTE]
> La configuración EnableFileHashComputation calcula el hash de archivo para el certificado y el archivo IoC durante los exámenes de archivos. Admite la aplicación de IoC de hashes y certificados que pertenecen a aplicaciones de confianza. Se habilitará y deshabilitará simultáneamente con la opción permitir o bloquear el archivo. EnableFileHashComputation está habilitado manualmente a través de la directiva de grupo y está deshabilitado de forma predeterminada.


Las acciones admitidas actuales son:
- Permitir
- Solo alerta
- Alerta y bloqueo


Puede crear un indicador para:
- [Files](indicator-file.md)
- [Direcciones IP, direcciones URL/dominios](indicator-ip-domain.md)
- [Certificados](indicator-certificates.md)


> [!NOTE]
> Hay un límite de 15.000 indicadores por inquilino. Los indicadores de archivo y certificado no [bloquean las exclusiones definidas para Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). Los indicadores no se admiten en Antivirus de Microsoft Defender cuando está en modo pasivo. 


## <a name="related-topics"></a>Temas relacionados

- [Crear IoC contextual](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Usar la API de indicadores de Microsoft Defender para puntos de conexión](ti-indicator.md)
- [Usar soluciones integradas de partners](partner-applications.md)
