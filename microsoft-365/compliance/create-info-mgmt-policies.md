---
title: Crear y aplicar directivas de administración de información
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar una directiva de administración de la información para controlar cuánto tiempo se mantiene la información y realizar un seguimiento de quién usa la información.
ms.openlocfilehash: d62eea4c43e6c171bf8c640e341933e81a23e0d0
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67678919"
---
# <a name="create-and-apply-information-management-policies"></a>Crear y aplicar directivas de administración de información

Las directivas de administración de la información permiten a su organización controlar cuánto tiempo se conserva el contenido, auditar lo que hacen los usuarios con el contenido y agregar códigos de barras o etiquetas a los documentos. Una directiva puede ayudar a aplicar el cumplimiento con las regulaciones legales y gubernamentales o los procesos empresariales internos. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de los documentos y cuánto tiempo conservarlos.

Puede crear una directiva de administración de información en tres ubicaciones diferentes de la jerarquía del sitio, desde la más amplia hasta la más estrecha:

- Cree una directiva para usarla en varios tipos de contenido dentro de una colección de sitios.
- Cree una directiva para un tipo de contenido de sitio.
- Cree una directiva para una lista o biblioteca.

Para obtener más información, consulte [Introducción a las directivas de administración de la información](intro-to-info-mgmt-policies.md).

## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Creación de una directiva para varios tipos de contenido dentro de una colección de sitios
<a name="__toc261001590"> </a>

Para asegurarse de que se aplica una directiva de información a todos los documentos de un tipo determinado dentro de una colección de sitios, considere la posibilidad de crear la directiva en el nivel de colección de sitios y, a continuación, aplicar la directiva a los tipos de contenido. Estas se conocen como directivas de colección de sitios.

1. En la página \> principal de la colección de sitios **, botón Configuración**![de SharePoint 2016 en la barra de título.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configuración del sitio**.

    En un sitio conectado a un grupo de SharePoint, haga clic en **Configuración**, en **Contenido del sitioy**, a continuación, en **Configuración del sitio**.

2. En la página Configuración del sitio, en Plantillas de directiva de tipo de contenido **de administración** \> de **colecciones de sitios**.

   ![Vínculo a la plantilla de directiva de tipo de contenido en la página Configuración del sitio.](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. En la página \> Directivas **, cree**.

4. Escriba un nombre y una descripción para la directiva y, a continuación, escriba una breve instrucción de directiva que explique a los usuarios para qué sirve la directiva.

5. Consulte la sección siguiente sobre la creación de directivas para un tipo de contenido de sitio para obtener información sobre cómo configurar las características que desea asociar a la directiva.

6. Elija **Aceptar**.

## <a name="create-a-policy-for-a-site-content-type"></a>Creación de una directiva para un tipo de contenido de sitio
<a name="__create_a_policy"> </a>

Agregar una directiva de administración de información a un tipo de contenido facilita la asociación de características de directiva con varias listas o bibliotecas. Puede elegir agregar una directiva de administración de información existente a un tipo de contenido o crear una directiva única específica para un tipo de contenido individual.

 También puede agregar una directiva de administración de información a un tipo de contenido específico de las listas. Esto tiene el efecto de aplicar la directiva solo a los elementos de esa lista que usan el tipo de contenido.

1. En la página \> principal de la colección de sitios **, botón Configuración**![de SharePoint 2016 en la barra de título.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configuración del sitio**.

    En un sitio conectado a un grupo de SharePoint, haga clic en **Configuración**, en **Contenido del sitioy**, a continuación, en **Configuración del sitio**.

2. En la página Configuración del sitio, en Tipos de **contenido del sitio** **galerías** \> del diseñador web.

   ![Vínculo tipos de contenido de sitio en la página Configuración del sitio.](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)

3. En la página Configuración del tipo de contenido del sitio, seleccione el tipo de contenido al que desea agregar una directiva.

4. En la página Tipo de contenido del sitio, en **Configuración** \> de **la directiva de administración de información**.

5. En la página Editar directiva, escriba un nombre y una descripción para la directiva y, a continuación, escriba una breve descripción que explique a los usuarios para qué sirve la directiva.

6. En las secciones siguientes, seleccione las características de directiva individuales que desea agregar a la directiva de administración de información.

   ![Tipos de directivas de contenido.](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)

7. Para especificar un período de retención para documentos y elementos que están sujetos a esta directiva, elija **Habilitar retención** y, a continuación, especifique el período de retención y las acciones que desea que se produzcan cuando expiren los elementos.

   Para especificar un período de retención:

   1. Elija **Agregar una fase de retención para los registros**.

   2. Seleccione una opción de período de retención para especificar cuándo se establecen los documentos o elementos para expirar. Realice uno de los pasos siguientes:
      - Para establecer la fecha de expiración en función de una propiedad de fecha, en **Evento** \> **Esta fase se basa en una propiedad de fecha en el elemento** y, a continuación, seleccione la acción de documento o elemento (por ejemplo, Creado o Modificado) y el incremento de tiempo después de esta acción (por ejemplo, el número de días, meses o años) cuando desee que expire el elemento.
      - Para usar una fórmula de retención personalizada para determinar la expiración, elija **Establecer por una fórmula de retención personalizada instalada en este servidor**.

        > [!NOTE]
        > Esta opción solo está disponible si el administrador ha configurado una fórmula personalizada.

   3. La opción **Iniciar un flujo de trabajo** solo está disponible si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene un flujo de trabajo asociado. A continuación, se le dará una opción de flujos de trabajo entre los que elegir.

   4. En la sección **Periodicidad** , seleccione **Repetir la acción de esta fase...** y escriba la frecuencia con la que desea que se repita la acción.

      > [!NOTE]
      >  Esta opción solo está disponible si se puede repetir la acción seleccionada. Por ejemplo, no se puede establecer la periodicidad para la acción **Eliminar permanentemente**.

   5. Elija **Aceptar**.

8. Para habilitar la auditoría de los documentos y elementos que están sujetos a esta directiva, elija **Habilitar auditoría** y, a continuación, especifique los eventos que desea auditar.

   Para habilitar la auditoría:

   1. En la página Editar directiva, en **Auditoría** , seleccione **Habilitar auditoría** y, a continuación, active las casillas situadas junto a los eventos para los que desea mantener un seguimiento de auditoría.

   2. Para pedir a los usuarios que inserten estos códigos de barras en documentos, elija **Preguntar a los usuarios que inserten un código de barras antes de guardarlos o imprimirlos**.

   3. Elija **Aceptar** para aplicar la característica de auditoría a la directiva.

   La característica Directiva de auditoría permite a las organizaciones crear y analizar seguimientos de auditoría de documentos y enumerar elementos como listas de tareas, listas de problemas, grupos de discusión y calendarios. Esta característica de directiva proporciona un registro de auditoría que graba eventos, por ejemplo cuando se ve, se modifica o se elimina contenido.

   Cuando la auditoría está habilitada como parte de una directiva de administración de información, los administradores pueden ver los datos de auditoría en los informes de uso de directivas basados en Microsoft Excel y que resumen el uso actual. Los administradores pueden usar estos informes para determinar cómo se usa la información en la organización. Estos informes también pueden ayudar a las organizaciones a comprobar y documentar su cumplimiento normativo o a investigar posibles problemas.

   El registro de auditoría graba la siguiente información: nombre del evento, fecha y hora del evento y nombre de sistema del usuario que realizó la acción.

9. Cuando los códigos de barras se habilitan como parte de una directiva, se agregan a las propiedades del documento y se muestran en el área de encabezado del documento al que se aplica el código de barras. Al igual que las etiquetas, los códigos de barras también se pueden quitar manualmente de un documento. Puede especificar si se debe pedir a los usuarios que incluyan el código de barras al imprimir o guardar un elemento o si el código de barras debe insertarse manualmente mediante la pestaña **Insertar** en los programas de versión de Office 2010.

   Para habilitar códigos de barras:

   1. En la página **Editar directiva** en **Códigos de barras**, seleccione **Habilitar códigos de barras**.

   2. Para pedir a los usuarios que inserten estos códigos de barras en documentos, elija **Preguntar a los usuarios que inserten un código de barras antes de guardarlos o imprimirlos**.

   3. Elija **Aceptar** para aplicar la característica de código de barras a la directiva.

   La directiva de código de barras genera códigos de barras estándar code 39. Cada imagen de código de barras incluye texto debajo del símbolo de código de barras que representa el valor del código de barras. Esto permite usar los datos del código de barras incluso cuando el hardware de escaneo no está disponible. Los usuarios pueden escribir manualmente el número de código de barras en el cuadro de búsqueda para localizar el elemento en un sitio.  <br/> |

10. Para requerir que los documentos que están sujetos a esta directiva tengan etiquetas, elija **Habilitar etiquetas** y, a continuación, especifique la configuración que desea para las etiquetas.

    Para habilitar las etiquetas:

    1. Para exigir a los usuarios que agreguen una etiqueta a un documento, elija **Solicitar a los usuarios que inserten una etiqueta antes de guardarla o imprimirla**.

       > [!NOTE]
       > Si desea que las etiquetas sean opcionales, no active esta casilla. 

    2. Para bloquear una etiqueta para que no se pueda cambiar una vez insertada, elija **Impedir cambios en las etiquetas después de agregarla**.

       Esta configuración impide que el texto de la etiqueta se actualice una vez que la etiqueta se haya insertado en un elemento dentro de una aplicación cliente, como Word, Excel o PowerPoint. Si desea que la etiqueta se actualice cuando se actualicen las propiedades del documento o elemento, no active esta casilla de verificación.

    3. En el cuadro Formato de etiqueta, escriba el texto de la etiqueta como desee que se muestre. Las etiquetas pueden contener hasta 10 referencias de columna, cada una de las cuales puede tener hasta 255 caracteres. Para crear el formato de la etiqueta, siga estos pasos:
       - Escriba los nombres de las columnas que desea incluir en la etiqueta en el orden en que desea que aparezcan. Incluya los nombres de columna entre corchetes ({}), como se muestra en el ejemplo de la página Editar directiva.
       - Escriba palabras para identificar las columnas fuera de los corchetes, como se muestra en el ejemplo de la página Editar directiva.

    4. Para agregar un salto de línea, escriba **\n** donde desea que aparezca el salto de línea.

    5. Seleccione el tamaño de fuente y el estilo que desee y especifique si desea que la etiqueta se coloque a la izquierda, al centro o a la derecha dentro del documento.

       Seleccione una fuente y un estilo que estén disponibles en los equipos de los usuarios. El tamaño de la fuente afecta a la cantidad de texto que puede mostrarse en la etiqueta.

    6. Escriba el alto y el ancho de la etiqueta. El alto de la etiqueta puede variar de 0,25 a 20 pulgadas ((0,63 cm. y 50,8 cm. respectivamente) y el ancho de la etiqueta puede variar de 0,.25 a 20 pulgadas (0,63 cm. y 50,8 cm. respectivamente). El texto de la etiqueta siempre se centra verticalmente en la imagen de la etiqueta.

    7. Elija **Actualizar** para obtener una vista previa del contenido de la etiqueta.

11. Elija **Aceptar**.

## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Crear una directiva para una lista, una biblioteca o una carpeta (directiva de retención basada en ubicación)
<a name="__create_a_policy"> </a>

Puede definir una directiva de retención que se aplique solo a una lista, biblioteca o carpeta específica. Sin embargo, si crea una directiva de retención de esta manera, no puede reutilizar esta directiva en otras listas, bibliotecas, carpetas o sitios y no puede aplicar una directiva de recopilación de sitios a una directiva basada en ubicación.

Si desea aplicar una sola directiva de retención a todos los tipos de contenido en una sola ubicación, lo más probable es que quiera usar la retención basada en ubicación. En la mayoría de los demás casos, querrá comprobar que se especifica una directiva de retención para todos los tipos de contenido.

Cada subcarpeta hereda la directiva de retención de su elemento primario, a menos que decida interrumpir la herencia y definir una nueva directiva de retención en el nivel secundario.

Si desea definir una directiva de administración de información distinta de la retención en una lista o biblioteca, debe definir una directiva de administración de información para cada tipo de contenido de lista individual asociado a esa lista o biblioteca.

Si en algún momento decide cambiar de tipo de contenido a directivas basadas en ubicación para una lista o biblioteca, solo se usará la directiva de retención como directiva basada en ubicación. Todas las demás directivas de administración (auditorías, códigos de barras y códigos de barras) se heredarán de los tipos de contenido asociados.

Las directivas basadas en ubicación se pueden deshabilitar para una colección de sitios desactivando la característica de retención basada en carpetas y bibliotecas. Esto permite a los administradores de colecciones de sitios asegurarse de que las directivas de tipo de contenido no se invalidan mediante las directivas basadas en la ubicación de un administrador de lista.

Necesita al menos el permiso Administrar listas para cambiar la configuración de la directiva de administración de información de una lista o biblioteca.

1. Vaya a la lista o biblioteca para la que desea especificar una directiva de administración de información.

2. En la cinta de opciones, elija la pestaña \> **Biblioteca** o **Lista** **Configuración de biblioteca** o **Configuración de lista**.

   En SharePoint Online, haga clic en **Configuración** y, a continuación, haga clic en **Configuración de lista** o **Configuración de biblioteca**.

3. En **Permisos y administración configuración de** **la directiva de**\> administración de información.

   ![Vínculo directivas de administración de información en la página de configuración de la biblioteca de documentos.](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. En la página Configuración de directivas de administración de información, asegúrese de que el origen de la retención de la lista o biblioteca está establecido en Biblioteca y carpetas.

   Si **tipo de contenido** aparece como origen, haga clic en **Cambiar origeny**, a continuación, haga clic en **Biblioteca y carpetas**. Se le avisa de que se omitirán las directivas de retención de tipos de contenido. Elija **Aceptar**.

5. En la página Editar directiva, en **Programación de retención basada en biblioteca**, escriba una breve descripción de la directiva que va a crear.

6. Elija **Agregar una fase de retención...**

   Tenga en cuenta que, en Registros, puede elegir definir directivas de retención diferentes para los registros seleccionando la opción Definir distintas fases de retención para registros.

7. En el cuadro de diálogo Propiedades de fase, seleccione una opción de período de retención para especificar cuándo se establece la expiración de documentos o elementos. Realiza una de las siguientes acciones:

   - Para establecer la fecha de expiración en función de una propiedad de fecha, en **Evento** \> **Esta fase se basa en una propiedad de fecha en el elemento** y, a continuación, seleccione la acción de documento o elemento (por ejemplo, Creado o Modificado) y el incremento de tiempo después de esta acción (por ejemplo, el número de días, meses o años) cuando desee que expire el elemento.

   - Para usar una fórmula de retención personalizada para determinar la expiración, elija **Establecer por una fórmula de retención personalizada instalada en este servidor**.

     > [!NOTE]
     >  Esta opción solo está disponible si el administrador ha configurado una fórmula personalizada.

   - En **Acción**, especifique lo que quiere que suceda cuando expire el documento o elemento. Para permitir que se produzca una acción específica en el documento o elemento (como la eliminación), seleccione una acción de la lista.

8. La opción **Iniciar un flujo de trabajo** solo está disponible si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene un flujo de trabajo asociado. A continuación, se le dará una opción de flujos de trabajo entre los que elegir.

9. En **Periodicidad**, elija **Repetir la acción de esta fase...** y escriba la frecuencia con la que desea que se repita la acción.

   > [!NOTE]
   >  Esta opción solo está disponible si se puede repetir la acción seleccionada. Por ejemplo, no se puede establecer la periodicidad para la acción **Eliminar permanentemente**.

10. Elija **Aceptar**.

## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Aplicación de una directiva de colección de sitios a un tipo de contenido
<a name="__apply_a_site"> </a>

Si ya se han creado directivas de administración de información para el sitio como directivas de recopilación de sitios, puede aplicar una de las directivas a un tipo de contenido. Al hacerlo, puede aplicar la misma directiva a varios tipos de contenido de una colección de sitios que no comparten el mismo tipo de contenido primario.

 Si desea aplicar directivas a varios tipos de contenido de una colección de sitios y tiene configurado un servicio de metadatos administrados, puede usar la publicación de tipos de contenido para publicar directivas de administración de información en varias colecciones de sitios. Consulte la sección [Aplicar una directiva entre colecciones de sitios](#apply-a-policy-across-site-collections) para obtener más información.

1. Vaya a la lista o biblioteca que contiene el tipo de contenido al que desea aplicar una directiva.

2. En la cinta de opciones, elija la pestaña \> **Biblioteca** o **Lista** **Configuración de biblioteca** o **Configuración de lista**.

   En SharePoint Online, haga clic en **Configuración** y, a continuación, haga clic en **Configuración de lista** o **Configuración de biblioteca**.

3. En **Permisos y administración configuración de** **la directiva de**\> administración de información.

   ![Vínculo directivas de administración de información en la página de configuración de la biblioteca de documentos.](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. Compruebe que el origen de la directiva está establecido en **Tipos de contenido** y, en **Directivas de tipo** de contenido, seleccione el tipo de contenido al que desea aplicar la directiva.

5. En **Especificar la directiva** \> **Use una directiva de colección de sitios** y, a continuación, seleccione la directiva que desea aplicar en la lista.

   > [!NOTE]
   >  Si la opción **Usar una directiva de colección** de sitios no está disponible, no se ha definido ninguna directiva de colección de sitios para la colección de sitios.

6. Elija **Aceptar**.

   Si la lista o biblioteca con la que trabaja admite la administración de varios tipos de contenido, en **Tipos** de contenido puede elegir el tipo de contenido para el que desea especificar una directiva de administración de información. Esto le llevará directamente al paso 5 anterior.

## <a name="apply-a-policy-across-site-collections"></a>Aplicación de una directiva entre colecciones de sitios
<a name="__toc260646789"> </a>

Comparta tipos de contenido entre colecciones de sitios mediante una aplicación de servicio de metadatos administrados para configurar la publicación de tipos de contenido. La publicación de tipos de contenido le ayuda a administrar el contenido y los metadatos de forma coherente en todos los sitios, ya que los tipos de contenido se pueden crear y actualizar de forma centralizada, y las actualizaciones se pueden publicar en varias colecciones de sitios o aplicaciones web de suscripción.

## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Creación de una plantilla a partir de una directiva existente para usarla entre colecciones de sitios
<a name="__toc262125409"> </a>

Puede definir una directiva de administración de información y, a continuación, crear una plantilla a partir de ella para usarla según sea necesario en varias colecciones de sitios. Este método se puede usar si desea tener una copia de seguridad de las directivas de información, o también se puede usar como método alternativo para usar la publicación de tipos de contenido para aplicar una directiva entre colecciones de sitios. Para crear una plantilla o copia de seguridad de la directiva, exporte la directiva de una colección de sitios y, a continuación, impórtelo a una ubicación guardada o a otra colección de sitios.

> [!IMPORTANT]
> Si usa la característica de exportación e importación como una manera de crear un conjunto de plantillas de directiva, tenga en cuenta que existe un identificador único en el archivo de .xml de directiva. Por este motivo, no puede importar esa directiva en un sitio más de una vez sin cambiar este identificador único.

### <a name="export-a-policy"></a>Exportación de una directiva
<a name="__toc260646790"> </a>

1. En la página principal de la colección de sitios, elija **Configuración Engranaje**![de configuración pequeña que tomó el lugar de Configuración del sitio.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Configuración del sitio**.

   En un sitio conectado a un grupo de SharePoint, haga clic en **Configuración**, en **Contenido del sitioy**, a continuación, en **Configuración del sitio**.

2. En la página Configuración del sitio, en Plantillas de directiva de tipo de contenido **de administración** \> de **colecciones de sitios**.

   ![Vínculo a la plantilla de directiva de tipo de contenido en la página Configuración del sitio.](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. Elija la directiva que desea exportar \> desplácese hasta la parte inferior \> **Exportar**.

4. En el símbolo del sistema para guardar o abrir el archivo, elija **Guardar** y, a continuación, seleccione una ubicación en la que guardar el archivo. Asegúrese de seleccionar una ubicación que esté disponible para las colecciones de sitios que importan la directiva.

5. Cuando se muestre el cuadro de diálogo Descargar completado, elija **Cerrar**.

### <a name="import-a-policy-to-a-different-site-collection"></a>Importación de una directiva a otra colección de sitios
<a name="__toc260646791"> </a>

La importación de una directiva de administración de información le permite aplicarla a varios tipos de contenido en el nivel de sitio o de lista dentro de una colección de sitios determinada. Las ventajas de hacerlo son dobles: no es necesario volver a definir y aplicar la directiva en cada tipo de contenido, y puede administrar más fácilmente las modificaciones de directiva realizando cambios en la directiva en un solo lugar.

1. En la página principal de la colección de sitios a la que desea aplicar la directiva, elija **Configuración**![Engranaje de configuración pequeña que tomó el lugar de Configuración del sitio.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Configuración del sitio**.

   En un sitio conectado a un grupo de SharePoint, haga clic en **Configuración**, en **Contenido del sitioy**, a continuación, en **Configuración del sitio**.

2. En la página Configuración del sitio, en Plantillas de directiva de tipo de contenido **de administración** \> de **colecciones de sitios**.

3. En la página \> Directivas **, vaya a Importar** \> **para** buscar el archivo XML de la directiva.

4. Seleccione el archivo XML en el que se guardó \> la directiva **Abrir**.

5. En la página Importar una directiva \> de colección de sitios **, importe** para agregar la directiva a la colección de sitios.

La directiva importada ahora se puede aplicar a uno o varios tipos de contenido en el nivel de sitio o lista.

Las directivas de administración de la información permiten a su organización controlar cuánto tiempo se conserva el contenido, auditar lo que hacen los usuarios con el contenido y agregar códigos de barras o etiquetas a los documentos. Una directiva puede ayudar a aplicar el cumplimiento con las regulaciones legales y gubernamentales o los procesos empresariales internos. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de los documentos y cuánto tiempo conservarlos.

Puede crear una directiva de administración de información en tres ubicaciones diferentes de la jerarquía del sitio, desde la más amplia hasta la más estrecha:

- Cree una directiva para usarla en varios tipos de contenido dentro de una colección de sitios.
- Cree una directiva para un tipo de contenido de sitio.
- Cree una directiva para una lista o biblioteca.

Para obtener más información, consulte [Introducción a las directivas de administración de la información](intro-to-info-mgmt-policies.md).
