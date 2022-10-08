---
title: Automatizaciones de simulación para Entrenamiento de simulación de ataque
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear simulaciones automatizadas que contienen técnicas y cargas específicas que se inician cuando se cumplen las condiciones especificadas en Microsoft Defender para Office 365 plan 2.
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 0fb6e45150d04e8a376964584506fc4ac876bd08
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060634"
---
# <a name="simulation-automations-for-attack-simulation-training"></a>Automatizaciones de simulación para Entrenamiento de simulación de ataque

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Para obtener información de introducción sobre Entrenamiento de simulación de ataque, consulte [Introducción al uso de Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md).

Para crear una automatización de simulación, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com/>, vaya a **Email & pestaña** \> **Automatizaciones** de la colaboración \> **Entrenamiento de simulación de ataque** \> **Automatizaciones automatizaciones**.

   Para ir directamente a la pestaña **Automatizaciones** , donde puede seleccionar **Automatizaciones de simulación**, use <https://security.microsoft.com/attacksimulator?viewid=automations>.

2. En **Automatizaciones de simulación**, seleccione ![El icono Crear automatización.](../../media/m365-cc-sc-create-icon.png) **Crear automatización**.

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="El botón Crear simulación de la pestaña Automatizaciones de simulación de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

3. Se abre el asistente para la creación. En el resto de este artículo se describen las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente para la creación de la simulación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y continuar configurando la simulación más adelante. La simulación incompleta tiene el valor **Estado** **Borrador** en la pestaña **Simulaciones** . Puede seleccionar dónde lo dejó seleccionando la simulación y haciendo clic en ![Editar icono de simulación.](../../media/m365-cc-sc-edit-icon.png) **Edite** simulation.## Asigne un nombre y describa la simulación.

## <a name="name-and-describe-the-simulation-automation"></a>Asigne un nombre y describa la automatización de la simulación.

En la página **Nombre de Automation** , configure los siguientes valores:

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
- **Concesión de consentimiento de OAuth**: la dirección URL malintencionada pide a los usuarios que concedan permisos a los datos para un Aplicación de Azure malintencionado.

Si hace clic en el vínculo **Ver detalles** de la descripción, se abre un control flotante de detalles que describe la técnica y los pasos de simulación que resultan de la técnica.

:::image type="content" source="../../media/attack-sim-training-simulations-select-technique-sim-steps.png" alt-text="El control flotante Detalles de la técnica de recolección de credenciales en la página Seleccionar técnicas de ingeniería social" lightbox="../../media/attack-sim-training-simulations-select-technique-sim-steps.png":::

Cuando termine, haga clic en **Siguiente**.

## <a name="select-a-payload-and-login-page"></a>Seleccionar una página de carga e inicio de sesión

En la página **Seleccionar carga e inicio de sesión** , debe seleccionar una carga existente en la lista o crear una nueva carga.

También puede ver la página de inicio de sesión que se usa en la carga útil, seleccionar una página de inicio de sesión diferente para usar o crear una nueva página de inicio de sesión para usarla.

### <a name="payload"></a>Carga útil

En la página **Seleccionar cargas,** seleccione una de las siguientes opciones:

- **Selección manual**
- **Randomize**

Si selecciona **Aleatorio**, no hay nada que configurar en esta página, por lo que haga clic en **Siguiente** para continuar.

Si selecciona **Seleccionar manualmente**, debe seleccionar una o varias cargas de la lista. Se muestran los detalles siguientes para cada carga:

- **Nombre de carga**
- **Técnica**: debe seleccionar al menos una carga por técnica que seleccionó en la página anterior.
- **Idioma**: Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** u **otro**.
- **Tasa de clics**: cuántas personas han hecho clic en esta carga.
- **Tasa de riesgo prevista**: datos históricos en Microsoft 365 que predice el porcentaje de personas que se verán comprometidas por esta carga (usuarios en peligro o número total de usuarios que reciben la carga).
- **Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.

En el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** , puede escribir parte del nombre de carga útil y presionar Entrar para filtrar los resultados.

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Complejidad**: se calcula en función del número de indicadores de la carga útil que indican un posible ataque (errores ortográficos, urgencia, etc.). Más indicadores son más fáciles de identificar como un ataque e indican una menor complejidad. Los valores disponibles son los siguientes:
  - **Alto**
  - **Medio**
  - **Baja**

- **Language**

- **Agregar etiquetas**

- **Filtrar por tema**: Los valores disponibles son: **Activación de la cuenta**, **Verificación de cuenta**, **Facturación**, **Limpiar correo**, **Documento recibido**, **Gastos**, **Fax**, **Informe financiero**, **Mensajes entrantes**, **Factura**, **Elementos recibidos**, **Alerta de inicio de sesión**, **Correo recibido**, **Contraseña**, **Pago**, **Nómina**, **Oferta personalizada**, **Cuarentena**, **Trabajo remoto**, **Mensaje de revisión**, **Actualización de seguridad**, **Servicio suspendido**, **Firma necesaria**, **Actualizar almacenamiento del buzón Comprobar buzón**, **Correo de voz** y **Otros**.

- **Filtrar por marca**: Los valores disponibles son: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** y **otros**.

- **Filtrar por sector**: Los valores disponibles son: **Banca**, **Servicios empresariales**, **Servicios de consumo**, **Educación**, **Energía**, **Construcción**, **Consultoría**, **Servicios financieros**, **Gobierno**, **Hostelería**, **Seguros**, **Legal**, **Servicios de mensajería**, **TI**, **Salud**, **Fabricación**, **Minorista**, **Telecomunicaciones**, **Bienes Raíces**, y **otros**.

- **Evento actual**: los valores disponibles son **Sí** o **No**.

- **Controversial**: los valores disponibles son **Sí** o **No**.

Cuando haya terminado de configurar los filtros, haga clic en **el** icono](../../media/m365-cc-sc-clear-filters-icon.png) Aplicar, **Cancelar** o ![Borrar filtros **Borrar filtros**.

Si selecciona una carga de la lista haciendo clic en cualquier lugar de la fila que no sea la casilla, los detalles sobre la carga se muestran en un control flotante:

- La pestaña **Carga contiene** un ejemplo y otros detalles sobre la carga.
- La pestaña **Página inicio de sesión** solo está disponible en **Credential Harvest** o **Link en cargas de datos adjuntos** y se describe en la sección siguiente.
- La pestaña **Simulaciones iniciadas** contiene el **nombre de la simulación**, **la tasa de clics**, **la velocidad comprometida** y **la acción**.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-details-payload-tab.png" alt-text="La pestaña Carga del control flotante de detalles de carga en Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-select-payload-details-payload-tab.png":::

### <a name="login-page"></a>Página de inicio de sesión

> [!NOTE]
> La pestaña **Página inicio de sesión** solo está disponible en **Credential Harvest** o **Link en cargas de datos adjuntos** .

Seleccione la carga de la lista haciendo clic en cualquier lugar de la fila que no sea la casilla para abrir el control flotante de detalles.

La pestaña **Página de inicio de sesión** del control flotante detalles de carga muestra la página de inicio de sesión seleccionada actualmente para la carga.

Para ver la página de inicio de sesión completa, use los vínculos **Página 1** y **Página 2** en la parte inferior de la página para las páginas de inicio de sesión de dos páginas.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-details-login-page-tab.png" alt-text="Pestaña de página de inicio de sesión en el control flotante de detalles de carga en Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-select-payload-details-login-page-tab.png":::

Para cambiar la página de inicio de sesión que se usa en la carga, haga clic en ![el icono Cambiar página de inicio de sesión.](../../media/m365-cc-sc-edit-icon.png) **Cambiar página de inicio de sesión**.

En el control flotante **Seleccionar página de inicio de sesión** que aparece, se muestra la siguiente información para cada página de inicio de sesión:

- **Nombre**
- **Language**
- **Origen**: para las páginas de inicio de sesión integradas, el valor es **Global**. Para las páginas de inicio de sesión personalizadas, el valor es **Inquilino**.
- **Estado**: **Listo** o **Borrador**.
- **Creado por**: para las páginas de inicio de sesión integradas, el valor es **Microsoft**. Para las páginas de inicio de sesión personalizadas, el valor es el UPN del usuario que creó la página de inicio de sesión.
- **Última modificación**
- **Acciones**: haga clic en el ![icono Vista previa.](../../media/m365-cc-sc-eye-icon.png) **Vista previa** para obtener una vista previa de la página de inicio de sesión.

Para buscar una página de inicio de sesión en la lista, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre de la página de inicio de sesión.

Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar las páginas de inicio de sesión por **origen** o **idioma**.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-select-login-page.png" alt-text="La página Seleccionar inicio de sesión de la pestaña Página de inicio de sesión del control flotante detalles de carga en Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-select-payload-select-login-page.png":::

Para crear una nueva página de inicio de sesión, haga clic en [el icono Crear nuevo.](../../media/m365-cc-sc-create-icon.png) **Cree una nueva** para iniciar el asistente para crear la página de inicio de sesión del usuario final. Los pasos son los mismos que en las **páginas de inicio de sesión** de **Entrenamiento de simulación de ataque** \> pestaña **Biblioteca de contenido simulado**. Para obtener instrucciones, consulte [Creación de páginas de inicio de sesión](attack-simulation-training-login-pages.md#create-login-pages).

De nuevo en la **página Seleccionar inicio de sesión**, compruebe que está seleccionada la nueva página de inicio de sesión que creó y, a continuación, haga clic en **Guardar**.

De nuevo en el control flotante detalles de carga, haga clic en [el icono Cerrar.](../../media/m365-cc-sc-close-icon.png) **Cerrar**.

Cuando haya terminado en la **página Seleccionar una carga e inicio de sesión**, haga clic en **Siguiente**.

## <a name="configure-oauth-payload"></a>Configuración de la carga de OAuth

> [!NOTE]
> Esta página solo está disponible si seleccionó **Concesión de consentimiento de OAuth** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) . De lo contrario, se le dirigirá a la página **Usuarios de destino** .

En la página **Configurar carga de OAuth** , configure los siguientes valores:

- **Nombre de la aplicación**

- **Logotipo de la aplicación**: haga clic en **Examinar** para seleccionar un archivo .png, .jpeg o .gif que se va a usar. Para quitar un archivo después de seleccionarlo, haga clic en **Quitar**.

- **Seleccionar ámbito de aplicación**: elija uno de los valores siguientes:
  - **Leer los calendarios del usuario**
  - **Leer los contactos del usuario**
  - **Leer el correo del usuario**
  - **Leer todos los mensajes de chat**
  - **Leer todos los archivos a  los que el usuario puede tener acceso**
  - **Acceso al correo del usuario para la lectura y la escritura**
  - **Enviar correo como usuario**

Cuando haya terminado en la página **Configurar carga de OAuth** , haga clic en **Siguiente**.

## <a name="target-users"></a>Usuarios de destino

En la página **Usuarios de destino** , seleccione quién recibirá la simulación. Configure una de las siguientes opciones:

- **Incluir todos los usuarios de la organización**: los usuarios afectados se muestran en listas de 10. Puede usar los botones **Siguiente** y **Anterior** directamente debajo de la lista de usuarios para desplazarse por la lista. También puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Icono de búsqueda** en la página para buscar usuarios afectados.
- **Incluir solo usuarios y grupos específicos**: elija una de las siguientes opciones:
  - ![Icono Agregar usuarios.](../../media/m365-cc-sc-create-icon.png) **Agregar usuarios**: en el control flotante **Agregar usuarios** que aparece, puede encontrar usuarios y grupos según los criterios siguientes:
    - **Usuarios o grupos**: en el ![icono Buscar usuarios y grupos.](../../media/m365-cc-sc-search-icon.png) **Cuadro Buscar usuarios y grupos**, puede escribir parte del **nombre** o **Email dirección** del usuario o grupo y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados. Cuando haya terminado, haga clic en **Agregar x usuarios**.

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

      :::image type="content" source="../../media/attack-sim-training-simulations-target-users-filter-by-category.png" alt-text="Filtrado de usuarios en la página Usuarios de destino de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-target-users-filter-by-category.png":::

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

:::image type="content" source="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png" alt-text="Opción para agregar el entrenamiento recomendado en la página Asignación de entrenamiento de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png":::

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

Si no desea usar un entrenamiento que se muestra, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

:::image type="content" source="../../media/attack-sim-training-training-assignment.png" alt-text="Página Asignación de entrenamiento de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-training-assignment.png":::

Cuando termine, haga clic en **Siguiente**.

### <a name="landing-page"></a>Página de aterrizaje

En la **página De aterrizaje** , configurará la página web a la que se llevará el usuario si abre la carga en la simulación.

- **Seleccionar preferencia de página de aterrizaje**: los valores disponibles dependen de las selecciones de carga anteriores en la página [Seleccionar una carga e inicio de sesión](#select-a-payload-and-login-page) , tal como se describe en la tabla siguiente:

  |Selección de carga|Valores disponibles para Seleccionar preferencia de página de aterrizaje|
  |---|---|
  |Selección manual|Uso de la página de aterrizaje predeterminada de Microsoft <br><br> Crear su propia página de aterrizaje <p> Uso de una dirección URL personalizada <p> **Nota**: El valor **Usar una dirección URL personalizada** no está disponible si seleccionó anteriormente **Datos adjuntos de malware** o **Vínculo a malware** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) .|
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

    - **Agregar indicadores de carga al correo electrónico**: esta configuración solo está disponible para seleccionar si se cumplen las dos instrucciones siguientes:
      - Ha seleccionado **Cosecha de credenciales**, **Vincular en datos adjuntos**, **Dirección URL de unidad** o **Concesión de consentimiento de OAuth** en la página [Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques) .
      - Ha agregado la **etiqueta dinámica** denominada **Insertar contenido de carga útil** en el contenido de la página de aterrizaje de esta página.

    - Contenido de la página de aterrizaje: hay dos pestañas disponibles:

      - **Texto**: hay disponible un editor de texto enriquecido para crear la página de aterrizaje. Además de la configuración típica de fuente y formato, están disponibles las siguientes opciones:
        - **Etiqueta dinámica**: seleccione una de las siguientes etiquetas:

          |Nombre de etiqueta|Valor de etiqueta|
          |---|---|
          |**Insertar nombre de usuario**|`${userName}`|
          |**Insertar nombre**|`${firstName}`|
          |**Insertar apellidos**|`${lastName}`|
          |**Insertar UPN**|`${upn}`|
          |**Insertar Email**|`${emailAddress}`|
          |**Insertar departamento**|`${department}`|
          |**Insertar administrador**|`${manager}`|
          |**Insertar teléfono móvil**|`${mobilePhone}`|
          |**Insertar ciudad**|`${city}`|
          |**Insertar nombre del remitente**|`${FromName}`|
          |**Insertar correo electrónico del remitente**|`${FromEmail}`|
          |**Insertar asunto de carga**|`${EmailSubject}`|
          |**Insertar contenido de carga útil**|`${EmailContent}`|
          |**Insertar fecha**|`${date|MM/dd/yyyy|offset}`|

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
      - **Pestaña Vista previa** : vea el mensaje de notificación como lo verán los usuarios.
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

  Estas notificaciones también están disponibles en **Notificaciones de usuario final** en la pestaña **Biblioteca de contenido de simulación** en Entrenamiento de simulación de ataque en <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>. La **notificación de asignación de entrenamiento predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales**. Las notificaciones de asignación de entrenamiento personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para Entrenamiento de simulación de ataque](attack-simulation-training-end-user-notifications.md).

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

    Estas notificaciones también están disponibles en **Notificaciones de usuario final** en la pestaña **Biblioteca de contenido de simulación** en Entrenamiento de simulación de ataque en <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>. La **notificación de recordatorio de entrenamiento predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales**. Las notificaciones de recordatorio de entrenamiento personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para Entrenamiento de simulación de ataque](attack-simulation-training-end-user-notifications.md).

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

    Estas notificaciones también están disponibles en **Notificaciones de usuario final** en la pestaña **Biblioteca de contenido de simulación** en Entrenamiento de simulación de ataque en <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>. **La notificación de refuerzo positivo predeterminada de Microsoft** está disponible en la pestaña **Notificaciones globales**. Las notificaciones de refuerzo positivo personalizadas están disponibles en la pestaña **Notificaciones de inquilino.** Para obtener más información, consulte [Notificaciones de usuario final para Entrenamiento de simulación de ataque](attack-simulation-training-end-user-notifications.md).

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
- **Dirigirse a todos los usuarios seleccionados en cada ejecución de simulación**: de forma predeterminada, esta configuración no está seleccionada.
- **Delincuentes repetidos de destino**: de forma predeterminada, esta configuración no está seleccionada. Si lo selecciona, configure el siguiente valor que aparece:
  - **Escriba el número máximo de veces que un usuario puede tener como destino esta automatización**: escriba un valor de 1 a 10.
- **Enviar correo electrónico de simulación en función de la configuración de zona horaria actual del usuario desde la aplicación web de Outlook**: de forma predeterminada, esta configuración no está seleccionada.

- **Mostrar la página recopilada de datos intersticiales de la técnica drive-by**: esta configuración solo está disponible si seleccionó **Dirección URL de drive-by** en la página **[Seleccionar técnicas de ingeniería social](#select-one-or-more-social-engineering-techniques)** .  Puede mostrar la superposición que aparece para los ataques de técnica de dirección URL de unidad por. De forma predeterminada, la configuración está activando Alternar ![en el icono.](../../media/scc-toggle-on.png) Para ocultar la superposición y ir directamente a la página de aterrizaje, desactive esta opción ![Desactivar icono.](../../media/scc-toggle-off.png)

## <a name="review-simulation-automation"></a>Revisión de la automatización de simulación

En la página **Revisar automatización de simulación** , puede revisar los detalles de la automatización de la simulación.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.
