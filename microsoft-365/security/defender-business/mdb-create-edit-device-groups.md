---
title: Grupos de dispositivos en Microsoft Defender para empresas
description: Obtenga información sobre los grupos de dispositivos en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 7a6cd07a4231cd1d3744b638ff80ffdea1346090
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317449"
---
# <a name="device-groups-in-microsoft-defender-for-business"></a>Grupos de dispositivos en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En Microsoft Defender para empresas, las directivas se aplican a dispositivos a través de determinadas colecciones que se denominan grupos de dispositivos. 

**En este artículo se describe lo siguiente**:  

- [Qué grupos de dispositivos son](#what-is-a-device-group)   
- [Cómo crear grupos de dispositivos en Defender para empresas](#create-a-new-device-group)

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="what-is-a-device-group"></a>¿Qué es un grupo de dispositivos?

Un grupo de dispositivos es una colección de dispositivos que se agrupan debido a determinados criterios especificados, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluyas. En Microsoft Defender para empresas, las directivas se aplican a dispositivos mediante grupos de dispositivos. 

Defender para empresas incluye grupos de dispositivos predeterminados que puedes usar. Los grupos de dispositivos predeterminados incluyen todos los dispositivos que están incorporados a Defender para empresas. Sin embargo, también puedes crear nuevos grupos de dispositivos para asignar directivas con una configuración específica a determinados dispositivos. 

Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y los grupos de dispositivos personalizados que definas, se almacenan en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD).

## <a name="create-a-new-device-group"></a>Crear un nuevo grupo de dispositivos

Actualmente, en Defender para empresas, puedes crear un nuevo grupo de dispositivos mientras estás en el proceso de crear o editar una directiva, como se describe en el siguiente procedimiento: 

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**. 

3. Lleve a cabo una de las siguientes acciones:

    1. Seleccione una directiva existente y, a continuación, **elija Editar**.
    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, consulta [Ver o editar directivas en Microsoft Defender para empresas](mdb-view-edit-policies.md).

4. En el **paso Información general** , revise la información, edite si es necesario y, a continuación, elija **Siguiente**.

5. Elija **+ Crear nuevo grupo**. 

6. Especifique un nombre y una descripción para el grupo de dispositivos y, a continuación, elija **Siguiente**.

7. Selecciona los dispositivos que quieres incluir en el grupo y, a continuación, elige **Crear grupo**.

8. En el **paso Grupos de dispositivos** , revisa la lista de grupos de dispositivos para la directiva. Si es necesario, quite un grupo de la lista. A continuación, elija **Siguiente**.

9. En la **página Configuración** , revise y edite la configuración según sea necesario y, a continuación, elija **Siguiente**. Para obtener más información acerca de estas opciones, consulte [Configuración](mdb-next-gen-configuration-settings.md).

10. En el **paso Revisar la directiva** , revise toda la configuración, realice las modificaciones necesarias y, a continuación, elija **Crear directiva** o **Actualizar directiva**.

## <a name="next-steps"></a>Pasos siguientes

Elija una o varias de las siguientes tareas:

- [Ver o editar directivas](mdb-view-edit-policies.md)

- [Crear una nueva directiva](mdb-create-new-policy.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)