---
title: Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft
description: certs/wifi/lan
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
ms.openlocfilehash: cf31778d773a271ead6a1745197f04eca127ab5d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841100"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft  
 
La autenticación basada en certificados es un requisito común para los clientes que usan escritorio administrado de Microsoft. Es posible que necesites certificados para acceder a Wi-Fi o LAN, para conectarte a soluciones VPN o para acceder a recursos internos de la organización.   
 
Dado que los dispositivos de escritorio administrados de Microsoft se unen a Azure Active Directory (Azure AD) y se administran mediante Microsoft Intune, debe implementar dichos certificados mediante un protocolo simple de inscripción de certificados (SCEP) o una infraestructura de certificados estándar de criptografía de clave pública (PKCS) integrada con Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de certificado 
 
Los certificados raíz son necesarios para implementar certificados a través de una infraestructura SCEP o PKCS. Es posible que otras aplicaciones y servicios de la organización requieran la implementación de certificados raíz en los dispositivos de Escritorio administrado de Microsoft.    
 
Antes de implementar certificados SCEP o PKCS en el Escritorio administrado de Microsoft, debe recopilar los requisitos para cada servicio que requiera un certificado de usuario o dispositivo en su organización. Para facilitar esta actividad, puede usar una de las siguientes plantillas de planeación:  
 
- [Plantilla de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Plantilla de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi de conectividad

Para permitir que un dispositivo se pueda proporcionar automáticamente con la configuración de Wi-Fi necesaria para la red empresarial, es posible que necesites un perfil de configuración Wi-Fi usuario. Puede configurar escritorio administrado de Microsoft para implementar estos perfiles en sus dispositivos. Si la seguridad de red requiere que los dispositivos sean parte del dominio local, es posible que también deba evaluar la infraestructura de red de Wi-Fi para asegurarse de que es compatible con dispositivos de Escritorio administrado de Microsoft (los dispositivos de Escritorio administrado de Microsoft solo están unidos a Azure AD). 
 
Antes de implementar una configuración de Wi-Fi en dispositivos de Escritorio administrado de Microsoft, tendrá que recopilar los requisitos de la organización para cada red Wi-Fi cliente. Para facilitar esta actividad, puedes usar esta plantilla [de perfil wi-fi.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividad por cable y autenticación 802.1x 
 
Si usa la autenticación 802.1x para proteger el acceso desde dispositivos a la red de área local (LAN), deberá insertar los detalles de configuración necesarios en los dispositivos de Escritorio administrado de Microsoft. Los dispositivos de Escritorio administrado de Microsoft que ejecutan Windows 10, versión 1809 o posterior, admiten la implementación de una configuración 802.1x a través del proveedor de servicios de configuración (CSP) WiredNetwork. Para obtener más información, consulta [la documentación de WIREDNetwork CSP.](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 
 
Antes de implementar un perfil de configuración de red cableada en dispositivos de Escritorio administrado de Microsoft, recopile los requisitos de su organización para la red corporativa cableada. Para hacerlo, siga estos pasos: 
 
 
1. Inicie sesión en un dispositivo que tenga configurado el perfil 802.1x existente y esté conectado a la red LAN.  
2. Abra un símbolo del sistema con credenciales administrativas. 
3. Busque el nombre de la interfaz LAN mediante la ejecución **de la interfaz netsh para mostrar la interfaz.** 
4. Exporte el XML de perfil LAN ejecutando **netsh lan export profile folder=.  Interface="interface_name"**. 
5. Si necesita probar el perfil exportado en el dispositivo de Escritorio administrado de Microsoft, ejecute **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implementar la infraestructura de certificados  
 
Si ya tiene una infraestructura SCEP o PKCS existente con Intune y este enfoque cumple sus requisitos, también puede usarlo para escritorio administrado de Microsoft. Si no existe ninguna infraestructura de SCEP o PKCS, tendrá que preparar una.  
 
Para obtener más información, consulta [Configurar un perfil de certificado para los dispositivos en Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure) 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implementar un perfil de LAN 
 
Una vez exportado el perfil de LAN, puede preparar la directiva para escritorio administrado de Microsoft siguiendo estos pasos:   
 
1. Cree un perfil personalizado en Microsoft Intune para el perfil DEN con la siguiente configuración (vea Usar la configuración personalizada para dispositivos [Windows 10 en Intune).](https://docs.microsoft.com/intune/custom-settings-windows-10) En **Configuración personalizada de OMA-URI,** selecciona **Agregar** y, a continuación, escribe los siguientes valores: 
    - Nombre: *perfil Workplace-Windows 10 LAN* 
    - Descripción: escriba una descripción que dé información general sobre la configuración y cualquier otro detalle importante. 
    - OMA-URI (distingue mayúsculas de minúsculas): escriba *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de datos: seleccione **Cadena (archivo XML).** 
    - XML personalizado: cargar el archivo XML exportado.
2. Envíe una solicitud de soporte técnico a las operaciones de TI de Escritorio administrado de Microsoft mediante el portal de administración de escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "Dispositivos de trabajo modernos: prueba". Las operaciones de TI de escritorio administrado de Microsoft le permitirán saber cuándo se completa la solicitud a través de la solicitud de soporte técnico en el portal de administración.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementar certificados y perfil de Wi-Fi/VPN 
 
 
Para implementar certificados y perfiles, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedio (vea [Crear perfiles de certificado de confianza.](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AAA. **Los perfiles de certificado sin una fecha de expiración no se implementarán.**
2. Cree un perfil para cada certificado SCEP o PKCS (vea Crear un perfil de certificado [SCEP](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) o Crear un perfil de certificado [PKCS)](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AAA. **Los perfiles de certificado sin una fecha de expiración no se implementarán.**
3. Crea un perfil para cada red WiFi corporativa (consulta la configuración [de Wi-Fi para Windows 10 y dispositivos posteriores).](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. Crea un perfil para cada VPN corporativa (consulta la configuración de [dispositivos Windows 10](https://docs.microsoft.com/intune/vpn-settings-windows-10)y Windows Holographic para agregar conexiones VPN con Intune).
5. Envíe una solicitud de soporte técnico titulada "Implementación de certificados" o "Implementación de perfiles Wi-Fi" a las operaciones de TI de escritorio administrado de Microsoft mediante el portal de administración de Escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "Dispositivos de trabajo modernos: prueba". Las operaciones de TI de escritorio administrado de Microsoft le permitirán saber cuándo se ha completado la solicitud a través de la solicitud de soporte técnico en el portal de administración. 
 
 
