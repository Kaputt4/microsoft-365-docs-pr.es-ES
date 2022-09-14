---
title: Solución de problemas de eventos o alertas que faltan para Microsoft Defender para punto de conexión en Linux
description: Solución de problemas de eventos o alertas que faltan en Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, eventos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 6ea07b089233217852b684009d8fea1280367e23
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687139"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solución de problemas de eventos o alertas que faltan para Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este artículo se proporcionan algunos pasos generales para mitigar los eventos o alertas que faltan en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

Una vez **que Microsoft Defender para punto de conexión** se haya instalado correctamente en un dispositivo, se generará una _página de dispositivo_ en el portal. Puede revisar todos los eventos grabados en la pestaña escala de tiempo de la página del dispositivo o en la página de búsqueda avanzada. En esta sección se soluciona el caso de que falten algunos o todos los eventos esperados.
Por ejemplo, si faltan todos los eventos _CreatedFile_ .

## <a name="missing-network-and-login-events"></a>Eventos de red e inicio de sesión que faltan

Microsoft Defender para punto de conexión marco de trabajo utilizado `audit` desde Linux para realizar un seguimiento de la actividad de red e inicio de sesión.

1. Asegúrese de que el marco de auditoría funciona.

    ```bash
    service auditd status
    ```

    salida esperada:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Si `auditd` está marcado como detenido, inícielo.

    ```bash
    service auditd start
    ```

En los sistemas **SLES**, la auditoría SYSCALL en podría estar deshabilitada de forma predeterminada y se puede tener en `auditd` cuenta los eventos que faltan.

1. Para validar que la auditoría SYSCALL no está deshabilitada, enumere las reglas de auditoría actuales:

    ```bash
    sudo auditctl -l
    ```

    si la línea siguiente está presente, quítela o edítela para habilitar Microsoft Defender para punto de conexión realizar un seguimiento de syscalls específicos.

    ```output
    -a task, never
    ```

    las reglas de auditoría se encuentran en `/etc/audit/rules.d/audit.rules`.

## <a name="missing-file-events"></a>Eventos de archivo que faltan

Los eventos de archivo se recopilan con `fanotify` framework. En caso de que falten algunos o todos los eventos de archivo, asegúrese de que `fanotify` está habilitado en el dispositivo y de que el sistema de archivos es [compatible](microsoft-defender-endpoint-linux.md#system-requirements).

Enumere los sistemas de archivos de la máquina con:

```bash
df -Th
```
