---
title: Microsoft 365 integración con entornos locales
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: En este artículo, aprenderá a integrar Microsoft 365 con los servicios de directorio y los entornos locales existentes.
ms.openlocfilehash: a3ba75fd2f2b69e71d5b14b14e17827ed96e4dd4
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093907"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 integración con entornos locales

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Puede integrar Microsoft 365 con los servicios de dominio de Active Directory local (AD DS) existentes y con instalaciones locales de Exchange Server, Skype Empresarial Server 2015 o SharePoint Server.
  
 - Al integrar AD DS, puede sincronizar y administrar cuentas de usuario para ambos entornos. También puede agregar sincronización de hash de contraseña (PHS) o inicio de sesión único (SSO) para que los usuarios puedan iniciar sesión en ambos entornos con sus credenciales locales.
 - Cuando se integra con productos de servidor locales, se crea un entorno híbrido. Un entorno híbrido puede ayudarle a migrar usuarios o información a Microsoft 365, o puede seguir teniendo algunos usuarios o información local y otros en la nube. Para obtener más información sobre los entornos híbridos, consulte [Nube híbrida](../solutions/cloud-architecture-models.md#hybrid).

También puede usar los asesores de Azure Active Directory (Azure AD) para obtener instrucciones de configuración personalizadas en el Centro de administración de Microsoft 365 (debe iniciar sesión en Microsoft 365):

- [guía de configuración de Azure AD](https://aka.ms/aadpguidance)
- [Sincronización de usuarios desde el directorio de la organización](https://aka.ms/aadconnectpwsync)
- [Asesor de implementación de Servicios de federación de Active Directory (AD FS) (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Antes de empezar

Antes de integrar Microsoft 365 y un entorno local, también debe realizar el [planeamiento de la red y el ajuste del rendimiento](network-planning-and-performance.md). También querrá comprender los [modelos de identidad](deploy-identity-solution-identity-model.md) disponibles. 

Consulte [Administrar cuentas de Microsoft 365](manage-microsoft-365-accounts.md) para obtener una lista de herramientas que puede usar para administrar cuentas de usuario Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integración de Microsoft 365 con AD DS

Si tiene cuentas de usuario existentes en AD DS, no quiere volver a crear todas esas cuentas en Microsoft 365 y corre el riesgo de introducir diferencias o errores entre los entornos. La sincronización de directorios le ayuda a reflejar esas cuentas entre los entornos locales y en línea. Con la sincronización de directorios, los usuarios no tienen que recordar información nueva para cada entorno y no es necesario crear o actualizar cuentas dos veces. Tendrá que preparar el [directorio local](prepare-for-directory-synchronization.md) para la sincronización de directorios.
  
![Use la sincronización de directorios para mantener sincronizada la información de la cuenta de usuario local y en línea.](../media/microsoft-365-integration/directory-synchronization.png)
  
Si desea que los usuarios puedan iniciar sesión en Microsoft 365 con sus credenciales locales, también puede configurar el inicio de sesión único. Con el inicio de sesión único, Microsoft 365 está configurado para confiar en el entorno local para la autenticación de usuarios.
  
![Con el inicio de sesión único, la misma cuenta está disponible en los entornos locales y en línea.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronización de directorios con o sin sincronización de hash de contraseña o autenticación de paso a través (PTA)

Un usuario inicia sesión en su entorno local con su cuenta de usuario (dominio\nombre de usuario). Cuando van a Microsoft 365, deben iniciar sesión de nuevo con su cuenta profesional o educativa (user@domain.com). El nombre de usuario es el mismo en ambos entornos. Al agregar PHS o PTA, el usuario tiene la misma contraseña para ambos entornos, pero tendrá que proporcionar esas credenciales de nuevo al iniciar sesión en Microsoft 365. La sincronización de directorios con PHS es la sincronización de directorios más usada.

Para configurar la sincronización de directorios, use Azure AD Conectar. Para obtener instrucciones, consulte [Configuración de la sincronización de directorios para Microsoft 365](set-up-directory-synchronization.md) y [Azure AD Conectar con configuración rápida](/azure/active-directory/hybrid/how-to-connect-install-express).

Obtenga más información sobre [cómo preparar la sincronización de directorios para Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Sincronización de directorios con SSO

Un usuario inicia sesión en su entorno local con su cuenta de usuario. Cuando van a Microsoft 365, inician sesión automáticamente o inician sesión con las mismas credenciales que usan para su entorno local (dominio\nombre de usuario).

Para configurar el inicio de sesión único, use también Azure AD Conectar. Para obtener instrucciones, consulte [Instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).

Para obtener más información, consulte [Inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Conectar reemplaza las versiones anteriores de las herramientas de integración de identidades, como DirSync y Sincronización de Azure AD. Si desea actualizar de Azure Active Directory Sync a Azure AD Conectar, consulte [las instrucciones de actualización](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started). 

## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)