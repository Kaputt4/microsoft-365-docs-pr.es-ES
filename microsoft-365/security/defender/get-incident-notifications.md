---
title: Obtener notificaciones de incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo crear reglas para obtener notificaciones por correo electrónico para incidentes en Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents
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
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501070"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="2e788-104">Obtener notificaciones de incidentes por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2e788-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2e788-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2e788-105">**Applies to:**</span></span>
- <span data-ttu-id="2e788-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e788-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2e788-107">Puedes configurar Microsoft 365 Defender para que te notifique por correo electrónico cada vez que haya nuevos incidentes o nuevas actualizaciones de incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="2e788-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="2e788-108">Puedes elegir obtener notificaciones según la gravedad del incidente o por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2e788-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="2e788-109">También puedes elegir obtener una notificación solo en la primera actualización por incidente.</span><span class="sxs-lookup"><span data-stu-id="2e788-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="2e788-110">Puede agregar o quitar destinatarios en las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e788-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="2e788-111">Los destinatarios recién agregados reciben una notificación sobre incidentes después de agregarse.</span><span class="sxs-lookup"><span data-stu-id="2e788-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="2e788-112">La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otras.</span><span class="sxs-lookup"><span data-stu-id="2e788-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="2e788-113">También puede ir directamente a incidentes para que pueda iniciar la investigación de inmediato.</span><span class="sxs-lookup"><span data-stu-id="2e788-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="2e788-114">Para obtener más información sobre cómo investigar incidentes, vea [Investigar incidentes en Microsoft 365 Defender](./investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="2e788-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="2e788-115">Necesita permisos de "Administrar la configuración de seguridad" para configurar la configuración de notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e788-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="2e788-116">Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico por usted.</span><span class="sxs-lookup"><span data-stu-id="2e788-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="2e788-117">Del mismo modo, si tu organización usa el control de acceso basado en roles (RBAC), solo puedes crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que puedas administrar.</span><span class="sxs-lookup"><span data-stu-id="2e788-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="2e788-118">Crear reglas para notificaciones de incidentes</span><span class="sxs-lookup"><span data-stu-id="2e788-118">Create rules for incident notifications</span></span>

<span data-ttu-id="2e788-119">Para configurar la primera notificación por correo electrónico para incidentes, cree una nueva regla y personalice la configuración de notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e788-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="2e788-120">En el panel de navegación, seleccione **Configuración**  >  **Notificaciones de correo electrónico incidentes**.</span><span class="sxs-lookup"><span data-stu-id="2e788-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="2e788-121">Seleccione **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="2e788-121">Select **Add item**.</span></span>
3. <span data-ttu-id="2e788-122">Asigne a la regla un nombre **en Name** y proporcione una **descripción**.</span><span class="sxs-lookup"><span data-stu-id="2e788-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Crear ventana de regla para notificaciones de correo electrónico de incidentes](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="2e788-124">Seleccione **Siguiente** para ir a **Configuración de notificación**.</span><span class="sxs-lookup"><span data-stu-id="2e788-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="2e788-125">Aquí puede especificar:</span><span class="sxs-lookup"><span data-stu-id="2e788-125">Here you can specify:</span></span>
    - <span data-ttu-id="2e788-126">**Gravedad de alerta:** elija la gravedad de la alerta que desencadenará una notificación de incidente.</span><span class="sxs-lookup"><span data-stu-id="2e788-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="2e788-127">Por ejemplo, si solo desea que se le informe sobre incidentes de alta gravedad, seleccione Alto.</span><span class="sxs-lookup"><span data-stu-id="2e788-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="2e788-128">**Ámbito de grupo de dispositivos:** este desplegable muestra todos los grupos de dispositivos a los que el usuario puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="2e788-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="2e788-129">Selecciona los grupos de dispositivos para los que estás creando las reglas de notificación de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2e788-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="2e788-130">**Notificar solo en la primera** aparición por incidente: si selecciona esta opción, solo se enviará una notificación por correo electrónico en la primera alerta que coincida con las demás selecciones.</span><span class="sxs-lookup"><span data-stu-id="2e788-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="2e788-131">Las actualizaciones posteriores o las alertas relacionadas con el incidente no desencadenarán una notificación.</span><span class="sxs-lookup"><span data-stu-id="2e788-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="2e788-132">**Incluir nombre de organización:** indica si el nombre del cliente aparece en la notificación por correo electrónico o no.</span><span class="sxs-lookup"><span data-stu-id="2e788-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="2e788-133">**Incluir vínculo de portal específico del inquilino:** agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.</span><span class="sxs-lookup"><span data-stu-id="2e788-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="2e788-135">Seleccione **Siguiente** para ir a **la sección** Destinatarios.</span><span class="sxs-lookup"><span data-stu-id="2e788-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="2e788-136">Aquí puede especificar direcciones de correo electrónico que recibirán las notificaciones de correo electrónico de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2e788-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="2e788-137">Seleccione **Agregar un destinatario después** de escribir cada dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e788-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Ventana Agregar destinatarios para notificaciones de correo electrónico de incidentes](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="2e788-139">Por último, seleccione **Siguiente** para ir **a Revisar regla** para que pueda ver toda la configuración asociada a la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="2e788-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="2e788-140">Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2e788-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e788-141">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2e788-141">See also</span></span>
- [<span data-ttu-id="2e788-142">Información general sobre incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e788-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="2e788-143">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e788-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="2e788-144">Investigar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e788-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
