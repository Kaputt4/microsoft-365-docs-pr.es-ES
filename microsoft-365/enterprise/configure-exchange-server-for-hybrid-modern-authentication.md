---
title: Cómo configurar Exchange Server local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/27/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar un Exchange Server local para usar la autenticación moderna híbrida (HMA), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ee190a541fdf3e4e77a251e040f2cb69416088c
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095760"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Cómo configurar Exchange Server local para usar la autenticación moderna híbrida

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

La autenticación moderna híbrida (HMA) es un método de administración de identidades que ofrece autenticación y autorización de usuario más seguras y está disponible para las implementaciones híbridas locales de Exchange servidor.

## <a name="definitions"></a>Definiciones

Antes de empezar, debería estar familiarizado con algunas definiciones:

- HMA de autenticación \> moderna híbrida

- Exchange local \> EXCH

- \> Exchange Online EXO

Además, *si un gráfico de este artículo tiene un objeto "atenuado" o "atenuado", significa que el elemento que se muestra en gris no se incluye en la configuración específica de HMA*.

## <a name="enabling-hybrid-modern-authentication"></a>Habilitación de la autenticación moderna híbrida

Activar HMA significa:

1. Asegúrese de conocer las preguntas previas antes de empezar.

1. Dado que muchos **requisitos previos** son comunes tanto para Skype Empresarial como para Exchange, [la introducción a la autenticación moderna híbrida y los requisitos previos para usarlo con servidores locales Skype Empresarial y Exchange](hybrid-modern-auth-overview.md). Haga esto antes de comenzar cualquiera de los pasos de este artículo.
Requisitos sobre los buzones vinculados que se van a insertar.

1. Agregar direcciones URL de servicio web locales como **nombres de entidad de seguridad de servicio (SPN)** en Azure AD. En caso de que EXCH esté en híbrido con **varios inquilinos, estas direcciones** URL de servicio web local deben agregarse como SPN en el Azure AD de todos los inquilinos que están en híbrido con EXCH.

1. Asegurarse de que todos los directorios virtuales están habilitados para HMA

1. Comprobación del objeto de servidor de autenticación de EvoSTS

1. Habilitación de HMA en EXCH.

> [!NOTE]
> ¿La versión de Office admite MA? Consulte [How modern authentication works for Office 2013 and Office 2016 client apps (Cómo funciona la autenticación moderna para las aplicaciones cliente de Office 2013 y Office 2016](modern-auth-for-office-2013-and-2016.md)).

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Asegúrese de cumplir todos los requisitos previos

Dado que muchos requisitos previos son comunes tanto para Skype Empresarial como para Exchange, revise [La introducción a la autenticación moderna híbrida y los requisitos previos para usarlo con servidores de Skype Empresarial y Exchange locales](hybrid-modern-auth-overview.md). Haga esto  *antes*  de comenzar cualquiera de los pasos de este artículo.

> [!NOTE]
> Outlook Web App y Exchange Panel de control no funcionan con la autenticación moderna híbrida.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Agregar direcciones URL de servicio web locales como SPN en Azure AD

Ejecute los comandos que asignan las direcciones URL del servicio web local como Azure AD SPN. Los SPN los usan los dispositivos y máquinas cliente durante la autenticación y autorización. Todas las direcciones URL que se pueden usar para conectarse desde el entorno local a Azure Active Directory (Azure AD) deben registrarse en Azure AD (esto incluye espacios de nombres internos y externos).

En primer lugar, recopile todas las direcciones URL que necesita agregar en AAD. Ejecute estos comandos en el entorno local:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*hostname*
```

Asegúrese de que las direcciones URL a las que se pueden conectar los clientes se enumeran como nombres de entidad de servicio HTTPS en AAD. En caso de que EXCH esté en híbrido con **varios inquilinos**, estos SPN HTTPS se deben agregar en el AAD de todos los inquilinos en híbrido con EXCH.

1. En primer lugar, conéctese a AAD con [estas instrucciones](connect-to-microsoft-365-powershell.md).

    > [!NOTE]
    > Debe usar la opción _Conectar-MsolService_ de esta página para poder usar el comando siguiente.

2. Para las direcciones URL relacionadas con Exchange, escriba el siguiente comando:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Tome nota de (y captura de pantalla para la comparación posterior) de la salida de este comando, que debe incluir una `https://*autodiscover.yourdomain.com*` dirección URL y `https://*mail.yourdomain.com*` , pero principalmente constan de SPN que comienzan por `00000002-0000-0ff1-ce00-000000000000/`. `https://` Si faltan direcciones URL del entorno local, esos registros específicos se deben agregar a esta lista.

3. Si no ve los registros MAPI/HTTP, EWS, ActiveSync, OAB y Autodiscover internos y externos en esta lista, debe agregarlos mediante el comando siguiente (las direcciones URL de ejemplo son `mail.corp.contoso.com` y `owa.contoso.com`, pero **reemplazaría las direcciones URL de ejemplo por las suyas propias**):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Compruebe que los nuevos registros se agregaron ejecutando el `Get-MsolServicePrincipal` comando del paso 2 de nuevo y examinando la salida. Compare la lista o captura de pantalla de antes con la nueva lista de SPN. También puede realizar una captura de pantalla de la nueva lista de los registros. Si se ha realizado correctamente, verá las dos direcciones URL nuevas en la lista. En nuestro ejemplo, la lista de SPN ahora incluirá las direcciones `https://mail.corp.contoso.com` URL específicas y `https://owa.contoso.com`.

## <a name="verify-virtual-directories-are-properly-configured"></a>Comprobar que los directorios virtuales están configurados correctamente

Ahora compruebe que OAuth está habilitado correctamente en Exchange en todos los directorios virtuales Outlook podría usar mediante la ejecución de los siguientes comandos:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Compruebe la salida para asegurarse de que **OAuth** está habilitado en cada uno de estos VDirs, tendrá un aspecto similar al siguiente (y el aspecto clave que debe tenerse en cuenta es "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Si falta OAuth en cualquier servidor y en cualquiera de los cuatro directorios virtuales, debe agregarlo mediante los comandos pertinentes antes de continuar ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory) y [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Confirmación de que el objeto del servidor de autenticación de EvoSTS está presente

Vuelva al shell de administración de Exchange local para este último comando. Ahora puede validar que el entorno local tiene una entrada para el proveedor de autenticación evoSTS:

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts*"} | ft name,enabled
```

La salida debe mostrar un AuthServer del nombre EvoSts con un GUID y el estado "Habilitado" debe ser True. Si no ve esto, debe descargar y ejecutar la versión más reciente del Asistente para configuración híbrida.

> [!NOTE]
> En caso de que EXCH esté en híbrido con **varios inquilinos**, la salida debe mostrar un AuthServer del nombre `EvoSts - {GUID}` de cada inquilino en híbrido con EXCH y el estado **Habilitado** debe ser True para todos estos objetos AuthServer.

> [!IMPORTANT]
> Si ejecuta Exchange 2010 en su entorno, no se creará el proveedor de autenticación de EvoSTS.

## <a name="enable-hma"></a>Habilitación de HMA

Ejecute el siguiente comando en el Shell de administración de Exchange, local, reemplazando \<GUID\> en la línea de comandos por la cadena del entorno:

```powershell
Set-AuthServer -Identity "EvoSTS - <GUID>" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> En versiones anteriores del Asistente para configuración híbrida, EvoSts AuthServer se llamaba simplemente EvoSTS sin un GUID asociado. No es necesario realizar ninguna acción, solo tiene que modificar la línea de comandos anterior para reflejarlo quitando la parte GUID del comando:
>
> ```powershell
> Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
> ```

Si la versión de EXCH es Exchange 2016 (CU18 o posterior) o Exchange 2019 (CU7 o posterior) y el híbrido se configuró con HCW descargado después de septiembre de 2020, ejecute el siguiente comando en el Shell de administración de Exchange, en el entorno local:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> En caso de que EXCH esté en híbrido con **varios inquilinos**, hay varios objetos AuthServer presentes en EXCH con dominios correspondientes a cada inquilino.  La marca **IsDefaultAuthorizationEndpoint** debe establecerse en true (mediante el cmdlet **IsDefaultAuthorizationEndpoint** ) para cualquiera de estos objetos AuthServer. Esta marca no se puede establecer en true para todos los objetos Authserver y HMA se habilitaría incluso si una de estas marcas **IsDefaultAuthorizationEndpoint** del objeto AuthServer está establecida en true.
> 
> Para el parámetro **DomainName** , use el valor de dominio de inquilino, que suele tener el formato `contoso.onmicrosoft.com`.

## <a name="verify"></a>Verificar

Una vez que habilite HMA, el siguiente inicio de sesión de un cliente usará el nuevo flujo de autenticación. Tenga en cuenta que al activar HMA no se desencadenará una nueva autenticación para ningún cliente y puede tardar un tiempo en que Exchange puedan elegir la nueva configuración.

También debe mantener presionada la tecla CTRL al mismo tiempo que haga clic con el botón derecho en el icono del cliente de Outlook (también en la bandeja de notificaciones de Windows) y haga clic en "Estado de conexión". Busque la dirección SMTP del cliente en un tipo **de autenticación** de `Bearer\*`, que representa el token de portador usado en OAuth.

> [!NOTE]
> ¿Necesita configurar Skype Empresarial con HMA? Necesitará dos artículos: uno que enumera [las topologías admitidas](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) y otro que muestra [cómo realizar la configuración](configure-skype-for-business-for-hybrid-modern-authentication.md).

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Uso de híbridos modernos de autenticación con Outlook para iOS y Android

Si es un cliente local que usa Exchange servidor en TCP 443, permita el tráfico de red desde los siguientes intervalos IP:

```console
52.125.128.0/20
52.127.96.0/23
```

Estos intervalos de direcciones IP también se documentan en [Puntos de conexión adicionales no incluidos en el servicio web de direcciones IP y direcciones IP Office 365](/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls).

## <a name="related-topics"></a>Temas relacionados

[Requisitos de configuración de autenticación moderna para la transición de Office 365 dedicated/ITAR a vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
