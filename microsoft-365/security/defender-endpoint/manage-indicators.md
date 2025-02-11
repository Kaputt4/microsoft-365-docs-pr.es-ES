---
title: Crear indicadores
ms.reviewer: ''
description: Cree indicadores para un hash de archivo, una dirección IP, direcciones URL o dominios que definan la detección, prevención y exclusión de entidades.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ccca356e33b22df31222f93be7defb4353d93854
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633667"
---
# <a name="create-indicators"></a>Crear indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
>
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

El indicador de coincidencia de peligro (IoC) es una característica esencial en todas las soluciones de Endpoint Protection. Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y el bloqueo (prevención y respuesta).

Cree indicadores que definan la detección, prevención y exclusión de entidades. Puede definir la acción que se va a realizar, así como la duración de la aplicación de la acción, así como el ámbito del grupo de dispositivos al que se va a aplicar.

Los orígenes admitidos actualmente son el motor de detección en la nube de Defender para punto de conexión, el motor de investigación y corrección automatizado y el motor de prevención de puntos de conexión (Microsoft Defender Antivirus).

## <a name="cloud-detection-engine"></a>Motor de detección de nube

El motor de detección en la nube de Defender para punto de conexión examina periódicamente los datos recopilados e intenta coincidir con los indicadores establecidos. Cuando haya una coincidencia, se realizará una acción según la configuración especificada para IoC.

## <a name="endpoint-prevention-engine"></a>Motor de prevención de puntos de conexión

El agente de prevención respeta la misma lista de indicadores. Es decir, si Microsoft Defender Antivirus es el antivirus principal configurado, los indicadores coincidentes se tratarán según la configuración. Por ejemplo, si la acción es "Alerta y Bloqueo", Microsoft Defender Antivirus impedirá las ejecuciones de archivos (bloquear y corregir) y se generará una alerta correspondiente. Por otro lado, si la acción está establecida en "Permitir", Microsoft Defender Antivirus no detectará ni bloqueará la ejecución del archivo.

## <a name="automated-investigation-and-remediation-engine"></a>Motor de investigación y corrección automatizado

La investigación y corrección automatizadas se comportan igual. Si un indicador se establece en "Permitir", la investigación y corrección automatizadas omitirán un veredicto "incorrecto" para él. Si se establece en "Bloquear", la investigación y la corrección automatizadas lo tratarán como "incorrecto".

La configuración EnableFileHashComputation calcula el hash de archivo para el certificado y el archivo IoC durante los exámenes de archivos. Admite la aplicación de IoC de hashes y certificados que pertenecen a aplicaciones de confianza. Se habilitará y deshabilitará simultáneamente con la configuración de permitir o bloquear archivos. EnableFileHashComputation se habilita manualmente mediante समूह नीति y está deshabilitado de forma predeterminada.

Al crear un nuevo indicador (IoC), están disponibles una o varias de las siguientes acciones:

- Permitir: se permitirá que IoC se ejecute en los dispositivos.
- Auditoría: se desencadenará una alerta cuando se ejecute IoC.
- Advertir: IoC le pedirá una advertencia que el usuario puede omitir. 
- Ejecución de bloques: no se permitirá la ejecución de IoC.
- Bloquear y corregir: no se permitirá la ejecución de IoC y se aplicará una acción de corrección a IoC.

>[!NOTE]
> El uso del modo Advertir indicará a los usuarios una advertencia si abren una aplicación de riesgo. El símbolo del sistema no les impedirá usar la aplicación, pero puede proporcionar un mensaje personalizado y vínculos a una página de empresa que describa el uso adecuado de la aplicación. Los usuarios pueden omitir la advertencia y seguir usando la aplicación si lo necesitan. Para obtener más información, consulte [Control de las aplicaciones detectadas por Microsoft Defender para punto de conexión](/cloud-app-security/mde-govern).

Puede crear un indicador para:

- [Files](indicator-file.md)
- [Direcciones IP, direcciones URL o dominios](indicator-ip-domain.md)
- [Certificados](indicator-certificates.md)

En la tabla siguiente se muestra exactamente qué acciones están disponibles por tipo de indicador (IoC):

| Tipo de IoC | Acciones disponibles |
|:---|:---|
| [Files](indicator-file.md) | Permitir <br> Auditoría <br> Bloquear y corregir |
| [Direcciones IP](indicator-ip-domain.md) | Permitir <br> Auditoría <br> Ejecución de bloques <br> Advertir |
| [Direcciones URL y dominios](indicator-ip-domain.md) | Permitir <br> Auditoría <br> Ejecución de bloques<br> Advertir |
| [Certificados](indicator-certificates.md) | Permitir <br> Bloquear y corregir |

La funcionalidad de los ioC preexistebles no cambiará. Sin embargo, se cambió el nombre de los indicadores para que coincidan con las acciones de respuesta admitidas actuales:

- Se cambió el nombre de la acción de respuesta "solo alerta" a "audit" con la opción generar alerta habilitada.
- Se cambió el nombre de la respuesta "alerta y bloque" a "bloquear y corregir" con la configuración de generación de alertas opcional.

El esquema de la API de IoC y los identificadores de amenazas en la búsqueda anticipada se han actualizado para alinearse con el cambio de nombre de las acciones de respuesta de IoC. Los cambios del esquema de API se aplican a todos los tipos de IoC.

> [!Note]
> Hay un límite de 15 000 indicadores por inquilino. Los indicadores de archivo y certificado no [bloquean las exclusiones definidas para Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). Los indicadores no se admiten en Microsoft Defender Antivirus cuando está en modo pasivo.
>
> El formato para importar nuevos indicadores (IoC) ha cambiado según la nueva configuración de alertas y acciones actualizadas. Se recomienda descargar el nuevo formato CSV que se encuentra en la parte inferior del panel de importación.

## <a name="related-topics"></a>Temas relacionados

- [Creación de IoC contextual](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Uso de la API de indicadores de Microsoft Defender para punto de conexión](ti-indicator.md)
- [Uso de soluciones integradas de asociados](partner-applications.md)
