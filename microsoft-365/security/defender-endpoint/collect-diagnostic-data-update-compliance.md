---
title: Recopilación de datos de diagnóstico para las actualizaciones de cumplimiento y Antivirus de Microsoft Defender
description: Use una herramienta para recopilar datos para solucionar problemas de cumplimiento de actualizaciones al usar el complemento Evaluación del antivirus de Microsoft Defender.
keywords: solución de problemas, error, corrección, cumplimiento de actualizaciones, oms, supervisión, informe, Antivirus de Microsoft Defender, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: b21201d5b3a24c570819ac903eb3a38058c362c8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479828"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Recopilación de datos de diagnóstico de cumplimiento de actualizaciones para la evaluación del Antivirus de Microsoft Defender


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este artículo se describe cómo recopilar datos de diagnóstico que pueden usar los equipos de ingeniería y soporte técnico de Microsoft para ayudar a solucionar problemas que puede encontrar al usar la sección Evaluación del antivirus de Microsoft Defender en el complemento De cumplimiento de actualizaciones.

Antes de intentar este proceso, asegúrese de que ha leído [Solución de problemas de informes del Antivirus de Microsoft Defender](troubleshoot-reporting.md), ha cumplido todos los requisitos previos necesarios y ha tomado cualquier otro paso de solución de problemas sugerido.

En al menos dos dispositivos que no informan ni aparecen en Cumplimiento de actualizaciones, obtenga el archivo de diagnóstico .cab siguiendo estos pasos:

1. Abra una versión de nivel de administrador del símbolo del sistema como se indica a continuación:

    a. Abra el menú **Inicio** .

    b. Escriba **cmd**. Haga clic con el botón derecho en símbolo **del sistema** y seleccione **Ejecutar como administrador**.

    c. Especifique las credenciales de administrador o apruebe el símbolo del sistema.

2. Vaya al directorio Windows Defender. El valor predeterminado es `C:\Program Files\Windows Defender`

3. Escriba el comando siguiente y, a continuación, presione **Entrar.**

    ```Dos
    mpcmdrun -getfiles
    ```

4. Se generará un archivo .cab que contiene varios registros de diagnóstico. La ubicación del archivo se especificará en la salida del símbolo del sistema. De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.

5. Copie estos archivos .cab en una ubicación a la que pueda acceder el soporte técnico de Microsoft. Un ejemplo podría ser una carpeta de OneDrive protegida con contraseña que puede compartir con nosotros.

6. Envíe un correo electrónico con la <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">plantilla de correo electrónico de compatibilidad con el cumplimiento de actualizaciones</a> y rellene la plantilla con la siguiente información:

    ```text
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:

    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Vea también

- [Solución de problemas de informes del Antivirus de Microsoft Defender](troubleshoot-reporting.md)
