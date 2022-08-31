---
title: Simule un ataque de suplantación de identidad con formación de simulación de ataques
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
ms.custom: ''
description: Los administradores pueden aprender a simular ataques de suplantación de identidad (phishing) y entrenar a sus usuarios en la prevención de suplantación de identidad mediante Entrenamiento de simulación de ataque en Microsoft Defender para Office 365 Plan 2.
ms.subservice: mdo
ms.openlocfilehash: 7983e1767565870cec1fb3457fc3466e99b0d8db
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474213"
---
# <a name="simulate-a-phishing-attack-with-attack-simulation-training-in-defender-for-office-365"></a>Simulación de un ataque de suplantación de identidad (phishing) con Entrenamiento de simulación de ataque en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Entrenamiento de simulación de ataque en Microsoft Defender para Office 365 plan 2 o Microsoft 365 E5 permite ejecutar simulaciones de ciberataques benignas en su organización. Estas simulaciones prueban las directivas y prácticas de seguridad, así como entrenan a los empleados para aumentar su reconocimiento y reducir su susceptibilidad a los ataques. Este artículo le guiará a través de la creación de un ataque simulado de suplantación de identidad mediante Entrenamiento de simulación de ataque.

Para obtener información de introducción sobre Entrenamiento de simulación de ataque, consulte [Introducción al uso de Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md).

Para iniciar un ataque de suplantación de identidad simulado, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya  a Email & pestaña **Entrenamiento de simulación de ataque Simulaciones** de **colaboración** \> \>.

   Para ir directamente a la pestaña **Simulaciones** , use <https://security.microsoft.com/attacksimulator?viewid=simulations>.

2. En la pestaña **Simulaciones** , seleccione ![Iniciar un icono de simulación.](../../media/m365-cc-sc-create-icon.png) **Inicie una simulación**.

   :::image type="content" source="../../media/attack-sim-training-simulations-launch.png" alt-text="El botón Iniciar una simulación en la pestaña Simulaciones de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-launch.png":::

3. Se abre el asistente para la creación de simulación. En el resto de este artículo se describen las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente para la creación de la simulación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y continuar configurando la simulación más adelante. La simulación incompleta tiene el valor **Estado** **Borrador** en la pestaña **Simulaciones** . Puede seleccionar dónde lo dejó seleccionando la simulación y haciendo clic en ![Editar icono de simulación.](../../media/m365-cc-sc-edit-icon.png) **Edición de** la simulación.

## <a name="select-a-social-engineering-technique"></a>Selección de una técnica de ingeniería social

En la página **Seleccionar técnica** , seleccione una técnica de ingeniería social disponible, que se ha seleccionado en el [marco DE ATT de MITRE&CK®](https://attack.mitre.org/techniques/enterprise/). Hay diferentes cargas disponibles para diferentes técnicas. Están disponibles las siguientes técnicas de ingeniería social:

- **Recopilación de credenciales**: intenta recopilar credenciales llevando a los usuarios a un sitio web de apariencia conocida con cuadros de entrada para enviar un nombre de usuario y una contraseña.
- **Datos adjuntos de malware**: agrega datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- **Vínculo en datos adjuntos**: un tipo de híbrido de recopilación de credenciales. Un atacante inserta una dirección URL en los datos adjuntos de un correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recopilación de credenciales.
- **Vínculo a malware**: ejecuta código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abrir el archivo ayudará al atacante a poner en peligro el dispositivo del destino.
- **Dirección URL de unidad por**: la dirección URL malintencionada del mensaje lleva al usuario a un sitio web de aspecto familiar que ejecuta o instala código de forma silenciosa en el dispositivo del usuario.
- **Concesión de consentimiento de OAuth**: la dirección URL malintencionada pide a los usuarios que concedan permisos a los datos para un Aplicación de Azure malintencionado.

Si hace clic en el vínculo **Ver detalles** de la descripción, se abre un control flotante de detalles que describe la técnica y los pasos de simulación que resultan de la técnica.

:::image type="content" source="../../media/attack-sim-training-simulations-select-technique-sim-steps.png" alt-text="Control flotante Detalles de la técnica de recolección de credenciales en la página Seleccionar técnica" lightbox="../../media/attack-sim-training-simulations-select-technique-sim-steps.png":::

Cuando termine, haga clic en **Siguiente**.

## <a name="name-and-describe-the-simulation"></a>Asigne un nombre y describa la simulación.

En la página **Simulación de nombres** , configure los siguientes valores:

- **Nombre**: escriba un nombre descriptivo único para la simulación.
- **Descripción**: escriba una descripción detallada opcional para la simulación.

Cuando termine, haga clic en **Siguiente**.

## <a name="select-a-payload-and-login-page"></a>Seleccionar una página de carga e inicio de sesión

En la página **Seleccionar carga e inicio de sesión** , debe seleccionar una carga existente en la lista o crear una nueva carga.

También puede ver la página de inicio de sesión que se usa en la carga útil, seleccionar una página de inicio de sesión diferente para usar o crear una nueva página de inicio de sesión para usarla.

### <a name="payload"></a>Carga útil

Se muestran los detalles siguientes para cada carga:

- **Nombre de carga**
- **Idioma**: idioma del contenido de la carga. El catálogo de cargas de Microsoft (global) proporciona cargas en más de 10 idiomas que también se pueden filtrar.
- **Tasa de clics**: cuántas personas han hecho clic en esta carga.
- **Tasa de riesgo prevista**: datos históricos de la carga útil en Microsoft 365 que predice el porcentaje de personas que se verán comprometidas por esta carga.
- **Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.

En el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** , puede escribir parte del nombre de carga útil y presionar Entrar para filtrar los resultados.

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Complejidad**: se calcula en función del número de indicadores de la carga útil que indican un posible ataque (errores ortográficos, urgencia, etc.). Más indicadores son más fáciles de identificar como un ataque e indican una menor complejidad. Los valores disponibles son los siguientes:
  - **Alto**
  - **Medio**
  - **Baja**

- **Idioma**: Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** u **otro**.

- **Agregar etiquetas**

- **Filtrar por tema**: Los valores disponibles son: **Activación de la cuenta**, **Verificación de cuenta**, **Facturación**, **Limpiar correo**, **Documento recibido**, **Gastos**, **Fax**, **Informe financiero**, **Mensajes entrantes**, **Factura**, **Elementos recibidos**, **Alerta de inicio de sesión**, **Correo recibido**, **Contraseña**, **Pago**, **Nómina**, **Oferta personalizada**, **Cuarentena**, **Trabajo remoto**, **Mensaje de revisión**, **Actualización de seguridad**, **Servicio suspendido**, **Firma necesaria**, **Actualizar almacenamiento del buzón Comprobar buzón**, **Correo de voz** y **Otros**.

- **Filtrar por marca**: Los valores disponibles son: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** y **otros**.

- **Filtrar por sector**: Los valores disponibles son: **Banca**, **Servicios empresariales**, **Servicios de consumo**, **Educación**, **Energía**, **Construcción**, **Consultoría**, **Servicios financieros**, **Gobierno**, **Hostelería**, **Seguros**, **Legal**, **Servicios de mensajería**, **TI**, **Salud**, **Fabricación**, **Minorista**, **Telecomunicaciones**, **Bienes Raíces**, y **otros**.

- **Evento actual**: los valores disponibles son **Sí** o **No**.

- **Controversial**: los valores disponibles son **Sí** o **No**.

Cuando haya terminado de configurar los filtros, haga clic en **el** icono](../../media/m365-cc-sc-clear-filters-icon.png) Aplicar, **Cancelar** o ![Borrar filtros **Borrar filtros**.

Si selecciona una carga de la lista seleccionando la casilla , un ![icono Enviar una carga útil de prueba.](../../media/m365-cc-sc-create-icon.png) **El botón Enviar una prueba** aparece en la página principal, donde puede enviar una copia del correo electrónico de carga a usted mismo (el usuario que ha iniciado sesión actualmente) para su inspección.

Para crear su propia carga, haga clic en ![el icono Crear una carga.](../../media/m365-cc-sc-create-icon.png) **Cree una carga**. Para obtener más información, consulte [Creación de cargas personalizadas para Entrenamiento de simulación de ataque](attack-simulation-training-payloads.md#create-payloads).

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload.png" alt-text="La página Seleccionar carga útil de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-select-payload.png":::

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
> Esta página solo está disponible si seleccionó **Concesión de consentimiento de OAuth** en la página [Seleccionar técnica](#select-a-social-engineering-technique) . De lo contrario, se le dirigirá a la página **Usuarios de destino** .

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

## <a name="target-users"></a>Usuarios de destino

En la página **Usuarios de destino** , seleccione quién recibirá la simulación. Configure una de las siguientes opciones:

- **Incluir todos los usuarios de la organización**: los usuarios afectados se muestran en listas de 10. Puede usar los botones **Siguiente** y **Anterior** directamente debajo de la lista de usuarios para desplazarse por la lista. También puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Icono de búsqueda** en la página para buscar usuarios afectados.

- **Incluir solo usuarios y grupos específicos**: elija una de las siguientes opciones:
  - ![Icono Agregar usuarios.](../../media/m365-cc-sc-create-icon.png) **Agregar usuarios**: en el control flotante **Agregar usuarios** que aparece, puede encontrar usuarios y grupos según los criterios siguientes:

    - **Buscar usuarios o grupos**: en el cuadro , puede escribir parte del **nombre** o **Email dirección** del usuario o grupo y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados. Cuando haya terminado, haga clic en **Agregar x usuarios**.

      > [!NOTE]
      > Al hacer clic en el botón **Agregar filtros** para volver a las opciones **Filtrar usuarios por categorías** , se borrarán los usuarios o grupos seleccionados en los resultados de la búsqueda.

    - **Filtrar usuarios por categorías**: seleccione entre ninguna, algunas o todas las opciones siguientes:

      - **Grupos de usuarios sugeridos**: seleccione entre los valores siguientes:
        - **Todos los grupos de usuarios sugeridos**
        - **Usuarios no dirigidos por una simulación en los últimos tres meses**
        - **Reincidentes**

      - **Etiquetas de usuario**: las etiquetas de usuario son identificadores para grupos específicos de usuarios (por ejemplo, cuentas de prioridad). Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365](user-tags.md).

          Use las siguientes opciones:

        - **Buscar**: en ![el icono Buscar por etiquetas de usuario.](../../media/m365-cc-sc-search-icon.png) **Busque por etiquetas de usuario**, puede escribir parte de la etiqueta de usuario y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccione **Todas las etiquetas de usuario.**
        - Seleccione las etiquetas de usuario existentes.

      - **Departamento**: Use las siguientes opciones:
        - **Buscar**: en ![el icono Buscar por departamento.](../../media/m365-cc-sc-search-icon.png) **Busque por departamento**, puede escribir parte del valor Departamento y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el departamento**
        - Seleccione los valores de Departamento existentes.

      - **Título**: Use las siguientes opciones:
        - **Buscar**: en ![el icono Buscar por título.](../../media/m365-cc-sc-search-icon.png) **Busque por título**, puede escribir parte del valor título y, a continuación, presionar Entrar. Puede seleccionar algunos o todos los resultados.
        - Seleccionar **todo el título**
        - Seleccione los valores de Título existentes.

      :::image type="content" source="../../media/attack-sim-training-simulations-target-users-filter-by-category.png" alt-text="Filtrado de usuarios en la página Usuarios de destino de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-target-users-filter-by-category.png":::

      Después de identificar los criterios, los usuarios afectados se muestran en la sección **Lista** de usuarios que aparece, donde puede seleccionar algunos o todos los destinatarios detectados.

      Cuando haya terminado, haga clic en **Aplicar(x)** y, a continuación, haga clic en **Agregar x usuarios**.

  De nuevo en la página **principal Usuarios de destino** , puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar usuarios afectados. También puede hacer clic en ![el icono Eliminar usuarios.](../../media/m365-cc-sc-search-icon.png) **Eliminar** para quitar usuarios específicos.

- ![Icono importar.](../../media/m365-cc-sc-create-icon.png) **Importar**: en el cuadro de diálogo que se abre, especifique un archivo CSV que contenga una dirección de correo electrónico por línea.

  Después de encontrar un archivo CSV seleccionado, la lista de usuarios se importa y se muestra en la página **Usuarios de destino** . Puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar usuarios afectados. También puede hacer clic en ![el icono Eliminar usuarios de destino.](../../media/m365-cc-sc-delete-icon.png) **Eliminar** para quitar usuarios específicos.

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

Para cada entrenamiento de la lista, debe seleccionar quién obtiene el entrenamiento seleccionando valores en la columna **Asignar a** :

- **Todos los usuarios**

  o uno o ambos de los siguientes valores:

- **Carga en la que se ha hecho clic**
- **Comprometido**

Si no desea usar un entrenamiento que se muestra, haga clic en ![el icono Eliminar entrenamiento.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

:::image type="content" source="../../media/attack-sim-training-training-assignment.png" alt-text="Página Asignación de entrenamiento de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-training-assignment.png":::

Cuando termine, haga clic en **Siguiente**.

### <a name="landing-page"></a>Página de aterrizaje

En la **página De aterrizaje** , configurará la página web a la que se llevará el usuario si abre la carga en la simulación.

Las páginas de aterrizaje seleccionadas por Microsoft están disponibles en 12 idiomas: chino (simplificado), chino (tradicional), inglés, francés, alemán, italiano, japonés, coreano, portugués, ruso, español y holandés.

- **Seleccionar preferencia de página de aterrizaje**: los valores disponibles son:
  - **Usar la página de aterrizaje predeterminada de Microsoft**: este es el valor predeterminado que tiene las siguientes opciones asociadas para configurar:
    - **Seleccionar diseño de página de aterrizaje**: seleccione una de las plantillas disponibles.
    - **Agregar logotipo**: haga clic en **Examinar** para buscar y seleccionar un archivo .png, .jpeg o .gif. El tamaño del logotipo debe ser un máximo de 210 x 70 para evitar distorsión. Para quitar el logotipo, haga clic en **Quitar**.
    - **Agregar indicadores de carga al correo electrónico**: esta configuración no está disponible si seleccionó anteriormente **Datos adjuntos de malware** o **Vincular a malware** en la página [Seleccionar técnica](#select-a-social-engineering-technique) .

    Puede obtener una vista previa de los resultados haciendo clic en el botón **Abrir panel de vista previa** en la parte inferior de la página.

  - **Usar una dirección URL personalizada**: esta configuración no está disponible si seleccionó anteriormente **Datos adjuntos de malware** o **Vincular a malware** en la página [Seleccionar técnica](#select-a-social-engineering-technique) .

    Si selecciona **Usar una dirección URL personalizada**, debe agregar la dirección URL en el cuadro **Escribir la dirección URL de la página de aterrizaje personalizada** que aparece. No hay otras opciones disponibles en la página.

  - **Crear su propia página de aterrizaje**: este valor tiene las siguientes opciones asociadas para configurar:
    - **Agregar indicadores de carga al correo electrónico**: esta configuración solo está disponible para seleccionar si se cumplen las dos instrucciones siguientes:
      - Ha seleccionado **Cosecha de credenciales**, **Vincular en datos adjuntos**, **Dirección URL de unidad** o **Concesión de consentimiento de OAuth** en la página [Seleccionar técnica](#select-a-social-engineering-technique) .
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

        - **Usar de forma predeterminada**: seleccione una plantilla disponible con la que empezar. Puede modificar el texto y el diseño en el área de edición. Para restablecer la página de aterrizaje al texto predeterminado y el diseño de la plantilla, haga clic en **Restablecer al valor predeterminado**.
    - **Código**: puede ver y modificar el código HTML directamente.

    Puede obtener una vista previa de los resultados haciendo clic en el botón **Abrir panel vista previa** en el centro de la página.

Cuando termine, haga clic en **Siguiente**.

> [!NOTE]
> Ciertas marcas comerciales, logotipos, símbolos, insignias y otros identificadores de origen reciben una protección mayor en virtud de leyes y leyes locales, estatales y federales. El uso no autorizado de dichos indicadores puede someter a los usuarios a sanciones, incluidas las multas penales. Aunque no es una lista extensa, esto incluye los sellos presidencial, vicepresidencial y del Congreso, la CIA, el FBI, el Seguro Social, Medicare y Medicaid, el Servicio de Ingresos Internos de Estados Unidos y los Juegos Olímpicos. Más allá de estas categorías de marcas comerciales, el uso y la modificación de cualquier marca comercial de terceros conlleva una cantidad inherente de riesgo. El uso de sus propias marcas comerciales y logotipos en una carga sería menos arriesgado, especialmente cuando su organización permite el uso. Si tiene más preguntas sobre lo que es o no es adecuado usar al crear o configurar una carga, debe consultar con sus asesores legales.

## <a name="select-end-user-notification"></a>Selección de la notificación del usuario final

En la página **Seleccionar notificación de usuario final** , seleccione una de las siguientes opciones de notificación:

- **No entregar notificaciones**: haga clic en **Continuar** en el cuadro de diálogo de alerta que aparece. Si selecciona esta opción, se le llevará a la página [Iniciar detalles](#launch-details) al hacer clic en **Siguiente**.

- **Notificación predeterminada de Microsoft (recomendado):** la siguiente configuración adicional está disponible en la página:

  - **Seleccionar idioma predeterminado**: Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** u **otro**.

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

  Se le llevará a la página [Detalles del inicio](#launch-details) al hacer clic en **Siguiente**.

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

  - **No entregar**: si selecciona esta opción, se le llevará a la página [Iniciar detalles](#launch-details) al hacer clic en **Siguiente**.

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

## <a name="launch-details"></a>Detalles del inicio

En la página **Iniciar detalles** , elija cuándo iniciar la simulación y cuándo finalizar la simulación. Dejaremos de capturar la interacción con esta simulación después de la fecha de finalización que especifique.

Estas son las opciones de configuración disponibles:

- Elija uno de los siguientes valores:
  - **Inicie esta simulación tan pronto como haya terminado.**
  - **Programe esta simulación para que se inicie más adelante**: este valor tiene las siguientes opciones asociadas para configurar:
    - **Seleccionar fecha de inicio**
    - **Seleccionar la hora de inicio**
- **Configure el número de días para finalizar la simulación después** de: El valor predeterminado es 2.
- **Habilitar la entrega de zona horaria compatible con la región**: entregue mensajes de ataque simulados a los empleados durante su horario laboral en función de su región.

- **Mostrar la página recopilada de datos intersticiales de técnica de unidad por**: esta configuración solo está disponible si seleccionó **Dirección URL de unidad por** en la página [seleccionar una técnica](#select-a-social-engineering-technique) . Puede mostrar la superposición que aparece para los ataques de técnica de dirección URL de unidad por. Para ocultar la superposición e ir directamente a la página de aterrizaje, no seleccione esta opción.

Cuando termine, haga clic en **Siguiente**.

## <a name="review-simulation"></a>Revisión de la simulación

En la página **Revisar simulación** , puede revisar los detalles de la simulación.

Haga clic en el ![icono Enviar una prueba.](../../media/m365-cc-sc-send-icon.png) **Enviar un botón de prueba** para enviar una copia del correo electrónico de carga a usted mismo (el usuario que ha iniciado sesión actualmente) para su inspección.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.

:::image type="content" source="../../media/attack-sim-training-simulations-review-simulation.png" alt-text="La página Revisar simulación de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-simulations-review-simulation.png":::
