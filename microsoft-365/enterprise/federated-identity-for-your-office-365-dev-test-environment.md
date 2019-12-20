---
title: Identidad federada para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
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
ms.openlocfilehash: 1158109a4d42a7434a1d66750b2182f940d511b9
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801855"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d907b-103">Identidad federada para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d907b-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d907b-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d907b-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d907b-p101">Office 365 admite la identidad federada. Esto significa que, en lugar de realizar la validación de las credenciales él mismo, Office 365 dirige al usuario que se conecta a un servidor de autenticación federada en el que Office 365 confía. Si las credenciales del usuario son correctas, el servidor de autenticación federada emite un token de seguridad que el cliente envía luego a Office 365 como prueba de autenticación. La identidad federada permite la descarga y el escalado vertical de autenticación para una suscripción de Office 365 y escenarios avanzados de seguridad y autenticación.</span><span class="sxs-lookup"><span data-stu-id="d907b-p101">Office 365 supports federated identity. This means that instead of performing the validation of credentials itself, Office 365 refers the connecting user to a federated authentication server that Office 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Office 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for an Office 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="d907b-109">En este artículo, se describe cómo puede configurar la autenticación federada para el entorno de prueba de Microsoft 365 u Office 365, lo que se traduce en el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d907b-109">This article describes how you can configure federated authentication for your Microsoft 365 or Office 365 test environment, resulting in the following:</span></span>

![La autenticación federada para el entorno de pruebas de Microsoft 365](media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="d907b-111">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d907b-111">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d907b-112">Una suscripción de prueba o de pago de Microsoft 365 E5 u Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d907b-112">A Microsoft 365 E5 or Office 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="d907b-p102">Una intranet de una organización simplificada conectada a Internet que consta de cinco máquinas virtuales en una subred de una red virtual de Azure (DC1, APP1, CLIENT1, ADFS1 y PROXY1). Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas del dominio de Active Directory Domain Services con Office 365. PROXY1 recibe las solicitudes de autenticación entrantes. ADFS1 valida las credenciales con DC1 y emite tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d907b-p102">A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1). Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Office 365. PROXY1 receives the incoming authentication requests. ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="d907b-117">Existen cinco fases para configurar este entorno de desarrollo y pruebas:</span><span class="sxs-lookup"><span data-stu-id="d907b-117">There are five phases to setting up this dev/test environment:</span></span>
  
1. <span data-ttu-id="d907b-118">Crear el entorno de prueba de la empresa simulada con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d907b-118">Create the simulated enterprise test environment with password hash synchronization.</span></span>
    
2. <span data-ttu-id="d907b-119">Crear el servidor de AD FS (ADFS1)</span><span class="sxs-lookup"><span data-stu-id="d907b-119">Create the AD FS server (ADFS1).</span></span>
    
3. <span data-ttu-id="d907b-120">Crear el servidor proxy web (PROXY1)</span><span class="sxs-lookup"><span data-stu-id="d907b-120">Create the web proxy server (PROXY1).</span></span>
    
4. <span data-ttu-id="d907b-121">Crear un certificado autofirmado y configurar ADFS1 y PROXY1</span><span class="sxs-lookup"><span data-stu-id="d907b-121">Create a self-signed certificate and configure ADFS1 and PROXY1.</span></span>
    
5. <span data-ttu-id="d907b-122">Configurar Office 365 con identidad federada</span><span class="sxs-lookup"><span data-stu-id="d907b-122">Configure Office 365 for federated identity.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d907b-123">No puede configurar este entorno de prueba con una suscripción de prueba de Azure.</span><span class="sxs-lookup"><span data-stu-id="d907b-123">You cannot configure this test environment with an Azure Trial subscription.</span></span> 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d907b-124">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d907b-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d907b-p103">Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="d907b-p103">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="d907b-128">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d907b-128">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d907b-129">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d907b-129">A Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="d907b-130">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="d907b-130">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="d907b-131">Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="d907b-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="d907b-132">Fase 2: Crear el servidor de AD FS</span><span class="sxs-lookup"><span data-stu-id="d907b-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="d907b-133">Un servidor de AD FS proporciona autenticación federada entre Office 365 y las cuentas del dominio corp.contoso.com hospedado en DC1.</span><span class="sxs-lookup"><span data-stu-id="d907b-133">An AD FS server provides federated authentication between Office 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="d907b-134">Para crear una máquina virtual de Azure para ADFS1, indique el nombre de la suscripción y del grupo de recursos y una ubicación de Azure para la configuración básica. Después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d907b-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="d907b-135">Después, vaya a [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con el nombre y contraseña de la cuenta de administrador local de ADFS1 y abra un símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d907b-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="d907b-136">Para comprobar la comunicación de red y la resolución de nombres entre ADFS1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="d907b-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="d907b-137">A continuación, una la máquina virtual de ADFS1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en ADFS1.</span><span class="sxs-lookup"><span data-stu-id="d907b-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="d907b-138">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="d907b-138">Here is your resulting configuration.</span></span>
  
![Servidor de AD FS agregado a DirSync para el entorno de prueba de Microsoft 365](media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="d907b-140">Fase 3: Crear el servidor proxy web</span><span class="sxs-lookup"><span data-stu-id="d907b-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="d907b-141">PROXY1 permite crear conexiones proxy de mensajes de autenticación entre usuarios que intentan autenticarse y ADFS1.</span><span class="sxs-lookup"><span data-stu-id="d907b-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="d907b-142">Para crear una máquina virtual de Azure para PROXY1, indique el nombre de su grupo de recursos y una ubicación de Azure y, después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d907b-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="d907b-143">PROXY1 se asigna como una dirección IP pública estática porque creará un registro DNS público que la señale y no debe cambiarse cuando reinicie la máquina virtual de PROXY1.</span><span class="sxs-lookup"><span data-stu-id="d907b-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span> 
  
<span data-ttu-id="d907b-p105">Después, agregue una regla al grupo de seguridad de red para que la subred CorpNet permita tráfico entrante no solicitado desde Internet a la dirección IP privada de PROXY1 y al puerto TCP 443. Ejecute estos comandos desde el símbolo del sistema de Azure PowerShell en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="d907b-p105">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="d907b-146">Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de PROXY1 con el nombre y contraseña de la cuenta de administrador local de PROXY1 y luego abra un símbolo del sistema de Windows PowerShell en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="d907b-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="d907b-147">Para comprobar la comunicación de red y la resolución de nombres entre PROXY1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.</span><span class="sxs-lookup"><span data-stu-id="d907b-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="d907b-148">A continuación, una la máquina virtual de PROXY1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="d907b-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="d907b-149">Muestre la dirección IP pública de PROXY1 con estos comandos de Azure PowerShell en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="d907b-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="d907b-p106">Después, trabaje con su proveedor de DNS público y cree un nuevo registro DNS A público para **fs.testlab.**\<su nombre de dominio DNS> que se resuelva en la dirección IP mostrada mediante el comando **Write-Host**. En lo sucesivo, se hace referencia a **fs.testlab.**\<su nombre de dominio DNS> como el FQDN del *Servicio de federación*.</span><span class="sxs-lookup"><span data-stu-id="d907b-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<your DNS domain name> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="d907b-152">Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y ejecute los siguientes comandos en un símbolo del sistema de Windows PowerShell con nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="d907b-152">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="d907b-153">Estos comandos crean un registro DNS A interno para que las máquinas virtuales de la red virtual de Azure pueden resolver el FQDN interno de la federación en la dirección IP privada de ADFS1.</span><span class="sxs-lookup"><span data-stu-id="d907b-153">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="d907b-154">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="d907b-154">Here is your resulting configuration.</span></span>
  
![El servidor proxy de la aplicación web agregado a DirSync para el entorno de prueba de Microsoft 365](media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="d907b-156">Fase 4: Crear un certificado autofirmado y configurar ADFS1 y PROXY1</span><span class="sxs-lookup"><span data-stu-id="d907b-156">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="d907b-157">En esta fase, crea un certificado digital autofirmado para su FQDN del Servicio de federación y configura ADFS1 y PROXY1 como una granja de servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="d907b-157">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="d907b-158">En primer lugar, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y luego abra un símbolo del sistema de Windows PowerShell con nivel de administrador. </span><span class="sxs-lookup"><span data-stu-id="d907b-158">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="d907b-159">Después, cree una cuenta de servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en DC1:</span><span class="sxs-lookup"><span data-stu-id="d907b-159">Next, create AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="d907b-p107">Tenga en cuenta que este comando le solicita que proporcione la contraseña de la cuenta. Elija una contraseña segura y guárdela en una ubicación segura. La necesitará para esta fase y para la fase 5.</span><span class="sxs-lookup"><span data-stu-id="d907b-p107">Note that this command prompts you to supply the account password. Choose a strong password and record it in a secured location. You will need it for this phase and Phase 5.</span></span>
  
<span data-ttu-id="d907b-p108">Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con las credenciales de CORP\\User1. Abra un símbolo del sistema de Windows PowerShell con nivel de administrador en ADFS1, indique el FQDN del Servicio de federación y luego ejecute estos comandos para crear un certificado autofirmado:</span><span class="sxs-lookup"><span data-stu-id="d907b-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="d907b-165">Después, use estos pasos para guardar el nuevo certificado autofirmado como archivo.</span><span class="sxs-lookup"><span data-stu-id="d907b-165">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="d907b-166">Haga clic en **Inicio**, escriba**mmc.exe** y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-166">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="d907b-167">Haga clic en **Archivo > Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="d907b-167">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="d907b-168">En **Agregar o quitar complementos**, haga doble clic en **Certificados** en la lista de complementos disponibles, haga clic en **Cuenta de equipo** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-168">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="d907b-169">En **Seleccionar equipo**, haga clic en **Finalizar** y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-169">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d907b-170">En el panel de árbol, abra **Certificados (equipo local) > Personal > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="d907b-170">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="d907b-171">Haga clic con el botón derecho en el certificado con su FQDN del Servicio de federación, haga clic en **Todas las tareas** y luego en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-171">Right-click the certificate with your federation service FQDN, click **All tasks**, and then click **Export**.</span></span>
    
7. <span data-ttu-id="d907b-172">En la página de **bienvenida**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-172">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="d907b-173">En la página **Exportar clave privada**, haga clic en **Sí** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-173">On the **Export Private Key** page, click **Yes**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d907b-174">En la página **Formato de archivo de exportación**, haga clic en **Exportar todas las propiedades extendidas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-174">On the **Export File Format** page, click **Export all extended properties**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="d907b-175">En la página **Seguridad**, haga clic en **Contraseña** y escriba una contraseña en **Contraseña** y **Confirmar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="d907b-175">On the **Security** page, click **Password** and type a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="d907b-176">En la página **Archivo que se va a exportar**, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-176">On the **File to Export** page, click **Browse**.</span></span>
    
12. <span data-ttu-id="d907b-177">Vaya a la carpeta **C:\\Certs**, escriba **SSL** en **Nombre de archivo** y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-177">Browse to the **C:\\Certs** folder, type **SSL** in **File name**, and then click **Save.**</span></span>
    
13. <span data-ttu-id="d907b-178">En la página **Archivo que se va a exportar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-178">On the **File to Export** page, click **Next**.</span></span>
    
14. <span data-ttu-id="d907b-p109">En la página **Finalización del Asistente para exportación de certificados**, haga clic en **Finalizar**. Cuando se le solicite, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-p109">On the **Completing the Certificate Export Wizard** page, click **Finish**. When prompted, click **OK**.</span></span>
    
<span data-ttu-id="d907b-181">Después, instale el servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en ADFS1:</span><span class="sxs-lookup"><span data-stu-id="d907b-181">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="d907b-182">Espere a que termine la instalación.</span><span class="sxs-lookup"><span data-stu-id="d907b-182">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="d907b-183">Después, configure el servicio de AD FS con estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d907b-183">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="d907b-184">Haga clic en **Inicio** y luego en el icono **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="d907b-184">Click **Start**, and then click the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="d907b-185">En el panel de árbol del Administrador de servidores, haga clic en **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="d907b-185">In the tree pane of Server Manager, click **AD FS**.</span></span>
    
3. <span data-ttu-id="d907b-186">En la barra de herramientas de la parte superior, haga clic en el símbolo de advertencia naranja y luego en **Configure el servicio de federación en este servidor**.</span><span class="sxs-lookup"><span data-stu-id="d907b-186">In the tool bar at the top, click the orange caution symbol, and then click **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="d907b-187">En la página **principal** del Asistente para la configuración de los Servicios de federación de Active Directory, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-187">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="d907b-188">En la página **Conectarse a AD DS**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-188">On the **Connect to AD DS** page, click **Next**.</span></span>
    
6. <span data-ttu-id="d907b-189">En la página **Especificar propiedades del servicio**:</span><span class="sxs-lookup"><span data-stu-id="d907b-189">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="d907b-190">En **Certificado SSL**, haga clic en la flecha abajo y luego en el certificado con el nombre del FQDN del Servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="d907b-190">For **SSL Certificate**, click the down arrow, and then click the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="d907b-191">En **Nombre para mostrar del Servicio de federación**, escriba el nombre de la organización ficticia.</span><span class="sxs-lookup"><span data-stu-id="d907b-191">In **Federation Service Display Name**, type the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="d907b-192">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-192">Click **Next**.</span></span>
    
7. <span data-ttu-id="d907b-193">En la página **Especificar cuenta de servicio**, haga clic en **Seleccionar** para **Nombre de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="d907b-193">On the **Specify Service Account** page, click **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="d907b-194">En **Seleccionar usuario o cuenta de servicio**, escriba **Servicio ADFS**, haga clic en **Comprobar nombres** y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-194">In **Select User or Service Account**, type **ADFS-Service**, click **Check Names**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="d907b-195">En **Contraseña de cuenta**, escriba la contraseña para la cuenta del servicio ADFS y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-195">In **Account Password**, type the password for the ADFS-Service account, and then click **Next**.</span></span>
    
10. <span data-ttu-id="d907b-196">En la página **Especificar base de datos de configuración**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-196">On the **Specify Configuration Database** page, click **Next**.</span></span>
    
11. <span data-ttu-id="d907b-197">En la página **Revisar opciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-197">On the **Review Options** page, click **Next**.</span></span>
    
12. <span data-ttu-id="d907b-198">En la página **Comprobaciones de requisitos previos**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-198">On the **Pre-requisite Checks** page, click **Configure**.</span></span>
    
13. <span data-ttu-id="d907b-199">En la página **Resultados**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-199">On the **Results** page, click **Close**.</span></span>
    
14. <span data-ttu-id="d907b-200">Haga clic en **Inicio**, en el icono de encendido/apagado, en **Reiniciar** y luego en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-200">Click **Start**, click the power icon, click **Restart**, and then click **Continue**.</span></span>
    
<span data-ttu-id="d907b-201">Desde [Azure Portal](https://portal.azure.com), conéctese a PROXY1 con las credenciales de la cuenta CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="d907b-201">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="d907b-202">Después, siga estos pasos para instalar el certificado autofirmado y configurar PROXY1.</span><span class="sxs-lookup"><span data-stu-id="d907b-202">Next, use these steps to install the self-signed certificate and configure PROXY1.</span></span>
  
1. <span data-ttu-id="d907b-203">Haga clic en **Inicio**, escriba**mmc.exe** y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-203">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="d907b-204">Haga clic en **Archivo > Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="d907b-204">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="d907b-205">En **Agregar o quitar complementos**, haga doble clic en **Certificados** en la lista de complementos disponibles, haga clic en **Cuenta de equipo** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-205">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="d907b-206">En **Seleccionar equipo**, haga clic en **Finalizar** y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-206">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d907b-207">En el panel de árbol, abra **Certificados (equipo local) > Personal > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="d907b-207">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="d907b-208">Haga clic con el botón derecho en **Personal**, haga clic en **Todas las tareas** y luego en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-208">Right-click **Personal**, click **All tasks**, and then click **Import**.</span></span>
    
7. <span data-ttu-id="d907b-209">En la página de **bienvenida**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-209">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="d907b-210">En la página **Archivo para importar**, escriba **\\\\adfs1\\certs\\ssl.pfx** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-210">On the **File to Import** page, type **\\\\adfs1\\certs\\ssl.pfx**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d907b-211">En la página **Protección de clave privada**, escriba la contraseña de certificado en **Contraseña** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-211">On the **Private key protection** page, type the certificate password in **Password**, and then click **Next.**</span></span>
    
10. <span data-ttu-id="d907b-212">En la página **Almacén de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-212">On the **Certificate store** page, click **Next.**</span></span>
    
11. <span data-ttu-id="d907b-213">En la página **Completando**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-213">On the **Completing** page, click **Finish**.</span></span>
    
12. <span data-ttu-id="d907b-214">En la página **Almacén de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-214">On the **Certificate Store** page, click **Next**.</span></span>
    
13. <span data-ttu-id="d907b-215">Cuando se le solicite, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-215">When prompted, click **OK**.</span></span>
    
14. <span data-ttu-id="d907b-216">Haga clic en **Certificados** en el panel de árbol.</span><span class="sxs-lookup"><span data-stu-id="d907b-216">Click **Certificates** in the tree pane.</span></span>
    
15. <span data-ttu-id="d907b-217">Haga clic con el botón derecho en el certificado y luego haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-217">Right-click the certificate, and then click **Copy**.</span></span>
    
16. <span data-ttu-id="d907b-218">En el panel de árbol, abra **Entidades de certificación raíz de confianza > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="d907b-218">In the tree pane, open **Trusted Root Certification Authorities > Certificates**.</span></span>
    
17. <span data-ttu-id="d907b-219">Mueva el puntero del mouse debajo de la lista de certificados instalados, haga clic con el botón derecho y luego haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-219">Move your mouse pointer below the list of installed certificates, right-click, and then click **Paste**.</span></span>
    
<span data-ttu-id="d907b-220">Abra un símbolo del sistema de PowerShell con el nivel de administrador y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="d907b-220">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="d907b-221">Espere a que termine la instalación.</span><span class="sxs-lookup"><span data-stu-id="d907b-221">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="d907b-222">Use estos pasos para configurar el servicio proxy de aplicación web para usar ADFS1 como su servidor de federación:</span><span class="sxs-lookup"><span data-stu-id="d907b-222">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="d907b-223">Haga clic en **Iniciar** y luego en **Administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="d907b-223">Click **Start**, and then click **Server Manager**.</span></span>
    
2. <span data-ttu-id="d907b-224">En el panel de árbol, haga clic en **Acceso remoto**.</span><span class="sxs-lookup"><span data-stu-id="d907b-224">In the tree pane, click **Remote Access**.</span></span>
    
3. <span data-ttu-id="d907b-225">En la barra de herramientas de la parte superior, haga clic en el símbolo de advertencia naranja y luego en **Abrir el Asistente para proxy de aplicación web**.</span><span class="sxs-lookup"><span data-stu-id="d907b-225">In the tool bar at the top, click the orange caution symbol, and then click **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="d907b-226">En la página **principal** del Asistente para configuración de Proxy de aplicación web, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-226">On the **Welcome** page of the Web Application Proxy Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="d907b-227">En la página **Servidor de federación**:</span><span class="sxs-lookup"><span data-stu-id="d907b-227">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="d907b-228">Escriba su FQDN del Servicio de federación en **Nombre del Servicio de federación**.</span><span class="sxs-lookup"><span data-stu-id="d907b-228">Type your federation service FQDN in **Federation service name**.</span></span>
    
  - <span data-ttu-id="d907b-229">Escriba **CORP\\User1** en **Nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d907b-229">Type **CORP\\User1** in **User name**.</span></span>
    
  - <span data-ttu-id="d907b-230">Escriba la contraseña de la cuenta User1 en **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="d907b-230">Type the password for the User1 account in **Password**.</span></span>
    
  - <span data-ttu-id="d907b-231">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-231">Click **Next**.</span></span>
    
6. <span data-ttu-id="d907b-232">En la página **Certificado de proxy de AD FS**, haga clic en la flecha abajo, en el certificado con su FQDN del Servicio de federación y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-232">On the **AD FS Proxy Certificate** page, click the down arrow, click the certificate with your federation service FQDN, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d907b-233">En la página **Confirmación**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-233">On the **Confirmation** page, click **Configure**.</span></span>
    
8. <span data-ttu-id="d907b-234">En la página **Resultados**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-234">On the **Results** page, click **Close**.</span></span>

    
## <a name="phase-5-configure-office-365-for-federated-identity"></a><span data-ttu-id="d907b-235">Fase 5: Configurar Office 365 con identidad federada</span><span class="sxs-lookup"><span data-stu-id="d907b-235">Phase 5: Configure Office 365 for federated identity</span></span>

<span data-ttu-id="d907b-236">Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de APP1 con las credenciales de la cuenta CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="d907b-236">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="d907b-237">Siga estos pasos para configurar Azure AD Connect y la suscripción de Office 365 con autenticación federada:</span><span class="sxs-lookup"><span data-stu-id="d907b-237">Use these steps to configure Azure AD Connect and your Office 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="d907b-238">En el escritorio, haga doble clic en **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="d907b-238">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="d907b-239">En la página **Bienvenido a Azure AD Connect**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-239">On the **Welcome to Azure AD Connect** page, click **Configure**.</span></span>
    
3. <span data-ttu-id="d907b-240">En la página **Tareas adicionales**, haga clic en **Cambiar inicio de sesión de usuario** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-240">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="d907b-241">En la página **Conectar con Azure AD**, escriba el nombre y contraseña de la cuenta de administrador global de Office 365 y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-241">On the **Connect to Azure AD** page, type your Office 365 global administrator account name and password, and then click **Next**.</span></span>
    
5. <span data-ttu-id="d907b-242">En la página **Inicio de sesión de usuario**, haga clic en **Federación con AD FS** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-242">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d907b-243">En la página **Granja de AD FS**, haga clic en **Usar una granja de AD FS**, escriba **ADFS1** en **Nombre del servidor** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-243">On the **AD FS farm** page, click **Use an existing AD FS farm**, type **ADFS1** in **Server Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d907b-244">Cuando le soliciten las credenciales del servidor, escriba las credenciales de la cuenta CORP\\User1 y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-244">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then click **OK**.</span></span>
    
8. <span data-ttu-id="d907b-245">En la página de credenciales **Administrador de dominio**, escriba **CORP\\User1** en **Nombre de usuario** y la contraseña de la cuenta en **Contraseña** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-245">On the **Domain Administrator** credentials page, type **CORP\\User1** in **Username** and the account password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d907b-246">En la página **Cuenta del servicio AD FS**, escriba **CORP\\ADFS-Service** en **Nombre de usuario de dominio** y la contraseña de la cuenta en **Contraseña de usuario de dominio** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-246">On the **AD FS service account** page, type **CORP\\ADFS-Service** in **Domain Username** and the account password in **Domain User Password**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="d907b-247">En la página **Dominio de Azure AD**, en **Dominio**, seleccione el nombre del dominio que ha creado y agregado anteriormente a la suscripción de Office 365 en la fase 1 y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d907b-247">On the **Azure AD Domain** page, in **Domain**, select the name of the domain you previously created and added to your Office 365 subscription in Phase 1, and then click **Next**.</span></span>
    
11. <span data-ttu-id="d907b-248">En la página **Listo para configurar**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-248">On the **Ready to configure** page, click **Configure**.</span></span>
    
12. <span data-ttu-id="d907b-249">En la página **Instalación completada**, haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="d907b-249">On the **Installation complete** page, click **Verify**.</span></span>
    
    <span data-ttu-id="d907b-250">Debe ver mensajes que indican que tanto la configuración de Internet como la de la intranet se han comprobado.</span><span class="sxs-lookup"><span data-stu-id="d907b-250">You should see messages indicating that both the intranet and Internet configuration was verified.</span></span>
    
13. <span data-ttu-id="d907b-251">En la página **Instalación completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="d907b-251">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="d907b-252">Para demostrar que la autenticación federada funciona:</span><span class="sxs-lookup"><span data-stu-id="d907b-252">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="d907b-253">Abra una nueva instancia privada del explorador en el equipo local y vaya a[https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d907b-253">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="d907b-254">Para obtener las credenciales de inicio de sesión, escriba **user1@**\<el dominio que creado en la fase 1>.</span><span class="sxs-lookup"><span data-stu-id="d907b-254">For the sign-in credentials, type **user1@**\<the domain created in Phase 1>.</span></span> 
    
    <span data-ttu-id="d907b-p110">Por ejemplo, si el dominio de prueba es **testlab.contoso.com**, escribirá «user1@testlab.contoso.com». Presione TAB o permita que Office 365 le redirija automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d907b-p110">For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com". Press TAB or allow Office 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="d907b-p111">Ahora debe ver una página **Su conexión no es privada**. Está viendo esto porque ha instalado un certificado autofirmado en ADFS1 que su equipo de escritorio no puede validar. En una implementación de producción de autenticación federada, usará un certificado de una entidad de certificación de confianza y sus usuarios no verán esta página.</span><span class="sxs-lookup"><span data-stu-id="d907b-p111">You should now see a **Your connection is not private** page. You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate. In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="d907b-260">En la página **Su conexión no es privada**, haga clic en **Avanzadas** y luego en **Continuar con \<su FQDN del Servicio de federación>**.</span><span class="sxs-lookup"><span data-stu-id="d907b-260">On the **Your connection is not private** page, click **Advanced**, and then click **Proceed to \<your federation service FQDN>**.</span></span> 
    
4. <span data-ttu-id="d907b-261">En la página con el nombre de su organización ficticia, inicie sesión con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d907b-261">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="d907b-262">**CORP\\User1** como nombre</span><span class="sxs-lookup"><span data-stu-id="d907b-262">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="d907b-263">Contraseña de la cuenta User1</span><span class="sxs-lookup"><span data-stu-id="d907b-263">The password for the User1 account</span></span>
    
    <span data-ttu-id="d907b-264">Debe ver la página **principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="d907b-264">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="d907b-p112">En este procedimiento, se muestra que su suscripción de prueba de Office 365 está federada con el dominio corp.contoso.com de AD DS hospedado en DC1. Estos son los conceptos básicos del proceso de autenticación:</span><span class="sxs-lookup"><span data-stu-id="d907b-p112">This procedure demonstrates that your Office 365 trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="d907b-267">Cuando use el dominio federado que ha creado en la fase 1 en el nombre de cuenta de inicio de sesión, Office 365 redirige su explorador al FQDN del Servicio de federación y a PROXY1.</span><span class="sxs-lookup"><span data-stu-id="d907b-267">When you use the federated domain that you created in Phase 1 within the sign-in account name, Office 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="d907b-268">PROXY1 envía a su equipo local la página de inicio de sesión de la compañía ficticia.</span><span class="sxs-lookup"><span data-stu-id="d907b-268">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="d907b-269">Cuando envía CORP\\User1 y la contraseña a PROXY1, estos se reenvían a ADFS1.</span><span class="sxs-lookup"><span data-stu-id="d907b-269">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="d907b-270">ADFS1 valida CORP\\User1 y la contraseña con DC1 y envía a su equipo local un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d907b-270">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="d907b-271">El equipo local envía el token de seguridad a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d907b-271">Your local computer sends the security token to Office 365.</span></span>
    
6. <span data-ttu-id="d907b-272">Office 365 valida que ese token de seguridad se haya creado mediante ADFS1 y permite el acceso.</span><span class="sxs-lookup"><span data-stu-id="d907b-272">Office 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="d907b-p113">Su suscripción de evaluación de Office 365 ahora está configurada con la autenticación federada. Puede usar este entorno de desarrollo y prueba para escenarios de autenticación avanzados.</span><span class="sxs-lookup"><span data-stu-id="d907b-p113">Your Office 365 trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="d907b-275">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="d907b-275">Next step</span></span>

<span data-ttu-id="d907b-276">Cuando esté listo para implementar la autenticación federada de alta disponibilidad preparada para producción de Microsoft 365 u Office 365 en Azure, consulte [Implementar la autenticación federada de alta disponibilidad para Office 365 en Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).</span><span class="sxs-lookup"><span data-stu-id="d907b-276">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 or Office 365 in Azure, see [Deploy high availability federated authentication for Office 365 in Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).</span></span>
  
