---
title: Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU
description: Obtenga información sobre los Microsoft Defender para punto de conexión para los requisitos y funcionalidades de los clientes del Gobierno de EE. UU. disponibles
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender para punto de conexión, endpoint, dod
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
ms.openlocfilehash: 55517599dabee5ee4304b3347f71bd53d8d9bfcc
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325757"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender para punto de conexión para clientes del Gobierno de los EE. UU

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender para punto de conexión para clientes del Gobierno de EE. UU., integrado en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Defender para punto de conexión en Azure Commercial.

Esta oferta está disponible para los clientes de GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de las funcionalidades de esta oferta.

> [!NOTE]
> Si es un cliente de GCC que usa Defender para punto de conexión en comercial, consulte las páginas de documentación pública.

## <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft Defender para punto de conexión para los clientes del Gobierno de EE. UU. requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 para GCC High|Microsoft 365 G5 para DOD|
|GCC de seguridad de Microsoft 365 G5|Seguridad de Microsoft 365 G5 para GCC High|Seguridad de Microsoft 365 G5 para DOD|
|Microsoft Defender para punto de conexión - GCC|Microsoft Defender para punto de conexión para GCC High|Microsoft Defender para punto de conexión para DOD|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 para GCC High|Windows 10 Enterprise E5 para DOD|

### <a name="server-licensing"></a>Licencias de servidor

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|GCC de Microsoft Defender para punto de conexión Server|Microsoft Defender para punto de conexión Server para GCC High|Microsoft Defender para punto de conexión Server for DOD|
|Microsoft Defender para servidores|Microsoft Defender para servidores: Administración pública|Microsoft Defender para servidores: Administración pública|

## <a name="portal-urls"></a>Direcciones URL del portal

A continuación se muestran las direcciones URL del portal de Microsoft Defender para punto de conexión para los clientes del gobierno de EE. UU.:

<br />

****

|Tipo de cliente|Portal URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|<https://security.microsoft.us>|
|DoD|<https://security.apps.mil>|

> [!NOTE]
> Si es cliente de GCC y está en proceso de pasar de Microsoft Defender para punto de conexión comercial a GCC, use https://transition.security.microsoft.com para acceder a sus datos comerciales Microsoft Defender para punto de conexión.

## <a name="endpoint-versions"></a>Versiones del punto de conexión

### <a name="standalone-os-versions"></a>Versiones independientes del sistema operativo

Se admiten las siguientes versiones del sistema operativo:

<br />

****

Versión del sistema operativo|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows 11|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 21H1 y posteriores|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 20H2 (con [KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 10, versión 2004 (con [KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-version-2004-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-version-2004-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-version-2004-end-of-servicing), actualice
Windows 10, versión 1909 (con [KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1909-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1909-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1909-end-of-servicing), actualice
Windows 10, versión 1903 (con [KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1903-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1903-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1903-end-of-servicing), actualice
Windows 10, versión 1809 (con [KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice
Windows 10, versión 1803 (con [KB4598245](https://support.microsoft.com/help/4598245) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice|![Sí](images/svg/check-yes.svg) <br /> Nota: [En desuso](/lifecycle/announcements/windows-10-1803-1809-end-of-servicing), actualice
Windows 10, versión 1709|![No.](images/svg/check-no.svg) <br /> Nota: No se admitirá|![Sí](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> <br /> Nota: [En desuso](/lifecycle/announcements/revised-end-of-service-windows-10-1709), actualice|![No](images/svg/check-no.svg) <br /> Nota: No se admitirá
Windows 10, versión 1703 y anteriores|![No.](images/svg/check-no.svg) <br /> Nota: No se admitirá|![No](images/svg/check-no.svg) <br /> Nota: No se admitirá|![No](images/svg/check-no.svg) <br /> Nota: No se admitirá
Windows Server 2022|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2019 (con [KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2016 (moderno) <sup>2</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 (moderno) <sup>2</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2016 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 8.1 Enterprise (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 8 Pro (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows 7 SP1 Pro (heredado) <sup>3</sup>|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Linux|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
macOS|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Android|![Sí.](images/svg/check-yes.svg) <br /> |![Sí](images/svg/check-yes.svg) <br /> |![Sí](images/svg/check-yes.svg) <br /> 
iOS|![Sí.](images/svg/check-yes.svg) <br /> |![Sí](images/svg/check-yes.svg) <br /> |![Sí](images/svg/check-yes.svg) <br /> 

> [!NOTE]
> <sup>1</sup> La revisión debe implementarse antes de la incorporación del dispositivo para configurar Defender para punto de conexión en el entorno correcto.
>
> <sup>2</sup> Obtenga información sobre la [solución moderna unificada para Windows 2016 y 2012 R2](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution). Si previamente ha incorporado los servidores mediante MMA, siga las instrucciones que se proporcionan en [Migración del servidor](server-migration.md) para migrar a la nueva solución.
>
> <sup>3</sup> Al usar [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) , deberá elegir "Azure US Government" en "Azure Cloud" si usa el [Asistente para la instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) o si usa una [línea de comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) o un [script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) : establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1. <br /> La versión mínima compatible con MMA es 10.20.18029 (marzo de 2020).

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>Versiones del sistema operativo al usar Microsoft Defender para servidores

Se admiten las siguientes versiones del sistema operativo cuando se usa [Microsoft Defender para servidores](/azure/security-center/security-center-wdatp):

<br />

****

Versión del sistema operativo|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows Server 2022|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2019|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2016|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2012 R2|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![Sí.](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)

## <a name="required-connectivity-settings"></a>Configuración de conectividad necesaria

Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Compruebe que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL, o cree una regla *de permiso* específicamente para ellas.

|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Microsoft Defender para punto de conexión lista de direcciones URL para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender para punto de conexión lista de direcciones URL de Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes de Gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Para obtener más información, consulte [Configuración del proxy de dispositivo y la conectividad a Internet](configure-proxy-internet.md).

> [!NOTE]
> La hoja de cálculo también contiene direcciones URL comerciales, asegúrese de comprobar las pestañas "US Gov".
>
> Al filtrar, busque los registros etiquetados como "US Gov" y su nube específica en la columna geography.

## <a name="api"></a>API

En lugar de los URI públicos que aparecen en la documentación de la [API](apis-intro.md), deberá usar los siguientes URI:

<br />

****

|Tipo de punto de conexión|GCC|GCC High & DoD|
|---|---|---|
|Inicio de sesión|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|API de Defender para punto de conexión|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial

Los clientes de Defender para punto de conexión para el gobierno de EE. UU. no tienen paridad completa con la oferta comercial. Aunque nuestro objetivo es ofrecer todas las características y funcionalidades comerciales a nuestros clientes del Gobierno de EE. UU., todavía no hay algunas funcionalidades disponibles que queremos resaltar.

Estas son las brechas conocidas:

<br />

****

|Nombre de la característica|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Informes: Estado del dispositivo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Informes: Filtrado de contenido web|![Yes](images/svg/check-yes.svg)|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Puntuación de seguridad de Microsoft|![Sí](images/svg/check-yes.svg) <sup>1</sup>|![No](images/svg/check-no.svg)|![No](images/svg/check-no.svg)|  
|Expertos en amenazas de Microsoft|![No](images/svg/check-no.svg)|![No](images/svg/check-no.svg)|![No](images/svg/check-no.svg)|  
> [!NOTE]
> <sup>1</sup> Aunque la Puntuación de seguridad de Microsoft está disponible para los clientes de GCC, hay algunas recomendaciones de seguridad que no están disponibles.


Estas son las características y las brechas conocidas de [Mobile Threat Defense (Microsoft Defender para punto de conexión en Android & iOS):](mtd.md)

<br />

****

|Nombre de la característica|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Protección web (Anti-Phishing e indicadores personalizados)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Protección contra malware (solo Android)|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|![No](images/svg/check-no.svg) En desarrollo|
|Detección de jailbreak (solo iOS)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Acceso condicional/inicio condicional|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Compatibilidad con MAM|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Controles de privacidad|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
|Administración de vulnerabilidades de Microsoft Defender (MDVM))|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|![Sí](images/svg/check-yes.svg)|
