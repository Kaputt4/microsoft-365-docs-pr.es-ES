---
title: Identidad federada para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Resumen: Configure la autenticación federada para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487689"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="89b0b-103">Identidad federada para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89b0b-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="89b0b-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="89b0b-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="89b0b-p101">Microsoft 365 admite la identidad federada. Esto significa que, en lugar de realizar la validación de las credenciales él mismo, Microsoft 365 dirige al usuario que se conecta a un servidor de autenticación federada en el que Microsoft 365 confía. Si las credenciales del usuario son correctas, el servidor de autenticación federada emite un token de seguridad que el cliente envía luego a Microsoft 365 como prueba de autenticación. La identidad federada permite la descarga y el escalado vertical de autenticación para una suscripción de Microsoft 365 y escenarios avanzados de seguridad y autenticación.</span><span class="sxs-lookup"><span data-stu-id="89b0b-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="89b0b-109">En este artículo se describe cómo configurar la autenticación federada para el entorno de prueba de Microsoft 365, lo que da como resultado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b0b-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![La autenticación federada para el entorno de pruebas de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="89b0b-111">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="89b0b-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="89b0b-112">Una suscripción de prueba o producción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="89b0b-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="89b0b-113">Una intranet de organización simplificada conectada a Internet, que consta de cinco máquinas virtuales en una subred de una red virtual de Azure (DC1, APP1, cliente1, ADFS1 y PROXY1).</span><span class="sxs-lookup"><span data-stu-id="89b0b-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="89b0b-114">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas del dominio de servicios de dominio de Active Directory con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89b0b-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="89b0b-115">PROXY1 recibe las solicitudes de autenticación entrantes.</span><span class="sxs-lookup"><span data-stu-id="89b0b-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="89b0b-116">ADFS1 valida las credenciales con DC1 y emite tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="89b0b-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="89b0b-117">La configuración de este entorno de prueba implica cinco fases:</span><span class="sxs-lookup"><span data-stu-id="89b0b-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="89b0b-118">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89b0b-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="89b0b-119">Fase 2: Crear el servidor de AD FS</span><span class="sxs-lookup"><span data-stu-id="89b0b-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="89b0b-120">Fase 3: Crear el servidor proxy web</span><span class="sxs-lookup"><span data-stu-id="89b0b-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="89b0b-121">Fase 4: Crear un certificado autofirmado y configurar ADFS1 y PROXY1</span><span class="sxs-lookup"><span data-stu-id="89b0b-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="89b0b-122">Fase 5: Configurar Microsoft 365 con identidad federada</span><span class="sxs-lookup"><span data-stu-id="89b0b-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="89b0b-123">No puede configurar este entorno de prueba con una suscripción de prueba de Azure.</span><span class="sxs-lookup"><span data-stu-id="89b0b-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="89b0b-124">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89b0b-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="89b0b-125">Siga las instrucciones de [sincronización de hash de contraseña para Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="89b0b-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="89b0b-126">La configuración resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="89b0b-126">Your resulting configuration looks like this:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="89b0b-128">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="89b0b-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="89b0b-129">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="89b0b-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="89b0b-130">Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y cliente1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="89b0b-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="89b0b-131">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de servicios de dominio de Active Directory (AD DS) TESTLAB con el espacio empresarial de Azure AD de las suscripciones de Microsoft 365 periódicamente.</span><span class="sxs-lookup"><span data-stu-id="89b0b-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="89b0b-132">Fase 2: Crear el servidor de AD FS</span><span class="sxs-lookup"><span data-stu-id="89b0b-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="89b0b-133">Un servidor de AD FS proporciona autenticación federada entre Microsoft 365 y las cuentas del dominio corp.contoso.com hospedado en DC1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="89b0b-134">Para crear una máquina virtual de Azure para ADFS1, indique el nombre de la suscripción y del grupo de recursos y una ubicación de Azure para la configuración básica. Después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="89b0b-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="89b0b-135">Después, vaya a [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con el nombre y contraseña de la cuenta de administrador local de ADFS1 y abra un símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89b0b-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="89b0b-136">Para comprobar la comunicación de red y la resolución de nombres entre ADFS1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="89b0b-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="89b0b-137">A continuación, una la máquina virtual de ADFS1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en ADFS1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="89b0b-138">La configuración resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="89b0b-138">Your resulting configuration looks like this:</span></span>
  
![Servidor de AD FS agregado a DirSync para el entorno de prueba de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="89b0b-140">Fase 3: Crear el servidor proxy web</span><span class="sxs-lookup"><span data-stu-id="89b0b-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="89b0b-141">PROXY1 permite crear conexiones proxy de mensajes de autenticación entre usuarios que intentan autenticarse y ADFS1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="89b0b-142">Para crear una máquina virtual de Azure para PROXY1, indique el nombre de su grupo de recursos y una ubicación de Azure y, después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="89b0b-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="89b0b-143">PROXY1 se asigna como una dirección IP pública estática porque creará un registro DNS público que la señale y no debe cambiarse cuando reinicie la máquina virtual de PROXY1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="89b0b-144">A continuación, agregue una regla al grupo de seguridad de red de la subred de la red corporativa para permitir el tráfico entrante no solicitado de Internet a PROXY1's dirección IP privada y el puerto TCP 443.</span><span class="sxs-lookup"><span data-stu-id="89b0b-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="89b0b-145">Ejecute estos comandos desde el símbolo del sistema de Azure PowerShell en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="89b0b-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="89b0b-146">Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de PROXY1 con el nombre y contraseña de la cuenta de administrador local de PROXY1 y luego abra un símbolo del sistema de Windows PowerShell en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="89b0b-147">Para comprobar la comunicación de red y la resolución de nombres entre PROXY1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="89b0b-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="89b0b-148">A continuación, una la máquina virtual de PROXY1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="89b0b-149">Mostrar la dirección IP pública de PROXY1 con estos comandos de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="89b0b-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="89b0b-p106">Después, trabaje con su proveedor de DNS público y cree un nuevo registro DNS A público para **fs.testlab.**\<*your DNS domain name*> se resuelva en la dirección IP mostrada mediante el comando **Write-Host**. En lo sucesivo, se hace referencia a **fs.testlab.**\<*your DNS domain name*> como el *FQDN del servicio de federación*.</span><span class="sxs-lookup"><span data-stu-id="89b0b-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="89b0b-154">Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y ejecute los siguientes comandos en un símbolo del sistema de Windows PowerShell con nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="89b0b-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="89b0b-155">Estos comandos crean un registro A de DNS interno para que las máquinas virtuales de la red virtual de Azure puedan resolver el FQDN del servicio de Federación interno en la dirección IP privada ADFS1's.</span><span class="sxs-lookup"><span data-stu-id="89b0b-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="89b0b-156">La configuración resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="89b0b-156">Your resulting configuration looks like this:</span></span>
  
![El servidor proxy de la aplicación web agregado a DirSync para el entorno de prueba de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="89b0b-158">Fase 4: Crear un certificado autofirmado y configurar ADFS1 y PROXY1</span><span class="sxs-lookup"><span data-stu-id="89b0b-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="89b0b-159">En esta fase, crea un certificado digital autofirmado para su FQDN del Servicio de federación y configura ADFS1 y PROXY1 como una granja de servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="89b0b-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="89b0b-160">En primer lugar, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y luego abra un símbolo del sistema de Windows PowerShell con nivel de administrador. </span><span class="sxs-lookup"><span data-stu-id="89b0b-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="89b0b-161">A continuación, cree una cuenta de servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en DC1:</span><span class="sxs-lookup"><span data-stu-id="89b0b-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="89b0b-162">Tenga en cuenta que este comando le pedirá que proporcione la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="89b0b-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="89b0b-163">Elija una contraseña segura y guárdela en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="89b0b-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="89b0b-164">La necesitará para esta fase y para la fase 5.</span><span class="sxs-lookup"><span data-stu-id="89b0b-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="89b0b-p108">Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con las credenciales de CORP\\User1. Abra un símbolo del sistema de Windows PowerShell con nivel de administrador en ADFS1, indique el FQDN del Servicio de federación y luego ejecute estos comandos para crear un certificado autofirmado:</span><span class="sxs-lookup"><span data-stu-id="89b0b-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="89b0b-167">Después, use estos pasos para guardar el nuevo certificado autofirmado como archivo.</span><span class="sxs-lookup"><span data-stu-id="89b0b-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="89b0b-168">Seleccione **Inicio**, escriba **mmc.exe**y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="89b0b-169">Seleccione **archivo**  >  **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="89b0b-170">En **Agregar o quitar complementos**, haga doble clic en **certificados** en la lista de complementos disponibles, seleccione **cuenta de equipo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="89b0b-171">En **seleccionar equipo**, haga clic en **Finalizar**y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="89b0b-172">En el panel de árbol, abra **Certificados (equipo local) > Personal > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="89b0b-173">Seleccione y mantenga presionado (o haga clic con el botón derecho) el certificado con el FQDN del servicio de Federación, seleccione **todas las tareas**y, a continuación, seleccione **exportar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="89b0b-174">En la página **principal** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="89b0b-175">En la página **Exportar clave privada** , seleccione **sí**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="89b0b-176">En la página **formato de archivo de exportación** , seleccione **exportar todas las propiedades extendidas**y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="89b0b-177">En la página **seguridad** , seleccione **contraseña** y escriba una contraseña en **contraseña** y **Confirmar contraseña.**</span><span class="sxs-lookup"><span data-stu-id="89b0b-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="89b0b-178">En la página **archivo que se va a exportar** , seleccione **examinar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="89b0b-179">Vaya a la **carpeta C \\ : certs** , escriba **SSL** en **nombre de archivo**y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="89b0b-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="89b0b-180">En la página **archivo que se va a exportar** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="89b0b-181">En la página **finalización del Asistente para exportación de certificados** , seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="89b0b-182">Cuando se le solicite, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="89b0b-183">Después, instale el servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en ADFS1:</span><span class="sxs-lookup"><span data-stu-id="89b0b-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="89b0b-184">Espere a que termine la instalación.</span><span class="sxs-lookup"><span data-stu-id="89b0b-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="89b0b-185">Después, configure el servicio de AD FS con estos pasos:</span><span class="sxs-lookup"><span data-stu-id="89b0b-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="89b0b-186">Seleccione **Inicio**y, a continuación, seleccione el icono **Administrador de servidores** .</span><span class="sxs-lookup"><span data-stu-id="89b0b-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="89b0b-187">En el panel de árbol del administrador de servidores, seleccione **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="89b0b-188">En la barra de herramientas de la parte superior, seleccione el símbolo de advertencia naranja y, después, seleccione **configurar el servicio de Federación en este servidor**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="89b0b-189">En la página de **bienvenida** del Asistente para la configuración de los servicios de Federación de Active Directory, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="89b0b-190">En la página **conectar con AD DS** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="89b0b-191">En la página **Especificar propiedades del servicio**:</span><span class="sxs-lookup"><span data-stu-id="89b0b-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="89b0b-192">En **certificado SSL**, seleccione la flecha abajo y, a continuación, seleccione el certificado con el nombre del FQDN del servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="89b0b-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="89b0b-193">En **nombre para mostrar del servicio de Federación**, escriba el nombre de la organización ficticia.</span><span class="sxs-lookup"><span data-stu-id="89b0b-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="89b0b-194">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="89b0b-195">En la página **especificar cuenta de servicio** , seleccione **seleccionar** para **nombre de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="89b0b-196">En **Seleccionar usuario o cuenta de servicio**, escriba **servicio ADFS**, seleccione **Comprobar nombres**y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="89b0b-197">En **contraseña**de la cuenta, escriba la contraseña de la cuenta de ADFS-Service y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="89b0b-198">En la página **especificar base de datos de configuración** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="89b0b-199">En la página **revisar opciones** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="89b0b-200">En la página **comprobaciones de requisitos** previos, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="89b0b-201">En la página **resultados** , seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="89b0b-202">Seleccione **Inicio**, seleccione el icono de energía, haga clic en **reiniciar**y, después, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="89b0b-203">Desde [Azure Portal](https://portal.azure.com), conéctese a PROXY1 con las credenciales de la cuenta CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="89b0b-204">Después, siga estos pasos para instalar el certificado autofirmado en **PROXY1 y APP1**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="89b0b-205">Seleccione **Inicio**, escriba **mmc.exe**y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="89b0b-206">Seleccione **archivo > agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="89b0b-207">En **Agregar o quitar complementos**, haga doble clic en **certificados** en la lista de complementos disponibles, seleccione **cuenta de equipo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="89b0b-208">En **seleccionar equipo**, haga clic en **Finalizar**y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="89b0b-209">En el panel de árbol, abra certificados personales **(equipo local)**  >  **Personal**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="89b0b-210">Seleccione y mantenga presionado (o haga clic con el botón derecho) **personal**, seleccione **todas las tareas**y, a continuación, seleccione **importar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="89b0b-211">En la página **principal** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="89b0b-212">En la página **archivo para importar** , escriba \*\* \\ \\ certificados de adfs1 \\ \\ SSL. pfx\*\*y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="89b0b-213">En la página **protección de clave privada** , escriba la contraseña de certificado en **contraseña**y, después, seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="89b0b-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="89b0b-214">En la página **almacén de certificados** , seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="89b0b-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="89b0b-215">En la página **finalización** , seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="89b0b-216">En la página **almacén de certificados** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="89b0b-217">Cuando se le solicite, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="89b0b-218">En el panel de árbol, seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="89b0b-219">Seleccione y mantenga presionado (o haga clic con el botón derecho) en el certificado y, a continuación, seleccione **copiar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="89b0b-220">En el panel de árbol, abra certificados de **entidades de certificación raíz de confianza**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="89b0b-221">Mueva el puntero del mouse debajo de la lista de certificados instalados, seleccione y mantenga presionado (o haga clic con el botón derecho) y seleccione **pegar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="89b0b-222">Abra un símbolo del sistema de PowerShell con el nivel de administrador y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b0b-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="89b0b-223">Espere a que termine la instalación.</span><span class="sxs-lookup"><span data-stu-id="89b0b-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="89b0b-224">Use estos pasos para configurar el servicio proxy de aplicación web para usar ADFS1 como su servidor de federación:</span><span class="sxs-lookup"><span data-stu-id="89b0b-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="89b0b-225">Seleccione **Inicio**y, a continuación, seleccione **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="89b0b-226">En el panel de árbol, seleccione **acceso remoto**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="89b0b-227">En la barra de herramientas de la parte superior, seleccione el símbolo de advertencia naranja y, a continuación, seleccione **abrir el Asistente para proxy de aplicación web**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="89b0b-228">En la página **principal** del Asistente para configuración de proxy de aplicación Web, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="89b0b-229">En la página **Servidor de federación**:</span><span class="sxs-lookup"><span data-stu-id="89b0b-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="89b0b-230">En el cuadro **nombre del servicio de Federación** , escriba el FQDN del servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="89b0b-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="89b0b-231">En el cuadro **nombre de usuario** , escriba **Corp \\ usuario1**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="89b0b-232">En el cuadro **contraseña** , escriba la contraseña de la cuenta usuario1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="89b0b-233">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="89b0b-234">En la página **certificado de proxy de AD FS** , seleccione la flecha abajo, seleccione el certificado con el FQDN del servicio de Federación y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="89b0b-235">En la página **confirmación** , seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="89b0b-236">En la página **resultados** , seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="89b0b-237">Fase 5: Configurar Microsoft 365 con identidad federada</span><span class="sxs-lookup"><span data-stu-id="89b0b-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="89b0b-238">Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de APP1 con las credenciales de la cuenta CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="89b0b-239">Siga estos pasos para configurar Azure AD Connect y la suscripción de Microsoft 365 con autenticación federada:</span><span class="sxs-lookup"><span data-stu-id="89b0b-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="89b0b-240">En el escritorio, haga doble clic en **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="89b0b-241">En la página **Bienvenido a Azure ad Connect** , seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="89b0b-242">En la página **tareas adicionales** , seleccione **cambiar inicio de sesión de usuario**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="89b0b-243">En la página **conectar con Azure ad** , escriba el nombre y la contraseña de la cuenta de administrador global y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="89b0b-244">En la página **Inicio de sesión de usuario** , seleccione **Federación con AD FS**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="89b0b-245">En la **Página granja de AD FS** , seleccione **usar una granja de AD FS existente**, escriba **ADFS1** en el cuadro **nombre del servidor** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="89b0b-246">Cuando se le soliciten las credenciales del servidor, escriba las credenciales de la \\ cuenta usuario1 user1 y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="89b0b-247">En la página credenciales de **Administrador de dominio** , escriba **Corp \\ user1** en el cuadro **nombre de usuario** , escriba la contraseña de la cuenta en el cuadro **contraseña** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="89b0b-248">En la página **cuenta de servicio de AD FS** , escriba **Corp \\ ad-Service** en el cuadro Nombre de usuario de **dominio** , escriba la contraseña de la cuenta en el cuadro contraseña de **usuario de dominio** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="89b0b-249">En la página **dominio de Azure ad** , en **dominio**, seleccione el nombre del dominio que ha creado y agregado anteriormente a su suscripción en la fase 1 y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="89b0b-250">En la página **listo para configurar** , seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="89b0b-251">En la página **Instalación completada** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="89b0b-252">Debe ver mensajes que indican que se ha comprobado la configuración de intranet e Internet.</span><span class="sxs-lookup"><span data-stu-id="89b0b-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="89b0b-253">En la página **Instalación completada** , seleccione **salir**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="89b0b-254">Para demostrar que la autenticación federada funciona:</span><span class="sxs-lookup"><span data-stu-id="89b0b-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="89b0b-255">Abra una nueva instancia privada del explorador en el equipo local y vaya a[https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="89b0b-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="89b0b-256">Para las credenciales de inicio de sesión, escriba **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="89b0b-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="89b0b-257">Por ejemplo, si el dominio de prueba es **testlab.contoso.com**, debe escribir "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="89b0b-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="89b0b-258">Presione la tecla **Tab** o deje que Microsoft 365 le redirija automáticamente.</span><span class="sxs-lookup"><span data-stu-id="89b0b-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="89b0b-259">Ahora debería ver que **la página su conexión no es privada** .</span><span class="sxs-lookup"><span data-stu-id="89b0b-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="89b0b-260">Está viendo esto porque ha instalado un certificado autofirmado en ADFS1 que su equipo de escritorio no puede validar.</span><span class="sxs-lookup"><span data-stu-id="89b0b-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="89b0b-261">En una implementación de producción de la autenticación federada, usaría un certificado de una entidad de certificación de confianza y los usuarios no verían esta página.</span><span class="sxs-lookup"><span data-stu-id="89b0b-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="89b0b-262">En la página **su conexión no es privada** , seleccione **avanzadas**y, a continuación, seleccione \*\*ir a \<*your federation service FQDN*> \*\*.</span><span class="sxs-lookup"><span data-stu-id="89b0b-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="89b0b-263">En la página con el nombre de su organización ficticia, inicie sesión con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b0b-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="89b0b-264">**CORP\\User1** como nombre</span><span class="sxs-lookup"><span data-stu-id="89b0b-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="89b0b-265">Contraseña de la cuenta User1</span><span class="sxs-lookup"><span data-stu-id="89b0b-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="89b0b-266">Debe ver la página **principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="89b0b-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="89b0b-p112">En este procedimiento, se muestra que su suscripción de prueba está federada con el dominio corp.contoso.com de AD DS hospedado en DC1. Estos son los conceptos básicos del proceso de autenticación:</span><span class="sxs-lookup"><span data-stu-id="89b0b-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="89b0b-269">Cuando use el dominio federado que ha creado en la fase 1 en el nombre de cuenta de inicio de sesión, Microsoft 365 redirige su explorador al FQDN del Servicio de federación y a PROXY1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="89b0b-270">PROXY1 envía a su equipo local la página de inicio de sesión de la compañía ficticia.</span><span class="sxs-lookup"><span data-stu-id="89b0b-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="89b0b-271">Cuando envía CORP\\User1 y la contraseña a PROXY1, estos se reenvían a ADFS1.</span><span class="sxs-lookup"><span data-stu-id="89b0b-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="89b0b-272">ADFS1 valida CORP\\User1 y la contraseña con DC1 y envía a su equipo local un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="89b0b-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="89b0b-273">El equipo local envía el token de seguridad a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89b0b-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="89b0b-274">Microsoft 365 valida que ese token de seguridad se haya creado mediante ADFS1 y permite el acceso.</span><span class="sxs-lookup"><span data-stu-id="89b0b-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="89b0b-p113">Su suscripción de evaluación ahora está configurada con la autenticación federada. Puede usar este entorno de desarrollo y prueba para escenarios de autenticación avanzados.</span><span class="sxs-lookup"><span data-stu-id="89b0b-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="89b0b-277">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="89b0b-277">Next step</span></span>

<span data-ttu-id="89b0b-278">Cuando esté listo para implementar la autenticación federada de alta disponibilidad preparada para producción para Microsoft 365 en Azure, consulte [deploy High Availability Federated Authentication for microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="89b0b-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
