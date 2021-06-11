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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="625ae-104">Programar exámenes con Microsoft Defender para endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="625ae-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="625ae-105">Para ejecutar un examen para Linux, vea [Comandos admitidos](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span><span class="sxs-lookup"><span data-stu-id="625ae-105">To run a scan for Linux, see [Supported Commands](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="625ae-106">Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.</span><span class="sxs-lookup"><span data-stu-id="625ae-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="625ae-107">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="625ae-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="625ae-108">Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="625ae-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="625ae-109">Ejemplos de zonas horarias:</span><span class="sxs-lookup"><span data-stu-id="625ae-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="625ae-110">Para establecer el trabajo cron</span><span class="sxs-lookup"><span data-stu-id="625ae-110">To set the Cron job</span></span>
<span data-ttu-id="625ae-111">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="625ae-111">Use the following commands:</span></span>

<span data-ttu-id="625ae-112">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="625ae-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="625ae-113">Where 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="625ae-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="625ae-114">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="625ae-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="625ae-115">Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz:</span><span class="sxs-lookup"><span data-stu-id="625ae-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="625ae-116">El editor predeterminado es VIM.</span><span class="sxs-lookup"><span data-stu-id="625ae-116">The default editor is VIM.</span></span>

<span data-ttu-id="625ae-117">Es posible que vea:</span><span class="sxs-lookup"><span data-stu-id="625ae-117">You might see:</span></span>

<span data-ttu-id="625ae-118">0 \* \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="625ae-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="625ae-119">Presione "Insertar"</span><span class="sxs-lookup"><span data-stu-id="625ae-119">Press “Insert”</span></span>

<span data-ttu-id="625ae-120">Agregue las siguientes entradas:</span><span class="sxs-lookup"><span data-stu-id="625ae-120">Add the following entries:</span></span>

<span data-ttu-id="625ae-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="625ae-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="625ae-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="625ae-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="625ae-123">En este ejemplo, lo hemos establecido en 00 minutos, 2 a.m.</span><span class="sxs-lookup"><span data-stu-id="625ae-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="625ae-124">(hora en formato de 24 horas), cualquier día del mes, cualquier mes, los sábados.</span><span class="sxs-lookup"><span data-stu-id="625ae-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="625ae-125">Lo que significa que se ejecutará los sábados a las 2:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="625ae-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="625ae-126">Pacífico (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="625ae-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="625ae-127">Presione "Esc"</span><span class="sxs-lookup"><span data-stu-id="625ae-127">Press “Esc”</span></span>

<span data-ttu-id="625ae-128">Escriba ":wq" sin las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="625ae-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="625ae-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="625ae-129">w == write, q == quit</span></span>

<span data-ttu-id="625ae-130">Para ver los trabajos de cron, escriba `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="625ae-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="625ae-132">**Para inspeccionar las ejecuciones de trabajos cron**</span><span class="sxs-lookup"><span data-stu-id="625ae-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="625ae-133">**Para inspeccionar el archivo mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="625ae-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="625ae-134">Para aquellos que usan Ansible, Chef o Puppet</span><span class="sxs-lookup"><span data-stu-id="625ae-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="625ae-135">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="625ae-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="625ae-136">Para establecer trabajos de cron en Ansible</span><span class="sxs-lookup"><span data-stu-id="625ae-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="625ae-137">Vea [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="625ae-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="625ae-138">Para establecer las fichas cron en El chef</span><span class="sxs-lookup"><span data-stu-id="625ae-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="625ae-139">Vea [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="625ae-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="625ae-140">Para establecer trabajos de cron en Puppet</span><span class="sxs-lookup"><span data-stu-id="625ae-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="625ae-141">Tipo de recurso: cron</span><span class="sxs-lookup"><span data-stu-id="625ae-141">Resource Type: cron</span></span>

<span data-ttu-id="625ae-142">Vea [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="625ae-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="625ae-143">Automatizar con Puppet: trabajos cron y tareas programadas</span><span class="sxs-lookup"><span data-stu-id="625ae-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="625ae-144">Vea [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="625ae-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="625ae-145">Información adicional</span><span class="sxs-lookup"><span data-stu-id="625ae-145">Additional information</span></span>

<span data-ttu-id="625ae-146">**Para obtener ayuda con crontab**</span><span class="sxs-lookup"><span data-stu-id="625ae-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="625ae-147">**Para obtener una lista del archivo crontab del usuario actual**</span><span class="sxs-lookup"><span data-stu-id="625ae-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="625ae-148">**Para obtener una lista del archivo crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="625ae-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="625ae-149">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="625ae-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="625ae-150">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="625ae-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="625ae-151">**Para restaurar entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="625ae-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="625ae-152">**Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz**</span><span class="sxs-lookup"><span data-stu-id="625ae-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="625ae-153">**Para editar la tabla crontab y agregar un nuevo trabajo**</span><span class="sxs-lookup"><span data-stu-id="625ae-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="625ae-154">**Para editar las entradas crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="625ae-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="625ae-155">**Para quitar todas las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="625ae-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="625ae-156">**Para quitar las entradas de tabla cron de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="625ae-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="625ae-157">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="625ae-157">**Explanation**</span></span>

<span data-ttu-id="625ae-158">+—————- minuto (valores: 0 – 59) (caracteres especiales: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="625ae-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="625ae-159">| +————- hora (valores: 0 – 23) (caracteres especiales: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="625ae-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="625ae-160">| | +———- día del mes (valores: 1 – 31) (caracteres especiales: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="625ae-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="625ae-161">| | | +——- mes (valores: 1 – 12) (caracteres especiales: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="625ae-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="625ae-162">| | | | +—- día de la semana (valores: 0 – 6) (sunday=0 o 7) (caracteres especiales: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="625ae-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="625ae-163">| | | | |\*\*\*\*\*comando que se va a ejecutar</span><span class="sxs-lookup"><span data-stu-id="625ae-163">| | | | |\*\*\*\*\*command to be executed</span></span>


