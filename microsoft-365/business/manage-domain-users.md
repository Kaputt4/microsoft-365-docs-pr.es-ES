---
title: Sincronizar usuarios del dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronizar usuarios controlados por dominio con Microsoft 365 para empresas.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841367"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar usuarios del dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparar la sincronización de directorios 

Antes de sincronizar los usuarios y equipos desde el dominio local de Active Directory, revise Preparar la sincronización de directorios [con Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). En particular:

   - Asegúrese de que no existen duplicados en el directorio para los atributos siguientes: **mail**, **proxyAddresses** y **userPrincipalName**. Estos valores deben ser únicos y se deben quitar los duplicados.
   
   - Se recomienda configurar el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local para que coincida con la dirección de correo electrónico principal que corresponde al usuario de Microsoft 365 con licencia. Por ejemplo: *mary.shelley@contoso.com* en lugar *de mary@contoso.local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *.local* o *.lan*, en lugar de un sufijo enrutable de Internet como *.com* o *.org,* ajuste primero el sufijo UPN de las cuentas de usuario local tal como se describe en Preparar un dominio no enrutable para la sincronización de directorios. [](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization) 

La **ejecución de IdFix en** el paso cuatro (4) siguiente, también se asegura de que su Active Directory local está listo para la sincronización de directorios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalar y configurar Azure AD Connect

Para sincronizar los usuarios, grupos y contactos del Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios. 

 1. En el [Centro de administración,](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleccione **Configurar** en el panel de navegación izquierdo.

 2. En **Inicio de sesión y seguridad,** elija **Ver** en Sincronizar usuarios del directorio de **su organización.**

 3. En la **página Sincronizar usuarios de la página del directorio** de su organización, elija **Introducción.**

 4. En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.

 5. Siga los pasos del asistente para descargar Azure AD Connect y usarlo para sincronizar los usuarios controlados por el dominio con Microsoft 365.


Consulte [Configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para obtener más información.

A medida que configure las opciones de Azure AD Connect, le recomendamos  que habilite la sincronización de contraseñas, el inicio de sesión único sin problemas y la característica de escritura escritura por contraseña, que también es compatible con Microsoft 365 para empresas.

> [!NOTE]
> Hay algunos pasos adicionales para la reescribición de contraseñas más allá de la casilla en Azure AD Connect. Para obtener más información, vea [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Si también quieres administrar dispositivos Windows 10 unidos a un dominio, consulta Habilitar dispositivos Windows 10 unidos a un dominio para que Microsoft [365 Empresa Premium](manage-windows-devices.md) administre para configurar una unión híbrida de Azure AD. 