---
title: Configurar orígenes de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar) en el Centro Microsoft 365 administración
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Obtenga información sobre cómo configurar orígenes de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar) en el centro Microsoft 365 administración.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e6ab6306db9a5ac9d91226431e5876cc244499
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245425"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Configurar orígenes de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar) en el Centro Microsoft 365 administración

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. 

Los administradores del centro de administración de Microsoft 365, ya sea por sí mismos o asignando el rol de administrador de conocimientos a individuos seleccionados de la organización, pueden administrar la configuración relacionada con Viva Learning (versión preliminar) y pueden configurar los orígenes de contenido de aprendizaje.

El administrador selecciona qué otros orígenes de contenido de aprendizaje (por ejemplo, SharePoint o orígenes de proveedores de contenido de terceros compatibles) estarán disponibles para los usuarios de Viva Learning (versión preliminar). A continuación, el administrador configura esos orígenes para asegurarse de que el contenido está disponible para la búsqueda y la detección y los empleados que usan Viva Learning (versión preliminar) pueden examinarlo.

> [!NOTE]
>  Los usuarios inician sesión en usuarios que no son de Microsoft y LinkedIn Learning Pro aprendizaje en un explorador o visor incrustado. Este aprendizaje configurado está sujeto a los términos de licencia, privacidad y servicio independientes entre su organización y el tercero, y no a los términos de Viva Learning (versión preliminar). Antes de seleccionar este tipo de aprendizaje, compruebe que tiene un acuerdo para la organización y los usuarios.

## <a name="assign-the-knowledge-admin-role-optional"></a>Asignar el rol de administrador de conocimientos (opcional)

Debe ser un administrador Microsoft 365 global para realizar estas tareas.

> [!TIP]
> El administrador de conocimientos debe ser moderadamente técnico y tener credenciales de administrador de SharePoint existentes, preferiblemente alguien que esté bien informado en la parte de educación, aprendizaje, formación o experiencia de los empleados de la organización.

### <a name="add-a-knowledge-admin"></a>Agregar un administrador de conocimientos

Para agregar un administrador de conocimientos para Viva Learning (versión preliminar), siga estos pasos:

1.  En la navegación izquierda del centro Microsoft 365 administración, vaya a **Roles**.

2.  En la **página Roles,** en la **pestaña Azure AD,** seleccione **Administrador de conocimientos.**
 
3.  En el panel **Administrador de** conocimientos, seleccione **Administradores asignados** y, a continuación, **seleccione Agregar**.

     ![Página Roles en el centro Microsoft 365 administración que muestra el panel Administrador de conocimientos para agregar un usuario.](../media/learning/learning-add-knowledge-admin-1.png)

3.  En el **panel Agregar administradores,** seleccione la persona que elija para el rol y, a continuación, **seleccione Agregar**.

     ![Página Roles en el centro Microsoft 365 administración que muestra el panel Agregar administradores para agregar un usuario.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Quitar un administrador de conocimientos

Para quitar un administrador de conocimientos para Viva Learning (versión preliminar), siga estos pasos:

1.  En la navegación izquierda del centro Microsoft 365 administración, vaya a **Roles**.

2.  En la **página Roles,** en la **pestaña Azure AD** y, a continuación, seleccione Administrador de **conocimientos.**
 
3.  En el panel **Administrador de** conocimientos, en la pestaña Administradores **asignados,** seleccione Quitar **y,** a continuación, seleccione la persona que desea quitar del rol. Para confirmarlo, seleccione **Quitar**.

     ![Página Roles en el centro Microsoft 365 administración que muestra el panel Administradores asignados para quitar un usuario.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Configuración de los orígenes de contenido de aprendizaje

Debe ser un administrador Microsoft 365 global o administrador de conocimientos para realizar estas tareas.

Para configurar la configuración de orígenes de contenido de aprendizaje en Viva Learning, siga estos pasos:

1.  En la navegación izquierda del centro Microsoft 365 administración, vaya a **Configuración**  >  **configuración de la organización.**

2.  En la **página Configuración de** la organización, en la pestaña **Servicios,** seleccione **Viva Learning (versión preliminar).**

     ![Configuración en el Centro Microsoft 365 administración que muestra la aplicación de aprendizaje que aparece.](../media/learning/learning-sharepoint-configure1.png)

3.  En el **panel Viva Learning (versión** preliminar), seleccione los orígenes de contenido de aprendizaje que desea configurar para la organización y, a continuación, **seleccione Guardar**.

     ![Panel de aprendizaje en el Centro Microsoft 365 administración que muestra las opciones de orígenes de contenido.](../media/learning/learning-sharepoint-configure2.png)

Entre todos los orígenes de aprendizaje que existen, algunos se habilitarán de forma predeterminada. Estos orígenes de aprendizaje incluyen:

- LinkedIn Learning (contenido gratuito)
- Microsoft Learn
- Microsoft 365 Formación

> [!NOTE]
> El contenido gratuito de LinkedIn se proporciona a los usuarios en virtud de las directivas de privacidad y el contrato de usuario de LinkedIn. LinkedIn recibirá la dirección IP del usuario, las cookies establecidas anteriormente por LinkedIn y establecerá una nueva cookie para realizar un seguimiento del uso del contenido gratuito. No es necesario que los usuarios inicien sesión con LinkedIn para recibir contenido gratuito.<br><br>
Para el contenido premium de LinkedIn, su organización necesita una suscripción para que su equipo pueda acceder a ese contenido. Los usuarios tendrán que iniciar sesión en LinkedIn para obtener acceso a ese aprendizaje, que se proporciona en los términos de los términos de usuario y de su organización con LinkedIn.<br><br> Para contenido que no sea de Microsoft (excepto contenido gratuito de LinkedIn), asegúrese de que su organización tiene una suscripción para que los usuarios accedan a ese contenido mediante una cuenta de trabajo antes de conectarlo a Viva Learning (versión preliminar). Las suscripciones personales de los usuarios a proveedores de aprendizaje que no son de Microsoft no se integrarán con Viva Learning (versión preliminar). Los usuarios inician sesión en usuarios que no son de Microsoft y LinkedIn Learning Pro aprendizaje en un explorador o visor incrustado. Si los usuarios navegan a contenido donde no tienen una suscripción organizativa, es posible que vean una página de proveedor en la que podrían registrarse para una suscripción individual. Todo el aprendizaje que no es de Microsoft se proporciona bajo los términos del proveedor que no es de Microsoft y no como parte de Viva Learning. 

Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen. Si un origen está habilitado, se mostrará una marca de verificación.

## <a name="third-party-content-providers"></a>Proveedores de contenido de terceros 

El conjunto de proveedores de aprendizaje conectados disponibles puede cambiar en cualquier momento. Más proveedores se unirán a medida que el programa crezca. Los proveedores disponibles también pueden optar por interrumpir su conexión con Viva Learning (versión preliminar).

### <a name="skillsoft-as-a-content-source"></a>Skillsoft como origen de contenido  

Para Viva Learning (versión preliminar), los usuarios que tienen Skillsoft habilitado y deciden ver contenido de Skillsoft llegarán a una página de Percipio que les pida que introduzcan el nombre del sitio de Percipio de la organización. Después de que los usuarios introduzcan el nombre del sitio de la organización, se les dirigirá a la página para que inicien sesión en el sitio de Percipio de la organización. Los usuarios iniciarán sesión con sus credenciales existentes y verán el contenido que seleccionaron originalmente. Se pedirá a los usuarios que introduzcan el nombre del sitio de Percipio solo una vez, hasta que se borra la memoria caché del explorador. Para simplificar esta experiencia para los usuarios, se recomienda incluir el nombre del sitio de Percipio en las comunicaciones internas que envíe sobre Viva Learning (versión preliminar).

Esto está pensado para ser una experiencia temporal para la versión preliminar y estamos trabajando con Skillsoft para habilitar la integración específica del inquilino para la disponibilidad general, lo que omitirá el paso que requiere que los usuarios proporcionen el nombre del sitio Percipio de su organización. 

### <a name="details-on-microsoft-substrate"></a>Detalles sobre el substrato de Microsoft  

En el caso de los datos que copie en Viva Learning (versión preliminar) de un servicio que no sea de Microsoft (proveedor de aprendizaje o sistema de administración de aprendizaje), no podrá extraer, corregir ni eliminar directamente los datos en Viva Learning (versión preliminar). Actualizamos los datos que importa de proveedores que no son de Microsoft con prontitud para reflejar los cambios y eliminaciones en los datos de origen que no son de Microsoft.

Debe trabajar con el proveedor del servicio que no es de Microsoft para obtener acceso, corregir, eliminar o extraer datos según los términos de licencia, servicio o privacidad del servicio que no sea de Microsoft. Los cambios realizados allí se reflejarán en los datos procesados para su uso en Viva Learning (versión preliminar) una vez completados los ciclos de actualización de datos del servicio que no es de Microsoft y Viva Learning (versión preliminar). Si desactiva la conexión entre Viva Learning (Versión preliminar) y un servicio que no es de Microsoft, se eliminarán todos los datos que haya importado anteriormente desde ese servicio. 

## <a name="next-step"></a>Paso siguiente

[Configurar SharePoint como origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar)](configure-sharepoint-content-source.md)