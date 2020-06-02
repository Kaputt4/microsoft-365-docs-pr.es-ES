---
title: Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business
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
description: Obtenga información sobre cómo obtener acceso a recursos locales como líneas de aplicaciones empresariales, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 conectado a Azure Active Directory.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471259"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 empresa Premium

Este artículo se aplica a Microsoft 365 empresa Premium.

Cualquier dispositivo de Windows 10 que se haya unido a Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede ser protegido por Microsoft 365 empresa Premium. También puede permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras. Para permitir el acceso, use [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory. 

Para obtener más información, consulte [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Los pasos también se resumen en las secciones siguientes.

> [!IMPORTANT]
> Este procedimiento solo es aplicable a OAuth y NTLM. Kerberos no es compatible.
 
## <a name="run-azure-ad-connect"></a>Ejecutar Azure AD Connect

Complete los siguientes pasos para habilitar los dispositivos de Azure AD Unidos de su organización para que tengan acceso a los recursos locales.
  
1. Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect como se describe en [configurar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
    
2. Una vez completada la sincronización de directorios, asegúrese de que los dispositivos Windows 10 de su organización están Unidos a Azure AD. Este paso se realiza de forma individual en cada dispositivo con Windows 10. Para obtener más información, consulte [configurar dispositivos Windows para los usuarios de Microsoft 365 empresa Premium](set-up-windows-devices.md) . 
    
3. Una vez que se unen los dispositivos de Windows 10, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Business Premium. Todos los dispositivos ahora también tienen acceso a los recursos locales.
    
No se necesitan pasos adicionales para obtener acceso a los recursos locales de los dispositivos Unidos de Azure AD. Esta funcionalidad está integrada en Windows 10. 

Si tiene previsto iniciar sesión en el dispositivo AADJ que no sea el método de contraseña como PIN/bio-Metric mediante credenciales WHFB y, a continuación, obtener acceso a recursos locales (recursos compartidos, impresoras.. etc.), sigahttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Si su organización no está lista para implementarla en la configuración de dispositivos Unidos a Azure AD descrita anteriormente, considere la posibilidad de configurar una [configuración de dispositivo de Unión híbrida de Azure ad](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Consideraciones a la hora de unir dispositivos Windows a Azure AD

Si el dispositivo de Windows al que se unió Azure-AD se unió anteriormente a un dominio o en un grupo de trabajo, tenga en cuenta las siguientes limitaciones:
  
- Cuando se une un dispositivo de Azure AD, se crea un nuevo usuario sin hacer referencia a un perfil existente. Los perfiles deben migrarse de forma manual. Un perfil de usuario contiene información como los favoritos, los archivos locales, la configuración del explorador y la configuración del menú Inicio. Un mejor enfoque es encontrar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.

- Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor de servicios de configuración](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) comparable en Intune. Ejecute la [herramienta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para buscar CSP comparables para los GPO existentes.

- Los usuarios no podrán autenticarse en las aplicaciones que dependen de la autenticación de Active Directory. Evalúe la aplicación heredada y considere la posibilidad de actualizarla a una aplicación que use la autenticación moderna, si es posible.

- La detección de impresoras de Active Directory no funcionará. Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión de nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
