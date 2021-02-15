---
title: Cómo configurar Exchange Server local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar Exchange Server local para usar la autenticación moderna híbrida (HM), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780289"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Cómo configurar Exchange Server local para usar la autenticación moderna híbrida

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna híbrida (HM) es un método de administración de identidades que ofrece una autenticación y autorización de usuario más seguras, y está disponible para las implementaciones híbridas locales de Exchange Server.

## <a name="fyi"></a>FYI

Antes de empezar, llame a:

- Autenticación moderna \> híbrida HM

- EXCH local de Exchange \>

- EXO de Exchange Online \>

Además, si un gráfico de este artículo tiene un objeto que es *"atenuado"* o "atenuado", significa que el elemento que se muestra en gris no se incluye en la configuración específica de HM .

## <a name="enabling-hybrid-modern-authentication"></a>Habilitar la autenticación moderna híbrida

Activar HM significa:

1. Asegúrese de que cumple los requisitos previos antes de comenzar.

1. Dado que **muchos requisitos previos** son comunes tanto para Skype Empresarial como para Exchange, la introducción a la autenticación moderna híbrida y los [requisitos previos](hybrid-modern-auth-overview.md)para usarlo con los servidores locales de Skype Empresarial y Exchange. Haga esto antes de comenzar cualquiera de los pasos de este artículo.

1. Agregar direcciones URL de servicios web locales como nombres principales de **servicio (SPN)** en Azure AD.

1. Asegurarse de que todos los directorios virtuales están habilitados para HM

1. Comprobación del objeto de servidor de autenticación de EvoSTS

1. Habilitar HM en EXCH.

 **Nota** ¿La versión de Office es compatible con MA? Vea cómo funciona la autenticación moderna para las aplicaciones cliente de [Office 2013 y Office 2016.](modern-auth-for-office-2013-and-2016.md)

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Asegúrese de que cumple todos los requisitos previos

Dado que muchos requisitos previos son comunes tanto para Skype Empresarial como para Exchange, revise la introducción a la autenticación moderna híbrida y los [requisitos previos](hybrid-modern-auth-overview.md)para usarlo con los servidores locales de Skype Empresarial y Exchange. Haga esto  *antes*  de comenzar cualquiera de los pasos de este artículo.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Agregar direcciones URL de servicios web locales como SPN en Azure AD

Ejecute los comandos que asignan las direcciones URL del servicio web local como SPN de Azure AD. Los dispositivos y equipos cliente usan los SPN durante la autenticación y autorización. Todas las direcciones URL que se pueden usar para conectarse desde local a Azure Active Directory (Azure AD) deben estar registradas en Azure AD (esto incluye espacios de nombres internos y externos).

En primer lugar, recopile todas las direcciones URL que necesita agregar en AAD. Ejecute estos comandos localmente:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Asegúrese de que los clientes de direcciones URL a los que se pueden conectar aparecen como nombres principales de servicio HTTPS en AAD.

1. En primer lugar, conéctese a AAD [con estas instrucciones.](connect-to-microsoft-365-powershell.md)

   **Nota** Debe usar la opción _Connect-MsolService_ de esta página para poder usar el siguiente comando.

2. Para las direcciones URL relacionadas con Exchange, escriba el siguiente comando:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Tome nota de (y captura de pantalla para una comparación posterior) del resultado de este comando, que debe incluir una dirección URL https://  *autodiscover.yourdomain.com*  y  *https:// mail.yourdomain.com,* pero principalmente con SPN que comienzan con 00000002-0000-0ff1-ce00-000000000000/. Si faltan https:// direcciones URL de su entorno local, tendremos que agregar esos registros específicos a esta lista.

3. Si no ve los registros MAPI/HTTP, EWS, ActiveSync, OAB y Autodiscover internos y externos en esta lista, debe agregarlos con el comando siguiente (las direcciones URL de ejemplo son ' ' y ' ', pero reemplazaría las direcciones URL de ejemplo por las `mail.corp.contoso.com` `owa.contoso.com` **suyas propias):**

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Compruebe que los nuevos registros se agregaron ejecutando el comando Get-MsolServicePrincipal del paso 2 y mirando el resultado. Compare la lista o captura de pantalla de antes con la nueva lista de SPN. También puede tomar una captura de pantalla de la nueva lista de los registros. Si se ha realizado correctamente, verá las dos direcciones URL nuevas en la lista. En nuestro ejemplo, la lista de SPN incluirá ahora las direcciones URL específicas  `https://mail.corp.contoso.com`  y  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Comprobar que los directorios virtuales están configurados correctamente

Ahora compruebe que OAuth está habilitado correctamente en Exchange en todos los directorios virtuales que Outlook puede usar ejecutando los siguientes comandos:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Compruebe el resultado para asegurarse de que **OAuth** está habilitado en cada uno de estos VDirs, tendrá un aspecto parecido a este (y la clave que se debe ver es "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Si falta OAuth en cualquier servidor y en cualquiera de los cuatro directorios virtuales, debe agregarlo mediante los comandos correspondientes antes de continuar ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)y [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Confirmar que el objeto de servidor de autenticación de EvoSTS está presente

Vuelva al Shell de administración de Exchange local para este último comando. Ahora puede validar que su entorno local tiene una entrada para el proveedor de autenticación de aoveSTS:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

El resultado debe mostrar un AuthServer del nombre EvoSts y el estado "Habilitado" debe ser True. Si no ve esto, debe descargar y ejecutar la versión más reciente del Asistente para la configuración híbrida.

 **Importante** Si ejecuta Exchange 2010 en su entorno, no se creará el proveedor de autenticación EvoSTS.

## <a name="enable-hma"></a>Habilitar HM

Ejecute el siguiente comando en el Shell de administración de Exchange, local:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Comprobar

Una vez que habilite HM, el siguiente inicio de sesión de un cliente usará el nuevo flujo de autenticación. Ten en cuenta que al activar HM no se desencadenará una nueva autenticación para ningún cliente. Los clientes se reautentifiquen en función de la duración de los tokens de autenticación o los certificados que tengan.

También debe mantener presionada la tecla CTRL al mismo tiempo que hace clic con el botón secundario en el icono del cliente de Outlook (también en la bandeja de notificaciones de Windows) y hacer clic en "Estado de conexión". Busque la dirección SMTP del cliente en un tipo "Authn" de "Bearer", que representa el token de portador usado \* en OAuth.

 **Nota** ¿Necesita configurar Skype Empresarial con HM? Necesitará dos artículos: uno [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)que enumera las topologías admitidas y otro que muestra cómo [realizar la configuración.](configure-skype-for-business-for-hybrid-modern-authentication.md)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Uso de híbridos modernos de autenticación con Outlook para iOS y Android

Si es un cliente local que usa el servidor Exchange en TCP 443, omita el procesamiento de tráfico para los siguientes intervalos IP:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Temas relacionados

[Requisitos de configuración de autenticación moderna para la transición de Office 365 dedicado/ITAR a vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
