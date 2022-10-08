---
title: Soporte técnico de Azure Information Protection para Office 365 operados por 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Obtenga más información sobre Azure Information Protection (AIP) para Office 365 operados por 21Vianet y cómo configurarlo para clientes en China.
monikerRange: o365-21vianet
ms.openlocfilehash: b1e140b1862cdfaa8662a3c3794125cd9e156f47
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68192649"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Soporte técnico de Azure Information Protection para Office 365 operados por 21Vianet

En este artículo se tratan las diferencias entre la compatibilidad de Azure Information Protection (AIP) con Office 365 operadas por 21Vianet y ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China&mdash;, incluido cómo instalar el escáner local de AIP y administrar trabajos de examen de contenido.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferencias entre AIP para Office 365 operadas por 21Vianet y ofertas comerciales

Aunque nuestro objetivo es ofrecer todas las características y funcionalidades comerciales a los clientes de China con nuestra oferta de AIP para Office 365 operada por 21Vianet, nos gustaría destacar algunas funcionalidades que nos gustaría destacar.

En la lista siguiente se incluyen las brechas existentes entre AIP para Office 365 operadas por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:

- El cifrado de Active Directory Rights Management Services (AD RMS) solo se admite en Aplicaciones Microsoft 365 para empresas (compilación 11731.10000 o posterior). Office Profesional Plus no admite AD RMS.

- La migración de AD RMS a AIP no está disponible actualmente.
  
- Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.
  
- El uso compartido de documentos y datos adjuntos de correo electrónico con los usuarios en la nube comercial no está disponible actualmente. Esto incluye Office 365 operados por 21 usuarios deVianet en la nube comercial, no Office 365 operados por 21 usuarios deVianet en la nube comercial y usuarios con una licencia RMS for Individuals.
  
- IRM con SharePoint (sitios y bibliotecas protegidos por IRM) no está disponible actualmente.
  
- La extensión de dispositivo móvil para AD RMS no está disponible actualmente.

- Azure China 21Vianet no admite [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) .

- El área AIP del Azure Portal no está disponible para los clientes de China. Use [comandos de PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) en lugar de realizar acciones en el portal, como administrar y ejecutar los trabajos de examen de contenido.

- Los puntos de conexión de AIP en Office 365 operados por 21Vianet son diferentes de los puntos de conexión necesarios para otros servicios en la nube. Se requiere conectividad de red de clientes a los siguientes puntos de conexión:
    - Descargar directivas de etiquetas y etiquetas: `*.protection.partner.outlook.cn`
    - Azure Rights Management servicio:`*.aadrm.cn`

## <a name="configure-aip-for-customers-in-china"></a>Configuración de AIP para clientes en China

Para configurar AIP para clientes en China:
1. [Habilite Rights Management para el inquilino](#step-1-enable-rights-management-for-the-tenant).

1. [Agregue la entidad de servicio Microsoft Information Protection Sync Service](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).

1. [Configure el cifrado DNS](#step-3-configure-dns-encryption).

1. [Instale y configure el cliente de etiquetado unificado de AIP](#step-4-install-and-configure-the-aip-unified-labeling-client).

1. [Configurar aplicaciones de AIP en Windows](#step-5-configure-aip-apps-on-windows).

1. [Instale el analizador local de AIP y administre los trabajos de examen de contenido](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs). 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Paso 1: Habilitar Rights Management para el inquilino

Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.

1. Compruebe si RMS está habilitado:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService`.
    3. Importe el módulo mediante `Import-Module AipService`.
    4. Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud`.
    5. Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled`.

2. Si el estado funcional es `Disabled`, ejecute `Enable-AipService`.

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Paso 2: Agregar la entidad de servicio de sincronización de Microsoft Information Protection

La entidad de servicio **Microsoft Information Protection Sync Service** no está disponible en los inquilinos de Azure China de forma predeterminada y es necesaria para Azure Information Protection. Cree esta entidad de servicio manualmente mediante el módulo Azure Az PowerShell.

1. Si no tiene instalado el módulo Azure Az, instálelo o use un recurso donde el módulo Azure Az esté preinstalado, como [Azure Cloud Shell](/azure/cloud-shell/overview). Para obtener más información, consulte [Instalación del módulo Azure Az PowerShell](/powershell/azure/install-az-ps).

1. Conéctese al servicio mediante el cmdlet [Connect-AzAccount](/powershell/module/az.accounts/Connect-AzAccount) y el nombre del `azurechinacloud` entorno:

    ```powershell
    Connect-azaccount -environmentname azurechinacloud
    ```

1. Cree manualmente la entidad de servicio **Microsoft Information Protection Sync Service** mediante el cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) y el `870c4f2e-85b6-4d43-bdda-6ed9a579b725` identificador de aplicación del servicio de sincronización de Microsoft Purview Information Protection:

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Después de agregar la entidad de servicio, agregue los permisos pertinentes necesarios para el servicio.

### <a name="step-3-configure-dns-encryption"></a>Paso 3: Configuración del cifrado DNS

Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia de China del servicio y arrancar desde allí. Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador de inquilinos debe configurar un registro SRV de DNS con información sobre la dirección URL de Azure RMS. Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y producirá un error.

Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, `joe@contoso.cn`), y no el `onmschina` nombre de usuario (por ejemplo, `joe@contoso.onmschina.cn`). El nombre de dominio del nombre de usuario se usa para el redireccionamiento DNS a la instancia de servicio correcta.

#### <a name="configure-dns-encryption---windows"></a>Configuración del cifrado DNS: Windows

1. Obtenga el identificador de RMS:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService`.
    3. Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud`.
    4. Ejecute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.

2. Inicie sesión en el proveedor de DNS, vaya a la configuración dns del dominio y agregue un nuevo registro SRV.

    - Servicio = `_rmsredir`
    - Protocolo = `_http`
    - Nombre = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (donde GUID es el identificador de RMS)
    - Priority, Weight, Seconds, TTL = valores predeterminados

3. Asocie el dominio personalizado al inquilino de la [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Esto agregará una entrada en DNS, que podría tardar varios minutos en comprobarse después de agregar el valor a la configuración de DNS.

4. Inicie sesión en el Centro de administración de Microsoft 365 con las credenciales de administrador global correspondientes y agregue el dominio (por ejemplo, `contoso.cn`) para la creación del usuario. En el proceso de verificación, es posible que se requieran cambios de DNS adicionales. Una vez realizada la comprobación, se pueden crear usuarios.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configuración del cifrado DNS: Mac, iOS, Android

Inicie sesión en el proveedor de DNS, vaya a la configuración dns del dominio y agregue un nuevo registro SRV.

- Servicio = `_rmsdisco`
- Protocolo = `_http`
- Nombre = `_tcp`
- Target = `api.aadrm.cn`
- Puerto = `80`
- Priority, Weight, Seconds, TTL = valores predeterminados


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Paso 4: Instalación y configuración del cliente de etiquetado unificado de AIP

Descargue e instale el cliente de etiquetado unificado de AIP desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

Para obtener más información, consulte:

- [Documentación de AIP](/azure/information-protection/)
- [Historial de versiones de AIP y directiva de soporte técnico](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos del sistema de AIP](/azure/information-protection/requirements)
- [Inicio rápido de AIP: Implementación del cliente de AIP](/azure/information-protection/quickstart-deploy-client)
- [Guía del administrador de AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guía del usuario de AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Más información sobre las etiquetas de confidencialidad de Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Paso 5: Configuración de aplicaciones AIP en Windows

Las aplicaciones de AIP en Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:

- Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Nombre = `CloudEnvType`
- Valor = `6` (valor predeterminado = 0)
- Tipo = `REG_DWORD`

> [!IMPORTANT]
> Asegúrese de que no elimina la clave del Registro después de una desinstalación. Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial). Si la clave está vacía o es incorrecta, también se agrega un error de impresión al registro.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Paso 6: Instalación del analizador local de AIP y administración de trabajos de examen de contenido

Instale el analizador local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales, y aplique las etiquetas de clasificación y protección configuradas en la directiva de su organización.

Al configurar y administrar los trabajos de examen de contenido, use el procedimiento siguiente en lugar de la [interfaz de Azure Portal](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) que usan las ofertas comerciales.

Para obtener más información, consulte [¿Qué es el analizador de etiquetado unificado de Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y [Administración de los trabajos de examen de contenido solo mediante PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).

**Para instalar y configurar el escáner**:

1. Inicie sesión en el equipo con Windows Server que ejecutará el analizador. Use una cuenta que tenga derechos de administrador local y que tenga permisos para escribir en la base de datos maestra de SQL Server.

1. Comience con PowerShell cerrado. Si ha instalado previamente el cliente y el escáner de AIP, asegúrese de que el servicio **AIPScanner** está detenido.

1. Abra una sesión de Windows PowerShell con la opción **Ejecutar como administrador**.

1. Ejecute el cmdlet [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) y especifique la instancia de SQL Server en la que crear una base de datos para el analizador de Azure Information Protection y un nombre significativo para el clúster del analizador.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Puede usar el mismo nombre de clúster en el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para asociar varios nodos del analizador al mismo clúster. El uso del mismo clúster para varios nodos de escáner permite que varios escáneres funcionen juntos para realizar los exámenes.
    > 

1. Compruebe que el servicio ya está instalado mediante **servicios de herramientas** >  administrativas.

    El servicio instalado se denomina **Azure Information Protection Scanner** y está configurado para ejecutarse mediante la cuenta de servicio del analizador que creó.

1. Obtenga un token de Azure para usarlo con el analizador. Un token de Azure AD permite que el analizador se autentique en el servicio azure Information Protection, lo que permite que el analizador se ejecute de forma no interactiva. 

    1. Abra el Azure Portal y cree una aplicación de Azure AD para especificar un token de acceso para la autenticación. Para obtener más información, consulte [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).
    
        > [!TIP]
        > Al crear y configurar aplicaciones de Azure AD para el comando [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), el panel **Solicitar permisos de API** muestra las **API que usa mi organización** en lugar de la pestaña **API de Microsoft**. Seleccione las **API que usa mi organización** para seleccionar **Azure Rights Management Services**. 
        >

    1. Desde el equipo con Windows Server, si a la cuenta de servicio del analizador se le ha concedido el derecho **Iniciar sesión localmente** para la instalación, inicie sesión con esta cuenta e inicie una sesión de PowerShell. 
    
        Si no se puede conceder a la cuenta de servicio del analizador el derecho **Iniciar sesión localmente** para la instalación, use el parámetro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), tal como se describe en [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

    1. Ejecute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) y especifique los valores copiados de la aplicación de Azure AD:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Por ejemplo:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    El analizador ahora tiene un token para autenticarse en Azure AD. Este token es válido durante un año, dos años o nunca, según la configuración del secreto de cliente de la **aplicación web /API** en Azure AD. Cuando expire el token, debe repetir este procedimiento.

1. Ejecute el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para establecer que el analizador funcione en modo sin conexión. Ejecute: 

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Ejecute el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para crear un trabajo de examen de contenido predeterminado.

    El único parámetro necesario en el cmdlet **Set-AIPScannerContentScanJob** es **Enforce**. Sin embargo, es posible que quiera definir otras opciones para el trabajo de examen de contenido en este momento. Por ejemplo:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    La sintaxis anterior configura los siguientes valores mientras continúa la configuración:

    - Mantiene la programación de ejecución del escáner *en el manual*
    - Establece los tipos de información que se detectarán en función de la directiva de etiquetado de confidencialidad.
    - *No* aplica una directiva de etiquetado de confidencialidad
    - Etiqueta automáticamente los archivos en función del contenido, con la etiqueta predeterminada definida para la directiva de etiquetado de confidencialidad.
    - *No permite* volver a etiquetar archivos
    - Conserva los detalles del archivo durante el examen y el etiquetado automático, incluida *la fecha de modificación*, *última modificación* y *modificación por* valores
    - Establece el analizador para excluir los archivos .msg y .tmp al ejecutar
    - Establece el propietario predeterminado en la cuenta que desea usar al ejecutar el analizador.

1. Use el cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir los repositorios que desea examinar en el trabajo de examen de contenido. Por ejemplo, ejecute:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Use una de las siguientes sintaxis, en función del tipo de repositorio que agregue:

    - Para un recurso compartido de red, use `\\Server\Folder`.
    - Para una biblioteca de SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
    - Para una ruta de acceso local: `C:\Folder`
    - Para una ruta de acceso UNC: `\\Server\Folder`

    > [!NOTE]
    > No se admiten caracteres comodín y no se admiten ubicaciones webDav.
    >
    > Para modificar el repositorio más adelante, use el cmdlet [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) en su lugar. 


Continúe con los pasos siguientes según sea necesario:

- [Ejecutar un ciclo de detección y ver informes del escáner](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Uso de PowerShell para configurar el analizador para aplicar la clasificación y la protección](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Uso de PowerShell para configurar una directiva DLP con el analizador](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

En la tabla siguiente se enumeran los cmdlets de PowerShell que son pertinentes para instalar el analizador y administrar los trabajos de examen de contenido:

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

Para obtener más información, consulte:

- [¿Qué es el analizador de etiquetado unificado de Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Configuración e instalación del analizador de etiquetado unificado de Azure Information Protection (AIP)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Administre los trabajos de examen de contenido solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).
