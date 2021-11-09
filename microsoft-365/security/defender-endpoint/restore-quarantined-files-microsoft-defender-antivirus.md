---
title: Restaurar archivos en cuarentena en el Antivirus de Windows Defender
description: Puede restaurar archivos y carpetas que fueron puestos en cuarentena por Antivirus de Microsoft Defender.
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: a1e5926233d5e1e86101d2f22dfe3e149746a120
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "60884030"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Restaurar archivos en cuarentena en el Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Si Antivirus de Microsoft Defender está configurado para detectar y corregir amenazas en el dispositivo, Antivirus de Microsoft Defender pone en cuarentena archivos sospechosos. Si está seguro de que un archivo en cuarentena no es una amenaza, puede restaurarlo.

1. Abra **Seguridad de Windows**.
2. Seleccione **Protección contra & virus y,** a continuación, haga clic en Historial de **protección**.
3. En la lista de todos los elementos recientes, filtre en **Elementos en cuarentena**.
4. Seleccione un elemento que desee conservar y haga una acción, como restaurar.

> [!TIP]
> La restauración de un archivo desde la cuarentena también se puede realizar mediante el símbolo del sistema. Consulte [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine). 

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la corrección para exámenes](configure-remediation-microsoft-defender-antivirus.md)
- [Revisar los resultados del examen](review-scan-results-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar Antivirus de Microsoft Defender exclusiones en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)