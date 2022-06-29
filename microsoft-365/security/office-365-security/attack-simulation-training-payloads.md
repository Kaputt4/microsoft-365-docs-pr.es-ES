---
title: Cargas en el entrenamiento de simulación de ataques
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
ms.custom: ''
description: Los administradores pueden aprender a crear y administrar cargas para el entrenamiento de simulación de ataques en Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.openlocfilehash: 38e9e60c50a7bc0dec4e8f9f75845fdc34e4b237
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66487232"
---
# <a name="payloads-in-attack-simulation-training-in-defender-for-office-365"></a>Cargas en el entrenamiento de simulación de ataques en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En Entrenamiento de simulación de ataques, una _carga_ es el mensaje de correo electrónico de suplantación de identidad (phishing) y vínculos o contenido adjunto que se presentan a los usuarios en simulaciones. El entrenamiento de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 ofrece un sólido catálogo de cargas integradas para las técnicas de ingeniería social disponibles. Sin embargo, es posible que quiera crear cargas personalizadas que funcionen mejor para su organización.

Para ver las cargas disponibles, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a correo **electrónico &** pestaña \> Biblioteca de contenido de **simulación de entrenamiento** \> de **simulación de simulación** de colaboración \> y, a continuación, seleccione **Cargas.** Para ir directamente a la pestaña **Biblioteca de contenido de simulación** , donde puede seleccionar **Cargas útiles**, use <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

**Las cargas de** la pestaña **Biblioteca de contenido de simulación** tienen dos pestañas:

- **Cargas globales**: contiene las cargas integradas y no modificables.
- **Cargas de inquilino:** contiene las cargas personalizadas que ha creado.

Se muestra la siguiente información para cada carga:

- **Nombre de carga**
- **Tipo**: actualmente, este valor siempre es **Ingeniería social**.
- **Idioma**: si la carga contiene varias traducciones, los dos primeros idiomas se muestran directamente. Para ver los idiomas restantes, mantenga el puntero sobre el icono numérico (por ejemplo, **+10**).
- **Origen**: en el caso de las cargas integradas, el valor es **Global**. En el caso de las cargas personalizadas, el valor es **Tenant**.
- **Simulaciones iniciadas**: el número de simulaciones iniciadas que usan la carga útil.
- **Tasa de riesgo (%)**: en el caso de las cargas integradas, este valor es la tasa de riesgo promedio prevista para las simulaciones de entrenamiento de simulación de ataques que usan el mismo tipo de carga en todas las demás organizaciones de Microsoft 365.
- **Creado por**: para cargas integradas, el valor es **Microsoft**. En el caso de las cargas personalizadas, el valor es el UPN del usuario que creó la carga.
- **Última modificación**
- **Técnica**: Una de las [técnicas de ingeniería social](attack-simulation-training.md#select-a-social-engineering-technique) disponibles:
  - **Cosecha de credenciales**
  - **Datos adjuntos de malware**
  - **Vínculo en datos adjuntos**
  - **Vínculo a malware**
  - **Dirección URL de unidad por**
- **Estado**: el valor es **Listo** o **Borrador**. En la pestaña **Cargas globales** , el valor siempre está **listo**.

Para buscar una carga en la lista, use el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar el nombre de la carga.

Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) para filtrar las cargas por uno o de los siguientes valores:

- **Complejidad**: **Alta**, **Media** y **Baja**.
- **Language**
- **Agregar etiquetas**
- **Theme**
- **Marca**
- **Industria**
- **Evento actual**: **Sí** o **No**.
- **Polémico**: **Sí** o **No**.

Para quitar una o varias columnas que se muestran, haga clic en ![el icono Personalizar columnas.](../../media/m365-cc-sc-customize-icon.png) **Personalizar columnas**. De forma predeterminada, la única columna que no se muestra es **Plataforma** y ese valor es actualmente siempre **Correo electrónico**.

Al seleccionar una carga de la lista, aparece un control flotante de detalles con la siguiente información:

- **Pestaña Información general** : vea la carga útil como la verán los usuarios. Las propiedades de carga también están visibles:
  - **Descripción de la carga**
  - **Nombre De**
  - **Desde el correo electrónico**
  - **Asunto del correo electrónico**
  - **Origen**: en el caso de las cargas integradas, el valor es **Global**. En el caso de las cargas personalizadas, el valor es **Tenant**.
  - **Theme**
  - **Marca**
  - **Industria**
  - **Polémico**
  - **Evento actual**
  - **Tags**

- **Pestaña Simulaciones iniciadas** :
  - **Nombre de la simulación**
  - **Tasa de clics**
  - **Tasa en peligro**
  - **Action**

## <a name="create-payloads"></a>Creación de cargas útiles

> [!NOTE]
> Ciertas marcas comerciales, logotipos, símbolos, insignias y otros identificadores de origen reciben una protección mayor en virtud de leyes y leyes locales, estatales y federales. El uso no autorizado de dichos indicadores puede someter a los usuarios a sanciones, incluidas las multas penales. Aunque no es una lista extensa, esto incluye los sellos presidencial, vicepresidencial y del Congreso, la CIA, el FBI, el Seguro Social, Medicare y Medicaid, el Servicio de Ingresos Internos de Estados Unidos y los Juegos Olímpicos. Más allá de estas categorías de marcas comerciales, el uso y la modificación de cualquier marca comercial de terceros conlleva una cantidad inherente de riesgo. El uso de sus propias marcas comerciales y logotipos en una carga sería menos arriesgado, especialmente cuando su organización permite el uso. Si tiene más preguntas sobre lo que es o no es adecuado usar al crear o configurar una carga, debe consultar con sus asesores legales.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** pestaña \> Biblioteca de contenido de **simulación de entrenamiento** \> de **simulación de simulación** de colaboración \> **. Pestaña Cargas útiles** \> De **inquilino** pestaña. Para ir directamente a la pestaña **Biblioteca de contenido de simulación**, donde puede seleccionar **Cargas útiles** y la pestaña **Cargas de inquilino**, use <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

   Haga clic en ![el icono Crear una carga.](../../media/m365-cc-sc-create-icon.png) **Cree una carga** en la pestaña **Cargas de inquilino en** **Cargas** para iniciar el Asistente para crear carga.

   ![Cree una carga en la pestaña Cargas de inquilino en Cargas en el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender.](../../media/attack-sim-training-payload-create.png)

   > [!NOTE]
   > ![Cree un icono de carga.](../../media/m365-cc-sc-create-icon.png) **La creación de una carga** también está disponible en la página **Seleccionar carga** del Asistente para la creación de simulación. Para obtener más información, vea [Simular un ataque de suplantación de identidad (phishing) en Defender para Office 365](attack-simulation-training.md).
   >
   > En cualquier momento durante el asistente para la creación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y seguir configurando la carga más adelante. Para seleccionar dónde lo dejó, seleccione la notificación en la pestaña **Cargas de inquilino en** **Cargas útiles** y, a continuación, haga clic en ![el icono Editar carga útil.](../../media/m365-cc-sc-edit-icon.png) **Edite la carga útil**. La carga parcialmente completada tendrá el valor **Estado** **Borrador**.

2. En la página **Seleccionar tipo** , el único valor que puede seleccionar actualmente es **Correo electrónico**.

   Haga clic en **Siguiente**.

3. En la página **Seleccionar técnica** , las opciones disponibles son las mismas que en la página **Seleccionar técnica** del Asistente para la creación de simulación:

   - **Cosecha de credenciales**
   - **Datos adjuntos de malware**
   - **Vínculo en datos adjuntos**
   - **Vínculo a malware**
   - **Dirección URL de unidad por**

   Para obtener más información, consulte [Simulación de un ataque de suplantación de identidad con entrenamiento de simulación de ataques en Defender para Office 365](attack-simulation-training.md).

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Nombre de carga** , configure los siguientes valores:

   - **Nombre**: escriba un nombre descriptivo único para la carga.
   - **Descripción**: escriba una descripción detallada opcional para la carga.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Configurar carga,** es el momento de compilar la carga. Muchos de los valores disponibles están determinados por la selección realizada en la página **Seleccionar técnica** (por ejemplo, vínculos frente a datos adjuntos).

   - **Sección detalles del remitente** : Configure las siguientes opciones:
     - **Nombre De**
     - **Use el nombre como nombre para mostrar**: de forma predeterminada, esta configuración no está seleccionada.
     - **Desde el correo electrónico**: si elige una dirección de correo electrónico interna para el remitente de la carga, parecerá que la carga procederá de un compañero empleado. Esta dirección de correo electrónico del remitente aumentará la susceptibilidad de un usuario a la carga útil y ayudará a educar a los empleados sobre el riesgo de amenazas internas.
     - **Asunto del correo electrónico**

   - **Sección detalles de datos adjuntos** : esta sección solo está disponible si seleccionó **Datos adjuntos de malware**, **Vínculo a datos adjuntos** o **Vínculo a malware** en la página **Seleccionar técnica** . Configure las siguientes opciones:
     - **Asignar un nombre a los datos adjuntos**
     - **Seleccionar un tipo de datos adjuntos**: actualmente, el único valor disponible es **Docx**.

   - **Sección Vínculo para datos adjuntos** : esta sección solo está disponible si seleccionó **Vincular a malware** en la página **Seleccionar técnica** . En el cuadro **Seleccionar una dirección URL que quiera que sea el vínculo de datos adjuntos de malware** , seleccione una de las direcciones URL disponibles (las mismas direcciones URL que se describen para la sección **Vínculo de suplantación de identidad** ).

     Más adelante, insertará la dirección URL en el cuerpo del mensaje.

   - Sección **de vínculo de phishing**: esta sección solo está disponible si seleccionó **Cosecha de credenciales**, **Vínculo en datos adjuntos** o **Dirección URL de unidad por** en la página **Seleccionar técnica**.

     Para **la recopilación de credenciales** o la **dirección URL de unidad por**, el nombre del cuadro es **Seleccionar una dirección URL que quiera que sea el vínculo de suplantación de identidad**. Más adelante, insertará la dirección URL en el cuerpo del mensaje.

     En **Vínculo en datos adjuntos**, el nombre del cuadro es **Seleccionar una dirección URL en este archivo adjunto que desea que sea el vínculo de suplantación de identidad**. Más adelante, insertará la dirección URL en los datos adjuntos.

     Seleccione uno de los valores de dirección URL disponibles:
  
     - <https://www.mcsharepoint.com>
     - <https://www.attemplate.com>
     - <https://www.doctricant.com>
     - <https://www.mesharepoint.com>
     - <https://www.officence.com>
     - <https://www.officenced.com>
     - <https://www.officences.com>
     - <https://www.officentry.com>
     - <https://www.officested.com>
     - <https://www.prizegives.com>
     - <https://www.prizemons.com>
     - <https://www.prizewel.com>
     - <https://www.prizewings.com>
     - <https://www.shareholds.com>
     - <https://www.sharepointen.com>
     - <https://www.sharepointin.com>
     - <https://www.sharepointle.com>
     - <https://www.sharesbyte.com>
     - <https://www.sharession.com>
     - <https://www.sharestion.com>
     - <https://www.templateau.com>
     - <https://www.templatent.com>
     - <https://www.templatern.com>
     - <https://www.windocyte.com>

     > [!NOTE]
     > Un servicio de reputación de direcciones URL podría identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web admitidos antes de usar la dirección URL en una simulación. Para obtener más información, consulte [Direcciones URL de simulación de suplantación de identidad bloqueadas por Google Safe Browsing](attack-simulation-training-faq.md#phishing-simulation-urls-blocked-by-google-safe-browsing).

   - **Sección Contenido de datos adjuntos** : esta sección solo está disponible si seleccionó **Vincular en datos adjuntos** en la página **Seleccionar técnica** .

     Hay disponible un editor de texto enriquecido para crear el contenido en la carga de datos adjuntos del archivo.

     Use el control **de vínculo phishing** para agregar la dirección URL de suplantación de identidad seleccionada anteriormente a los datos adjuntos.

   - Configuración común en la página **Configurar carga:**

     - **Agregar etiquetas**
  
     - **Tema**: Los valores disponibles son: **Activación de la cuenta**, **Verificación de cuenta**, **Facturación**, **Limpiar correo**, **Documento recibido**, **Gastos**, **Fax**, **Informe financiero**, **Mensajes entrantes**, **Factura**, **Elemento recibido**, **Alerta de inicio de sesión**, **Correo recibido**, **Otro**, **Contraseña**, **Pago**, **Nómina**, **Oferta personalizada**, **Cuarentena** , **Trabajo remoto**, **Mensaje de revisión**, **Actualización de seguridad**, **Servicio suspendido**, **Firma requerida**, **Actualizar almacenamiento del buzón**, **Comprobar buzón** o **Correo de voz**.
  
     - **Marca**: Los valores disponibles son: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** u **otros**.
  
     - **Industria**: Los valores disponibles son: **Banca**, **Servicios empresariales**, **Servicios de consumo**, **Educación**, **Energía**, **Construcción**, **Consultoría**, **Servicios financieros**, **Gobierno**, **Hostelería**, **Seguros**, **Servicios legales**, **De mensajería**, **TI**, **Atención sanitaria**, **Fabricación**, **Minorista**, **Telecomunicaciones**, **Bienes Raíces**, o **Otro**.

     - **Evento actual**: los valores disponibles son **Sí** o **No**.

     - **Controversial**: los valores disponibles son **Sí** o **No**.

   - **Sección idioma** : seleccione el idioma de la carga. Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** u **otro**.

   - **Sección de mensaje de correo electrónico** :

     - Puede hacer clic en **Importar correo electrónico** y, a continuación, **elegir archivo** para importar un archivo de mensaje de texto sin formato existente.

     - En la pestaña **Texto** , hay disponible un editor de texto enriquecido para crear la carga del mensaje de correo electrónico.

       - Use el control **Etiqueta dinámica** para personalizar el mensaje de correo electrónico de cada usuario insertando las etiquetas disponibles:
         - **Insertar nombre de usuario**: el valor que se agrega en el cuerpo del mensaje es `${userName}`.
         - **Insertar nombre**: el valor que se agrega en el cuerpo del mensaje es `${firstName}`.
         - **Insertar apellido**: el valor que se agrega en el cuerpo del mensaje es `${lastName}`.
         - **Insertar UPN**: el valor que se agrega en el cuerpo del mensaje es `${upn}`.
         - **Insertar correo electrónico**: el valor que se agrega en el cuerpo del mensaje es `${emailAddress}`.
         - **Insertar departamento**: el valor que se agrega en el cuerpo del mensaje es `${department}`.
         - **Administrador de inserción**: el valor que se agrega en el cuerpo del mensaje es `${manager}`.
         - **Insertar teléfono móvil**: el valor que se agrega en el cuerpo del mensaje es `${mobilePhone}`.
         - **Insertar ciudad**: el valor que se agrega en el cuerpo del mensaje es `${city}`.
         - **Insertar fecha**: el valor que se agrega en el cuerpo del mensaje es `${date|MM/dd/yyyy|offset}`.

         :::image type="content" source="../../media/attack-sim-training-payloads-configure-payload-email-message.png" alt-text="La sección Mensaje de correo electrónico de la página Configurar carga útil del Asistente para la creación de carga en Entrenamiento de simulación de ataques en Microsoft Defender para Office 365" lightbox="../../media/attack-sim-training-payloads-configure-payload-email-message.png":::

       - **Control de vínculo de suplantación de identidad** : este control solo está disponible si seleccionó **Recopilación de credenciales**, **Vínculo en datos adjuntos** o **Dirección URL de unidad por** en la página **Seleccionar técnica** . Use este control para asignar un nombre e insertar la dirección URL que seleccionó anteriormente en la sección **Vínculo de phishing** .

       - **Control de vínculo de datos adjuntos de malware** : este control solo está disponible si seleccionó **Vincular a malware** en la página **Seleccionar técnica** . Use este control para asignar un nombre e insertar la dirección URL que seleccionó anteriormente en la sección **Vínculo para datos adjuntos** .

       Al hacer clic en **vínculo phishing** o **vínculo de datos adjuntos de malware**, se abre un cuadro de diálogo que le pide que asigne un nombre al vínculo. Cuando haya terminado, haga clic en **Confirmar**.

       El valor que se agrega en el cuerpo del mensaje (visible en la pestaña **Código** ) es `<a href="${phishingUrl}" target="_blank">Name value you specified</a>`.

     - En la pestaña **Código** , puede ver y modificar el código HTML directamente. El formato y otros controles como **la etiqueta dinámica** y el **vínculo phishing** o **el vínculo de datos adjuntos de malware** no están disponibles.

     - El botón **Reemplazar todos los vínculos del mensaje de correo electrónico con el botón** de alternancia de vínculo de suplantación de identidad solo está disponible si seleccionó **Cosecha de credenciales**, **Vínculo a malware** o **Dirección URL de unidad por** en la página **Seleccionar técnica** . Este botón de alternancia puede ahorrar tiempo reemplazando todos los vínculos del mensaje por el **vínculo phishing** seleccionado anteriormente o vínculo para la dirección URL **de datos adjuntos** . Para ello, cambie la configuración a En el ![icono Alternar en .](../../media/scc-toggle-on.png)

   Cuando termine, haga clic en **Siguiente**.

6. La página **Agregar indicadores** solo está disponible si seleccionó **Cosecha de credenciales**, **Vínculo en datos adjuntos** o **Dirección URL de unidad por** en la página **Seleccionar técnica** .

   Los indicadores ayudan a los empleados a identificar los signos de los mensajes de phishing.

   En la página **Agregar indicadores** , haga clic en **Agregar indicador**. En el control flotante que aparece, configure los siguientes valores:

   - **Seleccione e indicador que desea usar** y **¿Dónde desea colocar este indicador en la carga útil?**:

     Estos valores están interrelacionados. Donde se puede colocar el indicador depende del tipo de indicador. Los valores disponibles se describen en la tabla siguiente:

     |Tipo de indicador|Ubicación del indicador|
     |---|---|
     |**Tipo de datos adjuntos**|Cuerpo del mensaje|
     |**Detalles que distraen**|Cuerpo del mensaje|
     |**Suplantación de dominio**|Cuerpo del mensaje <p> Desde la dirección de correo electrónico|
     |**Saludo genérico**|Cuerpo del mensaje|
     |**Llamamientos humanitarios**|Cuerpo del mensaje|
     |**Inconsistencia**|Cuerpo del mensaje|
     |**Falta de detalles del remitente**|Cuerpo del mensaje|
     |**Lenguaje legal**|Cuerpo del mensaje|
     |**Oferta por tiempo limitado**|Cuerpo del mensaje|
     |**Imitación de logotipos o personalización de marca con fecha**|Cuerpo del mensaje|
     |**Imita un proceso profesional o empresarial**|Cuerpo del mensaje|
     |**Personalización de marca mínima o nula**|Cuerpo del mensaje|
     |**Se hace pasar por amigo, compañero, supervisor o figura de autoridad**|Cuerpo del mensaje|
     |**Solicitud de información confidencial**|Cuerpo del mensaje|
     |**Indicadores e iconos de seguridad**|Cuerpo del mensaje <p> Asunto de mensaje|
     |**Nombre para mostrar del remitente y dirección de correo electrónico**|Nombre De <p> Desde la dirección de correo electrónico|
     |**Sentido de urgencia**|Cuerpo del mensaje <p> Asunto de mensaje|
     |**Errores ortográficos y gramaticales**|Cuerpo del mensaje <p> Asunto de mensaje|
     |**Lenguaje amenazante**|Cuerpo del mensaje <p> Asunto de mensaje|
     |**Demasiado bueno para ser verdaderas ofertas**|Cuerpo del mensaje|
     |**Diseño o formato de aspecto no profesional**|Cuerpo del mensaje|
     |**Hipervínculo de dirección URL**|Cuerpo del mensaje|
     |**Eres especial.**|Cuerpo del mensaje|
  
     Esta lista está seleccionada para contener las pistas más comunes que aparecen en los mensajes de phishing.

     Si selecciona el asunto del mensaje de correo electrónico o el cuerpo del mensaje como la ubicación del indicador, aparece un botón **Seleccionar texto** . Haga clic en este botón para seleccionar el texto del asunto del mensaje o el cuerpo del mensaje donde desea que aparezca el indicador. Cuando haya terminado, haga clic en **Seleccionar**.

     :::image type="content" source="../../media/attack-sim-training-payloads-add-indicators-select-location.png" alt-text="Ubicación de texto seleccionada en el cuerpo del mensaje que se va a agregar a un indicador en el Asistente para la creación de cargas en el entrenamiento de simulación de ataques" lightbox="../../media/attack-sim-training-payloads-add-indicators-select-location.png":::

     - **Descripción del indicador**: puede aceptar la descripción predeterminada del indicador o puede personalizarlo.

     - **Vista previa del indicador**: para ver el aspecto del indicador actual, haga clic en cualquier parte de la sección.

     Cuando haya terminado, haga clic en **Agregar.**

   Repita estos pasos para agregar varios indicadores.

   De nuevo en la página **Agregar indicadores** , puede revisar los indicadores seleccionados:

   - Para editar un indicador existente, selecciónelo en la lista y, a continuación, haga clic en ![el icono Editar indicador.](../../media/m365-cc-sc-edit-icon.png) **Editar indicador**.

   - Para eliminar un indicador existente, selecciónelo de la lista y haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Delete**.

   - Para mover los indicadores hacia arriba o hacia abajo en la lista, seleccione el indicador de la lista y, a continuación, haga clic en ![el icono Subir.](../../media/m365-cc-sc-increase-icon.png) **Icono Subir** o ![Bajar.](../../media/m365-cc-sc-decrease-icon.png) **Muévete hacia abajo**.

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar carga,** puede revisar los detalles de la carga.

   Haga clic en el ![icono Enviar una prueba.](../../media/m365-cc-sc-send-icon.png) **Enviar un botón de prueba** para enviar una copia del correo electrónico de carga a usted mismo (el usuario que ha iniciado sesión actualmente) para su inspección.

   Haga clic en el ![icono De vista previa del indicador.](../../media/m365-cc-sc-open-icon.png) **El botón Del indicador de vista previa** abre la carga en un control flotante de vista previa. La vista previa incluye todos los indicadores de carga que ha creado.

   En la página principal **Revisar carga útil** , puede seleccionar **Editar** en cada sección para modificar la configuración de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**. En la página de confirmación que aparece, haga clic en **Listo**.

   :::image type="content" source="../../media/attack-sim-training-payloads-review-payload.png" alt-text="La página Revisar carga útil del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-payloads-review-payload.png":::

## <a name="modify-payloads"></a>Modificación de cargas

No se pueden modificar las cargas integradas en la pestaña **Cargas globales** . Solo puede modificar cargas personalizadas en la pestaña **Cargas de inquilino** .

Para modificar una carga existente en la pestaña **Cargas de inquilino** , realice uno de los pasos siguientes:

- Seleccione la carga de la lista haciendo clic en la casilla. Haga clic en el ![icono Editar carga.](../../media/m365-cc-sc-edit-icon.png) **Icono de edición de carga que** aparece.
- Seleccione la carga de la lista haciendo clic en cualquier lugar de la fila excepto en la casilla. En el control flotante de detalles que se abre, haga clic en **Editar carga.**

El asistente para carga se abre con la configuración y los valores de la carga seleccionada. Los pasos son los mismos que se describen en la sección [Crear cargas](#create-payloads) .

## <a name="copy-payloads"></a>Copiar cargas útiles

Para copiar una carga existente en las pestañas **Cargas de inquilino** o **Cargas globales** , seleccione la carga de la lista haciendo clic en la casilla y, a continuación, haga clic en el ![icono Copiar carga útil.](../../media/m365-cc-sc-edit-icon.png) **Icono de carga útil de copia** que aparece.

El asistente para crear carga se abre con la configuración y los valores de la carga seleccionada. Los pasos son los mismos que se describen en la sección [Crear cargas](#create-payloads) .

> [!NOTE]
> Al copiar una carga integrada en la pestaña **Cargas globales** , asegúrese de cambiar el valor **Nombre** . Si no lo hace, la carga aparecerá en la página **Cargas de inquilino** con el mismo nombre que la carga integrada.

## <a name="send-a-test"></a>Envío de una prueba

En las pestañas **Cargas de inquilino** o **Cargas globales** , puede enviar una copia del correo electrónico de carga a usted mismo (el usuario que ha iniciado sesión actualmente) para su inspección.

Seleccione la carga de la lista haciendo clic en la casilla y, a continuación, haga clic en el ![icono Enviar una prueba.](../../media/m365-cc-sc-send-icon.png) **Enviar un botón de prueba** que aparece.

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Creación de una simulación de ataque de suplantación de identidad (phishing)](attack-simulation-training.md)

[Obtenga información a través de la formación de simulación de ataques](attack-simulation-training-insights.md)
