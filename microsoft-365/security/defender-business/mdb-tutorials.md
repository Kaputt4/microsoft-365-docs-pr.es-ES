---
title: Tutoriales y simulaciones en Microsoft Defender para Empresas
description: Obtenga información sobre varios tutoriales que le ayudarán a empezar a usar Defender para empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 80ec798842c29f42a70837b0a0e33042884c2e02
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600146"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Tutoriales y simulaciones en Microsoft Defender para Empresas

En este artículo se describen algunos escenarios para probar y varios tutoriales y simulaciones que están disponibles para Defender para empresas. Estos recursos muestran cómo Defender for Business puede funcionar para su empresa.


## <a name="try-these-scenarios"></a>Pruebe estos escenarios

En la tabla siguiente se resumen varios escenarios para probar con Defender para empresas.

| Escenario  | Descripción  |
|---------|---------|
| Incorporar dispositivos con un script local     | En Defender para empresas, puede incorporar dispositivos Windows y Mac mediante un script que descargue y ejecute en cada dispositivo. El script crea una confianza con Azure Active Directory (Azure AD), si esa confianza aún no existe; inscribe el dispositivo con Microsoft Intune, si tiene Intune, e incorpora el dispositivo a Defender for Business. Para más información, consulte [Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md).         |
| Incorporación de dispositivos mediante el Centro de administración de Microsoft Endpoint Manager     | Si ya usaba Intune antes de obtener Defender for Business, puede seguir usando Endpoint Manager centro de administración para incorporar dispositivos. Pruebe a incorporar los dispositivos Windows, Mac, iOS y Android con Microsoft Intune. Para más información, consulte [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).        |
| Edición de directivas de seguridad     | Si va a administrar las directivas de seguridad en Defender para empresas, use la página **Configuración del dispositivo** para ver y editar las directivas. Defender for Business incluye directivas predeterminadas que usan la configuración recomendada para proteger los dispositivos de su empresa en cuanto se incorporan. Puede mantener las directivas predeterminadas, editarlas y definir sus propias directivas para satisfacer sus necesidades empresariales. Para obtener más información, consulte [Visualización o edición de directivas en Defender para empresas](mdb-view-edit-policies.md).        |
| Ejecución de un ataque simulado   | Hay varios tutoriales y simulaciones disponibles en Defender para empresas. En estos tutoriales y simulaciones se muestra cómo las características de protección contra amenazas de Defender for Business pueden funcionar para su empresa. También puede usar un ataque simulado como ejercicio de entrenamiento para el equipo. Para probar los tutoriales, consulte [Tutoriales recomendados para Defender para empresas](#recommended-tutorials-for-defender-for-business).         |
| Visualización de incidentes en Microsoft 365 Lighthouse     | Si es proveedor de soluciones en la [nube de Microsoft](/partner-center/enrolling-in-the-csp-program) mediante Microsoft 365 Lighthouse, puede ver los incidentes en los inquilinos de los clientes en el portal de Microsoft 365 Lighthouse. Para más información, consulte [Microsoft 365 Lighthouse y Defender para empresas](mdb-lighthouse-integration.md).       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Tutoriales recomendados para Defender para empresas

En la tabla siguiente se describen los tutoriales recomendados para los clientes de Defender for Business.

| Tutorial  | Descripción  |
|---------|---------|
| **Puerta trasera de eliminación de documentos**     | Simular un ataque que introduce malware basado en archivos en un dispositivo de prueba. En el tutorial se describe cómo usar el archivo de simulación y qué se debe observar en el portal de Microsoft 365 Defender. <p>Este tutorial requiere que Microsoft Word esté instalado en el dispositivo de prueba.   |
| **Respuesta dinámica**     | Obtenga información sobre cómo usar comandos básicos y avanzados con Live Response. Obtenga información sobre cómo buscar un archivo sospechoso, corregirlo y recopilar información en un dispositivo.   |
| **Administración de vulnerabilidades de Microsoft Defender(escenarios principales)**     | Obtenga información sobre la administración de vulnerabilidades de Defender a través de tres escenarios:<ol><li>Reduzca la exposición a amenazas y vulnerabilidades de su empresa.</li><li>Solicite una corrección.</li><li>Cree una excepción para las recomendaciones de seguridad.</li></ol> <p> Defender Vulnerability Management usa un enfoque basado en riesgos para la detección, priorización y corrección de vulnerabilidades de punto de conexión y configuraciones incorrectas.      |

Cada tutorial incluye un documento de tutorial que explica el escenario, cómo funciona y qué hacer.

> [!TIP]
> Verá referencias a Microsoft Defender para punto de conexión en los documentos del tutorial. Los tutoriales enumerados en este artículo se pueden usar con Defender para punto de conexión o Defender para empresas.

## <a name="how-to-access-the-tutorials"></a>Acceso a los tutoriales

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, en **Puntos de conexión**, elija **Tutoriales**.

3. Elija uno de los siguientes tutoriales:

   - **Puerta trasera de eliminación de documentos**
   - **Respuesta dinámica**
   - **Administración de vulnerabilidades de Microsoft Defender (escenarios principales)**

## <a name="next-steps"></a>Pasos siguientes

- [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)