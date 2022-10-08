---
title: Habilitar y actualizar Microsoft Defender Antivirus en Windows Server
description: Obtenga información sobre cómo habilitar y actualizar Microsoft Defender Antivirus en Windows Server
keywords: Windows Server, Defender Antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
ms.localizationpriority: high
ms.date: 08/10/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: intro-overview
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 16c1dc690ad6cf297059b8589818cb57596b7a9e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203671"
---
# <a name="enable-and-update-defender-antivirus-to-the-latest-version-on-windows-server"></a>Habilitación y actualización del Antivirus de Defender a la versión más reciente en Windows Server

Si desea usar Microsoft Defender Antivirus en Windows Server y se ha deshabilitado o desinstalado anteriormente, es posible que tenga que seguir los pasos necesarios para volver a habilitarlo y asegurarse de que está totalmente actualizado.

Para habilitar y actualizar Microsoft Defender Antivirus en Windows Server, siga estos pasos:

1. Instale la última actualización de pila de mantenimiento (SSU).
2. Instale la última actualización acumulativa (LCU).
3. Vuelva a instalar Microsoft Defender Antivirus o vuelva a habilitarlo. Para obtener más información sobre cómo volver a instalar o volver a habilitar Microsoft Defender Antivirus en Windows Server, consulta [Volver a habilitar Microsoft Defender Antivirus en Windows Server si se ha deshabilitado](#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled) y [Volver a habilitar Microsoft Defender Antivirus en Windows Server si se ha desinstalado](#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled).
4. Reinicie el sistema.
5. Instale la versión más reciente de la actualización de la plataforma.

   > [!NOTE]
   > Volver a habilitar Microsoft Defender Antivirus no instala automáticamente la actualización de la plataforma. Puede descargar e instalar la versión más reciente de la plataforma mediante Windows Update. Como alternativa, puede descargar el paquete de actualización desde el [catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) o desde el [portal antimalware y ciberseguridad](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64).
   >  
   > Si se está preparando para instalar la solución moderna y unificada en Windows Server 2016, puede aprovechar el [script de ayuda del instalador](https://github.com/microsoft/mdefordownlevelserver/blob/main/Install.ps1) para automatizar la actualización de la plataforma y la instalación e incorporación posteriores. Este script también puede ayudar a volver a habilitar Microsoft Defender Antivirus.

## <a name="re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled"></a>Volver a habilitar Microsoft Defender Antivirus en Windows Server si se ha deshabilitado

En primer lugar, asegúrese de que Microsoft Defender Antivirus no esté deshabilitado a través de directiva de grupo o registro. Para obtener más información, consulte [Solución de problemas de Microsoft Defender Antivirus al migrar desde una solución de terceros](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus-when-migrating).

En Windows Server 2016, en algunos casos, es posible que tenga que usar la Utilidad de [protección contra malware Command-Line](command-line-arguments-microsoft-defender-antivirus.md) para volver a habilitar Microsoft Defender Antivirus.

Como administrador local en el servidor, realice los pasos siguientes:

1. Abra Símbolo del sistema.
2. Ejecute el siguiente comando: `MpCmdRun.exe -wdenable`.
3. Reinicie el dispositivo.

## <a name="re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled"></a>Volver a habilitar Microsoft Defender Antivirus en Windows Server si se ha desinstalado

En caso de que la característica de Defender se haya desinstalado o quitado, puede volver a agregarla.

Como administrador local en el servidor, realice los pasos siguientes:

1. Abra Windows PowerShell.

2. Ejecute los comandos siguientes:

   ```powershell
   # For Windows Server 2016
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Gui
   
   # For Windows Server 1803 and later, including Windows Server 2019 and 2022
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   ```

   Cuando se usa el comando DISM dentro de una secuencia de tareas que ejecuta PowerShell, se requiere la siguiente ruta de acceso a cmd.exe.
   
   ```powershell
   C:\Windows\System32\cmd.exe /c Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Features
   C:\Windows\System32\cmd.exe /c Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   ```

   > [!NOTE]
   > También puede usar cmdlets de Administrador del servidor o PowerShell para instalar la característica antivirus de Microsoft Defender.

3. Reinicie el sistema.
