---
title: Investigar el correo electrónico malintencionado que se entregó en Microsoft 365, buscar e investigar correo electrónico malintencionado
keywords: TIMailData-Inline, Security Incident, incident, Microsoft Defender para punto de conexión PowerShell, email malware, compromised users, email phish, email malware, read email headers, read headers, open email headers,special actions
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- m365-security
description: Obtenga información sobre cómo usar las funcionalidades de investigación y respuesta de amenazas para buscar e investigar correo electrónico malintencionado.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 51060efdb350147364d5df6aa20d7d7ccb7817d8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628497"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Investigación del correo electrónico malintencionado que se entregó en Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**

- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender para Office 365](defender-for-office-365.md) le permite investigar actividades que ponen en riesgo a las personas de su organización y tomar medidas para proteger su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar mensajes de correo electrónico sospechosos que se entregaron. Para ello, use [el Explorador de amenazas (o las detecciones en tiempo real).](threat-explorer.md)

> [!NOTE]
> Vaya al artículo de corrección [aquí](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que se cumplen los siguientes requisitos:

- Su organización tiene [Microsoft Defender para Office 365](defender-for-office-365.md) y [las licencias se asignan a los usuarios](../../admin/manage/assign-licenses-to-users.md).

- [El registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) está activado para su organización.

- Su organización tiene directivas definidas para antispam, antimalware, anti phishing, etc. Consulte [Protección contra amenazas en Office 365](protect-against-threats.md).

- Es un administrador global o tiene asignado el rol Administrador de seguridad o Buscar y purgar en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md). Para algunas acciones, también debe tener asignado el rol Vista previa.

### <a name="preview-role-permissions"></a>Permisos de rol en versión preliminar

Para realizar determinadas acciones, como ver encabezados de mensaje o descargar contenido de mensajes de correo electrónico, debe tener el rol *Vista previa* agregado a otro grupo de roles adecuado. En la tabla siguiente se aclaran los roles y permisos necesarios.

|Actividad|Grupo de funciones|¿Se necesita un rol de versión preliminar?|
|---|---|---|
|Uso del Explorador de amenazas (y detecciones en tiempo real) para analizar amenazas|Administrador global <p> Administrador de seguridad <p> Lector de seguridad|No|
|Use el Explorador de amenazas (y las detecciones en tiempo real) para ver los encabezados de los mensajes de correo electrónico, así como obtener una vista previa y descargar los mensajes de correo electrónico en cuarentena.|Administrador global <p> Administrador de seguridad <p> Lector de seguridad|No|
|Use el Explorador de amenazas para ver encabezados, obtener una vista previa del correo electrónico (solo en la página de la entidad de correo electrónico) y descargar los mensajes de correo electrónico entregados a los buzones.|Administrador global <p> Administrador de seguridad <p> Lector de seguridad <p> Preview|Sí|

> [!NOTE]
> **La versión preliminar** es un rol, no un grupo de roles. El rol de versión preliminar debe agregarse a un grupo de roles existente o a un nuevo grupo de roles en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
>
> Al rol administrador global se le asigna el Centro de administración de Microsoft 365 en <https://admin.microsoft.com>. Los roles Administrador de seguridad y Lector de seguridad se asignan en Microsoft 365 Defender portal.

Entendemos que la vista previa y la descarga de correo electrónico son actividades confidenciales, por lo que la auditoría está habilitada para estas actividades. Una vez que un administrador realiza estas actividades por correo electrónico, los registros de auditoría se generan para el mismo modo y se pueden ver en el portal de Microsoft 365 Defender en la <https://security.microsoft.com> pestaña **Búsqueda** de **auditoría** \> y filtrar por el nombre del administrador en el cuadro **Usuarios**. Los resultados filtrados mostrarán la actividad **AdminMailAccess**. Seleccione una fila para ver los detalles en la sección **Más información** sobre el correo electrónico en versión preliminar o descargado.

## <a name="find-suspicious-email-that-was-delivered"></a>Búsqueda de correo electrónico sospechoso que se ha entregado

El Explorador de amenazas es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una investigación posterior. El siguiente procedimiento se centra en el uso del Explorador para buscar y eliminar correo electrónico malintencionado de los buzones de correo del destinatario.

> [!NOTE]
> Las búsquedas predeterminadas en el Explorador no incluyen actualmente elementos entregados que se quitaron del buzón de correo en la nube mediante la purga automática de cero horas (ZAP). Esta limitación se aplica a todas las vistas (por ejemplo, las vistas **Email \> Malware** o **Email \> Phish**). Para incluir elementos quitados por ZAP, debe agregar una **acción de entrega** establecida para incluir **Eliminado por ZAP**. Si incluye todas las opciones, verá todos los resultados de la acción de entrega, incluidos los elementos eliminados por ZAP.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & **explorador** **de colaboración** \> . Para ir directamente a la página **Explorador** , use <https://security.microsoft.com/threatexplorer>.

   En la página **Explorador** , la columna **Acciones adicionales** muestra a los administradores el resultado del procesamiento de un correo electrónico. Se puede acceder a la columna **Acciones adicionales** en el mismo lugar que **Acción de entrega** y **Ubicación de entrega**. Las acciones especiales pueden actualizarse al final de la escala de tiempo del correo electrónico del Explorador de amenazas, que es una nueva característica destinada a mejorar la experiencia de búsqueda para los administradores.

2. En el menú **Ver**, elija **Email** \> **Todos los correos electrónicos** de la lista desplegable.

    :::image type="content" source="../../media/tp-InvestigateMalEmail-viewmenu.png" alt-text="Lista desplegable Malware" lightbox="../../media/tp-InvestigateMalEmail-viewmenu.png":::

    La vista *Malware* es actualmente la predeterminada y captura los correos electrónicos en los que se detecta una amenaza de malware. La vista *phish* funciona de la misma manera, para Phish.

    Sin embargo, *en la vista Todos los correos electrónicos* se muestra cada correo recibido por la organización, independientemente de si se detectaron amenazas o no. Como se puede imaginar, se trata de una gran cantidad de datos, por lo que esta vista muestra un marcador de posición que solicita que se aplique un filtro. (Esta vista solo está disponible para Defender para Office 365 clientes de P2).

    *La vista Envíos* muestra todos los correos enviados por el administrador o usuario que se notificaron a Microsoft.

4. **Buscar y filtrar en el Explorador de amenazas**: los filtros aparecen en la parte superior de la página de la barra de búsqueda para ayudar a los administradores en sus investigaciones. Observe que se pueden aplicar varios filtros al mismo tiempo y se agregan varios valores separados por comas a un filtro para restringir la búsqueda. Recuerde:

    - Los filtros hacen coincidencias exactas en la mayoría de las condiciones de filtro.
    - El filtro subject usa una consulta CONTAINS.
    - Los filtros url funcionan con o sin protocolos (por ejemplo, https).
    - Los filtros de dominio, ruta de dirección URL y dominio y ruta de acceso de dirección URL no requieren un protocolo para filtrar.
    - Debe hacer clic en el icono Actualizar cada vez que cambie los valores de filtro para obtener los resultados pertinentes.

5. **Filtros avanzados**: con estos filtros, puede crear consultas complejas y filtrar el conjunto de datos. Al hacer clic en *Filtros avanzados* , se abre un control flotante con opciones.

   El filtrado avanzado es una gran adición a las funcionalidades de búsqueda. Un valor booleano NOT en los filtros de **dominio** **Destinatario**, **Remitente** y Remitente permite a los administradores investigar mediante la exclusión de valores. Esta opción es **igual a ninguna selección** . Esta opción permite a los administradores excluir buzones no deseados de investigaciones (por ejemplo, buzones de alerta y buzones de respuesta predeterminados) y es útil para los casos en los que los administradores buscan un asunto específico (por ejemplo, Atención) donde el destinatario se puede establecer en *Igual a ninguno de: defaultMail@contoso.com*. Se trata de una búsqueda de valores exacta.

   :::image type="content" source="../../media/tp-InvestigateMalEmail-AdvancedFilter.png" alt-text="Panel Destinatarios" lightbox="../../media/tp-InvestigateMalEmail-AdvancedFilter.png":::

   Agregar un filtro de hora a la fecha de inicio y la fecha de finalización ayuda al equipo de seguridad a explorar en profundidad rápidamente. La duración de tiempo más corta permitida es de 30 minutos. Si puede restringir la acción sospechosa por período de tiempo (por ejemplo, ocurrió hace 3 horas), esto limitará el contexto y ayudará a identificar el problema.

   :::image type="content" source="../../media/tp-InvestigateMalEmail-FilterbyHours.png" alt-text="Opción de filtrado por horas" lightbox="../../media/tp-InvestigateMalEmail-FilterbyHours.png":::

6. **Campos en el Explorador de amenazas**: el Explorador de amenazas expone mucha más información de correo relacionada con la seguridad, como *la acción de entrega*, *la ubicación de entrega*, la *acción especial*, *la direccionalidad*, *las invalidaciones y la* *amenaza de dirección URL*. También permite que el equipo de seguridad de la organización investigue con mayor certeza.

    *La acción de entrega* es la acción realizada en un correo electrónico debido a directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

    - **Entregado** : el correo electrónico se entregó en la bandeja de entrada o carpeta de un usuario y el usuario puede acceder directamente a él.
    - **Correo no** deseado (entregado a correo no deseado): el correo electrónico se envió a la carpeta de correo no deseado del usuario o a la carpeta eliminada, y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta No deseado o Eliminado.
    - **Bloqueado** : todos los mensajes de correo electrónico que están en cuarentena, que han producido un error o que se han quitado.
    - **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por .txt archivos que indican que los datos adjuntos eran malintencionados

    **Ubicación de entrega**: el filtro Ubicación de entrega está disponible para ayudar a los administradores a comprender dónde terminó el correo malintencionado sospechoso y qué acciones se realizaron en él. Los datos resultantes se pueden exportar a la hoja de cálculo. Las posibles ubicaciones de entrega son:

    - **Bandeja de entrada o carpeta** : el correo electrónico está en la Bandeja de entrada o en una carpeta específica, de acuerdo con las reglas de correo electrónico.
    - **Local o externo** : el buzón no existe en la nube, pero es local.
    - **Carpeta no deseada** : el correo electrónico está en la carpeta correo no deseado de un usuario.
    - **Carpeta elementos eliminados** : el correo electrónico está en la carpeta Elementos eliminados de un usuario.
    - **Cuarentena** : el correo electrónico en cuarentena y no en el buzón de un usuario.
    - **Error** : el correo electrónico no alcanzó el buzón.
    - **Eliminado** : el correo electrónico se perdió en algún lugar del flujo de correo.

    **Direccionalidad**: esta opción permite que el equipo de operaciones de seguridad filtre por la "dirección" de la que proviene un correo o que va. Los valores de direccionalidad son *Inbound*, *Outbound* e *Intra-org* (correspondientes al correo que llega a su organización desde fuera, que se envía fuera de su organización o que se envía internamente a su organización, respectivamente). Esta información puede ayudar a los equipos de operaciones de seguridad a detectar suplantación y suplantación de suplantación, ya que no coinciden entre el valor de direccionalidad (por ejemplo, *Entrante*) y el dominio del remitente (que *parece* ser un dominio interno) será evidente. El valor Directionality es independiente y puede diferir del seguimiento de mensajes. Los resultados se pueden exportar a la hoja de cálculo.

    **Invalidaciones**: este filtro toma información que aparece en la pestaña de detalles del correo y la usa para exponer dónde se han *invalidado* las directivas de organización o de usuario para permitir y bloquear correos. Lo más importante de este filtro es que ayuda al equipo de seguridad de su organización a ver cuántos correos electrónicos sospechosos se entregaron debido a la configuración. Esto les ofrece la oportunidad de modificar los bloques y los permite según sea necesario. Este conjunto de resultados de este filtro se puede exportar a la hoja de cálculo.

    |Invalidaciones del Explorador de amenazas|¿Qué significan?|
    |---|---|
    |Permitido por la directiva de la organización|Se permitió el correo en el buzón según lo indicado por la directiva de la organización.|
    |Bloqueado por la directiva de la organización|Se ha bloqueado la entrega del correo al buzón según lo indicado por la directiva de la organización.|
    |Extensión de archivo bloqueada por la directiva de organización|Se bloqueó la entrega del archivo al buzón según lo indicado por la directiva de la organización.|
    |Permitido por la directiva de usuario|Se permitió el correo en el buzón según lo indicado por la directiva de usuario.|
    |Bloqueado por la directiva de usuario|Se ha bloqueado la entrega del correo al buzón según lo indicado por la directiva de usuario.|

    **Amenaza de dirección URL**: el campo Amenaza de dirección URL se ha incluido en la pestaña *de detalles* de un correo electrónico para indicar la amenaza presentada por una dirección URL. Las amenazas presentadas por una dirección URL pueden incluir *Malware*, *Phish* o *Spam*, y una dirección URL *sin amenaza* indicará *None* en la sección de amenazas.

7. **Email vista de escala de tiempo**: es posible que el equipo de operaciones de seguridad tenga que profundizar en los detalles del correo electrónico para investigar más a fondo. La escala de tiempo del correo electrónico permite a los administradores ver las acciones realizadas en un correo electrónico desde la entrega hasta la entrega posterior. Para ver una escala de tiempo de correo electrónico, haga clic en el asunto de un mensaje de correo electrónico y, a continuación, haga clic en Email escala de tiempo. (Aparece entre otros encabezados del panel, como Resumen o Detalles). Estos resultados se pueden exportar a una hoja de cálculo.

    Email escala de tiempo se abrirá en una tabla que muestra todos los eventos de entrega y posterior a la entrega del correo electrónico. Si no hay más acciones en el correo electrónico, debería ver un único evento para la entrega original que indique un resultado, como *Bloqueado*, con un veredicto como *Phish*. Los administradores pueden exportar toda la escala de tiempo del correo electrónico, incluidos todos los detalles de la pestaña y el correo electrónico (por ejemplo, Asunto, Remitente, Destinatario, Red e Id. de mensaje). La escala de tiempo del correo electrónico reduce la aleatoriedad porque se dedica menos tiempo a comprobar las distintas ubicaciones para intentar comprender los eventos que han ocurrido desde que llegó el correo electrónico. Cuando se producen varios eventos al mismo tiempo en un correo electrónico, o cerca de ellos, esos eventos se muestran en una vista de escala de tiempo.

8. **Versión preliminar o descarga**: El Explorador de amenazas proporciona al equipo de operaciones de seguridad los detalles que necesitan para investigar el correo electrónico sospechoso. El equipo de operaciones de seguridad puede:

    - [Compruebe la acción de entrega y la ubicación](#check-the-delivery-action-and-location).

    - [Vea la escala de tiempo del correo electrónico](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Comprobar la acción de entrega y la ubicación

En [el Explorador de amenazas (y detecciones en tiempo real),](threat-explorer.md) ahora tiene columnas **Acción de entrega** y **Ubicación de entrega** en lugar de la columna Estado de **entrega** anterior. Esto da como resultado una imagen más completa de dónde llegan los mensajes de correo electrónico. Parte del objetivo de este cambio es facilitar las investigaciones a los equipos de operaciones de seguridad, pero el resultado neto es conocer la ubicación de los mensajes de correo electrónico problemáticos de un vistazo.

El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?
- **Ubicación de entrega** : ¿dónde se enrutó este correo electrónico como resultado?

La acción de entrega es la acción realizada en un correo electrónico debido a directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

- **Entregado** : el correo electrónico se entregó en la bandeja de entrada o carpeta de un usuario y el usuario puede acceder directamente a él.
- **Correo no deseado** : el correo electrónico se envió a la carpeta de correo no deseado del usuario o a la carpeta eliminada, y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta Correo no deseado o Eliminado.
- **Bloqueado** : todos los mensajes de correo electrónico que están en cuarentena, que han producido un error o que se han quitado.
- **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por .txt archivos que indican que los datos adjuntos eran malintencionados.

La ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se ha agregado para proporcionar información sobre la acción realizada cuando se encuentra un correo con problemas. Estos son los valores posibles de la ubicación de entrega:

- **Bandeja de entrada o carpeta** : el correo electrónico está en la bandeja de entrada o en una carpeta (de acuerdo con las reglas de correo electrónico).
- **Local o externo** : el buzón no existe en la nube, pero es local.
- **Carpeta no deseada** : el correo electrónico está en la carpeta No deseado de un usuario.
- **Carpeta elementos eliminados** : el correo electrónico está en la carpeta Elementos eliminados de un usuario.
- **Cuarentena** : el correo electrónico en cuarentena y no en el buzón de un usuario.
- **Error** : el correo electrónico no alcanzó el buzón.
- **Eliminado** : el correo electrónico se pierde en algún lugar del flujo de correo.

### <a name="view-the-timeline-of-your-email"></a>Visualización de la escala de tiempo del correo electrónico

**Email Escala de tiempo** es un campo del Explorador de amenazas que facilita la búsqueda al equipo de operaciones de seguridad. Cuando se producen varios eventos a la misma hora o al mismo tiempo en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos eventos que se producen después de la entrega al correo electrónico se capturan en la columna **Acciones especiales** . La combinación de información de la escala de tiempo de un mensaje de correo electrónico con las acciones especiales que se realizaron después de la entrega proporciona a los administradores información sobre las directivas y el control de amenazas (por ejemplo, dónde se enrutó el correo y, en algunos casos, cuál era la evaluación final).

> [!IMPORTANT]
> Vaya a un tema de corrección [aquí](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Temas relacionados

[Corregir el correo electrónico malintencionado entregado en Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender para Office 365](office-365-ti.md)

[Protección contra amenazas en Office 365](protect-against-threats.md)

[Ver informes para Defender para Office 365](view-reports-for-mdo.md)
