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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845371"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Programar exámenes con Microsoft Defender para endpoint (Linux)

Para ejecutar un examen para Linux, vea [Comandos admitidos](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.

## <a name="pre-requisite"></a>Requisito previo

> [!NOTE]
> Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`<br>
> Ejemplos de zonas horarias:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para establecer el trabajo cron
Use los siguientes comandos:

**Para hacer una copia de seguridad de las entradas de tabla crontab**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Where 200919 == YRMMDD

> [!TIP]
> Haga esto antes de editar o quitar. <br>

Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz: <br>
`sudo crontab -e`

> [!NOTE]
> El editor predeterminado es VIM.

Es posible que vea:

0 * * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Presione "Insertar"

Agregue las siguientes entradas:

CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>En este ejemplo, lo hemos establecido en 00 minutos, 2 a.m. (hora en formato de 24 horas), cualquier día del mes, cualquier mes, los sábados. Lo que significa que se ejecutará los sábados a las 2:00 a.m. Pacífico (UTC –8).

Presione "Esc"

Escriba ":wq" sin las comillas dobles.

> [!NOTE]
> w == write, q == quit

Para ver los trabajos de cron, escriba `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**Para inspeccionar las ejecuciones de trabajos cron**

`sudo grep mdatp /var/log/cron`

**Para inspeccionar el archivo mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Para aquellos que usan Ansible, Chef o Puppet

Use los siguientes comandos:
### <a name="to-set-cron-jobs-in-ansible"></a>Para establecer trabajos de cron en Ansible

`cron – Manage cron.d and crontab entries`

Vea [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obtener más información.

### <a name="to-set-crontabs-in-chef"></a>Para establecer las fichas cron en El chef
`cron resource`

Vea [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obtener más información.

### <a name="to-set-cron-jobs-in-puppet"></a>Para establecer trabajos de cron en Puppet
Tipo de recurso: cron

Vea [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obtener más información.

Automatizar con Puppet: trabajos cron y tareas programadas

Vea [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obtener más información.

## <a name="additional-information"></a>Información adicional

**Para obtener ayuda con crontab**

`man crontab`

**Para obtener una lista del archivo crontab del usuario actual**

`crontab -l`

**Para obtener una lista del archivo crontab de otro usuario**

`crontab -u username -l`

**Para hacer una copia de seguridad de las entradas de tabla crontab**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Haga esto antes de editar o quitar. <br>

**Para restaurar entradas de tabla crontab**

`crontab /var/tmp/cron_backup.dat`

**Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz**

`sudo crontab -e`

**Para editar la tabla crontab y agregar un nuevo trabajo**

`crontab -e`

**Para editar las entradas crontab de otro usuario**

`crontab -u username -e`

**Para quitar todas las entradas de tabla crontab**

`crontab -r`

**Para quitar las entradas de tabla cron de otro usuario**

`crontab -u username -r`

**Explicación**

+—————- minuto (valores: 0 – 59) (caracteres especiales: , – * /)  <br>
| +————- hora (valores: 0 – 23) (caracteres especiales: , – * /) <br>
| | +———- día del mes (valores: 1 – 31) (caracteres especiales: , – * / L W C)  <br>
| | | +——- mes (valores: 1 – 12) (caracteres especiales: ,- * / )  <br>
| | | | +—- día de la semana (valores: 0 – 6) (sunday=0 o 7) (caracteres especiales: , – * / L W C) <br>
| | | | |*****comando que se va a ejecutar


