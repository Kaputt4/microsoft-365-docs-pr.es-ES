---
title: Acceder a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Aprende a obtener acceso a recursos locales como aplicaciones de línea de negocio, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 unido a Azure Active Directory.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233848"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Acceder a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa Premium

Este artículo se aplica a Microsoft 365 Empresa Premium.

Cualquier dispositivo con Windows 10 unido a Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede estar protegido por Microsoft 365 Empresa Premium. También puede permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras. Para permitir el acceso, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory. 

Para obtener más información, consulte [Introducción a la administración de dispositivos en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)
Los pasos también se resumen en las secciones siguientes.
 
## <a name="run-azure-ad-connect"></a>Ejecutar Azure AD Connect

Complete los siguientes pasos para permitir que los dispositivos unidos a Azure AD de su organización accedan a los recursos locales.
  
1. Para sincronizar los usuarios, grupos y contactos de Active Directory local con Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect, como se describe en Configurar la sincronización de directorios para [Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
    
2. Una vez completada la sincronización de directorios, asegúrate de que los dispositivos windows 10 de tu organización estén unidos a Azure AD. Este paso se realiza individualmente en cada dispositivo Windows 10. Consulte [Configurar dispositivos Windows para los usuarios de Microsoft 365 Empresa Premium](set-up-windows-devices.md) para obtener más información. 
    
3. Una vez que los dispositivos Windows 10 están unidos a Azure AD, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Empresa Premium. Ahora, todos los dispositivos también tienen acceso a los recursos locales.
    
No se requieren pasos adicionales para obtener acceso a recursos locales para dispositivos unidos a Azure AD. Esta funcionalidad está integrada en Windows 10. 

Si tienes previsto iniciar sesión en el dispositivo AADJ que no sea el método de contraseña, como PIN/Biométrica a través del inicio de sesión de credenciales WHFB y luego acceder a recursos locales (recursos compartidos, impresoras). etc.), siga https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Si su organización no está lista para implementar en la configuración de dispositivo unido a Azure AD descrita anteriormente, considere la posibilidad de configurar la configuración de dispositivos unidos a [Azure AD híbridos.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Consideraciones al unir dispositivos Windows a Azure AD

Si el dispositivo Windows al que te uniste a Azure-AD estaba previamente unido a un dominio o a un grupo de trabajo, ten en cuenta las siguientes limitaciones:
  
- Cuando un dispositivo se une a Azure AD, crea un nuevo usuario sin hacer referencia a un perfil existente. Los perfiles deben migrarse manualmente. Un perfil de usuario contiene información como favoritos, archivos locales, configuración del explorador y configuración del menú Inicio. Un mejor enfoque es buscar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.

- Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un proveedor de servicios de configuración [(CSP)](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparable en Intune. Ejecute la [herramienta MMAT para](https://www.microsoft.com/download/details.aspx?id=45520) buscar CSP comparables para GPO existentes.

- Es posible que los usuarios no puedan autenticarse en aplicaciones que dependen de la autenticación de Active Directory. Evalúa la aplicación heredada y considera la posibilidad de actualizar a una aplicación que use la autenticación moderna, si es posible.

- La detección de impresoras de Active Directory no funcionará. Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión universal.](https://aka.ms/UPDocs)
