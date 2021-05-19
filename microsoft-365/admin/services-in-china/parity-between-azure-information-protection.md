---
title: Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Obtenga más información sobre Azure Information Protection (AIP) para Office 365 operado por 21Vianet y cómo configurarlo para clientes en China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535847"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet

En este artículo se tratan las diferencias entre la compatibilidad con Azure Information Protection (AIP) para Office 365 operado por 21Vianet y las ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China, incluido cómo instalar el escáner local de AIP y administrar trabajos de examen de &mdash; contenido.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferencias entre AIP para Office 365 operado por 21Vianet y ofertas comerciales

Aunque nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a los clientes de China con nuestra oferta de AIP para Office 365 operado por 21Vianet, nos gustaría destacar algunas funciones que nos gustaría destacar.

La siguiente lista incluye las diferencias existentes entre AIP para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:

- Information Rights Management (IRM) solo se admite Aplicaciones Microsoft 365 para empresas (compilación 11731.10000 o posterior). Office 2010, Office 2013 y otras versiones Office 2016 no son compatibles.

- La migración Active Directory Rights Management Services (AD RMS) a AIP no está disponible actualmente.
  
- Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.
  
- El uso compartido de documentos y datos adjuntos de correo electrónico con usuarios en la nube comercial no está disponible actualmente. Esto incluye Office 365 operado por 21 usuarios deVianet en la nube comercial, no Office 365 operado por 21 usuarios deVianet en la nube comercial y usuarios con una licencia rms para individuos.
  
- IRM con SharePoint (bibliotecas y sitios protegidos por IRM) actualmente no está disponible.
  
- La extensión de dispositivo móvil para AD RMS no está disponible actualmente.

- [El Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.

- El área AIP de Azure Portal no está disponible para los clientes en China. Use [comandos de PowerShell en](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) lugar de realizar acciones en el portal, como administrar y ejecutar los trabajos de examen de contenido.

## <a name="configure-aip-for-customers-in-china"></a>Configurar AIP para clientes en China

Para configurar AIP para clientes en China:
1. [Habilitar Rights Management para el inquilino](#step-1-enable-rights-management-for-the-tenant).

1. [Agregue la entidad de servicio de sincronización de Microsoft Information Protection](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).

1. [Configurar el cifrado DNS](#step-3-configure-dns-encryption).

1. [Instalar y configurar el cliente de etiquetado unificado AIP](#step-4-install-and-configure-the-aip-unified-labeling-client).

1. [Configurar aplicaciones AIP en Windows](#step-5-configure-aip-apps-on-windows).

1. [Instale el escáner local de AIP y administre trabajos de análisis de contenido.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Paso 1: Habilitar Rights Management para el inquilino

Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.

1. Compruebe si RMS está habilitado:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Importe el módulo mediante `Import-Module AipService` .
    4. Conectar al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    5. Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .

2. Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Paso 2: Agregar la entidad de servicio de sincronización de Microsoft Information Protection

La **entidad de servicio del** servicio de sincronización de Microsoft Information Protection no está disponible en los inquilinos de Azure China de forma predeterminada y es necesaria para Azure Information Protection.

1. Cree esta entidad de servicio manualmente con el cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) y el identificador de aplicación del servicio de sincronización `870c4f2e-85b6-4d43-bdda-6ed9a579b725` de Microsoft Information Protection. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Después de agregar la entidad de servicio, agregue los permisos pertinentes necesarios al servicio.

### <a name="step-3-configure-dns-encryption"></a>Paso 3: Configurar el cifrado DNS

Para que el cifrado funcione correctamente, Office aplicaciones cliente deben conectarse a la instancia china del servicio y arrancar desde allí. Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador del espacio empresarial debe configurar un registro SRV dns con información sobre la dirección URL de Azure RMS. Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y producirá un error.

Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, ), y no con el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ). El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.

#### <a name="configure-dns-encryption---windows"></a>Configurar el cifrado DNS: Windows

1. Obtener el id. de RMS:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Conectar al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    4. Ejecute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.

2. Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.

    - Service = `_rmsredir`
    - Protocolo = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)
    - Priority, Weight, Seconds, TTL = default values

3. Asocie el dominio personalizado con el inquilino en [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración de DNS.

4. Inicie sesión en el Microsoft 365 de administración con las credenciales de administración global correspondientes y agregue el dominio (por ejemplo, `contoso.cn` ) para la creación de usuarios. En el proceso de comprobación, es posible que se necesiten cambios dns adicionales. Una vez que se realiza la comprobación, se pueden crear usuarios.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurar el cifrado DNS: Mac, iOS, Android

Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.

- Service = `_rmsdisco`
- Protocolo = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Priority, Weight, Seconds, TTL = default values


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Paso 4: Instalar y configurar el cliente de etiquetado unificado AIP

Descargue e instale el cliente de etiquetado unificado AIP desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

Para más información vea:

- [Documentación de AIP](/azure/information-protection/)
- [Historial de versiones de AIP y directiva de soporte técnico](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos del sistema AIP](/azure/information-protection/requirements)
- [Inicio rápido de AIP: implementar el cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guía de administrador de AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guía del usuario de AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Obtenga información sobre Microsoft 365 etiquetas de confidencialidad](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Paso 5: Configurar aplicaciones AIP en Windows

Las aplicaciones AIP Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:

- Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Valor = `6` (valor predeterminado = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Asegúrese de que no elimina la clave del Registro después de una desinstalación. Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial). Si la clave está vacía o incorrecta, también se agrega un error de impresión al registro.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Paso 6: Instalar el escáner local de AIP y administrar trabajos de análisis de contenido

Instale el escáner local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales y aplicar etiquetas de clasificación y protección según lo configurado en la directiva de su organización.

Al configurar y administrar los trabajos de análisis de contenido, use el siguiente procedimiento en lugar de la interfaz de [Azure Portal](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) que usan las ofertas comerciales.

Para obtener más información, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y Administrar los trabajos de examen de contenido [solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).

**Para instalar y configurar el escáner:**

1. Inicie sesión en el Windows servidor que ejecutará el escáner. Use una cuenta que tenga derechos de administrador local y que tenga permisos para escribir en la SQL Server base de datos maestra.

1. Comience con PowerShell cerrado. Si ha instalado previamente el cliente y el escáner de AIP, asegúrese de que el servicio **AIPScanner** está detenido.

1. Abra una Windows PowerShell sesión con la **opción Ejecutar como administrador.**

1. Ejecute el cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) especificando la instancia de SQL Server en la que se va a crear una base de datos para el escáner de Azure Information Protection y un nombre significativo para el clúster de escáneres.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Puede usar el mismo nombre de clúster en el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para asociar varios nodos de escáner al mismo clúster. El uso del mismo clúster para varios nodos de escáner permite que varios escáneres funcionen juntos para realizar los exámenes.
    > 

1. Compruebe que el servicio ya está instalado mediante **servicios de herramientas**  >  **administrativas**.

    El servicio instalado se denomina **Azure Information Protection Scanner** y está configurado para ejecutarse mediante la cuenta de servicio de escáner que creó.

1. Obtenga un token de Azure para usarlo con el escáner. Un token de Azure AD permite que el escáner se autentique en el servicio de Azure Information Protection, lo que permite que el escáner se ejecute de forma no interactiva. 

    1. Abra Azure Portal y cree una aplicación de Azure AD para especificar un token de acceso para la autenticación. Para obtener más información, [vea How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).
    
        > [!TIP]
        > Al crear y configurar aplicaciones de Azure AD para el comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) el panel Solicitar permisos **de api** muestra las API que mi organización usa en lugar de la pestaña API de **Microsoft.**  Seleccione las **API que usa mi organización** para, a continuación, seleccionar Azure Rights Management **Servicios**. 
        >

    1. Desde el equipo Windows Server, si se ha concedido a su cuenta de servicio de escáner el derecho Iniciar sesión **localmente** para la instalación, inicie sesión con esta cuenta e inicie una sesión de PowerShell. 
    
        Si no se puede conceder a su cuenta de servicio de escáner el derecho De iniciar sesión **localmente** para la instalación, use el parámetro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), tal como se describe en [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

    1. Ejecute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), especificando los valores copiados desde la aplicación de Azure AD:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Por ejemplo:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    El escáner ahora tiene un token para autenticarse en Azure AD. Este token es válido durante un año, dos años o nunca, según la configuración del secreto de cliente de la aplicación **web /API** en Azure AD. Cuando expire el token, debe repetir este procedimiento.

1. Ejecute el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para establecer el escáner para que funcione en modo sin conexión. Ejecutar:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Ejecute el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para crear un trabajo de detección de contenido predeterminado.

    El único parámetro necesario en el cmdlet **Set-AIPScannerContentScanJob** es **Enforce**. Sin embargo, es posible que desee definir otras opciones de configuración para el trabajo de examen de contenido en este momento. Por ejemplo:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    La sintaxis anterior configura las siguientes opciones mientras continúa la configuración:

    - Mantiene la programación de ejecución del escáner en *manual*
    - Establece los tipos de información que se detectarán en función de la directiva de etiquetado de confidencialidad
    - No *aplica una* directiva de etiquetado de confidencialidad
    - Etiqueta automáticamente los archivos en función del contenido, con la etiqueta predeterminada definida para la directiva de etiquetado de confidencialidad
    - No *permite* volver a etiquetar archivos
    - Conserva los detalles del archivo durante el examen y el etiquetado automático, incluidas las fechas modificadas, *las* últimas modificadas y *modificadas por valores*
    - Establece el escáner para excluir los archivos .msg y .tmp al ejecutarse
    - Establece el propietario predeterminado en la cuenta que desea usar al ejecutar el escáner

1. Use el cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir los repositorios que desea examinar en el trabajo de detección de contenido. Por ejemplo, ejecute:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Use una de las siguientes sintaxis, según el tipo de repositorio que agregue:

    - Para un recurso compartido de red, use `\\Server\Folder` .
    - Para una biblioteca SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Para una ruta de acceso local: `C:\Folder`
    - Para una ruta de acceso UNC: `\\Server\Folder`

    > [!NOTE]
    > No se admiten caracteres comodín y no se admiten las ubicaciones de WebDav.
    >
    > Para modificar el repositorio más adelante, use el cmdlet [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) en su lugar. 


Continúe con los pasos siguientes según sea necesario:

- [Ejecutar un ciclo de detección y ver informes del escáner](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Usar PowerShell para configurar el escáner para aplicar la clasificación y la protección](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Usar PowerShell para configurar una directiva DLP con el escáner](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

En la tabla siguiente se enumeran los cmdlets de PowerShell que son relevantes para instalar el escáner y administrar los trabajos de examen de contenido:

| Cmdlet | Descripción |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Agrega un nuevo repositorio al trabajo de examen de contenido. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Devuelve detalles sobre el clúster. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtiene detalles sobre el trabajo de examen de contenido. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtiene detalles sobre los repositorios definidos para el trabajo de examen de contenido. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina el trabajo de examen de contenido. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Quita un repositorio del trabajo de examen de contenido. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define la configuración del trabajo de examen de contenido. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define la configuración de un repositorio existente en el trabajo de examen de contenido. |
| | |

Para más información vea:

- [¿Qué es el escáner de etiquetado unificado de Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Configuración e instalación del escáner de etiquetado unificado de Azure Information Protection (AIP)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Administrar los trabajos de examen de contenido solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).
