---
title: Configuración de la sincronización de directorios para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Obtenga información sobre cómo configurar la sincronización de directorios entre Microsoft 365 y el Active Directory local.
ms.openlocfilehash: 18657dca2b41b0fa003b1c3cd5c24656c856af43
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207586"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Configuración de la sincronización de directorios para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa un inquilino de Azure Active Directory (Azure AD) para almacenar y administrar identidades para la autenticación y permisos para acceder a recursos basados en la nube. 

Si tiene un dominio o bosque de Active Directory local Domain Services (AD DS), puede sincronizar las cuentas de usuario, grupos y contactos de AD DS con el inquilino de Azure AD de su suscripción de Microsoft 365. Se trata de una identidad híbrida para Microsoft 365. Estos son sus componentes.

![Componentes de la sincronización de directorios para Microsoft 365.](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect se ejecuta en un servidor local y sincroniza AD DS con el inquilino de Azure AD. Junto con la sincronización de directorios, también puede especificar estas opciones de autenticación:

- Sincronización del hash de la contraseña (PHS)

  Azure AD realiza la autenticación en sí.

- Autenticación de paso a través (PTA)

  Azure AD hace que AD DS realice la autenticación.

- Autenticación federada

  Azure AD hace referencia al equipo cliente que solicita la autenticación a otro proveedor de identidades.

Consulte [Identidades híbridas](plan-for-directory-synchronization.md) para obtener más información.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Revisión de los requisitos previos para Azure AD Connect

Obtendrá una suscripción gratuita a Azure AD con su suscripción a Microsoft 365. Al configurar la sincronización de directorios, instalará Azure AD Connect en uno de los servidores locales.
  
Para Microsoft 365, deberá hacer lo siguiente:
  
- Compruebe el dominio local. El asistente de Azure AD Connect le guía a través de esto.
- Obtenga los nombres de usuario y las contraseñas de las cuentas de administrador de su inquilino de Microsoft 365 y AD DS.

Para el servidor local en el que instala Azure AD Connect, necesitará lo siguiente:
  
|**Sistema operativo del servidor**|**Otros programas de software**|
|:-----|:-----|
|Windows Server 2012 R2 y versiones posteriores | - PowerShell está instalado de forma predeterminada, no se requiere ninguna acción.  <br> - Net 4.5.1 y versiones posteriores se ofrecen a través de Windows Update. Asegúrese de que ha instalado las actualizaciones más recientes de Windows Server en el Panel de control. |
|Windows Server 2008 R2 con Service Pack 1 (SP1)** o Windows Server 2012 | - La versión más reciente de PowerShell está disponible en Windows Management Framework 4.0. Búscálo en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 y versiones posteriores están disponibles en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | - La versión compatible más reciente de PowerShell está disponible en Windows Management Framework 3.0, disponible en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 y versiones posteriores están disponibles en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Consulte [Requisitos previos de Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) para obtener los detalles de los requisitos de hardware, software, cuenta y permisos, requisitos de certificados SSL y límites de objetos para Azure AD Connect.
  
También puede revisar el [historial de versiones](/azure/active-directory/hybrid/reference-connect-version-history) de Azure AD Connect para ver lo que se incluye y se ha corregido en cada versión.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Instalación de Azure AD Connect y configuración de la sincronización de directorios

Antes de empezar, asegúrese de que tiene lo siguiente:

- Nombre de usuario y contraseña de un administrador global de Microsoft 365
- Nombre de usuario y contraseña de un administrador de dominio de AD DS
- Qué método de autenticación (PHS, PTA, federado)
- Si desea usar el [inicio de sesión único (SSO) de conexión directa de Azure AD](/azure/active-directory/hybrid/how-to-connect-sso)

Siga estos pasos:

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) (https://admin.microsoft.com) y elija **Usuarios** \> **usuarios activos** en el panel de navegación izquierdo.
2. En la página **Usuarios activos** , elija **Más** (tres puntos) \> **Sincronización de directorios**.
  
3. En la página de **preparación de Azure Active Directory** , seleccione el vínculo **Ir al centro de descarga para obtener el vínculo de la herramienta Azure AD Connect** para empezar. 
4. Siga los pasos descritos en El plan de [instalación de Azure AD Connect y Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Finalizar la configuración de dominios

Siga los pasos descritos en [Creación de registros DNS para Microsoft 365 cuando administre los registros DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) para finalizar la configuración de los dominios.

## <a name="next-step"></a>Paso siguiente

[Asignar licencias a cuentas de usuario](assign-licenses-to-user-accounts.md)