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
description: Use esta guía del laboratorio de pruebas para crear un entorno de prueba ligero para probar Microsoft 365 para empresas.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487393"
---
# <a name="the-lightweight-base-configuration"></a>Configuración básica ligera

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

En este artículo se describe cómo crear un entorno simplificado con una suscripción a Microsoft 365 E5 y un equipo con Windows 10 Enterprise.

![El entorno de pruebas ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

La creación de un entorno de prueba ligero implica cinco fases:
- [Fase 1: crear la suscripción a Microsoft 365 E5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: configurar la suscripción de prueba de Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: agregar una suscripción de prueba a Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: crear un equipo con Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: unir el equipo con Windows 10 a Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Use el entorno resultante para probar las características y funciones de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía de laboratorio de pruebas de Microsoft 365 para empresas, vea la pila de la [Guía de entorno de pruebas 365 para empresas de Microsoft](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365. Puede extender fácilmente la suscripción de prueba otros 30 días. Para un entorno de pruebas permanente, cree una nueva suscripción de pago con un inquilino de Azure AD distinto y un número reducido de licencias.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: crear la suscripción a Microsoft 365 E5

Empezamos con una suscripción de prueba de Microsoft 365 E5 y, a continuación, agregamos la suscripción a Microsoft 365 E5 a ella.

>[!NOTE]
>Le recomendamos que cree una suscripción de prueba de Office 365 para que el entorno de prueba tenga un inquilino de Azure AD independiente de las suscripciones pagadas actualmente. Esta separación significa que puede Agregar y quitar usuarios y grupos en el inquilino de prueba sin que ello afecte a las suscripciones de producción.

Para iniciar la suscripción de prueba de Microsoft 365 E5, en primer lugar necesita un nombre de compañía ficticio y una nueva cuenta de Microsoft.
  
1. Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia: ![Línea](../media/Common-Images/TableLine.png)
    
2. Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.
    
    - Anote aquí el nombre y los apellidos de la nueva cuenta: ![Línea](../media/Common-Images/TableLine.png)
    
    - Anote la dirección de la cuenta de correo electrónico nueva aquí: ![Línea](../media/Common-Images/TableLine.png)Outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrarse para una suscripción de prueba de Office 365 E5

1. En el explorador, vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. En el paso 1 de la página **gracias por elegir Office 365 E5** , escriba la dirección de la nueva cuenta de correo electrónico.
3. En el paso 2 del proceso de suscripción del rastro, escriba la información solicitada y, a continuación, realice la comprobación.
4. En el paso 3, escriba un nombre de organización y, a continuación, un nombre de cuenta que será el administrador global de la suscripción.
5. En el paso 4, registre la página de inicio de sesión aquí (seleccionar y copiar):  ![Línea](../media/Common-Images/TableLine.png)
6. Registre aquí el identificador de usuario: ![Linea](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Anote la contraseña que escribió en una ubicación segura.
   Este valor se denominará **nombre de administrador global**.
7. Seleccione **ir a la instalación**.
8. En el programa de instalación de Office 365 E5, seleccione **continuar usando *su organización*. onmicrosoft.com para el correo electrónico y el inicio de sesión**y, a continuación, seleccione **salir y continuar más tarde**.

Debería ver el Centro de administración de Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurar la suscripción de prueba de Office 365

En esta fase, se configura la suscripción con usuarios adicionales y se les asignan licencias de Office 365 E5.
  
Para conectarse a su suscripción con el módulo Azure Active Directory PowerShell para Graph desde su equipo, siga las instrucciones [que se indican en conectarse a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
    
En el cuadro de diálogo **solicitud de credenciales para Windows PowerShell** , escriba el nombre del administrador global (por ejemplo, *jdoe@contosotoycompany.onmicrosoft.com*) y la contraseña.
  
Rellene el nombre de la organización (por ejemplo, *contosotoycompany*), el código de país de dos caracteres de su ubicación, una contraseña de cuenta común y, a continuación, ejecute los siguientes comandos desde el símbolo del sistema de PowerShell:

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

Si todavía no ha registrado estos valores, grabe ahora:
  
- Nombre de administrador global: ![Línea](../media/Common-Images/TableLine.png). onmicrosoft.com (del paso 6 de la fase 1)
    
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

Si solo necesita un entorno de prueba de Office 365, no es necesario leer el resto de este artículo.

Para ver guías de laboratorio de pruebas adicionales que se aplican tanto a Office 365 como a Microsoft 365, consulte las [guías del laboratorio de pruebas de microsoft 365 para empresas](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: agregar una suscripción de prueba a Microsoft 365 E5

En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.
  
Primero, agregue la suscripción de prueba de Microsoft 365 E5 y asigne la nueva licencia de Microsoft 365 a su cuenta de administrador global.
  
1. En una ventana privada de explorador de Internet, use las credenciales de la cuenta de administrador global para iniciar sesión en el centro de administración de 365 de Microsoft en [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. En la página del **centro de administración de 365 de Microsoft** , en el panel de navegación de la izquierda, seleccione **facturación > los servicios de compra**.
    
3. En la página **servicios de compra** , seleccione **Microsoft 365 E5**y, después, haga clic en **obtener prueba gratuita**.

4. En la página de **prueba de Microsoft 365 E5** , decida si desea recibir un mensaje de texto o una llamada telefónica, escriba su número de teléfono y, después, seleccione **texto me** o **llámeme**. Realice la comprobación.

5. En la página **confirmar el pedido** , seleccione **probar ahora**.

6. En la página **recibo del pedido** , seleccione **continuar**.

7. En el centro de administración de Microsoft 365, seleccione **usuarios > usuarios activos**.

8. En **usuarios activos**, seleccione su cuenta de administrador.

9. Seleccione **licencias y aplicaciones**.

10. Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.

11. Seleccione **Guardar cambios**y, a continuación, cierre el panel de información de la cuenta de usuario.

Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).
  
> [!NOTE]
> La longitud de la suscripción de prueba de Microsoft 365 E5 es de 30 días. Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con un bajo número de licencias.
  
Su entorno de desarrollo y prueba ahora tiene:
  
- Una suscripción de prueba de Microsoft 365 E5.
- Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.
    
La configuración resultante, que agrega Microsoft 365 E5, tiene el siguiente aspecto:
  
![Fase 3 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: crear un equipo con Windows 10 Enterprise

En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.
  
### <a name="physical-computer"></a>Equipo físico

En un equipo personal, instale Windows 10 Enterprise. Puede descargar la versión de prueba de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Máquina virtual

Use el hipervisor que prefiera para crear una máquina virtual y, a continuación, instale Windows 10 Enterprise en ella. Puede descargar la versión de prueba de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Máquina virtual de Azure

Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estos conjuntos de comandos compilan una máquina virtual de Windows 10 Enterprise denominada WIN10 y toda la infraestructura necesaria, incluido un grupo de recursos, una cuenta de almacenamiento y una red virtual. Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones para que se ajusten a la infraestructura implementada actualmente.
  
En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.
  
Inicie sesión en su cuenta de Azure con este comando.
  
```powershell
Connect-AzAccount
```

Obtenga el nombre de la suscripción con este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Configure su suscripción de Azure. Reemplace todo lo que haya entre comillas, incluidos los \< and > caracteres, por el nombre correcto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Después, cree un nuevo grupo de recursos. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Cree el nuevo grupo de recursos con estos comandos. Reemplace todo lo que haya entre comillas, incluidos los \< and > caracteres, por los nombres correctos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

A continuación, cree una nueva red virtual y la máquina virtual de WIN10 con estos comandos. Cuando se le solicite, proporcione el nombre y la contraseña de la cuenta de administrador local para WIN10 y almacénelo en una ubicación segura.
  
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
  
1. En el escritorio del equipo WIN10, seleccione **iniciar > configuración > cuentas > tener acceso a trabajo o escuela > conectar**.
    
2. En el cuadro de diálogo **configurar una cuenta de trabajo o escuela** , seleccione **unirse a este dispositivo a Azure Active Directory**.
    
3. En **cuenta profesional o educativa**, escriba el nombre de la cuenta de administrador global de la suscripción a Microsoft 365 E5 y, a continuación, seleccione **siguiente**.
    
4. En **escribir contraseña**, escriba la contraseña de la cuenta de administrador global y, a continuación, seleccione **iniciar sesión**.
    
5. Cuando se le pida que se asegure de que esta es su organización, seleccione **unirse**y, después, haga clic en **listo**.
    
6. Cierre la ventana de configuración.
    
A continuación, instale Microsoft 365 apps for Enterprise en el equipo WIN10:
  
1. Abra el explorador Microsoft Edge e inicie sesión en el [centro de administración de microsoft 365](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.
    
2. En la pestaña **Página principal de Microsoft Office** , seleccione **instalar Office**.
    
3. Cuando se le pregunte qué hacer, seleccione **Ejecutar**y, a continuación, haga clic en **sí** para **control de cuentas de usuario**.
    
4. Espere a que Office complete su instalación. Cuando vea ya **está todo establecido**., seleccione **cerrar** dos veces.
    
El entorno resultante tiene el siguiente aspecto:

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Esto incluye el equipo WIN10 que tiene:

- Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.
- Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).
- Microsoft 365 apps for Enterprise instalado.
  
Ya está listo para experimentar con características adicionales de [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Pasos siguientes

Explore estos conjuntos adicionales de guías de laboratorio de pruebas:
  
- [Identidad](m365-enterprise-test-lab-guides.md#identity)
- [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protección de la información](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
