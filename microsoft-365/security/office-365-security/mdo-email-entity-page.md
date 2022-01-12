---
title: Página de entidad de correo Office 365 Microsoft Defender para correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: mdo
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Los clientes de Microsoft Defender Office 365 E5 y P1 y P2 ahora pueden obtener una vista de 360 grados de cada correo electrónico con página de entidad de correo electrónico.
ms.openlocfilehash: 263411d6f0c9931dfd03fbf8b89fd24a86c3c9e6
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61939750"
---
# <a name="the-email-entity-page"></a>Página de la entidad de correo electrónico

**En este artículo:**
- [Llegar a la página de entidad de correo electrónico](#reach-the-email-entity-page)
- [Leer la página de entidad de correo electrónico](#read-the-email-entity-page)
- [Usar pestañas de página de entidad de correo electrónico](#use-email-entity-page-tabs)
- [Nuevo en la página de entidad de correo electrónico](#new-to-the-email-entity-page)

Los administradores de Microsoft Defender para Office 365 E5 y Defender para Office P1 y P2 tienen una vista de 360 grados del correo electrónico mediante la página entidad **Correo electrónico**. Esta página de correo electrónico de acceso se creó para mejorar la información que se entrega en el desplegable "detalles de correo electrónico" del Explorador [de amenazas.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>Llegar a la página de entidad de correo electrónico

La página de entidad de correo electrónico está disponible en el portal de Microsoft 365 Defender en correo electrónico <https://security.microsoft.com> **& explorador de** \> **colaboración**. O bien, para ir directamente a la **página Explorador,** use <https://security.microsoft.com/threatexplorer> .

En **el Explorador,** seleccione el asunto de un correo electrónico que está investigando. Se mostrará una barra dorada en la parte superior del menú desplegable de correo electrónico para ese correo. En esta invitación a la nueva página, se lee "Pruebe nuestra nueva página de entidad de correo electrónico con datos enriquecidos...". Seleccione esta opción para ver la nueva página.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Verá un banner dorado con las palabras *Pruebe nuestra nueva página de entidad de correo electrónico con datos enriquecidos* para navegar a la nueva experiencia.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Este gráfico de la página de entidad de correo electrónico se centra en los encabezados que verá. Tenga en cuenta que el encabezado de correo electrónico se muestra aquí.":::

> [!NOTE]
> Los permisos necesarios para ver y usar esta página son los mismos que para ver **explorer**. El administrador debe ser miembro del administrador global o del lector global, o del administrador de seguridad o del lector de seguridad. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="read-the-email-entity-page"></a>Leer la página de entidad de correo electrónico

La estructura está diseñada para que sea fácil de leer y navegar de un vistazo. Varias pestañas a lo largo de la parte superior de la página le permiten investigar con más detalle. Así es como funciona el diseño:

1. Los campos más necesarios están en el lado izquierdo del menú desplegable. Estos detalles son "pegajosos", lo que significa que están anclados a la izquierda, independientemente de la pestaña a la que navegues en el resto del control de salida.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Gráfico de la página de entidad de correo electrónico con el lado izquierdo resaltado. El título y los datos sobre la entrega de correo están aquí.":::

2. En la esquina superior derecha se encuentran las acciones que se pueden realizar en un correo electrónico. Las acciones que se puedan realizar a través **del Explorador** también estarán disponibles a través de la página de entidad de correo electrónico.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Gráfico de la página de entidad de correo electrónico con el lado *right* resaltado, esta vez. Acciones como &quot;Vista previa de correo electrónico&quot; y &quot;Ir a cuarentena&quot; están aquí.":::

3. Se puede realizar un análisis más profundo ordenando el resto de la página. Compruebe los detalles de detección de correo electrónico, el estado de autenticación de correo electrónico y el encabezado. Esta área debe buscarse caso por caso, pero la información de estas pestañas está disponible para cualquier correo electrónico.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="El panel principal de esta página incluye el encabezado de correo electrónico y el estado de autenticación.":::

### <a name="use-email-entity-page-tabs"></a>Usar pestañas de página de entidad de correo electrónico

Las pestañas de la parte superior de la página de entidad le permitirán investigar el correo electrónico de forma eficaz.

1. **Escala** de tiempo: la vista de escala de tiempo de un correo electrónico (por escala de tiempo del **Explorador)** muestra la entrega original a los eventos posteriores a la entrega que se suceden en un correo electrónico. Para los correos electrónicos que no tienen acciones posteriores a la entrega, la vista muestra la fila de entrega original en la vista de escala de tiempo. Eventos como: Purga automática de hora cero (ZAP), Remediate, clics de URL, etc., de orígenes como: sistema, administrador y usuario, se muestran aquí, en el orden en que se produjeron.
2. **Análisis:** el análisis muestra campos que ayudan a los administradores a analizar un correo electrónico en profundidad. Para los casos en los que los administradores necesitan comprender más acerca de los detalles de detección, remitente o destinatario y autenticación de correo electrónico, deben usar la pestaña Análisis. En esta página también se encuentran vínculos para datos adjuntos y direcciones URL, en "Entidades relacionadas". Aquí se numeran los datos adjuntos y las amenazas identificadas, y hacer clic le llevará directamente a las páginas Datos adjuntos y URL. Esta pestaña también tiene una opción ver encabezado para *mostrar el encabezado de correo electrónico*. Los administradores pueden comparar cualquier detalle de los encabezados de correo electrónico, en paralelo con la información del panel principal, para mayor claridad.
3. **Datos** adjuntos: examina los datos adjuntos que se encuentran en el correo electrónico con otros detalles que se encuentran en los datos adjuntos. El número de datos adjuntos mostrados actualmente está limitado a 10. Observe que los detalles de detonación de los datos adjuntos encontrados como malintencionados también se muestran aquí.
4. **DIRECCIONES URL:** en esta pestaña se enumeran las direcciones URL que se encuentran en el correo electrónico con otros detalles sobre las direcciones URL. El número de direcciones URL está limitado a 10 en este momento, pero estas 10 tienen prioridad para mostrar *primero direcciones URL malintencionadas.* La priorización le ahorra tiempo y trabajo de adivinación. Las direcciones URL encontradas como malintencionadas y detonadas también se mostrarán aquí.
5. **Correos electrónicos similares:** en esta pestaña se enumeran todos los correos electrónicos similares a la combinación de *id. de* mensaje de red y destinatario específica de este correo electrónico. La similitud se basa *en el cuerpo del mensaje*, solo. Las determinaciones tomadas en los correos para clasificarlos como "similares" no incluyen una consideración de datos *adjuntos*.

## <a name="new-to-the-email-entity-page"></a>Nuevo en la página de entidad de correo electrónico

Hay nuevas funcionalidades que vienen con esta página de entidad de correo electrónico. Esta es la lista.

### <a name="email-preview-for-cloud-mailboxes"></a>Vista previa de correo electrónico para buzones en la nube

Los administradores pueden obtener una vista previa de los correos electrónicos en los buzones de correo en la ***nube,*** si los correos siguen estando presentes en la nube. En caso de una eliminación suave (por un administrador o usuario) o ZAP (para poner en cuarentena), los correos electrónicos ya no están presentes en la ubicación de la nube. En ese caso, los administradores no podrán obtener una vista previa de esos correos específicos. Los correos electrónicos que se descartaron, o donde la entrega falló, nunca llegaron al buzón. Como resultado, los administradores tampoco podrán obtener una vista previa de esos correos electrónicos.

> [!WARNING]
> La vista previa de mensajes de correo electrónico requiere un rol especial denominado **Vista previa**. Puede agregar este rol en el portal de Microsoft 365 Defender como se describe en Correo & roles de colaboración [en el portal Microsoft 365 Defender .](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal) Es posible que deba crear un nuevo grupo de  roles de colaboración email  & y agregar el rol Vista previa a ese nuevo grupo de roles o agregar el rol Vista previa a un grupo de roles que permita **a** los administradores de la organización trabajar en el **Explorador**.

### <a name="detonation-details"></a>Detalles de detonación

Estos detalles son específicos de los datos adjuntos y las direcciones URL de correo electrónico. Los usuarios pueden ver estos detalles yendo  al Explorador y aplicando el filtro de tecnología de detección establecido en detonación de archivos o detonación de dirección URL. Los correos electrónicos filtrados para la detonación de archivos contendrán un archivo malintencionado con detalles de detonación, y los filtrados para direcciones URL contienen una dirección URL malintencionada y sus detalles de detonación.

Los usuarios verán detalles enriquecidos de detonación para datos adjuntos malintencionados conocidos o direcciones URL encontradas en sus correos electrónicos, que se detonaron para su inquilino específico. Constará de la cadena de detonación, el resumen de detonación, la captura de pantalla y los detalles del comportamiento observado para ayudar a los clientes a comprender por qué los datos adjuntos o la dirección URL se consideraron malintencionados y detonados.

1. *Cadena de detonación*. Un único archivo o detonación de dirección URL puede desencadenar varias detonaciones. La cadena Detonación realiza un seguimiento de la ruta de las detonaciones, incluido el archivo malintencionado original o la dirección URL que causó el veredicto, y todos los demás archivos o direcciones URL afectados por la detonación. Es posible que estas direcciones URL o archivos adjuntos no se presenten directamente en el correo electrónico, pero incluir ese análisis es importante para determinar por qué se encontró que el archivo o la dirección URL son malintencionados.  

    > [!NOTE]
    > Esto puede mostrar solo el elemento de nivel superior si no se encontró que ninguna de las entidades vinculadas a él era problemática o se detonó.

1.  Resumen de detonación proporciona un resumen básico para la detonación, como el tiempo de *análisis,* la hora en que se produjo la detonación, el sistema operativo y la aplicación, el sistema operativo y la aplicación en la que se produjo la detonación, el tamaño del archivo y el motivo del veredicto.
1. *Las capturas de* pantalla muestran las capturas de pantalla capturadas durante la detonación. Puede haber varias capturas de pantalla durante la detonación. No se capturan capturas de pantalla para
    - Archivos de tipo contenedor como .zip o .rar.
    - Si se abre una dirección URL en un vínculo que descarga directamente un archivo. Sin embargo, verá el archivo descargado en la cadena de detonación.
1. *Los* detalles de comportamiento son una exportación que muestra detalles de comportamiento como eventos exactos que tuvieron lugar durante la detonación y observables que contienen direcciones URL, IP, dominios y archivos que se encontraron durante la detonación (y pueden ser problemáticos o benignos). Tenga en cuenta que puede que no haya detalles de comportamiento para:
    - Archivos contenedor como .zip o .rar que retienen otros archivos.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Captura de pantalla del resumen de detonación que muestra la cadena, el resumen, los detalles de detonación y la captura de pantalla bajo el título *Análisis profundo*.":::

### <a name="other-innovations"></a>Otras innovaciones

*Etiquetas:* se trata de etiquetas aplicadas a los usuarios. Si el usuario es un destinatario, los administradores verán una *etiqueta de* destinatario. Del mismo modo, si el usuario es un remitente, una *etiqueta de* remitente. Aparecerá en el lado izquierdo de la página entidades de correo  electrónico (en la parte que se describe como pegajosa y, por lo tanto, anclada a la página).

*Ubicación de entrega más* reciente: la ubicación de entrega más reciente es la ubicación en la que un correo electrónico aterrizó después de acciones del sistema como ZAP o acciones de administración como Mover a elementos eliminados, finalizar. La ubicación de entrega más reciente no está diseñada para informar a los administradores de la ubicación actual *del* mensaje. Por ejemplo, si un usuario elimina un mensaje o lo mueve al archivo, la ubicación de entrega no se actualizará. Sin embargo, si se lleva a cabo una acción del sistema y se actualiza la ubicación (como un ZAP que da como resultado que un correo electrónico se mueva a cuarentena), se actualizaría la ubicación de entrega más reciente a la cuarentena.

*Detalles del correo* electrónico: detalles necesarios para una comprensión más detallada del correo electrónico disponible en la *pestaña* Análisis.

- Exchange de transporte (también conocidas como reglas de flujo de correo o *ETR):* estas reglas se aplican a un mensaje en la capa de transporte y tienen prioridad sobre los veredictos de suplantación de identidad (phish) y correo no deseado. Las reglas de flujo de correo se crean y modifican en el Centro de administración de Exchange en , pero si alguna regla de flujo de correo se aplica a un mensaje, el nombre de regla y el GUID se <https://admin.exchange.microsoft.com/#/transportrules> mostrarán aquí. Información valiosa para fines de seguimiento.

- *Invalidaciones del* sistema: este es un medio para hacer excepciones a la ubicación de entrega destinada a un mensaje al invalidar la ubicación de entrega dada por el sistema (según la tecnología de amenazas y detección).

- *Nivel de queja masiva (BCL):* el nivel de queja masiva (BCL) del mensaje. Un BCL más alto indica que es más probable que un mensaje de correo masivo genere quejas (el resultado natural si es probable que el correo electrónico sea correo no deseado).

- Nivel de confianza de correo no deseado *(SCL):* el nivel de confianza de correo no deseado (SCL) del mensaje. Un valor superior indica que el mensaje tiene más posibilidades de ser correo no deseado.

- *Nombre de dominio:* es el nombre de dominio del remitente.

- *Propietario del dominio:* especifica el propietario del dominio de envío.

- *Ubicación del* dominio: especifica la ubicación del dominio de envío.

- *Fecha de creación del* dominio: especifica la fecha de creación del dominio de envío. Un dominio recién creado es algo que podrías tener cuidado si otras señales indican algún comportamiento sospechoso.

*Autenticación de* correo electrónico: los métodos de autenticación de correo Microsoft 365 incluyen SPF, DKIM y DMARC.

- Marco de directivas de remitente (**SPF):** describe los resultados de la comprobación de SPF para el mensaje. Los valores posibles pueden ser:
  - Pass (dirección IP): la comprobación SPF del mensaje pasado e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente.
  - Error (dirección IP): error en la comprobación SPF del mensaje e incluye la dirección IP del remitente. A veces, recibe la denominación "error no recuperable".
  - Softfail (razón): el registro SPF designó al host como no autorizado para enviar, pero está en transición.
  - Neutro: el registro SPF indica explícitamente que no afirma si la dirección IP está autorizada para enviar.
  - Ninguno: el dominio no tiene un registro SPF o el registro SPF no evalúa un resultado.
  - Temperror: se ha producido un error temporal. Por ejemplo, un error de DNS. Es posible la misma comprobación sea correcta más tarde.
  - Permerror: se ha producido un error permanente. Por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.

- DomainKeys Identified Mail (**DKIM**):
  - Pass: indica la comprobación DKIM del mensaje pasado.
  - Error (motivo): indica la comprobación DKIM del mensaje con error y por qué. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma.
  - Ninguno: indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.

- Autenticación de mensajes basada en dominio, informes y conformidad (**DMARC**):
  - Pass: indica la comprobación DMARC del mensaje pasado.
  - Error: indica que se ha fallado la comprobación DMARC del mensaje.
  - Bestguesspass: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, la comprobación DMARC del mensaje habría pasado.
  - Ninguno: indica que no existe ningún registro TXT de DMARC para el dominio de envío en DNS.

*Autenticación* compuesta: este es un valor usado por Microsoft 365 para combinar la autenticación de correo electrónico como SPF, DKIM y DMARC, para determinar si el mensaje es auténtico. Usa el *dominio From:* del correo como base de la evaluación.

### <a name="email-summary-panel"></a>Panel de resumen de correo electrónico

El panel de resumen de correo electrónico es una vista resumida de la página de entidad de correo electrónico completa. Contiene detalles estandarizados sobre el correo electrónico (por ejemplo, detecciones), así como información específica del contexto (por ejemplo, para metadatos de cuarentena o envíos). El panel de resumen de correo electrónico reemplaza a los elementos tradicionales Detecciones en tiempo real, Explorador de amenazas, Envíos e informes.

> [!div class="mx-imgBorder"]
> ![Abra el vínculo de entidad de correo electrónico.](../../media/open-email-entity-mdo.png)

> [!NOTE]
> Para ver todos los componentes, haga clic en el vínculo Abrir entidad **de correo electrónico** para abrir la página de entidad de correo electrónico completa.  

El panel de resumen de correo electrónico se divide en las siguientes secciones:  

- *Detalles de entrega:* contiene información sobre las amenazas y el nivel de confianza correspondiente, las tecnologías de detección y la ubicación de entrega original y más reciente.

- *Detalles del correo* electrónico: contiene información sobre las propiedades de correo electrónico como el nombre del remitente, la dirección del remitente, el tiempo recibido, los detalles de autenticación y otros detalles.

- *DIRECCIONES URL:* de forma predeterminada, verá 3 direcciones URL y sus amenazas correspondientes. Siempre puede hacer clic en **Ver todas las direcciones URL** para expandir y ver todas las direcciones URL y exportarlas.  

- *Datos* adjuntos: de forma predeterminada, verá 3 datos adjuntos. Siempre puede hacer clic en **Ver todos los datos adjuntos** para expandir y ver todos los datos adjuntos. 

Además de las secciones anteriores, también verá secciones específicas de algunas experiencias que están integradas con el panel de resumen: 

- Envíos: 

    - *Detalles del envío:* contiene información sobre los envíos específicos, como:
        - Fecha enviada
        - Subject
        - Tipo de envío
        - Motivo para enviar
        - Identificador de envío
        - Enviado por

    - *Detalles del resultado:* se revisan los mensajes enviados. Puede ver el resultado del envío, así como los pasos siguientes recomendados.

- Cuarentena:  

    - *Detalles de cuarentena:* contiene detalles específicos de cuarentena. Para obtener más información, vea [Manage quarantined messages](manage-quarantined-messages-and-files.md#view-quarantined-message-details).

        - Expira: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.
        - Liberado para: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.
        - Todavía no se ha liberado para: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

    - *Acciones de cuarentena:* para obtener más información sobre las distintas acciones de cuarentena, vea [Administrar mensajes en cuarentena.](manage-quarantined-messages-and-files.md#take-action-on-quarantined-email)