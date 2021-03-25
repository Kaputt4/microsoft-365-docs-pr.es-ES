---
title: Crear y administrar roles para el control de acceso basado en roles
description: Crear roles y definir los permisos asignados al rol como parte de la implementación del control de acceso basado en roles en el Centro de seguridad de Microsoft Defender
keywords: roles de usuario, roles, acceso a rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073987"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Crear y administrar roles para el control de acceso basado en roles

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Crear roles y asignar el rol a un grupo de Azure Active Directory

Los siguientes pasos le guían sobre cómo crear roles en el Centro de seguridad de Microsoft Defender. Se supone que ya ha creado grupos de usuarios de Azure Active Directory.

1. Inicie sesión en [el Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/) con una cuenta con un administrador de seguridad o un rol de administrador global asignado.

2. En el panel de navegación, seleccione **Configuración > Roles**.

3. Seleccione **Agregar elemento**.

4. Escriba el nombre, la descripción y los permisos del rol que desee asignar al rol.

5. Seleccione **Siguiente** para asignar el rol a un grupo de seguridad de Azure AD.

6. Use el filtro para seleccionar el grupo de Azure AD al que desea agregar a este rol.

7. **Guardar y cerrar**.

8. Aplica las opciones de configuración.

> [!IMPORTANT]
> Después de crear roles, tendrás que crear un grupo de dispositivos y proporcionar acceso al grupo de dispositivos al asignarlo a un rol que acaba de crear.

### <a name="permission-options"></a>Opciones de permisos

- **Ver datos**
    - **Operaciones de seguridad:** ver todos los datos de operaciones de seguridad en el portal
    - **Administración de amenazas y vulnerabilidades:** ver los datos de administración de amenazas y vulnerabilidades en el portal

- **Acciones de corrección activas**
    - **Operaciones de seguridad:** realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para automatización e indicadores
    - **Administración de amenazas y vulnerabilidades: control de excepciones:** crear nuevas excepciones y administrar excepciones activas
    - **Administración de amenazas y vulnerabilidades: control de** corrección: enviar nuevas solicitudes de corrección, crear vales y administrar las actividades de corrección existentes

- **Investigación de alertas:** administrar alertas, iniciar investigaciones automatizadas, ejecutar exámenes, recopilar paquetes de investigación, administrar etiquetas de dispositivo y descargar solo archivos ejecutables portátiles (PE) 

- **Administrar la configuración del** sistema del portal: configurar las opciones de almacenamiento, SIEM y la API intel de amenazas (se aplica globalmente), la configuración avanzada, las cargas automatizadas de archivos, los roles y los grupos de dispositivos

    > [!NOTE]
    > Esta configuración solo está disponible en el rol Administrador de Microsoft Defender para puntos de conexión (predeterminado).

- **Administrar la configuración** de seguridad en el Centro de seguridad: configure la configuración de supresión de alertas, administre las exclusiones de carpetas para la automatización, los dispositivos integrados y externos, y administre las notificaciones de correo electrónico, administre el laboratorio de evaluación

- **Capacidades de respuesta en directo**
    - **Comandos** básicos:
        - Iniciar una sesión de respuesta en directo
        - Realizar comandos de respuesta en directo de solo lectura en dispositivo remoto (excluyendo la copia y ejecución de archivos
    - **Comandos** avanzados:
        - Descargar un archivo desde el dispositivo remoto a través de una respuesta en directo
        - Descargar archivos PE y que no son PE de la página de archivos
        - Cargar un archivo en el dispositivo remoto
        - Ver un script desde la biblioteca de archivos
        - Ejecutar un script en el dispositivo remoto desde la biblioteca de archivos

Para obtener más información sobre los comandos disponibles, consulta [Investigar dispositivos con live response](live-response.md).
  
## <a name="edit-roles"></a>Editar roles

1. Inicie sesión en [el Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/) con una cuenta con el administrador de seguridad o el rol de administrador global asignado.

2. En el panel de navegación, seleccione **Configuración > Roles**.

3. Seleccione el rol que desea editar.

4. Haga clic en **Editar**.

5. Modifique los detalles o los grupos asignados al rol. 

6. Haga **clic en Guardar y cerrar**.

## <a name="delete-roles"></a>Eliminar roles

1. Inicie sesión en [el Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/) con una cuenta con el administrador de seguridad o el rol de administrador global asignado.

2. En el panel de navegación, seleccione **Configuración > Roles**.

3. Seleccione el rol que desea eliminar.

4. Haga clic en el botón desplegable y seleccione **Eliminar rol**.

## <a name="related-topic"></a>Tema relacionado

- [Permisos básicos del usuario para acceder al portal](basic-permissions.md)
- [Crear y administrar grupos de dispositivos](machine-groups.md)
