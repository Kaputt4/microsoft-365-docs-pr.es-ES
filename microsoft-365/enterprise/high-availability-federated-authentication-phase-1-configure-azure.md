---
title: Autenticación federada de alta disponibilidad Fase 1 Configuración de Azure
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Resumen: configure la infraestructura de Microsoft Azure para hospedar la autenticación federada de alta disponibilidad para Microsoft 365.'
ms.openlocfilehash: ee8e3d22f97bf26479d8aa4013e98b2d62d15cd7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68171133"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Fase 1 de la autenticación federada de alta disponibilidad: Configurar Azure

En esta fase, creará los grupos de recursos, la red virtual (VNet) y los conjuntos de disponibilidad en Azure que hospedarán las máquinas virtuales en las fases 2, 3 y 4. Debe completar esta fase para poder pasar a la [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Consulte Implementación de la [autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas las fases.
  
Azure debe aprovisionarse con estos componentes básicos:
  
- Grupos de recursos
    
- Una red virtual (VNET) de Azure entre locales con subredes para hospedar las máquinas virtuales de Azure
    
- Grupos de seguridad de red para realizar el aislamiento de subredes
    
- Conjuntos de disponibilidad
    
## <a name="configure-azure-components"></a>Configurar componentes de Azure

Antes de empezar a configurar los componentes de Azure, rellene las tablas siguientes. Para ayudarle en los procedimientos de configuración de Azure, imprima esta sección y anote la información necesaria, o bien copie esta sección en un documento y rellénelo. Para la configuración de la red virtual, rellene la tabla V.
  
|**Elemento**|**Opción de configuración**|**Descripción**|**Valor**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Nombre de VNET  <br/> |Nombre que se asignará a la red virtual (por ejemplo, FedAuthNet).  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Ubicación de la VNET  <br/> |Centro de datos regional de Azure que contendrá la red virtual.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Dirección IP del dispositivo VPN  <br/> |Dirección IPv4 pública de la interfaz del dispositivo VPN en Internet.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Espacio de direcciones de la VNET  <br/> |El espacio de direcciones de la red virtual. Colabore con su departamento de TI para determinar este espacio de direcciones.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Clave compartida IPsec  <br/> |A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabla V: Configuración de la red virtual entre locales**
  
Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.
  
For the first three subnets, specify a name and a single IP address space based on the virtual network address space. For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:
  
1. Establezca los bits variables en el espacio de direcciones de la VNET en 1, hasta los bits usados por la subred de la puerta de enlace y, después, establezca el resto de los bits en 0.
    
2. Convierta los bits resultantes a decimales y expréselo como un espacio de direcciones con la longitud de prefijo establecida en el tamaño de la subred de puerta de enlace.
    
Consulte [Calculadora de espacio de direcciones para subredes de puerta de enlace de Azure](address-space-calculator-for-azure-gateway-subnets.md) para obtener un bloque de comandos de PowerShell y una aplicación de consola de C# o Python que realice este cálculo de forma automática.
  
Trabaje con su departamento de TI para determinar estos espacios de direcciones a partir del espacio de direcciones de la red virtual.
  
|**Elemento**|**Nombre de la subred**|**Espacio de direcciones de la subred**|**Finalidad**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Subred usada por el controlador de dominio Servicios de dominio de Active Directory (AD DS) y las máquinas virtuales (VM) del servidor de sincronización de directorios.  <br/> |
|2.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Subred usada por las máquinas virtuales de AD FS.  <br/> |
|3.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Subred usada por las máquinas virtuales del proxy de aplicación web.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Subred usada por las máquinas virtuales de la puerta de enlace de Azure.  <br/> |
   
 **Tabla S: Subredes de la red virtual**
  
Ahora, rellene la Tabla I para las direcciones IP estáticas asignadas a las máquinas virtuales y a las instancias del equilibrador de carga.
  
|**Elemento**|**Objetivo**|**Dirección IP en la subred**|**Valor**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Dirección IP estática del primer controlador de dominio  <br/> |La cuarta dirección IP posible del espacio de direcciones de la subred definida en el elemento 1 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Dirección IP estática del segundo controlador de dominio  <br/> |La quinta dirección IP posible del espacio de direcciones de la subred definida en el elemento 1 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Dirección IP estática del servidor de sincronización de directorios  <br/> |La sexta dirección IP posible del espacio de direcciones de la subred definida en el elemento 1 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Dirección IP estática del equilibrador de carga interno para los servidores de AD FS  <br/> |La cuarta dirección IP posible del espacio de direcciones de la subred definida en el elemento 2 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Dirección IP estática del primer servidor de AD FS  <br/> |La quinta dirección IP posible del espacio de direcciones de la subred definida en el elemento 2 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |Dirección IP estática del segundo servidor de AD FS  <br/> |La sexta dirección IP posible del espacio de direcciones de la subred definida en el elemento 2 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |Dirección IP estática del primer servidor proxy de aplicación web  <br/> |La cuarta dirección IP posible del espacio de direcciones de la subred definida en el elemento 3 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |Dirección IP estática del segundo servidor proxy de aplicación web  <br/> |La quinta dirección IP posible del espacio de direcciones de la subred definida en el elemento 3 de la Tabla S.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabla I: Direcciones IP estáticas en la red virtual**
  
Para dos servidores de Sistema de nombres de dominio (DNS) en la red local que quiera usar al configurar de manera inicial los controladores de dominio en la red virtual, rellene la Tabla D. Colabore con su departamento de TI para determinar esta lista.
  
|**Elemento**|**Nombre descriptivo del servidor DNS**|**Dirección IP del servidor DNS**|
|:-----|:-----|:-----|
|1.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabla D: Servidores DNS locales**
  
Para enrutar paquetes de la red entre locales a la red de la organización a través de la conexión VPN de sitio a sitio, debe configurar la red virtual con una red local que tenga una lista de los espacios de direcciones (en notación CIDR) para todas las ubicaciones accesibles en la red local de la organización. La lista de espacios de direcciones que definen la red local tiene que ser única y no puede superponerse con el espacio de direcciones usado para otras redes virtuales ni otras redes locales.
  
For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.
  
|**Elemento**|**Espacio de direcciones de la red local**|
|:-----|:-----|
|1.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabla L: Prefijos de direcciones para la red local**
  
Ahora vamos a empezar a compilar la infraestructura de Azure para hospedar la autenticación federada para Microsoft 365.
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Consulte [Introducción a Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Primero, abra un símbolo del sistema de Azure PowerShell e inicie sesión con su cuenta.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Para generar bloques de comandos de PowerShell listos para ejecutarse en función de la configuración personalizada, use este [libro de configuración de Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

Obtenga su nombre de suscripción mediante el comando siguiente.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Para versiones anteriores de Azure PowerShell, use este comando en su lugar.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Configure su suscripción de Azure. Reemplace todo entre comillas, incluidos los \< and > caracteres, por el nombre correcto.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Next, create the new resource groups. To determine a unique set of resource group names, use this command to list your existing resource groups.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Rellene la tabla siguiente para el conjunto de nombres de grupos de recursos únicos.
  
|**Elemento**|**Nombre del grupo de recursos**|**Objetivo**|
|:-----|:-----|:-----|
|1.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Controladores de dominio  <br/> |
|2.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Servidores de AD FS  <br/> |
|3.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Servidores proxy de aplicación web  <br/> |
|4.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |Elementos de la infraestructura  <br/> |
   
 **Tabla R: Grupos de recursos**
  
Cree el grupo de recursos con estos comandos.
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Después, cree la red virtual de Azure y sus subredes.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

A continuación, creará grupos de seguridad de red para cada subred que tenga máquinas virtuales. Para realizar el aislamiento de la subred, puede agregar reglas para tipos específicos de tráfico permitido o denegado para el grupo de seguridad de red de una subred.
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Después, use estos comandos para crear las puertas de enlace para la conexión VPN de sitio a sitio.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> La autenticación federada de los usuarios individuales no se basa en los recursos locales. Sin embargo, si esta conexión VPN de sitio a sitio deja de estar disponible, los controladores de dominio de la red virtual no recibirán actualizaciones de las cuentas de usuario y los grupos realizados en Active Directory local Domain Services. Para asegurarse de que esto no sucede, puede configurar la alta disponibilidad para la conexión VPN de sitio a sitio. Para obtener más información, consulte [Conectividad de red virtual a red virtual y con alta disponibilidad entre locales](/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
El paso siguiente es anotar la dirección IPv4 pública de Azure VPN Gateway para la red virtual después de ejecutar este comando:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).
  
Para configurar el dispositivo VPN local necesita lo siguiente:
  
- La dirección IPv4 pública de Azure VPN Gateway.
    
- La clave precompartida IPsec para la conexión VPN de sitio a sitio (Tabla V, elemento 5, columna Valor).
    
Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.
  
Después, defina los nombres de los tres conjuntos de disponibilidad. Rellene la Tabla A. 
  
|**Elemento**|**Objetivo**|**Nombre del conjunto de disponibilidad**|
|:-----|:-----|:-----|
|1.  <br/> |Controladores de dominio  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Servidores de AD FS  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Servidores proxy de aplicación web  <br/> |![Línea.](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabla A: Conjuntos de disponibilidad**
  
Necesitará estos nombres al crear las máquinas virtuales en las fases 2, 3 y 4.
  
Cree los conjuntos de disponibilidad con estos comandos de Azure PowerShell.
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

Esta es la configuración que se muestra después de la finalización correcta de esta fase.
  
**Fase 1: La infraestructura de Azure para la autenticación federada de alta disponibilidad para Microsoft 365**

![Fase 1 de la autenticación federada de Microsoft 365 de alta disponibilidad en Azure con la infraestructura de Azure.](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Paso siguiente

Use [Fase 2: Configurar controladores de dominio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) para continuar con la configuración de esta carga de trabajo.
  
## <a name="see-also"></a>Consulta también

[Implementar la autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidad federada para el entorno de desarrollo y pruebas de Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)

[Descripción de los modelos de identidad de Microsoft 365](deploy-identity-solution-identity-model.md)