---
title: Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU.
description: Obtenga información sobre los requisitos y capacidades de Microsoft Defender para endpoint para clientes del gobierno de EE. UU. disponibles
keywords: gobierno, gcc, alto, requisitos, capacidades, defensor, Microsoft Defender for Endpoint, punto de conexión, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572674"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU.

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint para clientes gubernamentales de EE. UU., integrado en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Defender for Endpoint en Azure Commercial.

Esta oferta está disponible para clientes de GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de capacidades para esta oferta.

> [!NOTE]
> Si usted es un cliente GCC que usa Defender for Endpoint in Commercial, consulte las páginas de documentación pública.

## <a name="licensing-requirements"></a>Requisitos de licencias
Microsoft Defender for Endpoint para clientes gubernamentales de EE. UU. requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 para GCC High | Windows 10 Enterprise E5 para dod
| | Microsoft 365 E5 para GCC High | Microsoft 365 G5 para dod
| | Microsoft 365 Seguridad G5 para GCC High | Microsoft 365 Seguridad G5 para el Departamento de Dod
Microsoft Defender para endpoint - GCC | Microsoft Defender para endpoint para GCC High | Microsoft Defender para endpoint para DOD

### <a name="server-licensing"></a>Licencias de servidor
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender para Endpoint Server GCC | Microsoft Defender para Endpoint Server para GCC High | Microsoft Defender para Endpoint Server para DOD
Azure Defender para servidores | Azure Defender para servidores - Gobierno | Azure Defender para servidores - Gobierno

<br />

## <a name="portal-urls"></a>URL del portal
A continuación se presentan las direcciones URL del portal microsoft defender for endpoint para clientes gubernamentales de EE. UU.:

Tipo de cliente | Portal URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Versiones de punto final

### <a name="standalone-os-versions"></a>Versiones independientes del sistema operativo
Se admiten las siguientes versiones del sistema operativo:

Versión del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, versión 20H2 (con [KB4586853)](https://support.microsoft.com/help/4586853) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 2004 (con [KB4586853)](https://support.microsoft.com/help/4586853) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1909 (con [KB4586819)](https://support.microsoft.com/help/4586819) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1903 (con [KB4586819)](https://support.microsoft.com/help/4586819) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1809 (con [KB4586839)](https://support.microsoft.com/help/4586839) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1803 (con [KB4598245)](https://support.microsoft.com/help/4598245) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1709 | ![No](images/svg/check-no.svg)<br />Nota: No se admitirá | ![Sí ](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147)<br />Nota: [En desuso,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)actualice | ![No](images/svg/check-no.svg)<br />Nota: No se admitirá
Windows 10, versión 1703 y anteriores | ![No](images/svg/check-no.svg)<br />Nota: No se admitirá | ![No](images/svg/check-no.svg)<br />Nota: No se admitirá | ![No](images/svg/check-no.svg)<br />Nota: No se admitirá
Windows Servidor 2019 (con [KB4586839)](https://support.microsoft.com/help/4586839) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2016 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 8 Pro | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 7 ENTERPRISE SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 7 Pro SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Linux | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
macOS | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Android | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería
iOS | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería

> [!NOTE]
> Cuando se especifica una revisión, se debe implementar antes de la incorporación del dispositivo para configurar Defender para el punto de conexión al entorno correcto.

> [!NOTE]
> ¿Intenta incorporar Windows dispositivos anteriores a Windows 10 o Windows Server 2019 mediante [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)? Deberá elegir "Azure US Government" en "Azure Cloud" si usa el [asistente de instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)o si usa una línea de [comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) o un [script,](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versiones del sistema operativo cuando se usa Azure Defender para servidores
Se admiten las siguientes versiones del sistema operativo al usar [Azure Defender para servidores:](/azure/security-center/security-center-wdatp)

Versión del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Windows Server 2016 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Configuración de conectividad necesaria
Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.

La siguiente hoja de cálculo descargable enumera los servicios y sus DIRECCIONES URL asociadas a las que debe poder conectarse la red. Compruebe que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL o creen una regla *de permiso* específicamente para ellas.

Lista de hojas de cálculo de dominios | Descripción
:-----|:-----
![Imagen del pulgar para la hoja de cálculo de direcciones URL de Microsoft Defender para endpoints](images/mdatp-urls.png)<br/> | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <br /><br />[Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Para obtener más información, consulte [Configurar la configuración de proxy de dispositivo y conectividad a Internet.](configure-proxy-internet.md)

> [!NOTE]
> La hoja de cálculo también contiene URL comerciales, asegúrese de revisar las pestañas "Gobierno de EE. UU.".
> 
> Al filtrar, busque los registros etiquetados como "Gov de EE. UU." y su nube específica en la columna geography.

### <a name="service-backend-ip-ranges"></a>Rangos ip de back-end de servicio

Si los dispositivos de red no admiten reglas basadas en DNS, utilice intervalos IP en su lugar.

Defender para clientes de Endpoint for US Government se crea en el entorno de Azure US Government, implementado en las siguientes regiones:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Puede encontrar los intervalos de IP de Azure en [Intervalos de IP de Azure y etiquetas de servicio : Nube de gobierno de EE. UU.](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Como solución basada en la nube, los intervalos de direcciones IP pueden cambiar. Se recomienda pasar a reglas basadas en DNS.

<br />

## <a name="api"></a>API
En lugar de los URI públicos enumerados en nuestra [documentación de la API,](apis-intro.md)deberá usar las siguientes URI:

Tipo de punto de conexión | GCC | GCC Departamento de Alto &
:---|:---|:---
Inicio de sesión | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defensor de endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial
Defender for Endpoint para clientes del gobierno de EE. UU. no tiene una paridad completa con la oferta comercial. Si bien nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a nuestros clientes del Gobierno de ee. UU., hay algunas capacidades que aún no están disponibles que queremos destacar.

Estas son las brechas conocidas:

Nombre de la característica | GCC | GCC High | DoD
:---|:---|:---|:---
Administración y API: API de streaming | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Filtrado de contenido web | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Azure Sentinel | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) Alertas <br /> ![No](images/svg/check-no.svg) Incidentes & datos sin procesar: En desarrollo | ![Sí](images/svg/check-yes.svg) Alertas <br /> ![No](images/svg/check-no.svg) Incidentes & datos sin procesar: En desarrollo
Integraciones: Microsoft Cloud App Security | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Compliance Manager | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Defender para la identidad | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Endpoint DLP | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Intune | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Integraciones: Microsoft Power Automate & Azure Logic Apps | ![Sí](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Expertos en amenazas de Microsoft | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería | ![No](images/svg/check-no.svg) En el atraso de ingeniería
