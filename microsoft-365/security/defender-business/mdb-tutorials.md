---
title: Tutoriales y simulaciones en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre varios tutoriales que le ayudarán a empezar a usar Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: ff1a50a0ba04880680e663d1f960d3f10582d628
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423472"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business-preview"></a>Tutoriales y simulaciones en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Si acaba de terminar de configurar Microsoft Defender para empresas (versión preliminar), puede que se pregunte dónde empezar a aprender sobre cómo funciona Defender for Business (versión preliminar). En este artículo se describen los escenarios de vista previa que se van a probar y varios tutoriales y simulaciones que están disponibles para Defender para empresas (versión preliminar). Estos recursos están diseñados para ayudarle a ver cómo Defender para empresas (versión preliminar) puede funcionar para su empresa.

## <a name="try-these-preview-scenarios"></a>Pruebe estos escenarios de vista previa

En la tabla siguiente se resumen varios escenarios para probar durante la vista previa de Defender para empresas (versión preliminar). 
<br/><br/>


| Escenario  | Descripción  |
|---------|---------|
| Incorporar dispositivos con un script local     | En Defender para empresas (versión preliminar), puedes incorporar Windows 10 y 11 dispositivos mediante un script que descargues y ejecutes en cada dispositivo. El script crea una confianza con Azure Active Directory (Azure AD) e inscribe el dispositivo con Microsoft Intune. Para obtener más información, consulta [Incorporación de un dispositivo con un script local en Defender para empresas (versión preliminar).](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)         |
| Incorporar dispositivos con Microsoft Intune     | Si ya usaste Microsoft Intune obtener Defender for Endpoint, puedes usar Microsoft Intune para incorporar dispositivos. Prueba a incorporar dispositivos macOS, iOS, Linux y Android con Microsoft Intune. Para obtener más información, consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).        |
| Editar directivas y configuraciones de seguridad     | Si estás administrando las directivas de seguridad y la configuración en Defender para empresas (versión preliminar), usa la página **Configuración** del dispositivo para ver y editar las directivas. Para obtener más información, vea [Ver o editar directivas en Microsoft Defender para empresas (versión preliminar).](mdb-view-edit-policies.md)        |
| Ejecutar un ataque simulado   | Hay varios tutoriales y simulaciones disponibles en Defender para empresas (versión preliminar). Estos tutoriales y simulaciones están diseñados para mostrar de primera mano cómo las características de protección contra amenazas de Defender para empresas (versión preliminar) pueden funcionar para su empresa. Para probar uno o varios de los tutoriales, vea [Tutoriales recomendados para Microsoft Defender para empresas (versión preliminar).](#recommended-tutorials-for-defender-for-business)         |
| Ver incidentes en Microsoft 365 Lighthouse     | Si es un partner de Microsoft que usa Microsoft 365 Lighthouse, puede ver incidentes en los inquilinos de sus clientes en su portal Microsoft 365 Lighthouse cliente. Para obtener más información, [vea Microsoft 365 Lighthouse y Microsoft Defender para empresas (versión preliminar).](mdb-lighthouse-integration.md)       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Tutoriales recomendados para Defender para empresas

En la tabla siguiente se describen los tutoriales recomendados para clientes de Defender para empresas (versión preliminar):
<br/><br/>


| Tutorial  | Descripción  |
|---------|---------|
| **El documento deja atrás la puerta trasera**     | Simular un ataque que introduce malware basado en archivos en un dispositivo de prueba. En el tutorial se describe cómo obtener y usar el archivo de simulación y qué se debe buscar en el portal Microsoft 365 Defender simulación. <br/><br/>Este tutorial requiere Microsoft Word instalar en el dispositivo de prueba.   |
| **Tutorial de respuesta en directo**     | Aprende a usar comandos básicos y avanzados con Live Response. Obtén información sobre cómo localizar un archivo sospechoso, corregir el archivo y recopilar información en un dispositivo.   |
| **Administración & vulnerabilidad de amenazas (escenarios principales)**     | Obtenga información sobre Administración de amenazas y vulnerabilidades tres escenarios: <br/><br/>1. Reduzca la exposición a amenazas y vulnerabilidades de su organización. <br/>2. Solicitar una corrección. <br/>3. Cree una excepción para las recomendaciones de seguridad. <br/><br/> Threat and administración de vulnerabilidades uses a risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.      |

Cada tutorial incluye un documento de tutorial que explica el escenario, cómo funciona y qué hacer.

> [!TIP]
> Verá referencias a Microsoft Defender para Endpoint en los documentos del tutorial. Los tutoriales enumerados en este artículo se pueden usar con Defender para Endpoint o Defender para empresas (versión preliminar).

## <a name="how-to-access-the-tutorials"></a>Cómo obtener acceso a los tutoriales

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, en **Extremos,** elija **Tutoriales**.

3. Elija uno de los siguientes tutoriales:

   - **El documento deja atrás la puerta trasera**
   - **Tutorial de respuesta en directo**
   - **Administración & vulnerabilidad de amenazas (escenarios principales)**

## <a name="next-steps"></a>Siguientes pasos

- [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)