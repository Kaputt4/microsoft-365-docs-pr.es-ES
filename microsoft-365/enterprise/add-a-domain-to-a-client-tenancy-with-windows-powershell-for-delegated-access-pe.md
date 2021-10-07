---
title: Agregar un dominio a un arrendamiento de cliente con Windows PowerShell asociados de DAP
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Summary: Use PowerShell for Microsoft 365 to add an alternate domain name to an existing customer tenant.'
ms.openlocfilehash: 1a121407ebe242747a693084289e972e56e1cbee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170528"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados con permiso de acceso delegado (DAP)

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede crear y asociar nuevos dominios con el arrendamiento del cliente con PowerShell para Microsoft 365 más rápido que usar el Centro de administración de Microsoft 365.

Los asociados con permiso de acceso delegado (DAP) son asociados de sindicación y proveedor de soluciones en la nube (CSP). Con frecuencia son los proveedores de red o de telecomunicaciones para otras compañías. Agrupan Microsoft 365 suscripciones en sus ofertas de servicio a sus clientes. Cuando venden una suscripción Microsoft 365, se les conceden automáticamente permisos Administrar en nombre de (AOBO) a las tenencias del cliente para que puedan administrar e informar sobre las tenencias del cliente.
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Los procedimientos de este tema requieren que se conecte a [Conectar a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md).

Necesita también las credenciales del administrador de inquilinos del asociado.

También necesitará la siguiente información:

- Necesitará el nombre de dominio completo (FQDN) que desea el cliente.

- Necesita el **TenantId** del cliente.

- El FQDN debe estar registrado con un registrador del servicio de nombres de dominio (DNS), como GoDaddy. Para obtener más información sobre cómo registrar públicamente un nombre de dominio, vea [Cómo comprar un nombre de dominio](../admin/get-help-with-domains/buy-a-domain-name.md).

- Necesita saber cómo agregar un registro TXT a la zona DNS registrada para su registrador DNS. Para obtener más información sobre cómo agregar un registro TXT, vea [Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Si esos procedimientos no funcionan, necesitará encontrar los procedimientos de su registrador DNS.

## <a name="create-domains"></a>Crear dominios

 Sus clientes probablemente le pedirán crear dominios adicionales para asociar con su arrendamiento, ya que no desean que el dominio predeterminado \<domain>.onmicrosoft.com sea el dominio principal que represente su identidad corporativa en el mundo. En este procedimiento se explica cómo crear un nuevo dominio asociado con el arrendamiento de su cliente.

> [!NOTE]
> Para realizar algunas de estas operaciones, la cuenta de  administrador de  partners con la que inicia sesión debe establecerse en Administración completa para la configuración Asignar acceso administrativo a empresas compatibles que se encuentra en los detalles de la cuenta de administrador en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">el Centro de administración de Microsoft 365</a>. Para obtener más información sobre cómo administrar roles de administrador de partners, vea [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).

### <a name="create-the-domain-in-azure-active-directory"></a>Crear el dominio en Azure Active Directory

Este comando crea el dominio en Azure Active Directory, pero no lo asocia al dominio registrado públicamente. Esto se produce cuando se demuestra que es el propietario del dominio registrado públicamente en Microsoft Microsoft 365 para empresas.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Obtener los datos para la verificación del registro TXT de DNS

 Microsoft 365 generará los datos específicos que necesita colocar en el registro de verificación TXT dns. Para obtener los datos, ejecute este comando.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Se obtendrá el siguiente resultado:

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> Necesitará este texto para crear el registro TXT en la zona DNS registrada públicamente. Asegúrese de copiarlo y guardarlo.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Agregar un registro TXT a la zona DNS registrada públicamente

Antes Microsoft 365 empezar a aceptar el tráfico que se dirige al nombre de dominio registrado públicamente, debe demostrar que es propietario y tiene permisos de administrador en el dominio. Demuestre que el dominio le pertenece mediante la creación de un registro TXT en el dominio. Un registro TXT no hace nada en su dominio y puede eliminarse una vez que se establezca su propiedad del dominio. Para crear los registros TXT, siga los procedimientos de [Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Si esos procedimientos no funcionan, necesitará encontrar los procedimientos de su registrador DNS.

Confirme la creación correcta del registro TXT mediante nslookup. Siga esta sintaxis.

```console
nslookup -type=TXT <FQDN of registered domain>
```

Se obtendrá el siguiente resultado:

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Validar la propiedad del dominio en Microsoft 365

En este último paso, se valida para Microsoft 365 que es propietario del dominio registrado públicamente. Después de este paso, Microsoft 365 empezará a aceptar tráfico enrutado al nuevo nombre de dominio. Para completar la creación del dominio y el proceso de registro, ejecute este comando.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Este comando no devolverá ningún resultado, por lo tanto, para confirmar que funcionó, ejecute este comando.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Se mostrará un resultado semejante a

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>Consulte también

[Ayuda para asociados](https://go.microsoft.com/fwlink/p/?LinkID=533477)
