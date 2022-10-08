---
title: Autenticación federada de alta disponibilidad Fase 2 Configuración de controladores de dominio
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Resumen: configure los controladores de dominio y el servidor de sincronización de directorios para la autenticación federada de alta disponibilidad para Microsoft 365 en Microsoft Azure.'
ms.openlocfilehash: 6d6b955b88385c3d44eebde0ab6bfd7ba6953f39
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68186665"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Fase 2 de la autenticación federada de alta disponibilidad: Configurar controladores de dominio

En esta fase de implementación de alta disponibilidad para la autenticación federada de Microsoft 365 en los servicios de infraestructura de Azure, configurará dos controladores de dominio y el servidor de sincronización de directorios en la red virtual de Azure. Después, las solicitudes web de los clientes para la autenticación se pueden autenticar en la red virtual de Azure, en lugar de enviar ese tráfico de autenticación por la conexión VPN de sitio a sitio a la red local.
  
> [!NOTE]
> Servicios de federación de Active Directory (AD FS) (AD FS) no puede usar Azure Active Directory (Azure AD) como sustituto de los controladores de dominio de Servicios de dominio de Active Directory (AD DS). 
  
Debe completar esta fase antes de pasar a [Fase 3: Configurar servidores de AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Consulte Implementación de la [autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas las fases.
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Crear las máquinas virtuales del controlador de dominio en Azure

Primero, necesita rellenar la columna de **Nombre de la máquina virtual** de la Tabla M y modificar los tamaños de las máquinas virtuales según sea necesario en la columna **Tamaño mínimo**.
  
|**Elemento**|**Nombre de máquina virtual**|**Imagen de la galería**|**Tipo de almacenamiento**|**Tamaño mínimo**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  (primer controlador de dominio, ejemplo DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![Línea.](../media/Common-Images/TableLine.png)  (segundo controlador de dominio, ejemplo DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![Línea.](../media/Common-Images/TableLine.png) (servidor de sincronización de directorios, ejemplo DS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![Línea.](../media/Common-Images/TableLine.png) (primer servidor de AD FS, ejemplo ADFS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![Línea.](../media/Common-Images/TableLine.png) (segundo servidor de AD FS, ejemplo ADFS2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![Línea.](../media/Common-Images/TableLine.png) (primer servidor proxy de aplicación web, ejemplo WEB1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![Línea.](../media/Common-Images/TableLine.png) (segundo servidor proxy de aplicación web, ejemplo WEB2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabla M: Máquinas virtuales para la autenticación federada de alta disponibilidad para Microsoft 365 en Azure**
  
Para obtener la lista completa de tamaños de máquinas virtuales, vea [Tamaños de máquinas virtuales](/azure/virtual-machines/sizes).
  
El siguiente bloque de comandos de Azure PowerShell crea las máquinas virtuales de los dos controladores de dominio. Especifique los valores de las variables, quitando los \< and > caracteres. Tenga en cuenta que este bloque de comandos de Azure PowerShell usa valores de las siguientes tablas:
  
- Tabla N, para las máquinas virtuales
    
- Tabla R, para los grupos de recursos
    
- Tabla V, para la configuración de la red virtual
    
- Tabla S, para las subredes
    
- Tabla I, para las direcciones IP estáticas
    
- Tabla A, para los conjuntos de disponibilidad
    
Recuerde que ha definido las tablas R, V, S, I y A en [la fase 1: Configuración de Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Consulte [Introducción a Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Después de especificar todos los valores correctos, ejecute el bloque resultante en el símbolo del sistema de Azure PowerShell o en el Entorno de scripting integrado (ISE) de PowerShell en el equipo local.
  
> [!TIP]
> Para generar bloques de comandos de PowerShell listos para ejecutarse en función de la configuración personalizada, use este [libro de configuración de Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.
  
## <a name="configure-the-first-domain-controller"></a>Configurar el primer controlador de dominio

Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.
  
A continuación, agregue el disco de datos adicional al primer controlador de dominio con este comando desde un símbolo del sistema Windows PowerShell **en la primera máquina virtual del controlador de dominio**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

El paso siguiente es probar la conectividad del primer controlador de dominio a las ubicaciones en la red de la organización con el comando **ping** para hacer ping a los nombres y direcciones IP de los recursos en la red de la organización.
  
This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.
  
Después, desde el símbolo del sistema de Windows PowerShell en el primer controlador de dominio, ejecute los comandos siguientes:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

You will be prompted to supply the credentials of a domain administrator account. The computer will restart.
  
## <a name="configure-the-second-domain-controller"></a>Configurar el segundo controlador de dominio

Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.
  
A continuación, debe agregar el disco de datos adicional al segundo controlador de dominio con este comando desde un símbolo del sistema de Windows PowerShell **en la segunda máquina virtual del controlador de dominio**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Después, ejecute los comandos siguientes:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

Se le pedirá que especifique las credenciales de una cuenta de administrador de dominio. Se reiniciará el equipo.
  
Después, tendrá que actualizar los servidores DNS de la red virtual para que Azure asigne a las máquinas virtuales las direcciones IP de los dos nuevos controladores de dominio para que las usen como sus servidores DNS. Rellene las variables y ejecute estos comandos desde un símbolo del sistema de Windows PowerShell en el equipo local:
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.
  
Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>Configuración del servidor de sincronización de directorios

Use el cliente de escritorio remoto que prefiera y cree una conexión de escritorio remoto a la máquina virtual del servidor de sincronización de directorios. Use el nombre DNS de la intranet o el nombre de equipo y las credenciales de la cuenta de administrador local.
  
A continuación, únase al dominio de AD DS adecuado con estos comandos en el símbolo del sistema de Windows PowerShell.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Esta es la configuración completada después de la finalización correcta de esta fase, con los nombres de equipo de marcadores de posición.
  
**Fase 2: Controladores de dominio y servidor de sincronización de directorios para la infraestructura de autenticación federada de alta disponibilidad en Azure**

![Fase 2 de la infraestructura de autenticación federada de Microsoft 365 de alta disponibilidad en Azure con controladores de dominio.](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Paso siguiente

Usar [fase 3: Configurar servidores de AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) para seguir configurando esta carga de trabajo.
  
## <a name="see-also"></a>Consulta también

[Implementar la autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidad federada para el entorno de desarrollo y pruebas de Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)