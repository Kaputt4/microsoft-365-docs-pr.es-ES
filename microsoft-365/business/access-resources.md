---
title: Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Obtenga información sobre cómo obtener acceso a recursos locales como líneas de aplicaciones empresariales, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 conectado a Azure Active Directory.
ms.openlocfilehash: fa3cf640e799feb81ff08c5b7b81d57f707e0152
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072038"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business

Cualquier dispositivo de Windows 10 que se haya unido a Azure Active Directory tendrá acceso a todos los recursos basados en la nube, como las aplicaciones de Office 365 y puede ser protegido por Microsoft 365 Business. Para permitir también el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras, debe sincronizar su Active Directory local con Azure Active Directory mediante [Azure ad Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Consulte [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para obtener más información. 
  
## <a name="run-azure-ad-connect"></a>Ejecutar Azure AD Connect

Complete los siguientes pasos para habilitar los dispositivos de Azure AD Unidos de su organización para que tengan acceso a los recursos locales.
  
1. Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect como se describe en [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Una vez completada la sincronización de directorios, asegúrese de que los dispositivos Windows 10 de su organización están Unidos a Azure AD. Este paso se realiza de forma individual en cada dispositivo con Windows 10. Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para obtener más información. 
    
3. Una vez que se unen los dispositivos Windows 10, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Business. Todos los dispositivos ahora tendrán acceso también a los recursos locales.
    
No se necesitan pasos adicionales para obtener acceso a recursos locales para dispositivos Unidos de Azure AD. Esta es la funcionalidad integrada disponible en Windows 10. 
  
Si su organización no está lista para implementarse en la configuración de dispositivos Unidos a Azure AD descrita anteriormente, considere la posibilidad de configurar una [configuración de dispositivo de Unión híbrida de Azure ad](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Consideraciones al unir los dispositivos Windows a Azure AD

Si Azure AD se une a un dispositivo de Windows que anteriormente se unió a un dominio o está en un grupo de trabajo, debe tener en cuenta las siguientes limitaciones:
  
- Cuando se une un dispositivo de Azure AD, se crea un nuevo usuario sin hacer referencia a un perfil existente. Para solucionarlo, los perfiles deben migrarse de forma manual. Un perfil de usuario contiene información como los favoritos, los archivos locales, la configuración del explorador, la configuración del menú Inicio, etc. Un enfoque mejor es encontrar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil

- Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor de servicios de configuración](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) comparable en Intune. Ejecute la [herramienta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para buscar CSP comparables para los GPO existentes.

- Los usuarios no podrán autenticarse en las aplicaciones que dependen de la autenticación de Active Directory. Para solucionar este error, evalúe usando una aplicación heredada y considere la posibilidad de actualizar a una aplicación que use la autenticación moderna, si es posible.

- La detección de impresoras de Active Directory no funcionará. Para solucionarlo, proporcione rutas de impresora directas para todos los usuarios o aproveche [la impresión de nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
