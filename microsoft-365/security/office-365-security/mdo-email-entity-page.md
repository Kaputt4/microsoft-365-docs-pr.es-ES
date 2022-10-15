---
title: Página de la entidad de correo electrónico Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/12/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-security
ms.subservice: mdo
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom: ''
description: Microsoft Defender para Office 365 clientes de E5 y P1 y P2 pueden ver detalles de correo electrónico en el Explorador (Explorador de amenazas), incluidos los encabezados de correo electrónico para copia, Detalles de detección, Amenazas detectadas, Ubicaciones de entrega más recientes y originales, Acciones de entrega e identificadores como Identificador de mensaje de red, etc.
search.appverid: met150
ms.openlocfilehash: 2cf260b477a5e10e3502cd381e625e0024bc034f
ms.sourcegitcommit: 1f4c51d022d1cfb6c194bf0f0af9c2841c781d68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68573911"
---
# <a name="the-email-entity-page"></a>Página de la entidad de correo electrónico

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**En este artículo:**
- [Llegar a la página de la entidad de correo electrónico](#reach-the-email-entity-page)
- [Leer la página de la entidad de correo electrónico](#read-the-email-entity-page)
- [Usar pestañas de página de entidad de correo electrónico](#use-email-entity-page-tabs)
- [Nuevo en la página de entidad de correo electrónico](#new-to-the-email-entity-page)

Los administradores de Microsoft Defender para Office 365 E5 y Defender para Office P1 y P2 tienen una vista de correo electrónico de 360 grados mediante la **página de entidad Email**. Esta página de correo electrónico de acceso se creó para mejorar la información proporcionada en el [control flotante "detalles de correo electrónico" del Explorador de amenazas](threat-explorer-views.md).

Consulte los detalles del correo electrónico en explorador o explorador de amenazas, incluidos los encabezados de correo electrónico *con la opción de copiar*, Detalles de detección, Amenazas detectadas, ubicaciones de entrega más recientes y originales, Acciones de entrega e identificadores como Identificador de mensaje de red, etc.

## <a name="how-to-get-to-the-email-entity-page"></a>Cómo llegar a la página de entidad de correo electrónico

Vaya al portal de Microsoft 365 Defender en <https://security.microsoft.com>, Email & **explorador** de **colaboración**\>. O bien, para ir directamente a la página **Explorador** , use <https://security.microsoft.com/threatexplorer>.

1. En **el Explorador**, seleccione el asunto de un correo electrónico que está investigando.
1. Se abrirá el control flotante de correo electrónico de ese correo.
1. Verá **Abrir entidad de correo electrónico**.
1. Selecciónelo para profundizar en el correo electrónico.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Con el correo electrónico seleccionado, obtendrá un control flotante con detalles y la página Abrir entidad del correo electrónico en la parte superior." lightbox="../../media/email-entities-1-navigation-to-ee.png":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Gráfico de la página de la entidad de correo electrónico que se centra en los encabezados que verá" lightbox="../../media/email-entities-2-eep.png":::

> [!NOTE]
> Los permisos necesarios para ver y usar esta página son los mismos que para ver el **Explorador**. El administrador debe ser miembro del administrador global o lector global, o administrador de seguridad o lector de seguridad. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="how-to-read-the-email-entity-page"></a>Cómo leer la página de la entidad de correo electrónico

La estructura está diseñada para ser fácil de leer y navegar a través de un vistazo. Varias pestañas a lo largo de la parte superior de la página le permiten investigar con más detalle. Este es el funcionamiento del diseño:

1. Los campos más necesarios están en el lado izquierdo del control flotante. Estos detalles son "pegajosos", lo que significa que están anclados a la izquierda, independientemente de la pestaña a la que navegue en el resto del control flotante.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Gráfico de la página de la entidad de correo electrónico con el lado izquierdo resaltado" lightbox="../../media/email-entities-3-left-panel.png":::

2. En la esquina superior derecha se encuentran las acciones que se pueden realizar en un correo electrónico. Las acciones que se pueden realizar a través **del Explorador** también estarán disponibles a través de la página de entidades de correo electrónico.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Gráfico de la página de la entidad de correo electrónico con el lado derecho resaltado" lightbox="../../media/email-entities-5-preview.png":::

3. Se puede realizar un análisis más profundo mediante la ordenación a través del resto de la página. Compruebe los detalles de detección de correo electrónico, el estado de autenticación de correo electrónico y el encabezado. Esta área debe buscarse caso por caso, pero la información de estas pestañas está disponible para cualquier correo electrónico.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Panel principal de la página que incluye el encabezado de correo electrónico y el estado de autenticación" lightbox="../../media/email-entities-4-middle-panel.png":::

### <a name="how-to-use-the-email-entity-page-tabs"></a>Cómo usar las pestañas de página de la entidad de correo electrónico

Las pestañas de la parte superior de la página de entidad le permitirán investigar el correo electrónico de forma eficaz.

1. **Escala de tiempo**: la vista de escala de tiempo de un correo electrónico (por escala de tiempo del **Explorador** ) muestra la entrega original a eventos posteriores a la entrega que se producen en un correo electrónico. En el caso de los correos electrónicos que no tienen acciones posteriores a la entrega, la vista muestra la fila de entrega original en la vista de escala de tiempo. Eventos como: Purga automática de cero horas (ZAP), Corrección, clics de dirección URL, et cetera, de orígenes como: sistema, administrador y usuario, aparecen aquí, en el orden en que se produjeron.
2. **Análisis**: el análisis muestra campos que ayudan a los administradores a analizar un correo electrónico en profundidad. En los casos en los que los administradores necesitan comprender más sobre la detección, el remitente o el destinatario y los detalles de autenticación por correo electrónico, deben usar la pestaña Análisis. Los vínculos para datos adjuntos y direcciones URL también se encuentran en esta página, en "Entidades relacionadas". Los datos adjuntos y las amenazas identificadas se numeran aquí y al hacer clic se le llevará directamente a las páginas Datos adjuntos y URL. Esta pestaña también tiene una opción Ver encabezado para *mostrar el encabezado de correo electrónico*. Los administradores pueden comparar cualquier detalle de los encabezados de correo electrónico, en paralelo con la información del panel principal, para mayor claridad.
3. **Datos adjuntos**: examina los datos adjuntos que se encuentran en el correo electrónico con otros detalles que se encuentran en los datos adjuntos. El número de datos adjuntos que se muestran actualmente está limitado a 10. Observe que los detalles de la detonación de los datos adjuntos que se encuentran como malintencionados también se muestran aquí.
4. **Direcciones URL**: en esta pestaña se enumeran las direcciones URL que se encuentran en el correo electrónico con otros detalles sobre las direcciones URL. El número de direcciones URL está limitado a 10 en este momento, pero estas 10 tienen prioridad para mostrar *primero direcciones URL malintencionadas*. La priorización le ahorra tiempo y conjeturas. Las direcciones URL que se encontraron como malintencionadas y detonadas también se mostrarán aquí.
5. **Correos electrónicos similares**: en esta pestaña se enumeran todos los correos electrónicos similares a la combinación *de id. de mensaje de red y destinatario* específica de este correo electrónico. La similitud se basa únicamente en el *cuerpo del mensaje*. Las determinaciones realizadas en los correos para clasificarlos como "similares" no incluyen una consideración de *los datos adjuntos*.

## <a name="available-on-the-email-entity-page"></a>Disponible en la página de entidad de correo electrónico

Estos son algunos detalles útiles para empezar.

### <a name="email-preview-for-cloud-mailboxes"></a>Email versión preliminar para buzones en la nube

Los administradores pueden obtener una vista previa de los correos electrónicos en buzones en la nube ***, si*** los correos siguen presentes en la nube. En caso de una eliminación temporal (por parte de un administrador o usuario) o ZAP (para poner en cuarentena), los correos electrónicos ya no están presentes en la ubicación de la nube. En ese caso, los administradores no podrán obtener una vista previa de esos correos específicos. Los correos electrónicos que se quitaron o en los que se produjo un error en la entrega nunca lo hicieron en el buzón de correo. Como resultado, los administradores tampoco podrán obtener una vista previa de esos correos electrónicos.

> [!WARNING]
> La vista previa de los correos electrónicos requiere un rol especial denominado **Versión preliminar**. Puede agregar este rol en el portal de Microsoft 365 Defender como se describe en [Email & roles de colaboración en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal). Es posible que tenga que crear un nuevo Email & grupo de roles de **colaboración** allí y agregar el rol **De vista previa** a ese nuevo grupo de roles o agregar el rol **Vista previa** a un grupo de roles que permita a los administradores de su organización trabajar en **el Explorador**.

### <a name="detonation-details"></a>Detalles de la detonación

Estos detalles son específicos de los datos adjuntos y las direcciones URL del correo electrónico. Los usuarios pueden ver estos detalles yendo al Explorador y aplicando el filtro de *tecnología de detección* establecido en la detonación de archivos o la detonación de direcciones URL. Los correos electrónicos filtrados para la detonación de archivos contendrán un archivo malintencionado con detalles de detonación y los filtrados para direcciones URL contienen una dirección URL malintencionada y sus detalles de detonación.

Los usuarios verán detalles de detonación enriquecidos para los datos adjuntos malintencionados conocidos o las direcciones URL que se encuentran en sus correos electrónicos, que se detonaron para su inquilino específico. Incluirá la cadena de detonación, el resumen de la detonación, la captura de pantalla y los detalles del comportamiento observado para ayudar a los clientes a comprender por qué los datos adjuntos o la dirección URL se consideraron malintencionados y detonados.

1. *Cadena de detonación*. Una detonación de un solo archivo o dirección URL puede desencadenar varias detonaciones. La cadena de detonación realiza un seguimiento de la ruta de acceso de las detonaciones, incluido el archivo malintencionado original o la dirección URL que provocó el veredicto, y todos los demás archivos o direcciones URL afectados por la detonación. Es posible que estas direcciones URL o archivos adjuntos no estén directamente presentes en el correo electrónico, pero incluir ese análisis es importante para determinar por qué se encontró que el archivo o la dirección URL eran malintencionados.  

    > [!NOTE]
    > Esto puede mostrar solo el elemento de nivel superior si no se encontró que ninguna de las entidades vinculadas a él era problemática o se detonó.

1. *Resumen de la detonación* proporciona un resumen básico para la detonación, como el *tiempo de análisis*, la hora en que se produjo la detonación, el sistema operativo y la aplicación, el sistema operativo y la aplicación en los que se produjo la detonación, el tamaño del archivo y el motivo del veredicto.
1. *Las capturas de pantalla* muestran las capturas de pantalla capturadas durante la detonación. Puede haber varias capturas de pantalla durante la detonación. No se capturan capturas de pantalla para
    - Archivos de tipo contenedor como .zip o .rar.
    - Si una dirección URL se abre en un vínculo que descarga directamente un archivo. Sin embargo, verá el archivo descargado en la cadena de detonación.
1. *Detalles del comportamiento* son una exportación que muestra detalles de comportamiento como eventos exactos que tuvieron lugar durante la detonación y observables que contienen direcciones URL, direcciones IP, dominios y archivos que se encontraron durante la detonación (y pueden ser problemáticos o benignos). Tenga en cuenta que es posible que no haya detalles de comportamiento para:
    - Archivos de contenedor como .zip o .rar que contienen otros archivos.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Resumen de la detonación que muestra la cadena, el resumen, los detalles de la detonación y la captura de pantalla bajo el encabezado *Análisis profundo*" lightbox="../../media/email-entities-6-detonation-page.png":::

### <a name="other-features-that-make-the-email-entity-page-helpful"></a>Otras características que hacen que la página de la entidad de Email sea útil

*Etiquetas*: estas son etiquetas aplicadas a los usuarios. Si el usuario es un destinatario, los administradores verán una etiqueta *de destinatario* . Del mismo modo, si el usuario es un remitente, una etiqueta *de remitente* . Aparecerá en el lado izquierdo de la página de entidades de correo electrónico (en la parte que se describe como *pegajosa* y, por tanto, anclada a la página).

*Ubicación de entrega más reciente*: la ubicación de entrega más reciente es la ubicación donde aterrizó un correo electrónico después de que finalicen acciones del sistema como ZAP o acciones de administrador como Mover a elementos eliminados. La ubicación de entrega más reciente no está pensada para informar a los administradores de la ubicación *actual* del mensaje. Por ejemplo, si un usuario elimina un mensaje o lo mueve al archivo, la ubicación de entrega no se actualizará. Sin embargo, si se ha realizado una acción del sistema y se ha actualizado la ubicación (como un ZAP que da como resultado un correo electrónico que se mueve a cuarentena), se actualizaría la ubicación de entrega más reciente a la cuarentena.

*Email detalles*: detalles necesarios para comprender mejor el correo electrónico disponible en la pestaña *Análisis*.

- *Reglas de transporte de Exchange (también conocidas como reglas de flujo de correo o ETR):* estas reglas se aplican a un mensaje en la capa de transporte y tienen prioridad sobre los veredictos de phish y spam. Las reglas de flujo de correo se crean y modifican en el Centro de administración de Exchange en <https://admin.exchange.microsoft.com/#/transportrules>, pero si alguna regla de flujo de correo se aplica a un mensaje, el nombre de la regla y el GUID se mostrarán aquí. Información valiosa con fines de seguimiento.

- *Invalidación principal: origen*: la invalidación principal y el origen hacen referencia a la configuración de inquilino o usuario que ha afectado a la entrega del correo electrónico, reemplazando la ubicación de entrega dada por el sistema (según la tecnología de amenazas y detección). Por ejemplo, podría tratarse de un correo electrónico bloqueado debido a una regla de transporte configurada por el inquilino o a un correo electrónico permitido debido a una configuración de usuario final para remitentes seguros. 

- *Todas las invalidaciones*: todas las invalidaciones hacen referencia a la lista de invalidaciones (configuración de inquilino o usuario) que se aplicó en el correo electrónico, lo que puede o no haber afectado a la entrega de un correo electrónico. Por ejemplo, si se aplica una regla de transporte configurada por un inquilino, así como una configuración de directiva configurada por el inquilino (por ejemplo, desde las listas De permitir bloques de inquilinos), se aplicarán a un correo electrónico, ambos aparecerán en este campo. Puede comprobar el campo de invalidación principal para determinar la configuración que ha afectado a la entrega del correo electrónico. 

- *Nivel de queja masiva (BCL):* el nivel de queja masiva (BCL) del mensaje. Una BCL más alta indica que es más probable que un mensaje de correo masivo genere quejas (el resultado natural si es probable que el correo electrónico sea correo no deseado).

- *Nivel de confianza de correo no deseado (SCL):* el nivel de confianza de correo no deseado (SCL) del mensaje. Un valor superior indica que el mensaje tiene más posibilidades de ser correo no deseado.

- *Tipo de cliente*: indica el tipo de cliente desde el que se envió el correo electrónico como REST.

- *Reenvío*: en escenarios con reenvío automático, indica el usuario de reenvío, así como el tipo de reenvío, como ETR o el reenvío SMTP.

- *Lista de distribución*: muestra la lista de distribución, si el destinatario recibió el correo electrónico como miembro de la lista. Muestra la lista de distribución de nivel superior si hay listas de distribución anidadas implicadas.  

- *Para, Cc*: indica las direcciones que aparecen en los campos Para, Cc de un correo electrónico. La información de estos campos está restringida a 5000 caracteres.

- *Nombre de dominio*: es el nombre de dominio del remitente.

- *Propietario del dominio*: especifica el propietario del dominio de envío.

- *Ubicación del dominio*: especifica la ubicación del dominio de envío.

- *Fecha de creación del dominio*: especifica la fecha de creación del dominio de envío. Un dominio recién creado es algo que podría tener cuidado si otras señales indican algún comportamiento sospechoso.

*autenticación de Email*: Email métodos de autenticación usados por Microsoft 365 incluyen SPF, DKIM y DMARC.

- Marco de directivas de remitente (**SPF**): describe los resultados de la comprobación de SPF para el mensaje. Los valores posibles pueden ser:
  - Pasar (dirección IP): la comprobación SPF del mensaje pasado e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente.
  - Error (dirección IP): error en la comprobación de SPF del mensaje e incluye la dirección IP del remitente. A veces, recibe la denominación "error no recuperable".
  - Softfail (motivo): el registro SPF designó al host como que no se le permite enviar, pero está en transición.
  - Neutral: el registro SPF indica explícitamente que no afirma si la dirección IP está autorizada para enviar.
  - Ninguno: el dominio no tiene un registro SPF o el registro SPF no se evalúa como un resultado.
  - Temperror: se ha producido un error temporal. Por ejemplo, un error de DNS. Es posible la misma comprobación sea correcta más tarde.
  - Permerror: se ha producido un error permanente. Por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.

- Correo identificado de DomainKeys (**DKIM**):
  - Pasar: indica la comprobación DKIM del mensaje pasado.
  - Error (motivo): indica la comprobación DKIM del mensaje con error y por qué. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma.
  - Ninguno: indica que el mensaje no se firmó. Esto puede indicar o no que el dominio tiene un registro DKIM o que el registro DKIM no se evalúa como un resultado, solo que este mensaje no se firmó.

- Autenticación, informes y conformidad de mensajes basados en dominio (**DMARC**):
  - Pasar: indica la comprobación de DMARC para el mensaje pasado.
  - Error: indica que se ha producido un error en la comprobación de DMARC para el mensaje.
  - Bestguesspass: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, la comprobación de DMARC para el mensaje habría pasado.
  - Ninguno: indica que no existe ningún registro TXT de DMARC para el dominio de envío en DNS.

*Autenticación compuesta*: este es un valor usado por Microsoft 365 para combinar la autenticación de correo electrónico como SPF, DKIM y DMARC, para determinar si el mensaje es auténtico. Usa el dominio *From:* del correo como base de evaluación.

## <a name="actions-you-can-take-on-the-email-entity-page"></a>Acciones que puede realizar en la página de entidad Email

Los equipos de seguridad ahora pueden realizar acciones de correo electrónico, como la eliminación temporal y la eliminación rígida, pasar a correo no deseado, pasar a la bandeja de entrada, desencadenar una investigación, enviar a Microsoft para su revisión en línea y et cetera. **Las** acciones de bloque de nivel de inquilino, como el archivo y la dirección URL o el remitente, también se pueden desencadenar desde la página de entidad Email.  

Podrá seleccionar **Realizar acciones** en la esquina superior derecha de la página de entidad y se abrirá el Asistente para acciones para que seleccione la acción específica que necesita. 
![Realice una acción desde la página de la entidad.](../../media/Take-ActionWizard-Email-entity.png)

En el Asistente para acciones, puede realizar acciones de correo electrónico, envíos de correo electrónico, bloquear el dominio remitente y remitente, acciones de investigación y aprobación en dos pasos (agregar a la corrección) en el mismo panel lateral. Esto sigue un flujo coherente para facilitar su uso. El Asistente para acciones usa el mismo sistema que las acciones del Explorador (para las acciones Eliminar, Envíos e Investigación), por ejemplo. Podrá ver y realizar un seguimiento de estas acciones en el [Centro de acciones unificadas](https://security.microsoft.com/action-center/history) (para correos electrónicos eliminados), en el [portal de envío](https://security.microsoft.com/reportsubmission) (para envíos) y en la página Listas de [permitidos o bloqueados de inquilinos](https://security.microsoft.com/tenantAllowBlockList) para (bloques TABL). 

También vamos a incorporar la dirección URL del bloque de nivel de inquilino y los datos adjuntos a las respectivas pestañas URL de entidad Email y Datos adjuntos. Tras la aprobación, se puede realizar un seguimiento de todas las direcciones URL de bloque de listas de inquilinos y listas de bloques (o TABL) y los datos adjuntos de bloque en las páginas TABL/URL y TABL/file. 
![Realice una acción de dirección URL de bloque desde la página de entidad.](../../media/Block-URL-Email-entity.png)

Consulte [los permisos](permissions-microsoft-365-security-center.md) necesarios para realizar estas acciones. 

 
### <a name="the-email-summary-panel"></a>El panel de resumen de Email

El panel de resumen de correo electrónico es una vista resumida de la página completa de la entidad de correo electrónico. Contiene detalles estandarizados sobre el correo electrónico (por ejemplo, detecciones), así como información específica del contexto (por ejemplo, para metadatos de cuarentena o envíos). El panel de resumen de correo electrónico reemplaza los controles flotantes tradicionales Detecciones en tiempo real, Explorador de amenazas, Envíos y Informes.

> [!div class="mx-imgBorder"]
> ![Abra el vínculo de entidad de correo electrónico.](../../media/open-email-entity-mdo.png)

> [!NOTE]
> Para ver todos los componentes, haga clic en el vínculo **Abrir entidad de correo electrónico** para abrir la página completa de la entidad de correo electrónico.  

El panel de resumen de correo electrónico se divide en las secciones siguientes:  

- *Detalles de entrega*: contiene información sobre amenazas y el nivel de confianza correspondiente, las tecnologías de detección y la ubicación de entrega original y más reciente.

- *Email detalles*: contiene información sobre las propiedades de correo electrónico, como el nombre del remitente, la dirección del remitente, la hora recibida, los detalles de autenticación y otros detalles.

- *Direcciones URL*: de forma predeterminada, verá tres direcciones URL y sus amenazas correspondientes. Siempre puede seleccionar **Ver todas las direcciones URL** para expandirlas y ver todas las direcciones URL y exportarlas.  

- *Datos adjuntos*: de forma predeterminada, verá tres datos adjuntos. Siempre puede seleccionar **Ver todos los datos adjuntos** para expandir y ver todos los datos adjuntos. 

Además de las secciones anteriores, también verá secciones específicas de algunas experiencias que se integran con el panel de resumen: 

- Presentaciones: 

    - *Detalles del envío*: contiene información sobre los envíos específicos, como:
        - Fecha de envío
        - Subject
        - Tipo de envío
        - Motivo para enviar
        - Id. de envío
        - Enviado por

    - *Detalles del resultado*: se revisan los mensajes enviados. Puede ver el resultado del envío, así como los pasos siguientes recomendados.

- Cuarentena:  

    - *Detalles de cuarentena*: contiene detalles específicos de la cuarentena. Para obtener más información, consulte [Administración de mensajes en cuarentena](manage-quarantined-messages-and-files.md#view-quarantined-message-details).

        - Expira: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.
        - Liberado para: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.
        - Todavía no se ha liberado para: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

    - *Acciones de cuarentena*: para obtener más información sobre las diferentes acciones de cuarentena, consulte [Administración de mensajes en cuarentena](manage-quarantined-messages-and-files.md#take-action-on-quarantined-email).
