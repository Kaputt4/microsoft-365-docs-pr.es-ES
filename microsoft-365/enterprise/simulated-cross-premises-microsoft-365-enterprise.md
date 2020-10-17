---
title: Red virtual entre locales simulada en un entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Resumen: cree una red virtual entre locales simulada en Microsoft Azure como entorno de prueba de Microsoft 365.'
ms.openlocfilehash: ce8b1963e97decc58820bff7b563bb835a843772
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487656"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="c012a-103">Red virtual entre locales simulada en un entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c012a-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="c012a-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="c012a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c012a-p101">En este artículo se le indicará el proceso de creación de un entorno de nube híbrida simulado con Microsoft Azure mediante dos redes virtuales de Azure. Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="c012a-p101">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks. Here is the resulting configuration.</span></span> 
  
![Fase 3 del entorno de pruebas de la red virtual simulada entre locales, con la máquina virtual DC2 en la VNet XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="c012a-108">Esta configuración simula un entorno de producción de nube híbrida de IaaS de Azure y está formada por:</span><span class="sxs-lookup"><span data-stu-id="c012a-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="c012a-109">Una red local simulada y simplificada alojada en una red virtual de Azure (la red virtual TestLab).</span><span class="sxs-lookup"><span data-stu-id="c012a-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="c012a-110">Una red virtual entre locales simulada y alojada en Azure (XPrem).</span><span class="sxs-lookup"><span data-stu-id="c012a-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="c012a-111">Una relación de emparejamiento de VNet entre las dos redes virtuales.</span><span class="sxs-lookup"><span data-stu-id="c012a-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="c012a-112">Un controlador de dominio secundario en la red virtual XPrem.</span><span class="sxs-lookup"><span data-stu-id="c012a-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="c012a-113">Estos componentes constituyen la base a partir de la cual puede:</span><span class="sxs-lookup"><span data-stu-id="c012a-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="c012a-114">Desarrollar y probar las aplicaciones en un entorno simulado de nube de híbrida de IaaS de Azure.</span><span class="sxs-lookup"><span data-stu-id="c012a-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="c012a-115">Crear configuraciones de prueba de los equipos, algunos dentro de la red virtual TestLab y otros dentro de la red virtual XPrem, para simular cargas de trabajo de TI basadas en nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="c012a-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="c012a-116">Existen tres fases principales para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="c012a-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="c012a-117">Configurar la red virtual TestLab.</span><span class="sxs-lookup"><span data-stu-id="c012a-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="c012a-118">Crear la red virtual entre locales.</span><span class="sxs-lookup"><span data-stu-id="c012a-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="c012a-119">Configurar DC2.</span><span class="sxs-lookup"><span data-stu-id="c012a-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c012a-120">Esta configuración necesita una suscripción de pago de Azure.</span><span class="sxs-lookup"><span data-stu-id="c012a-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="c012a-121">Puede usar el entorno resultante para probar las características y funciones de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise) con guías de [entorno de pruebas](m365-enterprise-test-lab-guides.md) adicionales o por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c012a-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c012a-123">Vaya a [Microsoft 365 for Enterprise test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf) para obtener un mapa visual de todos los artículos de la pila de la guía de entorno de pruebas 365 para empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c012a-123">Go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="c012a-124">Fase 1: configurar la red virtual TestLab</span><span class="sxs-lookup"><span data-stu-id="c012a-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="c012a-125">Siga las instrucciones que se indican en **fase 1** de la [configuración base Enterprise](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar los equipos DC1, APP1 y cliente1 en la red virtual de Azure denominada TestLab.</span><span class="sxs-lookup"><span data-stu-id="c012a-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="c012a-126">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="c012a-126">This is your current configuration.</span></span> 
  
![La configuración base de Enterprise simulada en Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="c012a-128">Fase 2: Crear la red virtual XPrem</span><span class="sxs-lookup"><span data-stu-id="c012a-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="c012a-129">En esta fase, creará y configurará la nueva red virtual XPrem y la conectará a la red virtual TestLab mediante un emparejamiento de VNet.</span><span class="sxs-lookup"><span data-stu-id="c012a-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="c012a-130">En primer lugar, inicie un símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="c012a-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c012a-p102">Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="c012a-p102">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="c012a-133">Inicie sesión en su cuenta de Azure con este comando.</span><span class="sxs-lookup"><span data-stu-id="c012a-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="c012a-134">Obtenga su nombre de suscripción mediante este comando.</span><span class="sxs-lookup"><span data-stu-id="c012a-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="c012a-p103">Configure su suscripción de Azure. Reemplace todo lo que haya entre las comillas, incluidos los caracteres \< and > por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="c012a-p103">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="c012a-137">Después, cree la red virtual XPrem y protéjala con un grupo de seguridad de red con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="c012a-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
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

<span data-ttu-id="c012a-138">Después, cree la relación de emparejamiento de VNet entre las redes virtuales TestLab y XPrem con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="c012a-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="c012a-139">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="c012a-139">This is your current configuration.</span></span> 
  
![Fase 2 del entorno de pruebas de la red virtual simulada entre locales, con la relación de emparejamiento de VNet y la VNet XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="c012a-141">Fase 3: Configurar DC2</span><span class="sxs-lookup"><span data-stu-id="c012a-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="c012a-142">En esta fase, creará la máquina virtual de DC2 en la red virtual XPrem y, a continuación, la configurará como un controlador de dominio de réplica.</span><span class="sxs-lookup"><span data-stu-id="c012a-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="c012a-p104">En primer lugar, cree una máquina virtual para DC2. Ejecute estos comandos desde el símbolo del sistema de Azure PowerShell en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="c012a-p104">First, create a virtual machine for DC2. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="c012a-145">Después, conéctese a la nueva máquina virtual de DC2 desde [Azure Portal](https://portal.azure.com) con el nombre de cuenta y la contraseña del administrador local.</span><span class="sxs-lookup"><span data-stu-id="c012a-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="c012a-p105">Después, configure una regla de Firewall de Windows para permitir el tráfico durante la prueba de conectividad básica. Desde un símbolo del sistema de Windows PowerShell con el nivel de administrador en DC2, ejecute estos comandos:</span><span class="sxs-lookup"><span data-stu-id="c012a-p105">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing. From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="c012a-p106">El comando ping debería devolver cuatro respuestas correctas de la dirección IP 10.0.0.4. Esta prueba para comprobar el tráfico de la relación de emparejamiento de VNet.</span><span class="sxs-lookup"><span data-stu-id="c012a-p106">The ping command should result in four successful replies from IP address 10.0.0.4. This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="c012a-150">Después, agregue el disco de datos adicional como un volumen nuevo con la letra de unidad F: con estos comandos desde el símbolo del sistema de Windows PowerShell en DC2.</span><span class="sxs-lookup"><span data-stu-id="c012a-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="c012a-p107">Después, configure DC2 como un controlador de dominio de réplica para el dominio corp.contoso.com. Ejecute estos comandos desde el símbolo del sistema de Windows PowerShell en DC2.</span><span class="sxs-lookup"><span data-stu-id="c012a-p107">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain. Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="c012a-153">Tenga en cuenta que se le pedirá que proporcione la contraseña de CORP\\User1 y una contraseña del Modo de restauración de servicios de directorio (DSRM), y que reinicie DC2.</span><span class="sxs-lookup"><span data-stu-id="c012a-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="c012a-p108">Una vez que la red virtual XPrem tenga su propio servidor DNS (DC2), deberá configurarla para que utilice este servidor DNS. Ejecute estos comandos desde el símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="c012a-p108">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server. Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="c012a-p109">Desde el equipo local, vaya a Azure Portal y conéctese a DC1 con las credenciales de CORP\\User1. Para configurar el dominio CORP para que usuarios y equipos usen el controlador de dominio local para la autenticación, ejecute estos comandos desde un símbolo del sistema de Windows PowerShell de nivel de administrador en DC1.</span><span class="sxs-lookup"><span data-stu-id="c012a-p109">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials. To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="c012a-158">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="c012a-158">This is your current configuration.</span></span> 
  
![Fase 3 del entorno de pruebas de la red virtual simulada entre locales, con la máquina virtual DC2 en la VNet XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="c012a-160">Ya puede probar el entorno simulado de nube híbrida de Azure.</span><span class="sxs-lookup"><span data-stu-id="c012a-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="c012a-161">Ya está listo para experimentar con características adicionales de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="c012a-161">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c012a-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c012a-162">Next steps</span></span>

<span data-ttu-id="c012a-163">Explore estos conjuntos adicionales de guías de laboratorio de pruebas:</span><span class="sxs-lookup"><span data-stu-id="c012a-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="c012a-164">Identidad</span><span class="sxs-lookup"><span data-stu-id="c012a-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="c012a-165">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c012a-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="c012a-166">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="c012a-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="c012a-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="c012a-167">See also</span></span>

[<span data-ttu-id="c012a-168">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c012a-168">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c012a-169">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c012a-169">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c012a-170">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c012a-170">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
