---
title: Ver o editar directivas en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre cómo ver, editar, crear y eliminar directivas de protección de próxima generación en Microsoft Defender para empresas (versión preliminar)
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
ms.openlocfilehash: aed09fd10f3381b4d167ea31e303fc2cbce7e8f3
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508340"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business-preview"></a>Ver o editar directivas en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En Microsoft Defender para empresas (versión preliminar), la configuración de seguridad se configura mediante directivas. Hay dos tipos principales de directivas en Defender para empresas (versión preliminar):

- **Directivas de protección de próxima generación,** que determinan cómo se configuran Antivirus de Microsoft Defender y otras características de protección contra amenazas
- **Directivas de firewall,** que determinan qué tráfico de red puede fluir hacia y desde los dispositivos de la empresa

**En este artículo se describe cómo**:

- [Ver las directivas existentes](#view-your-existing-policies)
- [Editar una directiva existente](#edit-an-existing-policy)

> [!TIP]
> Si desea agregar una nueva directiva, vea [Create a new policy](mdb-create-new-policy.md).

## <a name="view-your-existing-policies"></a>Ver las directivas existentes

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente)** y el tipo de directiva (como **la protección de última** generación y **firewall).** 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes)** y, a continuación, revise la lista de directivas en las categorías Protección de próxima generación y  **Firewall.** 

4. Para ver más detalles sobre una directiva, seleccione su nombre. Se abrirá un panel lateral que proporciona más información sobre esa directiva, como qué dispositivos están protegidos por esa directiva.

## <a name="edit-an-existing-policy"></a>Editar una directiva existente

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente)** y el tipo de directiva (como **la protección de última** generación y **firewall).** 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes)** y, a continuación, revise la lista de directivas en las categorías Protección de próxima generación y  **Firewall.** 

4. Para editar una directiva, seleccione su nombre y, a continuación, **elija Editar**.

5. En la **pestaña Información general,** revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

6. En la **pestaña Grupos de dispositivos,** determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para mantener el grupo de dispositivos seleccionado tal como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, seleccione **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, selecciona **Crear nuevo grupo** y, a continuación, configura el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulta [Grupos de dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-create-edit-device-groups.md).)
   - Para aplicar la directiva a otro grupo de dispositivos, selecciona **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

7. En la **pestaña Configuración,** revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de próxima generación](mdb-next-gen-configuration-settings.md)   
   - [Configuración del firewall](mdb-firewall.md)

   Después de especificar la configuración de protección de próxima generación, elija **Siguiente**.

8. En la **pestaña Revisar la directiva,** revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.


## <a name="next-steps"></a>Pasos siguientes

Elija una o varias de las siguientes tareas:

- [Administrar dispositivos](mdb-manage-devices.md)

- [Crear una nueva directiva en Microsoft Defender para empresas (versión preliminar)](mdb-create-new-policy.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)