---
title: Configurar Antivirus de Microsoft Defender notificaciones
description: Obtenga información sobre cómo configurar y personalizar tanto las notificaciones estándar como otras Antivirus de Microsoft Defender en los puntos de conexión.
keywords: notificaciones, defender, antivirus, punto de conexión, administración, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985413"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="974a8-104">Configurar Antivirus de Microsoft Defender notificaciones que aparecen en los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="974a8-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="974a8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="974a8-105">**Applies to:**</span></span>

- [<span data-ttu-id="974a8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="974a8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="974a8-107">En Windows 10, las notificaciones de aplicaciones sobre detección y corrección de malware son más sólidas, coherentes y concisos.</span><span class="sxs-lookup"><span data-stu-id="974a8-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="974a8-108">Antivirus de Microsoft Defender notificaciones aparecen en los puntos de conexión cuando se completan los exámenes y se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="974a8-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="974a8-109">Las notificaciones siguen exámenes programados y activados manualmente.</span><span class="sxs-lookup"><span data-stu-id="974a8-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="974a8-110">Estas notificaciones también aparecen en el **Centro** de notificaciones y aparecen un resumen de exámenes y detecciones de amenazas en intervalos de tiempo regulares.</span><span class="sxs-lookup"><span data-stu-id="974a8-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="974a8-111">Si forma parte del equipo de seguridad de su organización, puede configurar cómo aparecen las notificaciones en los puntos de conexión, como las notificaciones que solicitan un reinicio del sistema o que indican que se ha detectado y corregido una amenaza.</span><span class="sxs-lookup"><span data-stu-id="974a8-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="974a8-112">Configurar notificaciones antivirus mediante la directiva de grupo o la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="974a8-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="974a8-113">Puedes configurar la presentación de notificaciones adicionales, como resúmenes recientes de detección de amenazas, en la [aplicación](microsoft-defender-security-center-antivirus.md) Seguridad de Windows y con la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="974a8-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="974a8-114">En Windows 10 versión 1607, la característica se denomina **notificaciones mejoradas** y se configuró en Windows Configuración   >  **Actualización & seguridad**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="974a8-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="974a8-115">En Configuración de directiva de grupo para todas las versiones Windows 10, la característica de notificación se denomina **Notificaciones mejoradas.**</span><span class="sxs-lookup"><span data-stu-id="974a8-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="974a8-116">Usar la directiva de grupo para deshabilitar notificaciones adicionales</span><span class="sxs-lookup"><span data-stu-id="974a8-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="974a8-117">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="974a8-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="974a8-118">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="974a8-119">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="974a8-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="974a8-120">Seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="974a8-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="974a8-121">Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender** > reporting\*\*.</span><span class="sxs-lookup"><span data-stu-id="974a8-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="974a8-122">Haga doble clic **en Desactivar notificaciones mejoradas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="974a8-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="974a8-123">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-123">Then select **OK**.</span></span> <span data-ttu-id="974a8-124">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="974a8-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="974a8-125">Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.</span><span class="sxs-lookup"><span data-stu-id="974a8-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="974a8-126">Usar la Seguridad de Windows para deshabilitar notificaciones adicionales</span><span class="sxs-lookup"><span data-stu-id="974a8-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="974a8-127">Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="974a8-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="974a8-128">Seleccione **Icono de protección contra &** virus (o el icono de escudo de la barra de menús izquierda) y, a continuación, seleccione Configuración de protección contra **&** virus</span><span class="sxs-lookup"><span data-stu-id="974a8-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="974a8-129">Desplácese a la **sección Notificaciones** y seleccione Cambiar configuración **de notificación.**</span><span class="sxs-lookup"><span data-stu-id="974a8-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="974a8-130">Deslice el conmutador **a Desactivado** o **Encendido para** deshabilitar o habilitar notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="974a8-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="974a8-131">Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.</span><span class="sxs-lookup"><span data-stu-id="974a8-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="974a8-132">Configurar notificaciones estándar en puntos de conexión mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="974a8-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="974a8-133">Puede usar la directiva de grupo para:</span><span class="sxs-lookup"><span data-stu-id="974a8-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="974a8-134">Mostrar texto adicional y personalizado en los puntos de conexión cuando el usuario necesita realizar una acción</span><span class="sxs-lookup"><span data-stu-id="974a8-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="974a8-135">Ocultar todas las notificaciones en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="974a8-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="974a8-136">Ocultar notificaciones de reinicio en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="974a8-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="974a8-137">Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz Antivirus de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="974a8-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="974a8-138">Consulta [Impedir que los usuarios vean o interactúen con la Antivirus de Microsoft Defender de usuario para](prevent-end-user-interaction-microsoft-defender-antivirus.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="974a8-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="974a8-139">Las notificaciones ocultas solo se producirán en los puntos de conexión en los que se ha implementado la directiva.</span><span class="sxs-lookup"><span data-stu-id="974a8-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="974a8-140">Las notificaciones relacionadas con las acciones que deben realizarse (como un reinicio) seguirán apareciendo en el panel de supervisión Microsoft Endpoint Manager Endpoint Protection [informes.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="974a8-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="974a8-141">Para agregar información de contacto personalizada a las notificaciones de punto de conexión, [consulta Personalizar la aplicación Seguridad de Windows para tu organización.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="974a8-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="974a8-142">Usar la directiva de grupo para ocultar notificaciones</span><span class="sxs-lookup"><span data-stu-id="974a8-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="974a8-143">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="974a8-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="974a8-144">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="974a8-145">En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y,** a continuación, seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="974a8-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="974a8-146">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** interfaz  >    >  **de cliente**.</span><span class="sxs-lookup"><span data-stu-id="974a8-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="974a8-147">Haga doble clic **en Suprimir todas las notificaciones** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="974a8-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="974a8-148">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-148">Select **OK**.</span></span> <span data-ttu-id="974a8-149">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="974a8-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="974a8-150">Usar la directiva de grupo para ocultar las notificaciones de reinicio</span><span class="sxs-lookup"><span data-stu-id="974a8-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="974a8-151">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="974a8-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="974a8-152">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="974a8-153">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="974a8-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="974a8-154">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="974a8-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="974a8-155">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** interfaz  >    >  **de cliente**.</span><span class="sxs-lookup"><span data-stu-id="974a8-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="974a8-156">Haz doble clic **en Suprimir notificaciones de reinicio** y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="974a8-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="974a8-157">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="974a8-157">Select **OK**.</span></span> <span data-ttu-id="974a8-158">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="974a8-158">This will prevent additional notifications from appearing.</span></span>

