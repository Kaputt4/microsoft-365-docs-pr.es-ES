---
title: Recopilar datos de diagnóstico para actualizar el cumplimiento y Windows Defender Antivirus de Microsoft Defender
description: Usar una herramienta para recopilar datos para solucionar problemas de cumplimiento de actualizaciones al usar el complemento evaluación antivirus de Microsoft Defender
keywords: troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3975a18c2986ac7766664194a6d4b80ee1a503b1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691105"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Recopilar datos de diagnóstico de cumplimiento de actualizaciones para la evaluación antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe cómo recopilar datos de diagnóstico que pueden usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas que se pueden encontrar al usar la sección Evaluación de antivirus de Microsoft Defender en el complemento Actualizar cumplimiento.

Antes de intentar este proceso, asegúrese de que ha leído Solucionar problemas de informes de Antivirus de [Microsoft Defender,](troubleshoot-reporting.md)cumple todos los requisitos previos y ha realizado otros pasos de solución de problemas sugeridos.

En al menos dos dispositivos que no se informen o se muestren en Update Compliance, obtenga el archivo de diagnóstico .cab siguiendo los pasos siguientes:

1. Abra una versión de nivel de administrador del símbolo del sistema de la siguiente manera:
        
    a. Abra el **menú** Inicio.

    b. Escriba **cmd**. Haga clic con el botón secundario en **el símbolo del sistema** y haga clic en Ejecutar como **administrador.**

    c. Escriba las credenciales de administrador o apruebe el mensaje.
        
2. Navegue hasta el Windows Defender directorio. El valor predeterminado es `C:\Program Files\Windows Defender`

3. Escriba el siguiente comando y, a continuación, presione **ENTRAR**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Se generará un archivo .cab que contenga varios registros de diagnóstico. La ubicación del archivo se especificará en la salida del símbolo del sistema. De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Copie estos archivos .cab en una ubicación a la que pueda tener acceso el soporte técnico de Microsoft. Un ejemplo podría ser una carpeta de OneDrive protegida con contraseña que puede compartir con nosotros.

6. Envíe un correo electrónico con la <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">plantilla de</a>correo electrónico de compatibilidad de actualización y rellene la plantilla con la siguiente información:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Vea también

- [Solucionar Windows Defender informes de Antivirus de Microsoft Defender](troubleshoot-reporting.md)