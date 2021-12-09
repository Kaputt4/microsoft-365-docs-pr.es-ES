---
title: Requisitos para Microsoft Defender para empresas
description: Requisitos de licencia, hardware y software de Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 43ff9e7957e5ec26f3242266c8393bdefdb3240f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375450"
---
# <a name="microsoft-defender-for-business-requirements"></a>Requisitos de Microsoft Defender para empresas

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

En este artículo se describen los requisitos para Microsoft Defender para empresas.

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos.](#review-the-requirements)

2. [Continúe con los pasos siguientes](#next-steps).

## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para configurar y usar Microsoft Defender para empresas. <br/><br/>

| Requisito | Description |
|:---|:---|
| Suscripción  | Microsoft Defender para empresas (actualmente en versión preliminar). Consulta [Cómo obtener Microsoft Defender para empresas](get-defender-business.md).<br/><br/>No es necesario que tenga otra suscripción Microsoft 365 para probar Microsoft Defender para empresas. |
| Datacenter | Una de las siguientes ubicaciones de centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |
| Azure Active Directory (Azure AD) | Azure AD es necesario para los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas. Para obtener más información, vea [What is Azure AD?](/azure/active-directory/fundamentals/active-directory-whatis) |
| Cuentas de usuario | Se crean cuentas de usuario<br/><br/>Se asignan licencias de Microsoft Defender para empresas <br/><br/>Para obtener ayuda con esto, vea [Agregar usuarios y asignar licencias.](../../admin/add-users/add-users.md) |
| Permisos  | Para tener acceso al portal Microsoft 365 Defender, los usuarios deben tener asignado uno de los [siguientes roles Azure AD:](mdb-roles-permissions.md) <br/>- Lector de seguridad<br/>- Administrador de seguridad<br/>- Administrador global<br/><br/>Para obtener más información, consulte [Roles and permissions in Microsoft Defender for Business](mdb-roles-permissions.md). |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo | Para administrar dispositivos en Microsoft Defender para empresas, los dispositivos deben ejecutarse Windows 10 Professional/Enterprise o posterior (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)). <br/><br/>Si ya está administrando dispositivos en Microsoft Intune (o Microsoft Endpoint Manager) o si usa una solución de administración de dispositivos que no sea de [Microsoft,](../defender-endpoint/minimum-requirements.md)los dispositivos deben ejecutar uno de los sistemas operativos compatibles con Microsoft Defender para endpoint . |
| Integración con Microsoft Endpoint Manager  |  **Durante la vista previa, puedes incorporar dispositivos mediante un script local. En este caso, los requisitos previos** para la integración con Microsoft Endpoint Manager que se enumeran aquí no son necesarios . Pero si planea incorporar dispositivos a Defender para empresas manualmente mediante el uso de paquetes descargables para Microsoft Endpoint Manager, directiva de grupo, System Center Configuration Manager o administración de dispositivos móviles, se deben cumplir los siguientes requisitos: <br/><br/>Los dispositivos deben Windows 10 o 11 Professional/Enterprise (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) aplicado). <br/><br/>Se deben cumplir los requisitos previos para [la administración de seguridad de Microsoft Defender para endpoint](/mem/intune/protect/mde-security-integration).<br/>- Azure AD debe configurarse de modo que se cree confianza entre los dispositivos de la empresa y Azure AD. <br/>- Defender para empresas debe tener habilitada la administración de seguridad en Microsoft Endpoint Manager.<br/><br/>Los dispositivos deben poder conectarse a las siguientes direcciones URL:<br/>- `enterpriseregistration.windows.net`(para el registro en Azure AD)<br/>- `login.microsoftonline.com`(para el registro en Azure AD)<br/>- `*.dm.microsoft.com` (El comodín (*) admite los puntos de conexión de servicio en la nube que se usan para la inscripción, la protección y los informes, y puede cambiar a medida que se escala el servicio). |


## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 2: Asignar roles y permisos en Microsoft Defender para empresas](mdb-roles-permissions.md) 
 