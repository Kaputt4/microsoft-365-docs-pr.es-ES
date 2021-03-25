---
title: Control de dispositivos para macOS
description: Aprende a configurar Microsoft Defender para Endpoint para Mac para reducir las amenazas del almacenamiento extraíble, como dispositivos USB.
keywords: microsoft, defender, atp, mac, device, control, usb, removable, media
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 098eb30764870e69c5b1b6c2cec3cf8e5cb11691
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186574"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="e5cfa-104">Control de dispositivos para macOS</span><span class="sxs-lookup"><span data-stu-id="e5cfa-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5cfa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5cfa-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e5cfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5cfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5cfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e5cfa-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e5cfa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5cfa-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="e5cfa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-110">Requirements</span></span>

<span data-ttu-id="e5cfa-111">El control de dispositivos para macOS tiene los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="e5cfa-112">Derechos de Microsoft Defender para extremo (puede ser de prueba)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="e5cfa-113">Versión mínima del sistema operativo: macOS 10.15.4 o posterior</span><span class="sxs-lookup"><span data-stu-id="e5cfa-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="e5cfa-114">Versión mínima del producto: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="e5cfa-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="e5cfa-115">El dispositivo debe ejecutarse con extensiones del sistema (este es el valor predeterminado en macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="e5cfa-116">Para comprobar si el dispositivo se está ejecutando en extensiones del sistema, ejecute el siguiente comando y compruebe que se está imprimiendo `endpoint_security_extension` en la consola:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="e5cfa-117">El dispositivo debe estar en `Beta` el canal de actualización de Microsoft AutoUpdate (anteriormente denominado `InsiderFast` ) .</span><span class="sxs-lookup"><span data-stu-id="e5cfa-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="e5cfa-118">Para obtener más información, vea [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="e5cfa-119">Puede comprobar el canal de actualización con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="e5cfa-120">Si el comando anterior no imprime ni `Beta` , ejecute el siguiente comando desde `InsiderFast` terminal.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="e5cfa-121">La actualización de canal surte efecto la próxima vez que se inicie el producto (cuando se instale la siguiente actualización del producto o cuando se reinicie el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="e5cfa-122">Como alternativa, si se encuentra en un entorno administrado (JAMF o Intune), puede configurar el canal de actualización de forma remota.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="e5cfa-123">Para obtener más información, vea [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="e5cfa-124">Directiva de control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-124">Device control policy</span></span>

<span data-ttu-id="e5cfa-125">Para configurar el control de dispositivos para macOS, debes crear una directiva que describa las restricciones que quieres establecer en tu organización.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="e5cfa-126">La directiva de control de dispositivos se incluye en el perfil de configuración que se usa para configurar el resto de opciones de producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="e5cfa-127">Para obtener más información, vea [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="e5cfa-128">Dentro del perfil de configuración, la directiva de control de dispositivos se define en la siguiente sección:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-129">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-129">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-130">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-130">**Key**</span></span> | <span data-ttu-id="e5cfa-131">deviceControl</span><span class="sxs-lookup"><span data-stu-id="e5cfa-131">deviceControl</span></span> |
| <span data-ttu-id="e5cfa-132">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-132">**Data type**</span></span> | <span data-ttu-id="e5cfa-133">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-133">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e5cfa-134">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-134">**Comments**</span></span> | <span data-ttu-id="e5cfa-135">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-135">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="e5cfa-136">La directiva de control de dispositivos se puede usar para:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-136">The device control policy can be used to:</span></span>

- [<span data-ttu-id="e5cfa-137">Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-137">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="e5cfa-138">Permitir o bloquear dispositivos extraíbles</span><span class="sxs-lookup"><span data-stu-id="e5cfa-138">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="e5cfa-139">Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-139">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="e5cfa-140">Cuando se aplica la directiva de control de dispositivos que has puesto en marcha en un dispositivo (por ejemplo, el acceso a un dispositivo multimedia extraíble está restringido), se muestra una notificación al usuario.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-140">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Notificación de control de dispositivos](images/mac-device-control-notification.png)

<span data-ttu-id="e5cfa-142">Cuando los usuarios finales hacen clic en esta notificación, se abre una página web en el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-142">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="e5cfa-143">Puede configurar la dirección URL que se abre cuando los usuarios finales hacen clic en la notificación.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-143">You can configure the URL that is opened when end users click the notification.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-144">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-144">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-145">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-145">**Key**</span></span> | <span data-ttu-id="e5cfa-146">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="e5cfa-146">navigationTarget</span></span> |
| <span data-ttu-id="e5cfa-147">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-147">**Data type**</span></span> | <span data-ttu-id="e5cfa-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="e5cfa-148">String</span></span> |
| <span data-ttu-id="e5cfa-149">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-149">**Comments**</span></span> | <span data-ttu-id="e5cfa-150">Si no se define, el producto usa una dirección URL predeterminada que apunta a una página genérica que explica la acción realizada por el producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-150">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="e5cfa-151">Permitir o bloquear dispositivos extraíbles</span><span class="sxs-lookup"><span data-stu-id="e5cfa-151">Allow or block removable devices</span></span>

<span data-ttu-id="e5cfa-152">La sección de medios extraíbles de la directiva de control de dispositivos se usa para restringir el acceso a medios extraíbles.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-152">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5cfa-153">Actualmente se admiten los siguientes tipos de medios extraíbles y se pueden incluir en la directiva: dispositivos de almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-153">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-154">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-154">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-155">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-155">**Key**</span></span> | <span data-ttu-id="e5cfa-156">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="e5cfa-156">removableMediaPolicy</span></span> |
| <span data-ttu-id="e5cfa-157">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-157">**Data type**</span></span> | <span data-ttu-id="e5cfa-158">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-158">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e5cfa-159">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-159">**Comments**</span></span> | <span data-ttu-id="e5cfa-160">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-160">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="e5cfa-161">Esta sección de la directiva es jerárquica, lo que permite la máxima flexibilidad y cubre una amplia variedad de casos de uso.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-161">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="e5cfa-162">En el nivel superior se encuentran los proveedores, identificados por un identificador de proveedor.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-162">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="e5cfa-163">Para cada proveedor, hay productos identificados por un identificador de producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-163">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="e5cfa-164">Por último, para cada producto hay números de serie que indican dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-164">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="e5cfa-165">Para obtener información sobre cómo encontrar los identificadores de dispositivo, consulta [Buscar identificadores de dispositivo.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-165">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="e5cfa-166">La directiva se evalúa desde la entrada más específica hasta la más general.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-166">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="e5cfa-167">Es decir, cuando un dispositivo está conectado, el producto intenta encontrar la coincidencia más específica en la directiva para cada dispositivo multimedia extraíble y aplicar los permisos en ese nivel.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-167">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="e5cfa-168">Si no hay coincidencia, se aplica la siguiente mejor coincidencia, hasta el permiso especificado en el nivel superior, que es el valor predeterminado cuando un dispositivo no coincide con ninguna otra entrada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-168">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="e5cfa-169">Nivel de aplicación de directivas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-169">Policy enforcement level</span></span>

<span data-ttu-id="e5cfa-170">En la sección medios extraíbles, hay una opción para establecer el nivel de cumplimiento, que puede tener uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-170">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="e5cfa-171">`audit` - En este nivel de aplicación, si el acceso a un dispositivo está restringido, se muestra una notificación al usuario, pero aún se puede usar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-171">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="e5cfa-172">Este nivel de cumplimiento puede ser útil para evaluar la eficacia de una directiva.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-172">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="e5cfa-173">`block` - En este nivel de cumplimiento, las operaciones que el usuario puede realizar en el dispositivo se limitan a lo que se define en la directiva.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-173">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="e5cfa-174">Además, se genera una notificación al usuario.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-174">Furthermore, a notification is raised to the user.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="e5cfa-175">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-176">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-176">**Key**</span></span> | <span data-ttu-id="e5cfa-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="e5cfa-177">enforcementLevel</span></span> |
| <span data-ttu-id="e5cfa-178">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-178">**Data type**</span></span> | <span data-ttu-id="e5cfa-179">Cadena</span><span class="sxs-lookup"><span data-stu-id="e5cfa-179">String</span></span> |
| <span data-ttu-id="e5cfa-180">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-180">**Possible values**</span></span> | <span data-ttu-id="e5cfa-181">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-181">audit (default)</span></span> <br/> <span data-ttu-id="e5cfa-182">bloque</span><span class="sxs-lookup"><span data-stu-id="e5cfa-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="e5cfa-183">Nivel de permisos predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5cfa-183">Default permission level</span></span>

<span data-ttu-id="e5cfa-184">En el nivel superior de la sección de medios extraíbles, puede configurar el nivel de permisos predeterminado para dispositivos que no coincidan con nada más en la directiva.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="e5cfa-185">Esta configuración se puede establecer en:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-185">This setting can be set to:</span></span>

- <span data-ttu-id="e5cfa-186">`none` - No se pueden realizar operaciones en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5cfa-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="e5cfa-187">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-187">A combination of the following values:</span></span>
    - <span data-ttu-id="e5cfa-188">`read` - Las operaciones de lectura están permitidas en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5cfa-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="e5cfa-189">`write` - Las operaciones de escritura están permitidas en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5cfa-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="e5cfa-190">`execute` - Las operaciones de ejecución están permitidas en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5cfa-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="e5cfa-191">Si `none` está presente en el nivel de permisos, cualquier otro permiso ( , , o ) se `read` `write` `execute` omitirá.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="e5cfa-192">El `execute` permiso solo hace referencia a la ejecución de archivos binarios de Mach-O.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="e5cfa-193">No incluye la ejecución de scripts u otros tipos de cargas.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-193">It does not include execution of scripts or other types of payloads.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-194">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-195">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-195">**Key**</span></span> | <span data-ttu-id="e5cfa-196">permiso</span><span class="sxs-lookup"><span data-stu-id="e5cfa-196">permission</span></span> |
| <span data-ttu-id="e5cfa-197">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-197">**Data type**</span></span> | <span data-ttu-id="e5cfa-198">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-198">Array of strings</span></span> |
| <span data-ttu-id="e5cfa-199">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-199">**Possible values**</span></span> | <span data-ttu-id="e5cfa-200">ninguno</span><span class="sxs-lookup"><span data-stu-id="e5cfa-200">none</span></span> <br/> <span data-ttu-id="e5cfa-201">read</span><span class="sxs-lookup"><span data-stu-id="e5cfa-201">read</span></span> <br/> <span data-ttu-id="e5cfa-202">write</span><span class="sxs-lookup"><span data-stu-id="e5cfa-202">write</span></span> <br/> <span data-ttu-id="e5cfa-203">execute</span><span class="sxs-lookup"><span data-stu-id="e5cfa-203">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="e5cfa-204">Restringir medios extraíbles por proveedor, producto y número de serie</span><span class="sxs-lookup"><span data-stu-id="e5cfa-204">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="e5cfa-205">Como se describe en [Permitir](#allow-or-block-removable-devices)o bloquear dispositivos extraíbles, los medios extraíbles, como dispositivos USB, pueden identificarse mediante el identificador de proveedor, el identificador de producto y el número de serie.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-205">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="e5cfa-206">En el nivel superior de la directiva de medios extraíbles, opcionalmente puede definir restricciones más granulares en el nivel de proveedor.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-206">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="e5cfa-207">El `vendors` diccionario contiene una o más entradas, con cada entrada identificada por el identificador de proveedor.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-207">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-208">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-209">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-209">**Key**</span></span> | <span data-ttu-id="e5cfa-210">proveedores</span><span class="sxs-lookup"><span data-stu-id="e5cfa-210">vendors</span></span> |
| <span data-ttu-id="e5cfa-211">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-211">**Data type**</span></span> | <span data-ttu-id="e5cfa-212">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-212">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e5cfa-213">Para cada proveedor, puede especificar el nivel de permisos deseado para los dispositivos de ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-213">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-214">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-214">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-215">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-215">**Key**</span></span> | <span data-ttu-id="e5cfa-216">permiso</span><span class="sxs-lookup"><span data-stu-id="e5cfa-216">permission</span></span> |
| <span data-ttu-id="e5cfa-217">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-217">**Data type**</span></span> | <span data-ttu-id="e5cfa-218">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-218">Array of strings</span></span> |
| <span data-ttu-id="e5cfa-219">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-219">**Possible values**</span></span> | <span data-ttu-id="e5cfa-220">Igual que [el nivel de permisos predeterminado](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-220">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="e5cfa-221">Además, puede especificar opcionalmente el conjunto de productos que pertenecen a ese proveedor para el que se definen permisos más granulares.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-221">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="e5cfa-222">El diccionario contiene una o más entradas, con `products` cada entrada identificada por el identificador del producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-222">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="e5cfa-223">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-223">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-224">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-224">**Key**</span></span> | <span data-ttu-id="e5cfa-225">productos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-225">products</span></span> |
| <span data-ttu-id="e5cfa-226">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-226">**Data type**</span></span> | <span data-ttu-id="e5cfa-227">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-227">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e5cfa-228">Para cada producto, puede especificar el nivel de permisos deseado para ese producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-228">For each product, you can specify the desired permission level for that product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-229">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-230">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-230">**Key**</span></span> | <span data-ttu-id="e5cfa-231">permiso</span><span class="sxs-lookup"><span data-stu-id="e5cfa-231">permission</span></span> |
| <span data-ttu-id="e5cfa-232">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-232">**Data type**</span></span> | <span data-ttu-id="e5cfa-233">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-233">Array of strings</span></span> |
| <span data-ttu-id="e5cfa-234">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-234">**Possible values**</span></span> | <span data-ttu-id="e5cfa-235">Igual que [el nivel de permisos predeterminado](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-235">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="e5cfa-236">Además, puede especificar un conjunto opcional de números de serie para los que se definen permisos más granulares.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-236">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="e5cfa-237">El `serialNumbers` diccionario contiene una o más entradas, con cada entrada identificada por el número de serie.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-237">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-238">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-238">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-239">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-239">**Key**</span></span> | <span data-ttu-id="e5cfa-240">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="e5cfa-240">serialNumbers</span></span> |
| <span data-ttu-id="e5cfa-241">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-241">**Data type**</span></span> | <span data-ttu-id="e5cfa-242">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-242">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e5cfa-243">Para cada número de serie, puede especificar el nivel de permisos deseado.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-243">For each serial number, you can specify the desired permission level.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e5cfa-244">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-244">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e5cfa-245">**Clave**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-245">**Key**</span></span> | <span data-ttu-id="e5cfa-246">permiso</span><span class="sxs-lookup"><span data-stu-id="e5cfa-246">permission</span></span> |
| <span data-ttu-id="e5cfa-247">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-247">**Data type**</span></span> | <span data-ttu-id="e5cfa-248">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-248">Array of strings</span></span> |
| <span data-ttu-id="e5cfa-249">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="e5cfa-249">**Possible values**</span></span> | <span data-ttu-id="e5cfa-250">Igual que [el nivel de permisos predeterminado](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-250">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="e5cfa-251">Ejemplo de directiva de control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-251">Example device control policy</span></span>

<span data-ttu-id="e5cfa-252">En el siguiente ejemplo se muestra cómo se pueden combinar todos los conceptos anteriores en una directiva de control de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-252">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="e5cfa-253">En el ejemplo siguiente, tenga en cuenta la naturaleza jerárquica de la directiva de medios extraíble.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-253">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="e5cfa-254">Hemos incluido más ejemplos de directivas de control de dispositivos en los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-254">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="e5cfa-255">Ejemplos de directivas de control de dispositivos para Intune</span><span class="sxs-lookup"><span data-stu-id="e5cfa-255">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="e5cfa-256">Ejemplos de directivas de control de dispositivos para JAMF</span><span class="sxs-lookup"><span data-stu-id="e5cfa-256">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="e5cfa-257">Buscar identificadores de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5cfa-257">Look up device identifiers</span></span>

<span data-ttu-id="e5cfa-258">Para buscar el identificador de proveedor, el id. de producto y el número de serie de un dispositivo USB:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-258">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="e5cfa-259">Inicie sesión en un dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-259">Log into a Mac device.</span></span>
1. <span data-ttu-id="e5cfa-260">Conecta el dispositivo USB para el que quieres buscar los identificadores.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-260">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="e5cfa-261">En el menú de nivel superior de macOS, seleccione **Acerca de este Mac**.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-261">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Acerca de este Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="e5cfa-263">Seleccione **Informe del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-263">Select **System Report**.</span></span>

    ![Informe del sistema](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="e5cfa-265">En la columna izquierda, seleccione **USB**.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-265">From the left column, select **USB**.</span></span>

    ![Vista de todos los dispositivos USB](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="e5cfa-267">En **Árbol de dispositivos USB,** vaya al dispositivo USB que enchufó.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-267">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Detalles de un dispositivo USB](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="e5cfa-269">Se muestran el id. de proveedor, el id. de producto y el número de serie.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-269">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="e5cfa-270">Al agregar el identificador de proveedor y el id. de producto a la directiva de medios extraíbles, solo debe agregar la parte después de `0x` .</span><span class="sxs-lookup"><span data-stu-id="e5cfa-270">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="e5cfa-271">Por ejemplo, en la imagen siguiente, el id. de proveedor `1000` es y el id. de producto es `090c` .</span><span class="sxs-lookup"><span data-stu-id="e5cfa-271">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="e5cfa-272">Descubrir dispositivos USB en la organización</span><span class="sxs-lookup"><span data-stu-id="e5cfa-272">Discover USB devices in your organization</span></span>

<span data-ttu-id="e5cfa-273">Puedes ver eventos de montaje, desmontaje y cambio de volumen que se originen desde dispositivos USB en Microsoft Defender para la búsqueda avanzada de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-273">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="e5cfa-274">Estos eventos pueden ser útiles para identificar actividades de uso sospechosas o realizar investigaciones internas.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-274">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="e5cfa-275">Implementación de directivas de control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e5cfa-275">Device control policy deployment</span></span>

<span data-ttu-id="e5cfa-276">La directiva de control de dispositivos debe incluirse junto a la otra configuración del producto, como se describe en Establecer preferencias para [Microsoft Defender para Endpoint para Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="e5cfa-276">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="e5cfa-277">Este perfil se puede implementar con las instrucciones enumeradas en [Implementación de perfiles de configuración.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="e5cfa-277">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="e5cfa-278">Sugerencias para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="e5cfa-278">Troubleshooting tips</span></span>

<span data-ttu-id="e5cfa-279">Después de insertar el perfil de configuración a través de Intune o JAMF, puede comprobar si el producto lo ha seleccionado correctamente ejecutando el siguiente comando desde el Terminal:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-279">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="e5cfa-280">Este comando imprimirá en salida estándar la directiva de control de dispositivos que usa el producto.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-280">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="e5cfa-281">En caso de que esto se imprima, asegúrese de que (a) el perfil de configuración se haya instalado en el dispositivo desde la consola de administración y (b) sea una directiva de control de dispositivo válida, como se describe en este `Policy is empty` documento.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-281">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="e5cfa-282">En un dispositivo donde la directiva se ha entregado correctamente y donde hay uno o varios dispositivos conectados, puedes ejecutar el siguiente comando para enumerar todos los dispositivos y los permisos efectivos que se les aplican.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-282">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="e5cfa-283">Ejemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="e5cfa-283">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="e5cfa-284">En el ejemplo anterior, solo hay un dispositivo multimedia extraíble conectado y tiene y permisos, según la directiva de control de dispositivo que se entregó `read` `execute` al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5cfa-284">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5cfa-285">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e5cfa-285">Related topics</span></span>

- [<span data-ttu-id="e5cfa-286">Ejemplos de directivas de control de dispositivos para Intune</span><span class="sxs-lookup"><span data-stu-id="e5cfa-286">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="e5cfa-287">Ejemplos de directivas de control de dispositivos para JAMF</span><span class="sxs-lookup"><span data-stu-id="e5cfa-287">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)