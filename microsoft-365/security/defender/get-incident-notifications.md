---
title: Obtener notificaciones de incidentes por correo electrónico en Microsoft 365 Defender
description: Obtenga información sobre cómo crear reglas para obtener notificaciones por correo electrónico para incidentes en Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2e47b35646a1cd6e1075d80f9ed0550e8e1e819f
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651397"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="c77d6-104">Obtener notificaciones de incidentes por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c77d6-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c77d6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c77d6-105">**Applies to:**</span></span>
- <span data-ttu-id="c77d6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c77d6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c77d6-107">Puedes configurar Microsoft 365 Defender para notificar a tu personal con un correo electrónico sobre nuevos incidentes o actualizaciones de incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="c77d6-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="c77d6-108">Puede elegir obtener notificaciones en función de:</span><span class="sxs-lookup"><span data-stu-id="c77d6-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="c77d6-109">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="c77d6-109">Incident severity.</span></span>
- <span data-ttu-id="c77d6-110">Grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c77d6-110">Device group.</span></span>
- <span data-ttu-id="c77d6-111">Solo en la primera actualización por incidente.</span><span class="sxs-lookup"><span data-stu-id="c77d6-111">Only on the first update per incident.</span></span>

<span data-ttu-id="c77d6-112">La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otras.</span><span class="sxs-lookup"><span data-stu-id="c77d6-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="c77d6-113">También puede ir directamente al incidente e iniciar el análisis de inmediato.</span><span class="sxs-lookup"><span data-stu-id="c77d6-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="c77d6-114">Para obtener más información, vea [Investigar incidentes](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="c77d6-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="c77d6-115">Puede agregar o quitar destinatarios en las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="c77d6-116">Los nuevos destinatarios reciben notificaciones sobre incidentes después de agregarse.</span><span class="sxs-lookup"><span data-stu-id="c77d6-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="c77d6-117">Necesita el permiso "Administrar la configuración de seguridad" para configurar las opciones de notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="c77d6-118">Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico por usted.</span><span class="sxs-lookup"><span data-stu-id="c77d6-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="c77d6-119">Del mismo modo, si tu organización usa el control de acceso basado en roles (RBAC), solo puedes crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que puedas administrar.</span><span class="sxs-lookup"><span data-stu-id="c77d6-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="c77d6-120">Crear una regla para notificaciones por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c77d6-120">Create a rule for email notifications</span></span>

<span data-ttu-id="c77d6-121">Siga estos pasos para crear una nueva regla y personalizar la configuración de notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="c77d6-122">En el panel de navegación, **seleccione Configuración > Microsoft 365 Defender > notificaciones de correo** electrónico de incidentes .</span><span class="sxs-lookup"><span data-stu-id="c77d6-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="c77d6-123">Seleccione **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-123">Select **Add item**.</span></span>
3. <span data-ttu-id="c77d6-124">En la **página Conceptos básicos,** escriba el nombre de la regla y una descripción y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="c77d6-125">En la **página Configuración de** notificaciones, configure:</span><span class="sxs-lookup"><span data-stu-id="c77d6-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="c77d6-126">**Gravedad de alerta:** elija las gravedades de alerta que desencadenarán una notificación de incidente.</span><span class="sxs-lookup"><span data-stu-id="c77d6-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="c77d6-127">Por ejemplo, si solo desea que se le informe sobre incidentes de alta gravedad, seleccione **Alto**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="c77d6-128">**Ámbito de grupo de dispositivos:** puede especificar todos los grupos de dispositivos o seleccionar en la lista de grupos de dispositivos del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c77d6-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="c77d6-129">**Notificar solo en la primera aparición por** incidente: seleccione si desea una notificación solo en la primera alerta que coincida con las demás selecciones.</span><span class="sxs-lookup"><span data-stu-id="c77d6-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="c77d6-130">Las actualizaciones posteriores o las alertas relacionadas con el incidente no enviarán notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="c77d6-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="c77d6-131">**Incluir el nombre de la organización en el correo** electrónico: seleccione si desea que el nombre de la organización aparezca en la notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="c77d6-132">**Incluir vínculo de portal específico** del inquilino: seleccione si desea agregar un vínculo con el identificador de inquilino en la notificación de correo electrónico para obtener acceso a un inquilino Microsoft 365 inquilino específico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Configuración de notificaciones para notificaciones de correo electrónico de incidentes":::

5. <span data-ttu-id="c77d6-134">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-134">Select **Next**.</span></span> <span data-ttu-id="c77d6-135">En la **página Destinatarios,** agregue las direcciones de correo electrónico que recibirán las notificaciones de incidentes.</span><span class="sxs-lookup"><span data-stu-id="c77d6-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="c77d6-136">Seleccione **Agregar después** de escribir cada nueva dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c77d6-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="c77d6-137">Para probar las notificaciones y asegurarse de que los destinatarios las reciben en las bandejas de entrada, seleccione **Enviar correo electrónico de prueba.**</span><span class="sxs-lookup"><span data-stu-id="c77d6-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="c77d6-138">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-138">Select **Next**.</span></span> <span data-ttu-id="c77d6-139">En la **página Revisar regla,** revise la configuración de la regla y, a continuación, **seleccione Crear regla**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="c77d6-140">Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c77d6-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="c77d6-141">Para editar una regla existente, selecciónelo en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="c77d6-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="c77d6-142">En el panel con el nombre de regla, seleccione **Editar** regla y realice los cambios en las páginas **Conceptos** básicos, Configuración de **notificación** y **Destinatarios.**</span><span class="sxs-lookup"><span data-stu-id="c77d6-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="c77d6-143">Para eliminar una regla, selecciónelo en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="c77d6-143">To delete a rule, select it from the list of rules.</span></span> <span data-ttu-id="c77d6-144">En el panel con el nombre de regla, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c77d6-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c77d6-145">See also</span></span>
- [<span data-ttu-id="c77d6-146">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="c77d6-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c77d6-147">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="c77d6-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="c77d6-148">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="c77d6-148">Investigate incidents</span></span>](investigate-incidents.md)
