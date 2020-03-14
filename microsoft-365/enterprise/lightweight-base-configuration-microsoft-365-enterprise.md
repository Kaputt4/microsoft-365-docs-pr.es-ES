---
title: Configuración básica ligera
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: Utilice esta guía de laboratorio de pruebas para crear un entorno de prueba ligero a con objeto de probar Microsoft 365 Enterprise.
ms.openlocfilehash: 4e90cc01cb37664f3084daf7295e9d59052809af
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633348"
---
# <a name="the-lightweight-base-configuration"></a>Configuración básica ligera

*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*

En este artículo se le ofrecen instrucciones paso a paso para crear un entorno simplificado con una suscripción Microsoft 365 E5 y un equipo que ejecute Windows 10 Enterprise. 

![El entorno de pruebas ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Use el entorno resultante para probar las características y funciones de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-create-your-office-365-e5-subscription"></a>Fase 1: Crear la suscripción de Office 365 E5

Inicie con una suscripción de prueba de Office 365 E5, después, agregue la suscripción a Microsoft 365 E5.

Para iniciar la suscripción de prueba a Office 365 E5, primero necesita el nombre de una compañía ficticia y una nueva cuenta Microsoft.
  
1. Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia: ![Línea](../media/Common-Images/TableLine.png)
    
2. Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.
    
  - Anote aquí el nombre y los apellidos de la nueva cuenta: ![Línea](../media/Common-Images/TableLine.png)
    
  - Anote la dirección de la cuenta de correo electrónico nueva aquí: ![Línea](../media/Common-Images/TableLine.png)Outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrarse para una suscripción de prueba de Office 365 E5

1. Abra el explorador de Internet en su equipo y vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial).
    
2. En la página **Gracias por elegir Office 365 E5**, especifique la dirección de su nueva cuenta de correo electrónico en el paso 1.
3. En el paso 2 del proceso de suscripción de prueba, escriba la información solicitada y, después, lleve a cabo la comprobación.
4. En el paso 3, escriba el nombre de la organización y después el nombre de la cuenta que será el administrador global de la suscripción. 
5. En el paso 4, registre la página de inicio de sesión aquí (seleccionar y copiar):  ![Línea](../media/Common-Images/TableLine.png) 
6. Registre aquí el identificador de usuario: ![Linea](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Anote en un lugar seguro la contraseña que escriba.
   Este valor se denominará **nombre de administrador global de Office 365**.
8. Haga clic en **Ir a Configuración**.
9. En el programa de instalación de Office 365 E5, haga clic en **Continuar usando *su organización*.onmicrosoft.com para el correo electrónico e inicio de sesión** y, a continuación, haga clic en **Salir y continuar más tarde**.

Debería ver el Centro de administración de Microsoft 365.
  
Tenemos que crear una suscripción de prueba de Office 365 para que su entorno de prueba tenga un inquilino de Azure AD separado de cualquier suscripción de pago que tenga actualmente. Esta separación significa que puede agregar y quitar usuarios y grupos en el espacio empresarial de prueba sin que afecte a las suscripciones de producción.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurar la suscripción de prueba de Office 365

En esta fase, se configura la suscripción a Office 365 con usuarios adicionales y se les asignan licencias de Office 365 E5.
  
Siga las instrucciones que se indican en [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) para conectarse a la suscripción a Office 365 con el módulo Azure Active Directory PowerShell para Graph desde su equipo.
    
En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre de administrador global de Office 365 (por ejemplo, svalladares@contosotoycompany.onmicrosoft.com) y la contraseña.
  
Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación, la contraseña de cuenta común y, después, ejecute los comandos siguientes desde el símbolo del sistema de PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> Aquí se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba. Evidentemente, esto no se recomienda en el caso de suscripciones de producción. 

### <a name="record-key-information-for-future-reference"></a>Guardar información clave para futuras referencias

Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365. Puede extender fácilmente la suscripción de prueba otros 30 días. Para un entorno de pruebas permanente, cree una nueva suscripción de pago con un inquilino de Azure AD distinto y un número reducido de licencias.

Registre estos valores:
  
- Office 365 nombre del administrador global: ![Línea](../media/Common-Images/TableLine.png). onmicrosoft.com (del paso 6 de la fase 1)
    
    Guarde también la contraseña de esta cuenta en una ubicación segura.
    
- Nombre de la organización de la suscripción de prueba: ![Línea](../media/Common-Images/TableLine.png) (en el paso 4 de la fase 1)
    
- Para mostrar las cuentas de los usuarios 2, 3, 4 y 5, ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell.
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Anote aquí los nombres de las cuentas:
    
  - Nombre de la cuenta de usuario 2: usuario2 @![Línea](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nombre de la cuenta de usuario 3: usuario3 @![Línea](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nombre de la cuenta de usuario 4: usuario4 @![Línea](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nombre de la cuenta de usuario 5: usuario5 @![Línea](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    También puede guardar la contraseña común de estas cuentas en un lugar seguro.
   

### <a name="using-an-office-365-test-environment"></a>Usar un entorno de prueba de Office 365

Si todo lo que necesita es un entorno de prueba de Office 365, puede detenerse aquí. 

Consulte las [Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para ver otras guías del laboratorio de pruebas que se aplican a Office 365 y Microsoft 365.
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: agregar una suscripción de prueba a Microsoft 365 E5

En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.
  
Primero, agregue la suscripción de prueba de Microsoft 365 E5 y asigne la nueva licencia de Microsoft 365 a su cuenta de administrador global.
  
1. Con una instancia privada de un explorador de Internet, inicie sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.
    
2. En la página **Centro de administración de Microsoft 365**, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.
    
3. En la página **Servicios de compra**, haga clic en **Microsoft 365 E5 **y, después, haga clic en **Obtener la versión de prueba gratuita**.

4. En la página de la **Versión de prueba de Microsoft 365 E5**, elija entre recibir una llamada o un mensaje de texto, escriba el número de teléfono y haga clic en **Enviarme un mensaje de texto** o **Llamarme**. Realice la comprobación.

5. En la página **Confirmar pedido**, haga clic en **Probar ahora**.

6. En la página **Recibo del pedido**, haga clic en **Continuar**.

7. En el Centro de administración de Microsoft 365, haga clic en **Usuarios > Usuarios activos**.

8. En **Usuarios activos**, haga clic en su cuenta de administrador.

9. Seleccione **Licencias y aplicaciones**.

10. Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.

11. Haga clic en **Guardar cambios** y, después, cierre el panel de información de la cuenta de usuario.

Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).
  
> [!NOTE]
> La suscripción de prueba de Microsoft 365 E5 tiene una duración de 30 días. Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con un bajo número de licencias. 
  
Su entorno de desarrollo y prueba ahora tiene:
  
- Una suscripción de prueba de Microsoft 365 E5.
- Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.
    
Esta es la configuración resultante, que agrega Microsoft 365 E5, que incluye Office 365 y Enterprise Security + administración (EMS).
  
![Fase 3 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: crear un equipo con Windows 10 Enterprise

En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.
  
### <a name="physical-computer"></a>Equipo físico

Obtenga un equipo personal e instale Windows 10 Enterprise en él. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Máquina virtual

Cree una máquina virtual con el hipervisor que prefiera e instale Windows 10 Enterprise en ella. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Máquina virtual de Azure

Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Los siguientes conjuntos de comandos usan la versión más reciente de Azure PowerShell. Vea [Introducción a los cmdlets de Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estos conjuntos de comandos compilan una máquina virtual con Windows 10 Enterprise llamada WIN10 y toda la infraestructura necesaria, que incluye un grupo de recursos, una cuenta de almacenamiento y una red virtual. Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones para que se ajusten a la infraestructura implementada actualmente. 
  
En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.
  
Inicie sesión en su cuenta de Azure con el siguiente comando.
  
```powershell
Connect-AzAccount
```

Obtenga su nombre de suscripción mediante el comando siguiente.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Configure su suscripción de Azure. Cambie todo el contenido entrecomillado, incluidos los caracteres \< y >, por los nombres correctos.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Después, cree un nuevo grupo de recursos. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Cree el nuevo grupo de recursos con estos comandos. Reemplace todo el contenido entrecomillado, incluidos los caracteres \< y > , por los nombres correctos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Después, cree una red virtual y la máquina virtual WIN10 con estos comandos. Cuando se le pida, indique el nombre y contraseña de la cuenta de administrador local para WIN10 y guárdelos en un lugar seguro.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Fase 5: unir el equipo con Windows 10 a Azure AD

Después de crear la máquina física o virtual con Windows 10 Enterprise, inicie sesión con una cuenta de administrador local.
  
> [!NOTE]
> En el caso de una máquina virtual de Azure, conéctela siguiendo [estas instrucciones](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
  
Después, una el equipo WIN10 al espacio empresarial de Azure AD de la suscripción de Microsoft 365 E5.
  
1. En el escritorio del equipo WIN10, haga clic en **Inicio > Configuración > Cuentas > Obtener acceso a trabajo o escuela > Conectarse**.
    
2. En el cuadro de diálogo **Set up a work or school account** (Configurar una cuenta profesional o educativa), haga clic en **Join this device to Azure Active Directory** (Unir este dispositivo a Azure Active Directory).
    
3. En **Cuenta profesional o educativa**, escriba el nombre de la cuenta de administrador global de la suscripción de Microsoft 365 E5 y haga clic en **Siguiente**.
    
4. En **Escribir contraseña**, escriba la contraseña de la cuenta de administrador global y luego haga clic en **Iniciar sesión**.
    
5. Cuando se le pida que confirme que es su organización, haga clic en **Unir** y luego en **Listo**.
    
6. Cierre la ventana de configuración.
    
Después, instale Office 365 ProPlus en el equipo con Windows 10.
  
1. Abra el explorador Microsoft Edge e inicie sesión en el portal de Office con las credenciales de la cuenta de administrador global. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. En la pestaña **Inicio de Microsoft Office**, haga clic en **Instalar Office**.
    
3. Cuando se le pregunte qué hacer, haga clic en **Ejecutar** y luego en **Sí** para **Control de cuentas de usuario**.
    
4. Espere hasta que se complete la instalación de Office. Cuando vea **Ya está listo**, haga clic en **Cerrar** dos veces.
    
Este es el entorno resultante.

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Esto incluye el equipo WIN10 que tiene:

- Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.
- Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).
- Tiene instalado Office 365 ProPlus.
  
Ahora está preparado para experimentar con otras características de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Pasos siguientes

Explore estos conjuntos adicionales de guías de laboratorio de pruebas:
  
- [Identidad](m365-enterprise-test-lab-guides.md#identity)
- [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protección de la información](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
