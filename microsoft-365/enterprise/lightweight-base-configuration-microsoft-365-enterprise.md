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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use esta Guía del entorno de pruebas para crear un entorno de prueba ligero para probar Microsoft 365 para empresas.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487393"
---
# <a name="the-lightweight-base-configuration"></a>Configuración básica ligera

*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*

En este artículo se describe cómo crear un entorno simplificado con una suscripción a Microsoft 365 E5 y un equipo que ejecute Windows 10 Enterprise.

![El entorno de pruebas ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

La creación de un entorno de prueba ligero consta de cinco fases:
- [Fase 1: Crear la suscripción a Microsoft 365 E5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: configurar la suscripción de prueba de Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: agregar una suscripción de prueba a Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: crear un equipo con Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: unir el equipo con Windows 10 a Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Use el entorno resultante para probar las características y la funcionalidad [de Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vea La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

>[!NOTE]
>Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365. Puede extender fácilmente la suscripción de prueba otros 30 días. Para un entorno de pruebas permanente, cree una nueva suscripción de pago con un inquilino de Azure AD distinto y un número reducido de licencias.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: Crear la suscripción a Microsoft 365 E5

Empezamos con una suscripción de prueba de Microsoft 365 E5 y, a continuación, le agregamos la suscripción de Microsoft 365 E5.

>[!NOTE]
>Le recomendamos que cree una suscripción de prueba de Office 365 para que el entorno de prueba tenga un inquilino de Azure AD independiente de las suscripciones de pago que tenga actualmente. Esta separación significa que puede agregar y quitar usuarios y grupos en el inquilino de prueba sin que ello afecte a las suscripciones de producción.

Para iniciar la suscripción de prueba de Microsoft 365 E5, en primer lugar necesita un nombre de compañía ficticio y una nueva cuenta de Microsoft.
  
1. Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia: ![Línea](../media/Common-Images/TableLine.png)
    
2. Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.
    
    - Anote aquí el nombre y los apellidos de la nueva cuenta: ![Línea](../media/Common-Images/TableLine.png)
    
    - Anote la dirección de la cuenta de correo electrónico nueva aquí: ![Línea](../media/Common-Images/TableLine.png)Outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrarse para una suscripción de prueba de Office 365 E5

1. En el explorador, vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. En el paso 1 de la página Gracias por **elegir Office 365 E5,** escriba su nueva dirección de cuenta de correo electrónico.
3. En el paso 2 del proceso de suscripción de prueba, escriba la información solicitada y, a continuación, realice la comprobación.
4. En el paso 3, escriba un nombre de organización y, a continuación, un nombre de cuenta que será el administrador global de la suscripción.
5. En el paso 4, registre la página de inicio de sesión aquí (seleccionar y copiar):  ![Línea](../media/Common-Images/TableLine.png)
6. Registre aquí el identificador de usuario: ![Linea](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Registre la contraseña que escribió en una ubicación segura.
   Este valor se denominará **nombre de administrador global**.
7. Seleccione **Ir a Instalación.**
8. In Office 365 E5 Setup, select **Continue using your *organization*.onmicrosoft.com for email and signing in**, and then select Exit and continue **later**.

Debería ver el Centro de administración de Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurar la suscripción de prueba de Office 365

En esta fase, se configura la suscripción con usuarios adicionales y se les asignan licencias de Office 365 E5.
  
Para conectarse a su suscripción con el módulo de Azure Active Directory PowerShell para Graph desde el equipo, siga las instrucciones de Conectarse a [Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
    
En el **Windows PowerShell de diálogo Solicitud** de credenciales, escriba el nombre del administrador global (por ejemplo, *jdoe@contosotoycompany.onmicrosoft.com)* y la contraseña.
  
Rellene el nombre de la organización (por ejemplo, *contosotoycompany),* el código de país de dos caracteres para su ubicación, una contraseña de cuenta común y, a continuación, ejecute los siguientes comandos desde el símbolo del sistema de PowerShell:

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

Si aún no ha registrado estos valores, indómelos ahora:
  
- Nombre del administrador global: ![Línea](../media/Common-Images/TableLine.png). onmicrosoft.com (del paso 6 de la fase 1)
    
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

Si solo necesita un entorno de prueba de Office 365, no es necesario que lea el resto de este artículo.

Para obtener guías adicionales del entorno de pruebas que se aplican a Office 365 y Microsoft 365, consulte Guías del entorno de pruebas de [Microsoft 365 para empresas.](m365-enterprise-test-lab-guides.md)
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: agregar una suscripción de prueba a Microsoft 365 E5

En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.
  
Primero, agregue la suscripción de prueba de Microsoft 365 E5 y asigne la nueva licencia de Microsoft 365 a su cuenta de administrador global.
  
1. En una ventana privada de explorador de Internet, use sus credenciales de cuenta de administrador global para iniciar sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. En la página centro de administración de **Microsoft 365,** en el panel de navegación izquierdo, seleccione **Facturación > servicios de compra.**
    
3. En la **página Servicios de** compra, seleccione Microsoft **365 E5** y, a continuación, **obtenga la versión de prueba gratuita.**

4. On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**. Realice la comprobación.

5. En la **página Confirmar pedido,** seleccione **Probar ahora.**

6. En la **página Recibo del** pedido, seleccione **Continuar**.

7. En el Centro de administración de Microsoft 365, seleccione **Usuarios > usuarios activos.**

8. En **Usuarios activos,** seleccione su cuenta de administrador.

9. Seleccione **Licencias y aplicaciones.**

10. Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.

11. Seleccione **Guardar cambios y,** a continuación, cierre el panel de información de la cuenta de usuario.

Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).
  
> [!NOTE]
> La duración de la suscripción de prueba de Microsoft 365 E5 es de 30 días. Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con un bajo número de licencias.
  
Su entorno de desarrollo y prueba ahora tiene:
  
- Una suscripción de prueba de Microsoft 365 E5.
- Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.
    
La configuración resultante, que agrega Microsoft 365 E5, tiene este aspecto:
  
![Fase 3 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: crear un equipo con Windows 10 Enterprise

En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.
  
### <a name="physical-computer"></a>Equipo físico

En un equipo personal, instala Windows 10 Enterprise. Puedes descargar la versión de prueba de Windows 10 Enterprise [aquí.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine"></a>Máquina virtual

Usa el hipervisor que prefieras para crear una máquina virtual y, a continuación, instala Windows 10 Enterprise en ella. Puedes descargar la versión de prueba de Windows 10 Enterprise [aquí.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine-in-azure"></a>Máquina virtual de Azure

Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estos conjuntos de comandos crean una máquina virtual de Windows 10 Enterprise denominada WIN10 y toda su infraestructura necesaria, incluido un grupo de recursos, una cuenta de almacenamiento y una red virtual. Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones a la infraestructura implementada actualmente.
  
En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.
  
Inicie sesión en su cuenta de Azure con este comando.
  
```powershell
Connect-AzAccount
```

Obtenga el nombre de la suscripción con este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Configure su suscripción de Azure. Reemplace todo el texto entre comillas, \< and > incluidos los caracteres, por el nombre correcto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Después, cree un nuevo grupo de recursos. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Cree el nuevo grupo de recursos con estos comandos. Reemplace todo el texto entre comillas, \< and > incluidos los caracteres, por los nombres correctos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

A continuación, cree una nueva red virtual y la máquina virtual WIN10 con estos comandos. Cuando se le solicite, proporcione el nombre y la contraseña de la cuenta de administrador local para WIN10 y guárdalo en una ubicación segura.
  
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
> Para una máquina virtual en Azure, siga  [estas instrucciones](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) para conectarse a ella.
  
Después, una el equipo WIN10 al espacio empresarial de Azure AD de la suscripción de Microsoft 365 E5.
  
1. En el escritorio del equipo WIN10, seleccione Inicio > Configuración > Cuentas > Obtener acceso al trabajo o escuela **> Conectarse.**
    
2. En el **cuadro de diálogo Configurar una cuenta** de trabajo o escuela, seleccione Unir este dispositivo a Azure Active **Directory.**
    
3. En **la cuenta de** trabajo o escuela, escriba el nombre de la cuenta de administrador global de su suscripción a Microsoft 365 E5 y, a continuación, seleccione **Siguiente**.
    
4. In **Enter password**, enter the password for your global administrator account, and then select Sign **in**.
    
5. Cuando se le pida que se asegúrese de que se trata de su organización, seleccione **Unirse** y, a continuación, seleccione **Listo.**
    
6. Cierre la ventana de configuración.
    
A continuación, instale Aplicaciones de Microsoft 365 para empresas en el equipo WIN10:
  
1. Abra el explorador Microsoft Edge e inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.
    
2. En la **Microsoft Office inicio,** seleccione **Instalar Office**.
    
3. Cuando se le pida qué hacer, seleccione **Ejecutar** y, a continuación, seleccione **Sí para** control de cuentas **de usuario.**
    
4. Espere a que Office complete su instalación. Cuando **veas que todo está configurado,** selecciona **Cerrar dos** veces.
    
El entorno resultante tiene este aspecto:

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Esto incluye el equipo WIN10 que tiene:

- Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.
- Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).
- Aplicaciones de Microsoft 365 para empresas instaladas.
  
Ya está listo para experimentar con características adicionales de [Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Pasos siguientes

Explore estos conjuntos adicionales de guías de laboratorio de pruebas:
  
- [Identidad](m365-enterprise-test-lab-guides.md#identity)
- [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protección de la información](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
