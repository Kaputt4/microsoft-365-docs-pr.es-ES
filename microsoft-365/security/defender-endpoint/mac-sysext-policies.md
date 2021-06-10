---
title: Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de macOS
description: En este tema se describen los cambios que se deben realizar para beneficiarse de las extensiones del sistema, que sustituyen las extensiones de kernel en macOS Catalina y las versiones más recientes de macOS.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, kernel, system, extensions, catalina
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932744"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

En alineación con la evolución de macOS, estamos preparando una actualización de Microsoft Defender para Endpoint en macOS que aprovecha las extensiones del sistema en lugar de las extensiones de kernel. Esta actualización solo se aplicará a macOS Catalina (10.15.4) y versiones más recientes de macOS.

Si has implementado Microsoft Defender para Endpoint en macOS en un entorno administrado (a través de JAMF, Intune u otra solución MDM), debes implementar nuevos perfiles de configuración. Si no se hacen estos pasos, los usuarios recibirán solicitudes de aprobación para ejecutar estos nuevos componentes.

## <a name="jamf"></a>JAMF

### <a name="system-extensions-policy"></a>Directiva de extensiones del sistema

Para aprobar las extensiones del sistema, cree la siguiente carga:

1. En **Equipos > de configuración seleccione** Opciones > Extensiones del **sistema**.
2. Seleccione **Extensiones de sistema permitidas en** la lista desplegable Tipos **de** extensión del sistema.
3. Usa **UBF8T346G9 para** id. de equipo.
4. Agregue los siguientes identificadores de agrupación a la **lista Extensiones de sistema permitidas:**

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    ![Captura de pantalla de extensiones del sistema aprobadas](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a>Control de directiva de preferencias de privacidad

Agregue la siguiente carga de JAMF para conceder acceso en disco completo a Microsoft Defender para endpoint security extension. Esta directiva es un requisito previo para ejecutar la extensión en el dispositivo.

1. Seleccione **Opciones Control de** directiva de  >  **preferencias de privacidad**.
2. Se `com.microsoft.wdav.epsext` usa como identificador **y** como tipo `Bundle ID` de **agrupación**.
3. Establecer el requisito de código en `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. Establezca **Aplicación o servicio en** **SystemPolicyAllFiles** y acceso a **Permitir**.

    ![Control de directiva de preferencias de privacidad](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a>Directiva de extensión de red

Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para endpoint en macOS inspecciona el tráfico de sockets e informa de esta información al portal Centro de seguridad de Microsoft Defender web. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

>[!NOTE]
>JAMF no tiene compatibilidad integrada con directivas de filtrado de contenido, que son un requisito previo para habilitar las extensiones de red que Microsoft Defender para Endpoint en macOS instala en el dispositivo. Además, JAMF a veces cambia el contenido de las directivas que se implementan.
>Por lo tanto, los siguientes pasos proporcionan una solución alternativa que implica firmar el perfil de configuración.

1. Guarde el siguiente contenido en el dispositivo como `com.microsoft.network-extension.mobileconfig` si usara un editor de texto:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. Compruebe que el archivo anterior se copió correctamente ejecutando la `plutil` utilidad en el Terminal:

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    Por ejemplo, si el archivo se almacenaba en Documentos:

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    Compruebe que el comando genera `OK` .
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. Siga las instrucciones de [esta página para](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) crear un certificado de firma con la entidad de certificación integrada de JAMF.

4. Después de crear e instalar el certificado en el dispositivo, ejecute el siguiente comando desde el Terminal para firmar el archivo:

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    Por ejemplo, si el nombre del certificado es **SigningCertificate** y el archivo firmado se va a almacenar en Documentos:
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. En el portal jamf, vaya a **Perfiles de configuración** y haga clic en **el botón Upload** configuración. Seleccione `com.microsoft.network-extension.signed.mobileconfig` cuando se le pida el archivo.

## <a name="intune"></a>Intune

### <a name="system-extensions-policy"></a>Directiva de extensiones del sistema

Para aprobar las extensiones del sistema:

1. En Intune, abra **Administrar configuración**  >  **de dispositivo.** Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.
2. Elija un nombre para el perfil. Cambiar **Platform=macOS** a **Profile type=Extensions**. Seleccione **Crear**.
3. En la `Basics` pestaña, asigne un nombre a este nuevo perfil.
4. En la `Configuration settings` pestaña, agregue las siguientes entradas en la `Allowed system extensions` sección:

    Identificador de agrupación         | Identificador de equipo
    --------------------------|----------------
    com.microsoft.wdav.epsext | UBF8T346G9
    com.microsoft.wdav.netext | UBF8T346G9

    ![Captura de pantalla de perfiles de configuración del sistema](images/mac-system-extension-intune2.png)

5. En la `Assignments` pestaña, asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
6. Revise y cree este perfil de configuración.

### <a name="create-and-deploy-the-custom-configuration-profile"></a>Crear e implementar el perfil de configuración personalizado

El siguiente perfil de configuración habilita la extensión de red y concede acceso en disco completo a la extensión del sistema endpoint security. 

Guarde el siguiente contenido en un archivo denominado **sysext.xml**:

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Compruebe que el archivo anterior se copió correctamente. Desde el Terminal, ejecute el siguiente comando y compruebe que emite `OK` :

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

Para implementar este perfil de configuración personalizado:

1.  En Intune, abra **Administrar configuración**  >  **de dispositivo.** Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.
2. Elija un nombre para el perfil. Cambiar **Platform=macOS** y **Profile type=Custom**. Seleccione **Configurar**.
3.  Abra el perfil de configuración y cargue **sysext.xml**. Este archivo se creó en el paso anterior.
4.  Seleccione **Aceptar**.

    ![Extensión del sistema en la captura de pantalla de Intune](images/mac-system-extension-intune.png)

5. En la `Assignments` pestaña, asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
6. Revise y cree este perfil de configuración.
