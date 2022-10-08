---
title: Microsoft Defender para punto de conexión demostración de protección entregada en la nube
description: Vea cómo la protección entregada en la nube puede detectar y eliminar automáticamente archivos malintencionados.
keywords: Microsoft Defender para punto de conexión, Microsoft Defender ATP, protección contra virus, detección de virus, eliminación de virus,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 97ec2b7422a90fac95547cf5a3c05d125a14fbd7
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319606"
---
# <a name="cloud-delivered-protection-demonstration"></a>Demostración de protección entregada en la nube

La protección proporcionada en la nube para Microsoft Defender Antivirus, también conocida como Servicio de protección avanzada de Microsoft (MAPS), le proporciona una protección fuerte y rápida además de nuestra protección estándar en tiempo real.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 7, Windows 8.1 & Windows 10
- Microsoft Defender protección en tiempo real está habilitada
- La protección entregada en la nube está habilitada de forma predeterminada, pero es posible que tenga que volver a habilitarla si se ha deshabilitado como parte de las directivas de la organización anteriores. Para obtener más información, consulte [Habilitación de la protección proporcionada en la nube en Microsoft Defender Antivirus](/windows/threat-protection/windows-defender-antivirus/enable-cloud-protection-windows-defender-antivirus?ocid=wd-av-demo-cloud-middle).
- También puede descargar y usar el [script de PowerShell](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/) para habilitar esta configuración y otras en Windows 10.

### <a name="scenario"></a>Escenario

1. Descargue el [archivo de prueba](https://aka.ms/ioavtest). Importante: El archivo de prueba no es malintencionado, es simplemente un archivo inofensivo que simula un virus.

2. Si ve el archivo bloqueado por Microsoft Defender SmartScreen, seleccione el botón "Ver descargas".

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-block.png" alt-text="SmartScreen bloquea una descarga no segura y proporciona un botón para seleccionar para ver los detalles de la lista **Descargas**.":::

3. En el menú Descargas, seleccione a la derecha en el archivo bloqueado y seleccione **Descargar archivo no seguro**.

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-block-view-downloads.png" alt-text="Enumera la descarga como no segura, pero proporciona una opción para continuar con la descarga.":::

4. Debería ver que "Microsoft Defender Antivirus" encontró un virus y lo eliminó.

   > [!NOTE]
   >
   > En algunos casos, también es posible que vea la notificación **Detección de amenazas** de Centro de seguridad de Microsoft Defender.

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-threat-found-notification.png" alt-text="Microsoft Defender notificación Detección de amenazas antivirus proporciona opciones para obtener detalles":::

5. Si el archivo se ejecuta o si ve que Microsoft Defender SmartScreen lo bloqueó, la protección entregada en la nube no funciona. Para obtener más información, consulte [Configuración y validación de conexiones de red para Microsoft Defender Antivirus](/windows/threat-protection/windows-defender-antivirus/configure-network-connections-windows-defender-antivirus?ocid=wd-av-demo-cloud-middle).


## <a name="see-also"></a>Vea también

[Uso de la protección proporcionada por la nube de Microsoft en Microsoft Defender Antivirus](/windows/threat-protection/windows-defender-antivirus/utilize-microsoft-cloud-protection-windows-defender-antivirus?ocid=wd-av-demo-cloud-bottom)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
