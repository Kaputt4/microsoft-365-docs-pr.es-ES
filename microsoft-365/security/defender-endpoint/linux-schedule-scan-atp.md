---
title: Cómo programar exámenes con Microsoft Defender para endpoint (Linux)
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para Endpoint (Linux) para proteger mejor los activos de su organización.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, exámenes, antivirus, microsoft defender para endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d1f6f004738dc50238b0941f7c7182400117fb50
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58559015"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Programar exámenes con Microsoft Defender para endpoint (Linux)

Para ejecutar un examen para Linux, vea [Comandos admitidos](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.

## <a name="pre-requisite"></a>Requisito previo

> [!NOTE]
> Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`<br>
> Ejemplos de zonas horarias:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para establecer el trabajo cron

Use los siguientes comandos:

### <a name="backup-crontab-entries"></a>Entradas de tabla crontab de copia de seguridad

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> Donde 200919 == YRMMDD

> [!TIP]
> Haga esto antes de editar o quitar.

Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz:

```bash
sudo crontab -e
```

> [!NOTE]
> El editor predeterminado es VIM.

Es posible que vea:

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

Escriba " `:wq` " sin las comillas dobles.

> [!NOTE]
> w == write, q == quit

Para ver los trabajos de cron, escriba `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="linux mdatp.":::

#### <a name="to-inspect-cron-job-runs"></a>Para inspeccionar las ejecuciones de trabajos cron

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>Para inspeccionar el archivo mdatp_cron_job.log*

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Para aquellos que usan Ansible, Chef o Puppet

Use los siguientes comandos:

### <a name="to-set-cron-jobs-in-ansible"></a>Para establecer trabajos de cron en Ansible

```bash
cron - Manage cron.d and crontab entries

See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.

### To set crontabs in Chef

```bash
cron resource
```bash

```
Vea <https://docs.chef.io/resources/cron/> para obtener más información.

### <a name="to-set-cron-jobs-in-puppet"></a>Para establecer trabajos de cron en Puppet

```bash
Resource Type: cron
```

Vea <https://puppet.com/docs/puppet/5.5/types/cron.html> para obtener más información.

Automatizar con Puppet: trabajos cron y tareas programadas

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

### <a name="to-backup-crontab-entries"></a>Para hacer una copia de seguridad de las entradas de tabla crontab

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> Haga esto antes de editar o quitar.

### <a name="to-restore-crontab-entries"></a>Para restaurar entradas de tabla crontab

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>Para editar la tabla crontab y agregar un nuevo trabajo

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>Para editar las entradas crontab de otro usuario

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>Para quitar todas las entradas de tabla crontab

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>Para quitar las entradas de tabla cron de otro usuario

```bash
crontab -u username -r
```

### <a name="explanation"></a>Explicación

+—————- minuto (valores: 0 - 59) (caracteres especiales: , - * /)  <br>
| +————- hora (valores: 0 - 23) (caracteres especiales: , - * /) <br>
| | +———- día del mes (valores: 1 - 31) (caracteres especiales: , - * / L W C)  <br>
| | | +——- mes (valores: 1 - 12) (caracteres especiales: ,- * / )  <br>
| | | | +—- día de la semana (valores: 0 - 6) (sunday=0 o 7) (caracteres especiales: , - * / L W C) <br>
| | | | |*****comando que se va a ejecutar
