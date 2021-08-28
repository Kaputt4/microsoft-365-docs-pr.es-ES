---
title: Configuración básica empresarial simulada para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use esta Guía del laboratorio de pruebas para crear un entorno de prueba de empresa simulado para Microsoft 365 para empresas.
ms.openlocfilehash: e3576c5d7e1a00069dd5dd46d1b1e6063da217bf
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575257"
---
# <a name="the-simulated-enterprise-base-configuration"></a>La configuración básica empresarial simulada

*Esta Guía del laboratorio de pruebas se puede usar tanto Microsoft 365 entornos de prueba empresariales como Office 365 Enterprise de prueba.*

En este artículo se describe cómo crear un entorno simplificado para Microsoft 365 empresa que incluya:

- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Una intranet de organización simplificada conectada a Internet, formada por tres máquinas virtuales en una red virtual de Azure (DC1, APP1 y CLIENT1).
 
![La configuración base de empresa simulada.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

La creación de un entorno de prueba simplificado implica dos fases:
- [Fase 1: Crear una intranet simulada](#phase-1-create-a-simulated-intranet)
- [Fase 2: crear la suscripción a Microsoft 365 E5](#phase-2-create-your-microsoft-365-e5-subscription)

Puede usar el entorno resultante para probar las características y la funcionalidad de [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) para empresas con guías de laboratorio de prueba [adicionales](m365-enterprise-test-lab-guides.md) o por su cuenta.

![Guías del laboratorio de pruebas para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-create-a-simulated-intranet"></a>Fase 1: Crear una intranet simulada

En esta fase, cree una intranet simulada en servicios de infraestructura de Azure que incluya un controlador de dominio de Servicios de dominio de Active Directory (AD DS), un servidor de aplicaciones y un equipo cliente.

Estos equipos se usarán en otras Microsoft 365 guías del laboratorio de pruebas [empresariales](m365-enterprise-test-lab-guides.md) para configurar y demostrar la identidad híbrida y otras funcionalidades.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Método 1: Crear la intranet simulada con una plantilla de Azure Resource Manager.

En este método, se usa una plantilla de Azure Resource Manager para crear la intranet simulada. Las plantillas de Azure Resource Manager contienen todas las instrucciones para crear la infraestructura de red de Azure, las máquinas virtuales y su configuración.

Antes de implementar la plantilla, lea la página [README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) de la plantilla y tenga lista la siguiente información:

- El nombre de dominio DNS público del entorno de prueba (testlab. \<*your public domain*> ). Escribirá este nombre en el campo **Nombre de dominio** de la página **Implementación** personalizada.
- Un prefijo de etiqueta DNS para las URL de las direcciones IP públicas de sus máquinas virtuales. Tendrá que escribir esta etiqueta en el campo **Prefijo de etiqueta Dns** de la página **implementación personalizada**.

Después de leer las instrucciones, seleccione **Implementar en Azure** en la página [README de la](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) plantilla para empezar.

>[!Note]
>La intranet simulada creada por la plantilla de Azure Resource Manager requiere una suscripción de Azure de pago.

Una vez completada la plantilla, la configuración tiene este aspecto:

![Intranet simulada en los servicios de infraestructura de Azure.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Método 2: Crear la intranet simulada con Azure PowerShell

En este método, utilizará Windows PowerShell y el módulo de Azure PowerShell para crear la infraestructura de red, las máquinas virtuales y su configuración.

Use este método si quiere obtener experiencia en la creación de elementos de una infraestructura de Azure paso a paso con PowerShell. Puede personalizar los bloques de comandos de PowerShell para la implementación de otras máquinas virtuales en Azure.

#### <a name="step-1-create-dc1"></a>Paso 1: Crear DC1

En este paso, se crea una red virtual de Azure y se agrega DC1, una máquina virtual que es un controlador de dominio para un dominio de AD DS.

En primer lugar, inicie un símbolo del sistema de Windows PowerShell en el equipo local.
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](/powershell/azureps-cmdlets-docs/). 
  
Inicie sesión en su cuenta de Azure con el siguiente comando.
  
```powershell
Connect-AzAccount
```

Obtenga su nombre de suscripción mediante el comando siguiente.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Configure su suscripción de Azure. Reemplace todo dentro de las comillas, incluidos los corchetes angulares ("<" y ">"), por el nombre correcto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Después, cree un nuevo grupo de recursos para su entorno de pruebas empresarial simulado. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Cree el nuevo grupo de recursos con estos comandos. Reemplace todo dentro de las comillas, incluidos los corchetes angulares, por los nombres correctos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

A continuación, cree la red virtual TestLab que hospedará la subred de red corporativa del entorno de empresa simulado y protéjala con un grupo de seguridad de red. Rellene el nombre del grupo de recursos y ejecute estos comandos en el símbolo del sistema de PowerShell en el equipo local.
  
```powershell
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

Luego, debe crear la máquina virtual DC1 y configurarla como controlador de dominio para **testlab.**\<your public domain> Un dominio de AD DS y un servidor DNS para las máquinas virtuales de la red virtual TestLab. Por ejemplo, si el nombre de dominio público es **<span>contoso</span>.com**, la máquina virtual DC1 será un controlador de dominio para el dominio **<span>testlab</span>.contoso.com**.
  
Para crear una máquina virtual de Azure para DC1, indique el nombre de su grupo de recursos y ejecute estos comandos desde el símbolo del sistema de PowerShell en su equipo local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
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

Se le pedirá un nombre de usuario y una contraseña para la cuenta de administrador local en DC1. Use una contraseña segura y registre el nombre de usuario y la contraseña en una ubicación segura.
  
A continuación, conéctese a la máquina virtual DC1:
  
1. En [Azure Portal,](https://portal.azure.com)seleccione **Grupos** de recursos > <nombre del nuevo grupo de recursos ***_> > _* DC1**  >  **Conectar**.
    
2. En el panel abierto, seleccione **Descargar archivo RDP**. Abra el archivo DC1.rdp que se descarga y, a continuación, **seleccione Conectar**.
    
3. Especifique el nombre de la cuenta del administrador local de DC1:
    
   - Para Windows 7:
    
     En el **Seguridad de Windows** de diálogo, **seleccione Usar otra cuenta**. En **Nombre de usuario,** escriba el nombre de cuenta de administrador local de **DC1 \\** < >.
    
   - Para Windows 8 o Windows 10:
    
     En el **Seguridad de Windows** de diálogo, seleccione **Más** opciones y, a continuación, **seleccione Usar una cuenta diferente.** En **Nombre de usuario,** escriba el nombre de cuenta de administrador local de **DC1 \\** < >.
    
4. En **Contraseña**, escriba la contraseña de la cuenta de administrador local y, a continuación, **seleccione Aceptar**.
    
5. Cuando se le pida, seleccione **Sí**.
    
Después, agregue otro disco de datos como nuevo volumen con la letra de unidad F: con este comando en un símbolo del sistema de Windows PowerShell con nivel de administrador en DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

A continuación, configure DC1 como controlador de dominio y servidor DNS para el dominio **testlab.**\<*your public domain*> . Especifique el nombre de dominio público, quite los corchetes angulares y, a continuación, ejecute estos comandos en un símbolo del sistema Windows PowerShell en DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Debe especificar una contraseña de administrador de modo seguro. Guarde esta contraseña en un lugar seguro.
  
Tenga en cuenta que estos comandos pueden tardan unos minutos en completarse.
  
Después de que DC1 se reinicie, vuelva a conectarse a la máquina virtual de DC1.
  
1. En [Azure Portal,](https://portal.azure.com)seleccione **Grupos de** recursos > <*nombre* del grupo de recursos> > **DC1**  >  **Conectar**.
    
2. Ejecute el archivo DC1.rdp que se descarga y, a continuación, **seleccione Conectar**.
    
3. En **Seguridad de Windows**, seleccione **Usar otra cuenta**. En **Nombre de usuario,** escriba **TESTLAB \\** nombre de cuenta de administrador local < *>.*
    
4. En el **cuadro Contraseña,** escriba la contraseña de la cuenta de administrador local y, a continuación, seleccione **Aceptar**.
    
5. Cuando se le pida, seleccione **Sí**.
    
A continuación, cree una cuenta de usuario en Active Directory que se usará al iniciar sesión en equipos miembros del dominio TESTLAB. En un símbolo del sistema de Windows PowerShell con un nivel de administrador, ejecute este comando:
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Tenga en cuenta que este comando le solicita que proporcione la contraseña de la cuenta User1. Esta cuenta se usará para las conexiones de escritorio remoto para todos los equipos miembros del dominio TESTLAB, así que elija una contraseña segura. Anote la contraseña de la cuenta User1 y almacénela en una ubicación segura.
  
Después, configure la nueva cuenta User1 como administrador de esquema, empresa o dominio. En un símbolo del sistema de Windows PowerShell con nivel de administrador, ejecute este comando.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Cierre la sesión de Escritorio remoto con DC1 y vuelva a conectarse con la cuenta TESTLAB\\User1.
  
Después, para permitir el tráfico desde la herramienta Ping, ejecute este comando desde un símbolo del sistema de Windows PowerShell con nivel de administrador:
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

La configuración actual tiene este aspecto:
  
![Paso 1 de la configuración base de empresa simulada.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Paso 2: Configurar APP1

En este paso, creará y configurará APP1, que es un servidor de aplicaciones que proporciona inicialmente servicios de uso compartido de archivos y web.

Para crear una máquina virtual de Azure para APP1, indique el nombre de su grupo de recursos y ejecute estos comandos desde el símbolo del sistema en su equipo local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Después, conéctese a la máquina virtual de APP1 usando el nombre y la contraseña de la cuenta de administrador local de APP1 y abra un símbolo del sistema de Windows PowerShell.
  
Para comprobar la resolución de nombres y la comunicación de red entre APP1 y DC1, ejecute el comando **ping dc1.testlab.**\<*your public domain name*> y verifique que haya cuatro respuestas.
  
Después, una la máquina virtual de APP1 al dominio TESTLAB con estos comandos en un símbolo del sistema de Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Tenga en cuenta que después de ejecutar el **comando Add-Computer,** debe proporcionar las credenciales de la cuenta de dominio TESTLAB \\ User1.
  
Una vez reiniciado APP1, conéctese a él con la cuenta TESTLAB\\User1 y luego abra un símbolo del sistema de Windows PowerShell con nivel de administrador.
  
Después, convierta APP1 en un servidor web con este comando en el símbolo del sistema de Windows PowerShell a nivel de administrador en APP1.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Por último, cree una carpeta compartida y un archivo de texto dentro de la carpeta en APP1 con estos comandos de PowerShell.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

La configuración actual tiene este aspecto:
  
![Paso 2 de la configuración base de empresa simulada.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Paso 3: Configurar CLIENT1.

En este paso, creará y configurará CLIENT1, que actúa como un equipo de escritorio, una tableta o un portátil típico de la intranet.

> [!NOTE]  
> El siguiente conjunto de comandos crea CLIENT1 con Windows Server 2016 Datacenter, lo que se puede realizar en todos los tipos de suscripciones de Azure. Si tiene una suscripción de Azure basada en Visual Studio, puede crear CLIENT1 con Windows 10 en [Azure Portal](https://portal.azure.com).
  
Para crear una máquina virtual de Azure para CLIENT1, rellene el nombre del grupo de recursos y ejecute estos comandos en el símbolo del sistema en el equipo local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Después, conéctese a la máquina virtual de CLIENT1 usando el nombre y la contraseña de la cuenta de administrador local de CLIENT1, y abra un símbolo del sistema de nivel de administrador de Windows PowerShell.
  
Para comprobar la resolución de nombres y la comunicación de red entre CLIENT1 y DC1, ejecute el comando **ping dc1.testlab.**\<*your public domain name*> en el símbolo del sistema de Windows PowerShell y verifique que haya cuatro respuestas.
  
Después, una la máquina virtual de CLIENT1 al dominio TESTLAB con estos comandos en un símbolo del sistema de Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Recuerde que debe indicar las credenciales de la cuenta de dominio TESTLAB\\User1 después de ejecutar el comando **Add-Computer**.
  
Una vez reiniciado CLIENT1, conéctese a él con el nombre y contraseña de la cuenta TESTLAB\\User1 y luego abra un símbolo del sistema de nivel de administrador de Windows PowerShell.
  
Después, compruebe que tiene acceso a recursos compartidos de archivos y web en APP1 desde CLIENT1.
  
1. En el Administrador del servidor, en el panel de árbol, seleccione **Servidor local**.
    
2. En **Propiedades de CLIENT1**, seleccione **Activar junto** a Configuración de seguridad mejorada **de IE**.
    
3. En **Configuración de seguridad mejorada de Internet Explorer,** seleccione **Desactivado** **para** administradores y usuarios **y,** a continuación, seleccione **Aceptar**.
    
4. En la pantalla Inicio, **seleccione Internet Explorer** y, a continuación, seleccione **Aceptar**.
    
5. En la barra de direcciones, escriba **http <span>://</span>app1.testab.** \<*your public domain name*> **/** y, a continuación, presione **ENTRAR**. Debería ver la página web predeterminada de Internet Information Services para APP1.
    
6. En la barra de tareas de escritorio, seleccione el icono Explorador de archivos.
    
7. En la barra de direcciones, escriba **\\ \\ Archivos \\ de app1** y, a continuación, presione **Entrar**. Debería ver una ventana de carpeta con el contenido de la carpeta compartida Archivos.
    
8. En la ventana de la carpeta compartida **Archivos**, haga doble clic en el archivo **Example.txt**. Debería ver el contenido del archivo Example.txt.
    
9. Cierre las ventanas de **example.txt: Bloc de notas** y de la carpeta compartida **Archivos**.
    
La configuración actual tiene este aspecto:
  
![Paso 3 de la configuración base de empresa simulada.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Fase 2: crear la suscripción a Microsoft 365 E5

En esta fase, creará una nueva suscripción a Microsoft 365 E5 que usa un nuevo espacio empresarial de Azure AD, que es independiente de su suscripción de producción. Puede hacer esto de dos maneras:

- Usar una suscripción de prueba de Microsoft 365 E5.

  La suscripción de prueba de Microsoft 365 E5 es de 30 días, que puede ampliarse fácilmente a 60 días. Cuando la suscripción de prueba expire, debe convertirla en suscripción de pago o crear una nueva suscripción de prueba. Crear nuevas suscripciones de prueba significa que perderá la configuración, que podría incluir escenarios complejos.  

- Usar una suscripción de producción independiente de Microsoft 365 E5 con un pequeño número de licencias.

  Este es un costo adicional, pero garantiza que tiene un entorno de prueba de trabajo que no expira; en él, puede probar características, configuraciones y escenarios. Puede usar el mismo entorno de pruebas a largo plazo para pruebas de concepto, demostración a compañeros y administración, y desarrollo y pruebas de aplicaciones. Esta método es el recomendado.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrarse para una suscripción de prueba de Office 365 E5

Desde Azure Portal, conéctese a CLIENT1 con la cuenta CORP\User1.

Para crear una nueva suscripción de prueba de Office 365 E5, siga las instrucciones que se indican en [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) de la guía del laboratorio de pruebas de la configuración básica ligera.

Para configurar su nueva suscripción de prueba de Office 365 E5, siga las instrucciones que se indican en [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) de la guía del laboratorio de pruebas de la configuración básica ligera.

#### <a name="using-an-office-365-e5-test-environment"></a>Usar un entorno de prueba de Office 365 E5

Si solo necesita un entorno Office 365 prueba, no es necesario leer el resto de este artículo.

Para obtener guías de laboratorio de prueba adicionales que se aplican a Microsoft 365 y Office 365, consulte Microsoft 365 guías de laboratorio [de pruebas empresariales](m365-enterprise-test-lab-guides.md).

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Agregar una suscripción de prueba de Microsoft 365 E5

Para agregar una Microsoft 365 E5 de prueba y configurar las cuentas de usuarios con licencias, siga las instrucciones de la fase [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) de la Guía de pruebas de configuración base ligera.

  
## <a name="results"></a>Resultados

Su entorno de desarrollo y prueba ahora tiene:
  
- Suscripción de prueba de Microsoft 365 E5.
- Todas las cuentas de usuario adecuadas están habilitadas para usar Microsoft 365 E5.
- Una intranet simulada y simplificada.
    
La configuración final tiene este aspecto:
  
![Fase 2 de la configuración base de empresa simulada.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
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