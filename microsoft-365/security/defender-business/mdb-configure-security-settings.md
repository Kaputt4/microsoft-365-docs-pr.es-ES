---
title: Configurar la configuración de seguridad en Microsoft Defender para empresas
description: Configurar las directivas y la configuración de seguridad en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 8f36d64b14dccdb445f1c4115811f571b55e49b8
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423256"
---
# <a name="configure-your-security-settings-and-policies-in-microsoft-defender-for-business-preview"></a>Configurar las directivas y las opciones de seguridad en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Después de incorporar los dispositivos de la empresa a Microsoft Defender para empresas (versión preliminar), el siguiente paso es ver y, si es necesario, editar la configuración de seguridad y las directivas. 

## <a name="what-to-do"></a>Qué hacer

1. [Elija dónde administrar la configuración de seguridad y las directivas](#choose-where-to-manage-security-settings-and-policies).

2. [Ver la configuración de seguridad y las directivas](#view-your-security-settings-and-policies). 

3. [Continúe con los pasos siguientes](#next-steps).

## <a name="choose-where-to-manage-security-settings-and-policies"></a>Elegir dónde administrar las directivas y la configuración de seguridad

Cuando se trata de administrar la configuración de seguridad y las directivas, puede elegir entre varias opciones, como se describe en la tabla siguiente: <br/><br/>

| Opción | Descripción |
|:---|:---|
| **Use la configuración y directivas de seguridad predeterminadas en el portal de Microsoft 365 Defender** (*recomendado*) | Defender para empresas (versión preliminar) se diseñó para la pequeña o mediana empresa ocupada en mente. Las directivas y la configuración de seguridad predeterminadas de Defender para empresas están diseñadas para proteger los dispositivos de su empresa desde el primer día.<br/><br/>Puede usar el portal de Microsoft 365 Defender ( ) para ver y administrar la [https://security.microsoft.com/](https://security.microsoft.com/) configuración de seguridad y las directivas.<br/><br/>Para obtener más información, consulta [Ver o editar directivas de dispositivo.](mdb-view-edit-policies.md) |
| **Use Microsoft Endpoint Manager** | Si su empresa usa Microsoft Endpoint Manager para administrar directivas y configuraciones de seguridad, puede seguir usando Endpoint Manager y aplicar directivas y configuraciones de seguridad a algunos o todos los dispositivos. Para obtener más información, consulte [Manage device security with endpoint security policies in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). <br/><br/>Considere la posibilidad de cambiar al [proceso de configuración simplificado en Defender para empresas](mdb-simplified-configuration.md). Si realiza el cambio, se le pedirá que elimine las directivas de seguridad existentes en Microsoft Endpoint Manager antes de continuar con el proceso de configuración simplificado en Defender para empresas. Eliminar las directivas en Microsoft Endpoint Manager ayuda a evitar conflictos de directivas más adelante. |

> [!TIP]
> Si desea registrarse en el programa de vista previa de Microsoft Defender para empresas, visite [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) . Para obtener más información, consulta [Obtener Microsoft Defender para empresas (versión preliminar).](get-defender-business.md)

## <a name="view-your-security-settings-and-policies"></a>Ver la configuración de seguridad y las directivas

Para ver la configuración de seguridad y las directivas, use uno de los procedimientos de la tabla siguiente:
<br/><br/>

| Portal | Procedure |
|:---|:---|
| Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) ) | 1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por **ejemplo, Windows clientes**).<br/><br/>4. Expanda una categoría (como Protección de **última** generación o **Firewall)** para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Ver o editar directivas de dispositivos](mdb-view-edit-policies.md)<br/>- [Comprender las opciones de configuración de próxima generación](mdb-next-gen-configuration-settings.md)<br/>- [Configuración del firewall](mdb-firewall.md)  |
| Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora estás en el Centro de administración Microsoft Endpoint Manager administración.<br/><br/>2. Seleccione Seguridad **del extremo**.<br/><br/>3. Seleccione una categoría, como **Antivirus,** **Firewall,** Detección y respuesta de extremos **o** **Reducción** de superficie de ataque para ver las directivas de esa categoría. <br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Microsoft Endpoint Manager, empiece por Administrar la seguridad de puntos de conexión [en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="next-steps"></a>Siguientes pasos

Continúe con una o varias de las siguientes tareas:

- [Introducción al uso de Microsoft Defender para empresas (versión preliminar)](mdb-get-started.md)

- [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Ver o editar directivas en Microsoft Defender para empresas (versión preliminar)](mdb-view-edit-policies.md)

