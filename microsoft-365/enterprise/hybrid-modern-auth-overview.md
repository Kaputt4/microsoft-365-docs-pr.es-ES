---
title: Introducción a la autenticación moderna híbrida y requisitos previos para el uso con servidores locales de Skype Empresarial y Exchange
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 12/03/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: En este artículo, aprenderá acerca de la autenticación moderna híbrida y los requisitos previos para su uso con servidores Skype Empresarial y Exchange local.
ms.openlocfilehash: efce3b5a04f2e9500330cab87d7ba8e62ca49db0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312871"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Introducción a la autenticación moderna híbrida y requisitos previos para el uso en Skype Empresarial y los servidores de Exchange locales

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

La _autenticación moderna_ es un método de administración de identidades que ofrece autenticación y autorización de usuarios más seguras. Está disponible para implementaciones híbridas Office 365 de servidores Skype Empresarial locales y Exchange servidores locales y híbridos de dominio dividido Skype Empresarial servidores. Este artículo contiene vínculos a los documentos relacionados sobre los requisitos previos, la configuración o desactivación de la autenticación moderna e información para algunos de los clientes relacionados (como  los clientes de Skype y Outlook).

- [¿Qué es la autenticación moderna?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [¿Qué cambia cuando uso la autenticación moderna?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Comprobar el estado de la autenticación moderna de su entorno local](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [¿Cumple los requisitos previos de la autenticación moderna?](#do-you-meet-modern-authentication-prerequisites)
- [¿Qué más necesito saber antes de comenzar?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>¿Qué es la autenticación moderna?
<a name="BKMK_WhatisModAuth"> </a>

La autenticación moderna es un término genérico para una combinación d métodos de autenticación y autorización entre un cliente (por ejemplo, el equipo portátil o el teléfono) y un servidor, así como algunas medidas de seguridad que dependen de las directivas de acceso que puede que ya conozca. Incluye:

- **Métodos de autenticación**: autenticación multifactor (MFA); autenticación de tarjeta inteligente; autenticación basada en certificados de cliente
- **Métodos de autorización**: la implementación de Microsoft de Open Authorization (OAuth).
- **Directivas de acceso condicional**: acceso condicional de Azure Active Directory (Azure AD) y administración de aplicaciones móviles (MAM)

La administración de identidades de usuario con la autenticación moderna ofrece a los administradores distintas herramientas para la protección de los recursos y ofrece métodos más seguros de administración de identidades para escenarios locales (Exchange y Skype Empresarial), implementaciones híbridas de Exchange y dominios divididos o híbridos de Skype Empresarial.

Dado Skype Empresarial funciona estrechamente con Exchange, el comportamiento de inicio de sesión Skype Empresarial usuarios cliente se verán afectados por el estado de autenticación moderno de Exchange. También es aplicable si tiene una arquitectura híbrida de dominio dividido  de Skype Empresarial, en la que tiene Skype Empresarial Online y Skype Empresarial local, con usuarios en ambas ubicaciones.

Para obtener más información acerca de la autenticación moderna en Office 365, [vea Office 365 Client App Support - Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).

> [!IMPORTANT]
> A partir de agosto de 2017, todos los nuevos espacios empresariales de Office 365 que incluyen Skype Empresarial online y Exchange online tienen la autenticación moderna habilitada de manera predeterminada. Los espacios empresariales preexistentes no tendrán un cambio en el estado de su MA predeterminado, pero todos los nuevos espacios empresariales admiten automáticamente el conjunto ampliado de características de identidad que aparecen anteriormente. Para comprobar el estado de su MA, vea la sección [Comprobar el estado de la autenticación moderna de su entorno local](hybrid-modern-auth-overview.md#BKMK_CheckStatus).

## <a name="what-changes-when-i-use-modern-authentication"></a>¿Qué cambia cuando uso la autenticación moderna?
<a name="BKMK_WhatChanges"> </a>

Cuando se usa la autenticación moderna con un servidor de Exchange o Skype Empresarial local, la *autenticación* de los usuarios sigue siendo local, pero la forma de *autorizar* su acceso a los recursos (como archivos o correos electrónicos) cambia. Por este motivo, aunque la autenticación moderna consiste en la comunicación entre el cliente y el servidor, los pasos que se toman durante la configuración de MA hacen que evoSTS (un servicio de token de seguridad usado por Azure AD) se establezca como servidor de autenticación para Skype Empresarial y el servidor de Exchange local.

El cambio a evoSTS permite que los servidores locales usen OAuth (emisión de tokens) para autorizar a los clientes, y también el uso de métodos de seguridad comunes en la nube (igual que la autenticación multifactor). Además, el evoSTS emite tokens que permiten que los usuarios soliciten el acceso a los recursos sin proporcionar su contraseña como parte de la solicitud. Independientemente de la ubicación de los usuarios (en línea o en el entorno local) y de la ubicación donde se encuentre el recurso necesario, EvoSTS se convertirá en el centro de autorización de usuarios y clientes cuando se configure la autenticación moderna.

Por ejemplo, si un cliente Skype Empresarial necesita tener acceso Exchange un servidor para obtener información de calendario en nombre de un usuario, usa la Biblioteca de autenticación de Microsoft (MSAL) para hacerlo. MSAL es una biblioteca de código diseñada para que los recursos protegidos del directorio estén disponibles para las aplicaciones cliente mediante tokens de seguridad de OAuth. MSAL funciona con OAuth para comprobar notificaciones y para intercambiar tokens (en lugar de contraseñas), para conceder a un usuario acceso a un recurso. En el pasado, la autoridad de una transacción como esta (el servidor que sabe cómo validar notificaciones de usuario y emitir los tokens necesarios) podría haber sido un servicio de token de seguridad local o incluso servicios de federación de Active Directory. Sin embargo, la autenticación moderna centraliza dicha autoridad al usar Azure AD.

Esto también significa que, aunque el servidor de Exchange y los entornos de Skype Empresarial puedan ser totalmente locales, el servidor de autorización estará en línea, y el entorno local debe tener la capacidad de crear y mantener una conexión con la suscripción de Office 365 en la nube (y la instancia de Azure AD que la suscripción usa como directorio).

¿Qué no cambia? Tanto si está en un entorno híbrido de dominio dividido como si usa Skype Empresarial y el servidor de Exchange local, todos los usuarios deben autenticarse en primer lugar *localmente*. En una implementación híbrida de la autenticación moderna, _Lyncdiscovery_ y _Autodiscovery_ apuntan al servidor local.

> [!IMPORTANT]
> Si necesita averiguar las topologías específicas de Skype Empresarial compatibles con MA, están [documentadas aquí](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Comprobar el estado de la autenticación moderna de su entorno local
<a name="BKMK_CheckStatus"> </a>

Dado que la autenticación moderna cambia el servidor de autorización usado cuando los servicios aplican OAuth/S2S, debe saber si la autenticación moderna está habilitada o deshabilitada para los entornos Skype Empresarial y Exchange locales. Para comprobar el estado de los servidores de Exchange, ejecute el siguiente comando de PowerShell:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Si el valor de la propiedad _OAuth2ClientProfileEnabled_ es **False**, la autenticación moderna está deshabilitada.

Para más información sobre el cmdlet Get-OrganizationConfig, consulte [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).

Para comprobar los servidores de Skype Empresarial, ejecute el siguiente comando de PowerShell:

```powershell
Get-CSOAuthConfiguration
```

Si el comando devuelve una propiedad _OAuthServers_ vacía, o si el valor de la propiedad _ClientADALAuthOverride_ no es **Allowed**, la autenticación moderna está deshabilitada.

Para más información sobre el cmdlet Get-CsOAuthConfiguration, vea [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration).

## <a name="do-you-meet-modern-authentication-prerequisites"></a>¿Cumple los requisitos previos de la autenticación moderna?

Verifique y compruebe estos elementos antes de continuar:

- **Específico de Skype Empresarial**
  - Todos los servidores deben tener la actualización acumulativa de mayo de 2017 (CU5) para Skype Empresarial Server 2015 o posterior
    - **Excepción:** Aplicación de sucursal con funciones de supervivencia (SBA) puede estar en la versión actual (basada en Lync 2013)
  - El dominio SIP se ha agregado como un dominio federado en Office 365
  - Todos los front-ends SFB deben tener conexiones salientes a Internet, a direcciones URL de autenticación de Office 365 (TCP 443) y CRLs raíz de certificado conocidas (TCP 80) enumeradas en las filas 56 y 125 de la sección "Microsoft 365 Common and Office" de las direcciones URL de Office 365 y los [intervalos](urls-and-ip-address-ranges.md) de direcciones IP.

- **Skype Empresarial en un entorno híbrido de Office 365**
  - Una implementación de Skype Empresarial Server 2019 con todos los servidores que ejecuten Skype Empresarial Server 2019.
  - Una implementación de Skype Empresarial Server 2015 con todos los servidores que ejecuten Skype Empresarial Server 2015.
  - Una implementación con un máximo de dos versiones de servidor distintas, como se muestra a continuación:
    - Skype Empresarial Server 2015
    - Skype Empresarial Server 2019
  - Todos los servidores de Skype Empresarial deben tener instaladas las últimas actualizaciones acumulativas, consulte [Actualizaciones de Skype Empresarial Server](/skypeforbusiness/sfb-server-updates) para buscar y administrar todas las actualizaciones disponibles.
  - No hay ningún Lync Server 2010 o 2013 en el entorno híbrido.

>[!NOTE]
>Si los servidores front-end de Skype Empresarial usan un servidor proxy para el acceso a Internet, el número de puerto y la IP del servidor proxy deben especificarse en la sección de configuración del archivo web.config para cada front-end.

- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Asegúrese de suscribirse a la fuente RSS de [Intervalos de direcciones IP y URL de Office 365](urls-and-ip-address-ranges.md) para mantenerse al día con las listas más recientes de direcciones URL necesarias.

- **Específico de Exchange Server**
  - Usa Exchange Server 2013 CU19 o posterior, Exchange Server 2016 CU8 o posterior, o Exchange Server 2019 CU1 o posterior.
  - No hay ningún servidor de Exchange 2010 en el entorno.
  - No se ha configurado la descarga de SSL. Se admite la terminación y el nuevo cifrado SSL.
  - En caso de que su entorno use una infraestructura de servidor proxy para permitir que los servidores se conecten a Internet, asegúrese de que todos los servidores de Exchange tengan el servidor proxy definido en la propiedad [InternetWebProxy](/powershell/module/exchange/set-exchangeserver).

- **Implementación local de Exchange Server en un entorno híbrido de Office 365**

  - Si usa Exchange Server 2013, al menos un servidor debe tener instalados los roles de servidor de Acceso de cliente y Buzón de correo. Aunque es posible instalar los roles de acceso de cliente y buzón de correo en servidores independientes, se recomienda encarecidamente instalar ambos roles en el mismo servidor para proporcionar más confiabilidad y un rendimiento mejorado.
  - Si usa Exchange Server 2016 o una versión posterior, al menos un servidor debe tener instalado el rol de servidor de Buzón de correo.
  - No hay ningún servidor de Exchange 2007 o 2010 en el entorno híbrido.
  - Todos los servidores de Exchange deben tener instaladas las últimas actualizaciones acumulativas, consulte [Actualizar Exchange a las últimas actualizaciones acumulativas](/exchange/plan-and-deploy/install-cumulative-updates) para buscar y administrar todas las actualizaciones disponibles.

- **Requisitos de protocolo y el cliente de Exchange**

    La disponibilidad de la autenticación moderna viene determinada por la combinación del cliente, el protocolo y la configuración. Si la autenticación moderna no es compatible con el cliente, el protocolo o la configuración, el cliente seguirá usando la autenticación heredada.
  
    Los siguientes clientes y protocolos admiten la autenticación moderna con Exchange local cuando la autenticación moderna está habilitada en el entorno:

  |**Clientes**|**Protocolo principal**|**Notas**|
  |:-----|:-----|:-----|
  |Outlook 2013 y versiones posteriores  <br/> |MAPI sobre HTTP  <br/> |MAPI sobre HTTP debe habilitarse en Exchange para poder usar la autenticación moderna con estos clientes (habilitada o True para las nuevas instalaciones de Exchange Service Pack 2013 1 y posteriores); para obtener más información, vea How [modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).  <br/> Asegúrese de que está ejecutando la compilación mínima necesaria de Outlook. Consulte [Últimas actualizaciones para las versiones de Outlook que usan Windows Installer (MSI)](/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 para Mac y posteriores  <br/> |Servicios Web de Exchange  <br/> |  <br/> |
  |Outlook para iOS y Android  <br/> | Tecnología de sincronización de Microsoft <br/> |Consulte [Usar la autenticación moderna híbrida con Outlook para iOS y Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) para más información.  <br/> |
  |Exchange ActiveSync clientes (por ejemplo, correo de iOS11)  <br/> |Exchange ActiveSync  <br/> |Para los clientes de Exchange ActiveSync que son compatibles con la autenticación moderna, debe volver a crear el perfil para cambiar de la autenticación básica a la autenticación moderna.  <br/> |

    Los clientes o protocolos que no aparecen (por ejemplo, POP3) no admiten la autenticación moderna con Exchange local y siguen usando mecanismos de autenticación heredados incluso después de habilitar la autenticación moderna en el entorno.

- **Requisitos previos generales**
  - Los escenarios de bosque de recursos requerirán una confianza de dos vías con el bosque de cuentas para garantizar que las búsquedas SID correctas se realicen durante las solicitudes de autenticación moderna híbrida. 
  - Si usa AD FS, debe tener Windows 2012 R2 AD FS 3.0 y superior para la federación.
  - Las configuraciones de identidad son cualquiera de los tipos compatibles con Azure AD Connect, como la sincronización de hash de contraseña, la autenticación de paso y el STS local compatibles con Office 365.
  - Tiene Azure AD Connect configurado y funcionando para la replicación y sincronización de usuarios.
  - Ha comprobado que la configuración híbrida está configurada con el modo de Topología híbrida de Exchange clásico entre el entorno local y el de Office 365. La declaración oficial del soporte para la implementación híbrida de Exchange indica que debe tener la CU actual o la CU actual -1.
    > [!NOTE]
    > La autenticación moderna híbrida no es compatible con el [Agente híbrido](/exchange/hybrid-deployment/hybrid-agent).

  - Asegúrese de que, tanto un usuario de prueba local como un usuario de prueba híbrida alojado en Office 365, puedan iniciar sesión en el cliente de escritorio de Skype Empresarial (si desea usar la autenticación moderna con Skype) y Microsoft Outlook (si desea usar la autenticación moderna con Exchange).
  - Asegúrese de que la configuración SignInOptions de Microsoft Office no esté configurada en su configuración más restrictiva. Para obtener más información, vea [How to allow Office to connect to the Internet](/office365/troubleshoot/access-management/office-feature-disabled).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>¿Qué más necesito saber antes de comenzar?
<a name="BKMK_Whatelse"> </a>

- Todos los escenarios para servidores locales implican la configuración de la autenticación moderna local (de hecho, para Skype Empresarial, hay una lista de las topologías compatibles), de modo que el servidor responsable de la autenticación y la autorización se encuentra en la nube de Microsoft (servicio de token de seguridad de Azure AD, denominado "evoSTS") y la actualización de Azure AD sobre las direcciones URL o espacios de nombres que se usan en la instalación local de Skype Empresarial o Exchange. Por lo tanto, los servidores locales ocupan una dependencia en la nube de Microsoft. Llevar a cabo esta acción podría considerarse una configuración de la "autenticación híbrida".
- Este artículo contiene vínculos a otros artículos que le ayudarán a elegir las topologías de autenticación modernas compatibles (necesarias solo para Skype Empresarial) y artículos de instrucciones que muestran los pasos de configuración o los pasos para deshabilitar la autenticación moderna, en Exchange local y en Skype Empresarial local. Marque esta página como favorita en el explorador si va a necesitar una base de inicio para usar la autenticación moderna en el entorno de servidor.

## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_URLListforMA"> </a>

- [Cómo configurar Exchange Server local para usar la autenticación moderna](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Topologías de Skype Empresarial compatibles con la autenticación moderna](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [Cómo configurar Skype Empresarial local para usar la autenticación moderna](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
