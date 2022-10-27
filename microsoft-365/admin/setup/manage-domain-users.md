---
title: Sincronizar usuarios del dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
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
description: Sincronice usuarios controlados por dominio con Microsoft 365 para empresas.
ms.openlocfilehash: d3a797f1de079108e58194f731d51b089f3d6c23
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68727661"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar usuarios del dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparación para la sincronización de directorios 

Antes de sincronizar los usuarios y equipos desde la Dominio de Active Directory local, revise [Preparación para la sincronización de directorios con Microsoft 365](../../enterprise/prepare-for-directory-synchronization.md). En particular:

   - Asegúrese de que no haya duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses** y **userPrincipalName**. Estos valores deben ser únicos y se deben quitar los duplicados.
   
   - Se recomienda configurar el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local para que coincida con la dirección de correo electrónico principal que corresponde al usuario con licencia de Microsoft 365. Por ejemplo: *mary.shelley@contoso.com* en lugar de *mary@contoso.local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *.local* o *.lan*, en lugar de un sufijo enrutable de Internet como *.com* o *.org*, ajuste primero el sufijo UPN de las cuentas de usuario local como se describe en [Preparación de un dominio no enrutable para la sincronización de directorios](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md). 

**El idfix de ejecución** del paso cuatro (4) siguiente también se asegurará de que el Active Directory local esté listo para la sincronización de directorios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalación y configuración de Azure AD Connect

Para sincronizar los usuarios, grupos y contactos desde la instancia local de Active Directory en Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios. 

 1. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **Configurar** en el panel de navegación izquierdo.

 2. En **Inicio de sesión y seguridad**, seleccione **Agregar o sincronizar usuarios con su cuenta Microsoft**.

 3. En la página **Agregar o sincronizar usuarios a su cuenta Microsoft** , elija **Introducción**.

 4. En el primer paso, ejecute la herramienta IdFix para prepararse para la sincronización del directorio.

 5. Siga los pasos del asistente para descargar Azure AD Connect y usarlo para sincronizar los usuarios controlados por dominio con Microsoft 365.


Consulte [Configuración de la sincronización de directorios para Microsoft 365](../../enterprise/set-up-directory-synchronization.md) para obtener más información.

A medida que configure las opciones para Azure AD Connect, se recomienda habilitar **la sincronización de contraseñas**, el **inicio de sesión único** de conexión directa y la característica de **escritura diferida de contraseñas** , que también se admite en Microsoft 365 para empresas.

> [!NOTE]
> Hay algunos pasos adicionales para la escritura diferida de contraseñas más allá de la casilla en Azure AD Connect. Para obtener más información, vea [Procedimiento: configuración de la escritura diferida de contraseñas](/azure/active-directory/authentication/howto-sspr-writeback). 

Si también desea administrar dispositivos de Windows 10 unidos a un dominio, consulte [Habilitación de dispositivos de Windows 10 unidos a un dominio para que se administren mediante Microsoft 365 Empresa Premium](../../business-premium/m365bp-manage-windows-devices.md) para configurar una unión a Azure AD híbrida.
