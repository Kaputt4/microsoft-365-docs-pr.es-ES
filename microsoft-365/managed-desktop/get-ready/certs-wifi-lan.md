---
title: Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft
description: Requisitos de certificado y conectividad wi-fi
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
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574588"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft  
 
La autenticación basada en certificados es un requisito común para los clientes que usan Escritorio administrado de Microsoft. Es posible que necesite certificados para obtener acceso a Wi-Fi o LAN, para conectarse a soluciones VPN o para obtener acceso a recursos internos de la organización.   
 
Dado que los dispositivos Escritorio administrado de Microsoft se unen a Azure Active Directory (Azure AD) y se administran mediante Microsoft Intune, debe implementar dichos certificados mediante una infraestructura de certificados del Protocolo simple de inscripción de certificados (SCEP) o una infraestructura de certificado estándar de criptografía de clave pública (PKCS) integrada con Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de certificado 
 
Los certificados raíz son necesarios para implementar certificados a través de una infraestructura SCEP o PKCS. Es posible que otras aplicaciones y servicios de la organización requieran la implementación de certificados raíz en los Escritorio administrado de Microsoft dispositivos.    
 
Antes de implementar certificados SCEP o PKCS en Escritorio administrado de Microsoft, debe recopilar requisitos para cada servicio que requiera un certificado de usuario o dispositivo en su organización. Para facilitar esta actividad, puede usar una de las siguientes plantillas de planeación:  
 
- [Plantilla de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Plantilla de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi de conectividad

Para permitir que un dispositivo se proporciona automáticamente con la configuración Wi-Fi configuración necesaria para la red de empresa, es posible que necesites un Wi-Fi de configuración. Puedes configurar Escritorio administrado de Microsoft para implementar estos perfiles en tus dispositivos. Si la seguridad de red requiere que los dispositivos sean parte del dominio local, es posible que también deba evaluar la infraestructura de red de Wi-Fi para asegurarse de que es compatible con dispositivos Escritorio administrado de Microsoft (los dispositivos Escritorio administrado de Microsoft solo están unidos a Azure AD). 
 
Antes de implementar una configuración Wi-Fi en Escritorio administrado de Microsoft dispositivos, se le requiere recopilar los requisitos de la organización para cada Wi-Fi red. Para facilitar esta actividad, puede usar esta plantilla [de perfil de WiFi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividad por cable y autenticación 802.1x 
 
Si usas la autenticación 802.1x para proteger el acceso desde dispositivos a la red de área local (LAN), deberás insertar los detalles de configuración necesarios en los dispositivos Escritorio administrado de Microsoft usuario. Escritorio administrado de Microsoft dispositivos que ejecutan Windows 10, versión 1809 o posterior admiten la implementación de una configuración 802.1x a través del proveedor de servicios de configuración WiredNetwork (CSP). Para obtener más información, consulte [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation. 
 
Antes de implementar un perfil de configuración de red por cable Escritorio administrado de Microsoft dispositivos, recopile los requisitos de la organización para la red corporativa cableada. Para hacerlo, siga estos pasos: 
 
 
1. Inicie sesión en un dispositivo que tenga configurado el perfil 802.1x existente y esté conectado a la red LAN.  
2. Abra un símbolo del sistema con credenciales administrativas. 
3. Para buscar el nombre de la interfaz LAN, ejecute **netsh interface show interface**. 
4. Exporte el XML de perfil DE LAN ejecutando **netsh lan export profile folder=.  Interface="interface_name"**. 
5. Si necesitas probar el perfil exportado en un dispositivo Escritorio administrado de Microsoft, ejecuta **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implementar infraestructura de certificados  
 
Si ya tiene una infraestructura SCEP o PKCS existente con Intune y este enfoque cumple sus requisitos, también puede usarlo para Escritorio administrado de Microsoft. Si ya no existe ninguna infraestructura SCEP o PKCS, tendrá que preparar una.  
 
Para obtener más información, vea [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implementar un perfil de LAN 
 
Una vez exportado el perfil de LAN, puede preparar la directiva para Escritorio administrado de Microsoft siguiendo estos pasos:   
 
1. Cree un perfil personalizado en Microsoft Intune para el perfil de LAN con la siguiente configuración (vea Usar la configuración personalizada para [Windows 10 dispositivos en Intune](/intune/custom-settings-windows-10)). En **Custom OMA-URI Configuración**, seleccione **Agregar** y, a continuación, escriba los siguientes valores: 
    - Nombre: *Modern Workplace-Windows 10 LAN Profile* 
    - Descripción: escriba una descripción que dé información general sobre la configuración y cualquier otro detalle importante. 
    - OMA-URI (distingue mayúsculas de minúsculas): escriba *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de datos: seleccione **String (archivo XML).** 
    - XML personalizado: Upload archivo XML exportado.
2. Envíe una solicitud de soporte técnico Escritorio administrado de Microsoft operaciones de TI mediante el portal de administración de Escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "Modern Workplace Devices : Test". Escritorio administrado de Microsoft Las operaciones de TI le permitirán saber cuándo se completa la solicitud a través de la solicitud de soporte técnico en el portal de administración.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementar certificados y perfil de Wi-Fi/VPN 
 
 
Para implementar certificados y perfiles, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedio (vea [Crear perfiles de certificado de confianza](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AYYY. **Los perfiles de certificado sin fecha de expiración no se implementarán.**
2. Cree un perfil para cada certificado SCEP o PKCS (vea Crear un perfil de certificado [SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) o Crear un perfil de certificado [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AYYY. **Los perfiles de certificado sin fecha de expiración no se implementarán.**
3. Crea un perfil para cada red WiFi corporativa (consulta Configuración de [Wi-Fi para Windows 10 dispositivos posteriores).](/intune/wi-fi-settings-windows)
4. Crea un perfil para cada VPN corporativa (consulta Windows 10 y Windows configuración del dispositivo [Holographic](/intune/vpn-settings-windows-10)para agregar conexiones VPN con Intune ).
5. Envíe una solicitud de soporte técnico titulada "Implementación de certificados" o "Implementación de perfiles Wi-Fi" a las operaciones de TI de Escritorio administrado de Microsoft mediante el portal de administración de Escritorio administrado de Microsoft para revisar e implementar el perfil de configuración en "Dispositivos modernos del lugar de trabajo: prueba". Escritorio administrado de Microsoft Las operaciones de TI le permitirán saber cuándo se ha completado la solicitud a través de la solicitud de soporte técnico en el portal de administración. 
 
## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos para Escritorio administrado de Microsoft](prerequisites.md).
2. Usar [herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para las cuentas de invitado](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar certificados y perfiles de red para Escritorio administrado de Microsoft](certs-wifi-lan.md) (este artículo)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en el Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md) 
