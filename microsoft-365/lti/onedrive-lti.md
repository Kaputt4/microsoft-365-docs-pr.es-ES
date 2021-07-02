---
title: Usar Microsoft OneDrive Learning tools Interoperability
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva aplicación de interoperabilidad Microsoft OneDrive Learning Tools.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257073"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integrar Microsoft OneDrive LTI con Canvas

La integración Microsoft OneDrive LTI con Canvas es un proceso de dos pasos. El primer paso habilita Microsoft OneDrive canvas y el segundo paso hace que el Microsoft OneDrive LTI esté disponible en los cursos de Canvas.

## <a name="recommended-browser-settings"></a>Configuración recomendada del explorador

- Las cookies deben estar habilitadas para Microsoft OneDrive.
- Los elementos emergentes no deben bloquearse Microsoft OneDrive.

> [!NOTE]
> - Las cookies no están habilitadas de forma predeterminada en el modo de incógnito del explorador Chrome y tendrán que estar habilitadas.
> - Microsoft OneDrive LTI funciona en modo privado en Microsoft Edge explorador. Asegúrese de que no ha bloqueado las cookies (que están habilitadas de forma predeterminada).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Habilitar Microsoft OneDrive LTI en canvas

> [!IMPORTANT]
> La persona que realiza esta integración debe ser un administrador de Canvas y un administrador del Microsoft 365 inquilino.

1. Inicie sesión en el <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive de registro de LTI</a>
1. Seleccione el **botón Consentimiento de** administrador y acepte los permisos.
1. Seleccione el **botón Crear nuevo inquilino de LTI.** En la página Registro de LTI, seleccione **Lienzo** en el desplegable y escriba la dirección URL base de la instancia de Canvas.

> [!NOTE]
> Si la instancia de Canvas es, por ejemplo, ]( , se debe especificar la https://contoso.test.instructure.com https://contoso.test.instructure.com) dirección URL completa.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Página de administración de inquilinos de LTI, con un campo desplegable para elegir la plataforma de consumidor de LTI y un campo de texto de dirección URL.":::

4. Copie el JSON seleccionando el **botón Copiar** (un icono de la derecha que muestra dos páginas una encima de otra). Se usará para generar la clave en Canvas.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Imagen que muestra el botón copiar que copiará el texto JSON mostrado y lo hará disponible para la generación de claves en Canvas.":::

5. Inicie sesión en la instancia de Canvas como administrador y seleccione **Claves** de desarrollador en el menú de la parte izquierda de la página. En el desplegable, crea una clave de desarrollador **seleccionando Clave LTI** en el desplegable de la parte superior derecha de la página.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Captura de pantalla que muestra la barra de navegación de la izquierda con las claves de desarrollador seleccionadas y la entrada de clave LTI seleccionada en un desplegable a la derecha de la página.":::

6. En la página Configurar, en el menú desplegable Método, seleccione Pegar **JSON** como método y pegue el texto JSON que copió en el paso 5 en el campo de texto que aparece. 
7. Guarde la clave y estará disponible en Canvas en **estado Desactivado.** Active la tecla **y** copie la clave especificada en la columna **Detalles** que se usará en el paso siguiente.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="La página Canvas con la clave establecida en estado desactivado. Tendrá que estar activada y la clave tendrá que copiarse de la columna de detalles de esta página.":::

8. Vuelva al portal Microsoft OneDrive registro de LTI y pegue la clave en el campo **Identificador de cliente de** Canvas. Seleccione **Siguiente** cuando esté listo.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Página de registro de inquilino de LTI, que muestra el texto JSON y el cuadro de texto en el que se debe copiar la clave.":::

9. Revise y guarde los cambios. Se mostrará un mensaje al registrarse correctamente.
10. Los detalles de registro también se pueden revisar seleccionando el botón Ver **inquilinos de LTI** en la página principal.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Habilitar Microsoft OneDrive LTI en cursos de Canvas

Un administrador de Canvas puede habilitar Microsoft OneDrive LTI para todos los cursos. Si Microsoft OneDrive LTI es necesario en un curso específico (y no en todos los cursos), el profesor del curso debe seguir los mismos pasos dentro de la configuración del curso.

1. Inicie sesión como administrador y vaya a la **Configuración.**
2. Ve a la **sección Aplicaciones** y selecciona el botón **Ver configuraciones de** aplicaciones.
3. Seleccione el **botón Agregar aplicación.**
4. En el **desplegable Tipo de configuración,** elija la **opción Por identificador de** cliente.
5. Pegue el valor de la clave de desarrollador generada anteriormente en el campo **Id.** de cliente y seleccione el **botón Enviar.**

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="La página Agregar aplicación, que muestra la opción Por identificador de cliente en el menú desplegable Tipo de configuración.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Colaboración Configuración para Microsoft OneDrive LTI en cursos de lienzo

> [!NOTE]
> Para que la colaboración funcione para profesores y alumnos, no debe habilitar la configuración de colaboración. Para asegurarse de que la configuración no está habilitada, siga los pasos siguientes.

1. Inicie sesión como administrador y vaya a la **Configuración.**
1. Vaya a **la sección Opciones de** características y, a continuación, vaya a la **sección** Curso.
1. Establezca la **característica Herramienta de colaboraciones externas** para que no esté habilitada.

> [!NOTE]
> La colaboración se puede asignar a alumnos individuales y grupos de alumnos. La asignación a alumnos individuales funciona de forma predeterminada. Para poder asignar colaboración a un grupo de alumnos, siga estos pasos:

1. Inicie sesión como administrador y vaya a la **sección Claves de** desarrollador.
1. Busque la clave con el valor 17000000000710 y estadóla en **On**.
