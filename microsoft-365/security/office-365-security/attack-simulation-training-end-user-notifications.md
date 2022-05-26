---
title: Notificaciones del usuario final para el aprendizaje de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear mensajes de correo electrónico de notificación del usuario final para el entrenamiento de simulación de ataques en Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.openlocfilehash: 66e3e029e8da203b35285080caa91dca3a51e5c7
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65678842"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>Notificaciones del usuario final para el aprendizaje de simulación de ataques

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

En El entrenamiento de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, las notificaciones del usuario final son mensajes de correo electrónico que se envían a los usuarios Hay dos tipos básicos de notificaciones:

- **Notificaciones de simulación**: estos mensajes se envían cuando los usuarios están inscritos en entrenamientos y como recordatorios de los entrenamientos necesarios.
- **Notificaciones de refuerzo positivas**: estos mensajes se envían cuando los usuarios notifican un mensaje de suplantación de identidad simulado.

Para ver la notificación de usuario final disponible, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>y, a continuación, vaya a **Correo electrónico &** pestaña \> **Biblioteca de contenido de** **simulación** \> de colaboración \> y seleccione **Notificaciones del usuario final**. Para ir directamente a la pestaña **Biblioteca de contenido de simulación** , use <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

**Las notificaciones de usuario final** tienen dos pestañas:

- **Notificaciones globales**: contiene las notificaciones integradas y no modificables.
- **Notificaciones de inquilino:** contiene las notificaciones personalizadas que ha creado.

Se muestra la siguiente información para cada notificación:

- **Notificaciones**: nombre de la notificación.
- **Idioma**: si la notificación contiene varias traducciones, los dos primeros idiomas se muestran directamente. Para ver los idiomas restantes, mantenga el puntero sobre el icono numérico (por ejemplo, **+10**).
- **Tipo**: el valor es **Notificación de simulación** o **Notificación de refuerzo positivo**.
- **Origen**: para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Inquilino**.
- **Estado**
- **Simulaciones vinculadas**
- **Creado por**: para las notificaciones integradas, el valor es **Microsoft**. En el caso de las notificaciones personalizadas, el valor es el UPN del usuario que creó la notificación.
- **Tiempo de creación**
- **Modificado por**
- **Hora de última modificación**

Para buscar una notificación en la lista, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre de la notificación.

Para agrupar las notificaciones por tipo, haga clic en ![Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupe** y, a continuación, seleccione **Tipo de notificación**. Para desagrupar las notificaciones, seleccione **Ninguno**.

En la pestaña Solo **notificaciones de inquilino** , haga clic en ![el icono Filtro.](../../media/m365-cc-sc-filter-icon.png) para filtrar las notificaciones por uno o varios idiomas.

Para quitar una o varias columnas que se muestran, haga clic en ![el icono Personalizar columnas.](../../media/m365-cc-sc-customize-icon.png) **Personalizar columnas**.

Al seleccionar una notificación de la lista, aparece un control flotante de detalles con la siguiente información:

- **Pestaña Vista previa** : vea el mensaje de notificación. Para ver el mensaje en diferentes idiomas, use el cuadro **Seleccionar idioma** .
- **Pestaña Detalles** : vea los detalles sobre la notificación:
  - **Descripción de la notificación**
  - **Origen**: para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Inquilino**.
  - **Tipo de notificación**
  - **Modificado por**
  - **Última modificación**
  - **Simulaciones**
    - **Nombres de simulación**
    - **Estado de la simulación**
    - **Finalizar por**

En el control flotante de detalles de la pestaña **Solo notificaciones de inquilino** , haga clic en **Editar notificación** para modificar la notificación.

## <a name="create-end-user-notifications"></a>Creación de notificaciones de usuario final

En la pestaña **Notificaciones de inquilino** , puede hacer clic en ![el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree nuevo** para iniciar el asistente para notificaciones de usuario final.

1. En la página **Definir detalles** **, configure los siguientes valores:
   - **Seleccionar tipo de notificación**: seleccione uno de los valores siguientes:
     - **Notificación de refuerzo positivo**
     - **Notificación de simulación**
     - **Notificación de asignación de entrenamiento**
     - **Notificación de recordatorio de entrenamiento**
   - **Nombre**: escriba un nombre único.
   - **Descripción**: escriba una descripción opcional.

   Cuando termine, haga clic en **Siguiente**.

2. En la página **Definir contenido** , la única configuración que está disponible es el botón **Agregar contenido en lenguaje empresarial** . Al hacer clic en él, aparece un control flotante **Agregar contenido en idioma predeterminado** que contiene la siguiente configuración:
   - **Desde el nombre para mostrar**
   - **Desde la dirección de correo electrónico**
   - **Seleccione el idioma del correo electrónico**: seleccione un idioma de la lista.
   - **Marque esto como el idioma predeterminado**: dado que este es el primer y único idioma de la notificación, este valor está seleccionado y no se puede cambiar.
   - **Asunto**: El valor predeterminado es **Gracias por informar de phish**, pero puede cambiarlo.
   - **Importar correo electrónico**: opcionalmente, puede hacer clic en este botón y, a continuación, hacer clic en **Elegir archivo** para importar un archivo de mensaje de texto sin formato existente.
   - Área de contenido de correo electrónico: hay dos pestañas disponibles:
     - **Pestaña Texto** : hay disponible un editor de texto enriquecido para crear el correo electrónico de notificación. Además de la configuración típica de fuente y formato, están disponibles las siguientes opciones:
       - **Etiqueta dinámica**: seleccione una de las siguientes etiquetas:
         - **Insertar nombre**
         - **Insertar apellidos**
         - **Insertar UPN**
         - **Insertar dirección de correo electrónico**
         - **Insertar carga útil**
     - **Pestaña Código** : puede ver y modificar el código HTML directamente.

   Para obtener una vista previa de los resultados, haga clic en el botón **Vista previa del correo electrónico** de la parte superior de la página.

   Cuando haya terminado, haga clic en **Guardar**.

   Vuelve a la página **Definir contenido** , donde la notificación que acaba de crear se resume con la siguiente información:

   - **Language**
   - **Asunto**
   - **Categoría**
   - **Acciones**: están disponibles los iconos siguientes:
     - ![Icono de edición.](../../media/m365-cc-sc-edit-icon.png) **Editar**
     - ![Icono de vista.](../../media/m365-cc-sc-view-icon.png) **View**
     - ![Icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**: si solo hay una versión de idioma de la notificación, no se puede eliminar.

   Para agregar una versión de la notificación en otro idioma, haga clic en ![Agregar icono](../../media/m365-cc-sc-create-icon.png) de traducción. En el control flotante **Agregar traducción** que aparece, la misma configuración está disponible que en el control flotante **Agregar contenido en idioma predeterminado** que se describió anteriormente. La única diferencia es que puede seleccionar **Marcar esto como idioma predeterminado** en traducciones adicionales.

   Cuando haya terminado, haga clic en **Guardar.**

   Puede repetir estos pasos tantas veces como sea necesario para crear versiones traducidas de la notificación en los 12 idiomas admitidos.

   Cuando haya terminado, haga clic en **Siguiente.**

3. En la página **Revisar notificación** , puede revisar los detalles de la notificación.

   Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

   En la página **Nueva notificación de simulación creada** , puede usar los vínculos para crear una nueva notificación, iniciar una simulación o ver todas las notificaciones.

   Cuando haya terminado, haga clic en **Listo**.

De nuevo en la pestaña **Notificaciones de inquilino** , la notificación que ha creado ahora es una lista.

Al seleccionar una notificación, están disponibles las siguientes opciones adicionales:

Vuelve a la página **Notificación de refuerzo positivo** , donde la notificación que acaba de crear aparece en la lista **Seleccionar una notificación de refuerzo positiva** .

- Para modificar la notificación o agregar traducciones adicionales, seleccione la notificación y haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edite la notificación** para iniciar el Asistente para notificaciones como se describió anteriormente (con la mayoría de los valores ya rellenados). Si la notificación ya tiene traducciones para los 12 idiomas admitidos, no puede agregar más traducciones.

- Para crear una copia de una notificación, selecciónela y, a continuación, haga clic en ![Cree un icono de copia.](../../media/m365-cc-sc-copy-icon.png).

- Para eliminar una notificación, selecciónela y, a continuación, haga clic en ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png).

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Creación de una simulación de ataque de suplantación de identidad (phishing)](attack-simulation-training.md)

[Automatizaciones de simulación para el entrenamiento de simulación de ataques](attack-simulation-training-simulation-automations.md)
