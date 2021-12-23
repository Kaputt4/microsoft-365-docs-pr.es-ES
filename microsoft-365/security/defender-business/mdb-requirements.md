---
title: Requisitos para Microsoft Defender para empresas (versión preliminar)
description: Requisitos de licencia, hardware y software de Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/21/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 253386571d96c5d2b0e4a4f85896e28eec400f8f
ms.sourcegitcommit: 1a3b79b3dff13a4895dfa4090a22bce2fcd0942b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2021
ms.locfileid: "61597572"
---
# <a name="microsoft-defender-for-business-preview-requirements"></a>Requisitos de Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En este artículo se describen los requisitos para Microsoft Defender para empresas (versión preliminar).

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos.](#review-the-requirements)

2. [Continúe con los pasos siguientes](#next-steps).

## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para configurar y usar Microsoft Defender para empresas (versión preliminar). <br/><br/>

| Requisito | Description |
|:---|:---|
| Suscripción  | Microsoft Defender para empresas (actualmente en versión preliminar). Consulta [Cómo obtener Microsoft Defender para empresas (versión preliminar).](get-defender-business.md)<br/><br/>**No es necesario que tenga otra suscripción Microsoft 365 para probar Microsoft Defender para empresas** (versión preliminar). |
| Datacenter | Una de las siguientes ubicaciones de centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |
| Cuentas de usuario | Se crean cuentas de usuario<br/><br/>Se asignan licencias de Microsoft Defender para empresas (versión preliminar) <br/><br/>Para obtener ayuda con esto, vea [Agregar usuarios y asignar licencias.](../../admin/add-users/add-users.md) |
| Permisos  | Para registrarse en Microsoft Defender para empresas (versión preliminar), debe ser administrador global.<br/><br/>Para tener acceso al portal Microsoft 365 Defender, los usuarios deben tener uno de los [siguientes roles Azure AD](mdb-roles-permissions.md) asignados: <br/>- Lector de seguridad<br/>- Administrador de seguridad<br/>- Administrador global<br/><br/>Para obtener más información, vea [Roles y permisos en Microsoft Defender para empresas (versión preliminar).](mdb-roles-permissions.md) |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo | Para administrar dispositivos en Microsoft Defender para empresas (versión preliminar), los dispositivos deben ejecutarse Windows 10 Professional/Enterprise o posterior (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)). <br/><br/>Si ya está administrando dispositivos en Microsoft Intune (o Microsoft Endpoint Manager) o si usa una solución de administración de dispositivos que no sea de [Microsoft,](../defender-endpoint/minimum-requirements.md)los dispositivos deben ejecutar uno de los sistemas operativos compatibles con Microsoft Defender para endpoint . |
| Integración con Microsoft Endpoint Manager  |  **Durante la vista previa, puedes incorporar dispositivos con un script local,** que no requiere integración con Microsoft Endpoint Manager . Pero si planea incorporar dispositivos a Defender para empresas (versión preliminar) manualmente mediante el uso de paquetes descargables para Microsoft Endpoint Manager, directiva de grupo, System Center Configuration Manager o administración de dispositivos móviles, se deben cumplir los siguientes requisitos: <br/><br/>Los dispositivos deben Windows 10 o 11 Professional/Enterprise (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) aplicado). <br/><br/>Se deben cumplir los requisitos previos para [la administración de seguridad de Microsoft Defender para endpoint](/mem/intune/protect/mde-security-integration).<br/>- Azure AD debe configurarse de modo que se cree confianza entre los dispositivos de la empresa y Azure AD. <br/>- Defender para empresas (versión preliminar) debe tener habilitada la administración de seguridad en Microsoft Endpoint Manager.<br/><br/>Los dispositivos deben poder conectarse a las siguientes direcciones URL:<br/>- `enterpriseregistration.windows.net`(para el registro en Azure AD)<br/>- `login.microsoftonline.com`(para el registro en Azure AD)<br/>- `*.dm.microsoft.com` (El comodín (*) admite los puntos de conexión de servicio en la nube que se usan para la inscripción, la protección y los informes, y puede cambiar a medida que se escala el servicio). |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) se usa para administrar los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas (versión preliminar). 
> - Si no tiene una suscripción Microsoft 365 antes de iniciar la prueba, Azure AD se aprovisionará durante el proceso de activación. 
> - Si tiene otra suscripción Microsoft 365 al iniciar la versión de prueba de Defender para empresas (versión preliminar), puede usar el servicio de Azure AD existente. 
> - Si usas [Microsoft 365 Empresa Premium](../../business/index.yml) al iniciar la versión de prueba de Defender para empresas (versión preliminar), tienes la opción de administrar dispositivos en Microsoft Intune. 

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 2: Asignar roles y permisos en Microsoft Defender para empresas (versión preliminar)](mdb-roles-permissions.md) 
 
