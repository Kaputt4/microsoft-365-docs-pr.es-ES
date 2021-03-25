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
# <a name="device-control-for-macos"></a>Control de dispositivos para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a>Requisitos

El control de dispositivos para macOS tiene los siguientes requisitos previos:

>[!div class="checklist"]
> - Derechos de Microsoft Defender para extremo (puede ser de prueba)
> - Versión mínima del sistema operativo: macOS 10.15.4 o posterior
> - Versión mínima del producto: 101.24.59
> - El dispositivo debe ejecutarse con extensiones del sistema (este es el valor predeterminado en macOS 11 Big Sur). 
> 
>   Para comprobar si el dispositivo se está ejecutando en extensiones del sistema, ejecute el siguiente comando y compruebe que se está imprimiendo `endpoint_security_extension` en la consola: 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - El dispositivo debe estar en `Beta` el canal de actualización de Microsoft AutoUpdate (anteriormente denominado `InsiderFast` ) . Para obtener más información, vea [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).
> 
>   Puede comprobar el canal de actualización con el siguiente comando: 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    Si el comando anterior no imprime ni `Beta` , ejecute el siguiente comando desde `InsiderFast` terminal. La actualización de canal surte efecto la próxima vez que se inicie el producto (cuando se instale la siguiente actualización del producto o cuando se reinicie el dispositivo). 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    Como alternativa, si se encuentra en un entorno administrado (JAMF o Intune), puede configurar el canal de actualización de forma remota. Para obtener más información, vea [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md). 

## <a name="device-control-policy"></a>Directiva de control de dispositivos

Para configurar el control de dispositivos para macOS, debes crear una directiva que describa las restricciones que quieres establecer en tu organización.

La directiva de control de dispositivos se incluye en el perfil de configuración que se usa para configurar el resto de opciones de producto. Para obtener más información, vea [Configuration profile structure](mac-preferences.md#configuration-profile-structure).

Dentro del perfil de configuración, la directiva de control de dispositivos se define en la siguiente sección:

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | deviceControl |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

La directiva de control de dispositivos se puede usar para:

- [Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos](#customize-url-target-for-notifications-raised-by-device-control)
- [Permitir o bloquear dispositivos extraíbles](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos

Cuando se aplica la directiva de control de dispositivos que has puesto en marcha en un dispositivo (por ejemplo, el acceso a un dispositivo multimedia extraíble está restringido), se muestra una notificación al usuario.

![Notificación de control de dispositivos](images/mac-device-control-notification.png)

Cuando los usuarios finales hacen clic en esta notificación, se abre una página web en el explorador predeterminado. Puede configurar la dirección URL que se abre cuando los usuarios finales hacen clic en la notificación.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | navigationTarget |
| **Tipo de datos** | Cadena |
| **Comments** | Si no se define, el producto usa una dirección URL predeterminada que apunta a una página genérica que explica la acción realizada por el producto. |

### <a name="allow-or-block-removable-devices"></a>Permitir o bloquear dispositivos extraíbles

La sección de medios extraíbles de la directiva de control de dispositivos se usa para restringir el acceso a medios extraíbles. 

> [!NOTE]
> Actualmente se admiten los siguientes tipos de medios extraíbles y se pueden incluir en la directiva: dispositivos de almacenamiento USB.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | removableMediaPolicy |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

Esta sección de la directiva es jerárquica, lo que permite la máxima flexibilidad y cubre una amplia variedad de casos de uso. En el nivel superior se encuentran los proveedores, identificados por un identificador de proveedor. Para cada proveedor, hay productos identificados por un identificador de producto. Por último, para cada producto hay números de serie que indican dispositivos específicos.

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

Para obtener información sobre cómo encontrar los identificadores de dispositivo, consulta [Buscar identificadores de dispositivo.](#look-up-device-identifiers)

La directiva se evalúa desde la entrada más específica hasta la más general. Es decir, cuando un dispositivo está conectado, el producto intenta encontrar la coincidencia más específica en la directiva para cada dispositivo multimedia extraíble y aplicar los permisos en ese nivel. Si no hay coincidencia, se aplica la siguiente mejor coincidencia, hasta el permiso especificado en el nivel superior, que es el valor predeterminado cuando un dispositivo no coincide con ninguna otra entrada de la directiva.

#### <a name="policy-enforcement-level"></a>Nivel de aplicación de directivas

En la sección medios extraíbles, hay una opción para establecer el nivel de cumplimiento, que puede tener uno de los siguientes valores:

- `audit` - En este nivel de aplicación, si el acceso a un dispositivo está restringido, se muestra una notificación al usuario, pero aún se puede usar el dispositivo. Este nivel de cumplimiento puede ser útil para evaluar la eficacia de una directiva.
- `block` - En este nivel de cumplimiento, las operaciones que el usuario puede realizar en el dispositivo se limitan a lo que se define en la directiva. Además, se genera una notificación al usuario. 

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | enforcementLevel |
| **Tipo de datos** | Cadena |
| **Posibles valores** | auditoría (valor predeterminado) <br/> bloque |

#### <a name="default-permission-level"></a>Nivel de permisos predeterminado

En el nivel superior de la sección de medios extraíbles, puede configurar el nivel de permisos predeterminado para dispositivos que no coincidan con nada más en la directiva.

Esta configuración se puede establecer en:

- `none` - No se pueden realizar operaciones en el dispositivo
- Una combinación de los siguientes valores:
    - `read` - Las operaciones de lectura están permitidas en el dispositivo
    - `write` - Las operaciones de escritura están permitidas en el dispositivo
    - `execute` - Las operaciones de ejecución están permitidas en el dispositivo

> [!NOTE]
> Si `none` está presente en el nivel de permisos, cualquier otro permiso ( , , o ) se `read` `write` `execute` omitirá.

> [!NOTE]
> El `execute` permiso solo hace referencia a la ejecución de archivos binarios de Mach-O. No incluye la ejecución de scripts u otros tipos de cargas.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | permiso |
| **Tipo de datos** | Matriz de cadenas |
| **Posibles valores** | ninguno <br/> read <br/> write <br/> execute |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Restringir medios extraíbles por proveedor, producto y número de serie

Como se describe en [Permitir](#allow-or-block-removable-devices)o bloquear dispositivos extraíbles, los medios extraíbles, como dispositivos USB, pueden identificarse mediante el identificador de proveedor, el identificador de producto y el número de serie.

En el nivel superior de la directiva de medios extraíbles, opcionalmente puede definir restricciones más granulares en el nivel de proveedor. 

El `vendors` diccionario contiene una o más entradas, con cada entrada identificada por el identificador de proveedor.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | proveedores |
| **Tipo de datos** | Diccionario (preferencia anidada) |

Para cada proveedor, puede especificar el nivel de permisos deseado para los dispositivos de ese proveedor.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | permiso |
| **Tipo de datos** | Matriz de cadenas |
| **Posibles valores** | Igual que [el nivel de permisos predeterminado](#default-permission-level) |

Además, puede especificar opcionalmente el conjunto de productos que pertenecen a ese proveedor para el que se definen permisos más granulares. El diccionario contiene una o más entradas, con `products` cada entrada identificada por el identificador del producto. 

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | productos |
| **Tipo de datos** | Diccionario (preferencia anidada) |

Para cada producto, puede especificar el nivel de permisos deseado para ese producto.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | permiso |
| **Tipo de datos** | Matriz de cadenas |
| **Posibles valores** | Igual que [el nivel de permisos predeterminado](#default-permission-level) |

Además, puede especificar un conjunto opcional de números de serie para los que se definen permisos más granulares.

El `serialNumbers` diccionario contiene una o más entradas, con cada entrada identificada por el número de serie.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | serialNumbers |
| **Tipo de datos** | Diccionario (preferencia anidada) |

Para cada número de serie, puede especificar el nivel de permisos deseado.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | permiso |
| **Tipo de datos** | Matriz de cadenas |
| **Posibles valores** | Igual que [el nivel de permisos predeterminado](#default-permission-level) |

#### <a name="example-device-control-policy"></a>Ejemplo de directiva de control de dispositivos

En el siguiente ejemplo se muestra cómo se pueden combinar todos los conceptos anteriores en una directiva de control de dispositivos. En el ejemplo siguiente, tenga en cuenta la naturaleza jerárquica de la directiva de medios extraíble.

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

Hemos incluido más ejemplos de directivas de control de dispositivos en los siguientes documentos:

- [Ejemplos de directivas de control de dispositivos para Intune](mac-device-control-intune.md)
- [Ejemplos de directivas de control de dispositivos para JAMF](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>Buscar identificadores de dispositivo

Para buscar el identificador de proveedor, el id. de producto y el número de serie de un dispositivo USB:

1. Inicie sesión en un dispositivo Mac.
1. Conecta el dispositivo USB para el que quieres buscar los identificadores.
1. En el menú de nivel superior de macOS, seleccione **Acerca de este Mac**.

    ![Acerca de este Mac](images/mac-device-control-lookup-1.png)

1. Seleccione **Informe del sistema**.

    ![Informe del sistema](images/mac-device-control-lookup-2.png)

1. En la columna izquierda, seleccione **USB**.

    ![Vista de todos los dispositivos USB](images/mac-device-control-lookup-3.png)

1. En **Árbol de dispositivos USB,** vaya al dispositivo USB que enchufó.

    ![Detalles de un dispositivo USB](images/mac-device-control-lookup-4.png)

1. Se muestran el id. de proveedor, el id. de producto y el número de serie. Al agregar el identificador de proveedor y el id. de producto a la directiva de medios extraíbles, solo debe agregar la parte después de `0x` . Por ejemplo, en la imagen siguiente, el id. de proveedor `1000` es y el id. de producto es `090c` .

#### <a name="discover-usb-devices-in-your-organization"></a>Descubrir dispositivos USB en la organización

Puedes ver eventos de montaje, desmontaje y cambio de volumen que se originen desde dispositivos USB en Microsoft Defender para la búsqueda avanzada de puntos de conexión. Estos eventos pueden ser útiles para identificar actividades de uso sospechosas o realizar investigaciones internas.

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Implementación de directivas de control de dispositivos

La directiva de control de dispositivos debe incluirse junto a la otra configuración del producto, como se describe en Establecer preferencias para [Microsoft Defender para Endpoint para Mac](mac-preferences.md).

Este perfil se puede implementar con las instrucciones enumeradas en [Implementación de perfiles de configuración.](mac-preferences.md#configuration-profile-deployment)

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

Después de insertar el perfil de configuración a través de Intune o JAMF, puede comprobar si el producto lo ha seleccionado correctamente ejecutando el siguiente comando desde el Terminal:

```bash
mdatp device-control removable-media policy list
```

Este comando imprimirá en salida estándar la directiva de control de dispositivos que usa el producto. En caso de que esto se imprima, asegúrese de que (a) el perfil de configuración se haya instalado en el dispositivo desde la consola de administración y (b) sea una directiva de control de dispositivo válida, como se describe en este `Policy is empty` documento.

En un dispositivo donde la directiva se ha entregado correctamente y donde hay uno o varios dispositivos conectados, puedes ejecutar el siguiente comando para enumerar todos los dispositivos y los permisos efectivos que se les aplican.

```bash
mdatp device-control removable-media devices list
```

Ejemplo de resultado:

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

En el ejemplo anterior, solo hay un dispositivo multimedia extraíble conectado y tiene y permisos, según la directiva de control de dispositivo que se entregó `read` `execute` al dispositivo.

## <a name="related-topics"></a>Temas relacionados

- [Ejemplos de directivas de control de dispositivos para Intune](mac-device-control-intune.md)
- [Ejemplos de directivas de control de dispositivos para JAMF](mac-device-control-jamf.md)