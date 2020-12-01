---
title: Paridad entre Azure Information Protection para Office 365 ofrecido por 21Vianet y ofertas comerciales
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
description: Obtenga más información sobre Azure Information Protection para Office 365 operado por 21Vianet y cómo configurarlo para clientes en China.
monikerRange: o365-21vianet
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519346"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paridad entre Azure Information Protection para Office 365 ofrecido por 21Vianet y ofertas comerciales

Aunque nuestro objetivo es ofrecer todas las características y funcionalidades comerciales a los clientes en China con nuestra oferta de Azure Information Protection para Office 365 operado por 21Vianet, hay algunas funcionalidades que nos gustaría destacar.

La siguiente lista incluye las brechas existentes entre Azure Information Protection para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de julio de 2019:

- Information Rights Management (IRM) solo es compatible con las aplicaciones de Microsoft 365 para empresas (compilación 11731,10000 o posteriores). Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.

- Actualmente no se puede realizar la migración de Active Directory Rights Management Services (AD RMS) a Azure Information Protection.
  
- Se admite el uso compartido de correo electrónico protegido para los usuarios en la nube comercial.
  
- Actualmente no está disponible el uso compartido de documentos y datos adjuntos de correo electrónico en los usuarios de la nube comercial. Esto incluye Office 365 operado por usuarios de 21Vianet en la nube comercial, los usuarios que no son de Office 365 operados por 21Vianet en la nube comercial y los usuarios con una licencia de RMS para personas.
  
- En estos momentos, IRM con SharePoint (bibliotecas y sitios protegidos por IRM) no está disponible.
  
- La extensión de dispositivos móviles para AD RMS actualmente no está disponible.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Configuración de Azure Information Protection para clientes en China

### <a name="enable-rights-management-for-the-tenant"></a>Habilitar la administración de derechos para el inquilino

Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.

- Compruebe si el RMS está habilitado:
  1. Inicie PowerShell como administrador.
  2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
  3. Importe el módulo mediante `Import-Module AipService` .
  4. Conéctese al servicio con `Connect-AipService -environmentname azurechinacloud` .
  5. Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .

- Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>Configuración de DNS para el cifrado (Windows)

Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia de China del servicio y arrancar desde allí. Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador de inquilinos debe configurar un registro SRV de DNS con información sobre la dirección URL de Azure RMS. Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y se producirá un error.

Además, se supone que los usuarios inician sesión con un nombre de usuario basado en el dominio de propiedad del espacio empresarial (por ejemplo, `joe@contoso.cn` ) y no en el `onmschina` nombre de usuario (por ejemplo, `joe@contoso.onmschina.cn` ). El nombre de dominio del nombre de usuario se usa para el redireccionamiento de DNS a la instancia de servicio correcta.

- Obtener el identificador de RMS:
  1. Inicie PowerShell como administrador.
  2. Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .
  3. Conéctese al servicio con `Connect-AipService -environmentname azurechinacloud` .
  4. Ejecutar `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.

- Inicie sesión en el proveedor de DNS, navegue hasta la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.
  - Servicio = `_rmsredir`
  - Protocolo = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (donde GUID es el identificador RMS)
  - Prioridad, peso, segundos, TTL = valores predeterminados

- Asocie el dominio personalizado con el inquilino en [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Esto agregará una entrada en DNS, que puede tardar varios minutos en realizar comprobaciones después de agregar el valor a la configuración de DNS.

- Inicie sesión en el centro de administración de Microsoft 365 con las credenciales de administrador global correspondientes y agregue el dominio (por ejemplo, `contoso.cn` ) para la creación de usuarios. En el proceso de comprobación, es posible que se necesiten cambios de DNS adicionales. Una vez realizada la comprobación, se pueden crear usuarios.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Configuración de DNS para cifrado (Mac, iOS, Android)

- Inicie sesión en el proveedor de DNS, navegue hasta la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.
  - Servicio = `_rmsdisco`
  - Protocolo = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - Port = `80`
  - Prioridad, peso, segundos, TTL = valores predeterminados
