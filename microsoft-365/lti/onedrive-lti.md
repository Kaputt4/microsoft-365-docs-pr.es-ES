---
title: Integración de LTI de Microsoft OneDrive con Canvas
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Crear y calificar asignaciones, compilar y mantener contenido del curso, y colaborar en archivos en tiempo real con el LTI de Microsoft OneDrive para Canvas.
ms.openlocfilehash: 405a47ee9ff510e452fa632eaef52b07aba2876b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203912"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integración de LTI de Microsoft OneDrive con Canvas

Este artículo está destinado a administradores de TI educativos que necesitan configurar el LTI de Microsoft OneDrive para Canvas.

Para obtener instrucciones para los formadores sobre cómo usar el LTI de OneDrive en Canvas, consulte [Uso de Microsoft OneDrive con su LMS](https://support.microsoft.com/topic/use-microsoft-onedrive-with-your-lms-c2ddeb48-f695-4267-94f2-14f7ff1b7bdd).

La integración de LTI de Microsoft OneDrive con Canvas es un proceso de dos pasos. El primer paso habilita Microsoft OneDrive en Canvas y el segundo paso hace que el LTI de Microsoft OneDrive esté disponible en los cursos de Canvas.

## <a name="recommended-browser-settings"></a>Configuración recomendada del explorador

- Las cookies deben estar habilitadas para Microsoft OneDrive.
- No se deben bloquear los elementos emergentes para Microsoft OneDrive.

> [!NOTE]
>
> - Las cookies no están habilitadas de forma predeterminada en el modo de incógnito del explorador Chrome y tendrán que estar habilitadas.
> - Microsoft OneDrive LTI funciona en modo privado en el explorador Microsoft Edge. Asegúrese de que no ha bloqueado las cookies (que están habilitadas de forma predeterminada).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Habilitación de LTI de Microsoft OneDrive en Canvas

> [!IMPORTANT]
> La persona que realiza esta integración debe ser administrador de Canvas y administrador del inquilino de Microsoft 365.

1. Inicie sesión en el <a href="https://onedrivelti.microsoft.com/admin" target="_blank">portal de registro de LTI de Microsoft OneDrive</a>.
2. Seleccione el botón **Administración Consentimiento** y acepte los permisos.

   > [!CAUTION]
   > Si no se realiza este paso, el siguiente paso le proporcionará un error y no podrá realizar este paso durante una hora una vez que haya recibido el error.

3. Seleccione el botón **Crear nuevo inquilino de LTI** . En la página Registro de LTI, seleccione **Lienzo** en la lista desplegable y escriba la dirección URL base de la instancia de Canvas.

   > [!NOTE]
   > Si la instancia de Canvas es, por ejemplo, `https://contoso.test.instructure.com`, se debe escribir la dirección URL completa.

   :::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Página de administración de inquilinos de LTI, con un campo desplegable para elegir la plataforma de consumidores LTI y un campo de texto de dirección URL.":::

4. Copie el archivo JSON seleccionando el botón **Copiar** (un icono a la derecha que muestra dos páginas una encima de otra). Esto se usará para generar la clave en Canvas.

   :::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Imagen que muestra el botón copiar que copiará el texto JSON mostrado y lo hará disponible para la generación de claves en Canvas.":::

5. Inicie sesión en la instancia de Canvas como administrador y seleccione **Claves de desarrollador** en el menú del lado izquierdo de la página. En la lista desplegable, cree una clave para desarrolladores eligiendo **Clave LTI** en la lista desplegable de la esquina superior derecha de la página.

   :::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Captura de pantalla que muestra la barra de navegación izquierda con las claves de desarrollador seleccionadas y la entrada de clave LTI seleccionada en una lista desplegable a la derecha de la página.":::

6. En la página Configurar, en la lista desplegable **Método** , seleccione **Pegar JSON** como método y pegue el texto JSON que copió en el paso 4 en el campo de texto que aparece.

    > [!TIP]
    > **Paso opcional:** Si los educadores de la escuela desean controlar por sí mismos qué vínculos aparecen en la navegación de sus cursos, puede modificar el ``default`` parámetro en el JSON copiado. El ``default`` parámetro se establece ``enabled`` en automáticamente; sin embargo, cambiar el ``default`` parámetro para permite a ``disabled`` los educadores elegir la navegación de sus propios cursos.
    >
    > Para obtener más información sobre cómo los educadores pueden modificar sus vínculos de navegación del curso, consulte [Cómo administrar vínculos de navegación del curso?](https://community.canvaslms.com/t5/Instructor-Guide/How-do-I-manage-Course-Navigation-links/ta-p/1020)

7. A continuación, expanda la lista desplegable **Configuración adicional** y establezca el **nivel de privacidad** en **Público**. 
  
   Establecer el **nivel de privacidad** en **Público** permite que los nombres de los miembros del curso aparezcan en otros miembros para la colaboración.

8. Guarde la clave y estará disponible en Canvas en estado **Desactivado** . Active **la clave y** copie la clave especificada en la columna **Detalles** que se usará en el paso siguiente.

   :::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Página Lienzo con la clave establecida en un estado desactivado. Tendrá que estar activada y la clave deberá copiarse de la columna de detalles de esta página.":::

9. Vuelva al portal de registro de LTI de Microsoft OneDrive y pegue la clave en el campo **Id. de cliente de Canvas** . Seleccione **Siguiente** cuando esté listo.

   :::image type="content" source="media/OneDrive-LTI-20.png" alt-text="La página de registro del inquilino de LTI, que muestra el texto JSON y el cuadro de texto en el que se debe copiar la clave.":::

10. Revise y guarde los cambios. Se mostrará un mensaje al registrarse correctamente.

11. Los detalles del registro también se pueden revisar seleccionando el botón **Ver inquilinos LTI** en la página principal.

Las versiones futuras pueden requerir consentimiento adicional del administrador. En esos casos, solo tendrá que repetir los pasos 1 y 2.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Habilitación de LTI de Microsoft OneDrive en los cursos de Canvas

Un administrador de Canvas puede habilitar Microsoft OneDrive LTI para todos los cursos. Si se necesita LTI de Microsoft OneDrive en un curso específico (y no en todos los cursos), el formador del curso debe seguir los mismos pasos dentro de la configuración del curso.

1. Inicie sesión como administrador y vaya a la sección **Configuración** .
2. Vaya a la sección **Aplicaciones** y seleccione el botón **Ver configuraciones de aplicaciones** .
3. Seleccione el botón **Agregar aplicación** .
4. En la lista desplegable **Tipo de configuración** , elija la opción **Por identificador de cliente** .
5. Pegue el valor de la clave de desarrollador generada anteriormente en el campo **Id. de cliente** y seleccione el botón **Enviar** .

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="La página Agregar aplicación, que muestra la opción Por identificador de cliente en el menú desplegable Tipo de configuración.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Configuración de colaboración para LTI de Microsoft OneDrive en cursos de lienzo

Para que las colaboraciones de OneDrive funcionen para educadores y alumnos, asegúrese de que la opción **Herramientas de colaboración externa** está desactivada. Para desactivar la configuración **de la Herramienta de colaboraciones externas** , siga los pasos que se indican a continuación.

1. Inicie sesión en Canvas como administrador y vaya a la sección **Configuración** .
1. Vaya a la sección **Opciones de características** y, a continuación, vaya a la sección **Curso** .
1. Establezca el botón de alternancia **herramienta colaboraciones externas** en la posición de desactivación.

Las colaboraciones se pueden asignar a alumnos individuales y a grupos de alumnos en un curso. Actualmente no se admiten las colaboraciones en grupos de Lienzo.

La asignación a alumnos individuales funciona de forma predeterminada. Para asignar colaboración a grupos de alumnos, siga estos pasos:

1. Inicie sesión en Canvas como administrador y vaya a la sección **Claves de desarrollador** .
1. Busque la clave con el valor `170000000000710` y establézcala **en Activado**.
