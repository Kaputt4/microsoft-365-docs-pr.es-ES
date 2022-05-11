---
title: Trabajar con grupos de dispositivos en Microsoft 365 Empresa Premium
description: Más información sobre los grupos de dispositivos en Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/16/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 2c218cd2b0f04201f46155a72a916cc7676aaddb
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65320826"
---
# <a name="device-groups-in-microsoft-365-business-premium"></a>Grupos de dispositivos en Microsoft 365 Empresa Premium

Microsoft 365 Empresa Premium incluye protección de puntos de conexión a través de Microsoft Defender para Empresas. Las directivas de protección de dispositivos se aplican a los dispositivos a través de determinadas colecciones denominadas grupos de dispositivos. 

**Esta guía describe**:  

- [Qué son los grupos de dispositivos](#whats-a-device-group)
- [Cómo crear un nuevo grupo de dispositivos](#how-do-i-create-a-new-device-group)

## <a name="whats-a-device-group"></a>¿Qué es un grupo de dispositivos?

Un grupo de dispositivos es una colección de dispositivos que se agrupan debido a determinados criterios especificados, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que se excluyan. 

Con su suscripción, tiene grupos de dispositivos predeterminados que puede usar. Los grupos de dispositivos predeterminados incluyen todos los dispositivos que se incorporan a Defender para Empresas. Sin embargo, también puede crear nuevos grupos de dispositivos para asignar directivas de protección de dispositivos con una configuración específica a determinados dispositivos. 

Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y los grupos de dispositivos personalizados que defina, se almacenan en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD).

## <a name="how-do-i-create-a-new-device-group"></a>Cómo crear un nuevo grupo de dispositivos?

Puede crear un nuevo grupo de dispositivos mientras está creando o editando una directiva de protección de dispositivos. 

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**. 

3. Realice una de las acciones siguientes:

    1. Seleccione una directiva existente y, a continuación, elija **Editar**.
    
    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, vea [Ver o editar directivas en Microsoft Defender para Empresas](m365bp-view-edit-create-mdb-policies.md).

4. En el paso **Información general**, revise la información, edítela si es necesario y, a continuación, elija **Siguiente**.

5. Elija **+ Crear nuevo grupo**. 

6. Especifique un nombre y una descripción para el grupo de dispositivos y, a continuación, elija **Siguiente**.

7. Seleccione los dispositivos que desea incluir en el grupo y, a continuación, elija **Crear grupo**.

8. En el paso **Grupos de dispositivos**, revise la lista de grupos de dispositivos de la directiva. Si es necesario, quite un grupo de la lista. A continuación, elija **Siguiente**.

9. En la página **Opciones de configuración**, revise y edite la configuración según sea necesario y, a continuación, elija **Siguiente**. Para obtener más información acerca de esta configuración, consulte [Comprender las opciones de configuración de última generación en Microsoft Defender para Empresas](../security/defender-business/mdb-next-gen-configuration-settings.md).

10. En el paso **Revisar la directiva**, revise toda la configuración, realice las modificaciones necesarias y, a continuación, elija **Crear directiva** o **Actualizar directiva**.

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha completado las misiones principales, configure sus [equipos de respuesta](m365bp-security-incident-management.md) y [administre su entorno](m365bp-maintain-environment.md).

