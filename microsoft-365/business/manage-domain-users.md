---
title: Sincronizar usuarios del dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578415"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar usuarios del dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparar la sincronización de directorios 

Antes de sincronizar los usuarios y equipos desde el dominio local de Active Directory, revise Preparar la sincronización de directorios [para Microsoft 365](../enterprise/prepare-for-directory-synchronization.md). En particular:

   - Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses** y **userPrincipalName**. Estos valores deben ser únicos y los duplicados deben quitarse.
   
   - Se recomienda configurar el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local para que coincida con la dirección de correo electrónico principal que corresponde al usuario Microsoft 365 licencia. Por ejemplo: *mary.shelley@contoso.com* en lugar *de mary@contoso.local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *.local* o *.lan*, en lugar de un sufijo enrutable de Internet como *.com* u *.org*, ajuste primero el sufijo UPN de las cuentas de usuario locales como se describe en Preparar un dominio no enrutable para la sincronización de directorios . [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

Run **IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalar y configurar Azure AD Conectar

Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, instale Azure Active Directory Conectar y configure la sincronización de directorios. 

 1. En el [Centro de administración,](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleccione **Configurar** en la navegación izquierda.

 2. En **Inicio de sesión y seguridad,** elija Ver **en** Sincronizar usuarios del directorio de **su organización.**

 3. En la página Sincronizar usuarios del directorio de la **organización,** elija **Introducción.**

 4. En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.

 5. Siga los pasos del asistente para descargar Azure AD Conectar y usarlo para sincronizar los usuarios controlados por el dominio para Microsoft 365.


Consulte [Configurar la sincronización de directorios Microsoft 365](../enterprise/set-up-directory-synchronization.md) para obtener más información.

Al configurar las opciones de Azure AD Conectar, se recomienda habilitar la sincronización de  **contraseñas,** el inicio de sesión único sin problemas y la característica de escritura de contraseña, que también se admite en Microsoft 365 para empresas.

> [!NOTE]
> Hay algunos pasos adicionales para la reescribición de contraseñas más allá de la casilla en Azure AD Conectar. Para obtener más información, vea [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback). 

Si también quieres administrar dispositivos Windows 10 unidos a un dominio, consulta Habilitar dispositivos de Windows 10 unidos [a](manage-windows-devices.md) un dominio para que los administre Microsoft 365 Empresa Premium para configurar una combinación híbrida de Azure AD.