---
title: Programación de una actualización de la Microsoft Defender para punto de conexión (Linux)
description: Obtenga información sobre cómo programar una actualización de la Microsoft Defender para punto de conexión (Linux) para proteger mejor los recursos de su organización.
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
ms.openlocfilehash: 263ffb74d433ba75fa61a59c75b1132a845f2cef
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519718"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Programar una actualización de Microsoft Defender para punto de conexión (Linux)

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Para ejecutar una actualización en Microsoft Defender para punto de conexión en Linux, consulte [Implementación de actualizaciones para Microsoft Defender para punto de conexión en Linux](/microsoft-365/security/defender-endpoint/linux-updates).

Linux (y Unix) tienen una herramienta denominada **crontab** (similar a Task Scheduler) para poder ejecutar tareas programadas.

## <a name="pre-requisite"></a>Requisito previo

> [!NOTE]
> Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`
>
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
sudo crontab -l > /var/tmp/cron_backup_201118.dat
```

> [!NOTE]
> Donde 201118 == AAAA

> [!TIP]
> Haga esto antes de editar o quitar.

Para editar la crontab y agregar un nuevo trabajo como usuario raíz:

```bash
sudo crontab -e
```

> [!NOTE]
> El editor predeterminado es VIM.

Es posible que vea lo siguiente:

```output
0****/etc/opt/microsoft/mdatp/logrorate.sh
```

And

```output
02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log
```

Consulte [Programación de exámenes con Microsoft Defender para punto de conexión (Linux)](linux-schedule-scan-mde.md)

Presione "Insertar"

Agregue las siguientes entradas:

```bash
CRON_TZ=America/Los_Angeles
```

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL y variantes (CentOS y Oracle Linux)
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo yum update mdatp -y >> ~/mdatp_cron_job.log
> ```

> #<a name="sles-and-variants"></a>! SLES y variantes
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo zypper update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="ubuntu-and-debian-systems"></a>! Sistemas Ubuntu y Debian
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo apt-get install --only-upgrade mdatp >> ~/mdatp_cron_job.log
> ```

> [!NOTE]
> En los ejemplos anteriores, se establece en 00 minutos, 6 a.m. (hora en formato de 24 horas), cualquier día del mes, cualquier mes, los domingos. [$(date +\%d) -le 15] == No se ejecutará a menos que sea igual o menor que el día 15 (3ª semana). Lo que significa que se ejecutará cada 3er domingo (7) del mes a las 6:00 a.m. Pacífico (UTC -8).

Presione "Esc"

Escriba "`:wq`" con las comillas dobles.

> [!NOTE]
> w == write, q == quit

Para ver los trabajos cron, escriba `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="actualice Defender para punto de conexión en Linux.":::

Para inspeccionar las ejecuciones de trabajos cron:

```bash
sudo grep mdatp /var/log/cron
```

Para inspeccionar el mdatp_cron_job.log

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Para aquellos que usan Ansible, Chef o Puppet

Use los siguientes comandos:

### <a name="to-set-cron-jobs-in-ansible"></a>Para establecer trabajos cron en Ansible

```bash
cron - Manage cron.d and crontab entries
```

Vea <https://docs.ansible.com/ansible/latest/modules/cron_module.html> para obtener más información.

### <a name="to-set-crontabs-in-chef"></a>Para establecer crontabs en Chef

```bash
cron resource
```

Vea <https://docs.chef.io/resources/cron/> para obtener más información.

### <a name="to-set-cron-jobs-in-puppet"></a>Para establecer trabajos cron en Puppet

Tipo de recurso: cron

Vea <https://puppet.com/docs/puppet/5.5/types/cron.html> para obtener más información.

Automatización con Puppet: trabajos de Cron y tareas programadas

Vea <https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/> para obtener más información.

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

<pre>
+—————- minute (values: 0 - 59) (special characters: , - * /)  <br>
| +————- hour (values: 0 - 23) (special characters: , - * /) <br>
| | +———- day of month (values: 1 - 31) (special characters: , - * / L W C)  <br>
| | | +——- month (values: 1 - 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 - 6) (Sunday=0 or 7) (special characters: , - * / L W C) <br>
| | | | |*****command to be executed
</pre>
