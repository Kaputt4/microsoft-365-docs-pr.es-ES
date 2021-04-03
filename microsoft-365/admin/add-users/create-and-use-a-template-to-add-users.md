---
title: Crear y usar una plantilla para agregar usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración al agregar varios usuarios.
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579391"
---
# <a name="create-and-use-a-template-to-add-users"></a>Crear y usar una plantilla para agregar usuarios

Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración al agregar varios usuarios. Las plantillas son especialmente útiles si tiene usuarios que comparten muchas propiedades comunes, como los que tienen el mismo rol y trabajan en la misma ubicación y los que requieren el mismo software. Por ejemplo, es posible que tenga un equipo de ingenieros de soporte técnico que trabajen en la misma oficina.  

## <a name="create-a-template"></a>Creación de una plantilla

Las plantillas son fáciles de crear, puede seleccionar Usuarios Usuarios activos Plantillas de usuario y, a continuación, seleccionar Agregar una plantilla de la lista desplegable, o puede agregar un nuevo usuario y, cuando haya terminado, tendrá la opción de guardar la entrada como &mdash;   >    >  plantilla. 

Al crear una plantilla después de agregar un usuario, los valores que elija para la siguiente configuración se guardan en la plantilla:

- Nombre de dominio
- Opción de configuración de contraseña: puede elegir crear contraseñas o generarlas automáticamente
- Opción de contraseña única: puede requerir que el usuario cree una nueva contraseña después del primer inicio de sesión
- Ubicación de la licencia
- Opciones de licencia
- Opciones de aplicación
- Role
- La mayoría de la información de perfil, como Perfil de **trabajo,** **Departamento,** **Office,** **Teléfono de Office** y Dirección de **calle** 

La siguiente información es específica del usuario y no se guarda en la plantilla:

- Nombre y apellidos
- Nombre para mostrar
- Nombre de usuario
- Elección para enviar la contraseña por correo electrónico y a quién se envía el correo electrónico de contraseña
- Número de teléfono móvil

Si decide no especificar información para una configuración dentro de una sección, ese valor estará en blanco y esa configuración no se mostrará en la plantilla. Por ejemplo, si deja **el** título de trabajo en blanco, al revisar la plantilla y al usar la **plantilla,** el título del trabajo no aparecerá en absoluto. Si dejas en blanco toda la **configuración de** la sección Perfil, la sección **Perfil** mostrará **Ninguno proporcionado** en la plantilla final.

Al crear una plantilla seleccionando la **opción Agregar una** plantilla, puede elegir los valores que desea completar. Todo lo que se deja en blanco aparecerá **como Ninguno proporcionado** en la plantilla.

## <a name="use-a-template-to-add-a-user"></a>Usar una plantilla para agregar un usuario

Para usar una plantilla existente para agregar un usuario:

1. En el Centro de administración, seleccione **Usuarios**  >  **usuarios activos.**

2. Seleccione **Plantillas de usuario** y, a continuación, seleccione una plantilla en la lista desplegable. (La lista solo contendrá las plantillas que haya creado, no las creadas por otros administradores).

   > [!NOTE]
   > También puede usar una plantilla para agregar un usuario seleccionando Plantillas de usuario Administrar plantillas, seleccionando una plantilla y, a continuación,  >   **seleccionando Usar plantilla**.

3. Siga los pasos para crear un usuario a partir de la plantilla seleccionada.

   > [!NOTE]
   > Si no dispone de licencias suficientes para un usuario que agregue y la información de pago esté disponible, intentaremos comprar otra licencia con la información de pago existente. Si la información de pago no está disponible, el usuario se creará como un usuario sin licencia.

## <a name="manage-templates"></a>Administrar plantillas

Solo puede eliminar plantillas que ya no necesite y agregar otras nuevas. Para eliminar una plantilla:

1. En el Centro de administración, seleccione **Usuarios**  >  **usuarios activos.**

2. Seleccione **Plantillas** y, a continuación, **seleccione Administrar plantillas** en la lista desplegable.

3. Aparecerá una lista de plantillas. Puede eliminar una plantilla mediante cualquiera de las acciones siguientes:
    - Seleccione una o más plantillas y, a continuación, **seleccione Eliminar**. 
    - Seleccione los tres puntos a la derecha del nombre de la plantilla y, a continuación, **seleccione Eliminar**.
    - Seleccione el nombre de la plantilla. Cuando aparezcan los detalles de la plantilla en el lado derecho de la pantalla, seleccione **Eliminar plantilla**.

## <a name="related-articles"></a>Artículos relacionados

[Agregar usuarios y asignar licencias al mismo tiempo](add-users.md)

[Quitar un antiguo empleado de Microsoft 365](remove-former-employee.md)
  
