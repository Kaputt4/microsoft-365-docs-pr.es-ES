---
title: Cómo programar una actualización de Microsoft Defender para Endpoint (Linux)
description: Obtenga información sobre cómo programar una actualización de Microsoft Defender para Endpoint (Linux) para proteger mejor los activos de su organización.
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
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730875"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="3cc41-104">Programar una actualización de Microsoft Defender para punto de conexión (Linux)</span><span class="sxs-lookup"><span data-stu-id="3cc41-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="3cc41-105">Para ejecutar una actualización en Microsoft Defender para Endpoint en Linux, consulte [Deploy updates for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-updates).</span><span class="sxs-lookup"><span data-stu-id="3cc41-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="3cc41-106">Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.</span><span class="sxs-lookup"><span data-stu-id="3cc41-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="3cc41-107">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="3cc41-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="3cc41-108">Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="3cc41-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="3cc41-109">Ejemplos de zonas horarias:</span><span class="sxs-lookup"><span data-stu-id="3cc41-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="3cc41-110">Para establecer el trabajo cron</span><span class="sxs-lookup"><span data-stu-id="3cc41-110">To set the Cron job</span></span>
<span data-ttu-id="3cc41-111">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="3cc41-111">Use the following commands:</span></span>

<span data-ttu-id="3cc41-112">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="3cc41-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="3cc41-113">Where 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="3cc41-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="3cc41-114">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="3cc41-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="3cc41-115">Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz:</span><span class="sxs-lookup"><span data-stu-id="3cc41-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="3cc41-116">El editor predeterminado es VIM.</span><span class="sxs-lookup"><span data-stu-id="3cc41-116">The default editor is VIM.</span></span>

<span data-ttu-id="3cc41-117">Es posible que vea:</span><span class="sxs-lookup"><span data-stu-id="3cc41-117">You might see:</span></span>

<span data-ttu-id="3cc41-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="3cc41-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="3cc41-119">And</span><span class="sxs-lookup"><span data-stu-id="3cc41-119">And</span></span>

<span data-ttu-id="3cc41-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="3cc41-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="3cc41-121">Consulta [Programar exámenes con Microsoft Defender para endpoint (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="3cc41-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="3cc41-122">Presione "Insertar"</span><span class="sxs-lookup"><span data-stu-id="3cc41-122">Press “Insert”</span></span>

<span data-ttu-id="3cc41-123">Agregue las siguientes entradas:</span><span class="sxs-lookup"><span data-stu-id="3cc41-123">Add the following entries:</span></span>

<span data-ttu-id="3cc41-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="3cc41-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="3cc41-125">! RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="3cc41-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="3cc41-126">! SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="3cc41-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="3cc41-127">! Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="3cc41-127">!Ubuntu and Debian systems</span></span>

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="3cc41-128">En los ejemplos anteriores, lo establecemos en 00 minutos, 6 a.m. (hora en formato de 24 horas), cualquier día del mes, cualquier mes, los domingos. [$(date + d) -le 15] == No se ejecutará a menos que sea igual o menor que el \% día 15 (3ª semana).</span><span class="sxs-lookup"><span data-stu-id="3cc41-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="3cc41-129">Lo que significa que se ejecutará cada tres domingos (7) del mes a las 6:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="3cc41-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="3cc41-130">Pacífico (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="3cc41-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="3cc41-131">Presione "Esc"</span><span class="sxs-lookup"><span data-stu-id="3cc41-131">Press “Esc”</span></span>

<span data-ttu-id="3cc41-132">Escriba ":wq" con las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="3cc41-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="3cc41-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="3cc41-133">w == write, q == quit</span></span>

<span data-ttu-id="3cc41-134">Para ver los trabajos de cron, escriba `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="3cc41-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="actualizar MDE linux":::

<span data-ttu-id="3cc41-136">Para inspeccionar las ejecuciones del trabajo cron: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="3cc41-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="3cc41-137">Para inspeccionar el archivo mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="3cc41-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="3cc41-138">Para aquellos que usan Ansible, Chef o Puppet</span><span class="sxs-lookup"><span data-stu-id="3cc41-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="3cc41-139">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="3cc41-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="3cc41-140">Para establecer trabajos de cron en Ansible</span><span class="sxs-lookup"><span data-stu-id="3cc41-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="3cc41-141">Vea [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc41-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="3cc41-142">Para establecer las fichas cron en El chef</span><span class="sxs-lookup"><span data-stu-id="3cc41-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="3cc41-143">Vea [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc41-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="3cc41-144">Para establecer trabajos de cron en Puppet</span><span class="sxs-lookup"><span data-stu-id="3cc41-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="3cc41-145">Tipo de recurso: cron</span><span class="sxs-lookup"><span data-stu-id="3cc41-145">Resource Type: cron</span></span>

<span data-ttu-id="3cc41-146">Vea [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc41-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="3cc41-147">Automatizar con Puppet: trabajos cron y tareas programadas</span><span class="sxs-lookup"><span data-stu-id="3cc41-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="3cc41-148">Vea [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc41-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="3cc41-149">Información adicional</span><span class="sxs-lookup"><span data-stu-id="3cc41-149">Additional information</span></span>

<span data-ttu-id="3cc41-150">**Para obtener ayuda con crontab**</span><span class="sxs-lookup"><span data-stu-id="3cc41-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="3cc41-151">**Para obtener una lista del archivo crontab del usuario actual**</span><span class="sxs-lookup"><span data-stu-id="3cc41-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="3cc41-152">**Para obtener una lista del archivo crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="3cc41-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="3cc41-153">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="3cc41-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="3cc41-154">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="3cc41-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="3cc41-155">**Para restaurar entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="3cc41-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="3cc41-156">**Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz**</span><span class="sxs-lookup"><span data-stu-id="3cc41-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="3cc41-157">**Para editar la tabla crontab y agregar un nuevo trabajo**</span><span class="sxs-lookup"><span data-stu-id="3cc41-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="3cc41-158">**Para editar las entradas crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="3cc41-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="3cc41-159">**Para quitar todas las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="3cc41-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="3cc41-160">**Para quitar las entradas de tabla cron de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="3cc41-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="3cc41-161">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="3cc41-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

