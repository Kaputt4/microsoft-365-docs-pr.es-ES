---
title: Conectarse a Microsoft 365 con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conéctese a su espacio empresarial de Microsoft 365 mediante PowerShell para Microsoft 365 de forma que pueda realizar tareas desde el Centro de administración desde la línea de comandos.
ms.openlocfilehash: 0192ed18c1c99cd08008570ce4b97a558621761f
ms.sourcegitcommit: edc9d4dec92ca81cff39bbf9590f1cd3a75ec436
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68484355"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Conectarse a Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos. Para conectarse a PowerShell, solo tiene que instalar el software necesario y después conectarse a su organización de Microsoft 365.

Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:

- Azure Active Directory PowerShell para Graph, cuyos cmdlets incluyen *AzureAD* en su nombre
- Módulo Microsoft Azure Active Directory para Windows PowerShell, cuyos cmdlets incluyen *Msol* en su nombre

Actualmente, el Módulo Azure Active Directory PowerShell para Graph no reemplaza completamente la funcionalidad del Módulo Microsoft Azure AD para Windows PowerShell para la administración de usuarios, grupos y licencias. En algunos casos, deberá usar ambas versiones. Puede instalar ambas versiones de forma segura en el mismo equipo.

>[!Note]
>También puede conectarse con [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) desde el Centro de administración de Microsoft 365.
>


## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

>[!NOTE]
> El módulo de Azure Active Directory se va reemplazar por el SDK de PowerShell de Microsoft Graph. Puede usar el SDK de PowerShell de Microsoft Graph para acceder a todas las API de Microsoft Graph. Para más información, consulte [Introducción al SDK de PowerShell de Microsoft Graph](/powershell/microsoftgraph/get-started).

**Sistema operativo**

You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.

Puede usar las siguientes versiones de Windows:
    
  - Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1

>[!Note]
>Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- Para el PowerShell de Azure Active Directory para el módulo de Graph, debe usar PowerShell versión 5.1.

- For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.
       
>[!Note]
>These procedures are intended for users who are members of a Microsoft 365 admin role. For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Conéctese al módulo de PowerShell de Azure Active Directory para Graph

Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen *AzureAD* en su nombre de cmdlet. Puede instalar el módulo [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](/powershell/azure/install-az-ps).

Para los procedimientos que necesitan los nuevos cmdlets del Módulo Azure Active Directory PowerShell para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.

> [!Note]
> Para información sobre la compatibilidad con diferentes versiones de Windows, vea [Módulo Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) .

### <a name="step-1-install-the-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios solo una vez en el equipo. Pero es probable que tenga que actualizar el software periódicamente.
  
1. Abra una ventana del símbolo del sistema Windows PowerShell.
    
2. Ejecute este comando:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**. La primera vez que use PSGallery, verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a todo** para continuar con la instalación.

3.  Ejecute este comando para importar el módulo:
    
    ```powershell
    Import-Module  AzureAD
    ```
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)

| Nube de Office 365 | Comando |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-AzureAD` |
| Office 365 ofrecido por 21Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

En el cuadro de diálogo **Inicie sesión en su cuenta**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar**.

Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.

Después de conectarse, puede usar los cmdlets para el [Módulo Azure Active Directory PowerShell para Graph](/powershell/module/azuread).

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Conectar con el Módulo Microsoft Azure Active Directory para Windows PowerShell

>[!Note]
>Los cmdlets del Módulo Microsoft Azure Active Directory para Windows PowerShell tienen *Msol* en su nombre.

La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlets que llevan *Msol* en su nombre. Para PowerShell versión 7 y posteriores, debe usar el SDK de PowerShell de Microsoft Graph.

PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name. Run these cmdlets from Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios solo una vez en el equipo. Pero es probable que tenga que actualizar el software periódicamente.
  
1.  Si no ejecuta Windows 10, instale la versión de 32 bits del asistente para inicio de sesión de Microsoft Online Services - Ayudante para el inicio de sesión: [Microsoft Online Services - Ayudante para el inicio de sesión para profesionales de TI RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).
    
2. Siga estos pasos para instalar el Módulo Microsoft Azure Active Directory para Windows PowerShell:
    
   1. Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
   1.  Ejecute el comando **Install-Module MSOnline**.
   1. Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione Entrar.
   1. Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione Entrar.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)

| Nube de Office 365 | Comando |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-MsolService` |
| Office 365 ofrecido por 21Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

En el cuadro de diálogo **Inicie sesión en su cuenta**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar**.

Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.

### <a name="how-do-you-know-it-worked"></a>¿Cómo sabrá que funcionó?

Si no recibe un mensaje de error, se ha conectado correctamente. Para realizar una prueba rápida, ejecute un cmdlet de Microsoft 365, como  **Get-MsolUser** y vea los resultados.
  
Si recibe un mensaje de error, compruebe los siguientes problemas:
  
- **A common problem is an incorrect password**. Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.
    
- **The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*). But backward compatibility with older versions of the .NET Framework can be enabled or disabled. For more information, see the following articles:
    
  - Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](/dotnet/framework/install/dotnet-35-windows-10)

  
- **Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.** To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Si el número de versión devuelto es menor que *1.0.8070.2*, desinstale el Módulo Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el [Paso 1](#step-1-install-the-required-software) descrito anteriormente.

- **Si recibe un mensaje de error de conexión**, consulte el [Error "Connect-MsolService: se produjo una excepción de tipo"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).
    
- **Si recibe un mensaje de error "Obtener elemento: no se encontró la ruta de acceso"**, utilice este comando:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a>Conexión con Azure Cloud Shell

To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar. In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.

Necesitará una suscripción de Azure activa para su organización que esté vinculada a su suscripción de Microsoft 365. Si aún no tiene una, puede crearla. Una vez que tenga una suscripción de Azure, se abrirá una ventana de PowerShell desde la que ejecutar comandos y scripts de PowerShell.

Para obtener más información, consulte [Azure Cloud Shell](/azure/cloud-shell/overview).



## <a name="see-also"></a>Consulte también

- [Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
