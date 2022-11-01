---
title: Pruebas de usuario en multigeográficas
description: Más información sobre las pruebas de usuario en multigeográficas
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.reviewer: dmwmsft
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: c150743b97e31e06ca1107dd3e5669b5296ad67c
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806127"
---
# <a name="user-testing-in-multi-geo"></a>Pruebas de usuario en multigeográficas

En Azure Active Directory (Azure AD) hay dos tipos de objetos de usuario: usuarios solo de nube y usuarios sincronizados. Siga las instrucciones adecuadas para el tipo de usuario.

>[!TIP]
>Se recomienda iniciar las validaciones con un usuario de prueba o un grupo pequeño de usuarios antes de implementar la versión multigeográfica en la organización completa.

## <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Sincronizar la ubicación de datos preferida del usuario con Azure AD Connect

Si los usuarios de su compañía se sincronizan con Azure AD desde un sistema local de Active Directory, sus PreferredDataLocation deben rellenarse en AD y sincronizarse en Azure AD.

Siga el proceso en <a href="/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation" target="_blank">Sincronización de Azure Active Directory Connect: Configuración de la ubicación de datos preferida para los recursos de Office 365</a> para configurar la sincronización de la ubicación de datos preferida desde los servicios de dominio de Active Directory (AD DS) locales a Azure AD.

Se recomienda incluir el establecimiento de la ubicación de datos preferida del usuario como parte del flujo de trabajo de creación de usuarios estándar.

>[!IMPORTANT]
>En el caso de los nuevos usuarios sin OneDrive aprovisionado, realice la licencia de la cuenta y espere al menos 48 horas después de que la PDL de un usuario se sincronice con Azure AD para que los cambios se propaguen antes de que el usuario inicie sesión en OneDrive para la Empresa. (El establecimiento de la PDL antes de que el usuario inicie sesión para aprovisionar OneDrive para la Empresa garantiza que la nueva instancia de OneDrive del usuario se aprovisionará en la ubicación correcta).

## <a name="setting-preferred-data-location-for-cloud-only-users"></a>Establecimiento de la ubicación de datos preferida de usuarios solo de nube

Si los usuarios de la compañía no se sincronizan con Azure AD en un sistema de Active Directory local, lo que indica que se crearon en Microsoft 365 o Azure AD, la PDL debe establecerse con el módulo de Microsoft Azure Active Directory para Windows PowerShell.

Los procedimientos de esta sección requieren el <a href="https://www.powershellgallery.com/packages/MSOnline/1.1.166.0" target="_blank">Módulo de Microsoft Azure Active Directory para Windows PowerShell</a>. Si ya tiene instalado este módulo, asegúrese de actualizarlo a la versión más reciente.

[Conéctese e inicie sesión](connect-to-microsoft-365-powershell.md) con un conjunto de credenciales de administrador global para el _inquilino_.

Use el cmdlet [Set-MsolUser](/powershell/module/msonline/set-msoluser) para establecer la ubicación de datos preferida para cada uno de los usuarios. Por ejemplo:

```PowerShell
Set-MsolUser -UserPrincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR
```

Puede comprobar para confirmar que la ubicación de datos preferida se actualizó correctamente mediante el cmdlet Get-MsolUser. Por ejemplo:

```PowerShell
Get-MsolUser -UserPrincipalName Robyn.Buckley@Contoso.com.PreferredDatalocation
```

Se recomienda incluir el establecimiento de la ubicación de datos preferida del usuario como parte del flujo de trabajo de creación de usuarios estándar.

>[!IMPORTANT]
>o nuevos usuarios sin OneDrive aprovisionado, licencian la cuenta y esperen al menos 48 horas después de que se establezca la PDL de un usuario para que los cambios se propaguen antes de que el usuario inicie sesión en OneDrive. (El establecimiento de la PDL antes de que el usuario inicie sesión para aprovisionar OneDrive para la Empresa garantiza que la nueva instancia de OneDrive del usuario se aprovisionará en la ubicación correcta).

## <a name="onedrive-for-business-provisioning-and-the-effect-of-pdl"></a>aprovisionamiento de OneDrive para la Empresa y el efecto de la PDL

Si el usuario ya tiene un sitio OneDrive para la Empresa creado en el _inquilino_, la configuración de su PDL no moverá automáticamente su OneDrive existente. Para mover OneDrive de un usuario, consulte [OneDrive para la Empresa Movimiento geográfico](move-onedrive-between-geo-locations.md).

> [!NOTE]
> Exchange Online reubica automáticamente el buzón del usuario si el PLD cambia y MailboxRegion ya no coincide con el código de ubicación geográfica de la base de datos de buzones. Para obtener más información, consulte [Administración de buzones de Exchange Online en un entorno multigeográfico](administering-exchange-online-multi-geo.md).

Si el usuario no tiene un sitio OneDrive para la Empresa dentro del _inquilino_, OneDrive para la Empresa se aprovisionará para ellos de acuerdo con su valor PDL, suponiendo que la PDL para el usuario coincida con una de las ubicaciones satélite de la empresa.
