---
title: Notificaciones del usuario final para el aprendizaje de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear mensajes de correo electrónico de notificación del usuario final para Entrenamiento de simulación de ataque en Microsoft Defender para Office 365 plan 2.
ms.subservice: mdo
ms.openlocfilehash: 6297fafeb572c807a49161b1bd3e11a0820b7686
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481072"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>Notificaciones del usuario final para el aprendizaje de simulación de ataques

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

En Entrenamiento de simulación de ataque en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, las notificaciones del usuario final son mensajes de correo electrónico que se envían a los usuarios como resultado de [simulaciones](attack-simulation-training.md) o [automatizaciones de simulaciones](attack-simulation-training-simulation-automations.md). Están disponibles los siguientes tipos de notificaciones de usuario final:

- **Notificación de refuerzo positivo**: se envía cuando los usuarios informan de un mensaje de suplantación de identidad simulado.
- **Notificación de simulación**: se envía cuando los usuarios se incluyen en una automatización de simulación o simulación, pero no se selecciona ningún entrenamiento.
- **Notificación de asignación de entrenamiento**: se envía cuando a los usuarios se les asignan los entrenamientos necesarios como resultado de una simulación o automatizaciones de simulación.
- **Notificación de recordatorio de entrenamiento**: se envía como recordatorio para los entrenamientos necesarios.

Para ver las notificaciones de usuario final disponibles, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & pestaña** \> De colaboración \> **Entrenamiento de simulación de ataque** \> **biblioteca de contenido simulación** y, a continuación, seleccione Notificaciones del **usuario final**. Para ir directamente a la pestaña **Biblioteca de contenido de simulación** , donde puede seleccionar **Notificaciones de usuario final**, use <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

**Las notificaciones de usuario final** tienen dos pestañas:

- **Notificaciones globales**: contiene las notificaciones integradas y no modificables.
- **Notificaciones de inquilino:** contiene las notificaciones personalizadas que ha creado.

Se muestra la siguiente información para cada notificación:

- **Notificaciones**: nombre de la notificación.
- **Idioma**: si la notificación contiene varias traducciones, los dos primeros idiomas se muestran directamente. Para ver los idiomas restantes, mantenga el puntero sobre el icono numérico (por ejemplo, **+10**).
- **Tipo**: el valor es **Notificación de refuerzo positivo**, **Notificación de simulación**, **Notificación de asignación de entrenamiento** o **Notificación de recordatorio de entrenamiento**.
- **Origen**: para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Inquilino**.
- **Estado**: el valor es **Listo** o **Borrador**. En la pestaña **Notificaciones globales** , el valor siempre está **listo**.
- **Simulaciones vinculadas**: el número total de [simulaciones](attack-simulation-training.md) o [automatizaciones de simulación](attack-simulation-training-simulation-automations.md) que usan la notificación.
- **Creado por**: para las notificaciones integradas, el valor es **Microsoft**. En el caso de las notificaciones personalizadas, el valor es el UPN del usuario que creó la notificación.
- **Tiempo de creación**
- **Modificado por**
- **Hora de última modificación**

Para buscar una notificación en la lista, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre de la notificación.

Para agrupar las notificaciones por tipo, haga clic en ![Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupe** y, a continuación, seleccione **Tipo de notificación**. Para desagrupar las notificaciones, seleccione **Ninguno**.

En la pestaña Solo **notificaciones de inquilino** , haga clic en ![el icono Filtro.](../../media/m365-cc-sc-filter-icon.png) para filtrar las notificaciones por uno o varios idiomas.

Para quitar una o varias columnas que se muestran, haga clic en ![el icono Personalizar columnas.](../../media/m365-cc-sc-customize-icon.png) **Personalizar columnas**.

Al seleccionar una notificación de la lista, aparece un control flotante de detalles con la siguiente información:

- **Pestaña Vista previa** : vea el mensaje de notificación como lo verán los usuarios. Para ver el mensaje en diferentes idiomas, use el cuadro **Seleccionar idioma** .
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

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a **Email & pestaña** \> Biblioteca de **contenido de simulación** **Entrenamiento de simulación de ataque** \> colaboración \> y, a continuación, seleccione **Notificaciones del usuario final**. Para ir directamente a la pestaña **Biblioteca de contenido de simulación** , donde puede seleccionar **Notificaciones de usuario final**, use <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

2. En la pestaña **Notificaciones de inquilino** , haga clic en ![el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree un nuevo** para iniciar el Asistente para notificaciones de usuario final.

   > [!NOTE]
   > En cualquier momento durante el asistente para la creación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y continuar configurando la notificación más adelante. Para seleccionar dónde lo dejó, seleccione la notificación en la pestaña Notificaciones de **inquilino en** **Notificaciones de usuario final** y, a continuación, haga clic en ![el icono Editar automatización.](../../media/m365-cc-sc-edit-icon.png) **Edite la automatización**. La notificación parcialmente completada tendrá el valor **Estado** **Borrador**.

3. En la página **Definir detalles** **, configure los siguientes valores:
   - **Seleccionar tipo de notificación**: seleccione uno de los valores siguientes:
     - **Notificación de refuerzo positivo**
     - **Notificación de simulación**
     - **Notificación de asignación de entrenamiento**
     - **Notificación de recordatorio de entrenamiento**
   - **Nombre**: escriba un nombre único.
   - **Descripción**: escriba una descripción opcional.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Definir contenido** , la única configuración que está disponible es el botón **Agregar contenido en lenguaje empresarial** . Al hacer clic en él, aparece un control flotante **Agregar contenido en idioma predeterminado** que contiene la siguiente configuración:
   - **Desde el nombre para mostrar**
   - **Desde la dirección de correo electrónico**
   - **Seleccione el idioma del correo electrónico**: seleccione un idioma de la lista.
   - **Marque esto como el idioma predeterminado**: dado que este es el primer y único idioma de la notificación, este valor está seleccionado y no se puede cambiar.
   - **Asunto**: El valor predeterminado es **Gracias por informar de phish**, pero puede cambiarlo.
   - **Importar correo electrónico**: opcionalmente, puede hacer clic en este botón y, a continuación, hacer clic en **Elegir archivo** para importar un archivo de mensaje de texto sin formato existente.
   - Email área de contenido: hay dos pestañas disponibles:
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
     - ![Icono de edición.](../../media/m365-cc-sc-edit-icon.png) **Edit**
     - ![Icono de vista.](../../media/m365-cc-sc-view-icon.png) **View**
     - ![Icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**: si solo hay una versión de idioma de la notificación, no se puede eliminar.

   Para agregar una versión de la notificación en otro idioma, haga clic en ![Agregar icono](../../media/m365-cc-sc-create-icon.png) de traducción. En el control flotante **Agregar traducción** que aparece, la misma configuración está disponible que en el control flotante **Agregar contenido en idioma predeterminado** que se describió anteriormente. La única diferencia es que puede seleccionar **Marcar esto como idioma predeterminado** en traducciones adicionales.

   Cuando haya terminado, haga clic en **Guardar.**

   Puede repetir estos pasos tantas veces como sea necesario para crear versiones traducidas de la notificación en los 12 idiomas admitidos.

   Cuando haya terminado, haga clic en **Siguiente.**

5. En la página **Revisar notificación** , puede revisar los detalles de la notificación.

   Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

   En la página **Nueva notificación de simulación creada** , puede usar los vínculos para crear una nueva notificación, iniciar una simulación o ver todas las notificaciones.

   Cuando haya terminado, haga clic en **Listo**.

De nuevo en la pestaña **Notificaciones de inquilino en** **Notificaciones de usuario final**, la notificación que ha creado ahora es una lista.

## <a name="modify-end-user-notifications"></a>Modificación de las notificaciones del usuario final

No se pueden modificar las notificaciones integradas en la pestaña **Notificaciones globales**. Solo puede modificar las notificaciones personalizadas en la pestaña **Notificaciones de inquilino.**

Para modificar una notificación personalizada existente en la pestaña **Notificaciones de inquilino** , realice uno de los pasos siguientes:

- Seleccione la notificación de la lista haciendo clic en la casilla. Haga clic en el ![icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Icono de edición** que aparece.
- Haga clic **en ⋮** (**Acciones**) entre los valores **notificaciones** y **idioma** de la notificación de la lista y, a continuación, seleccione ![Editar icono.](../../media/m365-cc-sc-edit-icon.png) **Edición**.
- Seleccione la notificación de la lista haciendo clic en cualquier lugar de la fila excepto en la casilla. En el control flotante de detalles que se abre, haga clic en **Editar notificación**.

El asistente para notificaciones del usuario final se abre con la configuración y los valores de la notificación seleccionada. Los pasos son los mismos que se describen en la sección [Crear notificaciones de usuario final](#create-end-user-notifications) .

## <a name="copy-end-user-notifications"></a>Copia de notificaciones de usuario final

Para copiar una notificación existente en las pestañas **Notificaciones de inquilino** o **Notificaciones globales** , realice uno de los pasos siguientes:

- Seleccione la notificación de la lista haciendo clic en la casilla y, a continuación, haga clic en el ![icono Crear una copia.](../../media/m365-cc-sc-edit-icon.png) **Cree un icono de copia** que aparezca.
- Haga clic en **⋮** (**Acciones**) entre los valores **notificaciones** y **idioma** de la notificación de la lista y, a continuación, seleccione ![Crear un icono de copia.](../../media/m365-cc-sc-edit-icon.png) **Cree una copia**.

Al copiar una notificación personalizada en la pestaña **Notificaciones de inquilino** , hay disponible una copia de la notificación denominada "\<OriginalName\> - Copiar" en la lista.

Al copiar una notificación integrada en la pestaña **Notificaciones globales** , aparece un cuadro de diálogo **Crear copia** . El cuadro de diálogo confirma que se ha creado una copia de la notificación y está disponible en la pestaña **Notificaciones de inquilino** . Si hace clic en **Ir a la notificación de inquilino** , se le dirigirá a la pestaña **Notificaciones de inquilino** , donde la notificación integrada copiada se denomina "\<OriginalName\> - Copiar" está disponible en la lista. Si hace clic en **Permanecer aquí** en el cuadro de diálogo, volverá a la pestaña **Notificaciones globales** .

Una vez creada la copia, puede modificarla como [se describió anteriormente](#modify-end-user-notifications).

> [!NOTE]
> El control **Usar desde predeterminado** en el control flotante **Agregar contenido en idioma predeterminado** en el asistente para notificaciones le permite copiar el contenido de una notificación integrada.

## <a name="remove-notifications"></a>Eliminación de notificaciones

No se pueden quitar las notificaciones integradas de la pestaña **Notificaciones globales**. Solo puede quitar notificaciones personalizadas en la pestaña **Notificaciones de inquilino.**

Para quitar una notificación personalizada existente de la pestaña **Notificaciones de inquilino** , realice uno de los pasos siguientes:

- Seleccione la notificación de la lista haciendo clic en la casilla y, a continuación, haga clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Icono de eliminación** que aparece.
- Haga clic en **⋮** (**Acciones**) entre los valores **notificaciones** y **idioma** de la notificación de la lista y, a continuación, seleccione el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Creación de una simulación de ataque de suplantación de identidad (phishing)](attack-simulation-training.md)

[Automatizaciones de simulación para Entrenamiento de simulación de ataque](attack-simulation-training-simulation-automations.md)
