---
title: Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft
description: certs/WiFi/LAN
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7a0af5db4e18bc46436ace6f9fefefc18f0ccd68
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608280"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft  
 
La autenticación basada en certificados es un requisito común para los clientes que usan Microsoft Managed Desktop. Es posible que necesite certificados para acceder a Wi-Fi o LAN, conectarse a soluciones VPN o para obtener acceso a los recursos internos de su organización.   
 
Debido a que los dispositivos de escritorio administrados de Microsoft se unen a Azure Active Directory (Azure AD) y se administran mediante Microsoft Intune, debe implementar dichos certificados con una infraestructura de certificados de protocolo de inscripción de certificados (SCEP) o estándar de criptografía de clave pública (PKCS) integrada con Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de certificado 
 
Los certificados raíz son necesarios para implementar los certificados a través de una infraestructura SCEP o PKCS. Es posible que otras aplicaciones y servicios de la organización necesiten que se implementen certificados raíz en los dispositivos de escritorio administrados por Microsoft.    
 
Antes de implementar los certificados de SCEP o PKCS en el escritorio administrado de Microsoft, debe recopilar los requisitos para cada servicio que requiera un certificado de usuario o de dispositivo en la organización. Para facilitar esta tarea, puede usar una de las siguientes plantillas de planeación:  
 
- [Plantilla de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Plantilla de certificado de SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Actualmente, solo se admiten perfiles de certificado de SCEP para la implementación de perfiles de Wi-Fi en el escritorio administrado de Microsoft cuando se usa un tipo de EAP. No se admiten los perfiles de certificado PKCS. Consulte [Agregar configuración Wi-Fi para dispositivos Windows 10 en Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) para referencia.

  
## <a name="wi-fi-connectivity-requirements"></a>Requisitos de conectividad Wi-Fi

Para permitir que un dispositivo se suministre automáticamente con la configuración de Wi-Fi necesaria para la red de la empresa, es posible que necesite un perfil de configuración de Wi-Fi. Puede configurar Microsoft Managed Desktop para implementar estos perfiles en sus dispositivos. Si su seguridad de red requiere que los dispositivos formen parte del dominio local, es posible que también necesite evaluar su infraestructura de red Wi-Fi para asegurarse de que es compatible con los dispositivos de escritorio administrados por Microsoft (los dispositivos de escritorio administrados por Microsoft son solo Unidos a Azure AD). 
 
Antes de implementar una configuración de Wi-Fi en dispositivos de escritorio administrados por Microsoft, se le pedirá que reúna los requisitos de la organización para cada red Wi-Fi. Para facilitar esta tarea, puede usar esta [plantilla de perfil Wi-Fi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividad cableada y autenticación de 802.1 x 
 
Si usa la autenticación de 802.1 x para proteger el acceso desde dispositivos a la red de área local (LAN), deberá insertar los detalles de configuración necesarios en los dispositivos de escritorio administrados por Microsoft. Los dispositivos de escritorio administrados por Microsoft que ejecutan Windows 10, versión 1809 o posterior, admiten la implementación de una configuración de 802.1 x a través del proveedor de servicios de configuración (CSP) de WiredNetwork. Para obtener más información, consulte la documentación de [CSP de WiredNetwork](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) . 
 
Antes de implementar un perfil de configuración de red cableada en dispositivos de escritorio administrados por Microsoft, reúna los requisitos de la organización para la red corporativa cableada. Para hacerlo, siga estos pasos: 
 
 
1. Inicie sesión en un dispositivo que tenga el perfil 802.1 x existente configurado y que esté conectado a la red LAN.  
2. Abra un símbolo del sistema con credenciales administrativas. 
3. Para buscar el nombre de la interfaz LAN, ejecute **netsh interface show interface**. 
4. Exporte el XML de Perfil de LAN ejecutando **netsh LAN Export Profile Folder =.  Interface = "interface_name"**. 
5. Si necesita probar el perfil exportado en un dispositivo de escritorio administrado por Microsoft, ejecute **netsh LAN Add Profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implementación de la infraestructura de certificados  
 
Si ya tiene una infraestructura de SCEP o PKCS existente con Intune y esto cumple sus requisitos, también puede usarla para escritorio administrado de Microsoft. Si no existe ninguna infraestructura de SCEP o PKCS, tendrá que preparar una.  
 
Para obtener más información, vea [Configure a Certificate Profile for Your Devices in Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implementación de un perfil de LAN 
 
Una vez que se haya exportado el perfil de LAN, puede preparar la Directiva para el escritorio administrado de Microsoft mediante los siguientes pasos:   
 
1. Cree un perfil personalizado en Microsoft Intune para el perfil de LAN mediante la configuración siguiente (consulte [usar la configuración personalizada para dispositivos Windows 10 en Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). En **Configuración personalizada de OMA-URI**, seleccione **Agregar**y, a continuación, escriba los siguientes valores: 
    - Nombre: *área de trabajo moderna: Perfil de LAN de Windows 10* 
    - Descripción: escriba una descripción que proporcione información general sobre la configuración y otros detalles importantes. 
    - OMA-URI (distingue entre mayúsculas y minúsculas): Enter *./Device/Vendor/msft/WiredNetwork/LanXML*
    - Tipo de datos: seleccionar **cadena (archivo XML)**. 
    - XML personalizado: carga el archivo XML exportado.
2. Envíe una solicitud de soporte técnico a las operaciones de TI de escritorio administradas de Microsoft mediante el portal de administración de escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "dispositivos de área de trabajo modernos: prueba". Las operaciones de TI de escritorio administradas por Microsoft le permitirán saber cuándo se completa la solicitud a través de la solicitud de soporte en el portal de administración.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementación de certificados y el perfil de Wi-Fi/VPN 
 
 
Para implementar certificados y perfiles, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedios (consulte [Create Trusted Certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AAAA. **No se implementarán los perfiles de certificado sin una fecha de expiración.**
2. Cree un perfil para cada certificado SCEP o PKCS (consulte [Create a SCEP Certificate](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) Profile or [Create a PKCS Certificate Profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato dd/mm/aaaa. **No se implementarán los perfiles de certificado sin una fecha de expiración.**
3. Cree un perfil para cada red WiFi corporativa (consulte [configuración de Wi-Fi para dispositivos con Windows 10 y versiones posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Cree un perfil para cada VPN corporativa (consulte la configuración de dispositivo de Windows [10 y Windows Holographic para agregar conexiones VPN con Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Envíe una solicitud de soporte titulada "implementación de certificados" o "implementación de Perfil de Wi-Fi" a operaciones de TI de escritorio administradas por Microsoft mediante el portal de administración de escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "dispositivos del área de trabajo modernos: prueba". Las operaciones de TI de escritorio administradas por Microsoft le permitirán saber cuándo se ha completado la solicitud a través de la solicitud de soporte técnico en el portal de administración. 
 
 
