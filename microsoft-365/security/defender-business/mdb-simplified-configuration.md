---
title: Proceso de configuración simplificado en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre el proceso de configuración simplificado en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 16e37e2f0c3daa34c576a92a4e08c544cef35f00
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423904"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business-preview"></a>Proceso de configuración simplificado en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Microsoft Defender para empresas (versión preliminar) presenta un proceso de configuración simplificado, diseñado especialmente para pequeñas y medianas empresas. Esta experiencia quita las conjeturas de incorporación y administración de dispositivos, con una experiencia de asistente y directivas predeterminadas diseñadas para proteger los dispositivos de su empresa desde el primer día. **Se recomienda usar el proceso de configuración simplificado; sin embargo, no se limita a esta opción**.

Cuando se trata de incorporar dispositivos y configurar la configuración de seguridad para los dispositivos de su empresa, puede elegir entre varias experiencias: 

- Proceso de configuración simplificado en Microsoft Defender para empresas (versión preliminar) (*recomendado*) 
- Microsoft Endpoint Manager, que incluye Microsoft Intune
- La solución que no es de Microsoft para administrar dispositivos 

## <a name="what-to-do"></a>Qué hacer

1. [Revisar las opciones de configuración y configuración](#review-your-setup-and-configuration-options)
2. [Obtenga más información sobre el proceso de configuración simplificado en Defender para empresas (versión preliminar)](#why-we-recommend-using-the-simplified-configuration-process)
3. [Continúe con los pasos siguientes](#next-steps)

## <a name="review-your-setup-and-configuration-options"></a>Revisar las opciones de configuración y configuración

En la tabla siguiente se describe cada experiencia:
<br/><br/>

| Experiencia del portal  | Descripción  |
|---------|---------|
| La experiencia de configuración simplificada en el portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) <br/>(*Esta es la opción recomendada para la mayoría de los clientes*)  | La experiencia de configuración simplificada incluye directivas y configuraciones de seguridad predeterminadas que te ayudan a proteger los dispositivos de tu empresa desde el primer día. Con esta experiencia, el equipo de seguridad usa el portal Microsoft 365 Defender para: <br/>- Configurar y configurar Defender para empresas (versión preliminar) <br/>- Ver y administrar incidentes<br/>- Responder y mitigar amenazas<br/>- Ver informes<br/>- Revisar acciones pendientes o completadas <br/><br/> Este portal es tu tienda única para la configuración de seguridad de tu empresa y las capacidades de protección contra amenazas. Obtiene una experiencia simplificada que le ayudará a empezar de forma rápida y eficaz.  Además, puedes editar la configuración o definir nuevas directivas para que se adapten a las necesidades de tu empresa.<br/><br/>Para obtener más información, [consulta Ver o editar directivas de dispositivos en Microsoft Defender para empresas (versión preliminar).](mdb-view-edit-policies.md) |
| El Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) )  | Microsoft Endpoint Manager incluye Microsoft Intune, un proveedor de administración de dispositivos móviles (MDM) basado en la nube y administración de aplicaciones móviles (MAM) para aplicaciones y dispositivos. <br/><br/>Muchas organizaciones usan Intune para administrar sus dispositivos, como teléfonos móviles, tabletas y portátiles. Para obtener más información, [consulta Microsoft Intune es un proveedor de MDM y MAM para tus dispositivos.](/mem/intune/fundamentals/what-is-intune) <br/><br/>Si ya está usando Microsoft Intune o Microsoft Endpoint Manager, puede seguir usando esa solución. |
| La solución de administración de dispositivos que no es de Microsoft  | Si usas una solución de administración de dispositivos y productividad que no sea de Microsoft, como Jamf para macOS o Ansible para Linux, puedes seguir usando esa solución con Defender para empresas (versión preliminar). <br/><br/>Cuando los dispositivos se incorporen a Defender para empresas (versión preliminar), verás su estado y alertas en el portal Microsoft 365 Defender negocio. Para obtener más información, consulte [Onboarding and configuration tool options for Defender for Endpoint](../defender-endpoint/onboard-configure.md).<br/><br/>Si ya estás usando una solución de administración de dispositivos que no sea de Microsoft, puedes seguir usando esa solución. |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>Por qué se recomienda usar el proceso de configuración simplificado

**Se recomienda usar el proceso de configuración simplificado en Microsoft Defender para empresas (versión preliminar)** para la mayoría de los clientes. El proceso de configuración simplificado se simplifica especialmente para pequeñas y medianas empresas. Defender para empresas (versión preliminar) está diseñado para ayudarle a proteger los dispositivos de su empresa el primer día, sin necesidad de conocimientos técnicos o conocimientos especiales. Con las directivas y la configuración de seguridad predeterminadas, los dispositivos se protegen tan pronto como se incorpore.


Defender para empresas (versión preliminar) está diseñado para proporcionar una protección segura y, al mismo tiempo, ahorrar tiempo y esfuerzo en la configuración de la configuración de seguridad. La experiencia optimizada en el portal Microsoft 365 Defender facilita la incorporación de dispositivos y su administración. Además, se incluyen directivas predeterminadas para que los dispositivos de la empresa estén protegidos tan pronto como se incorpore. Puede mantener la configuración predeterminada tal y como está o realizar cambios que se adapten a sus necesidades empresariales. También puedes agregar nuevas directivas para administrar dispositivos según sea necesario.

## <a name="next-steps"></a>Siguientes pasos

- [Configurar y configurar Microsoft Defender para empresas (versión preliminar)](mdb-setup-configuration.md)

- [Introducción al uso de Microsoft Defender para empresas (versión preliminar)](mdb-get-started.md)