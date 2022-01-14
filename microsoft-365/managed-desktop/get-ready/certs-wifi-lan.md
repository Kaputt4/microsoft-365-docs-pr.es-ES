---
title: Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft
description: Requisitos de certificado y conectividad wi-fi
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 69cea241c81130fdee2ae734c372981e0349ab64
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035599"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft  
 
La autenticación basada en certificados es un requisito común para los clientes que usan Escritorio administrado de Microsoft. Es posible que necesite certificados para obtener acceso a Wi-Fi o LAN, para conectarse a soluciones VPN o para obtener acceso a recursos internos de la organización.   
 
Dado que los dispositivos de Escritorio administrado de Microsoft se unen a Azure Active Directory (Azure AD) y se administran mediante Microsoft Intune, debe implementar dichos certificados mediante una infraestructura de certificados del Protocolo simple de inscripción de certificados (SCEP) o una infraestructura de certificado estándar de criptografía de clave pública (PKCS) integrada con Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de certificado 
 
Los certificados raíz son necesarios para implementar certificados a través de una infraestructura SCEP o PKCS. Es posible que otras aplicaciones y servicios de la organización requieran la implementación de certificados raíz en los dispositivos de Escritorio administrado de Microsoft.    
 
Antes de implementar certificados SCEP o PKCS en Microsoft Managed Desktop, debe recopilar requisitos para cada servicio que requiera un certificado de usuario o dispositivo en su organización. Para facilitar esta actividad, puede usar una de las siguientes plantillas de planeación:  
 
- [Plantilla de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Plantilla de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi de conectividad

Para permitir que un dispositivo se proporciona automáticamente con la configuración Wi-Fi configuración necesaria para la red de empresa, es posible que necesites un Wi-Fi de configuración. Puede configurar Microsoft Managed Desktop para implementar estos perfiles en sus dispositivos. Si la seguridad de red requiere que los dispositivos sean parte del dominio local, es posible que también deba evaluar la infraestructura de red de Wi-Fi para asegurarse de que es compatible con dispositivos de Escritorio administrado de Microsoft (los dispositivos de Escritorio administrado de Microsoft Azure AD están unidos únicamente). 
 
Antes de implementar una configuración Wi-Fi en dispositivos de Escritorio administrado de Microsoft, tendrá que recopilar los requisitos de su organización para cada Wi-Fi red. Para facilitar esta actividad, puede usar esta plantilla [de perfil de WiFi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividad por cable y autenticación 802.1x 
 
Si usa la autenticación 802.1x para proteger el acceso desde dispositivos a la red de área local (LAN), deberá insertar los detalles de configuración necesarios en los dispositivos de Escritorio administrado de Microsoft. Los dispositivos de Escritorio administrado de Microsoft que Windows 10, versión 1809 o posterior admiten la implementación de una configuración 802.1x a través del proveedor de servicios de configuración WiredNetwork (CSP). Para obtener más información, consulte [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation. 
 
Antes de implementar un perfil de configuración de red por cable en dispositivos de Escritorio administrado de Microsoft, recopile los requisitos de su organización para la red corporativa cableada. Para hacerlo, siga estos pasos: 
 
 
1. Inicie sesión en un dispositivo que tenga configurado el perfil 802.1x existente y esté conectado a la red LAN.  
2. Abra un símbolo del sistema con credenciales administrativas. 
3. Para buscar el nombre de la interfaz LAN, ejecute **netsh interface show interface**. 
4. Exporte el XML de perfil DE LAN ejecutando **netsh lan export profile folder=.  Interface="interface_name"**. 
5. Si necesita probar el perfil exportado en el dispositivo de Escritorio administrado de Microsoft, ejecute **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implementar infraestructura de certificados  
 
Si ya tiene una infraestructura SCEP o PKCS existente con Intune y este enfoque cumple sus requisitos, también puede usarlo para Microsoft Managed Desktop. Si ya no existe ninguna infraestructura SCEP o PKCS, tendrá que preparar una.  
 
Para obtener más información, consulte [Configuración de un perfil de certificado para sus dispositivos en Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implementar un perfil de LAN 
 
Una vez exportado el perfil de LAN, puede preparar la directiva para Microsoft Managed Desktop siguiendo estos pasos:   
 
1. Cree un perfil personalizado en Microsoft Intune para el perfil de LAN con la siguiente configuración (vea Usar la configuración personalizada para [Windows 10 dispositivos en Intune](/intune/custom-settings-windows-10)). En **Custom OMA-URI Configuración**, seleccione **Agregar** y, a continuación, escriba los siguientes valores: 
    - Nombre: *Modern Workplace-Windows 10 LAN Profile* 
    - Descripción: escriba una descripción con información general sobre la configuración y otros detalles importantes. 
    - OMA-URI (distingue mayúsculas de minúsculas): escriba *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de datos: seleccione **String (archivo XML).** 
    - XML personalizado: Upload archivo XML exportado.
2. Asignar el perfil personalizado al grupo *Dispositivos modernos del lugar de trabajo: prueba.*
3. Realiza las pruebas que sientas necesarias con un dispositivo que se encuentra en el grupo De prueba de implementación. Si se realiza correctamente, asigne el perfil personalizado a los grupos Dispositivos modernos del lugar de trabajo (en primer *lugar,* Dispositivos modernos del lugar de trabajo – Dispositivos rápidos y dispositivos modernos del lugar *de trabajo).*
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementar certificados y perfil de Wi-Fi/VPN 
 
 
Para implementar certificados y perfiles, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedio (vea [Crear perfiles de certificado de confianza](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AYYY. **Los perfiles de certificado deben tener una fecha de expiración.**
2. Cree un perfil para cada certificado SCEP o PKCS (vea Crear un perfil de certificado [SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) o Crear un perfil de certificado [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AYYY. **Los perfiles de certificado deben tener una fecha de expiración.**
3. Crea un perfil para cada red WiFi corporativa (consulta Configuración de [Wi-Fi para Windows 10 dispositivos posteriores).](/intune/wi-fi-settings-windows)
4. Crea un perfil para cada VPN corporativa (consulta Windows 10 y Windows configuración del dispositivo [Holographic](/intune/vpn-settings-windows-10)para agregar conexiones VPN con Intune ).
5. Asignar los perfiles al grupo *Dispositivos modernos del lugar de trabajo: prueba.*
6. Realiza las pruebas que sientas necesarias con un dispositivo que se encuentra en el grupo De prueba de implementación. Si se realiza correctamente, asigne el perfil personalizado a los grupos Dispositivos modernos del lugar de trabajo (en primer *lugar,* Dispositivos modernos del lugar de trabajo – Dispositivos rápidos y dispositivos modernos del lugar *de trabajo).*

 
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. Preparar certificados y perfiles de red (este artículo).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
