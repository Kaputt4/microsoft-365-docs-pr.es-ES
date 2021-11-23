---
title: Información general sobre Microsoft Defender para el plan 1 de punto de conexión
description: Obtenga información general sobre Defender for Endpoint Plan 1. Obtenga información sobre las características y capacidades incluidas en esta suscripción de protección de extremo.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 11/23/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: b21c72c44f19e4f9aede5a72c4860cbd6fac1c5c
ms.sourcegitcommit: b19e54b3888a0b07d08dbd23172daec303c7c95b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2021
ms.locfileid: "61152399"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1"></a>Información general sobre Microsoft Defender para el plan 1 de punto de conexión

> [!TIP]
> Si tiene Microsoft 365 E3 O A3 pero no Microsoft 365 E5 o A5, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) para registrarse en el programa de vista previa.

Microsoft Defender para endpoint es una plataforma de seguridad de extremo empresarial diseñada para ayudar a organizaciones como la de usted a prevenir, detectar, investigar y responder a amenazas avanzadas. Nos complace anunciar que Defender for Endpoint ya está disponible en dos planes: 

- **Defender for Endpoint Plan 1**, descrito en este artículo; y 
- **[Defender for Endpoint Plan 2](microsoft-defender-endpoint.md)**, generalmente disponible y anteriormente conocido como [Defender para Endpoint](microsoft-defender-endpoint.md).

Los cuadros verdes de la siguiente imagen muestran lo que se incluye en Defender for Endpoint Plan 1:

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Diagrama de Defender for Endpoint Plan 1":::

Use esta guía para:

- [Obtenga información general sobre lo que se incluye en defender para el plan de extremo 1](#defender-for-endpoint-plan-1-capabilities)
- [Comparar los planes 1 y 2 de Defender para punto de conexión](defender-endpoint-plan-1-2.md)
- [Obtenga información sobre cómo configurar y configurar Defender for Endpoint Plan 1](mde-p1-setup-configuration.md)
- [Introducción al portal de Microsoft 365 Defender, donde puede ver incidentes y alertas, administrar dispositivos y usar informes sobre amenazas detectadas](mde-plan1-getting-started.md)
- [Obtener información general sobre el mantenimiento y las operaciones](mde-p1-maintenance-operations.md)

> [!TIP]
> [Obtenga más información sobre las diferencias entre Defender for Endpoint Plan 1 y Plan 2](defender-endpoint-plan-1-2.md).

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Capacidades de Defender for Endpoint Plan 1

Defender for Endpoint Plan 1 incluye las siguientes funcionalidades:

- **[Protección de última generación](#next-generation-protection)** que incluye protección antivirus y antimalware sólida y líder del sector
- **[Acciones de respuesta manuales,](#manual-response-actions)** como enviar un archivo a la cuarentena, que el equipo de seguridad puede llevar a cabo en dispositivos o archivos cuando se detectan amenazas
- **[Capacidades de reducción de superficie de](#attack-surface-reduction)** ataque que endurecen los dispositivos, evitan ataques de día cero y ofrecen control granular sobre el acceso y los comportamientos de los puntos de conexión
- **[Configuración y administración centralizadas con](#centralized-management)** el portal Microsoft 365 Defender e integración con Microsoft Endpoint Manager
- **[Protección para una variedad de plataformas,](#cross-platform-support)** incluidos dispositivos Windows, macOS, iOS y Android

En las secciones siguientes se proporcionan más detalles sobre estas funcionalidades. 

## <a name="next-generation-protection"></a>Protección de última generación

La protección de última generación incluye protección antivirus sólida y antimalware. Con la protección de última generación, obtiene: 

- Protección antivirus basada en comportamiento, heurística y en tiempo real 
- Protección entregada en la nube, que incluye detección casi instantánea y bloqueo de amenazas nuevas y emergentes 
- Protección dedicada y actualizaciones de productos, incluidas las actualizaciones relacionadas con Antivirus de Microsoft Defender 

Para obtener más información, vea [Información general sobre la protección de próxima generación](next-generation-protection.md).

## <a name="manual-response-actions"></a>Acciones de respuesta manuales

Las acciones de respuesta manual son acciones que el equipo de seguridad puede realizar cuando se detectan amenazas en puntos de conexión o en archivos. Defender for Endpoint incluye determinadas [acciones de respuesta manuales](respond-machine-alerts.md) que se pueden realizar en un dispositivo que se detecta como potencialmente en peligro o que tiene contenido sospechoso. También puede ejecutar acciones [de respuesta en archivos](respond-file-alerts.md) detectados como amenazas. En la tabla siguiente se resumen las acciones de respuesta manuales que están disponibles en Defender para el plan de extremo 1. <br/><br/>

| Archivo/dispositivo | Acción | Descripción |
|:---|:---|:---|
| Dispositivo | Ejecutar examen de antivirus | Inicia un examen antivirus. Si se detecta alguna amenaza en el dispositivo, estas amenazas suelen tratarse durante un examen antivirus. |
| Dispositivo | Aislar el dispositivo | Desconecta un dispositivo de la red de su organización mientras conserva la conectividad con Defender para endpoint. Esta acción te permite supervisar el dispositivo y realizar más acciones si es necesario. |
| Archivo | Detener y poner en cuarentena un archivo |Impide que los procesos se ejecuten y ponga en cuarentena los archivos asociados. |
| Archivo | Agregar un indicador para bloquear o permitir un archivo | Los indicadores de bloqueo impiden que los archivos ejecutables portátiles se lean, escriban o ejecuten en dispositivos. <p>Los indicadores allow impiden que los archivos se bloqueen o corrijan. |

Para obtener más información, consulte los artículos siguientes:

- [Realizar acciones de respuesta en dispositivos](respond-machine-alerts.md) 
- [Realizar acciones de respuesta en archivos](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

Las superficies de ataque de la organización son todos los lugares donde eres vulnerable a los ataques cibernéticos. Con Defender for Endpoint Plan 1, puedes reducir las superficies de ataque protegiendo los dispositivos y aplicaciones que usa tu organización. Las capacidades de reducción de superficie de ataque que se incluyen en Defender para el plan de extremo 1 se describen en las secciones siguientes.

- [Reglas de la reducción de la superficie expuesta a ataques](#attack-surface-reduction-rules)
- [Mitigación de ransomware](#ransomware-mitigation)
- [Control de dispositivos](#device-control)
- [Protección web](#web-protection)
- [Protección de red](#web-protection)
- [Firewall de red](#network-firewall)
- [Control de la aplicación](#application-control)

Para obtener más información sobre las capacidades de reducción de superficie de ataque en Defender for Endpoint, consulta [Overview of attack surface reduction](overview-attack-surface-reduction.md).

### <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

Las reglas de reducción de superficie de ataque se aplican a determinados comportamientos de software que se consideran riesgosos. Estos comportamientos incluyen:

- Iniciar archivos ejecutables y scripts que intenten descargar o ejecutar otros archivos
- Ejecución de scripts ofuscados o sospechosos
- Iniciar comportamientos que las aplicaciones normalmente no inician durante el trabajo normal

Las aplicaciones empresariales legítimas pueden exhibir este tipo de comportamientos de software; sin embargo, estos comportamientos a menudo se consideran riesgosos porque los atacantes suelen abusar de ellos a través del malware. Las reglas de reducción de superficie de ataque pueden restringir comportamientos riesgosos y ayudar a mantener la seguridad de la organización.

Para obtener más información, consulta [Usar reglas de reducción de superficie de ataque para evitar la infección de malware.](attack-surface-reduction.md)

### <a name="ransomware-mitigation"></a>Mitigación de ransomware

Con acceso controlado a carpetas, obtiene mitigación de ransomware. El acceso controlado a carpetas solo permite que las aplicaciones de confianza obtengan acceso a carpetas protegidas en los puntos de conexión. Las aplicaciones se agregan a la lista de aplicaciones de confianza en función de su prevalencia y reputación. El equipo de operaciones de seguridad también puede agregar o quitar aplicaciones de la lista de aplicaciones de confianza.

Para obtener más información, vea [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md).

### <a name="device-control"></a>Control de dispositivos

En ocasiones, las amenazas a los dispositivos de la organización se incluyen en forma de archivos en unidades extraíbles, como unidades USB. Defender for Endpoint incluye funcionalidades que ayudan a evitar que las amenazas de periféricos no autorizados puedan poner en peligro los dispositivos. Puede configurar Defender for Endpoint para bloquear o permitir dispositivos y archivos extraíbles en dispositivos extraíbles. 

Para obtener más información, consulta [Controlar dispositivos USB y medios extraíbles.](control-usb-devices-using-intune.md)

### <a name="web-protection"></a>Protección web

Con la protección web, puede proteger los dispositivos de su organización frente a amenazas web y contenido no deseado. La protección web incluye protección contra amenazas web y filtrado de contenido web.

- [La protección contra amenazas](web-threat-protection.md) web impide el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación y sitios que bloquea explícitamente.
- [El filtrado de contenido web](web-content-filtering.md) (versión preliminar) impide el acceso a determinados sitios en función de su categoría. Las categorías pueden incluir contenido para adultos, sitios de ocio, sitios de responsabilidad legal y mucho más.

Para obtener más información, vea [protección web](web-protection-overview.md).

### <a name="network-protection"></a>Protección de red

Con la protección de red, puede impedir que su organización acceda a dominios peligrosos que puedan hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet. 

Para obtener más información, vea [Proteger la red](network-protection.md).

### <a name="network-firewall"></a>Firewall de red

Con la protección de firewall de red, puede establecer reglas que determinen qué tráfico de red puede fluir hacia o desde los dispositivos de la organización. Con el firewall de red y la seguridad avanzada que obtiene con Defender for Endpoint, puede:

- Reducir el riesgo de amenazas de seguridad de red
- Proteger los datos confidenciales y la propiedad intelectual
- Ampliar la inversión en seguridad

Para obtener más información, [vea Windows Defender Firewall con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).

### <a name="application-control"></a>Control de la aplicación

El control de aplicaciones protege los Windows de conexión mediante la ejecución de solo aplicaciones de confianza y código en el núcleo del sistema (kernel). El equipo de seguridad puede definir reglas de control de aplicaciones que consideren los atributos de una aplicación, como sus certificados de firma de código, su reputación, el proceso de inicio y mucho más. El control de aplicación está disponible en Windows 10 o posterior.

Para obtener más información, vea [Control de aplicaciones para Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control).

## <a name="centralized-management"></a>Administración centralizada

Defender for Endpoint Plan 1 incluye el portal de Microsoft 365 Defender, que permite al equipo de seguridad ver la información actual sobre las amenazas detectadas, realizar las acciones adecuadas para mitigar las amenazas y administrar de forma centralizada la configuración de protección contra amenazas de la organización.

Para obtener más información, [vea Microsoft 365 Defender información general del portal](portal-overview.md).

### <a name="role-based-access-control"></a>Control de acceso basado en roles

Con el control de acceso basado en roles (RBAC), el administrador de seguridad puede crear roles y grupos para conceder acceso adecuado al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ). Con RBAC, tienes un control preciso sobre quién puede acceder a Defender for Cloud y qué pueden ver y hacer. 

Para obtener más información, vea [Manage portal access using role-based access control](rbac.md).

### <a name="reporting"></a>Reporting

El Microsoft 365 Defender web ( ) proporciona un acceso fácil a la información sobre las amenazas detectadas y [https://security.microsoft.com](https://security.microsoft.com) las acciones para hacer frente a dichas amenazas. 

- La **página** principal incluye tarjetas para mostrar de un vistazo qué usuarios o dispositivos están en riesgo, cuántas amenazas se detectaron y qué alertas o incidentes se crearon.
- En **la sección & de alertas** de incidentes se enumeran los incidentes que se crearon como resultado de alertas desencadenadas. Las alertas e incidentes se generan a medida que se detectan amenazas en todos los dispositivos.
- El **Centro de acciones** enumera las acciones de corrección que se han realizado. Por ejemplo, si se envía un archivo a cuarentena o se bloquea una dirección URL, cada acción se muestra en el Centro de acciones de la **pestaña** Historial.
- La **sección Informes** incluye informes que muestran las amenazas detectadas y su estado. 

Para obtener más información, vea [Introducción a Microsoft Defender para el plan de extremo 1](mde-plan1-getting-started.md).

### <a name="apis"></a>API

Con las API de Defender para endpoints, puede automatizar flujos de trabajo e integrarse con las soluciones personalizadas de su organización. 

Para obtener más información, [vea Defender for Endpoint API](management-apis.md). 

## <a name="cross-platform-support"></a>Compatibilidad entre plataformas

La mayoría de las organizaciones usan varios dispositivos y sistemas operativos. Actualmente, Defender for Endpoint Plan 1 admite los siguientes sistemas operativos:

- Windows 10, versión 1709 o posterior
- macOS: 11.5 (Big Sur), 10.15.7 (Catalina) o 10.14.6 (Mojave)
- iOS
- Sistema operativo Android

## <a name="next-steps"></a>Siguientes pasos

- [Comparar Microsoft Defender para el plan de extremo 1 con el plan 2](defender-endpoint-plan-1-2.md)
- [Configurar y configurar Defender for Endpoint Plan 1](mde-p1-setup-configuration.md)
- [Introducción a Defender for Endpoint Plan 1](mde-plan1-getting-started.md)
- [Administrar Defender para el plan de extremo 1](mde-p1-maintenance-operations.md)
