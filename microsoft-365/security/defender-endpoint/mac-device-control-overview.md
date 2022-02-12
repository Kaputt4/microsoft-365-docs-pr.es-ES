---
title: Control de dispositivos para macOS
description: Obtén información sobre cómo configurar Microsoft Defender para Endpoint en Mac para reducir las amenazas del almacenamiento extraíble, como dispositivos USB.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, device, control, usb, removable, media
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cb41b0bd3f185237055daa2d282f0a1d6975a49
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765545"
---
# <a name="device-control-for-macos"></a>Control de dispositivos para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>Requisitos

El control de dispositivos para macOS tiene los siguientes requisitos previos:

> [!div class="checklist"]
>
> - Derechos de Microsoft Defender para extremo (puede ser de prueba)
> - Versión mínima del sistema operativo: macOS 11 o posterior
> - Versión mínima del producto: 101.34.20

## <a name="device-control-policy"></a>Directiva de control de dispositivos

Para configurar el control de dispositivos para macOS, debes crear una directiva que describa las restricciones que quieres establecer en tu organización.

La directiva de control de dispositivos se incluye en el perfil de configuración que se usa para configurar el resto de opciones de producto. Para obtener más información, vea [Estructura de perfiles de configuración](mac-preferences.md#configuration-profile-structure).

Dentro del perfil de configuración, la directiva de control de dispositivos se define en la siguiente sección:

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|deviceControl|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

La directiva de control de dispositivos se puede usar para:

- [Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos](#customize-url-target-for-notifications-raised-by-device-control)
- [Permitir o bloquear dispositivos extraíbles](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Personalizar el destino de dirección URL para las notificaciones que genera el control de dispositivos

Cuando se aplica la directiva de control de dispositivos que has puesto en marcha en un dispositivo (por ejemplo, el acceso a un dispositivo multimedia extraíble está restringido), se muestra una notificación al usuario.

![Notificación de control de dispositivos.](images/mac-device-control-notification.png)

Cuando los usuarios finales hacen clic en esta notificación, se abre una página web en el explorador predeterminado. Puede configurar la dirección URL que se abre cuando los usuarios finales hacen clic en la notificación.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|navigationTarget|
|**Tipo de datos**|String|
|**Comments**|Si no se define, el producto usa una dirección URL predeterminada que apunta a una página genérica que explica la acción realizada por el producto.|
|

### <a name="allow-or-block-removable-devices"></a>Permitir o bloquear dispositivos extraíbles

La sección de medios extraíbles de la directiva de control de dispositivos se usa para restringir el acceso a medios extraíbles.

> [!NOTE]
> Actualmente se admiten los siguientes tipos de medios extraíbles y se pueden incluir en la directiva: dispositivos de almacenamiento USB.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|removableMediaPolicy|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

Esta sección de la directiva es jerárquica, lo que permite la máxima flexibilidad y cubre una amplia variedad de casos de uso. En el nivel superior se encuentran los proveedores, identificados por un identificador de proveedor. Para cada proveedor, hay productos identificados por un identificador de producto. Por último, para cada producto hay números de serie que indican dispositivos específicos.

```text
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

Para obtener información sobre cómo buscar los identificadores de dispositivo, consulta [Buscar identificadores de dispositivo.](#look-up-device-identifiers)

La directiva se evalúa desde la entrada más específica hasta la más general. Es decir, cuando un dispositivo está conectado, el producto intenta encontrar la coincidencia más específica en la directiva para cada dispositivo multimedia extraíble y aplicar los permisos en ese nivel. Si no hay coincidencia, se aplica la siguiente mejor coincidencia, hasta el permiso especificado en el nivel superior, que es el valor predeterminado cuando un dispositivo no coincide con ninguna otra entrada de la directiva.

#### <a name="policy-enforcement-level"></a>Nivel de aplicación de directivas

En la sección medios extraíbles, hay una opción para establecer el nivel de cumplimiento, que puede tener uno de los siguientes valores:

- `audit` - En este nivel de aplicación, si el acceso a un dispositivo está restringido, se muestra una notificación al usuario, pero aún se puede usar el dispositivo. Este nivel de cumplimiento puede ser útil para evaluar la eficacia de una directiva.
- `block` - En este nivel de cumplimiento, las operaciones que el usuario puede realizar en el dispositivo se limitan a lo que se define en la directiva. Además, se genera una notificación al usuario.

> [!NOTE]
> De forma predeterminada, el nivel de cumplimiento se establece en `audit`.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|enforcementLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|auditoría (valor predeterminado) <p> bloque|
|

#### <a name="default-permission-level"></a>Nivel de permisos predeterminado

En el nivel superior de la sección de medios extraíbles, puede configurar el nivel de permisos predeterminado para dispositivos que no coincidan con nada más en la directiva.

Esta configuración se puede establecer en:

- `none` - No se pueden realizar operaciones en el dispositivo
- Una combinación de los siguientes valores:
  - `read` - Las operaciones de lectura están permitidas en el dispositivo
  - `write` - Las operaciones de escritura están permitidas en el dispositivo
  - `execute` - Las operaciones de ejecución están permitidas en el dispositivo

> [!NOTE]
> Si `none` está presente en el nivel de permisos, se omitirán los demás permisos (`read`, `write`o `execute`) .
>
> El `execute` permiso solo hace referencia a la ejecución de archivos binarios de Mach-O. No incluye la ejecución de scripts u otros tipos de cargas.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|ninguno <p> read <p> write <p> execute|
|

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Restringir medios extraíbles por proveedor, producto y número de serie

Como se describe en [Permitir o](#allow-or-block-removable-devices) bloquear dispositivos extraíbles, los medios extraíbles, como los dispositivos USB, pueden identificarse mediante el identificador de proveedor, el id. de producto y el número de serie.

En el nivel superior de la directiva de medios extraíbles, opcionalmente puede definir restricciones más granulares en el nivel de proveedor.

El `vendors` diccionario contiene una o más entradas, con cada entrada identificada por el identificador de proveedor.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|proveedores|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada proveedor, puede especificar el nivel de permisos deseado para los dispositivos de ese proveedor.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que [el nivel de permisos predeterminado](#default-permission-level)|
|

Además, puede especificar opcionalmente el conjunto de productos que pertenecen a ese proveedor para el que se definen permisos más granulares. El `products` diccionario contiene una o más entradas, con cada entrada identificada por el identificador del producto.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|productos|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada producto, puede especificar el nivel de permisos deseado para ese producto.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que [el nivel de permisos predeterminado](#default-permission-level)|
|

Además, puede especificar un conjunto opcional de números de serie para los que se definen permisos más granulares.

El `serialNumbers` diccionario contiene una o más entradas, con cada entrada identificada por el número de serie.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|serialNumbers|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada número de serie, puede especificar el nivel de permisos deseado.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que [el nivel de permisos predeterminado](#default-permission-level)|
|

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
1. En el menú de nivel superior de macOS, selecciona **Acerca de este Mac**.

    ![Acerca de este Mac.](images/mac-device-control-lookup-1.png)

1. Seleccione **Informe del sistema**.

    ![Informe del sistema.](images/mac-device-control-lookup-2.png)

1. En la columna izquierda, seleccione **USB**.

    ![Vista de todos los dispositivos USB.](images/mac-device-control-lookup-3.png)

1. En **Árbol de dispositivos USB**, navega hasta el dispositivo USB que conectaste.

    ![Detalles de un dispositivo USB.](images/mac-device-control-lookup-4.png)

1. Se muestran el id. de proveedor, el id. de producto y el número de serie. Al agregar el identificador de proveedor y el id. de producto a la directiva de medios extraíbles, solo debe agregar la parte después de `0x`. Por ejemplo, en la imagen siguiente, el id. de proveedor es `1000` y el id. de producto es `090c`.

#### <a name="discover-usb-devices-in-your-organization"></a>Descubrir dispositivos USB en la organización

Puedes ver eventos de montaje, desmontaje y cambio de volumen que se originen desde dispositivos USB en Microsoft Defender para la búsqueda avanzada de puntos de conexión. Estos eventos pueden ser útiles para identificar actividades de uso sospechosas o realizar investigaciones internas.

```bash
DeviceEvents
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Implementación de directivas de control de dispositivos

La directiva de control de dispositivos debe incluirse junto a la otra configuración del producto, como se describe en Establecer preferencias para [Microsoft Defender para Endpoint en macOS](mac-preferences.md).

Este perfil se puede implementar con las instrucciones enumeradas en [Implementación de perfiles de configuración](mac-preferences.md#configuration-profile-deployment).

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

Después de insertar el perfil de configuración a través de Intune o JAMF, puede comprobar si el producto lo ha seleccionado correctamente ejecutando el siguiente comando desde el Terminal:

```bash
mdatp device-control removable-media policy list
```

Este comando imprimirá en salida estándar la directiva de control de dispositivos que usa el producto. `Policy is empty`En caso de que esto se imprima, asegúrese de que (a) el perfil de configuración se haya instalado en el dispositivo desde la consola de administración y (b) sea una directiva de control de dispositivo válida, como se describe en este documento.

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

En el ejemplo anterior, solo `read` `execute` hay un dispositivo multimedia extraíble conectado y tiene y permisos, según la directiva de control de dispositivo que se entregó al dispositivo.

## <a name="related-topics"></a>Temas relacionados

- [Ejemplos de directivas de control de dispositivos para Intune](mac-device-control-intune.md)
- [Ejemplos de directivas de control de dispositivos para JAMF](mac-device-control-jamf.md)
