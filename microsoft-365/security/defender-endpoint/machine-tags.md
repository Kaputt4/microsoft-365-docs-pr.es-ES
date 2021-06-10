---
title: Crear y administrar etiquetas de dispositivos
description: Usar etiquetas de dispositivo para agrupar dispositivos para capturar contexto y habilitar la creación de listas dinámicas como parte de un incidente
keywords: etiquetas, etiquetas de dispositivo, grupos de dispositivos, grupos, corrección, nivel, reglas, grupo de aad, rol, asignación, clasificación
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
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187594"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="1586b-104">Crear y administrar etiquetas de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1586b-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1586b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1586b-105">**Applies to:**</span></span>
- [<span data-ttu-id="1586b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1586b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1586b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1586b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1586b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1586b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1586b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1586b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1586b-110">Agregue etiquetas en los dispositivos para crear una afiliación de grupos lógica.</span><span class="sxs-lookup"><span data-stu-id="1586b-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="1586b-111">Las etiquetas de dispositivo son compatibles con la asignación adecuada de la red, lo que permite adjuntar diferentes etiquetas para capturar contexto y habilitar la creación de listas dinámicas como parte de un incidente.</span><span class="sxs-lookup"><span data-stu-id="1586b-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="1586b-112">Las etiquetas se pueden usar como filtro en la **vista de lista** Dispositivos o para agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1586b-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="1586b-113">Para obtener más información sobre la agrupación de dispositivos, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1586b-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="1586b-114">Puedes agregar etiquetas en dispositivos de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="1586b-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="1586b-115">Usando el portal</span><span class="sxs-lookup"><span data-stu-id="1586b-115">Using the portal</span></span>
- <span data-ttu-id="1586b-116">Estableciendo un valor de clave de registro</span><span class="sxs-lookup"><span data-stu-id="1586b-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="1586b-117">Puede haber cierta latencia entre el momento en que se agrega una etiqueta a un dispositivo y su disponibilidad en la lista de dispositivos y la página del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1586b-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="1586b-118">Para agregar etiquetas de dispositivo con la API, consulte [API para agregar o quitar etiquetas de dispositivo](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="1586b-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="1586b-119">Agregar y administrar etiquetas de dispositivo con el portal</span><span class="sxs-lookup"><span data-stu-id="1586b-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="1586b-120">Seleccione el dispositivo en el que quiere administrar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="1586b-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="1586b-121">Puede seleccionar o buscar un dispositivo desde cualquiera de las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="1586b-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="1586b-122">**Panel de operaciones de seguridad:** seleccione el nombre del dispositivo en la sección Dispositivos principales con alertas activas.</span><span class="sxs-lookup"><span data-stu-id="1586b-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="1586b-123">**Cola de alertas**: seleccione el nombre del dispositivo junto al icono de dispositivo en la cola de alertas.</span><span class="sxs-lookup"><span data-stu-id="1586b-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="1586b-124">**Lista de dispositivos**: seleccione el nombre del dispositivo de la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1586b-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="1586b-125">**Cuadro de búsqueda**: seleccione Dispositivo en el menú desplegable y escriba el nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1586b-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="1586b-126">También puede acceder a la página de la alerta a través del archivo y las vistas IP.</span><span class="sxs-lookup"><span data-stu-id="1586b-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="1586b-127">Seleccione **Administrar etiquetas** en la fila Acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1586b-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Imagen del botón administrar etiquetas](images/manage-tags.png)

3. <span data-ttu-id="1586b-129">Tipo para buscar o crear etiquetas</span><span class="sxs-lookup"><span data-stu-id="1586b-129">Type to find or create tags</span></span>

    ![Imagen de agregar etiquetas en un dispositivo1](images/new-tags.png)

<span data-ttu-id="1586b-131">Las etiquetas se agregan a la vista de dispositivo y también se reflejarán en la **vista de lista Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="1586b-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="1586b-132">A continuación, puede usar el **filtro Etiquetas** para ver la lista relevante de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1586b-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="1586b-133">Es posible que el filtrado no funcione en nombres de etiquetas que contengan paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1586b-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="1586b-134">Al crear una etiqueta nueva, se muestra una lista de etiquetas existentes.</span><span class="sxs-lookup"><span data-stu-id="1586b-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="1586b-135">La lista solo muestra las etiquetas creadas a través del portal.</span><span class="sxs-lookup"><span data-stu-id="1586b-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="1586b-136">Las etiquetas existentes creadas a partir de dispositivos cliente no se mostrarán.</span><span class="sxs-lookup"><span data-stu-id="1586b-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="1586b-137">También puede eliminar etiquetas de esta vista.</span><span class="sxs-lookup"><span data-stu-id="1586b-137">You can also delete tags from this view.</span></span>

![Imagen de agregar etiquetas en un dispositivo2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="1586b-139">Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro</span><span class="sxs-lookup"><span data-stu-id="1586b-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="1586b-140">Solo se aplica a los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="1586b-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="1586b-141">Windows 10, versión 1709 o posterior</span><span class="sxs-lookup"><span data-stu-id="1586b-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="1586b-142">Windows Servidor, versión 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="1586b-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="1586b-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1586b-143">Windows Server 2016</span></span>
>- <span data-ttu-id="1586b-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1586b-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="1586b-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="1586b-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="1586b-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1586b-146">Windows 8.1</span></span>
>- <span data-ttu-id="1586b-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1586b-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="1586b-148">El número máximo de caracteres que se pueden establecer en una etiqueta es 200.</span><span class="sxs-lookup"><span data-stu-id="1586b-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="1586b-149">Los dispositivos con etiquetas similares pueden ser útiles cuando necesitas aplicar una acción contextual en una lista específica de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1586b-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="1586b-150">Use la siguiente entrada de clave del Registro para agregar una etiqueta a un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="1586b-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="1586b-151">Clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="1586b-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="1586b-152">Valor de clave del Registro (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="1586b-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="1586b-153">Datos de clave del Registro: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="1586b-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="1586b-154">La etiqueta de dispositivo forma parte del informe de información del dispositivo que se genera una vez al día.</span><span class="sxs-lookup"><span data-stu-id="1586b-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="1586b-155">Como alternativa, puede optar por reiniciar el punto de conexión que transferiría un nuevo informe de información del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1586b-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="1586b-156">Si necesita quitar una etiqueta que se agregó con la clave del Registro anterior, desactive el contenido de los datos de la clave del Registro en lugar de quitar la clave "Grupo".</span><span class="sxs-lookup"><span data-stu-id="1586b-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
