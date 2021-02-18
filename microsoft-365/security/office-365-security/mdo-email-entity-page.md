---
title: Página de entidad de correo electrónico de Microsoft Defender para Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los clientes de Microsoft Defender para Office 365 E5 y ATP P1 y ATP P2 ahora pueden obtener una vista de 360 grados de cada correo electrónico con la página de entidad de correo electrónico.
ms.openlocfilehash: 0a866b4d635e5c9e26b6fc065503b44ee2063e9f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289490"
---
# <a name="the-email-entity-page"></a>La página Entidad de correo electrónico

**En este artículo:**
- [Llegar a la página de entidad de correo electrónico](#reach-the-email-entity-page)
- [Leer la página de entidad de correo electrónico](#read-the-email-entity-page)
- [Usar pestañas de página de entidad de correo electrónico](#use-email-entity-page-tabs)
- [Nuevo en la página de entidad de correo electrónico](#new-to-the-email-entity-page)

Los administradores de Microsoft Defender para Office 365 (o MDO) E5, y MDO P1 y P2 tienen una vista de 360 grados del correo electrónico mediante la página entidad correo **electrónico.** Esta página de correo electrónico de ir se creó para mejorar la información que se entrega en el menú desplegable "Detalles de correo electrónico" del Explorador [de amenazas.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>Llegar a la página de entidad de correo electrónico

Tanto el Centro de seguridad y cumplimiento de Office (protection.office.com) como el nuevo Centro de seguridad de Microsoft 365 (security.microsoft.com) le permitirán ver y usar la página de entidad de correo electrónico.

|Hacia el centro  |URL  |Navegación  |
|---------|---------|---------|
|Seguridad y cumplimiento |protection.office.com | Explorador de administración > amenazas   |
|Centro de seguridad de Microsoft 365 |security.microsoft.com | Explorador de & colaboración > correo electrónico |

En el Explorador de amenazas, seleccione el asunto de un correo electrónico que está investigando. Se mostrará una barra de oro en la parte superior del menú desplegable de correo electrónico para ese correo. Esta invitación a la nueva página, dice "Pruebe nuestra nueva página de entidad de correo electrónico con datos enriquecidos...". Seleccione esta opción para ver la nueva página.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="You will see a gold banner with the words *Try out our new email entity page with enriched data* to navigate to the new experience.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Este gráfico de la página de entidad de correo electrónico se centra en los encabezados que verá. Tenga en cuenta que el encabezado de correo electrónico se muestra aquí.":::

> [!NOTE]
> Los permisos necesarios para ver y usar esta página son los mismos que para ver el Explorador de amenazas. El administrador debe ser miembro del administrador global o lector global, o administrador de seguridad o lector de seguridad.

## <a name="read-the-email-entity-page"></a>Leer la página de entidad de correo electrónico

La estructura está diseñada para que sea fácil de leer y navegar de un vistazo. Varias pestañas en la parte superior de la página permiten investigar con más detalle. Así es como funciona el diseño:

1. Los campos más obligatorios están en el lado izquierdo del menú desplegable. Estos detalles son "permanentes", lo que significa que están anclados a la izquierda, independientemente de la pestaña a la que navegues en el resto del control desplegable.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Gráfico de la página de entidad de correo electrónico con el lado izquierdo resaltado. El título y los datos sobre la entrega de correo están aquí.":::

2. En la esquina superior derecha se encuentran las acciones que se pueden realizar en un correo electrónico. Las acciones que se pueden realizar a través del Explorador también estarán disponibles a través de la página de entidad de correo electrónico.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Gráfico de la página de entidad de correo electrónico con el lado *right* resaltado, esta vez. Acciones como &quot;Vista previa de correo electrónico&quot; y &quot;Ir a cuarentena&quot; están aquí.":::

3. Se puede realizar un análisis más profundo ordenando el resto de la página. Compruebe los detalles de detección de correo electrónico, el estado de autenticación de correo electrónico y el encabezado. Esta área debe buscarse caso por caso, pero la información de estas pestañas está disponible para cualquier correo electrónico.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="El panel principal de esta página incluye el encabezado de correo electrónico y el estado de autenticación.":::

### <a name="use-email-entity-page-tabs"></a>Usar pestañas de página de entidad de correo electrónico

Las pestañas de la parte superior de la página de la entidad le permitirán investigar el correo electrónico de forma eficaz.

1. **Escala** de tiempo: la vista de escala de tiempo de un correo electrónico (según la escala de tiempo del Explorador de amenazas) muestra la entrega original a los eventos posteriores a la entrega que se suceden en un correo electrónico. Para los correos electrónicos que no tienen acciones posteriores a la entrega, la vista muestra la fila de entrega original en la vista escala de tiempo. Eventos como: Purga automática de cero horas (ZAP), Corrección, clics de URL, etc., de orígenes como: sistema, administrador y usuario, se muestran aquí, en el orden en que se produjeron.
2. **Análisis:** el análisis muestra campos que ayudan a los administradores a analizar un correo electrónico en profundidad. Para los casos en los que los administradores necesitan comprender más sobre la detección, el remitente o el destinatario y los detalles de autenticación de correo electrónico, deben usar la pestaña Análisis. También se encuentran vínculos para datos adjuntos y direcciones URL en esta página, en "Entidades relacionadas". Aquí se numeran los datos adjuntos y las amenazas identificadas y, al hacer clic, se le llevará directamente a las páginas de datos adjuntos y url. Esta pestaña también tiene una opción ver encabezado para *mostrar el encabezado de correo electrónico*. Los administradores pueden comparar cualquier detalle de los encabezados de correo electrónico, en paralelo con la información del panel principal, para mayor claridad.
3. **Datos** adjuntos: examina los datos adjuntos que se encuentran en el correo electrónico con otros detalles que se encuentran en los datos adjuntos. Actualmente, el número de datos adjuntos mostrados está limitado a 10. Observe que aquí también se muestran los detalles de detonación de los datos adjuntos que se encuentran como malintencionados.
4. **Direcciones URL:** en esta pestaña se enumeran las direcciones URL que se encuentran en el correo electrónico con otros detalles sobre las direcciones URL. El número de direcciones URL está limitado a 10 en este momento, pero estas 10 tienen prioridad para mostrar *primero direcciones URL malintencionadas.* La priorización ahorra tiempo y trabajo de conjetura. Las direcciones URL que se encontraron malintencionadas y detonadas también se mostrarán aquí.
5. **Mensajes de correo** electrónico similares: esta pestaña muestra todos los correos electrónicos similares a la combinación de *id. de* mensaje de red y destinatario específica de este correo electrónico. La similitud se basa *solo en el cuerpo del* mensaje. Las determinaciones tomadas en los correos para clasificarlos como "similares" no incluyen una consideración de datos *adjuntos.*

## <a name="new-to-the-email-entity-page"></a>Nuevo en la página de entidad de correo electrónico

Hay nuevas funcionalidades que vienen con esta página de entidad de correo electrónico. Esta es la lista.

### <a name="email-preview-for-cloud-mailboxes"></a>Vista previa de correo electrónico para buzones en la nube
Los administradores pueden obtener una vista previa de los correos electrónicos en ***los*** buzones en la nube, si los correos siguen presentes en la nube. En el caso de una eliminación de software (por parte de un administrador o usuario) o ZAP (para poner en cuarentena), los correos electrónicos ya no están presentes en la ubicación de la nube. En ese caso, los administradores no podrán obtener una vista previa de esos correos específicos. Los mensajes de correo electrónico que se descartaron, o en los que se ha fallado la entrega, nunca llegaron al buzón. Como resultado, los administradores tampoco podrán obtener una vista previa de esos correos electrónicos.

> [!WARNING]
>La vista previa de mensajes de correo electrónico requiere un rol especial denominado ***Preview** _ para asignarse a los administradores. Puede agregar este rol yendo a _ *Permisos & roles** > Correo electrónico & **roles** de colaboración en *security.microsoft.com* o **Permisos** en *protection.office.com*. Agrega el ***rol Vista*** previa a cualquiera de los grupos de roles o una copia de un grupo de roles que permita a los administradores de la organización trabajar en el Explorador de amenazas.

### <a name="detonation-details"></a>Detalles de la detonación

Estos detalles son específicos de los datos adjuntos de correo electrónico y las direcciones URL.

Los usuarios verán detalles enriquecidos de detonación para los datos adjuntos malintencionados conocidos o hipervínculos encontrados en sus buzones, incluida la cadena de detonación, el resumen de detonación, la captura de pantalla y los detalles del comportamiento observado para ayudar a los clientes a comprender por qué los datos adjuntos o la dirección URL se consideraron malintencionados y detonados.
 
- *Cadena de detonación:* un solo archivo o detonación de dirección URL puede desencadenar varias detonaciones. La cadena de detonación realiza un seguimiento de la ruta de las detonaciones, incluido el archivo malintencionado original o la dirección URL que provocó el veredicto, y todos los demás archivos o direcciones URL que se han producido por la detonación. Es posible que estas direcciones URL o archivos adjuntos no se presenten directamente en el correo electrónico, pero incluir ese análisis es importante para determinar por qué se ha encontrado que el archivo o la dirección URL son malintencionados.
- *Resumen de detonación:* proporciona información sobre:
    - Intervalo de tiempo de detonación.
    - Veredicto del archivo adjunto o dirección URL.
    - Información relacionada (número de archivo, direcciones URL, DIRECCIONES IP o dominios), que son otras entidades examinadas durante la detonación.
- *Captura de pantalla de detonación:* muestra capturas de pantalla tomadas durante el proceso de detonación.
- *Detalles de la detonación:* estos son los detalles de comportamiento exactos de cada proceso que tuvo lugar durante la detonación.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot of the detonation summary showing the chain, summary, detonation details, and screenshot under the heading *Deep Analysis*.":::

### <a name="other-innovations"></a>Otras innovaciones

*Etiquetas:* son etiquetas que se aplican a los usuarios. Si el usuario es un destinatario, los administradores verán una *etiqueta de* destinatario. Del mismo modo, si el usuario es un remitente, una *etiqueta de* remitente. Aparecerá en el lado izquierdo de la página de entidades de  correo electrónico (en la parte que se describe como permanente y, por lo tanto, anclada a la página).

*Ubicación de entrega más* reciente: la ubicación de entrega más reciente es la ubicación donde un correo electrónico aterrizó después de acciones del sistema como ZAP o acciones de administración como Mover a elementos eliminados, finalizar. La ubicación de entrega más reciente no está pensada para informar a los administradores de la ubicación actual *del* mensaje. Por ejemplo, si un usuario elimina un mensaje o lo mueve al archivo, la ubicación de entrega no se actualizará. Sin embargo, si se ha realizado una acción del sistema y se ha actualizado la ubicación (como un ZAP que da como resultado un correo electrónico que pasa a cuarentena), se actualizaría la ubicación de entrega más reciente a Cuarentena.

*Detalles del correo* electrónico: detalles necesarios para comprender mejor el correo electrónico disponible en la *pestaña Análisis.*

- *Reglas de transporte de Exchange (ETR* o reglas de flujo de correo): estas reglas se aplican a un mensaje en la capa de transporte y tienen prioridad sobre los veredictos de suplantación de identidad y correo no deseado. Solo se pueden crear y modificar en el Centro de administración de Exchange, pero si algún ETR se aplica a un mensaje, aquí se mostrarán el nombre de ETR y el GUID. Información valiosa para realizar un seguimiento.
    
- *Invalidaciones del* sistema: se trata de una forma de hacer excepciones a la ubicación de entrega destinada a un mensaje mediante la invalidación de la ubicación de entrega dada por el sistema (según la técnica de amenazas y detección).
    
- *Regla de buzón de* correo no deseado: "Correo no deseado" es una regla de bandeja de entrada oculta que está habilitada de forma predeterminada en todos los buzones.
    - Cuando la regla de correo no deseado está habilitada en el buzón, Exchange Online Protection (EOP) puede mover mensajes a Correo no deseado según algunos criterios. El movimiento puede basarse en la acción de veredicto de filtrado de correo no deseado Mover mensaje a la carpeta *Correo* no deseado o en la lista remitentes bloqueados en el buzón. Si se deshabilita la regla de correo no deseado, se impide la entrega de mensajes a la carpeta de correo no deseado en función de la lista de *remitentes* seguros del buzón.
    - Cuando la regla  de correo no deseado está deshabilitada en el buzón, EOP no puede mover mensajes a la carpeta de correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover mensaje a la carpeta de correo no deseado o la colección de listas seguras del buzón.
    
- *Nivel de cumplimiento masivo (BCL):* el nivel de queja masiva (BCL) del mensaje. Un BCL superior indica que es más probable que un mensaje de correo masivo genere quejas (el resultado natural si es probable que el correo electrónico sea correo no deseado).
    
- Nivel de confianza contra correo no deseado *(SCL):* el nivel de confianza contra correo no deseado (SCL) del mensaje. Un valor superior indica que el mensaje tiene más posibilidades de ser correo no deseado.

- *Nombre de dominio:* es el nombre de dominio del remitente.
    
- *Propietario del* dominio: especifica el propietario del dominio de envío.
    
- *Ubicación del* dominio: especifica la ubicación del dominio de envío.
    
- *Fecha de creación del* dominio: especifica la fecha de creación del dominio de envío. Un dominio recién creado es algo de lo que podrías tener cuidado si otras señales indican algún comportamiento sospechoso.

*Autenticación de* correo electrónico: los métodos de autenticación de correo electrónico usados por Microsoft 365 incluyen SPF, DKIM y DMARC.

- Marco de directivas de remitente **(SPF):** describe los resultados de la comprobación de SPF del mensaje. Los valores posibles pueden ser:
    - Contraseña (dirección IP): se ha pasado la comprobación de SPF del mensaje e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente.
    - Error (dirección IP): error en la comprobación de SPF del mensaje e incluye la dirección IP del remitente. A veces, recibe la denominación "error no recuperable".
    - Softfail (motivo): el registro SPF designó al host como no autorizado para enviar, pero está en transición.
    - Neutro: el registro SPF indica explícitamente que no afirma si la dirección IP está autorizada para enviarse.
    - Ninguno: el dominio no tiene un registro SPF o el registro de SPF no se evalúa como un resultado.
    - Temperror: se ha producido un error temporal. Por ejemplo, un error de DNS. Es posible la misma comprobación sea correcta más tarde.
    - Permerror: se ha producido un error permanente. Por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.

- DomainKeys Identified Mail (**DKIM**):
    - Pass: indica la comprobación DKIM del mensaje pasado.
    - Error (motivo): indica que se ha fallado la comprobación dkim del mensaje y por qué. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma.
    - Ninguno: indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.

- Autenticación, informes y conformidad de mensajes basados en dominio **(DMARC):**
    - Pass: indica la comprobación de DMARC del mensaje pasado.
    - Error: indica que se ha fallado la comprobación de DMARC del mensaje.
    - Bestguesspass: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, la comprobación de DMARC del mensaje habría pasado.
    - Ninguno: indica que no existe ningún registro TXT de DMARC para el dominio de envío en DNS.

*Autenticación* compuesta: Microsoft 365 usa este valor para combinar la autenticación de correo electrónico como SPF, DKIM y DMARC, para determinar si el mensaje es auténtico. Usa el dominio *From:* del correo como base de la evaluación.
