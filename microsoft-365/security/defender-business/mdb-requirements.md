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
ms.openlocfilehash: 1114bebe4b57f89989b0e21a3d73a72fd1b3e99e
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772891"
---
# <a name="microsoft-defender-for-business-requirements"></a>requisitos de Microsoft Defender para Empresas

En este artículo se describen los requisitos de Defender para empresas.

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos](#review-the-requirements).
2. [Continúe con los pasos siguientes](#next-steps).


## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos que necesita para configurar y usar Defender para empresas.

| Requisito | Descripción |
|:---|:---|
| Suscripción  | Microsoft 365 Empresa Premium o Defender para empresas (independiente). Consulte [Cómo obtener Defender para empresas](get-defender-business.md).<p>Tenga en cuenta que si tiene varias suscripciones, la suscripción más alta tiene prioridad. Por ejemplo, si tiene Microsoft Defender para punto de conexión plan 2 (suscripción comprada o de prueba) y obtiene Defender para empresas, el plan 2 de Defender para punto de conexión tiene prioridad. En este caso, no verá la experiencia de Defender para empresas. Consulte [¿Qué ocurre si tengo una combinación de suscripciones de Microsoft 365 Defender](mdb-faq.yml#what-happens-if-i-have-a-mix-of-microsoft-endpoint-security-subscriptions)?  |
| Datacenter | Una de las siguientes ubicaciones del centro de datos: <ul><li>Unión Europea</li><li>Reino Unido</li><li>Estados Unidos</li></ul> |
| Cuentas de usuario |<ul><li>Las cuentas de usuario se crean en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)).</li><li>Las licencias de Defender para empresas (o Microsoft 365 Empresa Premium) se asignan en el Centro de administración de Microsoft 365.</li></ul>Para obtener ayuda con esta tarea, consulte [Agregar usuarios y asignar licencias](mdb-add-users.md). |
| Permisos  | Para registrarse en Defender for Business, debe ser un Administración global.<p>Para acceder al portal de Microsoft 365 Defender, los usuarios deben tener asignado uno de los siguientes [roles en Azure AD](mdb-roles-permissions.md):<ul><li>Lector de seguridad</li><li>Administrador de seguridad</li><li>Administrador global</li></ul>Para más información, consulte [Roles y permisos en Defender para empresas](mdb-roles-permissions.md). |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo del dispositivo cliente | Para administrar dispositivos en el portal de Microsoft 365 Defender, los dispositivos deben ejecutar uno de los siguientes sistemas operativos: <ul><li>Windows 10 o 11 Empresas</li><li>Windows 10 o 11 Profesional</li><li>Windows 10 o 11 Enterprise</li><li>Mac (se admiten las tres versiones más recientes)</li></ul><p>Asegúrese de que [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) está instalado en los dispositivos Windows. <p>Si ya está administrando dispositivos en Microsoft Intune, puede seguir usando el Centro de administración de Microsoft Endpoint Manager. En ese caso, se admiten los siguientes sistemas operativos: <ul><li>iOS y iPadOS</li><li>Sistema operativo Android</li></ul> |
| Requisitos de servidor | Si tiene previsto incorporar una instancia de Windows Server o Linux Server, debe cumplir los siguientes requisitos: <ul><li>La opción **Características de vista previa** está activada. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), vaya a **Configuración** > **Puntos de conexión****Características avanzadas** > **generales** >  Características  > **en versión preliminar**.</li><li>El ámbito de cumplimiento para Windows Server está activado. En el portal de Microsoft 365 Defender, vaya a Configuración **Endpoints** Configuration management **Enforcement scope (Ámbito de cumplimiento** de **administración de configuración** >  de puntos  >  de conexión **de configuración** > ). Seleccione **Usar MDE para aplicar la configuración de seguridad desde MEM**, seleccione  **Windows Server** y, a continuación, seleccione **Guardar**.</li><li>Los puntos de conexión de Linux Server cumplen los [requisitos previos para Microsoft Defender para punto de conexión en Linux](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites).</li></ul> |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) se usa para administrar los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas. 
> - Si no tiene una suscripción a Microsoft 365 antes de iniciar la prueba, Azure AD se aprovisionará automáticamente durante el proceso de activación. 
> - Si tiene otra suscripción de Microsoft 365 al iniciar la prueba de Defender para empresas, puede usar el servicio de Azure AD existente. 
> - Si usa [Microsoft 365 Empresa Premium](../../business/index.yml) al iniciar la prueba de Defender for Business, tiene la opción de administrar los dispositivos mediante Intune.

## <a name="next-steps"></a>Pasos siguientes

Vaya al [paso 2: Asignación de roles y permisos en Defender para empresas](mdb-roles-permissions.md).
 
