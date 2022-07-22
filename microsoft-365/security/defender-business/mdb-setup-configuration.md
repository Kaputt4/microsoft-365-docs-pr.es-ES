---
title: Configuración y configuración de Microsoft Defender para Empresas
description: Vea cómo configurar la solución de ciberseguridad de Defender para empresas. Incorporación de dispositivos, revisión de las directivas y edición de la configuración según sea necesario.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: e6489fa45e85c8c9561a29bfc7e47615a5c0ea33
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969735"
---
# <a name="set-up-and-configure-microsoft-defender-for-business"></a>Configuración y configuración de Microsoft Defender para Empresas

Defender for Business proporciona una experiencia de configuración y configuración simplificada, diseñada especialmente para la pequeña y mediana empresa. Use este artículo como guía para el proceso general.

> [!TIP]
> Si usó el [asistente para la instalación](mdb-use-wizard.md), ya ha completado varios pasos del proceso de instalación básico. En este caso, puede:
> - [Incorporación de más dispositivos](mdb-onboard-devices.md)
> - [Configuración de directivas y opciones de seguridad](mdb-configure-security-settings.md)
> - [Visite el panel de administración de vulnerabilidades.](mdb-view-tvm-dashboard.md)


## <a name="the-setup-and-configuration-process"></a>Proceso de instalación y configuración

En el diagrama siguiente se muestra el proceso de configuración y configuración general de Defender para empresas. Si usó el asistente para la instalación, es probable que ya haya completado los pasos 1 a 3 y posiblemente el paso 4. 

:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Proceso de configuración y configuración de Defender para empresas.":::

| Paso  | Artículo | Descripción  |
|---------|---------|--------|
| 1 | [Revisar los requisitos](mdb-requirements.md) | Revise los requisitos, incluidos los sistemas operativos compatibles, para Defender para empresas. Consulte [Requisitos de Defender para empresas](mdb-requirements.md). |
| 2 | [Asignación de roles y permisos](mdb-roles-permissions.md)     | Los usuarios del equipo de seguridad necesitan permisos para realizar tareas, como revisar las amenazas detectadas & acciones de corrección, ver & directivas de edición, incorporar dispositivos y usar informes. Puede conceder estos permisos a través de determinados roles. Consulte [Asignación de roles y permisos](mdb-roles-permissions.md).        |
| 3 | [Configuración de notificaciones por correo electrónico](mdb-email-notifications.md) | Puede especificar quién debe recibir notificaciones por correo electrónico cuando se desencadenen alertas o se detecten nuevas vulnerabilidades. Consulte [Configuración de notificaciones por correo electrónico](mdb-email-notifications.md).| 
| 4 | [Incorporación de dispositivos](mdb-onboard-devices.md)     | Defender for Business está configurado para que pueda elegir entre varias opciones para incorporar los dispositivos de su empresa. Consulte [Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md).         |
| 5 | [Configuración de las directivas y las opciones de seguridad](mdb-configure-security-settings.md) | Puede elegir entre varias opciones para configurar las directivas y las opciones de seguridad, como el [proceso de configuración simplificado](mdb-simplified-configuration.md) en Defender para empresas o el Centro de administración de Microsoft Endpoint Manager. Consulte [Configuración de las directivas y las opciones de seguridad](mdb-configure-security-settings.md). |

## <a name="next-steps"></a>Pasos siguientes

Continúe con [el paso 1: Revisar los requisitos de Microsoft Defender para Empresas](mdb-requirements.md).
