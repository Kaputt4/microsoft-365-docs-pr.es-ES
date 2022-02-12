---
title: Comprobador de la evaluación de preparación descargable
description: Comprueba la configuración del dispositivo y la red, incluidos los puntos de conexión necesarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 9e3ad0953cdbd6561f9a0145ccff5aefe24b8dfb
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765617"
---
# <a name="downloadable-readiness-assessment-checker"></a>Comprobador de la evaluación de preparación descargable

Para funcionar bien con Microsoft Managed Desktop, los dispositivos deben cumplir ciertos requisitos de hardware y configuración. Cada dispositivo debe poder alcanzar puntos de conexión clave.

Descargue y ejecute la herramienta de comprobación de evaluación de preparación para obtener un informe HTML, ver los resultados y tomar medidas. Debe descargar la herramienta y los archivos de soporte técnico. A continuación, ejecutala manualmente en cada dispositivo que quieras inscribir en Microsoft Managed Desktop.

Para cada comprobación, la herramienta mostrará uno de los tres resultados posibles:

| Resultado | Significado |
| ----- | ----- |
| Listo | No se requiere ninguna acción antes de completar la inscripción. |
| Advertencia | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. <br><br> Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo. |
| No preparado | **La inscripción producirá un** error si no se solucionan estos problemas. <br><br> Siga los pasos de la herramienta para resolverlos. |

## <a name="obtain-the-checker"></a>Obtener el control

Descargue el .zip archivo de https://aka.ms/mmddratoolv0.

> [!NOTE]
> El usuario que ejecuta la herramienta debe tener derechos de administrador local en el dispositivo donde la está ejecutando.

**Para ejecutar la herramienta:**

1. Copia el archivo .zip descargado en cada dispositivo que quieras comprobar.
2. Extraiga todos los archivos de la descarga comprimida.
3. Ejecute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Cuando aparezca el símbolo del sistema control de acceso de usuario, seleccione **Sí**. La herramienta se ejecuta y abre un informe en el explorador predeterminado.

También puedes descargar y extraer el archivo .zip a una ubicación compartida, acceder a **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** desde cada dispositivo. A continuación, ejecute localmente.

## <a name="checks"></a>Comprobaciones

La herramienta descargable comprueba estos elementos relacionados con el dispositivo y la red:

| Cheque | Descripción |
| ----- | ----- |
| Hardware | Los dispositivos deben cumplir requisitos de hardware específicos para trabajar con Microsoft Managed Desktop. Para obtener más información, consulta [Requisitos del dispositivo](../service-description/device-list.md). <br><br> Si el dispositivo falla alguna de las comprobaciones, no es compatible con Microsoft Managed Desktop. |
| Puntos de conexión de red | Los dispositivos pueden llegar a varios [puntos de conexión clave](network.md) para trabajar con Microsoft Managed Desktop. <br><br> Si la herramienta informa de **un resultado** no listo, consulte el informe detallado para averiguar qué puntos de conexión no eran accesibles. A continuación, ajusta el firewall u otra configuración de red para garantizar que se pueda llegar a esos puntos de conexión. |

### <a name="other-settings"></a>Otras opciones de configuración

| Configuración | Descripción |
| ----- | ----- |
| Enterprise Wi-Fi perfiles | Un **resultado de** asesoramiento significa que está usando algunos perfiles Wi-Fi que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, consulta [Implementar certificados y perfil de Wi-Fi/VPN](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile). |
| Perfiles DE LAN | Un **resultado de asesoramiento** significa que tiene LAN que necesitan certificados y perfiles para funcionar correctamente. Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md). |
| Perfiles de VPN | Un **resultado de aviso** significa que está usando una red privada virtual (VPN). Cree un perfil de VPN que implemente certificados integrados con Microsoft Intune. Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md). |
| Unidades asignadas | Un **resultado de aviso** significa que tiene algunas unidades asignadas, lo que no se recomienda. Para obtener más información, vea [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md). |
| Colas de impresión | Un **resultado de aviso** significa que tiene algunas colas de impresión pendientes, que no se recomiendan. Una solución es usar la impresión en la nube. Para obtener más información, vea [Prepare printing resources for Microsoft Managed Desktop](printing.md). |
| Proxies | Un **resultado de aviso** significa que tiene un servidor proxy en uso. Para obtener más información, consulte [Configuración de red para Escritorio administrado de Microsoft](network.md). |
