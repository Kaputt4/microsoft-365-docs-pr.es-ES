---
title: Requisitos para Microsoft Defender para Empresas
description: Microsoft Defender para Empresas requisitos de licencia, hardware y software
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
- m365-initiative-defender-business
ms.openlocfilehash: ab24e3898d897df6813338fd0d2131c3787f0a09
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089592"
---
# <a name="microsoft-defender-for-business-requirements"></a>requisitos de Microsoft Defender para Empresas

En este artículo se describen los requisitos de Microsoft Defender para Empresas.

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos](#review-the-requirements).
2. [Continúe con los pasos siguientes](#next-steps).


## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para configurar y usar Microsoft Defender para Empresas.

| Requisito | Descripción |
|:---|:---|
| Suscripción  | Microsoft 365 Empresa Premium o Microsoft Defender para Empresas (independiente). Consulte [Cómo obtener Microsoft Defender para Empresas](get-defender-business.md).<br/><br/>Tenga en cuenta que si tiene varias suscripciones, la suscripción más alta tiene prioridad. Por ejemplo, si tiene Microsoft Defender para punto de conexión Plan 2 (suscripción comprada o de prueba) y obtiene Microsoft Defender para Empresas, El plan 2 de Defender para punto de conexión tiene prioridad. En este caso, no verá la experiencia de Defender para empresas.  |
| Datacenter | Una de las siguientes ubicaciones del centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |
| Cuentas de usuario | - Las cuentas de usuario se crean en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>: las licencias de Microsoft Defender para Empresas se asignan en el Centro de administración de Microsoft 365<br/><br/>Para obtener ayuda con esta tarea, consulte [Agregar usuarios y asignar licencias](mdb-add-users.md). |
| Permisos  | Para registrarse en Microsoft Defender para Empresas, debe ser un Administración global.<br/><br/>Para acceder al portal de Microsoft 365 Defender, los usuarios deben tener asignado uno de los siguientes [roles en Azure AD](mdb-roles-permissions.md): <br/>- Lector de seguridad<br/>- Administración de seguridad<br/>- Administración global<br/><br/>Para más información, consulte [Roles y permisos en Microsoft Defender para Empresas](mdb-roles-permissions.md). |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo | Para administrar dispositivos en el portal de Microsoft 365 Defender, los dispositivos deben ejecutar uno de los siguientes sistemas operativos: <br/>- Windows 10 Business o posterior <br/>- Windows 10 Professional o posterior <br/>- Windows 10 Enterprise o posterior <br/>- macOS (se admiten las tres versiones más actuales)<br/><br/>Asegúrese de que [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) está instalado en Windows dispositivos. <br/><br/>Si ya está administrando dispositivos en Microsoft Intune, puede seguir usando el centro de administración de Microsoft Endpoint Manager. |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) se usa para administrar los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas. 
> - Si no tiene una suscripción Microsoft 365 antes de iniciar la prueba, Azure AD se aprovisionará automáticamente durante el proceso de activación. 
> - Si tiene otra suscripción Microsoft 365 al iniciar la prueba de Defender para empresas, puede usar el servicio de Azure AD existente. 
> - Si usa [Microsoft 365 Empresa Premium](../../business/index.yml) al iniciar la prueba de Defender para empresas, tendrá la opción de administrar los dispositivos mediante Intune. 

## <a name="next-steps"></a>Pasos siguientes

Vaya al [paso 2: Asignación de roles y permisos en Microsoft Defender para Empresas](mdb-roles-permissions.md).
 
