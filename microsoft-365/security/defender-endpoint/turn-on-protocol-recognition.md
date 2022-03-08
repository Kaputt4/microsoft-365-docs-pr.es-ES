---
title: Activar el reconocimiento de protocolo para Antivirus de Microsoft Defender
description: Active el reconocimiento de protocolo para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensor, reconocimiento de protocolos
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 02/21/2022
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 221eff4af6bf8e77f29db84694bf3a683107fc8c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325185"
---
# <a name="turn-on-protocol-recognition"></a>Activar el reconocimiento de protocolos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Esta configuración de directiva le permite configurar el reconocimiento de protocolos para la protección de red frente a vulnerabilidades conocidas. Si habilita o no configura esta configuración, se habilitará el reconocimiento de protocolos. Si deshabilita esta configuración, se deshabilitará el reconocimiento de protocolo.

[!IMPORTANT]
Esta configuración ya está en desuso. 

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Usar la directiva de grupo para configurar el reconocimiento de protocolos

1. En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Configuración del equipo Plantillas administrativas** \> **Windows** \> **componentes Antivirus de Microsoft Defender** \>  \> **sistema de inspección de red**.

3. Seleccione **reconocimiento de protocolo**. Esta directiva está habilitada de modo predeterminado. Si se **establece No configurado**, se habilita la retirada de definiciones.

4. Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.

5. Seleccione **Habilitado** y, a continuación, **seleccione Aceptar**.

6. Implemente el objeto de directiva de grupo actualizado. Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis de directivas de grupo en Microsoft Endpoint Manager: versión preliminar](/mem/intune/configuration/group-policy-analytics).

## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
