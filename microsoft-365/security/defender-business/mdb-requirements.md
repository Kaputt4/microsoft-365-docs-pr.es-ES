---
title: Requisitos para Microsoft Defender para empresas
description: Requisitos de licencia, hardware y software de Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 17954ec9c01a053f847a7d8a74188edf2f4e4091
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525548"
---
# <a name="microsoft-defender-for-business-requirements"></a>Requisitos de Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En este artículo se describen los requisitos para Microsoft Defender para empresas.

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos](#review-the-requirements).

2. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para configurar y usar Microsoft Defender para empresas. <br/><br/>

| Requisito | Descripción |
|:---|:---|
| Suscripción  | Microsoft 365 Empresa Premium <br/>--- o ---<br/>Microsoft Defender para empresas (independiente; actualmente en versión preliminar). <br/><br/> Consulta [Cómo obtener Microsoft Defender para empresas](get-defender-business.md).<br/><br/>Ten en cuenta que si tienes varias suscripciones, la suscripción más alta tiene prioridad. Por ejemplo, si tienes Microsoft Defender para endpoint plan 2 (suscripción comprada o de prueba) y obtienes Microsoft Defender para empresas, Defender for Endpoint Plan 2 tiene prioridad. En este caso, no verá la experiencia de Defender para empresas.  |
| Datacenter | Una de las siguientes ubicaciones de centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |
| Cuentas de usuario | Las cuentas de usuario se crean en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/><br/>Las licencias de Microsoft Defender para empresas se asignan en el Centro de administración de Microsoft 365<br/><br/>Para obtener ayuda con esta tarea, consulte [Agregar usuarios y asignar licencias](../../admin/add-users/add-users.md). |
| Permisos  | Para registrarse en Microsoft Defender para empresas, debe ser administrador global.<br/><br/>Para tener acceso al portal Microsoft 365 Defender, los usuarios deben tener uno de los [siguientes roles Azure AD](mdb-roles-permissions.md) asignados: <br/>- Lector de seguridad<br/>- Administrador de seguridad<br/>- Administrador global<br/><br/>Para obtener más información, consulte [Roles and permissions in Microsoft Defender for Business](mdb-roles-permissions.md). |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo | Para administrar dispositivos en Microsoft Defender para empresas, los dispositivos deben ejecutar uno de los siguientes sistemas operativos: <br/>- Windows 10 Business o posterior <br/>- Windows 10 Professional o posterior <br/>- Windows 10 Enterprise o posterior <br/><br/>Asegúrese de que [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) está instalado. <br/><br/>Si ya estás administrando dispositivos en Microsoft Intune (o Microsoft Endpoint Manager), puedes incorporar esos dispositivos a Defender para empresas. |
| Integración con Microsoft Endpoint Manager  | Si planea incorporar dispositivos con la configuración de seguridad de [Microsoft Defender para](mdb-onboard-devices.md#microsoft-defender-for-business-security-configuration) empresas, se deben cumplir los siguientes requisitos:<br/><br/>Se deben cumplir los requisitos previos para [la administración de seguridad de Microsoft Defender para endpoint](/mem/intune/protect/mde-security-integration).<br/>- Azure AD debe configurarse de modo que se cree confianza entre los dispositivos de la empresa y Azure AD. <br/>- Defender para empresas debe tener habilitada la administración de seguridad en Microsoft Endpoint Manager.<br/><br/>Los dispositivos deben poder conectarse a las siguientes direcciones URL:<br/>- `enterpriseregistration.windows.net`(para el registro en Azure AD)<br/>- `login.microsoftonline.com`(para el registro en Azure AD)<br/>- `*.dm.microsoft.com` (El comodín (*) admite los puntos de conexión de servicio en la nube que se usan para la inscripción, la protección y los informes, y puede cambiar a medida que se escala el servicio). |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) se usa para administrar los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas. 
> - Si no tiene una suscripción Microsoft 365 antes de iniciar la prueba, Azure AD se aprovisionará durante el proceso de activación. 
> - Si tiene otra suscripción Microsoft 365 al iniciar la versión de prueba de Defender para empresas, puede usar el servicio de Azure AD existente. 
> - Si estás [usando Microsoft 365 Empresa Premium al](../../business/index.yml) iniciar la versión de prueba de Defender para empresas, tienes la opción de administrar dispositivos en Microsoft Intune. 

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 2: Asignar roles y permisos en Microsoft Defender para empresas](mdb-roles-permissions.md) 
 