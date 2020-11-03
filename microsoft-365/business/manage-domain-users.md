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
description: Sincronice los usuarios controlados por el dominio con Microsoft 365 para empresas.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841367"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar usuarios del dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. preparar la sincronización de directorios 

Antes de sincronizar los usuarios y los equipos desde el dominio local de Active Directory, consulte [preparar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). En particular:

   - Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail** , **proxyAddresses** y **userPrincipalName** . Estos valores deben ser únicos y se deben quitar todos los duplicados.
   
   - Le recomendamos que configure el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local de manera que coincida con la dirección de correo electrónico principal que corresponda al usuario con licencia de Microsoft 365. Por ejemplo: *Mary.Shelley@contoso.com* en lugar de *Mary@contoso. local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *. local* o *. LAN* , en lugar de un sufijo enrutable de Internet como *. com* o *. org* , ajuste primero el sufijo UPN de las cuentas de usuario locales como se describe en [preparar un dominio no enrutable para la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

La **ejecución de IdFix** en el paso cuatro (4) que se muestra a continuación, también asegurará que su Active Directory local esté listo para la sincronización de directorios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. instalar y configurar Azure AD Connect

Para sincronizar los usuarios, los grupos y los contactos de Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios. 

 1. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **configurar** en el panel de navegación izquierdo.

 2. En **Inicio de sesión y seguridad** , elija **Ver**  en **sincronizar usuarios en el directorio de su organización** .

 3. En la página **sincronizar usuarios desde el directorio de su organización** **, elija introducción** .

 4. En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.

 5. Siga los pasos del Asistente para descargar Azure AD Connect y usarlo para sincronizar los usuarios controlados por dominio a Microsoft 365.


Consulte [configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para obtener más información.

A medida que configure las opciones de Azure AD Connect, le recomendamos que habilite la **sincronización de contraseña** , el **Inicio de sesión único sin problemas** y la característica de **escritura diferida de contraseñas** , que también se admite en Microsoft 365 para empresas.

> [!NOTE]
> Hay algunos pasos adicionales para la escritura diferida de contraseñas más allá de la casilla en Azure AD Connect. Para obtener más información, consulte [How-to: configure password reescritura](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Si también quiere administrar dispositivos Windows 10 Unidos a un dominio, consulte [enable Domain-unirme a Domain Windows 10 Devices to Manage by Microsoft 365 Business Premium](manage-windows-devices.md) para configurar una Unión híbrida de Azure ad. 