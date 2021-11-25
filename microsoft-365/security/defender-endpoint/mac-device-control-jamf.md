---
title: Ejemplos de directivas de control de dispositivos para JAMF
description: Aprende a usar directivas de control de dispositivos con ejemplos que se pueden usar con JAMF.
keywords: microsoft, defender, endpoint, Microsoft Defender para Endpoint, mac, device, control, usb, removable, media, jamf
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20579b54e0ce9e58c1466afbbda348730ffad839
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168527"
---
# <a name="examples-of-device-control-policies-for-jamf"></a>Ejemplos de directivas de control de dispositivos para JAMF

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este documento contiene ejemplos de directivas de control de dispositivos que puedes personalizar para tu propia organización. Estos ejemplos son aplicables si usa JAMF para administrar dispositivos en su empresa.

## <a name="restrict-access-to-all-removable-media"></a>Restringir el acceso a todos los medios extraíbles

En el ejemplo siguiente se restringe el acceso a todos los medios extraíbles. Tenga en cuenta el permiso que se aplica en el nivel superior de la directiva, lo que significa que todas las operaciones `none` de archivos estarán prohibidas.

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

## <a name="set-all-removable-media-to-be-read-only"></a>Establecer todos los medios extraíbles como de solo lectura

En el ejemplo siguiente se configura todos los medios extraíbles para que sean de solo lectura. Tenga en cuenta el permiso que se aplica en el nivel superior de la directiva, lo que significa que no se permitirán todas las operaciones de `read` escritura y ejecución.

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

## <a name="disallow-program-execution-from-removable-media"></a>No permitir la ejecución del programa de medios extraíbles

En el ejemplo siguiente se muestra cómo se puede no poder realizar la ejecución del programa desde medios extraíbles. Tenga en `read` cuenta los permisos y que se aplican en el nivel superior de la `write` directiva.

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

## <a name="restrict-all-devices-from-specific-vendors"></a>Restringir todos los dispositivos de proveedores específicos

En el ejemplo siguiente se restringen todos los dispositivos de proveedores específicos (en este caso identificados por `fff0` y `4525` ). El resto de dispositivos no estarán restringidos, ya que el permiso definido en el nivel superior de la directiva enumera todos los permisos posibles (lectura, escritura y ejecución).

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

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>Restringir dispositivos específicos identificados por id. de proveedor, id. de producto y número de serie

En el ejemplo siguiente se restringen dos dispositivos específicos, identificados por el identificador de proveedor, el id. de producto `fff0` y los números de serie y `1000` `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` . En todos los demás niveles de la directiva, los permisos incluyen todos los valores posibles (lectura, escritura y ejecución), lo que significa que todos los demás dispositivos no estarán restringidos.

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

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre el control de dispositivos para macOS](mac-device-control-overview.md)
