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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
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
ms.openlocfilehash: 6a00b76113a750f306ef6545f1b38fcf9f9b2202
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634545"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar usuarios del dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparar la sincronización de directorios 

Antes de sincronizar los usuarios y equipos desde la Dominio de Active Directory local, revise Preparar la sincronización de directorios [para Microsoft 365](../../enterprise/prepare-for-directory-synchronization.md). En particular:

   - Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses** y **userPrincipalName**. Estos valores deben ser únicos y los duplicados deben quitarse.
   
   - Se recomienda configurar el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local para que coincida con la dirección de correo electrónico principal que corresponde al usuario Microsoft 365 licencia. Por ejemplo: *mary.shelley@contoso.com* en lugar de *mary@contoso.local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *.local* o *.lan*, en lugar de un sufijo enrutable de Internet como *.com* u *.org*, ajusta primero el sufijo UPN de las cuentas de usuario locales tal como se describe en Preparar un dominio no enrutable para la sincronización de directorios.[](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

Ejecutar **IdFix en** el paso cuatro (4) siguiente, también se asegura de que el Active Directory local esté listo para la sincronización de directorios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalar y configurar Azure AD Conectar

Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, instale Azure Active Directory Conectar y configure la sincronización de directorios. 

 1. En el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **Configurar** en la navegación izquierda.

 2. En **Inicio de sesión y seguridad**, seleccione **Agregar o sincronizar usuarios con su cuenta microsoft**.

 3. En la **página Agregar o sincronizar usuarios con su cuenta microsoft**, elija **Comenzar**.

 4. En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.

 5. Siga los pasos del asistente para descargar Azure AD Conectar y usarlo para sincronizar los usuarios controlados por el dominio para Microsoft 365.


Consulte [Configurar la sincronización de directorios Microsoft 365](../../enterprise/set-up-directory-synchronization.md) para obtener más información.

Al configurar las opciones para Azure AD Conectar, se recomienda habilitar la sincronización de **contraseñas,** el inicio de sesión único sin problemas y la característica de  escritura escritura por contraseña, que también se admite en Microsoft 365 para empresas.

> [!NOTE]
> Hay algunos pasos adicionales para la reescribición de contraseñas más allá de la casilla de verificación en Azure AD Conectar. Para obtener más información, vea [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback). 

Si también quieres administrar dispositivos de Windows 10 unidos a un dominio, consulta Habilitar dispositivos de [Windows 10](../../business-premium/m365bp-manage-windows-devices.md) unidos al dominio para que los administre Microsoft 365 Business Premium para configurar un Azure AD unirse.
