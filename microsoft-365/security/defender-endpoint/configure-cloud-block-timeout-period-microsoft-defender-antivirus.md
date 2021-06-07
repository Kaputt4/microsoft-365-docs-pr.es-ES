---
title: Configurar el período Antivirus de Microsoft Defender de tiempo de espera del bloque de nube
description: Puede configurar cuánto tiempo Antivirus de Microsoft Defender bloqueará la ejecución de un archivo mientras espera una determinación de nube.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, tiempo de espera, bloqueo, punto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789092"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurar el período de espera de bloqueo en la nube

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso, puede impedir que el archivo se ejecute mientras consulta el servicio [Antivirus de Microsoft Defender nube](cloud-protection-microsoft-defender-antivirus.md).

El período predeterminado de bloqueo del [archivo](configure-block-at-first-sight-microsoft-defender-antivirus.md) es de 10 segundos. Si es administrador de seguridad, puede especificar más tiempo para esperar antes de que se pueda ejecutar el archivo. Extender el período de tiempo de espera de bloqueo de nube puede ayudar a garantizar que hay tiempo suficiente para recibir una determinación adecuada del servicio de nube Antivirus de Microsoft Defender nube.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Requisitos previos para usar el tiempo de espera extendido del bloque de nube

[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) y sus requisitos previos deben estar habilitados para poder especificar un período de tiempo de espera extendido.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Especifique el período de tiempo de espera extendido mediante Microsoft Endpoint Manager

Puede especificar el período de tiempo de espera de bloqueo de nube con una [directiva de seguridad de extremo en Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).

1. Vaya al Centro Endpoint Manager de administración ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e inicie sesión.

2. Seleccione **Seguridad de extremo** y, a continuación, en **Administrar**, elija **Antivirus**.

3. Seleccione (o cree) una directiva antivirus.

4. En la **sección Configuración,** expanda **Protección de nube**. A continuación, en el cuadro Tiempo de espera extendido de la nube de **Defender en** segundos, especifique más tiempo, en segundos, de 1 segundo a 50 segundos. Lo que especifique se agrega al valor predeterminado de 10 segundos.

5. (Este paso es opcional) Realice cualquier otro cambio en la directiva de antivirus. (¿Necesita ayuda? Vea [Configuración para obtener Antivirus de Microsoft Defender directiva en Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. Elija **Siguiente** y termine de configurar la directiva.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Especificar el período de tiempo de espera extendido mediante la directiva de grupo

Puede usar la directiva de grupo para especificar un tiempo de espera extendido para las comprobaciones en la nube.

1. En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo y, a continuación, seleccione **Plantillas administrativas.**

3. Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **MpEngine**.

4. Haga doble clic en **Configurar la comprobación de nube extendida** y asegúrese de que la opción está habilitada. 

   Especifique la cantidad de tiempo adicional para evitar que el archivo se ejecute mientras espera una determinación de nube. Especifica el tiempo adicional, en segundos, de 1 segundo a 50 segundos. Lo que especifique se agrega al valor predeterminado de 10 segundos.

5. Seleccione **Aceptar**.

 