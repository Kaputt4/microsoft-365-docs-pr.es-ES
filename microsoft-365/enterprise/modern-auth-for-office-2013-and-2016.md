---
title: Cómo funciona la autenticación moderna para las aplicaciones de cliente de Office 2013 y Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
- scotvorg
- M365-security-compliance
description: Obtenga información sobre cómo funcionan las características de autenticación modernas de Microsoft 365 de forma diferente para las aplicaciones cliente de Office 2013 y 2016.
ms.openlocfilehash: e22f4106d52301acccebe53c6b42caa3663e2787
ms.sourcegitcommit: a250d043a2e42ecbc7b86147468d1660af5a6ba7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68672983"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Funcionamiento de la autenticación moderna para aplicaciones cliente de Office 2013, Office 2016 y Office 2019

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Lea este artículo para obtener información sobre cómo las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 usan características de autenticación modernas basadas en la configuración de autenticación en el inquilino de Microsoft 365 para Exchange Online, SharePoint Online y Skype Empresarial Online.

> [!NOTE]
> Las aplicaciones cliente heredadas, como Office 2010 y Office para Mac 2011, no admiten la autenticación moderna y solo se pueden usar con la autenticación básica.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Disponibilidad de la autenticación moderna para los servicios de Microsoft 365

Para los servicios de Microsoft 365, el estado predeterminado de la autenticación moderna es:

- **Activado para** Exchange Online de forma predeterminada. Consulte [Habilitación o deshabilitación de la autenticación moderna en Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) para desactivarla o activarla.

- **Activado para** SharePoint Online de forma predeterminada.

- **Activado para** Skype Empresarial En línea de forma predeterminada. Consulte [Enable Skype Empresarial Online for modern authentication to turn it off or on (Habilitar Skype Empresarial en línea para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)para desactivarla o activarla).

> [!NOTE]
> En el caso de los inquilinos creados **antes** del 1 de agosto de 2017, la autenticación moderna está **desactivada** de forma predeterminada para Exchange Online y Skype para empresas Online.

## <a name="sign-in-behavior-of-office-client-apps"></a>Comportamiento de inicio de sesión de aplicaciones cliente de Office

Las aplicaciones cliente de Office 2013 admiten la autenticación heredada de forma predeterminada. Heredado significa que admiten el Asistente de inicio de sesión de Microsoft Online o la autenticación básica. Para que estos clientes usen características de autenticación modernas, el cliente de Windows debe tener establecidas las claves del Registro. Para obtener instrucciones, vea [Habilitar la autenticación moderna para Office 2013 en dispositivos Windows](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

> [!IMPORTANT]
> El uso de la autenticación básica está en desuso para los buzones de Exchange Online en Microsoft 365. Esto significa que si Outlook 2013 no está configurado para usar la autenticación moderna, pierde la capacidad de conectarse. Lea [este artículo](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437) para obtener más información sobre el desuso de la autenticación básica.

To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:

|**Clave del registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover |REG_DWORD |1 |

Lea [Cómo usar la autenticación moderna (ADAL) con Skype Empresarial](./hybrid-modern-auth-overview.md) para obtener información sobre cómo funciona con Skype Empresarial.

## <a name="software-requirements"></a>Requisitos de software

Para habilitar la autenticación multifactor (MFA) para aplicaciones cliente de Office 2013, debe tener instalado el software que se muestra a continuación (en la versión que se muestra a continuación o en una versión *posterior* ). El proceso es diferente en función del tipo de instalación (basado en MSI o mediante Hacer clic y ejecutar).

En primer lugar, averigüe si la instalación de Office está basada en MSI o haga clic para ejecutar con los pasos siguientes.

1. Inicie Outlook 2013.
2. En el menú **Archivo** , seleccione **Cuenta de Office**.
3. Para las instalaciones de *Hacer clic y ejecutar* de Outlook 2013 se muestra un elemento **Opciones de actualización** . En las instalaciones basadas en MSI, no aparecerá un elemento Opciones de actualización.
    1. El botón Hacer clic y ejecutar **opciones de actualización** le indicará "Novedades se descargan e instalan automáticamente" y la versión actual.

### <a name="click-to-run-based-installations"></a>Instalaciones basadas en Hacer clic y ejecutar

Para las instalaciones basadas en hacer clic y ejecutar *, debe* tener instalado el siguiente software en una versión de archivo que se muestra a continuación o en una versión *posterior* del archivo. Si la versión del archivo no es igual o mayor que la versión del archivo que aparece, actualícela con los pasos siguientes.


|Nombre de archivo  |Ruta de instalación en el equipo  |Versión de archivo  |
|---------|---------|---------|
|MSO.DLL     |C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL       |15.0.4753.1001       |
|CSI.DLL   |CSI.DLL C:\Archivos de programa\Microsoft Office 15\root\office15\csi.dll         |15.0.4753.1000        |
|Groove.EXE*     |C:\Archivos de programa\Microsoft Office 15\root\office15\GROOVE.exe       |15.0.4763.1000      |
|Outlook.exe     |C:\Archivos de programa\Microsoft Office 15\root\office15\OUTLOOK.exe         |15.0.4753.1002     |
|ADAL.DLL    |C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL       |1.0.2016.624         |
|Iexplore.exe    |C:\Archivos de programa\Internet Explorer     |Varía         |

\* Si el componente Groove.EXE no está presente en la instalación de Office, no es necesario instalarlo para que ADAL funcione. Sin embargo, si está presente, se requiere la compilación para Groove.EXE que se muestra aquí.

### <a name="msi-based-installations"></a>Instalaciones basadas en MSI

Para las instalaciones basadas en MSI, el siguiente software *debe* instalarse en la versión de archivo que se muestra a continuación o en una versión *posterior* del archivo. Si la versión del archivo no es igual o mayor que la versión del archivo que se muestra a continuación, actualice mediante el vínculo de la columna *Actualizar artículo de KB* .


|Nombre de archivo  |Ruta de instalación en el equipo  |Dónde obtener la actualización  |Versión  |
|---------|---------|---------|---------|
|MSO.DLL|C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\MSO.DLL     |[KB3085480](https://support.microsoft.com/en-us/topic/description-of-the-security-update-for-office-2013-september-10-2019-0d171ba2-2eba-a2ca-a54d-c0f568de6bcc)        |15.0.4753.1001       |
|CSI.DLL|C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\Csi.dll     |[KB3172545](https://support.microsoft.com/en-us/topic/july-11-2017-update-for-office-2013-kb3172545-d6b47054-04d5-5154-40ba-3436d1e0efdb)        |15.0.4753.1000         |
|Groove.exe*|C:\Archivos de programa\Microsoft Office\Office15\GROOVE.EXE            |[KB4022226](https://support.microsoft.com/en-us/topic/august-7-2018-update-for-onedrive-for-business-for-office-2013-kb4022226-6163bb26-cbde-eb16-ac42-abfda7afbf68)        |15.0.4763.1000         |
|Outlook.exe|C:\Archivos de programa\Microsoft Office\Office15\OUTLOOK.EXE          |[KB4484096](https://support.microsoft.com/en-us/topic/october-1-2019-update-for-outlook-2013-kb4484096-6513145a-cc75-1cd1-72b7-78cb62d8476b)        |15.0.4753.1002         |
|ADAL.DLL|C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\ADAL.DLL   |[KB3085565](https://support.microsoft.com/en-us/topic/july-5-2016-update-for-office-2013-kb3085565-1d1a6d24-fbd4-1bae-242f-a35e0e2aba40)        |1.0.2016.624         |
|Iexplore.exe|C:\Archivos de programa\Internet Explorer                             |[MS14-052](https://support.microsoft.com/en-us/topic/ms14-052-cumulative-security-update-for-internet-explorer-september-9-2014-17d29b71-9e78-0bc1-8961-7b812d04e4e1)         |No aplicable         |

\* Si el componente Groove.EXE no está presente en la instalación de Office, no es necesario instalarlo para que ADAL funcione. Sin embargo, si está presente, se requiere la compilación para Groove.EXE que se muestra aquí.

Los clientes de Office 2016 y Office 2019 admiten la autenticación moderna de forma predeterminada y no se necesita ninguna acción para que el cliente use estos nuevos flujos. Sin embargo, se necesita una acción explícita para usar la autenticación heredada.

Haga clic en los vínculos siguientes para ver cómo funciona la autenticación de cliente de Office 2013, Office 2016 y Office 2019 con los servicios de Microsoft 365 en función de si la autenticación moderna está activada o no.

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype Empresarial Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a Exchange Online con o sin autenticación moderna.

|Versión de la aplicación cliente de Office****|¿La clave del Registro está presente?****|Autenticación moderna activada?****|Comportamiento de autenticación con la autenticación moderna activada para el inquilino (valor predeterminado)****|Comportamiento de autenticación con la autenticación moderna desactivada para el inquilino****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sí  <br/> |Fuerza la autenticación moderna en Outlook 2013, 2016 o 2019. <br/> [Más información](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Fuerza la autenticación moderna dentro del cliente de Outlook.<br/> |
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL=0  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2016  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Yes  <br/> |Fuerza la autenticación moderna en 2013, 2016 o 2019. <br/> [Más información](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Fuerza la autenticación moderna dentro del cliente de Outlook.<br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL=0  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Autenticación básica  <br/> |Autenticación básica  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa la autenticación básica. El servidor rechaza la autenticación moderna cuando el inquilino no está habilitado.  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a SharePoint Online con o sin autenticación moderna.

|Versión de la aplicación cliente de Office****|¿La clave del Registro está presente?****|Autenticación moderna activada?****|Comportamiento de autenticación con la autenticación moderna activada para el inquilino (valor predeterminado)****|Comportamiento de autenticación con la autenticación moderna desactivada para el inquilino****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sí  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Yes  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Solo autenticación moderna.  <br/> |Error al conectarse.  <br/> |

### <a name="skype-for-business-online"></a>Skype Empresarial Online
<a name="BK_SFBO"> </a>

En la tabla siguiente se describe el comportamiento de autenticación de las aplicaciones cliente de Office 2013, Office 2016 y Office 2019 cuando se conectan a Skype Empresarial Online con o sin autenticación moderna.

|Versión de la aplicación cliente de Office****|¿La clave del Registro está presente?****|Autenticación moderna activada?****|Comportamiento de autenticación con la autenticación moderna activada para el inquilino****|Comportamiento de autenticación con la autenticación moderna desactivada para el inquilino (valor predeterminado)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 1  <br/> |Sí  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |
|Office 2019  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Yes  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |
|Office 2016  <br/> |Sí, EnableADAL = 0  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |
|Office 2013  <br/> |Sí, EnableADAL = 1  <br/> |Yes  <br/> |Primero se intenta la autenticación moderna. Si el servidor rechaza una conexión de autenticación moderna, se usa microsoft online sign-in Assistant. El servidor rechaza la autenticación moderna cuando los inquilinos de Skype Empresarial online no están habilitados.  <br/> |Solo el Asistente de inicio de sesión de Microsoft Online.  <br/> |

## <a name="see-also"></a>Vea también

[Habilitar la autenticación moderna para Office 2013 en dispositivos Windows](../admin/security-and-compliance/enable-modern-authentication.md)

[Autenticación multifactor para Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Inicio de sesión en Microsoft 365 con autenticación multifactor](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
