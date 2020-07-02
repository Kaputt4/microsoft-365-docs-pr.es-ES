---
title: Crear y usar una plantilla para agregar usuarios
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
description: Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración cuando se agregan varios usuarios.
ms.openlocfilehash: 29953eb97476799d74e883ed8b20bd5f3382cbf4
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022150"
---
# <a name="create-and-use-a-template-to-add-users"></a>Crear y usar una plantilla para agregar usuarios

Puede crear y usar una plantilla para ahorrar tiempo y estandarizar la configuración cuando se agregan varios usuarios. Las plantillas son especialmente útiles si tiene usuarios que comparten muchas propiedades comunes, como las que tienen el mismo rol y trabajan en la misma ubicación y que necesitan el mismo software. Por ejemplo, es posible que tenga un equipo de ingenieros de soporte técnico que trabajan en la misma oficina.  

## <a name="create-a-template"></a>Creación de una plantilla

Las plantillas son fáciles de crear puede &mdash; seleccionar **a los**usuarios usuarios  >  **activos**  >  **plantillas de usuario**y, a continuación, seleccionar **Agregar una plantilla** de la lista desplegable o puede Agregar un nuevo usuario y, cuando haya terminado, tendrá la opción de guardar la entrada como una plantilla.

Al crear una plantilla después de agregar un usuario, los valores que elija para la siguiente configuración se guardan en la plantilla:

- Nombre de dominio
- Opciones de configuración de contraseña: puede elegir crear contraseñas o hacer que se generen automáticamente
- Elección de contraseña de un solo tiempo: puede solicitar al usuario que cree una contraseña nueva después de iniciar sesión
- Ubicación de la licencia
- Opciones de licencia
- Opciones de aplicación
- Role
- La mayoría de la información del perfil, como el **Perfil del trabajo**, el **Departamento**, la **Oficina**, el teléfono de la **Oficina**y la **dirección postal** 

La siguiente información es específica del usuario y no se guarda en la plantilla:

- Nombre y apellidos
- Nombre completo (DN)
- Nombre de usuario
- Opción para enviar la contraseña por correo electrónico y a quién se envía el correo electrónico de la contraseña
- Número de teléfono móvil

Si opta por no especificar información para una configuración dentro de una sección, ese valor estará en blanco y esa configuración no se mostrará en la plantilla. Por ejemplo, si deja el **puesto** en blanco, cuando revise la plantilla y cuando use la plantilla, el **puesto** no aparecerá en absoluto. Si deja en blanco la configuración de la sección de **perfil** , la sección de **perfil** no mostrará **ninguna** de las plantillas finales.

Al crear una plantilla seleccionando la opción **Agregar una plantilla** , puede elegir los valores que desea completar. Todo lo que quede en blanco aparecerá como **ninguno** de los que se proporcionan en la plantilla.

## <a name="use-a-template-to-add-a-user"></a>Usar una plantilla para agregar un usuario

Para usar una plantilla existente para agregar un usuario:

1. En el centro de administración, seleccione usuarios activos de **usuarios**  >  **Active users**.

2. Seleccione **plantillas de usuario**y, a continuación, seleccione una plantilla en la lista desplegable. (La lista solo contendrá las plantillas que ha creado, no las creadas por otros administradores).

 > [!NOTE]
 > También puede usar una plantilla para agregar un usuario seleccionando **plantillas de usuario**  >  **administrar plantillas**, seleccionando una plantilla y, a continuación, haciendo clic en **Usar plantilla**.

3. Siga los pasos para crear un usuario a partir de la plantilla que ha seleccionado.

> [!NOTE]
> Si no dispone de licencias suficientes para un usuario que agregue, y la información de pago está disponible, intentaremos comprar otra licencia con la información de pago existente. Si la información de pago no está disponible, el usuario se creará como un usuario sin licencia.

## <a name="manage-templates"></a>Administración de plantillas

Puede eliminar fácilmente las plantillas que ya no necesite y agregar otras nuevas. Para eliminar una plantilla:

1. En el centro de administración, seleccione usuarios activos de **usuarios**  >  **Active users**.

2. Seleccione **plantillas**y, a continuación, seleccione **administrar plantillas** en la lista desplegable.

3. Aparecerá una lista de las plantillas. Para eliminar una plantilla, realice uno de los procedimientos siguientes:
    - Seleccione una o más plantillas y, a continuación, seleccione **eliminar**. 
    - Seleccione los puntos suspensivos a la derecha del nombre de la plantilla y, a continuación, seleccione **eliminar**.
    - Seleccione el nombre de la plantilla. Cuando aparezcan los detalles de la plantilla en el lado derecho de la pantalla, seleccione **eliminar plantilla**.

## <a name="related-articles"></a>Artículos relacionados

[Agregar usuarios y asignar licencias al mismo tiempo](add-users.md)

[Quitar un antiguo empleado de Microsoft 365](remove-former-employee.md)
  
