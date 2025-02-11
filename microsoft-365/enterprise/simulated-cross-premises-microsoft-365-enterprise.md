---
title: Red virtual entre locales simulada en un entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Resumen: cree una red virtual entre locales simulada en Microsoft Azure como entorno de prueba de Microsoft 365.'
ms.openlocfilehash: de27e1fa1de5c2fa107bb5dffa1c3d77c549299a
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207652"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Red virtual entre locales simulada en un entorno de prueba de Microsoft 365

*Esta guía de laboratorio de pruebas se puede usar para Microsoft 365 para entornos de prueba empresariales y Office 365 Enterprise.*

This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks. Here is the resulting configuration. 
  
![Fase 3 del entorno de prueba de red virtual entre locales simulado, con la máquina virtual DC2 en la red virtual XPrem.](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Esta configuración simula un entorno de producción de nube híbrida de IaaS de Azure y está formada por:
  
- Una red local simulada y simplificada alojada en una red virtual de Azure (la red virtual TestLab).
    
- Una red virtual entre locales simulada y alojada en Azure (XPrem).
    
- Una relación de emparejamiento de VNet entre las dos redes virtuales.
    
- Un controlador de dominio secundario en la red virtual XPrem.
    
Estos componentes constituyen la base a partir de la cual puede: 
  
- Desarrollar y probar las aplicaciones en un entorno simulado de nube de híbrida de IaaS de Azure.
    
- Crear configuraciones de prueba de los equipos, algunos dentro de la red virtual TestLab y otros dentro de la red virtual XPrem, para simular cargas de trabajo de TI basadas en nube híbrida.
    
Existen tres fases principales para configurar el entorno de pruebas:
  
1. Configurar la red virtual TestLab.
    
2. Crear la red virtual entre locales.
    
3. Configurar DC2.
    
> [!NOTE]
> Esta configuración necesita una suscripción de pago de Azure. 

Puede usar el entorno resultante para probar las características y la funcionalidad de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise) con guías de [laboratorio de pruebas](m365-enterprise-test-lab-guides.md) adicionales o por su cuenta.

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Vaya a [La pila de la guía del laboratorio de pruebas de Microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf) para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas.

## <a name="phase-1-configure-the-testlab-virtual-network"></a>Fase 1: configurar la red virtual TestLab

Siga las instrucciones que se indican en **fase 1** de la [configuración base Enterprise](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar los equipos DC1, APP1 y cliente1 en la red virtual de Azure denominada TestLab.
  
Esta es su configuración actual. 
  
![Configuración base de empresa simulada en Azure.](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>Fase 2: Crear la red virtual XPrem

En esta fase, creará y configurará la nueva red virtual XPrem y la conectará a la red virtual TestLab mediante un emparejamiento de VNet.
  
En primer lugar, inicie un símbolo del sistema de Azure PowerShell en el equipo local.
  
> [!NOTE]
> The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/). 
  
Inicie sesión en su cuenta de Azure con este comando.
  
```powershell
Connect-AzAccount
```

Obtenga su nombre de suscripción mediante este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct names.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Después, cree la red virtual XPrem y protéjala con un grupo de seguridad de red con estos comandos.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Después, cree la relación de emparejamiento de VNet entre las redes virtuales TestLab y XPrem con estos comandos.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

Esta es su configuración actual. 
  
![Fase 2 del entorno de prueba de red virtual entre locales simulado, con la red virtual XPrem y la relación de emparejamiento de red virtual.](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>Fase 3: Configurar DC2

En esta fase, creará la máquina virtual de DC2 en la red virtual XPrem y, a continuación, la configurará como un controlador de dominio de réplica.
  
First, create a virtual machine for DC2. Run these commands at the Azure PowerShell command prompt on your local computer.
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Después, conéctese a la nueva máquina virtual de DC2 desde [Azure Portal](https://portal.azure.com) con el nombre de cuenta y la contraseña del administrador local.
  
Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing. From an administrator-level Windows PowerShell command prompt on DC2, run these commands. 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

The ping command should result in four successful replies from IP address 10.0.0.4. This is a test of traffic across the VNet peering relationship. 
  
Después, agregue el disco de datos adicional como un volumen nuevo con la letra de unidad F: con estos comandos desde el símbolo del sistema de Windows PowerShell en DC2.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Next, configure DC2 as a replica domain controller for the corp.contoso.com domain. Run these commands from the Windows PowerShell command prompt on DC2.
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

Tenga en cuenta que se le pedirá que proporcione la contraseña de CORP\\User1 y una contraseña del Modo de restauración de servicios de directorio (DSRM), y que reinicie DC2. 
  
Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server. Run these commands from the Azure PowerShell command prompt on your local computer.
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials. To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

Esta es su configuración actual. 
  
![Fase 3 del entorno de prueba de red virtual entre locales simulado, con la máquina virtual DC2 en la red virtual XPrem.](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Ya puede probar el entorno simulado de nube híbrida de Azure.
  
Ya está listo para experimentar con características adicionales de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Pasos siguientes

Explore estos conjuntos adicionales de guías de laboratorio de pruebas:
  
- [Identidad](m365-enterprise-test-lab-guides.md#identity)
- [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protección de la información](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)