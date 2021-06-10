---
title: Microsoft 365 integración con entornos locales
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: En este artículo, obtenga información sobre cómo integrar Microsoft 365 con los servicios de directorio existentes y los entornos locales.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923971"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 integración con entornos locales

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede integrar Microsoft 365 con los servicios de dominio de Active Directory (AD DS) locales existentes y con instalaciones locales de Exchange Server, Skype Empresarial Server 2015 o SharePoint Server.
  
 - Al integrar AD DS, puedes sincronizar y administrar cuentas de usuario para ambos entornos. También puede agregar sincronización de hash de contraseña (PHS) o inicio de sesión único (SSO) para que los usuarios puedan iniciar sesión en ambos entornos con sus credenciales locales.
 - Cuando se integra con productos de servidor locales, se crea un entorno híbrido. Un entorno híbrido puede ayudar a migrar usuarios o información a Microsoft 365, o puede seguir teniendo algunos usuarios o información local y otras en la nube. Para obtener más información acerca de los entornos híbridos, vea [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).

También puede usar los asesores de Azure Active Directory (Azure AD) para obtener instrucciones de configuración personalizadas en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):

- [Guía de configuración de Azure AD](https://aka.ms/aadpguidance)
- [Sincronizar usuarios desde el directorio de la organización](https://aka.ms/aadconnectpwsync)
- [Asesor de implementación de Servicios de federación de Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Antes de empezar

Antes de integrar Microsoft 365 y un entorno local, también debe realizar la planeación de red y [el ajuste del rendimiento](network-planning-and-performance.md). También querrá comprender los modelos de [identidad disponibles.](about-microsoft-365-identity.md) 

Consulta [administrar Microsoft 365 cuentas de usuario](manage-microsoft-365-accounts.md) para obtener una lista de herramientas que puedes usar para administrar Microsoft 365 cuentas de usuario. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrar Microsoft 365 con AD DS

Si tienes cuentas de usuario existentes en AD DS, no quieres volver a crear todas esas cuentas en Microsoft 365 y te arriesgas a introducir diferencias o errores entre los entornos. La sincronización de directorios le ayuda a reflejar esas cuentas entre sus entornos locales y en línea. Con la sincronización de directorios, los usuarios no tienen que recordar información nueva para cada entorno y no tiene que crear o actualizar cuentas dos veces. Deberá preparar el [directorio local](prepare-for-directory-synchronization.md) para la sincronización de directorios.
  
![Usar la sincronización de directorios para mantener sincronizada la información de cuenta de usuario local y en línea](../media/microsoft-365-integration/directory-synchronization.png)
  
Si desea que los usuarios puedan iniciar sesión en Microsoft 365 con sus credenciales locales, también puede configurar SSO. Con SSO, Microsoft 365 está configurado para confiar en el entorno local para la autenticación de usuario.
  
![Con el inicio de sesión único, la misma cuenta está disponible en los entornos locales y en línea](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronización de directorios con o sin sincronización de hash de contraseña o autenticación de paso a través (PTA)

Un usuario inicia sesión en su entorno local con su cuenta de usuario (dominio\nombredeusuario). Cuando vayan a Microsoft 365, deben iniciar sesión de nuevo con su cuenta laboral o educativa (user@domain.com). El nombre de usuario es el mismo en ambos entornos. Al agregar PHS o PTA, el usuario tiene la misma contraseña para ambos entornos, pero tendrá que proporcionar esas credenciales de nuevo al iniciar sesión en Microsoft 365. La sincronización de directorios con PHS es la sincronización de directorios más usada.

Para configurar la sincronización de directorios, usa Azure AD Conectar. Para obtener instrucciones, consulte [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and Azure AD Conectar with express [settings](/azure/active-directory/hybrid/how-to-connect-install-express).

Obtenga más información [sobre cómo preparar la sincronización de directorios Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Sincronización de directorios con SSO

Un usuario inicia sesión en su entorno local con su cuenta de usuario. Cuando van a Microsoft 365, inician sesión automáticamente o inician sesión con las mismas credenciales que usan para su entorno local (dominio\nombredeusuario).

Para configurar SSO, también usa Azure AD Conectar. Para obtener instrucciones, [consulte Instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).

Para obtener más información, [vea single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Conectar versiones anteriores de herramientas de integración de identidades, como DirSync y Sincronización de Azure AD. Si desea actualizar desde la sincronización Azure Active Directory a Azure AD Conectar, consulte [las instrucciones de actualización](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started). 

## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)