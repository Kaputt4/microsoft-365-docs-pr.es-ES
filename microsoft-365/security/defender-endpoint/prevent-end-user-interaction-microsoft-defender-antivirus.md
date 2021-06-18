---
title: Ocultar la Antivirus de Microsoft Defender interfaz
description: Puedes ocultar el icono de protección contra virus y amenazas en la Seguridad de Windows aplicación.
keywords: bloqueo de ui, modo sin cabeza, ocultar aplicación, ocultar configuración, ocultar interfaz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007676"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="917a5-104">Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario</span><span class="sxs-lookup"><span data-stu-id="917a5-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="917a5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="917a5-105">**Applies to:**</span></span>

- [<span data-ttu-id="917a5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="917a5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="917a5-107">Puede usar la directiva de grupo para impedir que los usuarios de los puntos de conexión vean la interfaz Antivirus de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="917a5-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="917a5-108">También puede evitar que pauten los exámenes.</span><span class="sxs-lookup"><span data-stu-id="917a5-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="917a5-109">Ocultar la Antivirus de Microsoft Defender interfaz</span><span class="sxs-lookup"><span data-stu-id="917a5-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="917a5-110">En Windows 10, versión 1703, ocultar la interfaz ocultará las notificaciones de Antivirus de Microsoft Defender e impedirá que el icono protección contra amenazas de Virus & aparezca en la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="917a5-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="917a5-111">Con la configuración establecida en **Enabled**:</span><span class="sxs-lookup"><span data-stu-id="917a5-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Seguridad de Windows sin el icono de escudo y la sección protección contra virus y amenazas":::

<span data-ttu-id="917a5-113">Con la configuración establecida en **Deshabilitado** o no configurada:</span><span class="sxs-lookup"><span data-stu-id="917a5-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Captura de pantalla Seguridad de Windows con el icono de escudo y las secciones de protección contra amenazas":::

>[!NOTE]
><span data-ttu-id="917a5-115">Ocultar la interfaz también impedirá que Antivirus de Microsoft Defender notificaciones en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="917a5-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="917a5-116">Las notificaciones de Microsoft Defender para puntos de conexión seguirán apareciendo.</span><span class="sxs-lookup"><span data-stu-id="917a5-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="917a5-117">También puede configurar [individualmente las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="917a5-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="917a5-118">En versiones anteriores de Windows 10, la configuración ocultará la interfaz Windows Defender cliente.</span><span class="sxs-lookup"><span data-stu-id="917a5-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="917a5-119">Si el usuario intenta abrirlo, recibirá una advertencia que indica: "El administrador del sistema ha restringido el acceso a esta aplicación".</span><span class="sxs-lookup"><span data-stu-id="917a5-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Mensaje de advertencia cuando el modo sin cabeza está habilitado Windows 10 versiones anteriores a 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="917a5-121">Usar la directiva de grupo para ocultar la interfaz av de Microsoft Defender a los usuarios</span><span class="sxs-lookup"><span data-stu-id="917a5-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="917a5-122">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="917a5-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="917a5-123">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="917a5-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="917a5-124">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="917a5-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="917a5-125">Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > interfaz de cliente**.</span><span class="sxs-lookup"><span data-stu-id="917a5-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="917a5-126">Haz doble clic en **la opción Habilitar modo de interfaz de** usuario sin cabeza y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="917a5-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="917a5-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="917a5-127">Click **OK**.</span></span> 

<span data-ttu-id="917a5-128">Consulta [Impedir que los usuarios modifiquen localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) la configuración de directiva para obtener más opciones sobre cómo impedir que los usuarios forme parte de la protección de sus equipos.</span><span class="sxs-lookup"><span data-stu-id="917a5-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="917a5-129">Impedir que los usuarios pauten un examen</span><span class="sxs-lookup"><span data-stu-id="917a5-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="917a5-130">Puede impedir que los usuarios pauten los exámenes, lo que puede ser útil para garantizar que los usuarios no interrumpan los exámenes programados o a petición.</span><span class="sxs-lookup"><span data-stu-id="917a5-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="917a5-131">Esta configuración no se admite en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="917a5-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="917a5-132">Usar la directiva de grupo para evitar que los usuarios pauten un examen</span><span class="sxs-lookup"><span data-stu-id="917a5-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="917a5-133">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="917a5-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="917a5-134">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="917a5-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="917a5-135">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="917a5-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="917a5-136">Expanda el árbol para Windows **componentes**  >  **Antivirus de Microsoft Defender**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="917a5-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="917a5-137">Haga doble clic en **la opción Permitir a los usuarios pausar el** examen y establezca la opción en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="917a5-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="917a5-138">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="917a5-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="917a5-139">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="917a5-139">Related articles</span></span>

- [<span data-ttu-id="917a5-140">Configurar las notificaciones que aparecen en los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="917a5-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="917a5-141">Configurar la interacción del usuario final con Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="917a5-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="917a5-142">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="917a5-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)