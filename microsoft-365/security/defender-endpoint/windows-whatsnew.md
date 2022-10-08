---
title: Novedades de Microsoft Defender para punto de conexión en Windows
description: Obtenga información sobre las versiones de características más recientes de Microsoft Defender para punto de conexión en Windows Client y Server.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, windows, windows client, windows server, whats new
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: v-mathavale
author: v-mathavale
ms.localizationpriority: medium
ms.date: 09/20/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: reference
ms.subservice: mde
ms.openlocfilehash: 90e5ab9fec1c6c8663f493ee9c9135ffbe33daa2
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2022
ms.locfileid: "68334854"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-windows"></a>Novedades de Microsoft Defender para punto de conexión en Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Todas las actualizaciones contienen:
- Mejoras en el rendimiento
- Mejoras en la capacidad de servicio
- Mejoras de integración (nube, [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804))

<details>
  <summary>Ago-2022 (versión de lanzamiento: 10.8210.*)</summary>

|SO  |Kb  |Versión de lanzamiento  |
|---------|---------|---------|
|Windows Server 2012 R2, 2016 |[KB 5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)|10.8210.22621.1011|
|Windows 11 21H2 (Cobalto)<br> (Windows 11 SV 21H2)     | [KB 5016691](https://support.microsoft.com/en-us/topic/august-25-2022-kb5016691-os-build-22000-918-preview-59097044-915a-49a0-8870-49823236adbd)        | 10.8210.22000.918        |
|Server 2022 (hierro)     | [KB 5016693](https://support.microsoft.com/en-us/topic/august-16-2022-kb5016693-os-build-20348-946-preview-ee90d0bc-c162-4124-b7c6-f963ee7b17ed)        |10.8210.20348.946         |
|Windows 10 20H2/21H1/21H2<br> Windows Server 20H2 (Vibranium)     | [KB 5016688](https://support.microsoft.com/en-us/topic/august-26-2022-kb5016688-os-builds-19042-1949-19043-1949-and-19044-1949-preview-ec31ebdc-067d-44dd-beb0-eabcc984d843)       | 10.8210.19041.1949        |
|Windows Server 2019 (RS5)   |[KB 5016690](https://support.microsoft.com/en-us/topic/august-23-2022-kb5016690-os-build-17763-3346-preview-b81d1ac5-75c7-42c1-b638-f13aa4242f42)       |10.8210.17763.3346         |

**Novedades**

- Se ha agregado una corrección para resolver un problema de certificado intermedio que falta con el uso de "TelemetryProxyServer" en Windows Server 2012 R2 que ejecuta el agente unificado.
- DLP de punto de conexión mejorado con capacidad para proteger archivos cifrados y protegidos con contraseña y no archivos de etiqueta.
- DLP de punto de conexión mejorado con compatibilidad con datos de contexto en telemetría de auditoría (evidencia corta).
- Se ha mejorado Microsoft Defender para punto de conexión compatibilidad con la autenticación de cliente para dispositivos VDI.
- Se ha mejorado la capacidad de Microsoft Defender para punto de conexión para identificar e interceptar ataques avanzados y ransomware.
- La característica Contener ahora admite más versiones de escritorio y servidor para realizar la acción Contener y bloquear los dispositivos detectados cuando están contenidos.
- Expandió la característica de modo de solución de problemas a versiones adicionales de escritorio y servidor. Para obtener una lista completa de las versiones del sistema operativo compatibles y más información sobre los requisitos previos, consulte [Introducción al modo de solución de problemas en Microsoft Defender para punto de conexión](enable-troubleshooting-mode.md).
- Entre las mejoras de Live Response se incluyen una latencia de creación de sesión reducida al usar servidores proxy, un comando manual de deshacer corrección, compatibilidad con el recurso compartido de OneDrive en la acción FindFile y mayor aislamiento y estabilidad.
- [Administración de seguridad para Microsoft Defender para punto de conexión](security-config-management.md#configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management) ahora proporciona la capacidad de sincronizar la configuración del dispositivo a petición en lugar de esperar una cadencia específica.

 > [!NOTE] 
 > El paquete de actualización KB5005292 se encuentra en una programación de implementación gradual a través de Windows Update. Hacia el final de esta programación, el paquete se publicará por completo, incluido el catálogo de actualizaciones para su descarga manual. Para la versión actual, será en la segunda mitad de octubre. Si quiere probar el paquete antes, puede usar [controles de implementación graduales para las actualizaciones de la plataforma](configure-updates.md) para seleccionar el canal de vista previa.
  
<br/>
</details>

Vea también: 
- [Novedades de Microsoft Defender para punto de conexión](whats-new-in-microsoft-defender-endpoint.md)
- [Novedades de Defender para punto de conexión en macOS](mac-whatsnew.md)
- [Novedades de Defender para punto de conexión en iOS](ios-whatsnew.md)
- [Novedades de Defender para punto de conexión en Linux](linux-whatsnew.md)
