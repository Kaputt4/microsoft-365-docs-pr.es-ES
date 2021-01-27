---
title: Soporte técnico de Azure Information Protection para Office 365 operado por 21Vianet
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
description: Obtenga más información sobre Azure Information Protection (AIP) para Office 365 operado por 21Vianet y cómo configurarlo para los clientes de China.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988049"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Soporte técnico de Azure Information Protection para Office 365 operado por 21Vianet

En este artículo se tratan las diferencias entre el soporte de Azure Information Protection (AIP) para Office 365 operado por 21Vianet y las ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China, incluido cómo instalar el escáner local de AIP y administrar trabajos de análisis de &mdash; contenido.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferencias entre AIP para Office 365 operado por 21Vianet y ofertas comerciales

Aunque nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a los clientes de China con nuestra oferta de AIP para Office 365 operado por 21Vianet, nos gustaría resaltar algunas funciones que faltan.

La siguiente lista incluye las diferencias existentes entre AIP para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:

- Information Rights Management (IRM) solo es compatible con Aplicaciones de Microsoft 365 para empresas (compilación 11731.10000 o posterior). Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.

- La migración de Active Directory Rights Management Services (AD RMS) a AIP no está disponible actualmente.
  
- Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.
  
- El uso compartido de documentos y datos adjuntos de correo electrónico con usuarios en la nube comercial no está disponible actualmente. Esto incluye Office 365 operado por usuarios de 21Vianet en la nube comercial, usuarios que no son de Office 365 operados por 21Vianet en la nube comercial y usuarios con una licencia rms para personas.
  
- IRM con SharePoint (bibliotecas y sitios protegidos por IRM) no está disponible actualmente.
  
- La extensión de dispositivo móvil para AD RMS no está disponible actualmente.

- El [Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.

## <a name="configure-aip-for-customers-in-china"></a>Configurar AIP para clientes en China

Para configurar AIP para clientes en China:
1. [Habilite Rights Management para el inquilino.](#step-1-enable-rights-management-for-the-tenant)

2. [Configurar el cifrado DNS.](#step-2-configure-dns-encryption)

3. [Instale y configure el cliente de etiquetado unificado de AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Configurar aplicaciones AIP en Windows.](#step-4-configure-aip-apps-on-windows)

5. [Instale el escáner local de AIP y administre los trabajos de análisis de contenido.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Paso 1: Habilitar Rights Management para el inquilino

Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.

1. Compruebe si RMS está habilitado:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Importe el módulo mediante `Import-Module AipService` .
    4. Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    5. Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .

2. Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Paso 2: Configurar el cifrado DNS

Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia de China del servicio y arrancar desde allí. Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador de inquilinos debe configurar un registro SRV de DNS con información sobre la dirección URL de Azure RMS. Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y se producirá un error.

Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio de inquilino (por ejemplo, ) y no en el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ). El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.

#### <a name="configure-dns-encryption---windows"></a>Configurar el cifrado DNS: Windows

1. Obtenga el id. de RMS:

    1. Inicie PowerShell como administrador.
    2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
    3. Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud` .
    4. Ejecutar `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.

2. Inicie sesión en su proveedor de DNS, vaya a la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.

    - Service = `_rmsredir`
    - Protocolo = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)
    - Prioridad, Peso, Segundos, TTL = valores predeterminados

3. Asocie el dominio personalizado con el inquilino en [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración dns.

4. Inicie sesión en el Centro de administración de Microsoft 365 con las credenciales de administrador global correspondientes y agregue el dominio (por ejemplo, ) para `contoso.cn` la creación de usuarios. En el proceso de comprobación, es posible que se necesiten cambios dns adicionales. Una vez realizada la comprobación, se pueden crear usuarios.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurar el cifrado DNS : Mac, iOS, Android

Inicie sesión en su proveedor de DNS, vaya a la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.

- Service = `_rmsdisco`
- Protocolo = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Prioridad, Peso, Segundos, TTL = valores predeterminados

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Paso 3: Instalar y configurar el cliente de etiquetado unificado AIP

Descargue el cliente de etiquetado unificado de AIP desde el [Centro de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Para más información, vea:

- [Documentación de AIP](/azure/information-protection/)
- [Historial de versiones AIP y directiva de soporte técnico](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos del sistema AIP](/azure/information-protection/requirements)
- [Inicio rápido de AIP: implementar el cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guía de administrador de AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guía de usuario de AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Más información sobre las etiquetas de confidencialidad de Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Paso 4: Configurar aplicaciones AIP en Windows

Las aplicaciones AIP en Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:

- Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Valor = `6` (valor predeterminado = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Asegúrese de no eliminar la clave del Registro después de una desinstalación. Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial). Si la clave está vacía o es incorrecta, también se agrega un error de impresión al registro.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Paso 5: Instalar el escáner local de AIP y administrar trabajos de análisis de contenido

Instale el escáner local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales y aplicar etiquetas de clasificación y protección según lo configurado en la directiva de su organización.

Al instalar el escáner y administrar los trabajos de análisis de contenido, use los siguientes cmdlets en lugar de la interfaz de Azure Portal que usan las ofertas comerciales:<br><br>

| Cmdlet | Descripción |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Agrega un nuevo repositorio al trabajo de análisis de contenido. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtiene detalles sobre el trabajo de análisis de contenido. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtiene detalles acerca de los repositorios definidos para el trabajo de análisis de contenido. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina el trabajo de análisis de contenido. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Quita un repositorio del trabajo de análisis de contenido. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define la configuración del trabajo de análisis de contenido. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define la configuración de un repositorio existente en el trabajo de análisis de contenido. |

Para obtener más información, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y Administre los trabajos de análisis de contenido solo [con PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)