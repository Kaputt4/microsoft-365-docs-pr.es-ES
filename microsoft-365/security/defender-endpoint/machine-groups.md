---
title: Creación y administración de grupos de dispositivos en Microsoft Defender para punto de conexión
description: Cree grupos de dispositivos y establezca niveles de corrección automatizados en ellos mediante la confirmación de las reglas que se aplican en el grupo.
keywords: grupos de dispositivos, grupos, corrección, nivel, reglas, grupo de aad, rol, asignación, clasificación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 3b163bfd62852bdd5d0edfebfa33457c09963df6
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67514397"
---
# <a name="create-and-manage-device-groups"></a>Crear y administrar grupos de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Azure Active Directory
- Office 365
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En un escenario empresarial, a los equipos de operaciones de seguridad normalmente se les asigna un conjunto de dispositivos. Estos dispositivos se agrupan en función de un conjunto de atributos, como sus dominios, nombres de equipo o etiquetas designadas.

En Microsoft Defender para punto de conexión, puede crear grupos de dispositivos y usarlos para:

- Limitar el acceso a alertas y datos relacionados a grupos de usuarios específicos de Azure AD con [roles de RBAC asignados](rbac.md)
- Configuración de diferentes opciones de corrección automática para diferentes conjuntos de dispositivos
- Asignar niveles de corrección específicos para aplicar durante las investigaciones automatizadas
- En una investigación, filtre la **lista Dispositivos** a grupos de dispositivos específicos mediante el filtro **Grupo** .

Puede crear grupos de dispositivos en el contexto del acceso basado en rol (RBAC) para controlar quién puede realizar acciones específicas o ver información mediante la asignación de los grupos de dispositivos a un grupo de usuarios. Para obtener más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

> [!TIP]
> Para obtener una visión completa de la aplicación RBAC, lea: [¿Su SOC se ejecuta de forma plana con RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)?

Como parte del proceso de creación de un grupo de dispositivos, hará lo siguiente:

- Establezca el nivel de corrección automatizada para ese grupo. Para obtener más información sobre los niveles de corrección, consulte [Uso de la investigación automatizada para investigar y corregir amenazas](automated-investigations.md).
- Especifique la regla de coincidencia que determina qué grupo de dispositivos pertenece al grupo en función del nombre del dispositivo, el dominio, las etiquetas y la plataforma del sistema operativo. Si un dispositivo también coincide con otros grupos, solo se agrega al grupo de dispositivos con la clasificación más alta.
- Seleccione el grupo de usuarios de Azure AD que debe tener acceso al grupo de dispositivos.
- Clasificar el grupo de dispositivos en relación con otros grupos después de crearlo.

> [!NOTE]
> Un grupo de dispositivos es accesible para todos los usuarios si no le asigna ningún grupo de Azure AD.

## <a name="create-a-device-group"></a>Crear un grupo de dispositivos

1. En el panel de navegación, seleccione **Configuración** \> **Permisos de** \> puntos \> **de conexión** **Grupos de dispositivos**.

2. Haga clic en **Agregar grupo de dispositivos**.

3. Escriba el nombre del grupo y la configuración de automatización y especifique la regla de coincidencia que determina qué dispositivos pertenecen al grupo. Consulte [Cómo se inicia la investigación automatizada](automated-investigations.md#how-the-automated-investigation-starts).

    > [!TIP]
    > Si desea usar el etiquetado para agrupar dispositivos, consulte [Creación y administración de etiquetas de dispositivo](machine-tags.md).

4. Obtenga una vista previa de varios dispositivos que coincidirán con esta regla. Si está satisfecho con la regla, haga clic en la pestaña **Acceso de usuario** .

5. Asigne los grupos de usuarios que pueden acceder al grupo de dispositivos que ha creado.

    > [!NOTE]
    > Solo puede conceder acceso a grupos de usuarios de Azure AD que se han asignado a roles de RBAC.

6. Haga clic en **Cerrar**. Se aplican los cambios de configuración.

## <a name="manage-device-groups"></a>Administrar grupos de dispositivos

Puede promover o disminuir la clasificación de un grupo de dispositivos para que se le dé mayor o menor prioridad durante la coincidencia. Cuando un dispositivo coincide con más de un grupo, solo se agrega al grupo de clasificación más alto. También puede editar y eliminar grupos.

> [!WARNING]
> La eliminación de un grupo de dispositivos puede afectar a las reglas de notificación por correo electrónico. Si un grupo de dispositivos está configurado en una regla de notificación por correo electrónico, se quitará de esa regla. Si el grupo de dispositivos es el único grupo configurado para una notificación por correo electrónico, esa regla de notificación por correo electrónico se eliminará junto con el grupo de dispositivos.

De forma predeterminada, todos los usuarios con acceso al portal pueden acceder a los grupos de dispositivos. Para cambiar el comportamiento predeterminado, asigne grupos de usuarios de Azure AD al grupo de dispositivos.

Los dispositivos que no coinciden con ningún grupo se agregan al grupo Dispositivos no agrupados (valor predeterminado). No puede cambiar la clasificación de este grupo ni eliminarlo. Sin embargo, puede cambiar el nivel de corrección de este grupo y definir los grupos de usuarios de Azure AD que pueden acceder a este grupo.

> [!NOTE]
> La aplicación de cambios en la configuración del grupo de dispositivos puede tardar hasta varios minutos.

### <a name="add-device-group-definitions"></a>Agregar definiciones de grupo de dispositivos

Las definiciones de grupos de dispositivos también pueden incluir varios valores para cada condición. Puede establecer varias etiquetas, nombres de dispositivo y dominios en la definición de un único grupo de dispositivos.

1. Cree un nuevo grupo de dispositivos y, a continuación, seleccione la pestaña **Dispositivos** .
2. Agregue el primer valor para una de las condiciones.
3. Seleccione esta opción `+` para agregar más filas del mismo tipo de propiedad.

> [!TIP]
> Use el operador 'OR' entre filas del mismo tipo de condición, lo que permite varios valores por propiedad.
> Puede agregar hasta 10 filas (valores) para cada tipo de propiedad: etiqueta, nombre de dispositivo, dominio.

Para obtener más información sobre la vinculación a definiciones de grupos de dispositivos, consulte [Grupos de dispositivos: seguridad de Microsoft 365](https://sip.security.microsoft.com/homepage).

## <a name="related-topics"></a>Temas relacionados

- [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md)
- [Crear y administrar etiquetas de dispositivos](machine-tags.md)
- [Obtener una lista de grupos de dispositivos de inquilinos mediante Graph API](/graph/api/device-list-memberof)
