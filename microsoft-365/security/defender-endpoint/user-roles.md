---
title: Creación y administración de roles para el control de acceso basado en rol
description: Cree roles y defina los permisos asignados al rol como parte de la implementación del control de acceso basado en rol en el Microsoft 365 Defender
keywords: roles de usuario, roles, acceso a rbac
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 868c3e17ed818c2599cefd8124f1f081cfd7ae9e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67699675"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Creación y administración de roles para el control de acceso basado en rol

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Creación de roles y asignación del rol a un grupo de Azure Active Directory

Los pasos siguientes le guían sobre cómo crear roles en Microsoft 365 Defender. Se supone que ya ha creado grupos de usuarios de Azure Active Directory.

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta con un administrador de seguridad o Administrador global rol asignado.

2. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).

3. Seleccione **Agregar elemento**.

4. Escriba el nombre del rol, la descripción y los permisos que desea asignar al rol.

5. Seleccione **Siguiente** para asignar el rol a un grupo de seguridad de Azure AD.

6. Use el filtro para seleccionar el grupo de Azure AD al que desea agregar este rol.

7. **Guarde y cierre**.

8. Aplique los valores de configuración.

> [!IMPORTANT]
> Después de crear roles, deberá crear un grupo de dispositivos y proporcionar acceso al grupo de dispositivos mediante su asignación a un rol que acaba de crear.

### <a name="permission-options"></a>Opciones de permiso

- **Ver datos**
  - **Operaciones de seguridad** : visualización de todos los datos de operaciones de seguridad en el portal
  - **Administración de amenazas y vulnerabilidades** : visualización de datos de Administración de vulnerabilidades de Defender en el portal

- **Acciones de corrección activas**
  - **Operaciones de seguridad** : realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para la automatización e indicadores
  - **Administración de amenazas y vulnerabilidades: control de excepciones** : creación de nuevas excepciones y administración de excepciones activas
  - **Administración de amenazas y vulnerabilidades: control de correcciones** : envío de nuevas solicitudes de corrección, creación de vales y administración de actividades de corrección existentes

- **Investigación de alertas** : administre alertas, inicie investigaciones automatizadas, ejecute exámenes, recopile paquetes de investigación, administre etiquetas de dispositivo y descargue solo archivos ejecutables portátiles (PE).

- **Administración de la configuración del sistema del portal** : configuración de la configuración de almacenamiento, SIEM y amenazas de la API intel (se aplica globalmente), opciones avanzadas, cargas de archivos automatizadas, roles y grupos de dispositivos

    > [!NOTE]
    > Esta configuración solo está disponible en el rol de administrador de Microsoft Defender para punto de conexión (valor predeterminado).

- **Administración de la configuración de seguridad en Security Center** : configuración de la supresión de alertas, administración de exclusiones de carpetas para la automatización, incorporación y eliminación de dispositivos, administración de notificaciones por correo electrónico y administración del laboratorio de evaluación

- **Funcionalidades de respuesta dinámica**
  - **Comandos básicos** :
    - Inicio de una sesión de respuesta dinámica
    - Realizar comandos de respuesta dinámica de solo lectura en el dispositivo remoto (excepto la copia y ejecución de archivos)
    - Descarga de un archivo desde el dispositivo remoto a través de una respuesta en directo
  - **Comandos avanzados** :
    - Descarga de archivos PE y no PE desde la página de archivos
    - Carga de un archivo en el dispositivo remoto
    - Visualización de un script desde la biblioteca de archivos
    - Ejecución de un script en el dispositivo remoto desde la biblioteca de archivos

Para obtener más información sobre los comandos disponibles, consulte [Investigación de dispositivos con respuesta dinámica](live-response.md).

## <a name="edit-roles"></a>Editar roles

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con la cuenta con el administrador de seguridad o Administrador global rol asignado.

2. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).

3. Seleccione el rol que desea editar.

4. Haga clic en **Editar**.

5. Modifique los detalles o los grupos asignados al rol.

6. Haga clic en **Guardar y cerrar**.

## <a name="delete-roles"></a>Eliminación de roles

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con la cuenta con el administrador de seguridad o Administrador global rol asignado.

2. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).

3. Seleccione el rol que desea eliminar.

4. Haga clic en el botón desplegable y seleccione **Eliminar rol**.

## <a name="related-topic"></a>Tema relacionado

- [Permisos básicos del usuario para acceder al portal](basic-permissions.md)
- [Crear y administrar grupos de dispositivos](machine-groups.md)
