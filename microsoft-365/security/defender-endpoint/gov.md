---
title: Microsoft Defender para el punto de conexión para clientes del gobierno de ESTADOS UNIDOS
description: Obtenga información sobre los requisitos y capacidades de Microsoft Defender para endpoint para clientes del gobierno de ESTADOS UNIDOS disponibles
keywords: government, gcc, high, requirements, capabilities, defender, defender atp, mdatp, endpoint, dod
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
ms.openlocfilehash: 059ff9ca6f0c93c6adbac3b1d552cbedcf308759
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222712"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender para el punto de conexión para clientes del gobierno de ESTADOS UNIDOS

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para endpoint para clientes del gobierno de Estados Unidos, integrado en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Defender para endpoint en Azure Commercial.

Esta oferta está disponible para los clientes de GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de capacidades para esta oferta.

> [!NOTE]
> Si es un cliente de GCC que usa Defender for Endpoint in Commercial, consulte las páginas de documentación pública.

## <a name="licensing-requirements"></a>Requisitos de licencia
Microsoft Defender para el punto de conexión para clientes del gobierno de ESTADOS UNIDOS requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 para GCC High | Windows 10 Enterprise E5 para DOD
| | Microsoft 365 E5 para GCC High | Microsoft 365 G5 para DOD
| | Seguridad de Microsoft 365 G5 para GCC High | Seguridad de Microsoft 365 G5 para DOD
Microsoft Defender para endpoint : GCC | Microsoft Defender para endpoint para GCC High | Microsoft Defender para endpoint para DOD

### <a name="server-licensing"></a>Licencias de servidor
GCC | GCC High | DoD
:---|:---|:---
GCC de Microsoft Defender para Endpoint Server | Microsoft Defender para Endpoint Server para GCC High | Microsoft Defender para Endpoint Server para DOD
Azure Defender para servidores | Azure Defender para servidores- Gobierno | Azure Defender para servidores- Gobierno

<br>

## <a name="portal-urls"></a>Direcciones URL del portal
Las siguientes son las direcciones URL del portal de Microsoft Defender para puntos de conexión para clientes del Gobierno de ESTADOS UNIDOS:

Tipo de cliente | Portal URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>Versiones de extremo

### <a name="standalone-os-versions"></a>Versiones del sistema operativo independiente
Se admiten las siguientes versiones del sistema operativo:

Versión del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, versión 20H2 (con [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 2004 (con [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1909 (con [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1903 (con [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1809 (con [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1803 (con [KB4598245](https://support.microsoft.com/help/4598245)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 10, versión 1709 | ![No](images/svg/check-no.svg)<br>Nota: No se admite | ![Sí ](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147)<br>Nota: [En desuso,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)actualice | ![No](images/svg/check-no.svg)<br>Nota: No se admite
Windows 10, versión 1703 y versiones anteriores | ![No](images/svg/check-no.svg)<br>Nota: No se admite | ![No](images/svg/check-no.svg)<br>Nota: No se admite | ![No](images/svg/check-no.svg)<br>Nota: No se admite
Windows Server 2019 (con [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2016 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 8 Pro | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Linux | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando
macOS | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando
Android | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
iOS | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería

> [!NOTE]
> Cuando se especifica una revisión, debe implementarse antes de la incorporación del dispositivo para configurar Defender for Endpoint en el entorno correcto.

> [!NOTE]
> ¿Intenta incorporar dispositivos Windows anteriores a Windows 10 o Windows Server 2019 con [Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Deberá elegir "Azure US Government" en "Azure Cloud" si usa el [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) asistente para la instalación [o](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)si usa una línea de comandos o un [script:](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versiones del sistema operativo al usar Azure Defender para servidores
Las siguientes versiones del sistema operativo se admiten al [usar Azure Defender para servidores:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

Versión del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2016 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)

<br>

## <a name="required-connectivity-settings"></a>Configuración de conectividad necesaria
Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Compruebe que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL o cree una regla de permitir específicamente para ellas.

Hoja de cálculo de la lista de dominios | Descripción
:-----|:-----
![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/> | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <br><br>[Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Para obtener más información, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

> [!NOTE]
> La hoja de cálculo también contiene direcciones URL comerciales, asegúrese de comprobar las pestañas "Us Gov".
> 
> Al filtrar, busque los registros etiquetados como "US Gov" y su nube específica en la columna geography.

### <a name="service-backend-ip-ranges"></a>Intervalos IP de back-end de servicio

Si los dispositivos de red no admiten reglas basadas en DNS, usa intervalos IP en su lugar.

Defender for Endpoint for US Government customers se basa en el entorno de Azure US Government, implementado en las siguientes regiones:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Puede encontrar los intervalos IP de Azure en [Intervalos IP](https://www.microsoft.com/download/details.aspx?id=57063)de Azure y etiquetas de servicio : Us Government Cloud .

> [!NOTE]
> Como solución basada en la nube, los intervalos de direcciones IP pueden cambiar. Se recomienda pasar a reglas basadas en DNS.

<br>

## <a name="api"></a>API
En lugar de los URI públicos enumerados en nuestra [documentación de la API,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)deberá usar los siguientes URI:

Tipo de extremo | GCC | GCC High & DoD
:---|:---|:---
Inicio de sesión | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender para la API de punto de conexión | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial
Defender for Endpoint for US Government customers doesn't have complete parity with the commercial offering. Aunque nuestro objetivo es ofrecer todas las funciones y características comerciales a nuestros clientes del Gobierno de Estados Unidos, aún no hay algunas funcionalidades disponibles que queremos destacar.

Estas son las diferencias conocidas a partir de marzo de 2021:

Nombre de la característica | GCC | GCC High | DoD
:---|:---|:---|:---
Investigación y corrección automatizadas: respuesta en directo | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Investigación y corrección automatizadas: respuesta a alertas de Office 365 | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Notificaciones de correo electrónico | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Laboratorio de evaluación | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Administración y API: informe de estado y cumplimiento de dispositivos | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Administración y API: integración con productos de terceros | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando | ![No](images/svg/check-no.svg) Implementando
Administración y API: API de streaming | ![Sí](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Administración y API: informe de protección contra amenazas | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Administración de amenazas y vulnerabilidades. | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Análisis de amenazas | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Filtrado de contenido web | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Azure Sentinel | ![Sí](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Cloud App Security | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Integraciones: Administrador de cumplimiento de Microsoft | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Integraciones: Microsoft Defender para la identidad | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Integraciones: Microsoft Defender para Office 365 | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Integraciones: DLP de punto de conexión de Microsoft | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
Integraciones: Microsoft Intune | ![Sí](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Microsoft Power Automate & Azure Logic Apps | ![Sí](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) En desarrollo | ![No](images/svg/check-no.svg) En desarrollo
Integraciones: Skype Empresarial / Teams | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg) | ![Sí](images/svg/check-yes.svg)
Expertos en amenazas de Microsoft | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería | ![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería
