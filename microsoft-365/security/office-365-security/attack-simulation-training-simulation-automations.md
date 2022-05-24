---
title: Automatizaciones de simulación para el entrenamiento de simulación de ataques
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
description: Los administradores pueden aprender a crear simulaciones automatizadas que contienen técnicas y cargas específicas que se inician cuando se cumplen las condiciones especificadas en Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.openlocfilehash: b80d73f6efe398465eecea9967c4bd8d929a51a2
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649417"
---
# <a name="simulation-automations-for-attack-simulation-training"></a>Automatizaciones de simulación para el entrenamiento de simulación de ataques

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Para obtener información de introducción sobre el entrenamiento de simulación de ataques, consulte [Comenzar uso del entrenamiento de simulación de ataques](attack-simulation-training-get-started.md).

Para crear una automatización de simulación, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com/>, vaya a la pestaña **Email & collaboration** **Attack simulation training** **Simulation automations (Automatizaciones de simulación de simulación** de entrenamiento \> de simulación de colaboración\>).

   Para ir directamente a la pestaña **Automatizaciones de simulación** , use <https://security.microsoft.com/attacksimulator?viewid=simulationautomation>.

2. En la pestaña **Automatizaciones de simulación** , seleccione ![El icono Crear automatización.](../../media/m365-cc-sc-create-icon.png) **Crear automatización**.

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="El botón Crear simulación de la pestaña Automatizaciones de simulación del entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

3. Se abre el asistente para la creación. En el resto de este artículo se describen las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente para la creación de la simulación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y continuar configurando la simulación más adelante. La simulación incompleta tiene el valor **Estado** **Borrador** en la pestaña **Simulaciones** . Puede seleccionar dónde lo dejó seleccionando la simulación y haciendo clic en ![Editar icono de simulación.](../../media/m365-cc-sc-edit-icon.png) **Edite** simulation.## Asigne un nombre y describa la simulación.

## <a name="name-and-describe-the-simulation-automation"></a>Asigne un nombre y describa la automatización de la simulación.

En la página **Nombre de Automation**, configure los siguientes valores:

- **Nombre**: escriba un nombre descriptivo único para la simulación.
- **Descripción**: escriba una descripción detallada opcional para la simulación.

Cuando termine, haga clic en **Siguiente**.

## <a name="select-one-or-more-social-engineering-techniques"></a>Selección de una o varias técnicas de ingeniería social

En la página **Select social engineering techniques (Seleccionar técnicas de ingeniería social** ), seleccione una o varias de las técnicas de ingeniería social disponibles, que se seleccionaron en el [marco de TRABAJO de MITRE ATT&CK®](https://attack.mitre.org/techniques/enterprise/). Hay diferentes cargas disponibles para diferentes técnicas. Están disponibles las siguientes técnicas de ingeniería social:

- **Recopilación de credenciales**: intenta recopilar credenciales llevando a los usuarios a un sitio web de apariencia conocida con cuadros de entrada para enviar un nombre de usuario y una contraseña.
- **Datos adjuntos de malware**: agrega datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- **Vínculo en datos adjuntos**: un tipo de híbrido de recopilación de credenciales. Un atacante inserta una dirección URL en los datos adjuntos de un correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recopilación de credenciales.
- **Vínculo a malware**: ejecuta código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abra el archivo y ayude al atacante a poner en peligro el dispositivo del destino.
- **Dirección URL de unidad por**: la dirección URL malintencionada del mensaje lleva al usuario a un sitio web de aspecto familiar que ejecuta o instala código de forma silenciosa en el dispositivo del usuario.

Si hace clic en el vínculo **Ver detalles** de la descripción, se abre un control flotante de detalles que describe la técnica y los pasos de simulación que resultan de la técnica.

:::image type="content" source="../../media/attack-sim-training-simulations-select-technique-sim-steps.png" alt-text="El control flotante Detalles de la técnica de recolección de credenciales en la página Seleccionar técnicas de ingeniería social" lightbox="../../media/attack-sim-training-simulations-select-technique-sim-steps.png":::

Cuando termine, haga clic en **Siguiente**.

## <a name="select-payloads"></a>Selección de cargas

En la página **Seleccionar cargas,** seleccione una de las siguientes opciones:

- **Selección manual**
- **Randomize**

Si selecciona **Aleatorio**, no hay nada que configurar en esta página, por lo que haga clic en **Siguiente** para continuar.

Si selecciona **Seleccionar manualmente**, debe seleccionar una o varias cargas de la lista. Se muestran los detalles siguientes para ayudarle a elegir:

- **Nombre de carga**
- **Técnica**: debe seleccionar al menos una carga por técnica que seleccionó en la página anterior.
- **Idioma**: idioma del contenido de la carga. El catálogo de cargas de Microsoft (global) proporciona cargas en más de 10 idiomas que también se pueden filtrar.
- **Tasa de clics**: cuántas personas han hecho clic en esta carga.
- **Tasa de compromiso prevista**: datos históricos de la carga útil en Microsoft 365 que predice el porcentaje de personas que se verán comprometidas por esta carga.
- **Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.

En el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** , puede escribir parte del nombre de carga útil y presionar Entrar para filtrar los resultados.

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Origen**: indica si la carga se creó en su organización o forma parte del catálogo de carga preexistente de Microsoft. Los valores admitidos son:
  - **Global** (integrado)
  - **Inquilino** (personalizado)
  - **Todo**

- **Complejidad**: se calcula en función del número de indicadores de la carga útil que indican un posible ataque (errores ortográficos, urgencia, etc.). Más indicadores son más fáciles de identificar como un ataque e indican una menor complejidad. Los valores disponibles son los siguientes:
  - **Baja**
  - **Media**
  - **Alta**

- **Idioma**: Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** y **otros**.

- **Agregar etiquetas**

- **Filtrar por tema**: Los valores disponibles son: **Activación de la cuenta**, **Verificación de cuenta**, **Facturación**, **Limpiar correo**, **Documento recibido**, **Gastos**, **Fax**, **Informe financiero**, **Mensajes entrantes**, **Factura**, **Elementos recibidos**, **Alerta de inicio de sesión**, **Correo recibido**, **Contraseña**, **Pago**, **Nómina**, **Oferta personalizada**, **Cuarentena**, **Trabajo remoto**, **Mensaje de revisión**, **Actualización de seguridad**, **Servicio suspendido**, **Firma necesaria**, **Actualizar almacenamiento del buzón Comprobar buzón**, **Correo de voz** y **Otros**.

- **Filtrar por marca**: Los valores disponibles son: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** y **otros**.

- **Filtrar por sector**: Los valores disponibles son: **Banca**, **Servicios empresariales**, **Servicios de consumo**, **Educación**, **Energía**, **Construcción**, **Consultoría**, **Servicios financieros**, **Gobierno**, **Hostelería**, **Seguros**, **Legal**, **Servicios de mensajería**, **TI**, **Salud**, **Fabricación**, **Minorista**, **Telecomunicaciones**, **Bienes Raíces**, y **otros**.

- **Evento actual**: los valores disponibles son **Sí** o **No**.

- **Controversial**: los valores disponibles son **Sí** o **No**.

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

Si selecciona una carga de la lista haciendo clic en el nombre, los detalles sobre la carga se muestran en un control flotante:

- La pestaña **Información general** contiene un ejemplo y otros detalles sobre la carga.
- La pestaña **Simulaciones iniciadas** contiene el **nombre de la simulación**, **la tasa de clics**, **la velocidad comprometida** y **la acción**.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-details.png" alt-text="El control flotante Detalles de carga del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-select-payload-details.png":::

Cuando termine, haga clic en **Siguiente**.

## <a name="target-users"></a>Usuarios de destino

En la página **Usuarios de destino** , seleccione quién recibirá la simulación. Configure una de las siguientes opciones:

- **Incluir todos los usuarios de la organización**: los usuarios afectados se muestran en listas de 10. Puede usar los botones **Siguiente** y **Anterior** directamente debajo de la lista de usuarios para desplazarse por la lista. También puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Icono de búsqueda** en la página para buscar usuarios afectados.
- **Incluir solo usuarios y grupos específicos**: elija una de las siguientes opciones:
  - ![Icono Agregar usuarios.](../../media/m365-cc-sc-create-icon.png) **Agregar usuarios**: en el control flotante **Agregar usuarios** que aparece, puede encontrar usuarios y grupos según los criterios siguientes:
    - **Usuarios o grupos**: en el ![icono Buscar usuarios y grupos.](../../media/m365-cc-sc-search-icon.png) **Cuadro Buscar usuarios y grupos** , puede escribir parte de la dirección de **nombre** o **correo electrónico** del usuario o grupo y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados. Cuando haya terminado, haga clic en **Agregar x usuarios**.

      > [!NOTE]
      > Al hacer clic en el botón **Agregar filtros** para volver a las opciones **Filtrar usuarios por categorías** , se borrarán los usuarios o grupos seleccionados en los resultados de la búsqueda.

    - **Filtrar usuarios por categorías**: seleccione entre ninguna, algunas o todas las opciones siguientes:
      - **Grupos de usuarios sugeridos**: seleccione entre los valores siguientes:
        - **Todos los grupos de usuarios sugeridos**
        - **Usuarios no dirigidos por una simulación en los últimos tres meses**
        - **Reincidentes**
      - **Departamento**: Use las siguientes opciones:
        - **Buscar**: en el ![icono Buscar por departamento.](../../media/m365-cc-sc-search-icon.png) **Cuadro Buscar por departamento** , puede escribir parte del valor Departamento y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el departamento**
        - Seleccione los valores de Departamento existentes.
      - **Título**: Use las siguientes opciones:
        - **Buscar**: en el ![icono Buscar por título.](../../media/m365-cc-sc-search-icon.png) **Cuadro Buscar por título** , puede escribir parte del valor título y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el título**
        - Seleccione los valores de Título existentes.

      :::image type="content" source="../../media/attack-sim-training-simulations-target-users-filter-by-category.png" alt-text="Filtrado de usuarios en la página Usuarios de destino del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-target-users-filter-by-category.png":::

      Después de identificar los criterios, los usuarios afectados se muestran en la sección **Lista** de usuarios que aparece, donde puede seleccionar algunos o todos los destinatarios detectados.

      Cuando haya terminado, haga clic en **Aplicar(x)** y, a continuación, haga clic en **Agregar x usuarios**.

  De nuevo en la página **principal Usuarios de destino** , puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar usuarios afectados. También puede hacer clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar** para quitar usuarios específicos.

- ![Icono importar.](../../media/m365-cc-sc-create-icon.png) **Importar**: en el cuadro de diálogo que se abre, especifique un archivo CSV que contenga una dirección de correo electrónico por línea.

  Después de seleccionar el archivo CSV, la lista de usuarios se importa y se muestra en la página **Usuarios de destino** . Puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar usuarios afectados. También puede hacer clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar** para quitar usuarios específicos.

Cuando termine, haga clic en **Siguiente**.

## <a name="assign-training"></a>Asignación de entrenamiento

En la página **Asignar entrenamiento** , puede asignar entrenamientos para la simulación. Se recomienda asignar entrenamiento para cada simulación, ya que los empleados que realizan el entrenamiento son menos susceptibles a ataques similares. Estas son las opciones de configuración disponibles:

- **Seleccionar preferencias de contenido de entrenamiento**: elija una de las siguientes opciones:
  - **Experiencia de entrenamiento de Microsoft**: este es el valor predeterminado que tiene las siguientes opciones asociadas para configurar:
    - Seleccione una de las siguientes opciones:
      - **Asignar entrenamiento para mí**: este es el valor predeterminado y recomendado. Asignamos entrenamiento en función de los resultados de simulación y entrenamiento anteriores de un usuario, y puede revisar las selecciones en los pasos siguientes del asistente.
      - **Seleccione los cursos de entrenamiento y los módulos yo mismo**: si selecciona este valor, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles en el siguiente paso del asistente.
    - **Fecha de vencimiento**: elija uno de los valores siguientes:
      - **30 días después de que finalice la simulación**: este es el valor predeterminado.
      - **15 días después de que finalice la simulación**
      - **7 días después de que finalice la simulación**
  - **Redirigir a una dirección URL personalizada**: este valor tiene las siguientes opciones asociadas para configurar:
    - **Dirección URL de entrenamiento personalizada** (obligatorio)
    - **Nombre de entrenamiento personalizado** (obligatorio)
    - **Descripción del entrenamiento personalizado**
    - **Duración de entrenamiento personalizada (en minutos):** el valor predeterminado es 0, lo que significa que no hay ninguna duración especificada para el entrenamiento.
    - **Fecha de vencimiento**: elija uno de los valores siguientes:
      - **30 días después de que finalice la simulación**: este es el valor predeterminado.
      - **15 días después de que finalice la simulación**
      - **7 días después de que finalice la simulación**
  - **Sin entrenamiento**: si selecciona este valor, la única opción de la página es el botón **Siguiente** que le lleva a la página [**De aterrizaje**](#landing-page) .

:::image type="content" source="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png" alt-text="Opción para agregar el entrenamiento recomendado en la página Asignación de entrenamiento en Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png":::

### <a name="training-assignment"></a>Asignación de entrenamiento

> [!NOTE]
> La página **Asignación de entrenamiento** solo está disponible si seleccionó **Experiencia** \> de entrenamiento de Microsoft **Seleccione cursos de entrenamiento y módulos yo mismo** en la página anterior.

En la página **Asignación de entrenamiento** , seleccione los entrenamientos que desea agregar a la simulación haciendo clic en el ![icono Agregar entrenamientos.](../../media/m365-cc-sc-create-icon.png) **Agregar entrenamientos**.

En el control flotante **Agregar entrenamiento** que aparece, puede seleccionar los entrenamientos que se van a usar en las pestañas siguientes que están disponibles:

- **Pestaña Recomendado** : muestra los entrenamientos integrados recomendados basados en la configuración de simulación. Estos son los mismos entrenamientos que se habrían asignado si seleccionó **Asignar entrenamiento para mí** en la página anterior.
- **Pestaña Todos los entrenamientos** : muestra todos los entrenamientos integrados que están disponibles.

  Se muestra la siguiente información para cada entrenamiento:

  - **Nombre del entrenamiento**
  - **Origen**: el valor es **Global**.
  - **Duración (minutos)**
  - **Vista previa**: haga clic en el botón **Vista previa** para ver el entrenamiento.

  En el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** , puede escribir parte del nombre de entrenamiento y presionar Entrar para filtrar los resultados en la pestaña actual.

  Seleccione todos los entrenamientos que desea incluir en la pestaña actual y, a continuación, haga clic en **Agregar**.

De nuevo en la página **principal Asignación de entrenamiento** , se muestran los entrenamientos seleccionados. Se muestra la siguiente información para cada entrenamiento:

- **Nombre del entrenamiento**
- **Source**
- **Duración (minutos)**

Para cada entrenamiento de la lista, seleccione uno o varios de los siguientes valores en la columna **Asignar a** para configurar quién obtiene el entrenamiento:

- **Todos los usuarios**
- **Carga en la que se ha hecho clic**
- **Comprometido**

Si no desea usar un entrenamiento que se muestra, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Delete**.

:::image type="content" source="../../media/attack-sim-training-training-assignment.png" alt-text="Página Asignación de entrenamiento en Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-training-assignment.png":::

Cuando termine, haga clic en **Siguiente**.

### <a name="landing-page"></a>Página de aterrizaje

En la **página De aterrizaje** , configurará la página web a la que se llevará el usuario si abre la carga en la simulación.

- **Seleccionar preferencia de página de aterrizaje**: los valores disponibles dependen de las selecciones anteriores en la página [Seleccionar cargas,](#select-payloads) como se describe en la tabla siguiente:

  |Selección en la página Seleccionar cargas|Valores disponibles para Seleccionar preferencia de página de aterrizaje|
  |---|---|
  |Selección manual|Uso de la página de aterrizaje predeterminada de Microsoft <p> Crear su propia página de aterrizaje <p> Uso de una dirección URL personalizada <p> **Nota**: El valor **Usar una dirección URL personalizada** no está disponible si seleccionó anteriormente **Datos adjuntos de malware** o **Vínculo a malware** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) .|
  |Randomize|Uso de la página de aterrizaje predeterminada de Microsoft|

  En la lista siguiente se describen los valores de **preferencia Seleccionar página de aterrizaje** disponibles y su configuración asociada:

  - **Use la página de aterrizaje predeterminada de Microsoft**. Este es el valor predeterminado y da como resultado una acción de indicador de carga, logotipo y plantilla predeterminada de Microsoft que se aplica a todas las cargas.

    Debe configurar las siguientes opciones adicionales en la **página De aterrizaje** :

    - **Seleccionar diseño de página de aterrizaje**: seleccione una de las 5 plantillas de página de aterrizaje disponibles.
    - **Agregar logotipo**: haga clic en **Examinar** para buscar y seleccionar un archivo .png, .jpeg o .gif para agregarlo a todas las cargas seleccionadas por Microsoft. El tamaño del logotipo debe ser un máximo de 210 x 70 para evitar distorsión. Para quitar el logotipo, haga clic en **Quitar**.
    - **Indicadores de carga** útil: esta configuración no está disponible si seleccionó anteriormente **Datos adjuntos de malware** o **Vincular a malware** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) .

      Seleccione **Agregar indicadores de carga al correo electrónico para** ayudar a los usuarios a aprender a identificar los mensajes de phishing.

    Puede obtener una vista previa de los resultados haciendo clic en el botón **Abrir panel vista previa** en el centro de la página. En el control flotante de vista previa que aparece, puede usar **Seleccionar carga para obtener una vista previa** para ver el aspecto de cada carga.

  - **Crear su propia página de aterrizaje**: este valor da como resultado una acción de indicador de carga única que se aplica a las cargas seleccionadas.

    Debe configurar las siguientes opciones adicionales en la **página De aterrizaje** :

    - **Indicadores de carga**: esta configuración solo está disponible para seleccionar si se cumplen las dos condiciones siguientes:
      - Anteriormente seleccionó **Cosecha de credenciales**, **Vínculo en datos adjuntos** o **Dirección URL de unidad** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) .
      - Después de agregar la **etiqueta dinámica** denominada **Insertar contenido de correo electrónico** en el contenido de la página.

    - Contenido de página: hay dos pestañas disponibles:

      - **Texto**: hay disponible un editor de texto enriquecido para crear la página de aterrizaje. Además de la configuración típica de fuente y formato, están disponibles las siguientes opciones:
        - **Etiqueta dinámica**: seleccione una de las siguientes etiquetas:
          - **Insertar nombre**
          - **Insertar nombre del remitente**
          - **Insertar correo electrónico del remitente**
          - **Insertar asunto de correo electrónico**
          - **Insertar contenido de correo electrónico**
          - **Insertar fecha**
        - **Usar de forma predeterminada**: seleccione una de las 5 plantillas de página de aterrizaje disponibles para empezar. Puede modificar el texto y el diseño en el área de edición. Para restablecer la página de aterrizaje al texto predeterminado y el diseño de la plantilla, haga clic en **Restablecer al valor predeterminado**.
        - **Vínculo de entrenamiento**: en el cuadro de diálogo **Name training URL (Dirección URL de entrenamiento** de nombre) que aparece, escriba un título de vínculo para el vínculo de entrenamiento y, a continuación, haga clic en **Confirmar** para agregar el vínculo a la página de aterrizaje.
      - **Código**: puede ver y modificar el código HTML directamente.

      Puede obtener una vista previa de los resultados haciendo clic en el botón **Abrir panel vista previa** en el centro de la página. En el control flotante de vista previa que aparece, puede usar **Seleccionar carga para obtener una vista previa** para ver el aspecto de cada carga.

  - **Usar una dirección URL personalizada**: agregue la dirección URL en el cuadro **Escribir la dirección URL de la página de aterrizaje personalizada** que aparece. No hay otras opciones disponibles en la página.

Cuando termine, haga clic en **Siguiente**.

## <a name="select-end-user-notification"></a>Selección de la notificación del usuario final

En la página **Seleccionar notificación de usuario final** , seleccione una de las siguientes opciones de notificación:

- **No entregar notificaciones**: haga clic en **Continuar** en el cuadro de diálogo de alerta que aparece. Si selecciona esta opción, se le llevará a la página [Programación de simulación](#simulation-schedule) al hacer clic en **Siguiente**.

- **Notificación predeterminada de Microsoft (recomendado):** la siguiente configuración adicional está disponible en la página:

  - **Seleccionar idioma predeterminado**: los valores disponibles son **: chino (simplificado)**, **chino (tradicional)**, **inglés**, **francés**, **alemán**, **italiano**, **japonés**, **coreano**, **portugués**, **ruso**, **español** y **holandés**.

  - De forma predeterminada, se incluyen las siguientes notificaciones:
    - **Notificación de refuerzo positivo de Microsoft**
    - **Notificación de asignación de entrenamiento predeterminada de Microsoft**
    - **Notificación de recordatorio de entrenamiento predeterminada de Microsoft**

    Para cada notificación, está disponible la siguiente información:
    - **Notificaciones**: nombre de la notificación.
    - **Idioma**: si la notificación contiene varias traducciones, los dos primeros idiomas se muestran directamente. Para ver los idiomas restantes, mantenga el puntero sobre el icono numérico (por ejemplo, **+10**).
    - **Tipo**: uno de los valores siguientes:
      - **Notificación de refuerzo positivo**
      - **Notificación de asignación de entrenamiento**
      - **Notificación de recordatorio de entrenamiento**
    - **Preferencias de entrega**: para los tipos de **notificación de refuerzo positivo** y **notificación de aviso de entrenamiento** , están disponibles los siguientes valores.
      - **No entregar**
      - **Entrega después de que finalice la campaña**
      - **Entrega durante la campaña**
    - **Acciones**: si hace clic en el ![icono Ver.](../../media/m365-cc-sc-view-icon.png) **Icono de vista** , aparece la página **Revisar notificación** con la siguiente información:
      - **Pestaña Vista previa** : vea el mensaje de notificación.
        - Para ver el mensaje en diferentes idiomas, use el cuadro **Seleccionar idioma** .
        - Use el cuadro **Seleccionar carga útil para obtener una vista previa** para seleccionar el mensaje de notificación para las simulaciones que contienen varias cargas.
      - **Pestaña Detalles** : vea los detalles sobre la notificación:
        - **Descripción de la notificación**
        - **Origen**: para las notificaciones integradas, el valor es **Global**. Para las notificaciones personalizadas, el valor es **Inquilino**.
        - **Tipo de notificación**: uno de los siguientes tipos se basa en la notificación que seleccionó originalmente:
          - **Notificación de refuerzo positivo**
          - **Notificación de asignación de entrenamiento**
          - **Notificación de recordatorio de entrenamiento**
        - **Modificado por**
        - **Última modificación**

        Cuando haya terminado, haga clic en **Cerrar**.

  Se le llevará a la página [Programación de simulación](#simulation-schedule) al hacer clic en **Siguiente**.

- **Notificaciones de usuario final personalizadas**: al hacer clic en **Siguiente**, se le llevará a la página **Notificación de asignación de entrenamiento** , tal como se describe en las secciones siguientes.

### <a name="training-assignment-notification"></a>Notificación de asignación de entrenamiento

La página **Notificación de asignación de entrenamiento** solo está disponible si seleccionó **Notificaciones personalizadas del usuario final** en la página **[Seleccionar notificación de usuario final](#select-end-user-notification)** .

En esta página se muestran las siguientes notificaciones y sus idiomas configurados:

- **Notificación de asignación de entrenamiento predeterminada de Microsoft**
- Cualquier notificación de asignación de entrenamiento personalizada que haya creado anteriormente.

  Estas notificaciones también están disponibles en la pestaña **Notificaciones de usuario final** en Entrenamiento de simulación de ataques en <https://security.microsoft.com/attacksimulator?viewid=endUserNotification>. La **notificación de asignación de entrenamiento predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales**. Las notificaciones de asignación de entrenamiento personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para el entrenamiento de simulación de ataques](attack-simulation-training-end-user-notifications.md).

Puede seleccionar una notificación de asignación de entrenamiento existente o crear una nueva notificación para usar:

- Para seleccionar una notificación existente, haga clic en el área en blanco situada junto al nombre de la notificación. Si hace clic en el nombre de la notificación, se selecciona la notificación y aparece un control flotante de vista previa. Para anular la selección de la notificación, desactive la casilla situada junto a la notificación.
- Para buscar una notificación existente, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre.

  Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

- Para crear y usar una nueva notificación, haga clic en ![el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Crear nuevo**.

#### <a name="create-new-training-assignment-notification-wizard"></a>Asistente para crear una notificación de asignación de entrenamiento

Si ha hecho ![clic en El icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree una nueva** en la página **Notificación de asignación de entrenamiento** , se abrirá un asistente para la creación de notificaciones.

Los pasos de creación son idénticos como se describe en [Creación de notificaciones de usuario final](attack-simulation-training-end-user-notifications.md#create-end-user-notifications).

> [!NOTE]
> En la página **Definir detalles** , asegúrese de seleccionar el valor **Notificación de asignación de entrenamiento** para **Seleccionar tipo de notificación**.

Cuando haya terminado, volverá a la página **Notificación de asignación de entrenamiento** , donde la notificación que acaba de crear aparece en la lista.

Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

### <a name="training-reminder-notification"></a>Notificación de recordatorio de entrenamiento

La página **Notificación de recordatorio de entrenamiento** solo está disponible si seleccionó **Notificaciones personalizadas del usuario final** en la página **[Seleccionar notificación del usuario final](#select-end-user-notification)** .

- **Establecer la frecuencia para la notificación de recordatorio**: seleccione **Semanal** (valor predeterminado) o **Dos veces a la semana**.

- **Seleccionar una notificación de recordatorio**: en esta sección se muestran las siguientes notificaciones y sus idiomas configurados:

  - **Notificación de recordatorio de entrenamiento predeterminada de Microsoft**
  - Cualquier notificación de recordatorio de entrenamiento personalizada que haya creado anteriormente.

    Estas notificaciones también están disponibles en la pestaña **Notificaciones de usuario final** en Entrenamiento de simulación de ataques en <https://security.microsoft.com/attacksimulator?viewid=endUserNotification>. La **notificación de recordatorio de entrenamiento predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales**. Las notificaciones de recordatorio de entrenamiento personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para el entrenamiento de simulación de ataques](attack-simulation-training-end-user-notifications.md).

  Puede seleccionar una notificación de recordatorio de entrenamiento existente o crear una nueva notificación para usar:

  - Para seleccionar una notificación existente, haga clic en el área en blanco situada junto al nombre de la notificación. Si hace clic en el nombre de la notificación, se selecciona la notificación y aparece un control flotante de vista previa. Para anular la selección de la notificación, desactive la casilla situada junto a la notificación.
  - Para buscar una notificación existente, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre.

    Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

  - Para crear y usar una nueva notificación, haga clic en ![el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Crear nuevo**.

#### <a name="create-new-training-reminder-notification-wizard"></a>Asistente para crear una notificación de recordatorio de entrenamiento

Si ha hecho ![clic en El icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree una nueva** en la página **Notificación de aviso de entrenamiento** , se abrirá un asistente para crear notificaciones.

Los pasos de creación son idénticos como se describe en [Creación de notificaciones de usuario final](attack-simulation-training-end-user-notifications.md#create-end-user-notifications).

> [!NOTE]
> En la página **Definir detalles** , asegúrese de seleccionar el valor **Notificación de recordatorio de entrenamiento** para **Seleccionar tipo de notificación**.

Cuando haya terminado, volverá a la página **Notificación de recordatorio de entrenamiento** , donde la notificación que acaba de crear aparece en la lista.

Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

### <a name="positive-reinforcement-notification"></a>Notificación de refuerzo positivo

La página **Notificación de refuerzo positivo** solo está disponible si seleccionó **Notificaciones personalizadas del usuario final** en la página **[Seleccionar notificación de usuario final](#select-end-user-notification)** .

- **Preferencias de entrega**: seleccione uno de los valores siguientes:

  - **No entregar**: si selecciona esta opción, se le llevará a la página Programación de [simulación](#simulation-schedule) al hacer clic en **Siguiente**.

  - **Entregar después de que el usuario informe de que finaliza una phish y una campaña** o **Entregar inmediatamente después de que el usuario informe de una phish**: estas secciones muestran las siguientes notificaciones y sus idiomas configurados en la sección **Seleccionar una notificación de refuerzo positivo** que aparece:

  - **Notificación de refuerzo positivo predeterminada de Microsoft**
  - Cualquier notificación de refuerzo positivo personalizada que haya creado anteriormente.

    Estas notificaciones también están disponibles en la pestaña **Notificaciones de usuario final** en Entrenamiento de simulación de ataques en <https://security.microsoft.com/attacksimulator?viewid=endUserNotification>. **La notificación de refuerzo positivo predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales** . Las notificaciones de refuerzo positivo personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para el entrenamiento de simulación de ataques](attack-simulation-training-end-user-notifications.md).

  Puede seleccionar una notificación de refuerzo positivo existente o crear una nueva notificación para usar:

  - Para seleccionar una notificación existente, haga clic en el área en blanco situada junto al nombre de la notificación. Si hace clic en el nombre de la notificación, se selecciona la notificación y aparece un control flotante de vista previa. Para anular la selección de la notificación, desactive la casilla situada junto a la notificación.
  - Para buscar una notificación existente, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre.

    Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

  - Para crear y usar una nueva notificación, haga clic en ![el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Crear nuevo**.

#### <a name="create-new-positive-reinforcement-notification-wizard"></a>Asistente para crear nuevas notificaciones de refuerzo positivo

Si ha hecho ![clic en El icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree una nueva** en la página **Notificación de refuerzo positivo** , se abrirá un asistente para la creación de notificaciones.

Los pasos de creación son idénticos como se describe en [Creación de notificaciones de usuario final](attack-simulation-training-end-user-notifications.md#create-end-user-notifications).

> [!NOTE]
> En la página **Definir detalles** , asegúrese de seleccionar el valor **Notificación de refuerzo positivo** para **Seleccionar tipo de notificación**.

Cuando haya terminado, volverá a la página **Notificación de refuerzo positivo** , donde la notificación que acaba de crear aparece en la lista.

Seleccione la notificación que desea usar y, a continuación, haga clic en **Siguiente**.

## <a name="simulation-schedule"></a>Programación de simulación

En la página **Programación de simulación** , seleccione uno de los valores siguientes:

- **Aleatorio**: todavía tiene que seleccionar la programación en la página siguiente, pero las simulaciones se iniciarán en momentos aleatorios con la programación.
- **Fixed**

Cuando termine, haga clic en **Siguiente**.

## <a name="schedule-details"></a>Detalles de programación

Lo que vea en la página **Detalles** de la programación depende de si **seleccionó Aleatorio** o **Fijo** en la página anterior.

- **Aleatorio**: están disponibles los siguientes valores:
  - **Sección de inicio de simulación** : Configure la siguiente configuración:
    - **Seleccione la fecha desde la que desea que comiencen las simulaciones.**
  - **Sección ámbito de simulación** : Configure los valores siguientes:
    - **Seleccione los días de la semana en los que pueden empezar las simulaciones**: seleccione uno o varios días de la semana.
    - **Escriba el número máximo de simulaciones que se pueden iniciar entre las fechas de inicio y finalización**: escriba un valor de 1 a 10.
    - **Aleatorizar las horas de envío**: seleccione esta configuración para aleatorizar las horas de envío.
  - **Sección final de simulación** : configure la siguiente configuración:
    - **Seleccione la fecha en que desea que finalicen las simulaciones.**

- **Corregido**: Hay disponibles los siguientes valores:
  - **Sección de inicio de simulación** : Configure la siguiente configuración:
    - **Seleccione la fecha desde la que desea que comiencen las simulaciones.**
  - **Sección Periodicidad de simulación** : Configure los siguientes valores:
    - **Seleccione si desea que las simulaciones se inicien semanalmente o mensualmente**: seleccione uno de los valores siguientes:
      - **Semanal**: este es el valor predeterminado.
      - **Mensualmente**
    - **Escriba la frecuencia con la que quiere que se repitan las simulaciones en semanas**: escriba un valor de 1 a 99 semanas.
    - **Seleccione el día de la semana desde el que desea que comiencen las simulaciones.**
  - **Sección final de simulación** : seleccione uno de los valores siguientes:
    - **Seleccione la fecha en que desea que finalicen las simulaciones.**
    - **Escriba el número de repeticiones de las simulaciones que se van a ejecutar antes de finalizar**: escriba un valor de 1 a 10.

Cuando termine, haga clic en **Siguiente**.

## <a name="launch-details"></a>Detalles del inicio

En la página **Detalles del inicio** , configure los siguientes valores adicionales para la automatización:

- **Usar cargas únicas en simulaciones dentro de una automatización**: de forma predeterminada, esta configuración no está seleccionada.
- **Delincuentes repetidos de destino**: de forma predeterminada, esta configuración no está seleccionada. Si lo selecciona, configure el siguiente valor que aparece:
  - **Escriba el número máximo de veces que un usuario puede tener como destino esta automatización**: escriba un valor de 1 a 10.
- **Enviar correo electrónico de simulación en función de la configuración de zona horaria actual del usuario desde Outlook aplicación web**: de forma predeterminada, esta configuración no está seleccionada.
- **Mostrar la página recopilada de datos intersticiales de la técnica drive-by**: esta configuración solo está disponible si seleccionó **Dirección URL de drive-by** en la página **[Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques)** . De forma predeterminada, la configuración está activada (![alternar en el icono).](../../media/scc-toggle-on.png)

## <a name="review-simulation-automation"></a>Revisión de la automatización de simulación

En la página **Revisar automatización de simulación** , puede revisar los detalles de la automatización de la simulación.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.
