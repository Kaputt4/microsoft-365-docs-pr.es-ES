---
title: 'Requisitos & permisos: Administración de amenazas y vulnerabilidades'
description: Antes de empezar a usar Administración de amenazas y vulnerabilidades, asegúrese de que tiene las configuraciones y permisos pertinentes.
keywords: requisitos previos de permisos de & administración de vulnerabilidades, requisitos previos de Administración de amenazas y vulnerabilidades permisos, requisitos previos de permisos de Microsoft Defender para Endpoint TVM, administración de vulnerabilidades
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
ms.openlocfilehash: 9fde7ed4c7a3b621730e2b6cd73370d87ea9c92c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189377"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Requisitos & permisos: Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

Asegúrese de que los dispositivos:

- Están incorporados a Microsoft Defender para endpoint

- Ejecutar [sistemas operativos y plataformas compatibles](tvm-supported-os.md)

- Haga que las siguientes actualizaciones obligatorias se instalen e implementen en la red para aumentar las tasas de detección de la evaluación de vulnerabilidades:

  > Liberar | Número y vínculo kb de actualización de seguridad
  > :---|:---
  > Windows 10 Versión 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) y [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
  > Windows 10 Versión 1803 | [KB4493464](https://support.microsoft.com/help/4493464) y [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
  > Windows 10 Versión 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
  > Windows 10 Versión 1903 | [Kb 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Se incorpora a [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) para ayudar a corregir las amenazas encontradas por Administración de amenazas y vulnerabilidades. Si usa Configuration Manager, actualice la consola a la versión más reciente.

  > [!NOTE]
  > Si tienes habilitada la conexión de Intune, obtienes una opción para crear una tarea de seguridad de Intune al crear una solicitud de corrección. Esta opción no aparece si la conexión no está establecida.

- Tener al menos una recomendación de seguridad que se pueda ver en la página del dispositivo

- Se etiquetan o se marcan como administrados de forma co-administrada

## <a name="relevant-permission-options"></a>Opciones de permisos relevantes

1. Inicie sesión en el portal Microsoft 365 Defender con una cuenta con un administrador de seguridad o un rol de administrador global asignado.
2. En el panel de navegación, **seleccione Configuración > Endpoints > Roles**.

Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md).

### <a name="view-data"></a>Ver datos

- **Operaciones de seguridad:** ver todos los datos de operaciones de seguridad en el portal
- **Amenaza y administración de vulnerabilidades:** ver Administración de amenazas y vulnerabilidades datos en el portal

### <a name="active-remediation-actions"></a>Acciones de corrección activas

- **Operaciones de seguridad:** realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para automatización e indicadores
- **Amenazas y administración de vulnerabilidades: control de excepciones:** crear nuevas excepciones y administrar excepciones activas
- **Amenazas y administración de vulnerabilidades: control de** corrección: enviar nuevas solicitudes de corrección, crear vales y administrar las actividades de corrección existentes

Para obtener más información, vea [Opciones de permisos RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Plataformas y sistemas operativos compatibles](tvm-supported-os.md)
- [Asignar valor de dispositivo](tvm-assign-device-value.md)
- [Panel de administración de vulnerabilidades amenazas](tvm-dashboard-insights.md)

