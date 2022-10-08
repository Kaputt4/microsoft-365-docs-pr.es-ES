---
title: Cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- scotvorg
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida (HMA), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 675998ee8a71817cc81f3ee9d8b1c8ae05aa0ec5
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198435"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna, es un método de administración de identidades que ofrece autenticación y autorización de usuario más seguras, está disponible para Skype Empresarial servidor local y exchange server local, y híbridos Skype Empresarial de dominio dividido.

> [!IMPORTANT]
> ¿Desea obtener más información sobre la autenticación moderna (MA) y por qué podría preferir usarla en su empresa u organización? Consulte [este documento](hybrid-modern-auth-overview.md) para obtener información general. Si necesita saber qué topologías de Skype Empresarial se admiten con MA, esto se documenta aquí.

**Antes de empezar**, uso estos términos:

- Autenticación moderna (MA)

- Autenticación moderna híbrida (HMA)

- Exchange local (EXCH)

- Exchange Online (EXO)

- Skype Empresarial local (SFB)

- Skype Empresarial en línea (SFBO)

Además, si un gráfico de este artículo tiene un objeto atenuado o atenuado, significa que el elemento que se muestra en gris **no se** incluye en la configuración específica de MA.

## <a name="read-the-summary"></a>Leer el resumen

Este resumen desglosa el proceso en pasos que, de lo contrario, podrían perderse durante la ejecución y es bueno para que una lista de comprobación general realice un seguimiento de dónde se encuentra en el proceso.

1. En primer lugar, asegúrese de cumplir todos los requisitos previos.

1. Dado que muchos **requisitos previos** son comunes tanto para Skype Empresarial como para Exchange, [consulte el artículo de información general de la lista de comprobación previa a la consulta](hybrid-modern-auth-overview.md). Haga esto  *antes*  de comenzar cualquiera de los pasos de este artículo.

1. Recopile la información específica de HMA que necesitará en un archivo o OneNote.

1. Active autenticación moderna para EXO (si aún no está activada).

1. Active la autenticación moderna para SFBO (si aún no está activada).

1. Active la autenticación moderna híbrida para Exchange local.

1. Active la autenticación moderna híbrida para Skype Empresarial local.

Estos pasos encienden MA para SFB, SFBO, EXCH y EXO, es decir, todos los productos que pueden participar en una configuración HMA de SFB y SFBO (incluidas las dependencias de EXCH/EXO). En otras palabras, si los usuarios están hospedados o tienen buzones creados en cualquier parte del híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB), el producto terminado tendrá el siguiente aspecto:

![Una topología mixta de HMA de Skype Empresarial 6 tiene MA en las cuatro ubicaciones posibles.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

Como puede ver, hay cuatro lugares diferentes para activar MA! Para obtener la mejor experiencia de usuario, se recomienda activar MA en las cuatro ubicaciones. Si no puede activar MA en todas estas ubicaciones, ajuste los pasos para que active ma solo en las ubicaciones necesarias para su entorno.

Consulte el [tema Compatibilidad para Skype Empresarial con MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) para obtener las topologías admitidas.

> [!IMPORTANT]
> Compruebe que ha cumplido todos los requisitos previos antes de empezar. Encontrará esa información en [Introducción a la autenticación moderna híbrida y requisitos previos](hybrid-modern-auth-overview.md).

## <a name="collect-all-hma-specific-info-youll-need"></a>Recopilar toda la información específica de HMA que necesitará

Después de comprobar que cumple los [requisitos previos](hybrid-modern-auth-overview.md) para usar la autenticación moderna (consulte la nota anterior), debe crear un archivo para contener la información que necesitará para configurar HMA en los pasos que se indican a continuación. Ejemplos usados en este artículo:

- **Dominio SIP/SMTP**

  - Ej. contoso.com (está federado con Office 365)

- **Identificación del inquilino**

  - GUID que representa el inquilino de Office 365 (en el inicio de sesión de contoso.onmicrosoft.com).

- **Direcciones URL de servicio web de SFB 2015 CU5**

Necesitará direcciones URL de servicio web internas y externas para todos los grupos de SfB 2015 implementados. Para obtenerlos, ejecute lo siguiente desde Skype Empresarial Shell de administración:

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ej. Interna: https://lyncwebint01.contoso.com

- Ej. Externos: https://lyncwebext01.contoso.com

Si usa un servidor Standard Edition, la dirección URL interna estará en blanco. En este caso, use el fqdn del grupo para la dirección URL interna.

## <a name="turn-on-modern-authentication-for-exo"></a>Activar la autenticación moderna para EXO

Siga las instrucciones que se indican aquí: [Exchange Online: Cómo habilitar el inquilino para la autenticación moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>Activar la autenticación moderna para SFBO

Siga las instrucciones que se indican aquí: [Skype Empresarial Online: Habilitar el inquilino para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Activar la autenticación moderna híbrida para Exchange local

Siga las instrucciones que se indican aquí: [Configuración de Exchange Server local para usar la autenticación moderna híbrida](configure-exchange-server-for-hybrid-modern-authentication.md).

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Activar la autenticación moderna híbrida para Skype Empresarial local

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Incorporación de direcciones URL de servicio web locales como SPN en Azure Active Directory

Ahora tendrá que ejecutar comandos para agregar las direcciones URL (recopiladas anteriormente) como entidades de servicio en SFBO.

> [!NOTE]
> Los nombres de entidad de seguridad de servicio (SPN) identifican los servicios web y los asocian a una entidad de seguridad (como un nombre de cuenta o grupo) para que el servicio pueda actuar en nombre de un usuario autorizado. Los clientes que se autentican en un servidor usan la información contenida en los SPN.

1. En primer lugar, conéctese a Azure Active Directory (Azure AD) con [estas instrucciones](/powershell/azure/active-directory/overview).

2. Ejecute este comando local para obtener una lista de direcciones URL del servicio web SFB.

   Tenga en cuenta que AppPrincipalId comienza por `00000004`. Esto corresponde a Skype Empresarial Online.

   Tome nota de (y captura de pantalla para la comparación posterior) de la salida de este comando, que incluirá una dirección URL de SE y WS, pero principalmente consta de SPN que comienzan por `00000004-0000-0ff1-ce00-000000000000/`.

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
   ```

3. Si faltan las direcciones URL de SFB internas **o** externas del entorno local (por ejemplo, https://lyncwebint01.contoso.com y https://lyncwebext01.contoso.com) tendremos que agregar esos registros específicos a esta lista).

    Asegúrese de reemplazar  *las direcciones URL de ejemplo* siguientes por las direcciones URL reales en los comandos Agregar.

    ```powershell
    $x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
    $x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
    $x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
    Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
    ```

4. Compruebe que los nuevos registros se agregaron ejecutando de nuevo el comando **Get-MsolServicePrincipal** del paso 2 y examinando la salida. Compare la lista o captura de pantalla de antes con la nueva lista de SPN. También puede realizar una captura de pantalla de la nueva lista de los registros. Si se ha realizado correctamente, verá las dos direcciones URL nuevas en la lista. En nuestro ejemplo, la lista de SPN ahora incluirá las direcciones https://lyncwebint01.contoso.com URL específicas y https://lyncwebext01.contoso.com/.

### <a name="create-the-evosts-auth-server-object"></a>Creación del objeto de servidor de autenticación de EvoSTS

Ejecute el siguiente comando en el Shell de administración de Skype Empresarial.

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Habilitación de la autenticación moderna híbrida

Este es el paso que activa realmente MA. Todos los pasos anteriores se pueden ejecutar con antelación sin cambiar el flujo de autenticación del cliente. Cuando esté listo para cambiar el flujo de autenticación, ejecute este comando en el Shell de administración de Skype Empresarial.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verificar

Una vez que habilite HMA, el siguiente inicio de sesión de un cliente usará el nuevo flujo de autenticación. Tenga en cuenta que al activar HMA no se desencadenará una nueva autenticación para ningún cliente. Los clientes vuelven a autenticarse en función de la duración de los tokens de autenticación o de los certificados que tengan.

Para probar que HMA funciona después de habilitarlo, cierre la sesión de un cliente de Windows SFB de prueba y asegúrese de hacer clic en "Eliminar mis credenciales". Vuelva a iniciar sesión. El cliente ahora debe usar el flujo de autenticación moderna y el inicio de sesión ahora incluirá una **solicitud de Office 365** para una cuenta "Profesional o educativa", que se ve justo antes de que el cliente se pone en contacto con el servidor e inicia sesión.

También debe comprobar la "Información de configuración" de los clientes de Skype Empresarial para obtener una "autoridad de OAuth". Para hacerlo en el equipo cliente, mantenga presionada la tecla CTRL al mismo tiempo que haga clic con el botón derecho en el icono de Skype Empresarial en la bandeja de notificaciones de Windows. Haga clic en **Información de configuración** en el menú que aparece. En la ventana "información de configuración de Skype Empresarial" que aparecerá en el escritorio, busque lo siguiente:

:::image type="content" alt-text="La información de configuración de un cliente de Skype Empresarial mediante la autenticación moderna muestra una dirección URL de autoridad de OAUTH de Lync y EWS de https://login.windows.net/common/oauth2/authorize." source="../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png":::

También debe mantener presionada la tecla CTRL al mismo tiempo que hace clic con el botón derecho en el icono del cliente de Outlook (también en la bandeja notificaciones de Windows) y haga clic en "Estado de conexión". Busque la dirección SMTP del cliente en un tipo AuthN de "Portador\*", que representa el token de portador usado en OAuth.

## <a name="related-articles"></a>Artículos relacionados

[Vuelva a vincular a la introducción a la autenticación moderna](hybrid-modern-auth-overview.md).

¿Necesita saber cómo usar la autenticación moderna para los clientes de Skype Empresarial? Aquí tenemos pasos: [Introducción a la autenticación moderna híbrida y requisitos previos para usarlo con servidores de Exchange y Skype Empresarial locales](./hybrid-modern-auth-overview.md).
