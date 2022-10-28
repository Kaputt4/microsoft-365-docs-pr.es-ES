---
title: Implementación con un sistema de Administración de dispositivos móvil (MDM) diferente para Microsoft Defender para punto de conexión en Mac
description: Instale Microsoft Defender para punto de conexión en Mac en otras soluciones de administración.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, macos, catalina, big sur, monterey, ventura, mde o mac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 93e22b11bba51b1b1ac33306c0a01c375ed09d27
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768091"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación con un sistema de mobile Administración de dispositivos (MDM) diferente para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte [la página principal Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión actual del software.


## <a name="approach"></a>Enfoque

> [!CAUTION]

> Actualmente, Microsoft admite oficialmente solo Intune y JAMF para la implementación y administración de Microsoft Defender para punto de conexión en macOS. Microsoft no ofrece ninguna garantía, expresa o implícita, con respecto a la información que se proporciona a continuación.

Si su organización usa una solución de mobile Administración de dispositivos (MDM) que no se admite oficialmente, esto no significa que no pueda implementar ni ejecutar Microsoft Defender para punto de conexión en macOS.

Microsoft Defender para punto de conexión en macOS no depende de ninguna característica específica del proveedor. Se puede usar con cualquier solución MDM que admita las siguientes características:

- Implemente un archivo .pkg de macOS en dispositivos administrados.
- Implemente perfiles de configuración del sistema macOS en dispositivos administrados.
- Ejecute una herramienta o script arbitrario configurados por el administrador en dispositivos administrados.

La mayoría de las soluciones MDM modernas incluyen estas características, pero pueden llamarlas de forma diferente.

Sin embargo, puede implementar Defender para punto de conexión sin el último requisito de la lista anterior:

- No podrá recopilar el estado de forma centralizada.
- Si decide desinstalar Defender para punto de conexión, deberá iniciar sesión en el dispositivo cliente localmente como administrador.

## <a name="deployment"></a>Implementación

La mayoría de las soluciones MDM usan el mismo modelo para administrar dispositivos macOS, con terminología similar. Use la [implementación basada en JAMF](mac-install-with-jamf.md) como plantilla.

### <a name="package"></a>Paquete

Configure la implementación de un [paquete de aplicación necesario](mac-install-with-jamf.md), con el paquete de instalación (wdav.pkg) descargado de [Microsoft 365 Defender portal](mac-install-with-jamf.md).

Para implementar el paquete en la empresa, use las instrucciones asociadas a la solución MDM.

### <a name="license-settings"></a>Configuración de licencia

Configurar [un perfil de configuración del sistema](mac-install-with-jamf.md). 

La solución MDM puede llamarla como "Perfil de configuración personalizada", ya que Microsoft Defender para punto de conexión en macOS no forma parte de macOS.

Use la lista de propiedades, jamf/WindowsDefenderATPOnboarding.plist, que se puede extraer de un paquete de incorporación descargado de [Microsoft 365 Defender portal](mac-install-with-jamf.md).
El sistema puede admitir una lista de propiedades arbitraria en formato XML. Puede cargar el archivo jamf/WindowsDefenderATPOnboarding.plist tal y como está en ese caso.
Como alternativa, puede que primero necesite convertir la lista de propiedades a otro formato.

Normalmente, el perfil personalizado tiene un identificador, un nombre o un atributo de dominio. Debe usar exactamente "com.microsoft.wdav.atp" para este valor.
MDM lo usa para implementar el archivo de configuración en **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** en un dispositivo cliente, y Defender para punto de conexión usa este archivo para cargar la información de incorporación.

### <a name="kernel-extension-policy"></a>Directiva de extensión de kernel

Configure una directiva de extensión KEXT o kernel. Use el identificador de equipo **UBF8T346G9** para permitir las extensiones de kernel proporcionadas por Microsoft.

> [!CAUTION]
> Si el entorno consta de dispositivos Apple Silicon (M1), estas máquinas no deben recibir perfiles de configuración con directivas KEXT.
> Apple no admite KEXT en estas máquinas; la implementación de este perfil produciría un error en las máquinas M1.

### <a name="system-extension-policy"></a>Directiva de extensión del sistema

Configure una directiva de extensión del sistema. Use el identificador de equipo **UBF8T346G9** y apruebe los siguientes identificadores de agrupación:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Directiva de acceso al disco completo

Conceda acceso completo al disco a los siguientes componentes:

- Microsoft Defender para punto de conexión
    - Identificador: `com.microsoft.wdav`
    - Tipo de identificador: id. de lote
    - Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- extensión de seguridad de Microsoft Defender para punto de conexión
    - Identificador: `com.microsoft.wdav.epsext`
    - Tipo de identificador: id. de lote
    - Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Directiva de extensión de red

Como parte de las funcionalidades de detección y respuesta de puntos de conexión, Microsoft Defender para punto de conexión en macOS inspecciona el tráfico de socket e informa de esta información al portal de Microsoft 365 Defender. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

- Tipo de filtro: Complemento
- Identificador de agrupación de complementos: `com.microsoft.wdav`
- Identificador de agrupación del proveedor de datos de filtro: `com.microsoft.wdav.netext`
- Requisito designado del proveedor de datos de filtro: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Sockets de filtro: `true`

## <a name="check-installation-status"></a>Comprobación del estado de la instalación

Ejecute [Microsoft Defender para punto de conexión](mac-install-with-jamf.md) en un dispositivo cliente para comprobar el estado de incorporación.
