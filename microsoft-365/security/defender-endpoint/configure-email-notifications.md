---
title: Configurar notificaciones de alertas en Microsoft Defender para endpoint
description: Puedes usar Microsoft Defender para Endpoint para configurar las opciones de notificación de correo electrónico para alertas de seguridad, según la gravedad y otros criterios.
keywords: notificaciones de correo electrónico, configurar notificaciones de alertas, notificaciones de atp de Microsoft Defender, alertas de atp de Microsoft Defender, windows 10 enterprise, windows 10 education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5a19464b9d5d1b9659d7bfae2d853f7a640a00b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687894"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c0a73-104">Configurar notificaciones de alertas en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c0a73-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0a73-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c0a73-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0a73-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c0a73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0a73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0a73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c0a73-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c0a73-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c0a73-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c0a73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="c0a73-110">Puede configurar Defender for Endpoint para enviar notificaciones por correo electrónico a destinatarios especificados para nuevas alertas.</span><span class="sxs-lookup"><span data-stu-id="c0a73-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="c0a73-111">Esta característica le permite identificar un grupo de personas que se informarán inmediatamente y pueden actuar en alertas en función de su gravedad.</span><span class="sxs-lookup"><span data-stu-id="c0a73-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="c0a73-112">Solo los usuarios con permisos de "Administrar configuración de seguridad" pueden configurar las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="c0a73-113">Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="c0a73-114">Puede establecer los niveles de gravedad de alerta que desencadenan las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c0a73-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="c0a73-115">También puede agregar o quitar destinatarios de la notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="c0a73-116">Los nuevos destinatarios reciben notificaciones sobre las alertas desencadenadas después de agregarse.</span><span class="sxs-lookup"><span data-stu-id="c0a73-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="c0a73-117">Para obtener más información acerca de las alertas, vea [Ver y organizar la cola de alertas](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c0a73-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="c0a73-118">Si usas el control de acceso basado en roles (RBAC), los destinatarios solo recibirán notificaciones en función de los grupos de dispositivos configurados en la regla de notificación.</span><span class="sxs-lookup"><span data-stu-id="c0a73-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="c0a73-119">Los usuarios con el permiso adecuado solo pueden crear, editar o eliminar notificaciones limitadas al ámbito de administración de grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c0a73-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="c0a73-120">Solo los usuarios asignados al rol de administrador global pueden administrar las reglas de notificación configuradas para todos los grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c0a73-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="c0a73-121">La notificación por correo electrónico incluye información básica sobre la alerta y un vínculo al portal donde puede realizar más investigaciones.</span><span class="sxs-lookup"><span data-stu-id="c0a73-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="c0a73-122">Crear reglas para notificaciones de alertas</span><span class="sxs-lookup"><span data-stu-id="c0a73-122">Create rules for alert notifications</span></span>
<span data-ttu-id="c0a73-123">Puede crear reglas que determinen los dispositivos y las gravedades de alerta para enviar notificaciones por correo electrónico y los destinatarios de las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c0a73-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="c0a73-124">En el panel de navegación, seleccione **Configuración Notificaciones** de  >  **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="c0a73-125">Haga clic **en Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-125">Click **Add item**.</span></span>

3. <span data-ttu-id="c0a73-126">Especifique la información general:</span><span class="sxs-lookup"><span data-stu-id="c0a73-126">Specify the General information:</span></span>
    - <span data-ttu-id="c0a73-127">**Nombre de regla:** especifique un nombre para la regla de notificación.</span><span class="sxs-lookup"><span data-stu-id="c0a73-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="c0a73-128">**Incluir nombre de organización:** especifique el nombre del cliente que aparece en la notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="c0a73-129">**Incluir vínculo de portal específico del inquilino:** agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="c0a73-130">**Incluir información del dispositivo:** incluye el nombre del dispositivo en el cuerpo de la alerta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="c0a73-131">Es posible que los servidores de correo de destinatarios procese esta información que no se encuentra en la ubicación geográfica seleccionada para los datos del extremo de Defender.</span><span class="sxs-lookup"><span data-stu-id="c0a73-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="c0a73-132">**Dispositivos:** elige si se notifica a los destinatarios alertas en todos los dispositivos (solo rol de administrador global) o en grupos de dispositivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c0a73-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="c0a73-133">Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="c0a73-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="c0a73-134">**Gravedad de alerta:** elija el nivel de gravedad de la alerta.</span><span class="sxs-lookup"><span data-stu-id="c0a73-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="c0a73-135">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="c0a73-136">Escriba la dirección de correo electrónico del destinatario y, a continuación, haga clic **en Agregar destinatario.**</span><span class="sxs-lookup"><span data-stu-id="c0a73-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="c0a73-137">Puede agregar varias direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0a73-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="c0a73-138">Compruebe que los destinatarios de correo electrónico pueden recibir las notificaciones de correo electrónico **seleccionando Enviar correo electrónico de prueba**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="c0a73-139">Haga clic **en Guardar regla de notificación**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="c0a73-140">Editar una regla de notificación</span><span class="sxs-lookup"><span data-stu-id="c0a73-140">Edit a notification rule</span></span>
1. <span data-ttu-id="c0a73-141">Seleccione la regla de notificación que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c0a73-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="c0a73-142">Actualice la información de las pestañas General y Destinatario.</span><span class="sxs-lookup"><span data-stu-id="c0a73-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="c0a73-143">Haga clic **en Guardar regla de notificación**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="c0a73-144">Eliminar regla de notificación</span><span class="sxs-lookup"><span data-stu-id="c0a73-144">Delete notification rule</span></span>

1. <span data-ttu-id="c0a73-145">Seleccione la regla de notificación que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="c0a73-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="c0a73-146">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c0a73-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="c0a73-147">Solucionar problemas de notificaciones de correo electrónico para alertas</span><span class="sxs-lookup"><span data-stu-id="c0a73-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="c0a73-148">En esta sección se enumeran varios problemas que puede encontrar al usar notificaciones por correo electrónico para alertas.</span><span class="sxs-lookup"><span data-stu-id="c0a73-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="c0a73-149">**Problema:** Los destinatarios previstos informan de que no reciben las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c0a73-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="c0a73-150">**Solución:** Asegúrese de que los filtros de correo electrónico no bloqueen las notificaciones:</span><span class="sxs-lookup"><span data-stu-id="c0a73-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="c0a73-151">Compruebe que las notificaciones de correo electrónico de Defender for Endpoint no se envíen a la carpeta Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c0a73-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="c0a73-152">Marcalos como No deseado.</span><span class="sxs-lookup"><span data-stu-id="c0a73-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="c0a73-153">Compruebe que el producto de seguridad de correo electrónico no está bloqueando las notificaciones de correo electrónico de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c0a73-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="c0a73-154">Comprueba las reglas de la aplicación de correo electrónico que podrían estar capturando y moviendo las notificaciones de correo electrónico de Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="c0a73-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0a73-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c0a73-155">Related topics</span></span>
- [<span data-ttu-id="c0a73-156">Actualizar la configuración de retención de datos</span><span class="sxs-lookup"><span data-stu-id="c0a73-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="c0a73-157">Configurar funciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="c0a73-157">Configure advanced features</span></span>](advanced-features.md)
