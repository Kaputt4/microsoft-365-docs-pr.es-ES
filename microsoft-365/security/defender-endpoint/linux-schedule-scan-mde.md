---
title: Programación de exámenes con Microsoft Defender para punto de conexión (Linux)
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para punto de conexión (Linux) para proteger mejor los recursos de su organización.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, scans, antivirus, microsoft defender for endpoint (linux)
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 21fbdd1e10fc929711944c2586e262c76e7a3905
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519762"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Programar exámenes con Microsoft Defender para punto de conexión (Linux)

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Para ejecutar un examen de Linux, consulte [Comandos admitidos](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

Linux (y Unix) tienen una herramienta denominada **crontab** (similar a Task Scheduler) para poder ejecutar tareas programadas.

## <a name="pre-requisite"></a>Requisito previo

> [!NOTE]
> Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`<br>
> Ejemplos de zonas horarias:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para establecer el trabajo de Cron

Use los siguientes comandos:

### <a name="backup-crontab-entries"></a>Entradas de crontab de copia de seguridad

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> Donde 200919 == YRMMDD

> [!TIP]
> Haga esto antes de editar o quitar.

Para editar la crontab y agregar un nuevo trabajo como usuario raíz:

```bash
sudo crontab -e
```

> [!NOTE]
> El editor predeterminado es VIM.

Es posible que vea lo siguiente:

```outbou
0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh
```

Presione "Insertar"

Agregue las siguientes entradas:

```bash
CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log
```

> [!NOTE]
> En este ejemplo, lo hemos establecido en 00 minutos, 2 a.m. (hora en formato de 24 horas), cualquier día del mes, cualquier mes, los sábados. Lo que significa que se ejecutará los sábados a las 2:00 a.m. Pacífico (UTC -8).

Presione "Esc"

Escriba "`:wq`" sin comillas dobles.

> [!NOTE]
> w == write, q == quit

Para ver los trabajos cron, escriba `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="Página mdatp de Linux" lightbox="../../media/linux-mdatp-1.png":::

#### <a name="to-inspect-cron-job-runs"></a>Para inspeccionar las ejecuciones de trabajos cron

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>Para inspeccionar el mdatp_cron_job.log*

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Para aquellos que usan Ansible, Chef o Puppet

Use los siguientes comandos:

### <a name="to-set-cron-jobs-in-ansible"></a>Para establecer trabajos cron en Ansible

```bash
cron - Manage cron.d and crontab entries

See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.

### To set crontabs in Chef

```bash
cron resource
```bash

```
Vea <https://docs.chef.io/resources/cron/> para obtener más información.

### <a name="to-set-cron-jobs-in-puppet"></a>Para establecer trabajos cron en Puppet

```bash
Resource Type: cron
```

Vea <https://puppet.com/docs/puppet/5.5/types/cron.html> para obtener más información.

Automatización con Puppet: trabajos de Cron y tareas programadas

Vea [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obtener más información.

## <a name="additional-information"></a>Información adicional

### <a name="to-get-help-with-crontab"></a>Para obtener ayuda con crontab

```bash
man crontab
```

### <a name="to-get-a-list-of-crontab-file-of-the-current-user"></a>Para obtener una lista del archivo crontab del usuario actual

```bash
crontab -l
```

### <a name="to-get-a-list-of-crontab-file-of-another-user"></a>Para obtener una lista del archivo crontab de otro usuario

```bash
crontab -u username -l
```

### <a name="to-backup-crontab-entries"></a>Para realizar una copia de seguridad de entradas de crontab

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> Haga esto antes de editar o quitar.

### <a name="to-restore-crontab-entries"></a>Para restaurar entradas de crontab

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>Para editar la crontab y agregar un nuevo trabajo como usuario raíz

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>Para editar el crontab y agregar un nuevo trabajo

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>Para editar las entradas de crontab de otro usuario

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>Para quitar todas las entradas de crontab

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>Para quitar las entradas de crontab de otro usuario

```bash
crontab -u username -r
```

### <a name="explanation"></a>Explicación

+—————- minuto (valores: 0 - 59) (caracteres especiales: , \- \* /)  <br>
| +————- hora (valores: 0 - 23) (caracteres especiales: , \- \* /) <br>
| | +———- día del mes (valores: 1 - 31) (caracteres especiales: , \- \* / L W C)  <br>
| | | +——- mes (valores: 1 - 12) (caracteres especiales: , \- \* / )  <br>
| | | | +—- día de la semana (valores: 0 - 6) (sunday=0 o 7) (caracteres especiales: , \- \* / L W C) <br>
comando | | | | |*****que se va a ejecutar
