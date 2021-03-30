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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418037"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet

En este artículo se tratan las diferencias entre la compatibilidad con Azure Information Protection (AIP) para Office 365 operado por 21Vianet y las ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China, incluido cómo instalar el escáner local de AIP y administrar trabajos de examen de &mdash; contenido.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferencias entre AIP para Office 365 operado por 21Vianet y ofertas comerciales

Aunque nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a los clientes de China con nuestra oferta de AIP para Office 365 operado por 21Vianet, nos gustaría destacar algunas funciones que nos gustaría destacar.

La siguiente lista incluye las diferencias existentes entre AIP para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:

- Information Rights Management (IRM) solo es compatible con aplicaciones de Microsoft 365 para empresas (compilación 11731.10000 o posterior). Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.

- Actualmente, la migración de Active Directory Rights Management Services (AD RMS) a AIP no está disponible.
  
- Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.
  
- El uso compartido de documentos y datos adjuntos de correo electrónico con usuarios en la nube comercial no está disponible actualmente. Esto incluye Office 365 operado por 21 usuarios deVianet en la nube comercial, que no es Office 365 operado por 21 usuarios deVianet en la nube comercial y usuarios con una licencia rms para individuos.
  
- IRM con SharePoint (bibliotecas y sitios protegidos por IRM) actualmente no está disponible.
  
- La extensión de dispositivo móvil para AD RMS no está disponible actualmente.

- [El Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.

- El área AIP de Azure Portal no está disponible para los clientes en China. Use [comandos de PowerShell en](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) lugar de realizar acciones en el portal, como instalar el escáner local y administrar los trabajos de examen de contenido.

## <a name="configure-aip-for-customers-in-china"></a>Configurar AIP para clientes en China

Para configurar AIP para clientes en China:
1. [Habilitar Rights Management para el inquilino](#step-1-enable-rights-management-for-the-tenant).

2. [Configurar el cifrado DNS](#step-2-configure-dns-encryption).

3. [Instalar y configurar el cliente de etiquetado unificado AIP](#step-3-install-and-configure-the-aip-unified-labeling-client).

4. [Configurar aplicaciones AIP en Windows](#step-4-configure-aip-apps-on-windows).

5. [Instale el escáner local de AIP y administre trabajos de análisis de contenido.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Paso 1: Habilitar Rights Management para el inquilino

Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.

1. Compruebe si RMS está habilitado:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Importe el módulo mediante `Import-Module AipService` .
    4. Conectarse al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    5. Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .

2. Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Paso 2: Configurar el cifrado DNS

Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia china del servicio y arrancar desde allí. Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador del espacio empresarial debe configurar un registro SRV dns con información sobre la dirección URL de Azure RMS. Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y producirá un error.

Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, ), y no con el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ). El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.

#### <a name="configure-dns-encryption---windows"></a>Configurar el cifrado DNS: Windows

1. Obtener el id. de RMS:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Conectarse al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    4. Ejecute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.

2. Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.

    - Service = `_rmsredir`
    - Protocolo = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)
    - Priority, Weight, Seconds, TTL = default values

3. Asocie el dominio personalizado con el inquilino en [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración de DNS.

4. Inicie sesión en el Centro de administración de Microsoft 365 con las credenciales de administración global correspondientes y agregue el dominio (por ejemplo, `contoso.cn` ) para la creación de usuarios. En el proceso de comprobación, es posible que se necesiten cambios dns adicionales. Una vez que se realiza la comprobación, se pueden crear usuarios.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurar el cifrado DNS: Mac, iOS, Android

Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.

- Service = `_rmsdisco`
- Protocolo = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Priority, Weight, Seconds, TTL = default values

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Paso 3: Instalar y configurar el cliente de etiquetado unificado AIP

Descargue el cliente de etiquetado unificado AIP desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

Para más información, vea:

- [Documentación de AIP](/azure/information-protection/)
- [Historial de versiones de AIP y directiva de soporte técnico](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos del sistema AIP](/azure/information-protection/requirements)
- [Inicio rápido de AIP: implementar el cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guía de administrador de AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guía del usuario de AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Obtenga información sobre las etiquetas de confidencialidad de Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>Paso 4: Configurar aplicaciones AIP en Windows

Las aplicaciones AIP en Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:

- Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Valor = `6` (valor predeterminado = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Asegúrese de que no elimina la clave del Registro después de una desinstalación. Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial). Si la clave está vacía o incorrecta, también se agrega un error de impresión al registro.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Paso 5: Instalar el escáner local de AIP y administrar trabajos de detección de contenido

Instale el escáner local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales y aplicar etiquetas de clasificación y protección según lo configurado en la directiva de su organización.

- Al crear y configurar aplicaciones de Azure AD para el comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) el panel Solicitar permisos **de api** muestra las API que mi organización usa en lugar de la pestaña API de **Microsoft.**  Seleccione las **API que usa mi organización para,** a continuación, seleccionar Azure Rights Management **Services**.

- Al instalar el escáner y administrar los trabajos de análisis de contenido, use los cmdlets siguientes en lugar de la interfaz de Azure Portal que usan las ofertas comerciales:<br><br>

    | Cmdlet | Descripción |
    |--|--|
    | [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Agrega un nuevo repositorio al trabajo de examen de contenido. |
    | [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtiene detalles sobre el trabajo de examen de contenido. |
    | [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtiene detalles sobre los repositorios definidos para el trabajo de examen de contenido. |
    | [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina el trabajo de examen de contenido. |
    | [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Quita un repositorio del trabajo de examen de contenido. |
    | [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define la configuración del trabajo de examen de contenido. |
    | [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define la configuración de un repositorio existente en el trabajo de examen de contenido. |
    | | |

> [!TIP]
> Al [instalar el escáner,](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)use el mismo nombre de clúster en el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para asociar varios nodos de escáner al mismo clúster. El uso del mismo clúster para varios nodos de escáner permite que varios escáneres funcionen juntos para realizar los exámenes.
> 
> Use el cmdlet [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) para devolver detalles sobre el clúster.
> 
Para obtener más información, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y Administrar los trabajos de examen de contenido [solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).