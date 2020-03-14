---
title: Implementar características de seguridad de Windows 10 Enterprise
description: Proporciona instrucciones de alto nivel sobre los pasos necesarios para implementar características de seguridad de Windows 10 Enterprise en equipos PC como parte de Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, seguridad
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 5407370933c2a99781adf4ca58d3fa905328ed04
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633008"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Paso 5: implementar las características de seguridad de Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 proporciona características de seguridad para proteger a los usuarios de la empresa, detener ciberamenazas y evitar la pérdida de datos. 

Para obtener más información acerca de estas tecnologías, consulte:

* [Protección de identidad](https://docs.microsoft.com/windows/security/identity-protection/) : Obtenga más información sobre Windows Hello para empresas, el guardián de credenciales y el control de acceso.
* [Protección contra amenazas](https://docs.microsoft.com/windows/threat-protection/) : Obtenga información sobre la protección contra amenazas avanzada de Microsoft defender, una plataforma unificada para la protección preventiva, la detección tras infracción, la investigación automatizada y la respuesta.
* [Protección](https://docs.microsoft.com/windows/security/information-protection/) de la información: Obtenga información sobre BitLocker, Windows Information Protection y otras formas en que Windows 10 ayuda a proteger los datos empresariales. 

En este paso, se muestra cómo puede implementar, administrar, configurar y solucionar problemas mediante el uso de estas características de seguridad:

* [Antivirus de Windows Defender](#windows-defender-antivirus)
* [Protección contra vulnerabilidades de seguridad de Windows Defender](#windows-defender-exploit-guard)
* [Protección contra amenazas avanzada de Microsoft Defender](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Antivirus de Windows Defender
Antivirus de Windows Defender (AV) es una solución antimalware integrada en Windows 10. Proporciona administración de seguridad y antimalware para equipos de escritorio, equipos portátiles y servidores. Para obtener más información acerca de AV de Windows Defender, los requisitos mínimos y cómo puede administrar esta característica, consulta [antivirus de Windows Defender en Windows 10 y Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Si no usa Windows Defender AV como cliente principal de antivirus, o si también usa ATP de Microsoft defender, hay algunas consideraciones que debe tener en cuenta. Para obtener más información, consulte [compatibilidad con AV de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Implementación y administración
Para implementar y administrar AV de Windows Defender, siga las instrucciones que se indican a continuación:

* [Implementación, administración y reporting de AV de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Temas de referencia para las herramientas de administración y configuración](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configuración
Los usuarios pueden configurar una serie de características. Para obtener más información, consulte estos recursos:

* [Configurar las características de AV de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Temas de referencia para las herramientas de administración y configuración](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Para ayudar a comprender las opciones de configuración, consulte esta lista de todas las configuraciones (como se define en la configuración de la Directiva de grupo): [usar la configuración de directiva de grupo para configurar y administrar Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Puede usar la guía de evaluación de la [protección AV de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) para evaluar el nivel de protección y el impacto del AV de Windows Defender en su red. Esto también puede resultarle útil para crear una configuración inicial o como una "Guía de inicio rápido" y se actualiza periódicamente para proporcionar las recomendaciones más útiles para configurar y habilitar características con el fin de garantizar la máxima protección.

### <a name="reporting"></a>Reporting
Puede obtener informes mediante una herramienta de configuración, como Microsoft Endpoint Configuration Manager o Microsoft Intune. También puede obtener informes desde el cumplimiento de actualizaciones (OMS) o mediante el uso de registros de eventos de Windows en SIEM. Si tiene una licencia de ATP de Microsoft defender, también puede obtener información sobre las detecciones de AV de Windows Defender y realizar correcciones básicas. Para obtener más información, consulte estos recursos:
* [Implementación, administración y reporting de AV de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Informe sobre la protección antivirus de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Información general del portal ATP de Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solución de problemas
Para obtener información sobre cómo solucionar problemas básicos de los códigos de error y de evento, consulte [revisar los registros de eventos y los códigos de error para solucionar problemas con Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

También puede enviar problemas (como falsos positivos) mediante el sistema de envío de inteligencia en seguridad de Windows Defender. Para obtener información sobre cómo hacerlo, vea [Enviar problemas a Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Protección contra vulnerabilidades de seguridad de Windows Defender
La protección contra la vulnerabilidad de Windows Defender es un nuevo conjunto de capacidades de prevención de intrusiones de host para Windows 10. Para obtener más información sobre la protección contra vulnerabilidades de Windows Defender, los requisitos mínimos y cómo puede administrar esta característica, consulta [protección contra vulnerabilidades de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Implementación, administración y configuración
Para implementar, administrar y configurar la protección contra vulnerabilidades de Windows Defender, siga las instrucciones que se indican a continuación:
* [Protección contra vulnerabilidades](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Protección de superficie de ataques](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Protección de red](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Acceso controlado a carpetas](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Puede usar una serie de temas de evaluación para ayudar a evaluar el nivel de protección y el impacto de la protección contra vulnerabilidades de Windows Defender en la red. Esto también puede resultarle útil para crear una configuración inicial o como una "Guía de inicio rápido" y los temas y las instrucciones se actualizan periódicamente para proporcionar las recomendaciones más útiles para configurar y habilitar las características a fin de garantizar la máxima protección. Para obtener más información, [evalúa protección contra vulnerabilidades de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
Puede obtener informes mediante una herramienta de configuración, como Configuration Manager o Intune. También puede obtener informes al consumir registros de eventos de Windows en SIEM. Si tiene una licencia de ATP de Microsoft defender, también puede obtener información sobre las detecciones de AV de Windows Defender y realizar correcciones básicas. Para obtener más información, consulte estos recursos:
* [Ver los eventos de protección contra vulnerabilidad de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Información general del portal ATP de Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solución de problemas
Puede realizar problemas básicos o proporcionar a Microsoft de forma opcional archivos. cab y enviar problemas (como falsos positivos) mediante el sistema de envío de inteligencia en seguridad de Windows Defender. Para obtener información sobre cómo hacerlo, vea [Enviar problemas a Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Protección contra amenazas avanzada de Microsoft Defender
Microsoft defender ATP, que solo está disponible con el plan 365 E5 de Microsoft, es un servicio de seguridad que permite a los clientes empresariales detectar, investigar y responder a amenazas avanzadas en sus redes. Para obtener más información acerca de ATP de Microsoft defender, los requisitos mínimos y cómo puede administrar esta característica, consulte:

* [ATP de Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisitos mínimos](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Implementación, administración y configuración
Para implementar ATP de Microsoft defender, tendrá que asegurarse de que tiene la licencia de Windows correcta. Después de comprobar que tiene la licencia correcta, deberá decidir la ubicación geográfica por la que se almacenarán los datos. A continuación, puede iniciar la incorporación de los puntos de conexión con el servicio.

Para obtener más información sobre estos pasos, consulte estos temas principales: 

* [Validar el aprovisionamiento y la configuración completa de licencias](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Almacenamiento de datos y privacidad](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Extremos incorporados y acceso a la instalación](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Detectar, investigar, responder
Después de incorporar correctamente los puntos de conexión al servicio, puede empezar a investigar las alertas de los distintos paneles. Una vez que haya investigado las alertas, puede realizar acciones de respuesta en las alertas. 

Para obtener más información sobre cómo hacerlo, consulte:
* [Información general del portal ATP de Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)
* [Usar el portal ATP de Microsoft defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Realizar acciones de respuesta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integración con otros productos y herramientas
ATP de Microsoft defender se integra y admite distintos productos y herramientas para ampliar sus capacidades de seguridad. 

Para obtener más información sobre las herramientas y otros productos, consulta:
* [Herramientas de SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Crear alertas personalizadas](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Usar las API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Crear informes de Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Solución de problemas
Es posible que se produzcan problemas durante la incorporación o al usar el producto. Para obtener más información sobre cómo solucionar problemas, consulte:
* [Solución de problemas de incorporación](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Solución de problemas de ATP de Microsoft defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de la infraestructura de Windows 10 Enterprise](windows10-exit-criteria.md)
