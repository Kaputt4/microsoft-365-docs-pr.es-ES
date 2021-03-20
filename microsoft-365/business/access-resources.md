---
title: Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa
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
description: Obtén información sobre cómo obtener acceso a recursos locales como aplicaciones de línea de negocio, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 unido a Azure Active Directory.
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913530"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa Premium

Este artículo se aplica a Microsoft 365 Empresa Premium.

Cualquier dispositivo con Windows 10 unido a Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede protegerse con Microsoft 365 Empresa Premium. También puedes permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras. Para permitir el acceso, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory. 

Para obtener más información, vea [Introducción a la administración de dispositivos en Azure Active Directory](/azure/active-directory/device-management-introduction).
Los pasos también se resumen en las secciones siguientes.
 
## <a name="run-azure-ad-connect"></a>Ejecutar Azure AD Connect

Siga estos pasos para permitir que los dispositivos unidos a Azure AD de la organización puedan tener acceso a los recursos locales.
  
1. Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect como se describe en Configurar la sincronización de directorios [para Office 365](../enterprise/set-up-directory-synchronization.md).
    
2. Una vez completada la sincronización de directorios, asegúrate de que los dispositivos windows 10 de la organización estén unidos a Azure AD. Este paso se realiza individualmente en cada dispositivo Windows 10. Consulta [Configurar dispositivos Windows para usuarios de Microsoft 365 Empresa Premium](set-up-windows-devices.md) para obtener más información. 
    
3. Una vez que los dispositivos Windows 10 estén unidos a Azure AD, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Empresa Premium. Todos los dispositivos ahora también tienen acceso a recursos locales.
    
No se requieren pasos adicionales para obtener acceso a recursos locales para dispositivos unidos a Azure AD. Esta funcionalidad está integrada en Windows 10. 

Si tiene planes de iniciar sesión en el dispositivo AADJ que no sea el método de contraseña Como PIN/Biométrica a través del inicio de sesión de credenciales WHFB y, a continuación, acceder a recursos locales (recursos compartidos, impresoras). etc.), por favor siga https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Si su organización no está lista para implementar en la configuración de dispositivo unido a Azure AD descrita anteriormente, considere la posibilidad de configurar la configuración de dispositivo unido a [Azure AD híbrido.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Consideraciones al unir dispositivos Windows a Azure AD

Si el dispositivo Windows al que se unió Azure-AD estaba previamente unido a un dominio o en un grupo de trabajo, tenga en cuenta las siguientes limitaciones:
  
- Cuando un dispositivo se une a Azure AD, crea un nuevo usuario sin hacer referencia a un perfil existente. Los perfiles deben migrarse manualmente. Un perfil de usuario contiene información como favoritos, archivos locales, configuración del explorador y configuración del menú Inicio. El mejor enfoque es buscar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.

- Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) de servicios de configuración (CSP) comparable en Intune. Ejecute la [herramienta MMAT para](https://www.microsoft.com/download/details.aspx?id=45520) buscar LOSP comparables para los GPO existentes.

- Es posible que los usuarios no puedan autenticarse en aplicaciones que dependen de la autenticación de Active Directory. Evalúa la aplicación heredada y considera la posibilidad de actualizar a una aplicación que usa Auth moderno, si es posible.

- La detección de impresoras de Active Directory no funcionará. Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión universal](/universal-print/).