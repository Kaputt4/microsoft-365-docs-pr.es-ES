---
title: Introducción al plan 1 de Microsoft Defender para punto de conexión
description: Obtenga información general sobre el plan 1 de Defender para punto de conexión. Obtenga información sobre las características y funcionalidades incluidas en esta suscripción de Endpoint Protection.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-overview
ms.openlocfilehash: d3d0118c75f2ac183b6a7c6b6eef599b2a943b1f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67468909"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1"></a>Introducción al plan 1 de Microsoft Defender para punto de conexión

**Se aplica a**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para punto de conexión es una plataforma de seguridad de punto de conexión empresarial diseñada para ayudar a organizaciones como la suya a prevenir, detectar, investigar y responder a amenazas avanzadas. Nos complace anunciar que Defender para punto de conexión ya está disponible en dos planes: 

- **Plan 1 de Defender para punto de conexión**, descrito en este artículo; Y 
- **[Plan 2 de Defender para punto de conexión](microsoft-defender-endpoint.md)**, disponible con carácter general y conocido anteriormente como [Defender para punto de conexión](microsoft-defender-endpoint.md).

Los cuadros verdes de la imagen siguiente muestran lo que se incluye en el plan 1 de Defender para punto de conexión:

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Qué se inculca con el plan 1 de Defender para punto de conexión" lightbox="../../media/mde-p1/mde-p1-overview-diagram.png":::

Use esta guía para:

- [Obtenga información general sobre lo que se incluye en el plan 1 de Defender para punto de conexión](#defender-for-endpoint-plan-1-capabilities)
- [Comparar los planes 1 y 2 de Defender para punto de conexión](defender-endpoint-plan-1-2.md)
- [Obtenga información sobre cómo configurar y configurar El plan 1 de Defender para punto de conexión](mde-p1-setup-configuration.md)
- [Empiece a usar el portal de Microsoft 365 Defender, donde puede ver incidentes y alertas, administrar dispositivos y usar informes sobre amenazas detectadas.](mde-plan1-getting-started.md)
- [Obtenga información general sobre el mantenimiento y las operaciones.](mde-p1-maintenance-operations.md)

> [!TIP]
> [Obtenga más información sobre las diferencias entre defender para el plan 1 y el plan 2](defender-endpoint-plan-1-2.md).

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Funcionalidades del plan 1 de Defender para punto de conexión

El plan 1 de Defender para punto de conexión incluye las siguientes funcionalidades:

- **[Protección de última generación](#next-generation-protection)** que incluye protección antivirus y antimalware sólida líder en el sector
- **[Acciones de respuesta manuales](#manual-response-actions)**, como enviar un archivo a cuarentena, que el equipo de seguridad puede tomar en dispositivos o archivos cuando se detectan amenazas.
- **[Funcionalidades de reducción de la superficie expuesta a ataques](#attack-surface-reduction)** que protegen los dispositivos, evitan ataques de día cero y ofrecen un control pormenorizado sobre el acceso y los comportamientos de los puntos de conexión.
- **[Configuración y administración centralizadas](#centralized-management)** con el portal de Microsoft 365 Defender e integración con Microsoft Endpoint Manager
- **[Protección para una variedad de plataformas, incluidos](#cross-platform-support)** dispositivos Windows, macOS, iOS y Android

En las secciones siguientes se proporcionan más detalles sobre estas funcionalidades. 

## <a name="next-generation-protection"></a>Protección de última generación

La protección de última generación incluye protección antivirus y antimalware sólida. Con la protección de próxima generación, obtendrá lo siguiente: 

- Protección antivirus basada en comportamientos, heurística y en tiempo real 
- Protección proporcionada por la nube, que incluye detección casi instantánea y bloqueo de amenazas nuevas y emergentes 
- Protección dedicada y actualizaciones de productos, incluidas las actualizaciones relacionadas con el Antivirus de Microsoft Defender 

Para más información, consulte [Introducción a la protección de próxima generación](next-generation-protection.md).

## <a name="manual-response-actions"></a>Acciones de contestación manual

Las acciones de respuesta manual son acciones que el equipo de seguridad puede realizar cuando se detectan amenazas en puntos de conexión o en archivos. Defender para punto de conexión incluye ciertas [acciones de respuesta manual que se pueden realizar en un dispositivo](respond-machine-alerts.md) que se detecta como potencialmente comprometido o que tiene contenido sospechoso. También puede ejecutar [acciones de respuesta en los archivos](respond-file-alerts.md) que se detectan como amenazas. En la tabla siguiente se resumen las acciones de respuesta manual que están disponibles en El plan 1 de Defender para punto de conexión. <br/><br/>

| Archivo o dispositivo | Acción | Descripción |
|:---|:---|:---|
| Device | Ejecutar examen de antivirus | Inicia un examen antivirus. Si se detecta alguna amenaza en el dispositivo, esas amenazas a menudo se abordan durante un examen antivirus. |
| Device | Aislar el dispositivo | Desconecta un dispositivo de la red de la organización mientras conserva la conectividad con Defender para punto de conexión. Esta acción le permite supervisar el dispositivo y realizar más acciones si es necesario. |
| Archivo | Detener y poner en cuarentena un archivo |Detiene la ejecución de procesos y pone en cuarentena los archivos asociados. |
| Archivo | Adición de un indicador para bloquear o permitir un archivo | Los indicadores de bloque impiden que los archivos ejecutables portátiles se lean, escriban o ejecuten en los dispositivos. <p>Permitir indicadores impide que los archivos se bloqueen o corrijan. |

Para más información, consulte los artículos siguientes:

- [Realizar acciones de respuesta en los dispositivos](respond-machine-alerts.md) 
- [Realizar acciones de respuesta en archivos](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

Las superficies de ataque de su organización son todos los lugares donde es vulnerable a los ciberataques. Con el plan 1 de Defender para punto de conexión, puede reducir las superficies expuestas a ataques mediante la protección de los dispositivos y aplicaciones que usa su organización. Las funcionalidades de reducción de la superficie expuesta a ataques que se incluyen en El plan 1 de Defender para punto de conexión se describen en las secciones siguientes.

- [Reglas de la reducción de la superficie expuesta a ataques](#attack-surface-reduction-rules)
- [Mitigación de ransomware](#ransomware-mitigation)
- [Control de dispositivos](#device-control)
- [Protección web](#web-protection)
- [Protección de red](#web-protection)
- [Firewall de red](#network-firewall)
- [Control de la aplicación](#application-control)

Para obtener más información sobre las funcionalidades de reducción de superficie expuesta a ataques en Defender para punto de conexión, consulte [Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md).

### <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

Las reglas de reducción de superficie expuesta a ataques se dirigen a determinados comportamientos de software que se consideran de riesgo. Estos comportamientos incluyen:

- Iniciar archivos ejecutables y scripts que intentan descargar o ejecutar otros archivos
- Ejecución de scripts ofuscados o sospechosos
- Iniciar comportamientos que las aplicaciones no suelen iniciar durante el trabajo normal

Las aplicaciones empresariales legítimas pueden presentar tales comportamientos de software; sin embargo, estos comportamientos a menudo se consideran de riesgo porque suelen ser objeto de abuso por parte de los atacantes a través de malware. Las reglas de reducción de la superficie expuesta a ataques pueden restringir los comportamientos de riesgo y ayudar a proteger su organización.

Para obtener más información, consulta [Usar reglas de reducción de superficie expuesta a ataques para evitar la infección por malware](attack-surface-reduction.md).

### <a name="ransomware-mitigation"></a>Mitigación de ransomware

Con el acceso controlado a carpetas, se obtiene la mitigación de ransomware. El acceso controlado a carpetas solo permite que las aplicaciones de confianza accedan a carpetas protegidas en los puntos de conexión. Las aplicaciones se agregan a la lista de aplicaciones de confianza en función de su prevalencia y reputación. El equipo de operaciones de seguridad también puede agregar o quitar aplicaciones de la lista de aplicaciones de confianza.

Para más información, consulte [Protección de carpetas importantes con acceso controlado a carpetas](controlled-folders.md).

### <a name="device-control"></a>Control de dispositivo

A veces, las amenazas a los dispositivos de la organización se presentan en forma de archivos en unidades extraíbles, como unidades USB. Defender for Endpoint incluye funcionalidades para ayudar a evitar que las amenazas de periféricos no autorizados pongan en peligro los dispositivos. Puede configurar Defender para punto de conexión para bloquear o permitir dispositivos y archivos extraíbles en dispositivos extraíbles. 

Para más información, consulte [Control de dispositivos USB y medios extraíbles](control-usb-devices-using-intune.md).

### <a name="web-protection"></a>Protección web

Con la protección web, puede proteger los dispositivos de su organización frente a amenazas web y contenido no deseado. La protección web incluye protección contra amenazas web y filtrado de contenido web.

- [La protección contra amenazas web](web-threat-protection.md) impide el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidades de seguridad, sitios que no son de confianza o de baja reputación y sitios que se bloquean explícitamente.
- [El filtrado de contenido web](web-content-filtering.md) impide el acceso a determinados sitios en función de su categoría. Las categorías pueden incluir contenido para adultos, sitios de ocio, sitios de responsabilidad legal, etc.

Para obtener más información, consulte [protección web](web-protection-overview.md).

### <a name="network-protection"></a>Protección de red

Con la protección de red, puede impedir que su organización acceda a dominios peligrosos que puedan hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet. 

Para más información, consulte [Protección de la red](network-protection.md).

### <a name="network-firewall"></a>Firewall de red

Con la protección del firewall de red, puede establecer reglas que determinen qué tráfico de red puede fluir hacia o desde los dispositivos de la organización. Con el firewall de red y la seguridad avanzada que obtiene con Defender para punto de conexión, puede hacer lo siguiente:

- Reducir el riesgo de amenazas de seguridad de red
- Protección de datos confidenciales y propiedad intelectual
- Ampliación de la inversión en seguridad

Para más información, consulte [Windows Defender Firewall con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).

### <a name="application-control"></a>Control de la aplicación

El control de aplicaciones protege los puntos de conexión de Windows ejecutando solo aplicaciones y código de confianza en el núcleo del sistema (kernel). El equipo de seguridad puede definir reglas de control de aplicaciones que consideren los atributos de una aplicación, como sus certificados de firma de código, reputación, proceso de inicio, etc. El control de aplicación está disponible en Windows 10 o posterior.

Para obtener más información, consulte [Control de aplicaciones para Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control).

## <a name="centralized-management"></a>Administración centralizada

El plan 1 de Defender para punto de conexión incluye el portal de Microsoft 365 Defender, que permite al equipo de seguridad ver la información actual sobre las amenazas detectadas, realizar las acciones adecuadas para mitigar las amenazas y administrar de forma centralizada la configuración de protección contra amenazas de su organización.

Para obtener más información, consulte [Microsoft 365 Defender introducción al portal](portal-overview.md).

### <a name="role-based-access-control"></a>Control de acceso basado en roles

Mediante el control de acceso basado en rol (RBAC), el administrador de seguridad puede crear roles y grupos para conceder el acceso adecuado al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Con RBAC, tiene un control específico sobre quién puede acceder a Defender for Cloud y qué pueden ver y hacer. 

Para más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

### <a name="reporting"></a>Reporting

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) proporciona fácil acceso a la información sobre las amenazas y acciones detectadas para abordar esas amenazas. 

- La página **Inicio** incluye tarjetas para mostrar de un vistazo qué usuarios o dispositivos están en riesgo, cuántas amenazas se detectaron y qué alertas o incidentes se crearon.
- En **la sección Incidentes & alertas** se enumeran los incidentes que se crearon como resultado de las alertas desencadenadas. Las alertas y los incidentes se generan a medida que se detectan amenazas en todos los dispositivos.
- El **Centro de** acciones enumera las acciones de corrección que se han realizado. Por ejemplo, si un archivo se envía a cuarentena o se bloquea una dirección URL, cada acción se muestra en el Centro de acciones de la pestaña **Historial** .
- La sección **Informes** incluye informes que muestran las amenazas detectadas y su estado. 

Para más información, consulte [Introducción a Microsoft Defender para punto de conexión Plan 1](mde-plan1-getting-started.md).

### <a name="apis"></a>API

Con las API de Defender para punto de conexión, puede automatizar los flujos de trabajo e integrarlos con las soluciones personalizadas de su organización. 

Para más información, consulte [Api de Defender para punto de conexión](management-apis.md). 

## <a name="cross-platform-support"></a>Compatibilidad multiplataforma.

La mayoría de las organizaciones usan varios dispositivos y sistemas operativos. Actualmente, El plan 1 de Defender para punto de conexión admite los siguientes sistemas operativos:

- Windows 7 (ESU obligatorio)
- Windows 8.1
- Windows 10, versión 1709 o posterior
- Windows 10 Enterprise
- Windows 10 Enterprise LTSC 2016 (o posterior)](/windows/whats-new/ltsc/)
- Windows 10 Enterprise loT
- macOS (se admiten las tres versiones más recientes)
- iOS
- Sistema operativo Android

## <a name="next-steps"></a>Pasos siguientes

- [Comparar Microsoft Defender para punto de conexión plan 1 con plan 2](defender-endpoint-plan-1-2.md)
- [Configurar Defender para punto de conexión plan 1](mde-p1-setup-configuration.md)
- [Introducción al plan 1 de Defender para punto de conexión](mde-plan1-getting-started.md)
- [Administración del plan 1 de Defender para punto de conexión](mde-p1-maintenance-operations.md)
