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
ms.openlocfilehash: c7ff838522c0bd97da4ffff5122454b128f97bf2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694165"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Identidad federada para el entorno de prueba de Microsoft 365

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

Microsoft 365 admite la identidad federada. Esto significa que, en lugar de realizar la validación de las credenciales él mismo, Microsoft 365 dirige al usuario que se conecta a un servidor de autenticación federada en el que Microsoft 365 confía. Si las credenciales del usuario son correctas, el servidor de autenticación federada emite un token de seguridad que el cliente envía luego a Microsoft 365 como prueba de autenticación. La identidad federada permite la descarga y el escalado vertical de autenticación para una suscripción de Microsoft 365 y escenarios avanzados de seguridad y autenticación.
  
En este artículo se describe cómo configurar la autenticación federada para el entorno de prueba de Microsoft 365, lo que da como resultado lo siguiente:

![La autenticación federada para el entorno de pruebas de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Esta configuración se compone de: 
  
- Una suscripción de prueba o producción de Microsoft 365 E5.
    
- Una intranet de organización simplificada conectada a Internet, que consta de cinco máquinas virtuales en una subred de una red virtual de Azure (DC1, APP1, cliente1, ADFS1 y PROXY1). Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas del dominio de servicios de dominio de Active Directory con Microsoft 365. PROXY1 recibe las solicitudes de autenticación entrantes. ADFS1 valida las credenciales con DC1 y emite tokens de seguridad.
    
Existen cinco fases para configurar este entorno de desarrollo y pruebas:
  
1. Crear el entorno de prueba de la empresa simulada con la sincronización de hash de contraseñas.
    
2. Crear el servidor de AD FS (ADFS1)
    
3. Crear el servidor proxy web (PROXY1)
    
4. Crear un certificado autofirmado y configurar ADFS1 y PROXY1
    
5. Configurar Microsoft 365 con identidad federada
    
> [!NOTE]
> No puede configurar este entorno de prueba con una suscripción de prueba de Azure. 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Esta configuración se compone de: 
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-create-the-ad-fs-server"></a>Fase 2: Crear el servidor de AD FS

Un servidor de AD FS proporciona autenticación federada entre Microsoft 365 y las cuentas del dominio corp.contoso.com hospedado en DC1.
  
Para crear una máquina virtual de Azure para ADFS1, indique el nombre de la suscripción y del grupo de recursos y una ubicación de Azure para la configuración básica. Después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.
  
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

Después, vaya a [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con el nombre y contraseña de la cuenta de administrador local de ADFS1 y abra un símbolo del sistema de Windows PowerShell.
  
Para comprobar la comunicación de red y la resolución de nombres entre ADFS1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.
  
A continuación, una la máquina virtual de ADFS1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Este es el resultado de la configuración.
  
![Servidor de AD FS agregado a DirSync para el entorno de prueba de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Fase 3: Crear el servidor proxy web

PROXY1 permite crear conexiones proxy de mensajes de autenticación entre usuarios que intentan autenticarse y ADFS1.
  
Para crear una máquina virtual de Azure para PROXY1, indique el nombre de su grupo de recursos y una ubicación de Azure y, después, ejecute estos comandos en el símbolo del sistema de Azure PowerShell en el equipo local.
  
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
> PROXY1 se asigna como una dirección IP pública estática porque creará un registro DNS público que la señale y no debe cambiarse cuando reinicie la máquina virtual de PROXY1. 
  
Después, agregue una regla al grupo de seguridad de red para que la subred CorpNet permita tráfico entrante no solicitado desde Internet a la dirección IP privada de PROXY1 y al puerto TCP 443. Ejecute estos comandos desde el símbolo del sistema de Azure PowerShell en su equipo local.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de PROXY1 con el nombre y contraseña de la cuenta de administrador local de PROXY1 y luego abra un símbolo del sistema de Windows PowerShell en PROXY1.
  
Para comprobar la comunicación de red y la resolución de nombres entre PROXY1 y DC1, ejecute el comando **ping dc1.corp.contoso.com** y compruebe que hay cuatro respuestas.
  
A continuación, una la máquina virtual de PROXY1 al dominio CORP con estos comandos en un símbolo del sistema de Windows PowerShell en PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Muestre la dirección IP pública de PROXY1 con estos comandos de Azure PowerShell en el equipo local:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Después, trabaje con su proveedor de DNS público y cree un nuevo registro DNS A público para **fs.testlab.**\<your DNS domain name> se resuelva en la dirección IP mostrada mediante el comando **Write-Host**. En lo sucesivo, se hace referencia a **fs.testlab.**\<your DNS domain name> como el *FQDN del servicio de federación*.
  
Después, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y ejecute los siguientes comandos en un símbolo del sistema de Windows PowerShell con nivel de administrador:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Estos comandos crean un registro DNS A interno para que las máquinas virtuales de la red virtual de Azure pueden resolver el FQDN interno de la federación en la dirección IP privada de ADFS1.
  
Este es el resultado de la configuración.
  
![El servidor proxy de la aplicación web agregado a DirSync para el entorno de prueba de Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fase 4: Crear un certificado autofirmado y configurar ADFS1 y PROXY1

En esta fase, crea un certificado digital autofirmado para su FQDN del Servicio de federación y configura ADFS1 y PROXY1 como una granja de servidores de AD FS.
  
En primer lugar, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de DC1 con las credenciales de CORP\\User1 y luego abra un símbolo del sistema de Windows PowerShell con nivel de administrador. 
  
Después, cree una cuenta de servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Tenga en cuenta que este comando le solicita que proporcione la contraseña de la cuenta. Elija una contraseña segura y guárdela en una ubicación segura. La necesitará para esta fase y para la fase 5.
  
Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de ADFS1 con las credenciales de CORP\\User1. Abra un símbolo del sistema de Windows PowerShell con nivel de administrador en ADFS1, indique el FQDN del Servicio de federación y luego ejecute estos comandos para crear un certificado autofirmado:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Después, use estos pasos para guardar el nuevo certificado autofirmado como archivo.
  
1. Haga clic en **Inicio**, escriba**mmc.exe** y presione **Entrar**.
    
2. Haga clic en **Archivo > Agregar o quitar complemento**.
    
3. En **Agregar o quitar complementos**, haga doble clic en **Certificados** en la lista de complementos disponibles, haga clic en **Cuenta de equipo** y luego en **Siguiente**.
    
4. En **Seleccionar equipo**, haga clic en **Finalizar** y luego en **Aceptar**.
    
5. En el panel de árbol, abra **Certificados (equipo local) > Personal > Certificados**.
    
6. Haga clic con el botón derecho en el certificado con su FQDN del Servicio de federación, haga clic en **Todas las tareas** y luego en **Exportar**.
    
7. En la página de **bienvenida**, haga clic en **Siguiente**.
    
8. En la página **Exportar clave privada**, haga clic en **Sí** y luego en **Siguiente**.
    
9. En la página **Formato de archivo de exportación**, haga clic en **Exportar todas las propiedades extendidas** y luego en **Siguiente**.
    
10. En la página **Seguridad**, haga clic en **Contraseña** y escriba una contraseña en **Contraseña** y **Confirmar contraseña**.
    
11. En la página **Archivo que se va a exportar**, haga clic en **Examinar**.
    
12. Vaya a la carpeta **C:\\Certs**, escriba **SSL** en **Nombre de archivo** y luego haga clic en **Guardar**.
    
13. En la página **Archivo que se va a exportar**, haga clic en **Siguiente**.
    
14. En la página **Finalización del Asistente para exportación de certificados**, haga clic en **Finalizar**. Cuando se le solicite, haga clic en **Aceptar**.
    
Después, instale el servicio de AD FS con este comando en el símbolo del sistema de Windows PowerShell en ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Espere a que termine la instalación.
  
Después, configure el servicio de AD FS con estos pasos:
  
1. Haga clic en **Inicio** y luego en el icono **Administrador de servidores**.
    
2. En el panel de árbol del Administrador de servidores, haga clic en **AD FS**.
    
3. En la barra de herramientas de la parte superior, haga clic en el símbolo de advertencia naranja y luego en **Configure el servicio de federación en este servidor**.
    
4. En la página **principal** del Asistente para la configuración de los Servicios de federación de Active Directory, haga clic en **Siguiente**.
    
5. En la página **Conectarse a AD DS**, haga clic en **Siguiente**.
    
6. En la página **Especificar propiedades del servicio**:
    
  - En **Certificado SSL**, haga clic en la flecha abajo y luego en el certificado con el nombre del FQDN del Servicio de federación.
    
  - En **Nombre para mostrar del Servicio de federación**, escriba el nombre de la organización ficticia.
    
  - Haga clic en **Siguiente**.
    
7. En la página **Especificar cuenta de servicio**, haga clic en **Seleccionar** para **Nombre de cuenta**.
    
8. En **Seleccionar usuario o cuenta de servicio**, escriba **Servicio ADFS**, haga clic en **Comprobar nombres** y luego en **Aceptar**.
    
9. En **Contraseña de cuenta**, escriba la contraseña para la cuenta del servicio ADFS y luego en **Siguiente**.
    
10. En la página **Especificar base de datos de configuración**, haga clic en **Siguiente**.
    
11. En la página **Revisar opciones**, haga clic en **Siguiente**.
    
12. En la página **Comprobaciones de requisitos previos**, haga clic en **Configurar**.
    
13. En la página **Resultados**, haga clic en **Cerrar**.
    
14. Haga clic en **Inicio**, en el icono de encendido/apagado, en **Reiniciar** y luego en **Continuar**.
    
Desde [Azure Portal](https://portal.azure.com), conéctese a PROXY1 con las credenciales de la cuenta CORP\\User1.
  
Después, siga estos pasos para instalar el certificado autofirmado en **PROXY1 y APP1**.
  
1. Haga clic en **Inicio**, escriba**mmc.exe** y presione **Entrar**.
    
2. Haga clic en **Archivo > Agregar o quitar complemento**.
    
3. En **Agregar o quitar complementos**, haga doble clic en **Certificados** en la lista de complementos disponibles, haga clic en **Cuenta de equipo** y luego en **Siguiente**.
    
4. En **Seleccionar equipo**, haga clic en **Finalizar** y luego en **Aceptar**.
    
5. En el panel de árbol, abra **Certificados (equipo local) > Personal > Certificados**.
    
6. Haga clic con el botón derecho en **Personal**, haga clic en **Todas las tareas** y luego en **Importar**.
    
7. En la página de **bienvenida**, haga clic en **Siguiente**.
    
8. En la página **Archivo para importar**, escriba **\\\\adfs1\\certs\\ssl.pfx** y luego haga clic en **Siguiente**.
    
9. En la página **Protección de clave privada**, escriba la contraseña de certificado en **Contraseña** y luego haga clic en **Siguiente**.
    
10. En la página **Almacén de certificados**, haga clic en **Siguiente**.
    
11. En la página **Completando**, haga clic en **Finalizar**.
    
12. En la página **Almacén de certificados**, haga clic en **Siguiente**.
    
13. Cuando se le solicite, haga clic en **Aceptar**.
    
14. Haga clic en **Certificados** en el panel de árbol.
    
15. Haga clic con el botón derecho en el certificado y luego haga clic en **Copiar**.
    
16. En el panel de árbol, abra **Entidades de certificación raíz de confianza > Certificados**.
    
17. Mueva el puntero del mouse debajo de la lista de certificados instalados, haga clic con el botón derecho y luego haga clic en **Pegar**.
    
Abra un símbolo del sistema de PowerShell con el nivel de administrador y ejecute el comando siguiente:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Espere a que termine la instalación.
  
Use estos pasos para configurar el servicio proxy de aplicación web para usar ADFS1 como su servidor de federación:
  
1. Haga clic en **Iniciar** y luego en **Administrador del servidor**.
    
2. En el panel de árbol, haga clic en **Acceso remoto**.
    
3. En la barra de herramientas de la parte superior, haga clic en el símbolo de advertencia naranja y luego en **Abrir el Asistente para proxy de aplicación web**.
    
4. En la página **principal** del Asistente para configuración de Proxy de aplicación web, haga clic en **Siguiente**.
    
5. En la página **Servidor de federación**:
    
  - Escriba su FQDN del Servicio de federación en **Nombre del Servicio de federación**.
    
  - Escriba **CORP\\User1** en **Nombre de usuario**.
    
  - Escriba la contraseña de la cuenta User1 en **Contraseña**.
    
  - Haga clic en **Siguiente**.
    
6. En la página **Certificado de proxy de AD FS**, haga clic en la flecha abajo, en el certificado con su FQDN del Servicio de federación y luego en **Siguiente**.
    
7. En la página **Confirmación**, haga clic en **Configurar**.
    
8. En la página **Resultados**, haga clic en **Cerrar**.

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fase 5: Configurar Microsoft 365 con identidad federada

Use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual de APP1 con las credenciales de la cuenta CORP\\User1.
  
Siga estos pasos para configurar Azure AD Connect y la suscripción de Microsoft 365 con autenticación federada:
  
1. En el escritorio, haga doble clic en **Azure AD Connect**.
    
2. En la página **Bienvenido a Azure AD Connect**, haga clic en **Configurar**.
    
3. En la página **Tareas adicionales**, haga clic en **Cambiar inicio de sesión de usuario** y, a continuación, haga clic en **Siguiente**.
    
4. En la página **Conectar con Azure AD**, escriba el nombre y contraseña de la cuenta de administrador global y luego haga clic en **Siguiente**.
    
5. En la página **Inicio de sesión de usuario**, haga clic en **Federación con AD FS** y luego en **Siguiente**.
    
6. En la página **Granja de AD FS**, haga clic en **Usar una granja de AD FS**, escriba **ADFS1** en **Nombre del servidor** y luego haga clic en **Siguiente**.
    
7. Cuando le soliciten las credenciales del servidor, escriba las credenciales de la cuenta CORP\\User1 y luego haga clic en **Aceptar**.
    
8. En la página de credenciales **Administrador de dominio**, escriba **CORP\\User1** en **Nombre de usuario** y la contraseña de la cuenta en **Contraseña** y luego haga clic en **Siguiente**.
    
9. En la página **Cuenta del servicio AD FS**, escriba **CORP\\ADFS-Service** en **Nombre de usuario de dominio** y la contraseña de la cuenta en **Contraseña de usuario de dominio** y luego haga clic en **Siguiente**.
    
10. En la página **Dominio de Azure AD**, en **Dominio**, seleccione el nombre del dominio que ha creado y agregado anteriormente a la suscripción en la fase 1 y, después, haga clic en **Siguiente**.
    
11. En la página **Listo para configurar**, haga clic en **Configurar**.
    
12. En la página **Instalación completada**, haga clic en **Comprobar**.
    
    Debe ver mensajes que indican que tanto la configuración de Internet como la de la intranet se han comprobado.
    
13. En la página **Instalación completada**, haga clic en **Salir**.
    
Para demostrar que la autenticación federada funciona:
  
1. Abra una nueva instancia privada del explorador en el equipo local y vaya a[https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Para las credenciales de inicio de sesión, escriba **user1@**\<the domain created in Phase 1>. 
    
    Por ejemplo, si el dominio de prueba es **testlab.contoso.com**, escribirá «user1@testlab.contoso.com». Presione TAB o permita que Microsoft 365 le redirija automáticamente.
    
    Ahora debe ver una página **Su conexión no es privada**. Está viendo esto porque ha instalado un certificado autofirmado en ADFS1 que su equipo de escritorio no puede validar. En una implementación de producción de autenticación federada, usará un certificado de una entidad de certificación de confianza y sus usuarios no verán esta página.
    
3. En la página **Su conexión no es privada**, haga clic en **Avanzadas** y luego en **Continuar con \<your federation service FQDN>**. 
    
4. En la página con el nombre de su organización ficticia, inicie sesión con lo siguiente:
    
  - **CORP\\User1** como nombre
    
  - Contraseña de la cuenta User1
    
    Debe ver la página **principal de Microsoft Office**.
    
En este procedimiento, se muestra que su suscripción de prueba está federada con el dominio corp.contoso.com de AD DS hospedado en DC1. Estos son los conceptos básicos del proceso de autenticación:
  
1. Cuando use el dominio federado que ha creado en la fase 1 en el nombre de cuenta de inicio de sesión, Microsoft 365 redirige su explorador al FQDN del Servicio de federación y a PROXY1.
    
2. PROXY1 envía a su equipo local la página de inicio de sesión de la compañía ficticia.
    
3. Cuando envía CORP\\User1 y la contraseña a PROXY1, estos se reenvían a ADFS1.
    
4. ADFS1 valida CORP\\User1 y la contraseña con DC1 y envía a su equipo local un token de seguridad.
    
5. El equipo local envía el token de seguridad a Microsoft 365.
    
6. Microsoft 365 valida que ese token de seguridad se haya creado mediante ADFS1 y permite el acceso.
    
Su suscripción de evaluación ahora está configurada con la autenticación federada. Puede usar este entorno de desarrollo y prueba para escenarios de autenticación avanzados.
  
## <a name="next-step"></a>Paso siguiente

Cuando esté listo para implementar la autenticación federada de alta disponibilidad preparada para producción para Microsoft 365 en Azure, consulte [deploy High Availability Federated Authentication for microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
