---
title: Configurar Antivirus de Microsoft Defender notificaciones
description: Obtenga información sobre cómo configurar y personalizar las notificaciones estándar y adicionales Antivirus de Microsoft Defender en los puntos de conexión.
keywords: notificaciones, defender, antivirus, punto de conexión, administración, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572350"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="41c1c-104">Configurar las notificaciones que aparecen en los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="41c1c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="41c1c-105">**Applies to:**</span></span>

- [<span data-ttu-id="41c1c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="41c1c-107">En Windows 10, las notificaciones de aplicaciones sobre detección y corrección de malware son más sólidas, coherentes y concisos.</span><span class="sxs-lookup"><span data-stu-id="41c1c-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="41c1c-108">Las notificaciones aparecen en los puntos de conexión cuando se desencadenan manualmente y se completan los exámenes programados y se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="41c1c-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="41c1c-109">Estas notificaciones también aparecen en el **Centro** de notificaciones y aparecen un resumen de exámenes y detecciones de amenazas en intervalos de tiempo regulares.</span><span class="sxs-lookup"><span data-stu-id="41c1c-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="41c1c-110">También puede configurar cómo aparecen las notificaciones estándar en los puntos de conexión, como las notificaciones para el reinicio o cuando se ha detectado y corregido una amenaza.</span><span class="sxs-lookup"><span data-stu-id="41c1c-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="41c1c-111">Configurar las notificaciones adicionales que aparecen en los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="41c1c-112">Puedes configurar la presentación de notificaciones adicionales, como resúmenes recientes de detección de amenazas, en la [aplicación](microsoft-defender-security-center-antivirus.md) Seguridad de Windows y con la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="41c1c-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="41c1c-113">En Windows 10, versión 1607, la característica se denomina notificaciones  **mejoradas** y se podía configurar en Windows Configuración  >  **Actualización & seguridad**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="41c1c-114">En configuración de directiva de grupo en todas las versiones de Windows 10, se denomina **Notificaciones mejoradas.**</span><span class="sxs-lookup"><span data-stu-id="41c1c-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41c1c-115">Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.</span><span class="sxs-lookup"><span data-stu-id="41c1c-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="41c1c-116">**Usa la Seguridad de Windows para deshabilitar notificaciones adicionales:**</span><span class="sxs-lookup"><span data-stu-id="41c1c-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="41c1c-117">Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="41c1c-118">Seleccione **Icono de protección contra &** virus (o el icono de escudo de la barra de menús izquierda) y, a continuación, seleccione Configuración de protección contra **&** virus</span><span class="sxs-lookup"><span data-stu-id="41c1c-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="41c1c-119">Desplácese a la **sección Notificaciones** y haga clic en Cambiar configuración **de notificación.**</span><span class="sxs-lookup"><span data-stu-id="41c1c-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="41c1c-120">Deslice el conmutador **a Desactivado** o **Encendido para** deshabilitar o habilitar notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="41c1c-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="41c1c-121">**Use la directiva de grupo para deshabilitar notificaciones adicionales:**</span><span class="sxs-lookup"><span data-stu-id="41c1c-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="41c1c-122">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="41c1c-123">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="41c1c-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="41c1c-124">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="41c1c-125">Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="41c1c-126">Haga doble clic **en Desactivar notificaciones mejoradas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="41c1c-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-127">Click **OK**.</span></span> <span data-ttu-id="41c1c-128">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="41c1c-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="41c1c-129">Configurar notificaciones estándar en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="41c1c-130">Puede usar la directiva de grupo para:</span><span class="sxs-lookup"><span data-stu-id="41c1c-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="41c1c-131">Mostrar texto adicional y personalizado en los puntos de conexión cuando el usuario necesita realizar una acción</span><span class="sxs-lookup"><span data-stu-id="41c1c-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="41c1c-132">Ocultar todas las notificaciones en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="41c1c-133">Ocultar notificaciones de reinicio en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41c1c-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="41c1c-134">Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz Antivirus de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="41c1c-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="41c1c-135">Consulta [Impedir que los usuarios vean o interactúen con la Antivirus de Microsoft Defender de usuario para](prevent-end-user-interaction-microsoft-defender-antivirus.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41c1c-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="41c1c-136">Las notificaciones ocultas solo se producirán en los puntos de conexión en los que se ha implementado la directiva.</span><span class="sxs-lookup"><span data-stu-id="41c1c-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="41c1c-137">Las notificaciones relacionadas con las acciones que deben realizarse (como un reinicio) seguirán apareciendo en el panel de supervisión Microsoft Endpoint Manager Endpoint Protection [informes.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="41c1c-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="41c1c-138">Consulta [Personalizar la aplicación Seguridad de Windows para](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) tu organización para obtener instrucciones para agregar información de contacto personalizada a las notificaciones que los usuarios ven en sus máquinas.</span><span class="sxs-lookup"><span data-stu-id="41c1c-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="41c1c-139">**Use la directiva de grupo para ocultar las notificaciones:**</span><span class="sxs-lookup"><span data-stu-id="41c1c-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="41c1c-140">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="41c1c-141">En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="41c1c-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="41c1c-142">Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > interfaz de cliente**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="41c1c-143">Haga doble clic **en Suprimir todas las notificaciones** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="41c1c-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-144">Click **OK**.</span></span> <span data-ttu-id="41c1c-145">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="41c1c-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="41c1c-146">**Use la directiva de grupo para ocultar las notificaciones de reinicio:**</span><span class="sxs-lookup"><span data-stu-id="41c1c-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="41c1c-147">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="41c1c-148">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="41c1c-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="41c1c-149">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="41c1c-150">Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > interfaz de cliente**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="41c1c-151">Haz doble clic **en Suprimir notificaciones de reinicio** y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="41c1c-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41c1c-152">Click **OK**.</span></span> <span data-ttu-id="41c1c-153">Esto impedirá que aparezcan notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="41c1c-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41c1c-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="41c1c-154">Related topics</span></span>

- [<span data-ttu-id="41c1c-155">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="41c1c-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="41c1c-156">Configurar la interacción del usuario final con Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41c1c-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
