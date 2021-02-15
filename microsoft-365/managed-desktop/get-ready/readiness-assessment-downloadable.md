---
title: Comprobador de la evaluación de preparación descargable
description: Comprueba la configuración de dispositivo y red, incluidos los puntos de conexión necesarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922025"
---
# <a name="downloadable-readiness-assessment-checker"></a>Comprobador de la evaluación de preparación descargable

Para funcionar bien con el Escritorio administrado de Microsoft, los dispositivos deben cumplir ciertos requisitos de hardware y configuración. Además, cada dispositivo debe ser capaz de alcanzar puntos de conexión clave. Descargue y ejecute esta herramienta para obtener un informe HTML, ver los resultados y, a continuación, tomar medidas. Deberás descargar la herramienta y los archivos de soporte técnico y, a continuación, ejecutarla manualmente en cada dispositivo que quieras inscribir en el Escritorio administrado de Microsoft.

Para cada comprobación, la herramienta mostrará uno de los tres resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Aviso    | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *Si no* solucionas estos problemas, se producirá un error en la inscripción. Siga los pasos de la herramienta para resolverlos.        |

## <a name="obtain-the-checker"></a>Obtener el checker

Descargue el archivo .zip desde https://aka.ms/mmddratoolv0 .

> [!NOTE]
> El usuario que ejecuta la herramienta debe tener derechos de administrador local en el dispositivo donde la está ejecutando.

 A continuación, ejecute la herramienta siguiendo estos pasos:

1. Copia el archivo .zip descargado en cada dispositivo que quieras comprobar.
2. Extraiga todos los archivos de la descarga comprimida.
3. Ejecute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Cuando aparezca el mensaje Control de acceso de usuario, seleccione **Sí**. La herramienta se ejecuta y abre un informe en el explorador predeterminado.

También puedes descargar y extraer el archivo .zip en una ubicación compartida, acceder a **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** de cada dispositivo y, a continuación, ejecutarlo localmente.


## <a name="checks"></a>Comprobaciones

La herramienta descargable comprueba estos elementos relacionados con el dispositivo y la red:

### <a name="hardware"></a>Hardware

Los dispositivos deben cumplir requisitos de hardware específicos para trabajar con escritorio administrado de Microsoft. Actualmente, solo pueden [inscribirse](../service-description/device-list.md) dispositivos aprobados específicos. 

Si el dispositivo produce un error en cualquiera de las comprobaciones, no es compatible con el Escritorio administrado de Microsoft.

### <a name="network-endpoints"></a>Puntos de conexión de red

Los dispositivos pueden llegar a varios [puntos de conexión clave para](network.md) trabajar con escritorio administrado de Microsoft.

Si la herramienta informa de un **resultado** no listo, consulta el informe detallado para averiguar a qué puntos de conexión no se ha accesible. A continuación, ajusta el firewall u otra configuración de red para garantizar que se puedan alcanzar esos puntos de conexión.

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enterprise-wi-fi-profiles"></a>Perfiles wi-fi empresariales

Un **resultado de** aviso significa que estás usando algunos perfiles wi-fi que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, consulta [Implementar certificados y perfil de Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>Perfiles LAN

Un **resultado de** aviso significa que tiene LAN que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>Perfiles de VPN

Un **resultado de** aviso significa que estás usando una red privada virtual (VPN). Cree un perfil de VPN que implemente certificados integrados con Microsoft Intune. Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Unidades asignadas

Un **resultado de aviso** significa que tienes algunas unidades asignadas, lo cual no se recomienda. Para obtener más información, vea [Preparar unidades asignadas para escritorio administrado de Microsoft.](mapped-drives.md)

#### <a name="print-queues"></a>Colas de impresión

Un **resultado de aviso** significa que tiene algunas colas de impresión pendientes, que no se recomiendan. Una solución es usar la impresión en la nube. Para obtener más información, vea [Preparar los recursos de impresión para escritorio administrado de Microsoft.](printing.md)

#### <a name="proxies"></a>Proxies

Un **resultado de** aviso significa que tiene un servidor proxy en uso. Para obtener más información, vea [Configuración de red para Escritorio administrado de Microsoft.](network.md)

