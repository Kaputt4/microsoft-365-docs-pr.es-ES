---
title: Cómo funciona la autenticación moderna para las aplicaciones de cliente de Office 2013 y Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo las características de autenticación modernas de Microsoft 365 funcionan de forma diferente para las aplicaciones cliente de Office 2013 y 2016.
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921671"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Cómo funciona la autenticación moderna para las aplicaciones cliente de Office 2013, Office 2016 y Office 2019

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Lea este artículo para obtener información sobre cómo las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 usan características de autenticación modernas basadas en la configuración de autenticación en el inquilino de Microsoft 365 para Exchange Online, SharePoint Online y Skype Empresarial Online.

> [!NOTE]
> Las aplicaciones cliente heredadas, como Office 2010 y Office para Mac 2011, no admiten la autenticación moderna y solo se pueden usar con autenticación básica.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Disponibilidad de autenticación moderna para servicios de Microsoft 365

Para los servicios de Microsoft 365, el estado predeterminado de la autenticación moderna es:
  
- Activado **para** Exchange Online de forma predeterminada. Consulte [Habilitar o deshabilitar la autenticación moderna en Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) para desactivarla o activarla. 
    
- Activado **para** SharePoint Online de forma predeterminada. 
    
- Activado **para** Skype Empresarial Online de forma predeterminada. Vea [Habilitar Skype Empresarial Online para la autenticación ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)moderna para desactivarla o activarla.

> [!NOTE]
> En el caso de los inquilinos creados **antes** del 1 de agosto de 2017, la autenticación moderna está **desactivada** de forma predeterminada para Exchange Online y Skype para empresas Online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Comportamiento de inicio de sesión de aplicaciones cliente de Office

Las aplicaciones cliente de Office 2013 admiten la autenticación heredada de forma predeterminada. Legacy significa que admiten el Asistente para inicio de sesión de Microsoft Online o la autenticación básica. Para que estos clientes usen características de autenticación modernas, el cliente de Windows debe tener las claves del Registro establecidas. Para obtener instrucciones, vea [Enable Modern Authentication for Office 2013 on Windows devices](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves se tienen que establecer en cada dispositivo en el que quiera habilitar la autenticación moderna:
  
|**Clave del registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Lea [Cómo usar la autenticación moderna (ADAL) con Skype](./hybrid-modern-auth-overview.md) Empresarial para obtener información sobre cómo funciona con Skype Empresarial. 
  
Los clientes de Office 2016 y Office 2019 admiten la autenticación moderna de forma predeterminada y no se necesita ninguna acción para que el cliente use estos nuevos flujos. Sin embargo, se necesita una acción explícita para usar la autenticación heredada.
  
Haga clic en los vínculos siguientes para ver cómo funciona la autenticación de cliente de Office 2013, Office 2016 y Office 2019 con los servicios de Microsoft 365 en función de si la autenticación moderna está activada o no.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype Empresarial Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange en línea

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a Exchange Online con o sin autenticación moderna.
  
|Versión de la aplicación cliente de Office****|Clave del Registro presente?****|Autenticación moderna en?****|Comportamiento de autenticación con autenticación moderna activada para el inquilino (predeterminado)****|Comportamiento de autenticación con autenticación moderna desactivada para el inquilino****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sí  <br/> |Fuerza la autenticación moderna en Outlook 2013, 2016 o 2019. <br/> [Más información](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Fuerza la autenticación moderna en el cliente de Outlook.<br/> |
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL=0  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2016  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sí  <br/> |Fuerza la autenticación moderna en 2013, 2016 o 2019. <br/> [Más información](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Fuerza la autenticación moderna en el cliente de Outlook.<br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL=0  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint en linea

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a SharePoint Online con o sin autenticación moderna.
  
|Versión de la aplicación cliente de Office****|Clave del Registro presente?****|Autenticación moderna en?****|Comportamiento de autenticación con autenticación moderna activada para el inquilino (predeterminado)****|Comportamiento de autenticación con autenticación moderna desactivada para el inquilino****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype Empresarial Online
<a name="BK_SFBO"> </a>

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a Skype Empresarial Online con o sin autenticación moderna.
  
|Versión de la aplicación cliente de Office****|Clave del Registro presente?****|Autenticación moderna en?****|Comportamiento de autenticación con autenticación moderna activada para el inquilino****|Comportamiento de autenticación con autenticación moderna desactivada para el inquilino (predeterminado)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |La autenticación moderna se intenta primero. Si el servidor rechaza una conexión de autenticación moderna, se usa el Asistente para inicio de sesión de Microsoft Online. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial Online no están habilitados.  <br/> |Solo asistente de inicio de sesión de Microsoft Online.  <br/> |
   
## <a name="see-also"></a>Vea también

[Habilitar la autenticación moderna para Office 2013 en dispositivos Windows](../admin/security-and-compliance/enable-modern-authentication.md)

[Autenticación multifactor para Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Iniciar sesión en Microsoft 365 con autenticación multifactor](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)