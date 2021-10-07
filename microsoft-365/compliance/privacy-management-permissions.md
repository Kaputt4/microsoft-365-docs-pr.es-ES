---
title: Establecer permisos de usuario y asignar roles en la administración de privacidad (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo configurar los permisos de administración de privacidad y asignar usuarios a grupos de roles.
ms.openlocfilehash: b1db7a9fd0bef1429172fe9afef262be4808c164
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206018"
---
# <a name="set-user-permissions-and-assign-roles-in-privacy-management-preview"></a>Establecer permisos de usuario y asignar roles en la administración de privacidad (versión preliminar)

Para conceder a los miembros de la organización permisos para usar la administración de privacidad, asígnelos a los grupos de roles adecuados de la Centro de cumplimiento de Microsoft 365. Tenga en cuenta que los roles específicos de la administración de privacidad no aparecerán en Azure Active Directory.

## <a name="sign-in-and-set-permissions"></a>Iniciar sesión y establecer permisos

1. Vaya a la [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) y seleccione **Permisos en** la navegación izquierda.  
2. En la lista **desplegable Centro de** cumplimiento, seleccione **Roles**. Aparecerá la lista completa de grupos de roles.
3. Busque el grupo de roles al que desea agregar uno o varios usuarios y active la casilla a la izquierda del nombre del grupo. Vea a continuación una lista de roles de administración de privacidad.  
4. En el panel desplegable de ese grupo, seleccione **Editar en** el **encabezado** Miembros.  
5. Seleccione **Elegir miembros**. Aparecerá otra ventana desplegable.
6. Seleccione **+ Agregar** para elegir uno o varios usuarios para agregar al grupo.  
7. Seleccione la casilla situada junto a los nombres que desea agregar y, a continuación, seleccione el **botón** Agregar en la parte inferior.  
8. Cuando haya terminado de asignar usuarios, seleccione **Listo** y, a continuación, **Guardar** y, a continuación, **Cerrar**.

## <a name="role-groups-and-roles"></a>Roles y grupos de roles

Los miembros deben asignarse a grupos de roles en función de las tareas que necesiten realizar y del nivel de acceso a archivos adecuado. Cada grupo de roles incluye uno o más roles. Estos roles pueden pertenecer a tareas específicas de administración de privacidad o funciones clave que están habilitadas o restringidas para los miembros de ese grupo.  

Los grupos de roles se pueden personalizar si es necesario. Para evitar la pérdida accidental de acceso, se recomienda crear una copia del grupo de roles existente que desee personalizar, asignar a la copia un nombre identificable, realizar y comprobar los cambios realizados en el nuevo grupo y asignarle personas según corresponda.

## <a name="privacy-management-role-group"></a>Grupo de roles de administración de privacidad

Este grupo contiene todos los roles de permisos de administración de privacidad en un solo grupo. Este grupo de roles puede ser un buen ajuste para las organizaciones donde la misma persona puede realizar todas las tareas dentro de la solución de administración de privacidad. La pertenencia a este grupo de roles concederá a esa cuenta acceso total a todas las características de la solución de administración de privacidad.

Los roles incluyen:

- Administración de casos  
- Visor de contenido de clasificación de datos  
- Visor de listas de clasificación de datos  
- Administrador de administración de privacidad  
- Análisis de administración de privacidad  
- Investigación de administración de privacidad  
- Contribución permanente de administración de privacidad  
- Contribución temporal de administración de privacidad  
- Visor de administración de privacidad  
- Administrador de solicitudes de derechos de sujeto  
- View-Only case

## <a name="privacy-management-administrators-role-group"></a>Grupo de roles Administradores de administración de privacidad

Los miembros de este grupo de roles tienen un amplio acceso a las funciones de administración de privacidad, como crear, leer, actualizar y eliminar directivas de administración de privacidad, solicitudes de derechos de sujeto, permisos de administración de privacidad y configuración de administración de privacidad.

Los roles incluyen:

- Administración de casos  
- Administrador de administración de privacidad  
- View-Only case

## <a name="privacy-management-analysts-role-group"></a>Grupo de roles Analistas de administración de privacidad

Los miembros de este grupo de roles actúan como analistas de casos de administración de privacidad. Pueden investigar coincidencias de directivas, ver metadatos de archivos y realizar acciones de corrección. Este grupo no puede tener acceso a archivos completos a través del Explorador de contenido.

Los roles incluyen:

- Administración de casos  
- Visor de listas de clasificación de datos  
- Análisis de administración de privacidad  
- View-Only case

### <a name="privacy-management-investigators-role-group"></a>Grupo de roles De investigadores de administración de privacidad

Los miembros de este grupo actúan como investigadores de datos de administración de privacidad. Pueden investigar coincidencias de directivas, ver el contenido del archivo asociado y realizar acciones de corrección. Este grupo puede tener acceso a los archivos a través del Explorador de contenido.

Los roles incluyen:

- Administración de casos  
- Visor de contenido de clasificación de datos  
- Visor de listas de clasificación de datos  
- Investigación de administración de privacidad  
- View-Only case

## <a name="privacy-management-viewer-role-group"></a>Grupo de roles visor de administración de privacidad

Los miembros de este grupo pueden ver información analítica en la administración de privacidad, como información general, perfil de datos e informes de solicitud de sujeto.

Los roles incluyen:

- Visor de administración de privacidad

## <a name="subject-rights-request-administrators-role-group"></a>Grupo de roles Administradores de solicitudes de derechos de sujeto

Los miembros de este grupo tienen acceso completo para administrar y crear solicitudes de derechos de sujeto.

Los roles incluyen:

- Administrador de solicitudes de derechos de sujeto

## <a name="privacy-management-contributors-role-group"></a>Grupo de roles Colaboradores de administración de privacidad

Los miembros de este grupo tienen acceso de colaborador a solicitudes de derechos de sujeto.  

Los roles incluyen:

- Contribución temporal de administración de privacidad  
- Contribución permanente de administración de privacidad
