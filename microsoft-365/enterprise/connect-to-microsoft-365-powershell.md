---
title: Conectarse a Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conéctese a su espacio empresarial de Microsoft 365 mediante PowerShell para Microsoft 365 de forma que pueda realizar tareas desde el Centro de administración desde la línea de comandos.
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782806"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Conectarse a Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos. Para conectarse a PowerShell, solo tiene que instalar el software necesario y después conectarse a su organización de Microsoft 365.

Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:

- Azure Active Directory PowerShell para Graph, cuyos cmdlets incluyen *AzureAD* en su nombre
- Módulo Microsoft Azure Active Directory para Windows PowerShell, cuyos cmdlets incluyen *Msol* en su nombre

Actualmente, el Módulo Azure Active Directory PowerShell para Graph no reemplaza completamente la funcionalidad del Módulo Microsoft Azure AD para Windows PowerShell para la administración de usuarios, grupos y licencias. En algunos casos, deberá usar ambas versiones. Puede instalar ambas versiones de forma segura en el mismo equipo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?


**Sistema operativo**

Use una versión de 64 bits de Windows. La compatibilidad con la versión de 32 bits de Módulo Microsoft Azure Active Directory para Windows PowerShell se descontinuó en 2014.

Puede usar las siguientes versiones de Windows:
    
  - Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1

>[!Note]
>Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- Para el Módulo Azure Active Directory PowerShell para Graph, debe usar la versión 5.1 o posterior de PowerShell.

- Para el Módulo Microsoft Azure Active Directory para Windows PowerShell, debe usar la versión 5.1 o posterior de PowerShell, hasta la versión 6 de PowerShell. No puede usar la versión 7 de PowerShell.
       
>[!Note]
>Estos procedimientos están diseñados para los usuarios que sean miembros de un rol de administrador de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](../admin/add-users/about-admin-roles.md).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Conéctese al módulo de PowerShell de Azure Active Directory para Graph

Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen *AzureAD* en su nombre de cmdlet. Puede instalar el módulo [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](/powershell/azure/install-az-ps).

Para los procedimientos que necesitan los nuevos cmdlets del Módulo Azure Active Directory PowerShell para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.

> [!Note]
> Para información sobre la compatibilidad con diferentes versiones de Windows, vea [Módulo Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) .

### <a name="step-1-install-the-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios solo una vez en el equipo. Pero es probable que tenga que actualizar el software periódicamente.
  
1. Abra una ventana de símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
    
2. Ejecute este comando:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**. La primera vez que use PSGallery, verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a todo** para continuar con la instalación.


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).

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

La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlets que llevan *Msol* en su nombre. Para la versión 7 de PowerShell y versiones posteriores, debe usar el Módulo Azure Active Directory Powershell para Graph o Azure PowerShell.

PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre. Ejecute estos cmdlets desde Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios solo una vez en el equipo. Pero es probable que tenga que actualizar el software periódicamente.
  
1.  Si no ejecuta Windows 10, instale la versión de 64 bits del asistente para inicio de sesión de Microsoft Online Services: [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).
    
2. Siga estos pasos para instalar el Módulo Microsoft Azure Active Directory para Windows PowerShell:
    
   1. Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
   1.  Ejecute el comando **Install-Module MSOnline**.
   1. Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione Entrar.
   1. Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione Entrar.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor, ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).

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
  
- **Un problema habitual es una contraseña incorrecta**. Vuelva a ejecutar el [Paso 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) y preste atención al nombre de usuario y la contraseña que escriba.
    
- **El Módulo Microsoft Azure Active Directory para Windows PowerShell necesita que Microsoft .NET Framework 3.5.* x* esté habilitado en el equipo**. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5.* x*). Pero la compatibilidad con versiones anteriores de .NET Framework se puede habilitar o deshabilitar. Para más información, consulte los siguientes artículos:
    
  - Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](/dotnet/framework/install/dotnet-35-windows-10)

  
- **Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.** Para comprobarlo, ejecute el siguiente comando en PowerShell para Microsoft 365 o el Módulo de Microsoft Azure Active Directory para Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Si el número de versión devuelto es menor que *1.0.8070.2*, desinstale el Módulo Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el [Paso 1](#step-1-install-the-required-software) descrito anteriormente.

- **Si recibe un mensaje de error de conexión**, consulte el [Error "Connect-MsolService: se produjo una excepción de tipo"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).
    
- **Si recibe un mensaje de error "Obtener elemento: no se encontró la ruta de acceso"**, utilice este comando:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>Consulte también

- [Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
