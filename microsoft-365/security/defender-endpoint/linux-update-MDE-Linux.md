---
title: Cómo programar una actualización de Microsoft Defender para Endpoint (Linux)
description: Obtenga información sobre cómo programar una actualización de Microsoft Defender para Endpoint (Linux) para proteger mejor los activos de su organización.
keywords: microsoft, defender, atp, linux, exámenes, antivirus, microsoft defender para el punto de conexión (linux)
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
ms.openlocfilehash: b4c2e4d80628dab40de9e99abb27237176b9f171
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070504"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Programar una actualización de Microsoft Defender para endpoint (Linux)

Para ejecutar una actualización en Microsoft Defender para Endpoint para Linux, consulte [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).

Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.

## <a name="pre-requisite"></a>Requisito previo

> [!NOTE]
> Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`<br>
> Ejemplos de zonas horarias: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para establecer el trabajo cron
Use los siguientes comandos:

**Para hacer una copia de seguridad de las entradas de tabla crontab**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Where 201118 == YYMMDD

> [!TIP]
> Haga esto antes de editar o quitar. <br>

Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz: <br>
`sudo crontab -e`

> [!NOTE]
> El editor predeterminado es VIM.

Es posible que vea:

0****/etc/opt/microsoft/mdatp/logrorate.sh

And

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Consulta [Programar exámenes con Microsoft Defender para endpoint (Linux)](linux-schedule-scan-atp.md)

Presione "Insertar"

Agregue las siguientes entradas:

CRON_TZ=America/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL y variantes (CentOS y Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES y variantes

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Sistemas Ubuntu y Debian

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> En los ejemplos anteriores, lo establecemos en 00 minutos, 6 a.m. (hora en formato de 24 horas), cualquier día del mes, cualquier mes, los domingos. [$(date + d) -le 15] == No se ejecutará a menos que sea igual o menor que el \% día 15 (3ª semana). Lo que significa que se ejecutará cada tres domingos (7) del mes a las 6:00 a.m. Pacífico (UTC -8).

Presione "Esc"

Escriba ":wq" con las comillas dobles.

> [!NOTE]
> w == write, q == quit

Para ver los trabajos de cron, escriba `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="actualizar MDE linux":::

Para inspeccionar las ejecuciones del trabajo cron: `sudo grep mdatp /var/log/cron`

Para inspeccionar el archivo mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

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

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

