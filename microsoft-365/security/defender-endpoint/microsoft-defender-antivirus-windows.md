---
title: Antivirus de Microsoft Defender
description: Información sobre cómo administrar, configurar y usar Antivirus de Microsoft Defender, una protección integrada antimalware y antivirus.
keywords: Antivirus de Microsoft Defender, windows defender, antimalware, scep, protección de punto de conexión del centro del sistema, administrador de configuración del centro del sistema, virus, malware, amenazas, detección, protección, seguridad
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323051"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Antivirus de Microsoft Defender en Windows

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender es el mayor componente de protección de nueva generación en Microsoft Defender para punto de conexión. Esta protección reúne el aprendizaje automático, el análisis de macrodatos, la investigación de resistencia contra amenazas en profundidad y la infraestructura de nube de Microsoft para proteger a los dispositivos (o puntos de conexión) en la organización. El antivirus de Microsoft Defender está integrado en Windows y funciona con Microsoft Defender para punto de conexión para proporcionar protección en el dispositivo y en la nube. 

## <a name="compatibility-with-other-antivirus-products"></a>Compatibilidad con otros productos antivirus

Si usa un producto antimalware o antivirus que no es de Microsoft en el dispositivo, es posible que pueda ejecutar el Antivirus de Microsoft Defender en modo pasivo junto con la solución antivirus que no es de Microsoft. Depende del sistema operativo usado y de si el dispositivo está incorporado a Defender para punto de conexión. Para más información, consulte [Compatibilidad con Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Comparación del modo activo, el modo pasivo y el modo deshabilitado

En la tabla siguiente se describe qué esperar cuando el Antivirus de Microsoft Defender está en modo activo, en modo pasivo o deshabilitado.

| Modo  | Qué ocurre  |
|---------|---------|
| Modo activo | En modo activo, el Antivirus de Microsoft Defender se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan, se corrigen las amenazas y las amenazas detectadas se enumeran en los informes de seguridad de la organización y en la aplicación de Seguridad de Windows. |
| Modo pasivo | En modo pasivo, el Antivirus de Microsoft Defender no se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan y se notifican las amenazas detectadas, pero el Antivirus de Microsoft Defender no corrige las amenazas.   |
| Deshabilitado o desinstalado  | Cuando se deshabilita o desinstala, no se usa el Antivirus de Microsoft Defender. Los archivos no se examinan y las amenazas no se corrigen. En general, no se recomienda deshabilitar o desinstalar el Antivirus de Microsoft Defender.  |

Para más información, consulte [Compatibilidad con Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Comprobar el estado del Antivirus de Microsoft Defender en el dispositivo

Si quiere comprobar el estado del Antivirus de Microsoft Defender en el dispositivo, puede usar uno de varios métodos, como la aplicación Seguridad de Windows o Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Usar la aplicación Seguridad de Windows para comprobar el estado del Antivirus de Microsoft Defender

1. En el dispositivo Windows, seleccione el menú Inicio y empiece a escribir `Security`. A continuación, abra la aplicación Seguridad de Windows en los resultados.

2. Seleccione **Protección antivirus y contra amenazas**.

3. En **Configuración de antivirus y protección contra amenazas**, elija **Administrar la configuración**.

Verá el nombre de la solución antivirus/antimalware en la página de configuración.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Usar PowerShell para comprobar el estado del Antivirus de Microsoft Defender

1. Seleccione el menú Inicio y empiece a escribir `PowerShell`. A continuación, abra Windows PowerShell en los resultados.

2. Tipo `Get-MpComputerStatus`.

3. En la lista de resultados, examine la fila **AMRunningMode**.

   - **Normal** significa que el Antivirus de Microsoft Defender se ejecuta en modo activo.
   - **Modo pasivo** significa que el Antivirus de Microsoft Defender está ejecución, pero no es el producto antivirus/antimalware principal del dispositivo.
   - **Modo de bloqueo de EDR** significa que el Antivirus de Microsoft Defender se está ejecutando y está habilitada una funcionalidad de Microsoft Defender para punto de conexión denominada "EDR en modo de bloqueo". (Ver [Detección y respuesta de punto de conexión (EDR) en el modo bloqueo](edr-in-block-mode.md).)
   - **Modo pasivo SxS** significa que el Antivirus de Microsoft Defender se ejecuta en modo pasivo junto con otro producto antivirus/antimalware, y el dispositivo no está incorporado a Microsoft Defender para punto de conexión. En este caso, el análisis rápido limitado se utiliza en el Antivirus de Windows Defender. Para obtener más información, consulte [Usar el análisis rápido limitado en el Antivirus de Windows Defender](limited-periodic-scanning-microsoft-defender-antivirus.md)

Para obtener más información sobre el cmdlet de Get-MpComputerStatus PowerShell, consulte el artículo de referencia [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Obtener actualizaciones de la plataforma malware/antivirus

Es importante mantener actualizados el Antivirus de Microsoft Defender, o cualquier solución antivirus/antimalware. Microsoft publica actualizaciones periódicas para ayudar a garantizar que los dispositivos tengan la última tecnología  para protegerse contra nuevas técnicas de ataque y malware. Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Administración y configuración de Antivirus de Microsoft Defender](configuration-management-reference-microsoft-defender-antivirus.md)
- [Evaluar la protección de Antivirus de Microsoft Defender](evaluate-microsoft-defender-antivirus.md)
