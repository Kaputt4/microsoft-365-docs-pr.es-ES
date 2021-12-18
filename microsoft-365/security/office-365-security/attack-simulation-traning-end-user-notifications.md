---
title: Notificaciones de usuario final para el aprendizaje de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear mensajes de correo electrónico de notificación de usuario final para el aprendizaje de simulación de ataques en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.openlocfilehash: bddd0b587e8fbf3007009a070cbd3e7616faac04
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "61561132"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>Notificaciones de usuario final para el aprendizaje de simulación de ataques

En Formación de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, las notificaciones de usuario final son mensajes de correo electrónico que se envían a los usuarios Hay dos tipos básicos de notificaciones:

- **Notificaciones de simulación:** estos mensajes se envían cuando los usuarios están inscritos en cursos y como avisos para los entrenamientos necesarios.
- **Notificaciones de refuerzo positivos:** estos mensajes se envían cuando los usuarios informan de un mensaje de suplantación de identidad simulada.

Para ver la notificación de usuario final disponible, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com> **y, a continuación, vaya a Correo** electrónico & la pestaña Aprendizaje de simulación de \>  \> **ataques** de colaboración. Para ir directamente a la **pestaña Notificaciones de usuario final,** use <https://security.microsoft.com/attacksimulator?viewid=endUserNotification> .

La **pestaña Notificaciones de usuario final** tiene dos pestañas:

- **Notificaciones globales:** contiene las notificaciones integradas y no modificables.
- **Notificaciones de inquilino:** contiene las notificaciones personalizadas que ha creado.

Se muestra la siguiente información para cada notificación:

- **Notificaciones:** el nombre de la notificación.
- **Idioma:** si la notificación contiene varias traducciones, los dos primeros idiomas se muestran directamente. Para ver los idiomas restantes, mantenga el mouse sobre el icono numérico (por ejemplo, **+10**).
- **Tipo**: El valor es Notificación **de simulación** o **Notificación de refuerzo positivo.**
- **Source:** para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Tenant**.
- **Estado**
- **Simulaciones vinculadas**
- **Creado por**: Para notificaciones integradas, el valor es **Microsoft**. Para las notificaciones personalizadas, el valor es el UPN del usuario que creó la notificación.
- **Hora de creación**
- **Modificado por**
- **Hora de la última modificación**

Para buscar una notificación en la lista, use el ![ icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro** de búsqueda para buscar el nombre de la notificación.

Para agrupar las notificaciones por tipo, haga clic ![ en Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupa y,** a continuación, selecciona **Tipo de notificación**. Para desagrupar las notificaciones, seleccione **Ninguno**.

Solo en **la pestaña Notificaciones de inquilino,** haga clic en Filtrar ![ icono.](../../media/m365-cc-sc-filter-icon.png) para filtrar las notificaciones por uno o más idiomas.

Para quitar una o varias columnas que se muestran, haga clic ![ en Personalizar icono de columnas.](../../media/m365-cc-sc-customize-icon.png) **Personalizar columnas**.

Al seleccionar una notificación de la lista, aparece un desplegable de detalles con la siguiente información:

- **Pestaña Vista** previa: ver el mensaje de notificación. Para ver el mensaje en diferentes idiomas, use el **cuadro Seleccionar idioma.**
- **Ficha Detalles:** Ver detalles sobre la notificación:
  - **Descripción de notificación**
  - **Source:** para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Tenant**.
  - **Tipo de notificación**
  - **Modificado por**
  - **Última modificación**

## <a name="create-end-user-notifications"></a>Crear notificaciones de usuario final

En la **pestaña Notificaciones de inquilino,** puede hacer clic ![ en Crear nuevo icono.](../../media/m365-cc-sc-create-icon.png) **Cree nuevo** para iniciar el nuevo asistente para notificaciones de usuario final.

1. En la **página Definir detalles**,** configure las siguientes opciones:
   - **Seleccione tipo de notificación:** **hay disponibles notificaciones de refuerzo positivas** o de **simulación.**
   - **Nombre:** escriba un nombre único.
   - **Descripción:** escriba una descripción opcional.

   Cuando termine, haga clic en **Siguiente**.

2. En la **página Definir contenido,** la única configuración disponible es el **botón Agregar contenido en idioma** empresarial. Al hacer clic en él, aparece un menú desplegable Agregar **contenido** en idioma predeterminado que contiene la siguiente configuración:
   - **Desde el nombre para mostrar**
   - **Desde dirección de correo electrónico**
   - **Seleccione el idioma del correo** electrónico: seleccione un idioma de la lista.
   - **Marca esto como el idioma predeterminado:** dado que este es el primer y único idioma de la notificación, este valor está seleccionado y no puedes cambiarlo.
   - **Asunto:** el valor predeterminado es **Thanks for reporting phish**, pero puede cambiarlo.
   - **Importar correo** electrónico: opcionalmente, puede hacer clic en este botón y, a continuación, hacer clic en Elegir archivo **para** importar un archivo de mensaje de texto sin formato existente.
   - Área de contenido de correo electrónico: hay dos pestañas disponibles:
     - **Pestaña** Texto: un editor de texto enriquecido está disponible para crear el correo electrónico de notificación. Además de la configuración típica de fuente y formato, están disponibles las siguientes opciones:
       - **Etiqueta dinámica:** seleccione entre las siguientes etiquetas:
         - **Insertar nombre**
         - **Insertar apellido**
         - **Insertar UPN**
         - **Insertar dirección de correo electrónico**
         - **Insertar carga**
     - **Pestaña** Código: puede ver y modificar el código HTML directamente.

   Para obtener una vista previa de los resultados, haga clic en el botón **Vista** previa del correo electrónico situado en la parte superior de la página.

   Cuando haya terminado, haga clic en **Guardar**.

   Vuelve a la página Definir **contenido,** donde la notificación que acaba de crear se resume con la siguiente información:

   - **Language**
   - **Asunto**
   - **Categoría**
   - **Acciones:** los siguientes iconos están disponibles:
     - ![Icono editar.](../../media/m365-cc-sc-edit-icon.png) **Editar**
     - ![Icono de vista.](../../media/m365-cc-sc-view-icon.png) **View**
     - ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar:** si solo hay una versión de idioma de la notificación, no se puede eliminar.

   Para agregar una versión de la notificación en un idioma diferente, haga clic ![ en Agregar icono de traducción. ](../../media/m365-cc-sc-create-icon.png) . En el **menú** desplegable Agregar traducción que aparece,  la misma configuración está disponible que en el menú desplegable Agregar contenido en idioma predeterminado que se describió anteriormente. La única diferencia es que puede seleccionar **Marcar esto como el idioma predeterminado** en traducciones adicionales.

   Cuando haya terminado, haga clic en **Guardar**

   Puede repetir estos pasos tantas veces como sea necesario para crear versiones traducidas de la notificación en los 12 idiomas admitidos.

   Cuando haya terminado, haga clic en **Siguiente**

3. En la **página Revisar notificación,** puede revisar los detalles de la notificación.

   Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

   En la **página Nueva notificación de simulación** creada, puede usar los vínculos para crear una nueva notificación, iniciar una simulación o ver todas las notificaciones.

   Cuando haya terminado, haga clic en **Listo**.

De nuevo en la pestaña **Notificaciones de inquilino,** la notificación que creó ahora es una lista.

Al seleccionar una notificación, están disponibles las siguientes opciones adicionales:

Vuelves a la  página Notificación de refuerzo positivo, donde la notificación que acaba de crear aparece ahora en la **lista Seleccionar una notificación de refuerzo** positivo.

- Para modificar la notificación o agregar traducciones adicionales, seleccione la notificación y, a continuación, haga clic ![ en Editar icono.](../../media/m365-cc-sc-edit-icon.png) **Edit notification** to start the notification wizard as previously described (with most values already filled in). Si la notificación ya tiene traducciones para los 12 idiomas admitidos, no puede agregar más traducciones.

- Para crear una copia de una notificación, selecciónelo y, a continuación, haga clic en ![Crear un icono de copia.](../../media/m365-cc-sc-copy-icon.png).

- Para eliminar una notificación, selecciónelo y, a continuación, haga clic en ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png).

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Crear una simulación de ataque de suplantación de identidad](attack-simulation-training.md)

[Automatización de la simulación para el aprendizaje de simulación de ataques](attack-simulation-training-simulation-automations.md)
