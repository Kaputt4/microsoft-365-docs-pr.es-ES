---
title: Comprobador de la evaluación de preparación descargable
description: Comprueba la configuración del dispositivo y la red, incluidos los puntos de conexión necesarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581039"
---
# <a name="downloadable-readiness-assessment-checker"></a>Comprobador de la evaluación de preparación descargable

Para funcionar bien con Escritorio administrado de Microsoft, los dispositivos deben cumplir ciertos requisitos de hardware y configuración. Además, cada dispositivo debe poder alcanzar puntos de conexión clave. Descargue y ejecute esta herramienta para obtener un informe HTML, ver los resultados y, a continuación, realizar acciones. Deberás descargar la herramienta y los archivos de soporte técnico y, a continuación, ejecutarla manualmente en cada dispositivo en el que quieras inscribirte Escritorio administrado de Microsoft.

Para cada comprobación, la herramienta mostrará uno de los tres resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Advertencia    | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *La inscripción producirá un* error si no se solucionan estos problemas. Siga los pasos de la herramienta para resolverlos.        |

## <a name="obtain-the-checker"></a>Obtener el control

Descargue el .zip archivo de https://aka.ms/mmddratoolv0 .

> [!NOTE]
> El usuario que ejecuta la herramienta debe tener derechos de administrador local en el dispositivo donde la está ejecutando.

 A continuación, ejecute la herramienta siguiendo estos pasos:

1. Copia el archivo .zip descargado en cada dispositivo que quieras comprobar.
2. Extraiga todos los archivos de la descarga comprimida.
3. Ejecute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Cuando aparezca el símbolo del sistema control de acceso de usuario, seleccione **Sí**. La herramienta se ejecuta y abre un informe en el explorador predeterminado.

También puedes descargar y extraer el archivo .zip a una ubicación compartida, acceder aMicrosoft.MMD.DeviceReadinessAssessmentTool.exe **desde** cada dispositivo y, a continuación, ejecutarlo localmente.


## <a name="checks"></a>Comprobaciones

La herramienta descargable comprueba estos elementos relacionados con el dispositivo y la red:

### <a name="hardware"></a>Hardware

Los dispositivos deben cumplir requisitos de hardware específicos para trabajar con Escritorio administrado de Microsoft. Actualmente, solo se [pueden](../service-description/device-list.md) inscribir dispositivos aprobados específicos. 

Si el dispositivo falla alguna de las comprobaciones, no es compatible con Escritorio administrado de Microsoft.

### <a name="network-endpoints"></a>Puntos de conexión de red

Los dispositivos pueden llegar a varios [puntos de conexión clave](network.md) para trabajar con Escritorio administrado de Microsoft.

Si la herramienta informa de **un resultado** no listo, consulte el informe detallado para averiguar qué puntos de conexión no eran accesibles. A continuación, ajuste el firewall u otra configuración de red para asegurarse de que se pueda alcanzar esos puntos de conexión.

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise de wi-fi

Un **resultado de asesoramiento** significa que está usando algunos perfiles wi-fi que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, vea [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).

#### <a name="lan-profiles"></a>Perfiles DE LAN

Un **resultado de asesoramiento** significa que tiene LAN que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, vea [Prepare certificates and network profiles for Escritorio administrado de Microsoft](certs-wifi-lan.md).

#### <a name="vpn-profiles"></a>Perfiles vpn

Un **resultado de aviso** significa que está usando una red privada virtual (VPN). Cree un perfil de VPN que implemente certificados integrados con Microsoft Intune. Para obtener más información, vea [Prepare certificates and network profiles for Escritorio administrado de Microsoft](certs-wifi-lan.md).

#### <a name="mapped-drives"></a>Unidades asignadas

Un **resultado de aviso** significa que tiene algunas unidades asignadas, lo que no se recomienda. Para obtener más información, vea [Prepare mapped drives for Escritorio administrado de Microsoft](mapped-drives.md).

#### <a name="print-queues"></a>Colas de impresión

Un **resultado de aviso** significa que tiene algunas colas de impresión pendientes, que no se recomiendan. Una solución es usar la impresión en la nube. Para obtener más información, vea [Prepare printing resources for Escritorio administrado de Microsoft](printing.md).

#### <a name="proxies"></a>Proxies

Un **resultado de aviso** significa que tiene un servidor proxy en uso. Para obtener más información, vea [Configuración de red para Escritorio administrado de Microsoft](network.md).

