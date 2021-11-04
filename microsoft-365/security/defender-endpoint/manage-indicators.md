---
title: Crear indicadores
ms.reviewer: ''
description: Cree indicadores para un hash de archivo, una dirección IP, direcciones URL o dominios que definan la detección, prevención y exclusión de entidades.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8933c96d96e59f4b1a3c0b5956bf3248f2eb73d2
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785629"
---
# <a name="create-indicators"></a>Crear indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
>
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

El indicador de coincidencia de puntos de conexión (IoCs) es una característica esencial en cada solución de protección de puntos de conexión. Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y para el bloqueo (prevención y respuesta).

Cree indicadores que definan la detección, prevención y exclusión de entidades. Puedes definir la acción que se va a realizar, así como la duración de cuándo aplicar la acción, así como el ámbito del grupo de dispositivos al que aplicarla.

Los orígenes compatibles actualmente son el motor de detección en la nube de Defender for Endpoint, el motor automatizado de investigación y corrección y el motor de prevención de puntos de conexión (Antivirus de Microsoft Defender).

## <a name="cloud-detection-engine"></a>Motor de detección de nube

El motor de detección en la nube de Defender for Endpoint examina periódicamente los datos recopilados e intenta coincidir con los indicadores que estableces. Cuando haya una coincidencia, se realizará una acción de acuerdo con la configuración especificada para IoC.

## <a name="endpoint-prevention-engine"></a>Motor de prevención de extremos

El agente de prevención respeta la misma lista de indicadores. Es decir, si Microsoft Defender AV es el antivirus principal configurado, los indicadores coincidentes se tratarán de acuerdo con la configuración. Por ejemplo, si la acción es "Alerta y bloqueo", AV de Microsoft Defender impedirá las ejecuciones de archivos (bloquear y corregir) y se genera una alerta correspondiente. Por otra parte, si la acción está establecida en "Permitir", AV de Microsoft Defender no detectará ni bloqueará la ejecución del archivo.

## <a name="automated-investigation-and-remediation-engine"></a>Motor automatizado de investigación y corrección

La investigación automatizada y la corrección se comportan igual. Si un indicador está establecido en "Permitir", la investigación automatizada y la corrección omitirán un veredicto "malo" para él. Si se establece en "Bloquear", la investigación automatizada y la corrección la tratarán como "mala".

La configuración EnableFileHashComputation calcula el hash de archivo para el certificado y el archivo IoC durante los exámenes de archivos. Admite la aplicación de IoC de hashes y certificados que pertenecen a aplicaciones de confianza. Se habilitará y deshabilitará simultáneamente con la opción permitir o bloquear el archivo. EnableFileHashComputation está habilitado manualmente a través de la directiva de grupo y está deshabilitado de forma predeterminada.

Al crear un nuevo indicador (IoC), hay disponibles una o varias de las siguientes acciones:

- Permitir: se permitirá que el IoC se ejecute en los dispositivos.
- Auditoría: se activará una alerta cuando se ejecute ioC.
- Warn: IoC le pedirá una advertencia de que el usuario puede omitir (solo MCAS) 
- Bloquear la ejecución: no se permitirá la ejecución de IoC.
- Bloquear y corregir: el IoC no podrá ejecutarse y se aplicará una acción de corrección al IoC.

>[!NOTE]
> El uso del modo de advertencia le pedirá a los usuarios una advertencia si abren una aplicación de riesgo. El mensaje no les impedirá usar la aplicación, pero puedes proporcionar un mensaje personalizado y vínculos a una página de empresa que describe el uso adecuado de la aplicación. Los usuarios aún pueden omitir la advertencia y seguir usando la aplicación si lo necesitan. Para obtener más información, vea [Govern apps discovered by Microsoft Defender for Endpoint](/cloud-app-security/mde-govern).

Puede crear un indicador para:

- [Files](indicator-file.md)
- [Direcciones IP, direcciones URL/dominios](indicator-ip-domain.md)
- [Certificados](indicator-certificates.md)

La tabla siguiente muestra exactamente qué acciones están disponibles por tipo de indicador (IoC):

| Tipo de IoC | Acciones disponibles |
|:---|:---|
| [Files](indicator-file.md) | Permitir <br> Auditoría <br> Bloquear y corregir |
| [Direcciones IP](indicator-ip-domain.md) | Permitir <br> Auditoría <br> Ejecución de bloques |
| [Direcciones URL y dominios](indicator-ip-domain.md) | Permitir <br> Auditoría <br> Ejecución de bloques |
| [Certificados](indicator-certificates.md) | Permitir <br> Bloquear y corregir |

La funcionalidad de los IoCs preexisteos no cambiará. Sin embargo, se cambió el nombre de los indicadores para que coincidan con las acciones de respuesta admitidas actuales:

- La acción de respuesta "solo alerta" se cambió a "auditoría" con la configuración de generar alerta habilitada.
- La respuesta "alerta y bloqueo" se cambió a "bloquear y corregir" con la configuración de alerta de generación opcional.

El esquema de la API de IoC y los identificadores de amenazas en búsqueda anticipada se han actualizado para alinearse con el cambio de nombre de las acciones de respuesta de IoC. Los cambios del esquema de API se aplican a todos los tipos de IoC.

> [!Note]
> Hay un límite de 15.000 indicadores por inquilino. Los indicadores de archivo y certificado no [bloquean las exclusiones definidas para Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). Los indicadores no se admiten Antivirus de Microsoft Defender cuando está en modo pasivo.
>
> El formato para importar nuevos indicadores (IoCs) ha cambiado según la nueva configuración de alertas y acciones actualizadas. Se recomienda descargar el nuevo formato CSV que se encuentra en la parte inferior del panel de importación.

## <a name="related-topics"></a>Temas relacionados

- [Crear IoC contextual](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Usar la API de indicadores de Microsoft Defender para puntos de conexión](ti-indicator.md)
- [Usar soluciones integradas de partners](partner-applications.md)
