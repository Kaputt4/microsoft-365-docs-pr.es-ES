---
title: Trabajar con grupos de dispositivos en Microsoft 365 Empresa Premium
description: Obtenga información sobre los grupos de dispositivos en Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ab20237605e567aff63662100acfc136483c8d33
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406548"
---
# <a name="device-groups-in-microsoft-365-business-premium"></a>Grupos de dispositivos en Microsoft 365 Empresa Premium

Microsoft 365 Empresa Premium la protección de puntos de conexión a través de Microsoft Defender para empresas. Las directivas de protección de dispositivos se aplican a dispositivos a través de determinadas colecciones que se denominan grupos de dispositivos. 

**En este artículo se describe lo siguiente**:  

- [Qué grupos de dispositivos son](#whats-a-device-group)
- [Cómo crear un nuevo grupo de dispositivos](#how-do-i-create-a-new-device-group)

## <a name="whats-a-device-group"></a>¿Qué es un grupo de dispositivos?

Un grupo de dispositivos es una colección de dispositivos que se agrupan debido a determinados criterios especificados, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluyas. 

Con la suscripción, tienes grupos de dispositivos predeterminados que puedes usar. Los grupos de dispositivos predeterminados incluyen todos los dispositivos que están incorporados a Defender para empresas. Sin embargo, también puedes crear nuevos grupos de dispositivos para asignar directivas de protección de dispositivos con una configuración específica a determinados dispositivos. 

Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y los grupos de dispositivos personalizados que definas, se almacenan en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD).

## <a name="how-do-i-create-a-new-device-group"></a>¿Cómo puedo crear un nuevo grupo de dispositivos?

Puedes crear un nuevo grupo de dispositivos mientras estás en el proceso de crear o editar una directiva de protección de dispositivos. 

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**. 

3. Lleve a cabo una de las siguientes acciones:

    1. Seleccione una directiva existente y, a continuación, **elija Editar**.
    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, consulta [Ver o editar directivas en Microsoft Defender para empresas](m365bp-view-edit-create-mdb-policies.md).

4. En el **paso Información general** , revise la información, edite si es necesario y, a continuación, elija **Siguiente**.

5. Elija **+ Crear nuevo grupo**. 

6. Especifique un nombre y una descripción para el grupo de dispositivos y, a continuación, elija **Siguiente**.

7. Selecciona los dispositivos que quieres incluir en el grupo y, a continuación, elige **Crear grupo**.

8. En el **paso Grupos de dispositivos** , revisa la lista de grupos de dispositivos para la directiva. Si es necesario, quite un grupo de la lista. A continuación, elija **Siguiente**.

9. En la **página Configuración** , revise y edite la configuración según sea necesario y, a continuación, elija **Siguiente**. Para obtener más información acerca de estas opciones de configuración, consulte [Understand next-generation configuration settings in Microsoft Defender for Business](../security/defender-business/mdb-next-gen-configuration-settings.md).

10. En el **paso Revisar la directiva** , revise toda la configuración, realice las modificaciones necesarias y, a continuación, elija **Crear directiva** o **Actualizar directiva**.


