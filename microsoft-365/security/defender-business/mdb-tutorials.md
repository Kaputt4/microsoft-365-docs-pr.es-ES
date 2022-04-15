---
title: Tutoriales y simulaciones en Microsoft Defender para Empresas
description: Obtenga información sobre varios tutoriales que le ayudarán a empezar a usar Defender para empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 42d7acb4512928a32ac99c486a231d7891102208
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861342"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Tutoriales y simulaciones en Microsoft Defender para Empresas

> [!IMPORTANT]
> Microsoft Defender para Empresas ya está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Tenga en cuenta que la versión preliminar se iniciará con un [conjunto inicial de escenarios](#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí. 

Si acaba de terminar de configurar Microsoft Defender para Empresas, es posible que se pregunte dónde empezar a aprender sobre cómo funciona Defender para empresas. En este artículo se describen los escenarios de vista previa que se van a probar y varios tutoriales y simulaciones que están disponibles para Defender para empresas. Estos recursos están diseñados para ayudarle a ver cómo Defender for Business puede funcionar para su empresa.

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="try-these-preview-scenarios"></a>Pruebe estos escenarios de vista previa

En la tabla siguiente se resumen varios escenarios para probar con Defender para empresas:

| Escenario  | Descripción  |
|---------|---------|
| Incorporar dispositivos con un script local <br/>(*no para la implementación de producción*)     | En Defender para empresas, puede incorporar hasta diez Windows 10 y 11 dispositivos mediante un script que descargue y ejecute en cada dispositivo. Adecuado para evaluar cómo funcionará Defender for Business en su entorno, el script crea una confianza con Azure Active Directory (Azure AD) e inscribe el dispositivo con Microsoft Intune. Para más información, consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).         |
| Incorporación de dispositivos mediante Microsoft Intune     | Si ya usaba Microsoft Intune antes de obtener Defender para punto de conexión, puede seguir usando Microsoft Intune para incorporar dispositivos. Pruebe a incorporar dispositivos macOS, iOS y Android con Microsoft Intune. Para más información, consulte [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).        |
| Edición de directivas de seguridad     | Si va a administrar las directivas de seguridad en Defender para empresas, use la página **Configuración del dispositivo** para ver y editar las directivas. Para obtener más información, consulte [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md).        |
| Ejecución de un ataque simulado   | Hay varios tutoriales y simulaciones disponibles en Defender para empresas. Estos tutoriales y simulaciones están diseñados para mostrar de primera mano cómo pueden funcionar las características de protección contra amenazas de Defender for Business para su empresa. Para probar uno o varios de los tutoriales, consulte [Tutoriales recomendados para Microsoft Defender para Empresas](#recommended-tutorials-for-defender-for-business).         |
| Visualización de incidentes en Microsoft 365 Lighthouse     | Si es un [Proveedor de soluciones en la nube de Microsoft](/partner-center/enrolling-in-the-csp-program) que usa Microsoft 365 Lighthouse, pronto podrá ver los incidentes en los inquilinos de los clientes en el portal de Microsoft 365 Lighthouse. Para más información, consulte [Microsoft 365 Lighthouse y Microsoft Defender para Empresas](mdb-lighthouse-integration.md).       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Tutoriales recomendados para Defender para empresas

En la tabla siguiente se describen los tutoriales recomendados para clientes de Defender for Business:

| Tutorial  | Descripción  |
|---------|---------|
| **El documento quita la puerta trasera**     | Simular un ataque que introduce malware basado en archivos en un dispositivo de prueba. En el tutorial se describe cómo obtener y usar el archivo de simulación y qué se debe observar en el portal de Microsoft 365 Defender. <br/><br/>Este tutorial requiere que Microsoft Word se instale en el dispositivo de prueba.   |
| **Tutorial de respuesta dinámica**     | Obtenga información sobre cómo usar comandos básicos y avanzados con Live Response. Obtenga información sobre cómo buscar un archivo sospechoso, corregirlo y recopilar información en un dispositivo.   |
| **Administración de vulnerabilidades de & amenazas (escenarios principales)**     | Obtenga información sobre Administración de amenazas y vulnerabilidades a través de tres escenarios: <br/><br/>1. Reduzca la exposición a amenazas y vulnerabilidades de su empresa. <br/>2. Solicitar una corrección. <br/>3. Cree una excepción para las recomendaciones de seguridad. <br/><br/> Amenazas y administración de vulnerabilidades usa un enfoque basado en riesgos para la detección, priorización y corrección de vulnerabilidades de punto de conexión y configuraciones incorrectas.      |

Cada tutorial incluye un documento de tutorial que explica el escenario, cómo funciona y qué hacer.

> [!TIP]
> Verá referencias a Microsoft Defender para punto de conexión en los documentos del tutorial. Los tutoriales enumerados en este artículo se pueden usar con Defender para punto de conexión o Defender para empresas.

## <a name="how-to-access-the-tutorials"></a>Acceso a los tutoriales

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, en **Puntos de conexión**, elija **Tutoriales**.

3. Elija uno de los siguientes tutoriales:

   - **El documento quita la puerta trasera**
   - **Tutorial de respuesta dinámica**
   - **Administración de vulnerabilidades de & amenazas (escenarios principales)**

## <a name="next-steps"></a>Siguientes pasos

- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)