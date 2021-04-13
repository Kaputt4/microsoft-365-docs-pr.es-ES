---
title: Configurar el período de tiempo de espera de bloqueo de nube de Antivirus de Microsoft Defender
description: Puede configurar durante cuánto tiempo antivirus de Microsoft Defender bloqueará la ejecución de un archivo mientras espera una determinación de nube.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, tiempo de espera, bloqueo, punto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691065"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurar el período de tiempo de espera del bloque de nube

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso, puede impedir que el archivo se ejecute mientras consulta el servicio en la nube [de Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).

El período predeterminado en el que se [bloqueará el archivo](configure-block-at-first-sight-microsoft-defender-antivirus.md) es de 10 segundos. Puede especificar un período de tiempo adicional para esperar antes de que se pueda ejecutar el archivo. Esto puede ayudar a garantizar que hay suficiente tiempo para recibir una determinación adecuada del servicio en la nube de Antivirus de Microsoft Defender.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Requisitos previos para usar el tiempo de espera extendido del bloque de nube

[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) y sus requisitos previos deben estar habilitados para poder especificar un período de tiempo de espera extendido.

## <a name="specify-the-extended-timeout-period"></a>Especificar el período de tiempo de espera extendido

Puede usar la directiva de grupo para especificar un tiempo de espera extendido para las comprobaciones en la nube.

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **componentes de Windows > Antivirus de Microsoft Defender > MpEngine**

4. Haga doble clic en **Configurar la comprobación de nube extendida** y asegúrese de que la opción está habilitada. Especifique la cantidad de tiempo adicional para evitar que el archivo se ejecute mientras espera una determinación de nube. Puede especificar el tiempo adicional, en segundos, de 1 segundo a 50 segundos. Esta vez se agregará al valor predeterminado de 10 segundos.

5. Haga clic en **Aceptar**.

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Usar tecnologías antivirus de última generación a través de la protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md)
- [Configurar bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Habilitar la protección de entrega en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)