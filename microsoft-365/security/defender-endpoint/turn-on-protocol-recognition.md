---
title: Activar el reconocimiento de protocolo para Antivirus de Microsoft Defender
description: Active el reconocimiento de protocolo para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensor, reconocimiento de protocolos
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296494"
---
# <a name="turn-on-protocol-recognition"></a>Activar el reconocimiento de protocolos 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Esta configuración de directiva le permite configurar el reconocimiento de protocolos para la protección de red frente a vulnerabilidades conocidas. Si habilita o no configura esta configuración, se habilitará el reconocimiento de protocolos. Si deshabilita esta configuración, se deshabilitará el reconocimiento de protocolo.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Usar la directiva de grupo para configurar el reconocimiento de protocolos

1. En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Configuración del equipo** Plantillas administrativas  >  **Windows** componentes  >    >  **Antivirus de Microsoft Defender** sistema de  >  **inspección de red**. 

3. Seleccione **reconocimiento de protocolo**. Esta directiva está habilitada de modo predeterminado. Si se establece **No configurado,** la retirada de definiciones está habilitada. 

4. Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.

5. Seleccione **Habilitado** y, a continuación, **seleccione Aceptar**.

6. Implemente el objeto de directiva de grupo actualizado. Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa . 
  
## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)