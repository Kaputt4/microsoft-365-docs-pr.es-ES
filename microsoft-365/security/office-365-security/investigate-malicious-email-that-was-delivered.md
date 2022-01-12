---
title: Investigar el correo electrónico malintencionado que se entregó en Microsoft 365, Buscar e investigar correo electrónico malintencionado
keywords: TIMailData-Inline, Security Incident, incident, Microsoft Defender for Endpoint PowerShell, email malware, compromised users, email phish, email malware, read email headers, read headers, open email headers,special actions
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar las capacidades de investigación y respuesta de amenazas para buscar e investigar el correo electrónico malintencionado.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc76f546286597c12469e849eab6e62f9a58a6cc
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61938173"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Investigar el correo electrónico malintencionado que se entregó en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a:**

- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender para Office 365](defender-for-office-365.md) permite investigar actividades que ponen en riesgo a los usuarios de la organización y tomar medidas para proteger su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede buscar e investigar mensajes de correo electrónico sospechosos que se entregaron. Para ello, use el Explorador de amenazas [(o detecciones en](threat-explorer.md)tiempo real).

> [!NOTE]
> Vaya al artículo de corrección [aquí](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que se cumplen los siguientes requisitos:

- Su organización tiene [Microsoft Defender para Office 365](defender-for-office-365.md) y las licencias se asignan a los [usuarios](../../admin/manage/assign-licenses-to-users.md).

- [El registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) está activado para la organización.

- Su organización tiene directivas definidas para correo no deseado, antimalware, anti phishing, y así sucesivamente. Vea [Proteger contra amenazas en Office 365](protect-against-threats.md).

- Es un administrador global o tiene asignado el administrador de seguridad o el rol Buscar y purgar en el portal Microsoft 365 Defender búsqueda. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md). Para algunas acciones, también debe tener asignado el rol Vista previa.

### <a name="preview-role-permissions"></a>Permisos de función de vista previa

Para realizar determinadas acciones, como ver encabezados de mensaje  o descargar contenido de mensajes de correo electrónico, debe agregar el rol Vista previa a otro grupo de roles adecuado. En la tabla siguiente se aclaran los roles y permisos necesarios.

<br>

****

|Actividad|Grupo de funciones|¿Se necesita un rol de vista previa?|
|---|---|---|
|Usar el Explorador de amenazas (y detecciones en tiempo real) para analizar amenazas|Administrador global <p> Administrador de seguridad <p> Lector de seguridad|No|
|Usar el Explorador de amenazas (y detecciones en tiempo real) para ver encabezados de mensajes de correo electrónico, así como obtener una vista previa y descargar mensajes de correo electrónico en cuarentena|Administrador global <p> Administrador de seguridad <p> Lector de seguridad|No|
|Usar el Explorador de amenazas para ver encabezados, obtener una vista previa del correo electrónico (solo en la página de entidad de correo electrónico) y descargar mensajes de correo electrónico entregados a buzones de correo|Administrador global <p> Administrador de seguridad <p> Lector de seguridad <p> Preview|Sí|
|

> [!NOTE]
> **La** vista previa es un rol, no un grupo de funciones. El rol Vista previa debe agregarse a un grupo de roles existente o a un nuevo grupo de roles en el portal de Microsoft 365 Defender funciones. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
>
> El rol Administrador global tiene asignado el Centro de administración de Microsoft 365 en <https://admin.microsoft.com> . Los roles Administrador de seguridad y Lector de seguridad se asignan en Microsoft 365 Defender portal.

Entendemos que la vista previa y la descarga de correo electrónico son actividades confidenciales, por lo que la auditoría está habilitada para estas actividades. Una vez que un administrador realiza estas actividades en el correo electrónico, los registros de auditoría se generan para el mismo y se pueden ver en el portal de Microsoft 365 Defender en la pestaña Búsqueda de auditoría y filtrar el nombre de administrador en el cuadro <https://security.microsoft.com>  \>  Usuarios.  Los resultados filtrados mostrarán la **actividad AdminMailAccess**. Seleccione una fila para ver detalles en la **sección Más información** sobre el correo electrónico descargado o con vista previa.

## <a name="find-suspicious-email-that-was-delivered"></a>Buscar correo electrónico sospechoso que se entregó

El Explorador de amenazas es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una investigación posterior. El siguiente procedimiento se centra en el uso del Explorador para buscar y eliminar correo electrónico malintencionado de los buzones de correo del destinatario.

> [!NOTE]
> Actualmente, las búsquedas predeterminadas en el Explorador no incluyen elementos entregados que se quitaron del buzón de correo en la nube mediante la purga automática de cero horas (ZAP). Esta limitación se aplica a todas las vistas (por ejemplo, las vistas **\> Malware de correo** electrónico o **\> Suplantación de identidad** de correo electrónico). Para incluir elementos eliminados por ZAP, debe agregar un conjunto de acciones **de** entrega para incluir **Removed by ZAP**. Si incluye todas las opciones, verá todos los resultados de la acción de entrega, incluidos los elementos eliminados por ZAP.

1. En el portal Microsoft 365 Defender en <https://security.microsofot.com> , vaya a Correo electrónico & explorador de  \> **colaboración** . Para ir directamente a la **página Explorador,** use <https://security.microsoft.com/threatexplorer> .

   En la **página Explorador,** la **columna Acciones adicionales** muestra a los administradores el resultado del procesamiento de un correo electrónico. Se **puede tener acceso** a la columna Acciones adicionales en el mismo lugar que Acción de **entrega** y Ubicación **de entrega.** Las acciones especiales pueden actualizarse al final de la escala de tiempo de correo electrónico del Explorador de amenazas, que es una nueva característica destinada a mejorar la experiencia de búsqueda para los administradores.

2. En el **menú Ver,** elija **Correo electrónico** todo \> **el correo** electrónico de la lista desplegable.

    ![Menú Vista del explorador de amenazas y Correo electrónico: malware, phish, envíos y todas las opciones de correo electrónico, también contenido : malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    La *vista Malware* es actualmente el valor predeterminado y captura correos electrónicos donde se detecta una amenaza de malware. La *vista Phish* funciona de la misma manera, para phishing.

    Sin embargo, *todas las vistas* de correo electrónico enumeran todos los correos recibidos por la organización, independientemente de si se detectaron o no amenazas. Como puede imaginar, se trata de una gran cantidad de datos, por lo que esta vista muestra un marcador de posición que pide que se aplique un filtro. (Esta vista solo está disponible para Defender para Office 365 clientes de P2).

    *La vista Envíos* muestra todos los correos enviados por el administrador o el usuario que se han notificado a Microsoft.

4. **Buscar y filtrar en el Explorador de** amenazas: los filtros aparecen en la parte superior de la página en la barra de búsqueda para ayudar a los administradores en sus investigaciones. Observe que se pueden aplicar varios filtros al mismo tiempo y se agregan varios valores separados por comas a un filtro para restringir la búsqueda. Recuerde:

    - Los filtros coinciden exactamente en la mayoría de las condiciones de filtro.
    - El filtro de asunto usa una consulta CONTAINS.
    - Los filtros de dirección URL funcionan con o sin protocolos (por ejemplo. https).
    - El dominio de dirección URL, la ruta de acceso url y los filtros de dominio y ruta de acceso url no requieren un protocolo para filtrar.
    - Debe hacer clic en el icono Actualizar cada vez que cambie los valores de filtro para obtener resultados relevantes.

5. **Filtros avanzados:** con estos filtros, puede crear consultas complejas y filtrar el conjunto de datos. Al hacer *clic en Filtros avanzados,* se abre un control desplegable con opciones.

   El filtrado avanzado es una gran adición a las capacidades de búsqueda. Un valor BOOLEAN NOT en los filtros **de dominio Recipient**, **Sender** y **Sender** permite a los administradores investigar excluyendo valores. Esta opción es **igual a ninguna de la** selección. Esta opción permite a los administradores excluir buzones no deseados de investigaciones (por ejemplo, buzones de alerta y buzones de respuesta predeterminados) y resulta útil para los casos en los que los administradores buscan un asunto específico (por ejemplo, Atención) donde el destinatario puede establecerse en Igual a ninguno *de: defaultMail@contoso.com*. Se trata de una búsqueda de valor exacto.

   ![El filtro Destinatarios: "No contiene ninguno de" Avanzado.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Agregar un filtro de hora a la fecha de inicio y la fecha de finalización ayuda al equipo de seguridad a profundizar rápidamente. La duración de tiempo permitida más corta es de 30 minutos. Si puede restringir la acción sospechosa por período de tiempo (por ejemplo, ocurrió hace 3 horas), esto limitará el contexto y ayudará a identificar el problema.

   ![La opción de filtrado por horas para restringir la cantidad de equipos de seguridad de datos tiene que procesarse y cuya duración más corta es de 30 minutos.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campos en el** Explorador de amenazas: el Explorador de amenazas expone mucha más información de correo relacionada con la seguridad, como Acción de *entrega,* Ubicación de entrega *,* *Acción* especial , *Direccionalidad,* Invalidaciones y amenaza de *dirección URL.*  También permite que el equipo de seguridad de la organización investigue con mayor certeza.

    *La acción de* entrega es la acción realizada en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que un correo electrónico puede realizar:

    - **Entregado:** el correo electrónico se entregó a la bandeja de entrada o carpeta de un usuario y el usuario puede acceder directamente a él.
    - **Correo no** deseado (entregado a la correo no deseado): el correo electrónico se envió a la carpeta de correo no deseado del usuario o a la carpeta eliminada y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta Correo no deseado o Eliminado.
    - **Bloqueado:** cualquier mensaje de correo electrónico que se ponga en cuarentena, que falle o que se haya descartado.
    - **Reemplazado:** cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por .txt que los datos adjuntos son malintencionados.

    **Ubicación de** entrega: el filtro ubicación de entrega está disponible para ayudar a los administradores a comprender dónde terminó el correo malintencionado sospechoso y qué acciones se llevaron a cabo en él. Los datos resultantes se pueden exportar a hoja de cálculo. Las ubicaciones de entrega posibles son:

    - **Bandeja de entrada o carpeta:** el correo electrónico está en la Bandeja de entrada o en una carpeta específica, según las reglas de correo electrónico.
    - **Local o externo:** el buzón no existe en la nube, pero es local.
    - **Carpeta de correo** no deseado: el correo electrónico está en la carpeta de correo no deseado de un usuario.
    - **Carpeta Elementos eliminados:** el correo electrónico se encuentra en la carpeta Elementos eliminados de un usuario.
    - **Cuarentena:** el correo electrónico en cuarentena y no en el buzón de un usuario.
    - **Error:** el correo electrónico no pudo llegar al buzón.
    - **Eliminado:** el correo electrónico se perdió en algún lugar del flujo de correo.

    **Direccionalidad:** esta opción permite al equipo de operaciones de seguridad filtrar por la "dirección" de la que proviene o va el correo. Los valores de direccionalidad son *Entrantes,* Salientes e *Intra-org* (correspondientes a correo que entra en la organización desde fuera, se envía fuera de la organización o se envía internamente a su organización, respectivamente). Esta información puede ayudar a los equipos de operaciones de seguridad a detectar la suplantación y la suplantación, ya que existe un error de coincidencia entre el valor de direccionalidad (por ejemplo. *Entrante*) y el dominio del remitente *(que* parece ser un dominio interno) será evidente. El valor de direccionalidad es independiente y puede diferir del seguimiento de mensajes. Los resultados se pueden exportar a una hoja de cálculo.

    **Invalidaciones:** este filtro toma la información que aparece en la pestaña detalles del correo y la usa para exponer dónde se han invalidado las directivas de usuario o organizativas para permitir y bloquear *correos.* Lo más importante de este filtro es que ayuda al equipo de seguridad de la organización a ver cuántos correos electrónicos sospechosos se entregaron debido a la configuración. Esto les da la oportunidad de modificar los bloques y los permite según sea necesario. Este conjunto de resultados de este filtro se puede exportar a la hoja de cálculo.

    <br>

    ****

    |Invalidaciones del Explorador de amenazas|Qué significan|
    |---|---|
    |Permitido por la directiva de organización|El correo se permitió en el buzón según lo indicado por la directiva de la organización.|
    |Directiva de organización bloqueada|El correo se bloqueó para que no se entregara al buzón según lo indicado por la directiva de la organización.|
    |Extensión de archivo bloqueada por la directiva de organización|El archivo se bloqueó para que no se entregara al buzón según lo indicado por la directiva de la organización.|
    |Permitido por la directiva de usuario|El correo se permitió en el buzón según lo indicado por la directiva de usuario.|
    |Bloqueado por la directiva de usuario|El correo se bloqueó para que no se entregara al buzón según lo indicado por la directiva de usuario.|
    |

    **Amenaza de dirección URL:** el campo  Amenaza de dirección URL se ha incluido en la pestaña detalles de un correo electrónico para indicar la amenaza presentada por una dirección URL. Las amenazas presentadas por una dirección URL pueden incluir *Malware,* *Phish* o *Spam,* y una dirección URL *sin* amenaza dirá *None* en la sección amenazas.

7. **Vista escala de tiempo de** correo electrónico: es posible que el equipo de operaciones de seguridad necesite profundizar en los detalles del correo electrónico para investigar más. La escala de tiempo de correo electrónico permite a los administradores ver las acciones realizadas en un correo electrónico desde la entrega hasta la posterior a la entrega. Para ver una escala de tiempo de correo electrónico, haga clic en el asunto de un mensaje de correo electrónico y, a continuación, haga clic en Escala de tiempo de correo electrónico. (Aparece entre otros encabezados en el panel como Resumen o Detalles). Estos resultados se pueden exportar a una hoja de cálculo.

    La escala de tiempo del correo electrónico se abrirá en una tabla que muestra todos los eventos de entrega y posterior a la entrega del correo electrónico. Si no hay más acciones en el correo electrónico, debería ver un solo evento para la entrega original que indica un resultado, como *Blocked*, con un veredicto como *Phish*. Los administradores pueden exportar toda la escala de tiempo del correo electrónico, incluidos todos los detalles de la pestaña y el correo electrónico (por ejemplo, Asunto, Remitente, Destinatario, Red e Id. de mensaje). La escala de tiempo de correo electrónico reduce la aleatorización porque hay menos tiempo dedicado a comprobar diferentes ubicaciones para intentar comprender los eventos que han ocurrido desde que llegó el correo electrónico. Cuando se suceden varios eventos al mismo tiempo o cerca de ellos en un correo electrónico, estos eventos se muestran en una vista de escala de tiempo.

8. **Vista previa o descarga:** el Explorador de amenazas proporciona al equipo de operaciones de seguridad los detalles que necesitan para investigar el correo electrónico sospechoso. El equipo de operaciones de seguridad puede:

    - [Compruebe la acción de entrega y la ubicación](#check-the-delivery-action-and-location).

    - [Ver la escala de tiempo del correo electrónico](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Comprobar la acción de entrega y la ubicación

En [el Explorador de amenazas (y](threat-explorer.md)detecciones en  tiempo real), ahora tiene columnas De acción de entrega y Ubicación de entrega en lugar de la columna Estado **de entrega** anterior.  Esto da como resultado una imagen más completa de dónde aterrizan los mensajes de correo electrónico. Parte del objetivo de este cambio es facilitar las investigaciones a los equipos de operaciones de seguridad, pero el resultado neto es conocer de un vistazo la ubicación de los mensajes de correo electrónico con problemas.

El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega:** ¿cuál es el estado de este correo electrónico?
- **Ubicación de entrega:** ¿dónde se enrutó este correo electrónico como resultado?

La acción de entrega es la acción realizada en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que un correo electrónico puede realizar:

- **Entregado:** el correo electrónico se entregó a la bandeja de entrada o carpeta de un usuario y el usuario puede acceder directamente a él.
- **Junked:** el correo electrónico se envió a la carpeta de correo no deseado del usuario o a la carpeta eliminada y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta Correo no deseado o Eliminado.
- **Bloqueado:** cualquier mensaje de correo electrónico que se ponga en cuarentena, que falle o que se haya descartado.
- **Reemplazado:** cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan .txt los archivos adjuntos que den a los datos adjuntos son malintencionados.

La ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción realizada cuando se encuentra un correo con problemas. Estos son los posibles valores de la ubicación de entrega:

- **Bandeja de entrada o carpeta:** el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
- **Local o externo:** el buzón no existe en la nube, pero es local.
- **Carpeta de correo** no deseado: el correo electrónico está en la carpeta de correo no deseado de un usuario.
- **Carpeta Elementos eliminados:** el correo electrónico se encuentra en la carpeta Elementos eliminados de un usuario.
- **Cuarentena:** el correo electrónico en cuarentena y no en el buzón de un usuario.
- **Error:** el correo electrónico no pudo llegar al buzón.
- **Eliminado:** el correo electrónico se pierde en algún lugar del flujo de correo.

### <a name="view-the-timeline-of-your-email"></a>Ver la escala de tiempo del correo electrónico

**La escala de tiempo de** correo electrónico es un campo en el Explorador de amenazas que facilita la búsqueda del equipo de operaciones de seguridad. Cuando se suceden varios eventos al mismo tiempo o cerca de él en un correo electrónico, estos eventos se muestran en una vista de escala de tiempo. Algunos eventos que se suceden después de la entrega al correo electrónico se capturan en la **columna Acciones** especiales. La combinación de información de la escala de tiempo de un mensaje de correo electrónico con cualquier acción especial que se llevara a cabo después de la entrega proporciona a los administradores información sobre las directivas y el tratamiento de amenazas (por ejemplo, dónde se enrutó el correo y, en algunos casos, cuál era la evaluación final).

> [!IMPORTANT]
> Vaya a un tema de corrección [aquí](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Temas relacionados

[Corregir el correo electrónico malintencionado entregado en Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender para Office 365](office-365-ti.md)

[Proteger contra amenazas en Office 365](protect-against-threats.md)

[Ver informes de Defender para Office 365](view-reports-for-mdo.md)
