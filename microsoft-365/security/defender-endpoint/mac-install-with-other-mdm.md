---
title: Implementación con un sistema de administración de dispositivos móviles (MDM) diferente para Microsoft Defender para Endpoint para Mac
description: Instale Microsoft Defender para Endpoint para Mac en otras soluciones de administración.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e929c17ada761a334700f6e66d2921483686834b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861568"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación con un sistema de administración de dispositivos móviles (MDM) diferente para Microsoft Defender para Endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulta la página principal de Microsoft Defender para Endpoint [en macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.


## <a name="approach"></a>Enfoque

> [!CAUTION]

> Actualmente, Microsoft admite oficialmente solo Intune y JAMF para la implementación y administración de Microsoft Defender para Endpoint en macOS. Microsoft no ofrece garantías, explícitas o implícitas, con respecto a la información que se proporciona a continuación.

Si su organización usa una solución de administración de dispositivos móviles (MDM) que no es compatible oficialmente, esto no significa que no pueda implementar o ejecutar Microsoft Defender para Endpoint en macOS.

Microsoft Defender para endpoint en macOS no depende de las características específicas del proveedor. Se puede usar con cualquier solución MDM que admita las siguientes características:

- Implementar un .pkg de macOS en dispositivos administrados.
- Implementar perfiles de configuración del sistema macOS en dispositivos administrados.
- Ejecute una herramienta o un script arbitrarios configurados por el administrador en dispositivos administrados.

La mayoría de las soluciones MDM modernas incluyen estas características, sin embargo, pueden llamarlas de forma diferente.

Sin embargo, puede implementar Defender sin el último requisito de la lista anterior:

- No podrá recopilar el estado de forma centralizada
- Si decide desinstalar Defender, tendrá que iniciar sesión en el dispositivo cliente localmente como administrador

## <a name="deployment"></a>Implementación

La mayoría de las soluciones MDM usan el mismo modelo para administrar dispositivos macOS, con terminología similar. Use [la implementación basada en JAMF](mac-install-with-jamf.md) como plantilla.

### <a name="package"></a>Paquete

Configure la implementación de un [paquete de aplicación](mac-install-with-jamf.md)necesario, con el paquete de instalación (wdav.pkg) descargado del Centro de seguridad de Microsoft [Defender](mac-install-with-jamf.md).

Para implementar el paquete en tu empresa, usa las instrucciones asociadas con la solución MDM.

### <a name="license-settings"></a>Configuración de licencia

Configurar un [perfil de configuración del sistema](mac-install-with-jamf.md). 

La solución MDM puede llamarla algo así como "Perfil de configuración personalizada", ya que Microsoft Defender para Endpoint en macOS no forma parte de macOS.

Usa la lista de propiedades, jamf/WindowsDefenderATPOnboarding.plist, que se puede extraer de un paquete de incorporación descargado del Centro de seguridad [de Microsoft Defender](mac-install-with-jamf.md).
El sistema puede admitir una lista de propiedades arbitrarias en formato XML. Puedes cargar el archivo jamf/WindowsDefenderATPOnboarding.plist tal como está en ese caso.
Como alternativa, es posible que primero necesites convertir la lista de propiedades a otro formato.

Normalmente, el perfil personalizado tiene un identificador, un nombre o un atributo de dominio. Debe usar exactamente "com.microsoft.wdav.atp" para este valor.
MDM lo usa para implementar el archivo de configuración en **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** en un dispositivo cliente y Defender usa este archivo para cargar la información de incorporación.

### <a name="kernel-extension-policy"></a>Directiva de extensión de kernel

Configurar una directiva de extensión de kernel o KEXT. Use el identificador de equipo **UBF8T346G9** para permitir extensiones de kernel proporcionadas por Microsoft.

> [!CAUTION]
> Si el entorno consta de dispositivos Apple Silicon (M1), estas máquinas no deben recibir perfiles de configuración con directivas KEXT.
> Apple no admite KEXT en estas máquinas, la implementación de dicho perfil produciría un error en máquinas M1.

### <a name="system-extension-policy"></a>Directiva de extensión del sistema

Configurar una directiva de extensión del sistema. Use el identificador de equipo **UBF8T346G9** y apruebe los siguientes identificadores de agrupación:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Directiva de acceso a disco completo

Conceder acceso en disco completo a los siguientes componentes:

- Microsoft Defender para punto de conexión
    - Identificador: `com.microsoft.wdav`
    - Tipo de identificador: Id. de agrupación
    - Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender para la extensión de seguridad de extremo
    - Identificador: `com.microsoft.wdav.epsext`
    - Tipo de identificador: Id. de agrupación
    - Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Directiva de extensión de red

Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint en macOS inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

- Tipo de filtro: Complemento
- Identificador de agrupación de complementos: `com.microsoft.wdav`
- Identificador de agrupación del proveedor de datos de filtro: `com.microsoft.wdav.netext`
- Requisito designado por el proveedor de datos de filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Sockets de filtro: `true`

## <a name="check-installation-status"></a>Comprobar el estado de la instalación

Ejecute [Microsoft Defender para endpoint](mac-install-with-jamf.md) en un dispositivo cliente para comprobar el estado de incorporación.
