---
title: Crear y usar una plantilla para agregar usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración al agregar varios usuarios en el Centro de administración de Microsoft 365.
ms.openlocfilehash: b316b5e30a98258ccf0ee6dcf4afd5d190b0faa0
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722052"
---
# <a name="create-and-use-a-template-to-add-users"></a>Crear y usar una plantilla para agregar usuarios

Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración al agregar varios usuarios. Las plantillas son especialmente útiles si tiene usuarios que comparten muchas propiedades comunes, como las que tienen el mismo rol y trabajan en la misma ubicación y las que requieren el mismo software. Por ejemplo, es posible que tenga un equipo de ingenieros de soporte técnico que trabajen en la misma oficina.  

## <a name="create-a-template"></a>Creación de una plantilla

Las plantillas son fáciles de crear&mdash;, puede seleccionar **Usuarios** > **usuarios activos** > **Plantillas de usuario** y, a continuación, seleccionar **Agregar una plantilla** en la lista desplegable, o bien puede agregar un nuevo usuario y, cuando haya terminado, tendrá la opción de guardar la entrada como plantilla.

Al crear una plantilla después de agregar un usuario, los valores que elija para la siguiente configuración se guardan en la plantilla:

- Nombre de dominio
- Opción de configuración de contraseña: puede elegir crear contraseñas o generarlas automáticamente.
- Elección de contraseña única: puede requerir que el usuario cree una nueva contraseña después del primer inicio de sesión
- Ubicación de la licencia
- Opciones de licencia
- Opciones de aplicación
- Rol
- La mayoría de la información de perfil, como **perfil de trabajo**, **departamento**, **oficina**, **teléfono de Office** y **dirección postal** 

La siguiente información es específica del usuario y no se guarda en la plantilla:

- Nombre y apellidos
- Nombre para mostrar
- Nombre de usuario
- Elección para enviar la contraseña por correo electrónico y a quién se envía el correo electrónico de contraseña
- Número de teléfono móvil

Si decide no escribir información para una configuración dentro de una sección, ese valor estará en blanco y esa configuración no se mostrará en la plantilla. Por ejemplo, si deja el **título del trabajo** en blanco, al revisar la plantilla y al usar la plantilla, el **título del trabajo** no aparecerá en absoluto. Si deja en blanco toda la configuración de la sección **Perfil** , la sección **Perfil** mostrará **Ninguno proporcionado** en la plantilla final.

Al crear una plantilla seleccionando la opción **Agregar una plantilla** , puede elegir qué valores completar. Todo lo que se deje en blanco aparecerá como **Ninguno proporcionado** en la plantilla.

## <a name="use-a-template-to-add-a-user"></a>Uso de una plantilla para agregar un usuario

Para usar una plantilla existente para agregar un usuario:

1. En el centro de administración, seleccione **Usuarios** > **usuarios activos**.

2. Seleccione **Plantillas de usuario** y, a continuación, seleccione una plantilla en la lista desplegable. (La lista contendrá solo las plantillas que creó, no las creadas por otros administradores).

   > [!NOTE]
   > También puede usar una plantilla para agregar un usuario seleccionando **Plantillas** >  de usuario **Administrar plantillas**, seleccionando una plantilla y, a continuación, seleccionando **Usar plantilla**.

3. Siga los pasos para crear un usuario a partir de la plantilla seleccionada.

   > [!NOTE]
   > Si no tiene suficientes licencias disponibles para un usuario que agregue y su información de pago está disponible, intentaremos comprar otra licencia con su información de pago existente. Si la información de pago no está disponible, el usuario se creará como un usuario sin licencia.

## <a name="manage-templates"></a>Administrar plantillas

Solo puede eliminar plantillas que ya no necesite y agregar otras nuevas. Para eliminar una plantilla:

1. En el centro de administración, seleccione **Usuarios** > **usuarios activos**.

2. Seleccione **Plantillas** y, a continuación, seleccione **Administrar plantillas** en la lista desplegable.

3. Aparecerá una lista de plantillas. Puede eliminar una plantilla mediante cualquiera de las siguientes acciones:
    - Seleccione una o más plantillas y, a continuación, seleccione **Eliminar**. 
    - Seleccione los tres puntos situados a la derecha del nombre de la plantilla y, a continuación, seleccione **Eliminar**.
    - Seleccione el nombre de la plantilla. Cuando los detalles de la plantilla aparezcan en el lado derecho de la pantalla, seleccione **Eliminar plantilla**.

## <a name="related-articles"></a>Artículos relacionados

[Agregar usuarios y asignar licencias al mismo tiempo](add-users.md)

[Eliminación de un antiguo empleado de Microsoft 365](remove-former-employee.md)
  
