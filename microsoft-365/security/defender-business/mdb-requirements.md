---
title: Requisitos para Microsoft Defender für Unternehmen
description: Microsoft Defender für Unternehmen de licencia, hardware y software
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 9fd082160640c239424ec75ff58c695a0175d630
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634941"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender für Unternehmen requisitos

> [!IMPORTANT]
> Microsoft Defender für Unternehmen se está implementando para [Microsoft 365 Business Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En este artículo se describen los requisitos para Microsoft Defender für Unternehmen.

## <a name="what-to-do"></a>Qué hacer

1. [Revise los requisitos y asegúrese de cumplirlos](#review-the-requirements).

2. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Por favor, <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">haga nuestra breve encuesta sobre Microsoft Defender für Unternehmen</a>. Nos encantaría conocer su opinión.
>

## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para configurar y usar Microsoft Defender für Unternehmen. <br/><br/>

| Requisito | Descripción |
|:---|:---|
| Suscripción  | Microsoft 365 Empresa Premium <br/>--- o ---<br/>Microsoft Defender für Unternehmen (independiente; actualmente en versión preliminar). <br/><br/> Consulte [How to get Microsoft Defender für Unternehmen](get-defender-business.md).<br/><br/>Ten en cuenta que si tienes varias suscripciones, la suscripción más alta tiene prioridad. Por ejemplo, si tiene Pertahanan Microsoft untuk Titik Akhir plan 2 (comprada o suscripción de prueba) y obtiene Microsoft Defender für Unternehmen, Defender for Endpoint Plan 2 tiene prioridad. En este caso, no verá la experiencia de Defender para empresas.  |
| Datacenter | Una de las siguientes ubicaciones de centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |
| Cuentas de usuario | Las cuentas de usuario se crean en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/><br/>Microsoft Defender für Unternehmen licencias se asignan en el Centro de administración de Microsoft 365<br/><br/>Para obtener ayuda con esta tarea, consulte [Agregar usuarios y asignar licencias](../../admin/add-users/add-users.md). |
| Permissions  | Para registrarse en Microsoft Defender für Unternehmen, debe ser un administrador global.<br/><br/>Para tener acceso al portal Microsoft 365 Defender, los usuarios deben tener uno de los [siguientes roles Azure AD](mdb-roles-permissions.md) asignados: <br/>- Lector de seguridad<br/>- Administrador de seguridad<br/>- Administrador global<br/><br/>Para obtener más información, consulte [Roles and permissions in Microsoft Defender für Unternehmen](mdb-roles-permissions.md). |
| Requisitos de los exploradores | Microsoft Edge o Google Chrome |
| Sistema operativo | Para administrar dispositivos en Microsoft Defender für Unternehmen, los dispositivos deben ejecutar uno de los siguientes sistemas operativos: <br/>- Windows 10 商務版 o posterior <br/>- Windows 10 Professional o posterior <br/>- Windows 10 Enterprise o posterior <br/><br/>Asegúrese de que [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) está instalado. <br/><br/>Si ya estás administrando dispositivos en Microsoft Intune (o Microsoft Endpoint Manager), puedes incorporar esos dispositivos a Defender para empresas. |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) se usa para administrar los permisos de usuario y los grupos de dispositivos. Azure AD se incluye en la suscripción de Defender para empresas. 
> - Si no tiene una suscripción Microsoft 365 antes de iniciar la prueba, Azure AD se aprovisionará durante el proceso de activación. 
> - Si tiene otra suscripción Microsoft 365 al iniciar la versión de prueba de Defender para empresas, puede usar el servicio de Azure AD existente. 
> - Si estás [usando Microsoft 365 Business Premium al](../../business/index.yml) iniciar la versión de prueba de Defender para empresas, tienes la opción de administrar dispositivos en Microsoft Intune. 

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 2: Asignar roles y permisos en Microsoft Defender für Unternehmen](mdb-roles-permissions.md) 
 