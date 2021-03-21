---
title: Preparar un dominio no enrutable para la sincronización de directorios
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Obtenga información sobre qué hacer si tiene un dominio no enrutable asociado a sus cuentas de usuario locales antes de sincronizarlas con su inquilino de Microsoft 365.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927401"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Preparar un dominio no enrutable para la sincronización de directorios

Al sincronizar el directorio local con Microsoft 365, debe tener un dominio comprobado en Azure Active Directory (Azure AD). Solo se sincronizan los nombres de entidad de seguridad de usuario (UPN) asociados con el dominio local de Servicios de dominio de Active Directory (AD DS). Sin embargo, cualquier UPN que contenga un dominio no enrutable, como ".local" (ejemplo: billa@contoso.local), se sincronizará con un dominio .onmicrosoft.com (ejemplo: billa@contoso.onmicrosoft.com). 

Si actualmente usa un dominio ".local" para sus cuentas de usuario en AD DS, se recomienda cambiarlas para usar un dominio comprobado, como billa@contoso.com, para sincronizarse correctamente con su dominio de Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>¿Qué sucede si solo tengo un dominio local ".local"?

Usa Azure AD Connect para sincronizar su AD DS con el inquilino de Azure AD de su inquilino de Microsoft 365. Para obtener más información, vea [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).
  
Azure AD Connect sincroniza el UPN y la contraseña de los usuarios para que los usuarios puedan iniciar sesión con las mismas credenciales que usan localmente. Sin embargo, Azure AD Connect solo sincroniza los usuarios con los dominios comprobados por Microsoft 365. Esto significa que Azure AD también comprueba el dominio porque las identidades de Microsoft 365 están administradas por Azure AD. En otras palabras, el dominio debe ser un dominio de Internet válido (por ejemplo, .com, .org, .net, .us). Si su AD DS interno solo usa un dominio no enrutable (por ejemplo, ".local"), esto no puede coincidir con el dominio comprobado que tiene para su inquilino de Microsoft 365. Puedes solucionar este problema cambiando el dominio principal en tu AD DS local o agregando uno o varios sufijos UPN.
  
### <a name="change-your-primary-domain"></a>Cambiar el dominio principal

Cambie el dominio principal a un dominio que haya comprobado en Microsoft 365, por ejemplo, contoso.com. A continuación, todos los usuarios que tienen el dominio contoso.local se actualizan a contoso.com. Sin embargo, este es un proceso muy implicado y se describe una solución más sencilla en la siguiente sección.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Agregar sufijos UPN y actualizar los usuarios a ellos

Puedes solucionar el problema ".local" registrando sufijos o sufijos UPN nuevos en AD DS para que coincidan con el dominio (o dominios) que has comprobado en Microsoft 365. Después de registrar el nuevo sufijo, actualiza los UPN de usuario para reemplazar el ".local" por el nuevo nombre de dominio, por ejemplo, para que una cuenta de usuario parezca billa@contoso.com.
  
Después de actualizar los UPN para usar el dominio comprobado, estás listo para sincronizar tu AD DS local con Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Paso 1: Agregar el nuevo sufijo UPN**
  
1. En el controlador de dominio de AD DS, en el Administrador de servidores elija **Herramientas** \> **Dominios y confianzas de Active Directory**.
    
    **O bien, si no tienes Windows Server 2012**
    
    Presione **la tecla Windows + R** para abrir el cuadro de diálogo Ejecutar y, a continuación, escriba Domain.msc y, a continuación, elija **Aceptar**. 
    
    ![Elija Dominios y confianzas de Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. En la **ventana Dominios y confianzas** de Active Directory, haga clic con el botón secundario en Dominios y **confianzas** de Active Directory y, a continuación, **elija Propiedades**.
    
    ![Haga clic con el botón secundario en Dominios y confianzas de Active Directory y elija Propiedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. En la pestaña Sufijos **UPN,** en el cuadro Sufijos **UPN** alternativos, escriba el sufijo o sufijos UPN nuevo y, a continuación, **elija** \> **Agregar aplicar**.
    
    ![Agregar un sufijo UPN nuevo](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Elija **Aceptar** cuando haya terminado de agregar sufijos. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Paso 2: Cambiar el sufijo UPN para los usuarios existentes
  
1. En el controlador de dominio de AD DS, en el Administrador del servidor elija **Herramientas** \> **Usuarios y equipos de Active Directory**.
    
    **O bien, si no tienes Windows Server 2012**
    
    Presione **la tecla Windows + R** para abrir el cuadro **de** diálogo Ejecutar y, a continuación, escriba Dsa.msc y, a continuación, haga clic en **Aceptar.**
    
2. Seleccione un usuario, haga clic con el botón secundario y, a continuación, elija **Propiedades**.
    
3. En la **pestaña** Cuenta, en la lista desplegable Sufijo UPN, elija el nuevo sufijo UPN y, a continuación, **elija Aceptar**.
    
    ![Agregar nuevo sufijo UPN para un usuario](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Complete estos pasos para cada usuario.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Usar PowerShell para cambiar el sufijo UPN para todos los usuarios

Si tiene muchas cuentas de usuario que actualizar, es más fácil usar PowerShell. En el ejemplo siguiente se usan los cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) y [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) para cambiar todos los sufijos contoso.local a contoso.com en AD DS. 

Por ejemplo, puede ejecutar los siguientes comandos de PowerShell para actualizar todos los sufijos contoso.local a contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Consulta [Módulo de Windows PowerShell Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) para obtener más información sobre cómo usar Windows PowerShell en AD DS.