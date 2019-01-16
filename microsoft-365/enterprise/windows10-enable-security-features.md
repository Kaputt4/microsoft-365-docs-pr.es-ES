---
title: Implementar las características de seguridad de Windows 10 Enterprise
description: Proporciona una orientación de alto nivel en los pasos que necesarios para implementar Windows 10 Enterprise en los equipos como parte de Microsoft 365 Enterprise.
keywords: Seguridad de Microsoft 365, 365 Enterprise de Microsoft, Microsoft 365 documentación, Windows 10 Enterprise,
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871799"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Paso 5: Implementar las características de seguridad de Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

10 de Windows proporciona características para ayudar a proteger contra amenazas, ayuda seguro de los dispositivos y ayuda en el control de acceso. 

Para obtener más información acerca de estas tecnologías, consulte:
* [Protección de acceso](https://docs.microsoft.com/windows/access-protection/) : Obtenga información sobre access control, S/MIME, certificados digitales, Guard de credenciales, Control de cuentas de usuario, virtual tarjetas inteligentes, Windows Hello para profesionales, Firewall de Windows con seguridad avanzada etc.
* [Seguridad de los dispositivos](https://docs.microsoft.com/windows/device-security/) - incluye AppLocker, BitLocker, protección del dispositivo y módulo de plataforma segura
* [Protección contra amenazas](https://docs.microsoft.com/windows/threat-protection/) - incluye centro de seguridad de Windows Defender, la protección de amenaza avanzada de Windows Defender, Windows Defender Antivirus, Guard de aplicación de Windows Defender, Windows Defender inteligentes pantalla y protección de la información de Windows

En este paso se muestra cómo implementar, administrar, configurar y solucionar problemas de uso de estas características de seguridad:

* [Antivirus de Windows Defender](#windows-defender-antivirus)
* [Protección contra vulnerabilidades de seguridad de Windows Defender](#windows-defender-exploit-guard)
* [Protección contra amenazas avanzada de Windows Defender](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Antivirus de Windows Defender
Windows Defender Antivirus (AV) es una solución antimalware que se basa en Windows 10. Proporciona seguridad y administración de antimalware para escritorios, equipos portátiles y servidores. Para obtener más información acerca de Windows Defender AV, los requisitos mínimos y cómo pueden administrar esta característica, vea [Windows Defender Antivirus en 10 de Windows y Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Si no se usa Windows Defender AV como su cliente antivirus principal o, si también está usando Windows Defender ATP, hay algunas consideraciones debe tener en cuenta. Para obtener más información, vea [compatibilidad de Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Implementación y administración
Para implementar y administrar Windows Defender AV, siga las instrucciones aquí:

* [Implementar, administrar e informar sobre Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Temas de referencia para las herramientas de administración y configuración](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configuración
Los usuarios pueden configurar un número de características. Para obtener más información, consulte estos recursos:

* [Configurar las características de Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Temas de referencia para las herramientas de administración y configuración](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Para ayudar a comprender las opciones de configuración, consulte esta lista de todas las configuraciones (como se define por su configuración de directiva de grupo): [configuración de usar Directiva de grupo para configurar y administrar Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Puede usar la [protección de Windows Defender AV Guía de evaluación](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) para ayudar a evaluar el impacto de Windows Defender AV en la red y el nivel de protección. Esto también puede ser útil en la creación de una configuración inicial o como una guía de inicio rápido de' ' y se actualiza con regularidad para proporcionar las recomendaciones más útiles para configurar y habilitar las características garantizar la máxima protección.

### <a name="reporting"></a>Informes
Puede obtener informes mediante una herramienta de configuración, como System Center Configuration Manager o Microsoft Intune. También puede obtener informes de cumplimiento de normas de actualización (OMS) o por consumo de los registros de eventos de Windows en su SIEM. Si tiene una licencia para Windows Defender ATP, también puede obtener informes de detecciones de Windows Defender AV y realizar la corrección básica. Para obtener más información, consulte estos recursos:
* [Implementar, administrar e informar sobre Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Informar sobre protección de Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Información general del portal de Windows Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solución de problemas
Para obtener información sobre solución de problemas básicos de los códigos de error y eventos, vea [los registros de eventos de revisión y los códigos de error para solucionar problemas con Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

También puede enviar problemas (como falsos positivos) mediante el sistema de envío de inteligencia de seguridad de Windows Defender. Para obtener más información, vea [problemas de envío a Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Protección contra vulnerabilidades de seguridad de Windows Defender
Windows Defender aprovechan Guard es un nuevo conjunto de capacidades de prevención de intrusiones de host para Windows 10. Para obtener más información acerca de Windows Defender aprovechan Guard, los requisitos mínimos y cómo pueden administrar esta característica, vea [Windows Defender aprovechan Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Implementación, administración y configuración
Para implementar, administrar y configurar a Windows Defender aprovechan Guard, siga las instrucciones aquí:
* [Protección de vulnerabilidad](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Protección de superficie de ataque](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Protección de la red](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Controla el acceso a la carpeta](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Puede usar una serie de temas de evaluación para ayudar a evaluar el impacto de Windows Defender aprovechan Guard en la red y el nivel de protección. También puede ser útil en la creación de una configuración inicial o como una guía de inicio rápido de' ' y los temas y las instrucciones se actualizan con regularidad para proporcionar las recomendaciones más útiles para configurar y habilitar las características garantizar la máxima protección. Para obtener más información, [Evaluar Windows Defender aprovechan Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Informes
Puede obtener informes mediante una herramienta de configuración, como System Center Configuration Manager o Intune. También puede obtener informes por consumo de los registros de eventos de Windows en su SIEM. Si tiene una licencia para Windows Defender ATP, también puede obtener informes de detecciones de Windows Defender AV y realizar la corrección básica. Para obtener más información, consulte estos recursos:
* [Visualización de eventos de Windows Defender aprovechan Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Información general del portal de Windows Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solución de problemas
Puede realizar los problemas básicos o, opcionalmente, proporcionar a Microsoft con los archivos .cab y enviar problemas (como falsos positivos) mediante el sistema de envío de inteligencia de seguridad de Windows Defender. Para obtener más información, vea [problemas de envío a Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Protección contra amenazas avanzada de Windows Defender
Windows Defender ATP, sólo está disponible con el plan de Microsoft 365 Enterprise E5, es un servicio de seguridad que permite a los clientes de empresa detectar, investigar y responder a las amenazas avanzadas en sus redes. Para obtener más información acerca de Windows Defender ATP, los requisitos mínimos y cómo pueden administrar esta característica, vea:

* [ATP de Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisitos mínimos](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Implementación, administración y configuración
Para implementar Windows Defender ATP, debe asegurarse de que tiene el derecho de licencia de Windows. Después de comprobar que dispone de la licencia adecuada, debe decidir la ubicación geográfica de donde se almacenarán los datos. Después, puede iniciar incorporación extremos para el servicio.

Para obtener más detalles sobre estos pasos, vea estos temas principales: 

* [Validar el aprovisionamiento de licencia y completar el conjunto de copia de seguridad](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Privacidad y almacenamiento de datos](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Extremos incorporados y el acceso del programa de instalación](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Se detectan, investigar, responder
Después de la incorporación de redes correctamente los extremos para el servicio, puede iniciar investigar las alertas de los diversos paneles. Una vez que haya investigarse alertas, puede realizar acciones de respuesta a las alertas. 

Para obtener más información acerca de cómo hacer esto, vea:
* [Información general del portal de Windows Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)
* [Usar el portal de Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Realizar acciones de respuesta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrar con otros productos y herramientas
Windows Defender ATP se integra y es compatible con varios otros productos y herramientas para ampliar su capacidad de seguridad. 

Para obtener más información sobre las herramientas y otros productos, consulte:
* [Herramientas SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Crear alertas personalizadas](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Usar las API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Crear informes de Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Solución de problemas
Pueden surgir problemas durante la incorporación o durante el uso del producto. Para obtener más información acerca de cómo resolver problemas, vea:
* [Solución de problemas de incorporación](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Solución de problemas de Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de Enterprise del 10 de Windows](windows10-exit-criteria.md)
