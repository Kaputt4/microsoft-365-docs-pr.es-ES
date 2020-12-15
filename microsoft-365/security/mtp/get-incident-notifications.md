---
title: Obtener notificaciones de incidentes en Microsoft 365 defender
description: Aprenda a crear reglas para obtener notificaciones de correo electrónico para incidentes en Microsoft 365 defender
keywords: incidente, correo electrónico, correo electrónico notfications, configuración, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668362"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="6ed09-104">Obtener notificaciones de incidentes por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6ed09-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="6ed09-105">La característica de notificaciones de correo electrónico para incidentes se encuentra actualmente en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="6ed09-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="6ed09-106">Parte de la información sobre esta característica puede cambiar antes de la disponibilidad comercial.</span><span class="sxs-lookup"><span data-stu-id="6ed09-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="6ed09-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6ed09-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6ed09-108">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6ed09-108">**Applies to:**</span></span>
- <span data-ttu-id="6ed09-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ed09-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="6ed09-110">Puede configurar Microsoft 365 defender para que le envíe una notificación por correo electrónico cada vez que haya nuevos incidentes o actualizaciones nuevas a los incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="6ed09-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="6ed09-111">Puede elegir obtener notificaciones en función de la gravedad del incidente o del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6ed09-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="6ed09-112">También puede optar por obtener una notificación solo en la primera actualización por incidente.</span><span class="sxs-lookup"><span data-stu-id="6ed09-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="6ed09-113">Puede Agregar o quitar destinatarios en las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="6ed09-114">Los destinatarios recién agregados reciben una notificación sobre los incidentes después de que se hayan agregado.</span><span class="sxs-lookup"><span data-stu-id="6ed09-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="6ed09-115">La notificación de correo electrónico contiene detalles importantes sobre el incidente como el nombre del incidente, la gravedad y las categorías, entre otros.</span><span class="sxs-lookup"><span data-stu-id="6ed09-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="6ed09-116">También puede ir directamente a incidentes para que pueda iniciar la investigación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6ed09-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="6ed09-117">Para obtener más información sobre la investigación de incidentes, consulte [investigar incidentes en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="6ed09-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="6ed09-118">Necesita los permisos de administración de la configuración de seguridad para configurar las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="6ed09-119">Si ha elegido usar la administración básica de permisos, los usuarios con roles de administrador de seguridad o de administrador global pueden configurar las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="6ed09-120">Del mismo modo, si su organización usa el control de acceso basado en roles (RBAC), solo puede crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que se le permita administrar.</span><span class="sxs-lookup"><span data-stu-id="6ed09-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="6ed09-121">Crear reglas para notificaciones de incidentes</span><span class="sxs-lookup"><span data-stu-id="6ed09-121">Create rules for incident notifications</span></span>

<span data-ttu-id="6ed09-122">Para configurar su primera notificación de incidentes, cree una nueva regla y personalice la configuración de las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="6ed09-123">En el panel de navegación, seleccione  >  **notificaciones por correo electrónico de incidente** de configuración.</span><span class="sxs-lookup"><span data-stu-id="6ed09-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="6ed09-124">Seleccione **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="6ed09-124">Select **Add item**.</span></span>
3. <span data-ttu-id="6ed09-125">Asigne un nombre a la regla en **nombre** y proporcione una **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="6ed09-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Ventana crear regla para notifs de correo electrónico de incidentes](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="6ed09-127">Seleccione **siguiente** para ir a **configuración de notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="6ed09-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="6ed09-128">Aquí puede especificar:</span><span class="sxs-lookup"><span data-stu-id="6ed09-128">Here you can specify:</span></span>
    - <span data-ttu-id="6ed09-129">**Gravedad de alerta** : elija la gravedad de la alerta que desencadenará una notificación de incidente.</span><span class="sxs-lookup"><span data-stu-id="6ed09-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="6ed09-130">Por ejemplo, si solo desea recibir información sobre los incidentes de gravedad alta, seleccione alta.</span><span class="sxs-lookup"><span data-stu-id="6ed09-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="6ed09-131">**Ámbito de grupo de dispositivos** : este cuadro desplegable muestra todos los grupos de dispositivos a los que el usuario puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="6ed09-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="6ed09-132">Seleccione los grupos de dispositivos para los que va a crear las reglas de notificación de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6ed09-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="6ed09-133">**Notificar solo en la primera aparición por incidente** : al seleccionar esta opción, se enviará una notificación por correo electrónico sólo en la primera alerta que coincida con las otras selecciones.</span><span class="sxs-lookup"><span data-stu-id="6ed09-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="6ed09-134">Las actualizaciones o alertas posteriores relacionadas con el incidente no desencadenarán una notificación.</span><span class="sxs-lookup"><span data-stu-id="6ed09-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="6ed09-135">**Incluir nombre** de la organización: indica si el nombre del cliente aparece en la notificación por correo electrónico o no.</span><span class="sxs-lookup"><span data-stu-id="6ed09-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="6ed09-136">**Incluir vínculo de portal específico del inquilino** : agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Ventana Configuración de la Notif para el correo electrónico de incidentes notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="6ed09-138">Seleccione **siguiente** para ir a la sección **destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="6ed09-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="6ed09-139">Aquí puede especificar las direcciones de correo electrónico que recibirán las notificaciones por correo electrónico de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6ed09-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="6ed09-140">Seleccione **Agregar un destinatario después de** escribir cada dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ed09-140">Select **Add a recipient** after typing every email address.</span></span>

    ![Ventana agregar destinatarios para el correo electrónico de incidentes notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="6ed09-142">Por último, seleccione **siguiente** para ir a **revisar regla** para que pueda ver toda la configuración asociada a la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="6ed09-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="6ed09-143">Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6ed09-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ed09-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ed09-144">See also</span></span>
- [<span data-ttu-id="6ed09-145">Información general sobre los incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="6ed09-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="6ed09-146">Priorizar incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="6ed09-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="6ed09-147">Investigar incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="6ed09-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

