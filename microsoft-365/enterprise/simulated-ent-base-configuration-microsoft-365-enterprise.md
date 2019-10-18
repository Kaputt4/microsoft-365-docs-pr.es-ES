---
title: Configuración básica empresarial simulada para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Utilice esta guía de laboratorio de pruebas para crear un entorno de prueba empresarial simulado para Microsoft 365 Enterprise.
ms.openlocfilehash: b0bb241cb475b8ab3bdb0d7ebbbda6ab0936b29d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073100"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="4da8a-103">La configuración básica empresarial simulada</span><span class="sxs-lookup"><span data-stu-id="4da8a-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="4da8a-104">En este artículo se ofrecen instrucciones paso a paso para crear un entorno simplificado para Microsoft 365 Enterprise que incluye:</span><span class="sxs-lookup"><span data-stu-id="4da8a-104">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="4da8a-105">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-105">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="4da8a-106">Una intranet de organización simplificada conectada a Internet, que consta de tres máquinas virtuales en una red virtual de Azure (DC1, APP1 y CLIENTE1).</span><span class="sxs-lookup"><span data-stu-id="4da8a-106">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![La configuración básica empresarial simulada](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="4da8a-108">Puede usar el entorno resultante para probar las características y funcionalidades de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise), con [guías de laboratorio de pruebas](m365-enterprise-test-lab-guides.md) adicionales o por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="4da8a-108">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4da8a-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4da8a-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="4da8a-111">Fase 1: Crear una intranet simulada</span><span class="sxs-lookup"><span data-stu-id="4da8a-111">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="4da8a-112">En esta fase, puede crear una intranet simulada en servicios de infraestructura de Azure que incluya un controlador de dominio de Active Directory Domain Services (AD DS), un servidor de aplicaciones y un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="4da8a-112">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="4da8a-113">Utilizará estos equipos en otras [Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para configurar y demostrar la identidad híbrida y otras funciones.</span><span class="sxs-lookup"><span data-stu-id="4da8a-113">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="4da8a-114">Método 1: Crear la intranet simulada con una plantilla de Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="4da8a-114">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="4da8a-p101">En este método, usará una plantilla de Azure Resource Manager (ARM) para crear la intranet simulada. Las plantillas ARM contienen todas las instrucciones para crear la infraestructura de red de Azure, las máquinas virtuales y su configuración.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="4da8a-117">Antes de implementar la plantilla, lea la [Página de plantilla Léame](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) y prepare la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4da8a-117">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="4da8a-p102">El nombre de dominio DNS público de su entorno de prueba (práctica de prueba.\<su dominio público>). Deberá escribir este nombre en el **campo Nombre de dominio** de la página **Implementación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="4da8a-p103">Un prefijo de etiqueta DNS para las URL de las direcciones IP públicas de sus máquinas virtuales. Tendrá que escribir esta etiqueta en el campo **Prefijo de etiqueta Dns** de la página **implementación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="4da8a-122">Después de leer las instrucciones, haga clic en **Implementar en Azure** en la [página de plantilla Léame](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) para empezar.</span><span class="sxs-lookup"><span data-stu-id="4da8a-122">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="4da8a-123">La intranet simulada creada por la plantilla ARM requiere una suscripción pagada de Azure.</span><span class="sxs-lookup"><span data-stu-id="4da8a-123">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="4da8a-124">Esta la configuración una vez completada la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4da8a-124">Here is your configuration after the template is complete.</span></span>

![Una intranet simulada en servicios de infraestructura de Azure](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="4da8a-126">Método 2: Crear la intranet simulada con Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4da8a-126">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="4da8a-127">En este método, utilizará Windows PowerShell y el módulo de Azure PowerShell para crear la infraestructura de red, las máquinas virtuales y su configuración.</span><span class="sxs-lookup"><span data-stu-id="4da8a-127">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="4da8a-p104">Use este método si quiere obtener experiencia en la creación de elementos de una infraestructura de Azure paso a paso con PowerShell. Puede personalizar los bloques de comandos de PowerShell para la implementación de otras máquinas virtuales en Azure.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="4da8a-130">Paso 1: Crear DC1</span><span class="sxs-lookup"><span data-stu-id="4da8a-130">Step 1: Create DC1</span></span>

<span data-ttu-id="4da8a-131">En este paso, se crea una red virtual de Azure y se agrega DC1, una máquina virtual que es un controlador de dominio para un dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="4da8a-131">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="4da8a-132">En primer lugar, inicie un símbolo del sistema de Windows PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4da8a-132">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4da8a-p105">Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="4da8a-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="4da8a-135">Inicie sesión en su cuenta de Azure con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="4da8a-135">Sign in to your Azure account with the following command.</span></span>
  
```
Connect-AzAccount
```

<span data-ttu-id="4da8a-136">Obtenga su nombre de suscripción mediante el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="4da8a-136">Get your subscription name using the following command.</span></span>
  
```
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="4da8a-p106">Configure su suscripción de Azure. Cambie todo el contenido entrecomillado, incluidos los caracteres < y >, por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="4da8a-p107">Después, cree un nuevo grupo de recursos para su entorno de pruebas empresarial simulado. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="4da8a-p108">Cree el nuevo grupo de recursos con estos comandos. Reemplace todo el contenido entrecomillado, incluidos los caracteres < y >, por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="4da8a-p109">Después, cree una red virtual de laboratorio de pruebas para hospedar la subred de la red corporativa del entorno empresarial simulado y protegerla con un grupo de seguridad de red. Rellene el nombre de su grupo de recursos y ejecute estos comandos en el símbolo del sistema de PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="4da8a-145">Después cree la máquina virtual DC1 y configúrela como controlador de dominio para el **testlab.**\<su dominio público> dominio de AD DS y un servidor DNS para las máquinas virtuales de la red virtual de TestLab.</span><span class="sxs-lookup"><span data-stu-id="4da8a-145">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="4da8a-146">Por ejemplo, si el nombre de dominio público es **<span>contoso</span>.com**, la máquina virtual DC1 será un controlador de dominio para el dominio **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-146">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="4da8a-147">Para crear una máquina virtual de Azure para DC1, indique el nombre de su grupo de recursos y ejecute estos comandos desde el símbolo del sistema de PowerShell en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="4da8a-147">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="4da8a-p111">Se le pedirá un nombre de usuario y una contraseña para la cuenta de administrador local en DC1. Use una contraseña segura y registre el nombre de usuario y la contraseña en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="4da8a-150">Después conéctese a la máquina virtual DC1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-150">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="4da8a-151">En el [Azure Portal](https://portal.azure.com), haga clic en **Grupos de recursos** [nombre del nuevo grupo de recursos nuevo] **> DC1 > Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-151">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="4da8a-p112">En el panel abierto, haga clic en **Descargar archivo RDP**. Abra el archivo DC1.rdp descargado y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="4da8a-154">Especifique el nombre de la cuenta del administrador local de DC1:</span><span class="sxs-lookup"><span data-stu-id="4da8a-154">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="4da8a-155">Para Windows 7:</span><span class="sxs-lookup"><span data-stu-id="4da8a-155">For Windows 7:</span></span>
    
     <span data-ttu-id="4da8a-p113">En el cuadro de diálogo **Seguridad de Windows**, haga clic en **Usar otra cuenta**. En **Nombre de usuario**, escriba **DC1\\**[nombre de la cuenta de administrador local].</span><span class="sxs-lookup"><span data-stu-id="4da8a-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="4da8a-158">Para Windows 8 o Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4da8a-158">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="4da8a-p114">En el cuadro de diálogo **Seguridad de Windows**, haga clic en **Más opciones** y luego en **Usar una cuenta diferente**. En **Nombre de usuario**, escriba **DC1\\**[nombre de la cuenta de administrador local]</span><span class="sxs-lookup"><span data-stu-id="4da8a-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="4da8a-161">En **Contraseña**, escriba la contraseña de la cuenta de administrador local y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-161">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4da8a-162">Cuando se le solicite, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-162">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="4da8a-163">Después, agregue otro disco de datos como nuevo volumen con la letra de unidad F: con este comando en un símbolo del sistema de Windows PowerShell con nivel de administrador en DC1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-163">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="4da8a-p115">Luego, configure DC1 como un controlador de dominio y servidor DNS para el **testlab.**\<su dominio público > dominio. Especifique el nombre de dominio público, quite los caracteres \< y > y después ejecute estos comandos en un símbolo del sistema de Windows PowerShell de nivel de administrador en DC1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="4da8a-p116">Debe especificar una contraseña de administrador de modo seguro. Guarde esta contraseña en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="4da8a-168">Tenga en cuenta que estos comandos pueden tardan unos minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="4da8a-168">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="4da8a-169">Después de que DC1 se reinicie, vuelva a conectarse a la máquina virtual de DC1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-169">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="4da8a-170">En [Azure Portal](https://portal.azure.com), haga clic en **Grupos de recursos >** [nombre del grupo de recursos] **> DC1 > Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-170">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="4da8a-171">Ejecute el archivo DC1.rdp que se descarga y luego haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-171">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="4da8a-p117">En **Seguridad de Windows**, haga clic en **Usar otra cuenta**. En **Nombre de usuario**, escriba **TESTLAB\\**[nombre de la cuenta de administrador local].</span><span class="sxs-lookup"><span data-stu-id="4da8a-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="4da8a-174">En **Contraseña**, escriba la contraseña de la cuenta de administrador local y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-174">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4da8a-175">Cuando se le solicite, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-175">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="4da8a-p118">Después, cree una cuenta de usuario en Active Directory que se usará al iniciar sesión en equipos de miembros del dominio TESTLAB. En un símbolo del sistema de Windows PowerShell con un nivel de administrador, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="4da8a-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="4da8a-p119">Tenga en cuenta que este comando le solicita que proporcione la contraseña de la cuenta User1. Dado que esta cuenta se usará para las conexiones de Escritorio remoto en todos los equipos miembros del dominio TESTLAB, elija una contraseña segura. Anote la contraseña de la cuenta User1 y almacénela en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="4da8a-p120">Después, configure la nueva cuenta User1 como administrador de esquema, empresa o dominio. En un símbolo del sistema de Windows PowerShell con nivel de administrador, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="4da8a-183">Cierre la sesión de Escritorio remoto con DC1 y vuelva a conectarse con la cuenta TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-183">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="4da8a-184">Después, para permitir el tráfico desde la herramienta Ping, ejecute este comando desde un símbolo del sistema de Windows PowerShell con nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="4da8a-184">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="4da8a-185">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="4da8a-185">This is your current configuration.</span></span>
  
![Paso 1 de la configuración básica empresarial simulada](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="4da8a-187">Paso 2: Configurar APP1</span><span class="sxs-lookup"><span data-stu-id="4da8a-187">Step 2: Configure APP1</span></span>

<span data-ttu-id="4da8a-188">En este paso, creará y configurará APP1, que es un servidor de aplicaciones que proporciona inicialmente servicios de uso compartido de archivos y web.</span><span class="sxs-lookup"><span data-stu-id="4da8a-188">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="4da8a-189">Para crear una máquina virtual de Azure para APP1, indique el nombre de su grupo de recursos y ejecute estos comandos desde el símbolo del sistema en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="4da8a-189">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="4da8a-190">Después, conéctese a la máquina virtual de APP1 usando el nombre y la contraseña de la cuenta de administrador local de APP1 y abra un símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-190">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4da8a-191">Para comprobar la comunicación de red y la resolución de nombres entre APP1 y DC1, ejecute el comando **ping dc1.testlab.**\< y compruebe que haya cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="4da8a-191">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="4da8a-192">Después, una la máquina virtual de APP1 al dominio TESTLAB con estos comandos en un símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-192">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="4da8a-193">Recuerde que debe indicar las credenciales de la cuenta de dominio TESTLAB\\User1 después de ejecutar el comando **Add-Computer**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-193">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="4da8a-194">Una vez reiniciado APP1, conéctese a él con la cuenta TESTLAB\\User1 y luego abra un símbolo del sistema de Windows PowerShell con nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="4da8a-194">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4da8a-195">Después, convierta APP1 en un servidor web con este comando en el símbolo del sistema de Windows PowerShell a nivel de administrador en APP1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-195">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="4da8a-196">Por último, cree una carpeta compartida y un archivo de texto dentro de la carpeta en APP1 con estos comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-196">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="4da8a-197">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="4da8a-197">This is your current configuration.</span></span>
  
![Paso 2 de la configuración básica empresarial simulada](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="4da8a-199">Paso 3: Configurar CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-199">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="4da8a-200">En este paso, creará y configurará CLIENT1, que actúa como un equipo de escritorio, una tableta o un portátil típico de la intranet.</span><span class="sxs-lookup"><span data-stu-id="4da8a-200">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="4da8a-p121">El siguiente conjunto de comandos crea CLIENT1 con Windows Server 2016 Datacenter, lo que se puede realizar en todos los tipos de suscripciones de Azure. Si tiene una suscripción de Azure basada en Visual Studio, puede crear CLIENT1 con Windows 10 en [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4da8a-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="4da8a-203">Para crear una máquina virtual de Azure para CLIENT1, indique el nombre de su grupo de recursos y ejecute estos comandos desde el símbolo del sistema en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="4da8a-203">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="4da8a-204">Después, conéctese a la máquina virtual de CLIENT1 usando el nombre y la contraseña de la cuenta de administrador local de CLIENT1, y abra un símbolo del sistema de nivel de administrador de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-204">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4da8a-205">Para comprobar la comunicación de red y la resolución de nombres entre CLIENT1 y DC1, ejecute el comando **ping dc1.testlab.**\< en un símbolo del sistema de Windows PowerShell y compruebe que haya cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="4da8a-205">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="4da8a-206">Después, una la máquina virtual de CLIENT1 al dominio TESTLAB con estos comandos en un símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-206">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="4da8a-207">Recuerde que debe indicar las credenciales de la cuenta de dominio TESTLAB\\User1 después de ejecutar el comando **Add-Computer**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-207">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="4da8a-208">Una vez reiniciado CLIENT1, conéctese a él con el nombre y contraseña de la cuenta TESTLAB\\User1 y luego abra un símbolo del sistema de nivel de administrador de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4da8a-208">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4da8a-209">Después, compruebe que tiene acceso a recursos compartidos de archivos y web en APP1 desde CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-209">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="4da8a-210">En el panel de árbol del Administrador del servidor, haga clic en **Servidor Local**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-210">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="4da8a-211">En **Propiedades de CLIENT1**, haga clic en la opción **Activada** al lado de **Configuración de seguridad mejorada de IE**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-211">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="4da8a-212">En **Configuración de seguridad mejorada de Internet Explorer**, haga clic en **Desactivada** para **Administradores** y **Usuarios** y luego, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-212">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4da8a-213">En la pantalla Inicio, haga clic en **Internet Explorer** y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-213">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4da8a-p122">En la barra de direcciones, escriba **http<span>://</span>app1.testab.**\<su nombre de dominio público>**/** y después presione ENTRAR. Verá la página web predeterminada de Internet Information Services para APP1.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="4da8a-216">En la barra de tareas del escritorio, haga clic en el icono del Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="4da8a-216">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="4da8a-p123">En la barra de direcciones, escriba **\\\\app1\\Files** y luego presione ENTRAR. Debería ver una ventana de carpeta con el contenido de la carpeta compartida Archivos.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="4da8a-p124">En la ventana de la carpeta compartida **Archivos**, haga doble clic en el archivo **Example.txt**. Debería ver el contenido del archivo Example.txt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="4da8a-221">Cierre las ventanas de **example.txt: Bloc de notas** y de la carpeta compartida **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-221">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="4da8a-222">Esta es su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="4da8a-222">This is your current configuration.</span></span>
  
![Paso 3 de la configuración básica empresarial simulada](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscriptions"></a><span data-ttu-id="4da8a-224">Fase 2: cree la suscripción de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4da8a-224">Phase 2: Create your Microsoft 365 E5 subscriptions</span></span>

<span data-ttu-id="4da8a-p125">En esta fase, creará una nueva suscripción de Microsoft 365 E5 que usa un nuevo inquilino de Azure AD, que es independiente de su suscripción de producción. Puede hacer esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="4da8a-p125">In this phase, you create a new Microsoft 365 E5 subscription that use a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="4da8a-227">Usar una suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-227">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="4da8a-p126">La suscripción de prueba de Microsoft 365 E5 es de 30 días, que puede ampliarse fácilmente a 60 días. Cuando la suscripción de prueba expire, debe convertirla en suscripción de pago o crear una nueva suscripción de prueba. Crear nuevas suscripciones de prueba significa que perderá la configuración, que podría incluir escenarios complejos.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p126">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscriptions or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  
- <span data-ttu-id="4da8a-231">Usar una suscripción de producción independiente de Microsoft 365 E5 con un pequeño número de licencias.</span><span class="sxs-lookup"><span data-stu-id="4da8a-231">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="4da8a-p127">Esto supone un coste adicional, pero garantiza que dispone de un entorno de prueba funcional para probar escenarios, características y configuraciones que no caduca. Puede usar el mismo entorno de prueba a largo plazo para pruebas de concepto, demostraciones a compañeros y jefes, y desarrollar aplicaciones y probarlas. Este es el método recomendado.</span><span class="sxs-lookup"><span data-stu-id="4da8a-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

### <a name="use-trial-subscriptions"></a><span data-ttu-id="4da8a-235">Usar suscripciones de prueba</span><span class="sxs-lookup"><span data-stu-id="4da8a-235">Use trial subscriptions</span></span>

<span data-ttu-id="4da8a-236">Primero, siga los pasos los pasos de Fase 2 y Fase 3 del [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) para crear un entorno de desarrollo y prueba ligero de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4da8a-236">First, follow the steps in Phase 2 and Phase 3 of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) to create a lightweight Office 365 dev/test environment.</span></span>

>[!Note]
><span data-ttu-id="4da8a-237">Tenemos que crear una suscripción de prueba de Office 365 para que su entorno de desarrollo y prueba tenga un espacio empresarial de Azure AD separado de cualquier suscripción de pago que tenga actualmente. </span><span class="sxs-lookup"><span data-stu-id="4da8a-237">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="4da8a-238">Esta separación significa que puede agregar y quitar usuarios y grupos en el espacio empresarial de prueba sin que afecte a las suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="4da8a-238">This separation means you can add and remove users and groups in the test tenant without effecting your production subscriptions.</span></span>
>

<span data-ttu-id="4da8a-239">Después agregue la suscripción de prueba de Microsoft 365 E5 y asigne una licencia de Microsoft 365 a su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4da8a-239">Next, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>

1. <span data-ttu-id="4da8a-240">Con una instancia privada de un explorador de Internet, inicie sesión en el Centro de administración de Microsoft 365 en [http://admin.microsoft.com](http://admin.microsoft.com) con sus credenciales de cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4da8a-240">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [http://admin.microsoft.com](http://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="4da8a-241">En la página **Centro de administración de Microsoft 365**, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-241">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="4da8a-242">En la página **Servicios de compra**, busque el elemento **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-242">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="4da8a-243">Mantenga el puntero del ratón sobre dicho elemento y haga clic en **Iniciar prueba gratuita**. </span><span class="sxs-lookup"><span data-stu-id="4da8a-243">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="4da8a-244">En la página de la **Versión de prueba de Microsoft 365 E5**, elija entre recibir una llamada o un mensaje de texto, escriba el número de teléfono y haga clic en **Enviarme un mensaje de texto** o **Llamarme**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-244">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="4da8a-245">En la página **Confirmar pedido**, haga clic en **Probar ahora**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-245">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="4da8a-246">En la página **Recibo del pedido**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-246">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="4da8a-247">En el Centro de administración de Microsoft 365, haga clic en **Usuarios activos** y en su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="4da8a-247">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="4da8a-248">Haga clic en **Editar** para **Licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-248">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="4da8a-249">Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-249">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="4da8a-250">Haga clic en **Guardar > Cerrar > Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-250">Click **Save > Close > Close**.</span></span>

 <span data-ttu-id="4da8a-251">***Si ha completado la fase 3 del*** [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), repita los pasos 8 al 11 del procedimiento anterior para las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).</span><span class="sxs-lookup"><span data-stu-id="4da8a-251">Next, ***if you completed Phase 3 of the*** [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4da8a-252">La suscripción de prueba de Microsoft 365 E5 tiene una duración de 30 días.</span><span class="sxs-lookup"><span data-stu-id="4da8a-252">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="4da8a-253">Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con unas pocas licencias.</span><span class="sxs-lookup"><span data-stu-id="4da8a-253">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="4da8a-254">Su entorno de desarrollo y prueba ahora tiene:</span><span class="sxs-lookup"><span data-stu-id="4da8a-254">Your test environment now has:</span></span>
  
- <span data-ttu-id="4da8a-255">Una suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-255">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="4da8a-256">Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-256">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
### <a name="results"></a><span data-ttu-id="4da8a-257">Resultados</span><span class="sxs-lookup"><span data-stu-id="4da8a-257">Results</span></span>

<span data-ttu-id="4da8a-258">Su entorno de desarrollo y prueba ahora tiene:</span><span class="sxs-lookup"><span data-stu-id="4da8a-258">Your test environment now has:</span></span>
  
- <span data-ttu-id="4da8a-259">Suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-259">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="4da8a-260">Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4da8a-260">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="4da8a-261">Esta es la configuración final.</span><span class="sxs-lookup"><span data-stu-id="4da8a-261">This is your final configuration.</span></span>
  
![Fase 4 de la configuración básica empresarial simulada](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="4da8a-263">Ahora tiene todo preparado para experimentar con otras características de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="4da8a-263">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4da8a-264">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4da8a-264">Next steps</span></span>

<span data-ttu-id="4da8a-265">Explore estos conjuntos adicionales de guías de laboratorio de pruebas:</span><span class="sxs-lookup"><span data-stu-id="4da8a-265">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="4da8a-266">Identidad</span><span class="sxs-lookup"><span data-stu-id="4da8a-266">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="4da8a-267">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="4da8a-267">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="4da8a-268">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="4da8a-268">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="4da8a-269">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da8a-269">See also</span></span>

[<span data-ttu-id="4da8a-270">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4da8a-270">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4da8a-271">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4da8a-271">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4da8a-272">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4da8a-272">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
