---
title: Automatización de la simulación para el aprendizaje de simulación de ataques
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
description: Los administradores pueden aprender a crear simulaciones automatizadas que contienen técnicas y cargas específicas que se inician cuando se cumplen las condiciones especificadas en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.openlocfilehash: a6612a14a4a583cf3b61cf7b678fbdc1d1055dc6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662224"
---
# <a name="simulation-automations-for-attack-simulation-training"></a>Automatización de la simulación para el aprendizaje de simulación de ataques

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta [Introducción al aprendizaje de simulación de ataques.](attack-simulation-training-get-started.md)

Para crear una automatización de simulación, siga estos pasos:

1. En el portal Microsoft 365 Defender en , vaya a Correo electrónico & la pestaña Aprendizaje de simulación de <https://security.microsoft.com/>  \>  \> **ataques Simulación de** automatización.

   Para ir directamente a la pestaña **Simulation automations,** use <https://security.microsoft.com/attacksimulator?viewid=simulationautomation> .

2. En la **pestaña Automatización de Simulation,** seleccione ![ Crear icono de simulación.](../../media/m365-cc-sc-create-icon.png) **Crear simulación**.

   ![Cree el botón de simulación en la pestaña Automatización de simulación en el aprendizaje de simulación de ataque en el portal Microsoft 365 Defender simulación.](../../media/attack-sim-training-sim-automations-create.png)

3. Se abrirá el Asistente para creación. El resto de este artículo describe las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente  para la creación de simulación, puede hacer clic en Guardar y cerrar para guardar el progreso y continuar configurando la simulación más adelante. La simulación incompleta tiene el **valor de Estado** **Borrador** en la **ficha Simulaciones.** Puede elegir dónde lo dejó seleccionando la simulación y haciendo clic ![ en Editar icono de simulación.](../../media/m365-cc-sc-edit-icon.png) **Edite** simulation.## Name y describa la simulación.

## <a name="name-and-describe-the-simulation-automation"></a>Nombre y descripción de la automatización de simulación

En la **página Nombre de** automatización, configure las siguientes opciones:

- **Nombre:** escriba un nombre descriptivo único para la simulación.
- **Descripción:** escriba una descripción detallada opcional para la simulación.

Cuando termine, haga clic en **Siguiente**.

## <a name="select-one-or-more-social-engineering-techniques"></a>Seleccionar una o varias técnicas de ingeniería social

En la página Seleccionar técnicas de ingeniería **social,** seleccione una o varias de las técnicas de ingeniería social disponibles, que se han seleccionado desde el marco de trabajo&[MITRE ATT ® CK.](https://attack.mitre.org/techniques/enterprise/) Hay diferentes cargas disponibles para distintas técnicas. Las siguientes técnicas de ingeniería social están disponibles:

- **Recolección de credenciales:** intenta recopilar credenciales llevando a los usuarios a un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.
- **Datos adjuntos de malware:** agrega datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- **Vínculo en datos adjuntos:** un tipo de híbrido de recolección de credenciales. Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recolección de credenciales.
- **Vínculo a malware:** ejecuta código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.
- **Dirección URL de** unidad por: la dirección URL malintencionada del mensaje lleva al usuario a un sitio web familiar que ejecuta o instala código de forma silenciosa en el dispositivo del usuario.

Si hace clic **en** el vínculo Ver detalles de la descripción, se abrirá un desplegable de detalles que describe la técnica y los pasos de simulación que resultan de la técnica.

![Muestra los detalles de la técnica de recolección de credenciales en la página Seleccionar técnicas de ingeniería social.](../../media/attack-sim-training-simulations-select-technique-sim-steps.png)

Cuando termine, haga clic en **Siguiente**.

## <a name="select-payloads"></a>Seleccionar cargas

En la **página Seleccionar cargas,** seleccione una de las siguientes opciones:

- **Selección manual**
- **Randomize**

Si selecciona **Randomize**, no hay nada que configurar en esta página, por lo que haga clic **en Siguiente** para continuar.

Si selecciona **Manualmente,** debe seleccionar una o más cargas de la lista. Se muestran los siguientes detalles para ayudarle a elegir:

- **Nombre de carga**
- **Técnica:** debe seleccionar como una carga por técnica que seleccionó en la página anterior.
- **Language:** el idioma del contenido de carga. El catálogo de carga útil (global) de Microsoft proporciona cargas en más de 10 idiomas que también se pueden filtrar.
- **Tasa de clics:** cuántas personas han hecho clic en esta carga.
- **Tasa de compromiso predicho:** datos históricos de la carga en Microsoft 365 que predice el porcentaje de personas que se verán comprometidas por esta carga.
- **Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.

En el ![ icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro** de búsqueda, puede escribir parte del nombre de carga y presionar Entrar para filtrar los resultados.

Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:

- **Complejidad:** se calcula en función del número de indicadores de la carga útil que indican un posible ataque (errores ortográficos, urgencia, etc.). Más indicadores son más fáciles de identificar como un ataque e indican menor complejidad. Los valores disponibles son los siguientes:
  - **Baja**
  - **Media**
  - **Alta**
- **Source:** indica si la carga se creó en la organización o si forma parte del catálogo de carga preexistnte de Microsoft. Los valores admitidos son:
  - **Global**
  - **Tenant**
  - **Todo**
- **Idioma**: Los valores disponibles son: **inglés** **,** español , alemán , japonés **,** francés **,** portugués **,** neerlandés **,** **italiano** **,** sueco , chino **(simplificado)** **,** noruego **Bokmål**, polaco **,** ruso **,** finlandés **,** coreano **,** turco **,** húngaro **,** hebreo , **tailandés**, **árabe**, **vietnamita**, eslovaco  ****, **Griego**, **indonesio**, **rumano**, **esloveno**, **croata,** **catalán** y **otros**.
- **Agregar etiquetas**
- **Filtrar por** **tema:** Los valores disponibles son: Activación de la cuenta **,** Verificación de cuenta **,** Facturación **,** Limpiar correo **,** Documento recibido , **Gastos**, **Fax** **,** Informe de finanzas , **Mensajes** entrantes **,** Factura , **Elementos** recibidos **,** Alerta de inicio de sesión , **Correo** recibido **,** Contraseña **,** **Pago**, Nómina , **Oferta** personalizada , **Cuarentena**, **Trabajo remoto**, **Mensaje de revisión,** Actualización de **seguridad,** **Servicio** suspendido, **Firma** requerida, Actualizar almacenamiento de buzones De correo Detección de **buzones** de **correo,** Correo de voz y **Otros**.
- **Filtro por** marca: Los valores disponibles son: **American Express**, Capital **One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** y **Other**.
- **Filtro por** industria: Los valores disponibles **son:** Banca **,** Servicios empresariales **,** Servicios de consumo **,** Educación **,** Energía **,** Construcción , **Consultoría** **,** Servicios financieros , **Gobierno**, **Hospitalidad**, **Seguros**, **Legal**, **Servicios** de mensajería , **IT**, **Salud**, **Fabricación**, **Retail**, **Telecom**, **Bienes raíces**, y **Otros**.
- **Evento actual:** los valores disponibles **son Sí** o **No**.
- **Polémico:** los valores disponibles **son Sí** o **No**.

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.

Si selecciona una carga de la lista haciendo clic en el nombre, los detalles sobre la carga se muestran en un desplegable:

- La **pestaña Información** general contiene un ejemplo y otros detalles sobre la carga.
- La **pestaña Simulaciones iniciadas** contiene el nombre **de simulación**, la tasa **de clics,** la **velocidad comprometida** y la **acción**.

![Detalles de carga en el aprendizaje de simulación de ataque en el portal Microsoft 365 Defender ataque.](../../media/attack-sim-training-simulations-select-payload-details.png)

Cuando termine, haga clic en **Siguiente**.

## <a name="target-users"></a>Usuarios de destino

En la **página Usuarios de** destino, seleccione quién recibirá la simulación. Configure una de las siguientes opciones:

- **Incluir todos los usuarios de la organización:** los usuarios afectados se muestran en listas de 10. Puede usar los botones **Siguiente** **y Anterior** directamente debajo de la lista de usuarios para desplazarse por la lista. También puede usar el ![ icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Icono** de búsqueda en la página para buscar usuarios afectados.
- **Incluir solo usuarios y grupos específicos:** elija una de las siguientes opciones:
  - ![Icono Agregar usuarios.](../../media/m365-cc-sc-create-icon.png) **Agregar usuarios:** en **el** menú desplegable Agregar usuarios que aparece, puede encontrar usuarios y grupos en función de los siguientes criterios:
    - **Usuarios o grupos:** en el ![ icono Buscar usuarios y grupos.](../../media/m365-cc-sc-search-icon.png) **Busque usuarios y grupos** en el cuadro,  puede escribir parte del nombre o la dirección de correo electrónico del usuario o grupo y, a continuación, presione ENTRAR.  Puede seleccionar algunos o todos los resultados. Cuando haya terminado, haga clic **en Agregar x usuarios**.

      > [!NOTE]
      > Al hacer **clic en el** botón Agregar filtros para volver a las opciones **Filtrar** usuarios por categorías, se borrarán los usuarios o grupos seleccionados en los resultados de búsqueda.

    - **Filtrar usuarios por categorías:** seleccione entre ninguna, algunas o todas las opciones siguientes:
      - **Grupos de usuarios sugeridos:** seleccione entre los siguientes valores:
        - **Todos los grupos de usuarios sugeridos**
        - **Usuarios no dirigidos por una simulación en los últimos tres meses**
        - **Reincidentes**
      - **Departamento:** use las siguientes opciones:
        - **Buscar:** en el ![ icono Buscar por departamento.](../../media/m365-cc-sc-search-icon.png) **En el cuadro** Buscar por departamento, puede escribir parte del valor departamento y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el departamento**
        - Seleccione los valores de Departamento existentes.
      - **Título:** use las siguientes opciones:
        - **Buscar:** en el ![ icono Buscar por título.](../../media/m365-cc-sc-search-icon.png) **Busque por cuadro Título,** puede escribir parte del valor Título y, a continuación, presione ENTRAR. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el título**
        - Seleccione los valores de Título existentes.

      ![Filtrado de usuarios en la página Usuarios de destino del aprendizaje de simulación de ataque en el portal Microsoft 365 Defender ataque.](../../media/attack-sim-training-simulations-target-users-filter-by-category.png)

      Después de identificar los criterios, los  usuarios afectados se muestran en la sección Lista de usuarios que aparece, donde puede seleccionar algunos o todos los destinatarios detectados.

      Cuando haya terminado, haga clic **en Aplicar(x)** y, a continuación, haga clic **en Agregar usuarios x**.

  De vuelta en la **página Principal de los usuarios de** destino, puede usar el icono ![ buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro** de búsqueda para buscar usuarios afectados. También puede hacer clic en ![ Eliminar icono.](../../media/m365-cc-sc-delete-icon.png) **Eliminar** para quitar usuarios específicos.

- ![Icono importar.](../../media/m365-cc-sc-create-icon.png) **Importar:** en el cuadro de diálogo que se abre, especifique un archivo CSV que contenga una dirección de correo electrónico por línea.

  Después de encontrar una selección del archivo CSV, la lista de usuarios se importa y se muestra en la **página Usuarios dirigidos.** Puede usar el icono ![ Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro** de búsqueda para buscar usuarios afectados. También puede hacer clic en ![ Eliminar icono.](../../media/m365-cc-sc-delete-icon.png) **Eliminar** para quitar usuarios específicos.

Cuando termine, haga clic en **Siguiente**.

## <a name="assign-training"></a>Asignar formación

En la **página Asignar aprendizaje,** puede asignar cursos para la simulación. Se recomienda asignar formación para cada simulación, ya que los empleados que pasan por el aprendizaje son menos propensos a ataques similares. Estas son las opciones de configuración disponibles:

- **Seleccionar preferencia de contenido de aprendizaje:** elija una de las siguientes opciones:
  - **Experiencia de aprendizaje de Microsoft:** este es el valor predeterminado que tiene las siguientes opciones asociadas para configurar:
    - Seleccione una de las siguientes opciones:
      - **Asignarme formación:** este es el valor predeterminado y recomendado. Asignamos formación en función de los resultados de simulación y aprendizaje anteriores de un usuario, y puede revisar las selecciones en los pasos siguientes del asistente.
      - **Seleccionar cursos y** módulos de aprendizaje: si selecciona este valor, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles en el siguiente paso del asistente.
    - **Fecha de vencimiento:** elija uno de los siguientes valores:
      - **30 días después de que finalice la** simulación: este es el valor predeterminado.
      - **15 días después de que finalice la simulación**
      - **7 días después de que finalice la simulación**
  - **Redirigir a una dirección URL personalizada:** este valor tiene las siguientes opciones asociadas para configurar:
    - **Dirección URL de aprendizaje** personalizada (obligatorio)
    - **Nombre de aprendizaje personalizado** (obligatorio)
    - **Descripción del aprendizaje personalizado**
    - **Duración del aprendizaje personalizado (en minutos):** el valor predeterminado es 0, lo que significa que no hay una duración especificada para el aprendizaje.
    - **Fecha de vencimiento:** elija uno de los siguientes valores:
      - **30 días después de que finalice la** simulación: este es el valor predeterminado.
      - **15 días después de que finalice la simulación**
      - **7 días después de que finalice la simulación**
  - **Sin formación:** si selecciona este valor, la única  opción de la página es el botón Siguiente que le llevará a la página [**De aterrizaje.**](#landing-page)

![Agregue el aprendizaje recomendado en la página Asignación de aprendizaje en El entrenamiento de simulación de ataques en el portal Microsoft 365 Defender búsqueda.](../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png)

### <a name="training-assignment"></a>Asignación de aprendizaje

> [!NOTE]
> La **página Asignación de** aprendizaje solo está disponible si seleccionó Experiencia de aprendizaje de **Microsoft** Seleccione los cursos y módulos de aprendizaje en \>  la página anterior.

En la **página Asignación de** aprendizaje, seleccione los cursos que desea agregar a la simulación haciendo clic ![ en Agregar aprendizajes icono.](../../media/m365-cc-sc-create-icon.png) **Agregar aprendizajes**.

En el **control desplegable** Agregar aprendizaje que aparece, puede seleccionar los cursos que se van a usar en las siguientes pestañas disponibles:

- **Ficha** Recomendada: muestra los entrenamientos integrados recomendados en función de la configuración de simulación. Estos son los mismos cursos que se habrían asignado si seleccionaste Asignar **aprendizaje para mí** en la página anterior.
- **Pestaña Todos los entrenamientos:** muestra todos los cursos integrados que están disponibles.

  Se muestra la siguiente información para cada aprendizaje:

  - **Nombre de la formación**
  - **Source:** el valor es **Global**.
  - **Duración (minutos)**
  - **Vista** previa: haga clic en **el botón Vista** previa para ver el aprendizaje.

  En el ![ icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro** de búsqueda, puede escribir parte del nombre del aprendizaje y presionar Entrar para filtrar los resultados en la pestaña actual.

  Seleccione todos los entrenamientos que desee incluir en la pestaña actual y, a continuación, haga clic en **Agregar**.

De vuelta en la **página principal de la asignación de** aprendizaje, se muestran los entrenamientos seleccionados. Se muestra la siguiente información para cada aprendizaje:

- **Nombre de la formación**
- **Source**
- **Duración (minutos)**

Para cada aprendizaje de la lista, debe seleccionar quién obtiene el aprendizaje seleccionando valores en la columna **Asignar a:**

- **Todos los usuarios**

  o uno o ambos de los siguientes valores:

- **Carga clicked**
- **Comprometida**

Si no quieres usar un aprendizaje que se muestra, haz clic en ![ Eliminar icono.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

![Página de asignación de aprendizaje en aprendizaje de simulación de ataque en el portal Microsoft 365 Defender de aprendizaje.](../../media/attack-sim-training-training-assignment.png)

Cuando termine, haga clic en **Siguiente**.

### <a name="landing-page"></a>Página de aterrizaje

En la **página Página de aterrizaje,** configura la página de aterrizaje de aprendizaje que los usuarios ven. Estas son las opciones de configuración disponibles:

- **Header**
- **Cuerpo**

Puede aceptar los valores predeterminados o personalizarlos.

Cuando termine, haga clic en **Siguiente**.

## <a name="simulation-schedule"></a>Programación de simulación

En la **página Programación de** Simulación, seleccione uno de los siguientes valores:

- **Randomized**: Todavía tiene que seleccionar la programación en la página siguiente, pero las simulaciones se iniciarán en momentos aleatorios con la programación.
- **Fixed**

Cuando termine, haga clic en **Siguiente**.

## <a name="schedule-details"></a>Detalles de programación

Lo que ve en la **página Detalles de programación** depende de si seleccionó **Randomized** o **Fixed** en la página anterior.

- **Randomized:** las siguientes opciones de configuración están disponibles:
  - **Sección inicio de** simulación: Configure la siguiente configuración:
    - **Seleccione la fecha desde la que desea que comiencen las simulaciones**
  - **Sección Ámbito de simulación:** Configure las siguientes opciones:
    - **Seleccione los días de la semana en** los que pueden iniciarse las simulaciones: Seleccione uno o más días de la semana.
    - **Escriba el número máximo de simulaciones** que se pueden iniciar entre las fechas de inicio y finalización: escriba un valor de 1 a 10.
    - **Aleatorizar las horas de** envío: seleccione esta configuración para aleatorizar las horas de envío.
  - **Sección final de** simulación: Configure la siguiente configuración:
    - **Seleccione la fecha en la que desea que finalicen las simulaciones**

- **Corregido**: La siguiente configuración está disponible:
  - **Sección inicio de** simulación: Configure la siguiente configuración:
    - **Seleccione la fecha desde la que desea que comiencen las simulaciones**
  - **Sección Periodicidad** de simulación: Configure las siguientes opciones:
    - **Seleccione si desea que las simulaciones se inicien semanalmente** o mensualmente: Seleccione uno de los siguientes valores:
      - **Semanal:** este es el valor predeterminado.
      - **Mensualmente**
    - **Escriba con qué frecuencia en semanas desea que se** repitan las simulaciones para : Escriba un valor de 1 a 99 semanas.
    - **Seleccione el día de la semana desde el que desea que comiencen las simulaciones**
  - **Sección final de** simulación: Seleccione uno de los siguientes valores:
    - **Seleccione la fecha en la que desea que finalicen las simulaciones**
    - **Escriba el número de repeticiones de las simulaciones** que se ejecutarán antes de finalizar: Escriba un valor de 1 a 10.

Cuando termine, haga clic en **Siguiente**.

## <a name="launch-details"></a>Detalles del inicio

En la **página Detalles del** inicio, configure las siguientes opciones adicionales para la automatización:

- **Use cargas únicas en simulaciones dentro de una automatización:** de forma predeterminada, esta configuración no está seleccionada.
- **Infractores reincidentes de destino:** de forma predeterminada, esta configuración no está seleccionada. Si lo selecciona, configure la siguiente configuración que aparece:
  - **Escriba el número máximo de veces que un** usuario puede ser dirigido dentro de esta automatización: escriba un valor de 1 a 10.
- **Enviar correo electrónico de simulación** en función de la configuración de zona horaria actual del usuario desde Outlook aplicación web: de forma predeterminada, esta configuración no está seleccionada.
- Mostrar la página de datos **intersticiales** de la técnica de unidad por : esta configuración solo está disponible si seleccionó dirección **URL** de unidad por en la página Seleccionar una o más técnicas de ingeniería **[social.](#select-one-or-more-social-engineering-techniques)** De forma predeterminada, la configuración está en ( ![ Icono Activar. ](../../media/scc-toggle-on.png) ).

## <a name="review-simulation-automation"></a>Revisar la automatización de simulación

En la **página Revisar automatización de simulación,** puede revisar los detalles de la automatización de la simulación.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.
