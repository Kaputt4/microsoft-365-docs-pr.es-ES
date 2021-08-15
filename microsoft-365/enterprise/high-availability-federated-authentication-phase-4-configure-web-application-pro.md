---
title: Fase 4 de autenticación federada de alta disponibilidad Configurar servidores proxy de aplicación web
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 'Resumen: configure los servidores proxy de aplicación web para la autenticación federada de alta disponibilidad Microsoft 365 en Microsoft Azure.'
ms.openlocfilehash: cc74fd93fc668094d9627486ac0106447825166e3c69b4c79c36be7ccd6ea107
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53870647"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>Fase 4 de la autenticación federada de alta disponibilidad: Configurar los proxy de aplicación web

En esta fase de implementación de alta disponibilidad Microsoft 365 autenticación federada en los servicios de infraestructura de Azure, se crea un equilibrador de carga interno y dos servidores de AD FS.
  
Debe completar esta fase antes de pasar a [fase 5: Configurar](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)la autenticación federada para Microsoft 365 . Consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas las fases.
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>Crear el equilibrador de carga orientado a Internet en Azure

Debe crear un equilibrador de carga orientado a Internet para que Azure distribuya el tráfico de autenticación de cliente entrante de Internet de forma uniforme entre los dos servidores proxy de aplicación web.
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Consulte [Introducción a Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Cuando haya proporcionado valores de ubicación y grupo de recursos, ejecute el bloque resultante en el símbolo del sistema Azure PowerShell o en powerShell ISE.
  
> [!TIP]
> Para generar bloques de comandos de PowerShell listos para ejecutarse en función de la configuración personalizada, use este [Microsoft Excel de configuración](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

Para mostrar la dirección IP pública asignada al equilibrador de carga orientado a Internet, ejecute estos comandos en el símbolo del sistema Azure PowerShell en el equipo local:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>Determinar el FQDN del servicio de federación y crear registros DNS

Debe determinar el nombre DNS para identificar el nombre del servicio de federación en Internet. Azure AD Conectar configurará Microsoft 365 con este nombre en la fase 5, que pasará a formar parte de la dirección URL que Microsoft 365 envía a los clientes de conexión para obtener un token de seguridad. Un ejemplo es fs.contoso.com (fs significa servicio de federación).
  
Una vez que tenga el servicio de federación FDQN, cree un registro A de dominio DNS público para el servicio de federación FDQN que se resuelva en la dirección IP pública del equilibrador de carga de Azure Internet.
  
|**Nombre**|**Tipo**|**TTL**|**Valor**|
|:-----|:-----|:-----|:-----|
|FDQN del servicio de federación  <br/> |A  <br/> |3600  <br/> |dirección IP pública del equilibrador de carga de Azure Internet (mostrado por el comando **Write-Host** en la sección anterior) <br/> |
   
A continuación le mostramos un ejemplo:
  
|**Nombre**|**Tipo**|**TTL**|**Valor**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
A continuación, agregue un registro de dirección DNS al espacio de nombres DNS privado de la organización que resuelva el FQDN del servicio de federación a la dirección IP privada asignada al equilibrador de carga interno para los servidores de AD FS (tabla I, elemento 4, columna Valor).
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>Crear las máquinas virtuales del servidor proxy de aplicación web en Azure

Use el siguiente bloque de Azure PowerShell comandos para crear las máquinas virtuales para los dos servidores proxy de aplicación web. 
  
Tenga en cuenta que los siguientes Azure PowerShell de comandos usan valores de las tablas siguientes:
  
- Tabla N, para las máquinas virtuales
    
- Tabla R, para los grupos de recursos
    
- Tabla V, para la configuración de la red virtual
    
- Tabla S, para las subredes
    
- Tabla I, para las direcciones IP estáticas
    
- Tabla A, para los conjuntos de disponibilidad
    
Recuerde que ha definido la tabla M en la fase [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Configurar controladores de dominio y tablas R, V, S, I y A en la fase [1: Configurar Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
Después de especificar todos los valores correctos, ejecute el bloque resultante en el símbolo del sistema de Azure PowerShell o en PowerShell ISE.
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Como estas máquinas virtuales son para una aplicación de intranet, no se les asigna una dirección IP pública ni una etiqueta de nombre de dominio DNS, ni se exponen a Internet. Pero esto también quiere decir que no podrá conectarse a estas desde Azure Portal. La opción **Conectar** no estará disponible al ver las propiedades de la máquina virtual. Use el accesorio Conexión de Escritorio remoto u otra herramienta de Escritorio remoto para conectarse a la máquina virtual con su dirección IP privada o nombre DNS de intranet y las credenciales de la cuenta de administrador local.
  
Esta es la configuración completada después de la finalización correcta de esta fase, con los nombres de equipo de marcadores de posición.
  
**Fase 4: Equilibrador de carga con conexión a Internet y servidores proxy de aplicaciones web para la infraestructura de autenticación federada de alta disponibilidad en Azure**

![Fase 4 de la infraestructura de autenticación federada Microsoft 365 alta disponibilidad en Azure con los servidores proxy de aplicaciones web](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>Paso siguiente

Usar [la fase 5: Configurar la autenticación federada para Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) continuar configurando esta carga de trabajo.
  
## <a name="see-also"></a>Consulte también

[Implementar la autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidad federada para el entorno Microsoft 365 de desarrollo y pruebas](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)