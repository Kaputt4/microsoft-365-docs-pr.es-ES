---
title: Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU
description: Obtenga información sobre los requisitos y capacidades de Microsoft Defender para endpoint para clientes del gobierno de ESTADOS UNIDOS disponibles
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 92e35fb75b26df6768860b4cb98b825086fa80d5
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61109808"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para endpoint para clientes del gobierno de Estados Unidos, integrado en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Defender para endpoint en Azure Commercial.

Esta oferta está disponible para clientes GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de capacidades para esta oferta.

> [!NOTE]
> Si es un cliente GCC que usa Defender para Endpoint en Commercial, consulte las páginas de documentación pública.

## <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft Defender para el punto de conexión para clientes del gobierno de ESTADOS UNIDOS requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 para GCC High|Microsoft 365 G5 para DOD|
|Microsoft 365 G5 Security GCC|Microsoft 365 G5 Security for GCC High|Microsoft 365 G5 Security for DOD|
|Microsoft Defender para endpoint: GCC|Microsoft Defender para endpoint for GCC High|Microsoft Defender para endpoint para DOD|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 para GCC High|Windows 10 Enterprise E5 para DOD|
|

### <a name="server-licensing"></a>Licencias de servidor

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender para endpoint server GCC|Microsoft Defender para Endpoint Server para GCC High|Microsoft Defender para Endpoint Server para DOD|
|Microsoft Defender para servidores|Microsoft Defender para servidores- Gobierno|Microsoft Defender para servidores- Gobierno|
|

## <a name="portal-urls"></a>Direcciones URL del portal

Las siguientes son las direcciones URL del portal de Microsoft Defender para puntos de conexión para clientes del Gobierno de ESTADOS UNIDOS:

<br />

****

|Tipo de cliente|Portal URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|<https://securitycenter.microsoft.us>|
|DoD|<https://securitycenter.microsoft.us>|
|
> [!NOTE]
> Si es un cliente GCC y en el proceso de pasar de Microsoft Defender para endpoint comercial a GCC, use para obtener acceso a los datos comerciales de https://transition.security.microsoft.com Microsoft Defender para endpoint.

## <a name="endpoint-versions"></a>Versiones de extremo

### <a name="standalone-os-versions"></a>Versiones del sistema operativo independiente

Se admiten las siguientes versiones del sistema operativo:

<br />

****

Versión del sistema operativo|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows 11|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10 versión 21H1 y versiones posteriores|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 20H2 (con [KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 2004 (con [KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 1909 (con [KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 1903 (con [KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 1809 (con [KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 1803 (con [KB4598245](https://support.microsoft.com/help/4598245) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 1709|![No.](images/svg/check-no.svg) <br /> Nota: No se admite|![Sí ](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> <br /> Nota: [En desuso,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)actualice|![No](images/svg/check-no.svg) <br /> Nota: No se admite
Windows 10, versión 1703 y versiones anteriores|![No.](images/svg/check-no.svg) <br /> Nota: No se admite|![No](images/svg/check-no.svg) <br /> Nota: No se admite|![No](images/svg/check-no.svg) <br /> Nota: No se admite
Windows Server 2022|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2019 (con [KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2016 (moderno) <sup>2</sup>|![Sí.](images/svg/check-yes.svg) <br /> Versión preliminar pública|![Sí](images/svg/check-yes.svg) <br /> Versión preliminar pública|![Sí](images/svg/check-yes.svg) <br /> Versión preliminar pública
Windows Server 2012 R2 (moderno) <sup>2</sup>|![Sí.](images/svg/check-yes.svg) <br /> Versión preliminar pública|![Sí](images/svg/check-yes.svg) <br /> Versión preliminar pública|![Sí](images/svg/check-yes.svg) <br /> Versión preliminar pública
Windows Server 2016 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 8.1 Enterprise (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 8 Pro (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Pro (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Linux|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
macOS|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Android|![No.](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo
iOS|![No.](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo
|

> [!NOTE]
> <sup>1</sup> La revisión debe implementarse antes de la incorporación de dispositivos para configurar Defender for Endpoint en el entorno correcto.
>
> <sup>2</sup> Obtenga información sobre la [solución moderna unificada para Windows 2016 y 2012 R2](configure-server-endpoints.md#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview). Si ya ha incorporado los servidores con MMA, siga las instrucciones que se proporcionan en [Migración](server-migration.md) de servidores para migrar a la nueva solución.
>
> <sup>3</sup> Cuando use [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) deberá elegir "Azure US Government" en "Azure Cloud" si usa el [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) asistente para la instalación [o](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)si usa una línea de comandos o un [script:](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1. <br /> La versión mínima compatible con MMA es 10.20.18029 (marzo de 2020).

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>Versiones del sistema operativo al usar Microsoft Defender para servidores

Las siguientes versiones del sistema operativo se admiten al [usar Microsoft Defender para servidores:](/azure/security-center/security-center-wdatp)

<br />

****

Versión del sistema operativo|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows Server 2022|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2019|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2016|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
|

## <a name="required-connectivity-settings"></a>Configuración de conectividad necesaria

Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Compruebe que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL o cree una regla de permitir específicamente para ellas.

Hoja de cálculo de la lista de dominios|Descripción
:-----|:-----
![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión.](images/mdatp-urls.png)|Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Para obtener más información, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

> [!NOTE]
> La hoja de cálculo también contiene direcciones URL comerciales, asegúrese de comprobar las pestañas "Us Gov".
>
> Al filtrar, busque los registros etiquetados como "US Gov" y su nube específica en la columna geography.

## <a name="api"></a>API

En lugar de los URI públicos enumerados en nuestra [documentación de la API,](apis-intro.md)deberá usar los siguientes URI:

<br />

****

|Tipo de extremo|GCC|GCC High & DoD|
|---|---|---|
|Inicio de sesión|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Defender para la API de punto de conexión|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|
|

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial

Defender for Endpoint for US Government customers doesn't have complete parity with the commercial offering. Aunque nuestro objetivo es ofrecer todas las funciones y características comerciales a nuestros clientes del Gobierno de Estados Unidos, aún no hay algunas funcionalidades disponibles que queremos destacar.

Estas son las diferencias conocidas:

<br />

****

|Nombre de la característica|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Evaluaciones de red|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Detección de redes|![Sí](images/svg/check-yes.svg)|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Filtrado de contenido web|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Integraciones: Microsoft Sentinel|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg) Alertas <br /> ![Sí](images/svg/check-yes.svg) Incidentes & datos sin procesar: en versión preliminar privada|![Sí](images/svg/check-yes.svg) Alertas <br /> ![Sí](images/svg/check-yes.svg) Incidentes & datos sin procesar: en versión preliminar privada|
|Integraciones: Microsoft Power Automate & Azure Logic Apps|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Expertos en amenazas de Microsoft|![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](images/svg/check-no.svg) En el trabajo pendiente de ingeniería|
