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
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933138"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="41422-104">Programar exámenes con Microsoft Defender para endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="41422-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="41422-105">Para ejecutar un examen para Linux, vea [Comandos admitidos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span><span class="sxs-lookup"><span data-stu-id="41422-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="41422-106">Linux (y Unix) tienen una herramienta denominada **crontab** (similar al Programador de tareas) para poder ejecutar tareas programadas.</span><span class="sxs-lookup"><span data-stu-id="41422-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="41422-107">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="41422-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="41422-108">Para obtener una lista de todas las zonas horarias, ejecute el siguiente comando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="41422-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="41422-109">Ejemplos de zonas horarias:</span><span class="sxs-lookup"><span data-stu-id="41422-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="41422-110">Para establecer el trabajo cron</span><span class="sxs-lookup"><span data-stu-id="41422-110">To set the Cron job</span></span>
<span data-ttu-id="41422-111">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="41422-111">Use the following commands:</span></span>

<span data-ttu-id="41422-112">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="41422-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="41422-113">Where 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="41422-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="41422-114">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="41422-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="41422-115">Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz:</span><span class="sxs-lookup"><span data-stu-id="41422-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="41422-116">El editor predeterminado es VIM.</span><span class="sxs-lookup"><span data-stu-id="41422-116">The default editor is VIM.</span></span>

<span data-ttu-id="41422-117">Es posible que vea:</span><span class="sxs-lookup"><span data-stu-id="41422-117">You might see:</span></span>

<span data-ttu-id="41422-118">0 \* \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="41422-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="41422-119">Presione "Insertar"</span><span class="sxs-lookup"><span data-stu-id="41422-119">Press “Insert”</span></span>

<span data-ttu-id="41422-120">Agregue las siguientes entradas:</span><span class="sxs-lookup"><span data-stu-id="41422-120">Add the following entries:</span></span>

<span data-ttu-id="41422-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="41422-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="41422-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="41422-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="41422-123">En este ejemplo, lo hemos establecido en 00 minutos, 2 a.m.</span><span class="sxs-lookup"><span data-stu-id="41422-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="41422-124">(hora en formato de 24 horas), cualquier día del mes, cualquier mes, los sábados.</span><span class="sxs-lookup"><span data-stu-id="41422-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="41422-125">Lo que significa que se ejecutará los sábados a las 2:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="41422-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="41422-126">Pacífico (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="41422-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="41422-127">Presione "Esc"</span><span class="sxs-lookup"><span data-stu-id="41422-127">Press “Esc”</span></span>

<span data-ttu-id="41422-128">Escriba ":wq" sin las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="41422-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="41422-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="41422-129">w == write, q == quit</span></span>

<span data-ttu-id="41422-130">Para ver los trabajos de cron, escriba `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="41422-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="41422-132">**Para inspeccionar las ejecuciones de trabajos cron**</span><span class="sxs-lookup"><span data-stu-id="41422-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="41422-133">**Para inspeccionar el archivo mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="41422-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="41422-134">Para aquellos que usan Ansible, Chef o Puppet</span><span class="sxs-lookup"><span data-stu-id="41422-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="41422-135">Use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="41422-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="41422-136">Para establecer trabajos de cron en Ansible</span><span class="sxs-lookup"><span data-stu-id="41422-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="41422-137">Vea [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41422-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="41422-138">Para establecer las fichas cron en El chef</span><span class="sxs-lookup"><span data-stu-id="41422-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="41422-139">Vea [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41422-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="41422-140">Para establecer trabajos de cron en Puppet</span><span class="sxs-lookup"><span data-stu-id="41422-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="41422-141">Tipo de recurso: cron</span><span class="sxs-lookup"><span data-stu-id="41422-141">Resource Type: cron</span></span>

<span data-ttu-id="41422-142">Vea [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41422-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="41422-143">Automatizar con Puppet: trabajos cron y tareas programadas</span><span class="sxs-lookup"><span data-stu-id="41422-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="41422-144">Vea [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41422-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="41422-145">Información adicional</span><span class="sxs-lookup"><span data-stu-id="41422-145">Additional information</span></span>

<span data-ttu-id="41422-146">**Para obtener ayuda con crontab**</span><span class="sxs-lookup"><span data-stu-id="41422-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="41422-147">**Para obtener una lista del archivo crontab del usuario actual**</span><span class="sxs-lookup"><span data-stu-id="41422-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="41422-148">**Para obtener una lista del archivo crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="41422-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="41422-149">**Para hacer una copia de seguridad de las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="41422-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="41422-150">Haga esto antes de editar o quitar.</span><span class="sxs-lookup"><span data-stu-id="41422-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="41422-151">**Para restaurar entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="41422-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="41422-152">**Para editar la tabla crontab y agregar un nuevo trabajo como usuario raíz**</span><span class="sxs-lookup"><span data-stu-id="41422-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="41422-153">**Para editar la tabla crontab y agregar un nuevo trabajo**</span><span class="sxs-lookup"><span data-stu-id="41422-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="41422-154">**Para editar las entradas crontab de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="41422-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="41422-155">**Para quitar todas las entradas de tabla crontab**</span><span class="sxs-lookup"><span data-stu-id="41422-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="41422-156">**Para quitar las entradas de tabla cron de otro usuario**</span><span class="sxs-lookup"><span data-stu-id="41422-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="41422-157">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="41422-157">**Explanation**</span></span>

<span data-ttu-id="41422-158">+—————- minuto (valores: 0 – 59) (caracteres especiales: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="41422-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="41422-159">| +————- hora (valores: 0 – 23) (caracteres especiales: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="41422-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="41422-160">| | +———- día del mes (valores: 1 – 31) (caracteres especiales: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="41422-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="41422-161">| | | +——- mes (valores: 1 – 12) (caracteres especiales: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="41422-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="41422-162">| | | | +—- día de la semana (valores: 0 – 6) (sunday=0 o 7) (caracteres especiales: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="41422-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="41422-163">| | | | |\*\*\*\*\*comando que se va a ejecutar</span><span class="sxs-lookup"><span data-stu-id="41422-163">| | | | |\*\*\*\*\*command to be executed</span></span>


