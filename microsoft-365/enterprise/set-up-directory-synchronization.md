---
title: Configurar la sincronización de directorios para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Obtenga información sobre cómo configurar la sincronización de directorios entre Microsoft 365 y su Active Directory local.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924909"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Configurar la sincronización de directorios para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa un inquilino de Azure Active Directory (Azure AD) para almacenar y administrar identidades para autenticación y permisos para obtener acceso a recursos basados en la nube. 

Si tiene un bosque o dominio de Servicios de dominio de Active Directory (AD DS) local, puede sincronizar sus cuentas de usuario, grupos y contactos de AD DS con el inquilino de Azure AD de su suscripción a Microsoft 365. Se trata de una identidad híbrida para Microsoft 365. Estos son sus componentes.

![Componentes de sincronización de directorios para Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect se ejecuta en un servidor local y sincroniza su AD DS con el inquilino de Azure AD. Junto con la sincronización de directorios, también puede especificar estas opciones de autenticación:

- Sincronización de hash de contraseña (PHS)

  Azure AD realiza la autenticación en sí.

- Autenticación de paso a través (PTA)

  Azure AD tiene AD DS para realizar la autenticación.

- Autenticación federada

  Azure AD hace referencia al equipo cliente que solicita la autenticación a otro proveedor de identidades.

Consulte [Identidades híbridas](plan-for-directory-synchronization.md) para obtener más información.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Revisar los requisitos previos de Azure AD Connect

Obtiene una suscripción gratuita de Azure AD con su suscripción a Microsoft 365. Al configurar la sincronización de directorios, instalará Azure AD Connect en uno de los servidores locales.
  
Para Microsoft 365 tendrás que:
  
- Compruebe el dominio local. El Asistente para Azure AD Connect le guiará a través de esto.
- Obtenga los nombres de usuario y las contraseñas de las cuentas de administrador de su inquilino de Microsoft 365 y AD DS.

Para el servidor local en el que instale Azure AD Connect, necesitará:
  
|**Sistema operativo del servidor**|**Otros programas de software**|
|:-----|:-----|
|Windows Server 2012 R2 y versiones posteriores | - PowerShell está instalado de forma predeterminada, no se requiere ninguna acción.  <br> - Net 4.5.1 y versiones posteriores se ofrecen a través de Windows Update. Asegúrate de haber instalado las actualizaciones más recientes de Windows Server en el Panel de control. |
|Windows Server 2008 R2 con Service Pack 1 (SP1)** o Windows Server 2012 | - La versión más reciente de PowerShell está disponible en Windows Management Framework 4.0. Busque en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 y versiones posteriores están disponibles en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | - La última versión compatible de PowerShell está disponible en Windows Management Framework 3.0, disponible en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 y versiones posteriores están disponibles en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Consulte [Requisitos previos](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) de Azure Active Directory Connect para obtener más información sobre los requisitos de hardware, software, cuenta y permisos, los requisitos de certificado SSL y los límites de objetos para Azure AD Connect.
  
También puede revisar el historial de versiones de Azure AD [Connect](/azure/active-directory/hybrid/reference-connect-version-history) para ver lo que se incluye y se ha corregido en cada versión.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Instalar Azure AD Connect y configurar la sincronización de directorios

Antes de comenzar, asegúrese de que tiene:

- Nombre de usuario y contraseña de un administrador global de Microsoft 365
- Nombre de usuario y contraseña de un administrador de dominio de AD DS
- Qué método de autenticación (PHS, PTA, federado)
- Si desea usar el inicio de sesión único sin problemas [(SSO)](/azure/active-directory/hybrid/how-to-connect-sso) de Azure AD

Siga estos pasos:

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) ( y elija Usuarios usuarios activos en la navegación https://admin.microsoft.com)  \>  izquierda.
2. En la **página Usuarios activos,** elija **Más** (tres puntos) Sincronización \> **de directorios**.
  
3. En la **página de preparación de Azure Active Directory,** seleccione el vínculo Ir al Centro de descarga para obtener el vínculo de la herramienta Azure AD **Connect** para empezar. 
4. Siga los pasos descritos en [Azure AD Connect y guía](/azure/active-directory/hybrid/how-to-connect-install-roadmap)básica de instalación de Azure AD Connect Health .

## <a name="3-finish-setting-up-domains"></a>3. Finalizar la configuración de dominios

Siga los pasos de [Crear registros DNS para Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) cuando administre los registros DNS para terminar de configurar los dominios.

## <a name="next-step"></a>Paso siguiente

[Asignar licencias a cuentas de usuario](assign-licenses-to-user-accounts.md)