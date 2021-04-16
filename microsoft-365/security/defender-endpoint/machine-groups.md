---
title: Crear y administrar grupos de dispositivos en Microsoft Defender para endpoint
description: Crear grupos de dispositivos y establecer niveles de corrección automatizados en ellos mediante la confidción de las reglas que se aplican en el grupo
keywords: grupos de dispositivos, grupos, corrección, nivel, reglas, grupo de aad, rol, asignación, clasificación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860308"
---
# <a name="create-and-manage-device-groups"></a>Crear y administrar grupos de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Azure Active Directory
- Office 365

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


En un escenario de empresa, los equipos de operaciones de seguridad suelen tener asignado un conjunto de dispositivos. Estos dispositivos se agrupan en función de un conjunto de atributos, como sus dominios, nombres de equipo o etiquetas designadas.

En Microsoft Defender para endpoint, puedes crear grupos de dispositivos y usarlos para:
- Limitar el acceso a alertas y datos relacionados a grupos de usuarios específicos de Azure AD con [roles RBAC asignados](rbac.md) 
- Configurar diferentes opciones de corrección automática para distintos conjuntos de dispositivos
- Asignar niveles de corrección específicos para aplicar durante investigaciones automatizadas
- En una investigación, filtre la lista **Dispositivos** a grupos de dispositivos específicos mediante el **filtro** Grupo.

Puedes crear grupos de dispositivos en el contexto del acceso basado en roles (RBAC) para controlar quién puede realizar acciones específicas o ver información asignando los grupos de dispositivos a un grupo de usuarios. Para obtener más información, vea [Manage portal access using role-based access control](rbac.md).

>[!TIP]
> Para obtener una visión completa de la aplicación RBAC, lea: [¿Su SOC se ejecuta sin formato con RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

Como parte del proceso de creación de un grupo de dispositivos, podrás:
- Establezca el nivel de corrección automatizado para ese grupo. Para obtener más información sobre los niveles de corrección, vea [Use Automated investigation to investigate and remediate threats](automated-investigations.md).
- Especifica la regla de coincidencia que determina qué grupo de dispositivos pertenece al grupo en función del nombre del dispositivo, el dominio, las etiquetas y la plataforma del sistema operativo. Si un dispositivo también coincide con otros grupos, se agrega solo al grupo de dispositivos clasificado más alto.
- Seleccione el grupo de usuarios de Azure AD que debe tener acceso al grupo de dispositivos.
- Clasifice el grupo de dispositivos con respecto a otros grupos después de crearlo.

>[!NOTE]
>Un grupo de dispositivos es accesible para todos los usuarios si no le asigna ningún grupo de Azure AD.

## <a name="create-a-device-group"></a>Crear un grupo de dispositivos

1. En el panel de navegación, seleccione **Configuración Grupos**  >  **de dispositivos**.

2. Haga clic **en Agregar grupo de dispositivos**.

3. Escriba el nombre del grupo y la configuración de automatización y especifique la regla de coincidencia que determina qué dispositivos pertenecen al grupo. Vea [Cómo se inicia la investigación automatizada](automated-investigations.md#how-the-automated-investigation-starts).

    >[!TIP]
    >Si desea agrupar dispositivos por unidad organizativa, puede configurar la clave del Registro para la afiliación de grupo. Para obtener más información sobre el etiquetado de dispositivos, consulta [Crear y administrar etiquetas de dispositivo.](machine-tags.md)

4. Obtenga una vista previa de varios dispositivos que coincidirán con esta regla. Si está satisfecho con la regla, haga clic en la **pestaña Acceso de** usuario.

5. Asigna los grupos de usuarios que pueden tener acceso al grupo de dispositivos que creaste.

    >[!NOTE]
    >Solo puede conceder acceso a grupos de usuarios de Azure AD que se hayan asignado a roles RBAC.

6. Haga clic en **Cerrar**. Se aplican los cambios de configuración.

## <a name="manage-device-groups"></a>Administrar grupos de dispositivos

Puedes promover o disminuir la clasificación de un grupo de dispositivos para que se le de mayor o menor prioridad durante la coincidencia. Cuando un dispositivo coincide con más de un grupo, se agrega solo al grupo clasificado más alto. También puede editar y eliminar grupos.

>[!WARNING]
>Eliminar un grupo de dispositivos puede afectar a las reglas de notificación de correo electrónico. Si un grupo de dispositivos está configurado en una regla de notificación de correo electrónico, se quitará de esa regla. Si el grupo de dispositivos es el único grupo configurado para una notificación de correo electrónico, esa regla de notificación de correo electrónico se eliminará junto con el grupo de dispositivos.

De forma predeterminada, los grupos de dispositivos son accesibles para todos los usuarios con acceso al portal. Puede cambiar el comportamiento predeterminado asignando grupos de usuarios de Azure AD al grupo de dispositivos.

Los dispositivos que no coinciden con ningún grupo se agregan al grupo Dispositivos desagrupados (predeterminado). No puede cambiar la clasificación de este grupo ni eliminarlo. Sin embargo, puede cambiar el nivel de corrección de este grupo y definir los grupos de usuarios de Azure AD que pueden tener acceso a este grupo.

>[!NOTE]
> La aplicación de cambios en la configuración del grupo de dispositivos puede tardar hasta varios minutos.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso al portal mediante el control de acceso basado en roles](rbac.md)
- [Crear y administrar etiquetas de dispositivos](machine-tags.md)
- [Obtener una lista de grupos de dispositivos de inquilino con la API de Graph](https://docs.microsoft.com/graph/api/device-list-memberof)
