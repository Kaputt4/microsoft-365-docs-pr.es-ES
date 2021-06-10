---
title: Ejemplos de directivas de control de dispositivos para JAMF
description: Aprende a usar directivas de control de dispositivos con ejemplos que se pueden usar con JAMF.
keywords: microsoft, defender, endpoint, Microsoft Defender para Endpoint, mac, device, control, usb, removable, media, jamf
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
ms.openlocfilehash: b9ce161a472366d11b267824c9bd08ceccf285aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933462"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="cf291-104">Ejemplos de directivas de control de dispositivos para JAMF</span><span class="sxs-lookup"><span data-stu-id="cf291-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf291-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cf291-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf291-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cf291-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf291-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf291-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cf291-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="cf291-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cf291-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf291-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cf291-110">Este documento contiene ejemplos de directivas de control de dispositivos que puedes personalizar para tu propia organización.</span><span class="sxs-lookup"><span data-stu-id="cf291-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="cf291-111">Estos ejemplos son aplicables si usa JAMF para administrar dispositivos en su empresa.</span><span class="sxs-lookup"><span data-stu-id="cf291-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="cf291-112">Restringir el acceso a todos los medios extraíbles</span><span class="sxs-lookup"><span data-stu-id="cf291-112">Restrict access to all removable media</span></span>

<span data-ttu-id="cf291-113">En el ejemplo siguiente se restringe el acceso a todos los medios extraíbles.</span><span class="sxs-lookup"><span data-stu-id="cf291-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="cf291-114">Tenga en cuenta el permiso que se aplica en el nivel superior de la directiva, lo que significa que todas las operaciones `none` de archivos estarán prohibidas.</span><span class="sxs-lookup"><span data-stu-id="cf291-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="cf291-115">Establecer todos los medios extraíbles como de solo lectura</span><span class="sxs-lookup"><span data-stu-id="cf291-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="cf291-116">En el ejemplo siguiente se configura todos los medios extraíbles para que sean de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="cf291-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="cf291-117">Tenga en cuenta el permiso que se aplica en el nivel superior de la directiva, lo que significa que no se permitirán todas las operaciones de `read` escritura y ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf291-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="cf291-118">No permitir la ejecución del programa de medios extraíbles</span><span class="sxs-lookup"><span data-stu-id="cf291-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="cf291-119">En el ejemplo siguiente se muestra cómo se puede no poder realizar la ejecución del programa desde medios extraíbles.</span><span class="sxs-lookup"><span data-stu-id="cf291-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="cf291-120">Tenga en `read` cuenta los permisos y que se aplican en el nivel superior de la `write` directiva.</span><span class="sxs-lookup"><span data-stu-id="cf291-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="cf291-121">Restringir todos los dispositivos de proveedores específicos</span><span class="sxs-lookup"><span data-stu-id="cf291-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="cf291-122">En el ejemplo siguiente se restringen todos los dispositivos de proveedores específicos (en este caso identificados por `fff0` y `4525` ).</span><span class="sxs-lookup"><span data-stu-id="cf291-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="cf291-123">El resto de dispositivos no estarán restringidos, ya que el permiso definido en el nivel superior de la directiva enumera todos los permisos posibles (lectura, escritura y ejecución).</span><span class="sxs-lookup"><span data-stu-id="cf291-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="cf291-124">Restringir dispositivos específicos identificados por id. de proveedor, id. de producto y número de serie</span><span class="sxs-lookup"><span data-stu-id="cf291-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="cf291-125">En el ejemplo siguiente se restringen dos dispositivos específicos, identificados por el identificador de proveedor, el id. de producto `fff0` y los números de serie y `1000` `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="cf291-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="cf291-126">En todos los demás niveles de la directiva, los permisos incluyen todos los valores posibles (lectura, escritura y ejecución), lo que significa que todos los demás dispositivos no estarán restringidos.</span><span class="sxs-lookup"><span data-stu-id="cf291-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="cf291-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cf291-127">Related topics</span></span>

- [<span data-ttu-id="cf291-128">Información general sobre el control de dispositivos para macOS</span><span class="sxs-lookup"><span data-stu-id="cf291-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
