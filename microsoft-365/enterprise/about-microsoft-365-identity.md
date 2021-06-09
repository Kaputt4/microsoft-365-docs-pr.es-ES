---
title: Microsoft 365 modelos de identidad y Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Obtenga información sobre cómo administrar el servicio de identidad de usuario de Azure AD en Microsoft 365 modelos de identidad híbrida o solo en la nube.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905709"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 modelos de identidad y Azure Active Directory

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa Azure Active Directory (Azure AD), un servicio de autenticación y identidad de usuario basado en la nube que se incluye con la suscripción Microsoft 365, para administrar identidades y autenticación para Microsoft 365. La configuración correcta de la infraestructura de identidad es fundamental para administrar Microsoft 365 acceso de usuario y permisos para la organización.

Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

La primera opción de planeación es Microsoft 365 de identidad.

## <a name="microsoft-365-identity-models"></a>Microsoft 365 de identidad

Para planear las cuentas de usuario, primero debe comprender los dos modelos de identidad en Microsoft 365. Puede mantener las identidades de su organización solo en la nube, o puede mantener sus identidades locales de Servicios de dominio de Active Directory (AD DS) y usarlas para la autenticación cuando los usuarios tienen acceso Microsoft 365 servicios en la nube.  

Estos son los dos tipos de identidad y su mejor ajuste y ventajas.

| Atributo | Identidad solo de nube | Identidad híbrida |
|:-------|:-----|:-----|
| **Definición** | La cuenta de usuario solo existe en el inquilino de Azure AD para su Microsoft 365 suscripción. | La cuenta de usuario existe en AD DS y también hay una copia en el inquilino de Azure AD para su Microsoft 365 suscripción. La cuenta de usuario de Azure AD también puede incluir una versión hash de la contraseña de la cuenta de usuario de AD DS ya hash. |
| **Cómo Microsoft 365 autentica las credenciales de usuario** | El inquilino de Azure AD para la suscripción Microsoft 365 realiza la autenticación con la cuenta de identidad de la nube. | El inquilino de Azure AD para la suscripción Microsoft 365 administra el proceso de autenticación o redirige al usuario a otro proveedor de identidades. |
| **Ideal para** | Organizaciones que no tienen o necesitan un AD DS local. | Organizaciones que usan AD DS u otro proveedor de identidades. |
| **Mayor beneficio** | Fácil de usar. No se requieren servidores ni herramientas de directorio adicionales. | Los usuarios pueden usar las mismas credenciales al obtener acceso a recursos locales o basados en la nube. |
||||

## <a name="cloud-only-identity"></a>Identidad solo de nube

Una identidad solo en la nube usa cuentas de usuario que solo existen en Azure AD. La identidad de solo nube suele ser usada por organizaciones pequeñas que no tienen servidores locales o que no usan AD DS para administrar identidades locales. 

Estos son los componentes básicos de la identidad de solo nube.
 
![Componentes básicos de identidad de solo nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

Tanto los usuarios locales como los remotos (en línea) usan sus cuentas de usuario y contraseñas de Azure AD para acceder a Microsoft 365 servicios en la nube. Azure AD autentica las credenciales de usuario en función de sus cuentas de usuario y contraseñas almacenadas.

### <a name="administration"></a>Administración
Dado que las cuentas de usuario solo se almacenan en [](../admin/add-users/index.yml) Azure AD, se administran identidades en la nube con herramientas como el centro de administración de Microsoft 365 y [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md). 

## <a name="hybrid-identity"></a>Identidad híbrida

La identidad híbrida usa cuentas que se originan en un AD DS local y tienen una copia en el inquilino de Azure AD de una Microsoft 365 suscripción. Sin embargo, la mayoría de los cambios solo fluyen de un modo. Los cambios realizados en cuentas de usuario de AD DS se sincronizan con su copia en Azure AD. Pero los cambios realizados en cuentas basadas en la nube en Azure AD, como las cuentas de usuario nuevas, no se sincronizan con AD DS.

Azure AD Conectar proporciona la sincronización de cuentas en curso. Se ejecuta en un servidor local, comprueba si hay cambios en AD DS y reenvía esos cambios a Azure AD. Azure AD Conectar permite filtrar qué cuentas están sincronizadas y si se sincroniza una versión hash de contraseñas de usuario, conocida como sincronización de hash de contraseña (PHS).

Al implementar la identidad híbrida, su AD DS local es el origen autoritativo para la información de la cuenta. Esto significa que realiza tareas de administración principalmente locales, que luego se sincronizan con Azure AD. 

Estos son los componentes de la identidad híbrida.

![Componentes de identidad híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

El inquilino de Azure AD tiene una copia de las cuentas de AD DS. En esta configuración, los usuarios locales y remotos que acceden a Microsoft 365 servicios en la nube se autentican en Azure AD.

>[!Note]
>Siempre debe usar Azure AD Conectar para sincronizar cuentas de usuario para la identidad híbrida. Necesita las cuentas de usuario sincronizadas en Azure AD para realizar la asignación de licencias y la administración de grupos, configurar permisos y otras tareas administrativas que impliquen cuentas de usuario.
>

### <a name="administration"></a>Administración

Dado que las cuentas de usuario originales y autoritativa se almacenan en el AD DS local, administra las identidades con las mismas herramientas que administra ad DS. 

No use el Centro de administración Microsoft 365 o PowerShell para Microsoft 365 administrar cuentas de usuario sincronizadas en Azure AD.

## <a name="next-step"></a>Paso siguiente

Si necesita el modelo de identidad solo en la nube, consulte [Cloud-only identity](cloud-only-identities.md).

Si necesita el modelo de identidad híbrida, vea [Identidad híbrida](plan-for-directory-synchronization.md).


## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)