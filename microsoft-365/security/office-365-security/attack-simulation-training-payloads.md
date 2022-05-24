---
title: Crear una carga personalizada para el aprendizaje la simulación de ataques
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
description: Los administradores pueden aprender a crear cargas personalizadas para el entrenamiento de simulación de ataques en Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.openlocfilehash: f0f91eb3936d1dc4ed6c028552b37fecb5df2ff6
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648313"
---
# <a name="create-custom-payloads-for-attack-simulation-training-in-defender-for-office-365"></a>Creación de cargas personalizadas para el entrenamiento de simulación de ataques en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En El entrenamiento de simulación de ataques, una _carga útil_ es el mensaje de correo electrónico de suplantación de identidad (phishing) y las páginas web que se presentan a los usuarios en simulaciones. El entrenamiento de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 ofrece un sólido catálogo de cargas integradas para las técnicas de ingeniería social disponibles. Sin embargo, es posible que quiera crear cargas personalizadas que funcionen mejor para su organización.

En este artículo se describe cómo crear sus propias cargas en el entrenamiento de simulación de ataques. Puede crear cargas personalizadas en las siguientes ubicaciones:

- La pestaña **Cargas:** en el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a **Correo electrónico &** pestaña **Cargas útiles** de entrenamiento \> de **simulación de ataques** de colaboración\>. Para ir directamente a la pestaña **Cargas,** use <https://security.microsoft.com/attacksimulator?viewid=payload>.
- Durante la creación de la simulación: puede crear cargas personalizadas en la página **Seleccionar una carga (** la tercera página) del Asistente para la creación de simulación. Para obtener más información, vea [Simular un ataque de suplantación de identidad (phishing) en Defender para Office 365](attack-simulation-training.md).

Para obtener información de introducción sobre el entrenamiento de simulación de ataques, consulte [Comenzar uso del entrenamiento de simulación de ataques](attack-simulation-training-get-started.md).

> [!NOTE]
> Ciertas marcas comerciales, logotipos, símbolos, insignias y otros identificadores de origen reciben una protección mayor en virtud de leyes y leyes locales, estatales y federales. El uso no autorizado de dichos indicadores puede someter a los usuarios a sanciones, incluidas las multas penales. Aunque no es una lista extensa, esto incluye los sellos presidencial, vicepresidencial y del Congreso, la CIA, el FBI, el Seguro Social, Medicare y Medicaid, el Servicio de Ingresos Internos de Estados Unidos y los Juegos Olímpicos. Más allá de estas categorías de marcas comerciales, el uso y la modificación de cualquier marca comercial de terceros conlleva una cantidad inherente de riesgo. El uso de sus propias marcas comerciales y logotipos en una carga sería menos arriesgado, especialmente cuando su organización permite el uso. Si tiene más preguntas sobre lo que es o no es adecuado usar al crear o configurar una carga, debe consultar con sus asesores legales.

## <a name="create-a-payload"></a>Creación de una carga

Después de hacer clic en ![Crear un icono de carga.](../../media/m365-cc-sc-create-icon.png) **Cree una carga desde** la pestaña **Cargas** del entrenamiento de simulación de ataques o, en la página **[Seleccionar una carga](attack-simulation-training.md#select-a-payload)** del Asistente para la creación de simulación, se inicia el asistente para la creación de cargas y se describe en esta sección.

### <a name="select-a-payload-type"></a>Selección de un tipo de carga

En la página **Seleccionar tipo** , el único valor que puede seleccionar actualmente es **Correo electrónico**.

Haga clic en **Siguiente**.

### <a name="select-a-social-engineering-technique"></a>Selección de una técnica de ingeniería social

En la página **Seleccionar técnica** , las opciones disponibles son las mismas que en la página [Seleccionar técnica](attack-simulation-training.md#select-a-social-engineering-technique) del Asistente para la creación de simulación:

- **Cosecha de credenciales**
- **Datos adjuntos de malware**
- **Vínculo en datos adjuntos**
- **Vínculo a malware**
- **Dirección URL de unidad por**

Cuando termine, haga clic en **Siguiente**.

### <a name="name-and-describe-the-payload"></a>Asigne un nombre y describa la carga.

En la página **Nombre de carga** , configure los siguientes valores:

- **Nombre**: escriba un nombre descriptivo único para la carga.
- **Descripción**: escriba una descripción detallada opcional para la carga.

Cuando termine, haga clic en **Siguiente**.

## <a name="configure-the-payload"></a>Configuración de la carga

En la página **Configurar carga,** es el momento de compilar la carga. Muchos de los valores disponibles están determinados por la selección realizada en la página **Seleccionar técnica** (por ejemplo, vínculos frente a datos adjuntos).

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
  > Un servicio de reputación de direcciones URL podría identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web admitidos antes de usar la dirección URL en una simulación. Para obtener más información, consulte [Direcciones URL de simulación de suplantación de identidad bloqueadas por Google Caja fuerte Exploración](attack-simulation-training-faq.md#phishing-simulation-urls-blocked-by-google-safe-browsing).

- **Sección Contenido de datos adjuntos** : esta sección solo está disponible si seleccionó **Vincular en datos adjuntos** en la página **Seleccionar técnica** .

  Hay disponible un editor de texto enriquecido para crear el contenido en la carga de datos adjuntos del archivo.

  Use el control **de vínculo phishing** para agregar la dirección URL de suplantación de identidad seleccionada anteriormente a los datos adjuntos.

- Configuración común:
  - **Agregar etiquetas**
  - **Tema**: Los valores disponibles son: **Activación de la cuenta**, **Verificación de cuenta**, **Facturación**, **Limpiar correo**, **Documento recibido**, **Gastos**, **Fax**, **Informe financiero**, **Mensajes entrantes**, **Factura**, **Elemento recibido**, **Alerta de inicio de sesión**, **Correo recibido**, **Otro**, **Contraseña**, **Pago**, **Nómina**, **Oferta personalizada**, **Cuarentena** , **Trabajo remoto**, **Revisar mensaje**, **Actualización de seguridad**, **Servicio suspendido**, **Firma requerida**, **Actualizar buzón Storage**, **Comprobar buzón** o **Correo de voz**.
  - **Marca**: Los valores disponibles son: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** u **otros**.
  - **Industria**: Los valores disponibles son: **Banca**, **Servicios empresariales**, **Servicios de consumo**, **Educación**, **Energía**, **Construcción**, **Consultoría**, **Servicios financieros**, **Gobierno**, **Hostelería**, **Seguros**, **Servicios legales**, **De mensajería**, **TI**, **Atención sanitaria**, **Fabricación**, **Minorista**, **Telecomunicaciones**, **Bienes Raíces**, o **Otro**.
  - **Evento actual**: los valores disponibles son **Sí** o **No**.
  - **Controversial**: los valores disponibles son **Sí** o **No**.

- **Sección idioma** : seleccione el idioma de la carga. Los valores disponibles son: **inglés**, **español**, **alemán**, **japonés**, **francés**, **portugués**, **holandés**, **italiano**, **sueco**, **chino (simplificado),** **noruego Bokmål**, **polaco**, **ruso**, **finés**, **coreano**, **turco**, **húngaro**, **hebreo**, **tailandés**, **árabe**, **vietnamita**, **eslovaco**, **griego**, **indonesio**, **rumano**, **esloveno**, **croata**, **catalán** u **otro**.

- **Sección de mensaje de correo electrónico** :

  - Puede hacer clic en **Importar correo electrónico** y, a continuación, **elegir archivo** para importar un archivo de mensaje de texto sin formato existente.

  - En la pestaña **Texto** , hay disponible un editor de texto enriquecido para crear la carga del mensaje de correo electrónico.

    - Use el control **Etiqueta dinámica** para personalizar el mensaje de correo electrónico de cada usuario insertando las etiquetas disponibles:
      - **Insertar nombre**: el valor que se agrega en el cuerpo del mensaje es `${userName}`.
      - **Insertar correo electrónico**: el valor que se agrega en el cuerpo del mensaje es `${emailAddress}`.

      :::image type="content" source="../../media/attack-sim-training-payloads-configure-payload-email-message.png" alt-text="La sección Mensaje de correo electrónico de la página Configurar carga útil del Asistente para la creación de carga en Entrenamiento de simulación de ataques en Microsoft Defender para Office 365" lightbox="../../media/attack-sim-training-payloads-configure-payload-email-message.png":::

      **Control de vínculo de suplantación de identidad** : este control solo está disponible si seleccionó **Recopilación de credenciales**, **Vínculo en datos adjuntos** o **Dirección URL de unidad por** en la página **Seleccionar técnica** . Use este control para insertar la dirección URL que seleccionó anteriormente en la sección **Vínculo de phishing** .

      **Control de vínculo de datos adjuntos de malware** : este control solo está disponible si seleccionó **Vincular a malware** en la página **Seleccionar técnica** . Use este control para insertar la dirección URL que seleccionó anteriormente en la sección **Vínculo para datos adjuntos** .

      Si hace clic en **vínculo phishing** o **vínculo de datos adjuntos de malware**, se abre un cuadro de diálogo que le pide que asigne un nombre al vínculo. Cuando haya terminado, haga clic en **Confirmar**.

      El valor que se agrega en el cuerpo del mensaje (visible en la pestaña **Código** ) es `<a href="${phishingUrl}" target="_blank">Name value you specified</a>`.

  - En la pestaña **Código** , puede ver y modificar el código HTML directamente. El formato y otros controles como **la etiqueta dinámica** y el **vínculo phishing** o **el vínculo de datos adjuntos de malware** no están disponibles.

  - El botón **Reemplazar todos los vínculos del mensaje de correo electrónico con el botón** de alternancia de vínculo de suplantación de identidad solo está disponible si seleccionó **Cosecha de credenciales**, **Vínculo a malware** o **Dirección URL de unidad por** en la página **Seleccionar técnica** . Este botón de alternancia puede ahorrar tiempo reemplazando todos los vínculos del mensaje por el **vínculo phishing** seleccionado anteriormente o vínculo para la dirección URL **de datos adjuntos** . Para ello, cambie la configuración a En el ![icono Alternar en .](../../media/scc-toggle-on.png)

Cuando termine, haga clic en **Siguiente**.

## <a name="add-indicators-to-phishing-clues"></a>Adición de indicadores a pistas de suplantación de identidad

> [!NOTE]
> Los indicadores no están disponibles si seleccionó **Datos adjuntos de malware** o **Vincular a malware** en la página **Seleccionar técnica** .

Los indicadores ayudan a los empleados a pasar por la simulación de ataques para identificar los signos de cuenta de los mensajes de suplantación de identidad (phishing).

En la página **Agregar indicadores** , haga clic en **Agregar indicador**. En el control flotante que aparece, configure los siguientes valores:

- **Nombre del indicador** y **ubicación del indicador**: estos valores están interrelacionados. Donde se puede colocar el indicador depende del propio indicador. Los valores disponibles se describen en la tabla siguiente:

  |Nombre del indicador|Ubicación del indicador|
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

  Si selecciona el asunto del mensaje de correo electrónico o el cuerpo del mensaje como ubicación del indicador, está disponible el botón **Seleccionar texto** . Haga clic en este botón para seleccionar el texto del asunto del mensaje o el cuerpo del mensaje donde desea que aparezca el indicador. Cuando haya terminado, haga clic en **Seleccionar**.

  :::image type="content" source="../../media/attack-sim-training-payloads-add-indicators-select-location.png" alt-text="Ubicación de texto seleccionada en el cuerpo del mensaje que se va a agregar a un indicador en el Asistente para la creación de cargas en el entrenamiento de simulación de ataques" lightbox="../../media/attack-sim-training-payloads-add-indicators-select-location.png":::

  - **Descripción del indicador**: puede aceptar la descripción predeterminada del indicador o personalizarlo.

  - **Vista previa del indicador**: para ver el aspecto del indicador actual, haga clic en esta sección.

  Cuando haya terminado, haga clic en **Agregar.**

Repita los pasos de esta sección para agregar varios indicadores.

Para editar un indicador existente, selecciónelo en la lista y, a continuación, haga clic en ![el icono Editar indicador.](../../media/m365-cc-sc-edit-icon.png) **Edite la carga útil**.

Para eliminar un indicador existente, selecciónelo de la lista y haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Delete**.

Cuando termine, haga clic en **Siguiente**.

## <a name="review-payload"></a>Revisión de la carga útil

En la página **Revisar carga,** puede revisar los detalles de la carga.

Haga clic en el ![icono Enviar una prueba.](../../media/m365-cc-sc-send-icon.png) **Enviar un botón de prueba** para enviar una copia del correo electrónico de carga a usted mismo (el usuario que ha iniciado sesión actualmente) para su inspección.

Haga clic en el ![icono De vista previa del indicador.](../../media/m365-cc-sc-open-icon.png) **El botón Del indicador de vista previa** abre la carga en un control flotante de vista previa. La vista previa incluye todos los indicadores de carga que ha creado.

En la página principal **Revisar carga útil** , puede seleccionar **Editar** en cada sección para modificar la configuración de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**. En la página de confirmación que aparece, haga clic en **Listo**.

:::image type="content" source="../../media/attack-sim-training-payloads-review-payload.png" alt-text="La página Revisar carga útil del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-payloads-review-payload.png":::

> [!IMPORTANT]
> Las cargas que ha creado tendrán el valor **Tenant** para la propiedad **Source** . Al crear simulaciones y seleccionar cargas, asegúrese de que no filtra el valor **De origen** **Inquilino**.

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Creación de una simulación de ataque de suplantación de identidad (phishing)](attack-simulation-training.md)

[Obtenga información a través de la formación de simulación de ataques](attack-simulation-training-insights.md)
