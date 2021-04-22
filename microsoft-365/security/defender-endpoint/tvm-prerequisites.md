---
title: 'Requisitos previos & permisos: administración de amenazas y vulnerabilidades'
description: Antes de empezar a usar la administración de amenazas y vulnerabilidades, asegúrese de que tiene las configuraciones y permisos pertinentes.
keywords: requisitos previos & de administración de vulnerabilidades, permisos de administración de amenazas y vulnerabilidades, requisitos previos de permisos de Microsoft Defender para Endpoint TVM, administración de vulnerabilidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935190"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Requisitos previos & permisos: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Asegúrese de que los dispositivos:

- Están incorporados a Microsoft Defender para endpoint
- Ejecutar [sistemas operativos y plataformas compatibles](tvm-supported-os.md)
- Haga que las siguientes actualizaciones obligatorias se instalen e implementen en la red para aumentar las tasas de detección de la evaluación de vulnerabilidades:

> Versión | Número y vínculo kb de actualización de seguridad
> :---|:---
> Windows 10 Versión 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) y [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Versión 1803 | [KB4493464](https://support.microsoft.com/help/4493464) y [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Versión 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Versión 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Se incorpora a [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) y Microsoft Endpoint  [Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) para ayudar a corregir las amenazas encontradas por la administración de amenazas y vulnerabilidades. Si usa Configuration Manager, actualice la consola a la versión más reciente.
    - **Nota:** Si tienes habilitada la conexión de Intune, obtienes una opción para crear una tarea de seguridad de Intune al crear una solicitud de corrección. Esta opción no aparece si la conexión no está establecida.
- Tener al menos una recomendación de seguridad que se pueda ver en la página del dispositivo
- Se etiquetan o se marcan como administrados de forma co-administrada

## <a name="relevant-permission-options"></a>Opciones de permisos relevantes

1. Inicie sesión en el Centro de seguridad de Microsoft Defender con una cuenta con un administrador de seguridad o un rol de administrador global asignado.
2. En el panel de navegación, seleccione **Configuración > Roles**.

Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md)

### <a name="view-data"></a>Ver datos

- **Operaciones de seguridad:** ver todos los datos de operaciones de seguridad en el portal
- **Administración de amenazas y vulnerabilidades:** ver los datos de administración de amenazas y vulnerabilidades en el portal

### <a name="active-remediation-actions"></a>Acciones de corrección activas

- **Operaciones de seguridad:** realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para automatización e indicadores
- **Administración de amenazas y vulnerabilidades: control de excepciones:** crear nuevas excepciones y administrar excepciones activas
- **Administración de amenazas y vulnerabilidades: control de** corrección: enviar nuevas solicitudes de corrección, crear vales y administrar las actividades de corrección existentes

Para obtener más información, vea [Opciones de permisos RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Plataformas y sistemas operativos compatibles](tvm-supported-os.md)
- [Asignar valor de dispositivo](tvm-assign-device-value.md)
- [Panel de administración de amenazas y vulnerabilidades](tvm-dashboard-insights.md)

