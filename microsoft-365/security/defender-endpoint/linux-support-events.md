---
title: Solucionar problemas de alertas o eventos que faltan para Microsoft Defender para Endpoint en Linux
description: Solucionar problemas de alertas o eventos que faltan en Microsoft Defender para Endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, eventos
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 5a17f94e3d26c08c0f6e0ca358778a65189cf6a5
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766027"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solucionar problemas de alertas o eventos que faltan para Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este artículo se proporcionan algunos pasos generales para mitigar los eventos o alertas que <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">faltan en Microsoft 365 Defender portal</a>.

Una **vez que Microsoft Defender para endpoint** se haya instalado correctamente en un dispositivo,  se generará una página de dispositivo en el portal. Puedes revisar todos los eventos registrados en la pestaña escala de tiempo de la página del dispositivo o en la página de búsqueda avanzada. En esta sección se soluciona el caso de que faltan algunos o todos los eventos esperados.
Por ejemplo, si faltan todos los eventos _CreatedFile_ .

## <a name="missing-network-and-login-events"></a>Faltan eventos de red e inicio de sesión

Microsoft Defender para endpoint utilizó `audit` el marco de linux para realizar un seguimiento de la actividad de red e inicio de sesión.

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

2. Si `auditd` está marcado como detenido, indábalo.

    ```bash
    service auditd start
    ```

**En los sistemas SLES** , la auditoría de SYSCALL puede `auditd` deshabilitarse de forma predeterminada y puede tenerse en cuenta si faltan eventos.

1. Para validar que la auditoría de SYSCALL no está deshabilitada, enumere las reglas de auditoría actuales:

    ```bash
    sudo auditctl -l
    ```

    si la siguiente línea está presente, quítela o edite para permitir que Microsoft Defender for Endpoint realice un seguimiento de syscalls específicos.

    ```output
    -a task, never
    ```

    las reglas de auditoría se encuentran en `/etc/audit/rules.d/audit.rules`.

## <a name="missing-file-events"></a>Eventos de archivo que faltan

Los eventos de archivo se recopilan con `fanotify` framework. En caso de que falte alguno o todos los eventos de archivo, `fanotify` asegúrese de que está habilitado en el dispositivo y de que el sistema de [archivos es compatible](microsoft-defender-endpoint-linux.md#system-requirements).

Enumere los sistemas de archivos del equipo con:

```bash
df -Th
```
