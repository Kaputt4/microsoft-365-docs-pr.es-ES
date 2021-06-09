---
title: Incorporar versiones anteriores de Windows en Microsoft Defender para endpoint
description: Incorporar versiones anteriores compatibles de Windows dispositivos para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844435"
---
# <a name="onboard-previous-versions-of-windows"></a>Incorporar versiones anteriores de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>¿Desea experimentar Defender for Endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

Defender for Endpoint amplía la compatibilidad para incluir sistemas operativos de nivel inferior, lo que proporciona capacidades avanzadas de detección de ataques e investigación en versiones Windows compatibles.

Para incorporar puntos de conexión Windows cliente a Defender for Endpoint, deberás:
- Configure y actualice System Center Endpoint Protection clientes.
- Instale y configure Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Defender for Endpoint como se indica a continuación.

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio. Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurar y actualizar System Center Endpoint Protection clientes
> [!IMPORTANT]
> Este paso solo es necesario si la organización usa System Center Endpoint Protection (SCEP).

Defender for Endpoint se integra con System Center Endpoint Protection para proporcionar visibilidad a las detecciones de malware y detener la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. 

Se requieren los siguientes pasos para habilitar esta integración: 
- Instalar la actualización de la plataforma antimalware de enero de [2017 para Endpoint Protection cliente](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Configurar la pertenencia del servicio de protección en la nube del cliente SCEP a la **configuración** Avanzada
- Configure la red para permitir conexiones a la Antivirus de Microsoft Defender nube. Para obtener más información, consulte [Allow connections to the Antivirus de Microsoft Defender cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Microsoft Defender para endpoint

### <a name="before-you-begin"></a>Antes de empezar
Revise los siguientes detalles para comprobar los requisitos mínimos del sistema:
- Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Solo se aplica Windows 7 SP1 Enterprise y Windows 7 SP1 Pro. 

- Instalar la actualización [para la experiencia del cliente y telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Solo se aplica Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.
    > No instales .NET Framework 4.0.x, ya que anulará la instalación anterior.

- Cumpla los requisitos mínimos del sistema del agente de Azure Log Analytics. Para obtener más información, vea [Recopilar datos de equipos de su entorno con Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).



1. Descargue el archivo de instalación del agente: Windows agente de [64](https://go.microsoft.com/fwlink/?LinkId=828603) bits o Windows agente de [32 bits](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Obtenga el identificador del área de trabajo:
   - En el panel de navegación Defender para endpoint, **seleccione Configuración > Administración de dispositivos > incorporación**
   - Seleccione **Windows 7 SP1 y 8.1** como sistema operativo
   - Copiar el identificador del área de trabajo y la clave del área de trabajo

3. Con el identificador de área de trabajo y la clave Área de trabajo, elija cualquiera de los siguientes métodos de instalación para instalar el agente:
    - [Instale manualmente el agente mediante el programa de instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      En la **página Opciones de configuración del** agente, seleccione Conectar el agente a Azure Log Analytics **(OMS)**
    - [Instale el agente mediante la línea de comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure el agente mediante un script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

4. Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.

Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurar las opciones del proxy y de conectividad a Internet
 
- Cada Windows punto de conexión debe poder conectarse a Internet mediante HTTPS. Esta conexión puede ser directa, mediante un proxy o a través de la puerta [de enlace OMS](/azure/log-analytics/log-analytics-oms-gateway).
- Si un proxy o firewall bloquea todo el tráfico de forma predeterminada y permite solo dominios específicos a través o el examen HTTPS (inspección SSL) está habilitado, asegúrese de habilitar el acceso a las direcciones URL del servicio [defender](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)para puntos de conexión .

## <a name="offboard-client-endpoints"></a>Extremos de cliente offboard
To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace. Después de salir del agente, el punto de conexión ya no enviará datos del sensor a Defender para Endpoint. 

> ¿Desea experimentar Defender for Endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).
