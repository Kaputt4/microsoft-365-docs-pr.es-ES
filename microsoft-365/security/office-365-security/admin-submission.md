---
title: Administrar envíos
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal envíos en el portal de Microsoft 365 Defender para enviar correo electrónico legítimo bloqueado, correo electrónico sospechoso, sospecha de correo electrónico de phishing, correo no deseado, otros mensajes potencialmente dañinos, direcciones URL y datos adjuntos de correo electrónico a Microsoft para volver a examinar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 17083a248e31d5ae1eff3c088497f071bcac643b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639454"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-legitimate-email-getting-blocked-and-email-attachments-to-microsoft"></a>Use el portal envíos para enviar sospechas de correo no deseado, mensajes no deseados, direcciones URL, bloqueo de correo electrónico legítimo y datos adjuntos de correo electrónico a Microsoft.

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online, los administradores pueden usar el portal envíos del portal de Microsoft 365 Defender para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su examen.

Cuando envíe un mensaje de correo electrónico para su análisis, obtendrá lo siguiente:

- **Comprobación de autenticación por correo electrónico**: detalles sobre si se ha pasado o no la autenticación por correo electrónico cuando se ha entregado.
- **Aciertos de directiva**: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en el inquilino, reemplazando nuestros veredictos de filtro de servicio.
- **Reputación o detonación de carga**: examen actualizado de las direcciones URL y los datos adjuntos del mensaje.
- **Análisis de calificador**: revisión realizada por calificadores humanos con el fin de confirmar si los mensajes son malintencionados o no.

> [!IMPORTANT]
> La reputación/detonación de carga útil y el análisis de calificador no se realizan en todos los inquilinos. Se impide que la información salga de la organización cuando se supone que los datos no deben salir del límite del inquilino con fines de cumplimiento.

Para obtener otras maneras de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

Vea este breve vídeo para aprender a usar envíos de administrador en Microsoft Defender para Office 365 para enviar mensajes a Microsoft para su evaluación.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBLPn]

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

- Para enviar mensajes y archivos a Microsoft, debe tener uno de los siguientes roles:
  - **Administrador de seguridad** o **Lector de seguridad** en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

    Tenga en cuenta que uno de estos roles es necesario para [ver los envíos de usuarios al buzón personalizado](#view-user-submissions-to-microsoft) , como se describe más adelante en este artículo.

- Los administradores pueden enviar mensajes con una antigüedad de 30 días si siguen estando disponibles en el buzón y no purgados por el usuario u otro administrador.

- Administración envíos están limitados a las siguientes tarifas:
  - Número máximo de envíos en un período de 15 minutos: 150 envíos
  - Los mismos envíos en un período de 24 horas: 3 envíos
  - Los mismos envíos en un período de 15 minutos: 1 envío

- Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Informar de contenido sospechoso a Microsoft

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** o **Datos adjuntos** o **direcciones URL**  de correo electrónico está seleccionada en función del tipo de contenido que desea informar y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para análisis** que parece enviar el tipo de contenido correspondiente (correo electrónico, dirección URL o datos adjuntos de correo electrónico), tal como se describe en las secciones siguientes.

   > [!NOTE]
   > Los envíos de archivos y direcciones URL no están disponibles en las nubes que no permiten que los datos salgan del entorno. La capacidad de seleccionar Archivo o DIRECCIÓN URL se atenuará.

### <a name="notify-users-from-within-the-portal"></a>Notificar a los usuarios desde el portal

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Correo electrónico &** **envíos de** colaboración\>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione **la pestaña Mensajes notificados** por el usuario y, a continuación, seleccione el mensaje que desea marcar y notificar.

3. Seleccione la lista desplegable **Marcar como y notificar** y, a continuación, seleccione **No se encontró** \> amenazas **phishing o** **correo no deseado**.

   :::image type="content" source="../../media/unified-submission-user-reported-message.png" alt-text="Página Envíos" lightbox="../../media/unified-submission-user-reported-message.png":::

El mensaje notificado se marcará como falso positivo o falso negativo. Una notificación por correo electrónico se envía automáticamente desde el portal al usuario que ha notificado el mensaje.

### <a name="submit-a-questionable-email-to-microsoft"></a>Envío de un correo electrónico cuestionable a Microsoft

1. En el cuadro **Seleccionar el tipo de envío** , compruebe que **Correo electrónico** está seleccionado en la lista desplegable.

2. En la sección **Agregar el identificador de mensaje de red o cargar el archivo de correo electrónico** , use una de las siguientes opciones:
   - **Agregar el identificador de mensaje de red de correo electrónico**: se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en los mensajes en cuarentena.
   - **Cargar el archivo de correo electrónico (.msg o .eml):** haga clic en **Examinar archivos**. En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.

3. En el cuadro **Choose a recipient who had an issue (Elegir un destinatario que tenía un problema** ), especifique el destinatario en el que desea ejecutar una comprobación de directiva. La comprobación de directiva determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.

4. En la sección **Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No se debería haber bloqueado (Falso positivo)**
   - **Se debería haber bloqueado (Falso negativo):** en la sección **Se debería haber clasificado el correo electrónico como** que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**
     - **Correo no deseado**

5. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-flyout-email.png" alt-text="El proceso de envío de nueva dirección URL" lightbox="../../media/submission-flyout-email.png":::

### <a name="send-a-suspect-url-to-microsoft"></a>Envío de una dirección URL sospechosa a Microsoft

1. En el cuadro **Seleccionar el tipo de envío** , seleccione **DIRECCIÓN URL** en la lista desplegable.

2. En el cuadro **URL** que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html`).

3. En la sección **Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No se debería haber bloqueado (Falso positivo)**
   - **Debería haberse bloqueado (Falso negativo):** en la sección **Esta dirección URL debería haberse clasificado como** que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**

4. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-url-flyout.png" alt-text="El nuevo proceso de envío de correo electrónico" lightbox="../../media/submission-url-flyout.png":::

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Envío de un archivo adjunto de correo electrónico sospechoso a Microsoft

1. En el cuadro **Seleccionar el tipo de envío** , seleccione **Datos adjuntos de correo electrónico** en la lista desplegable.

2. En la sección **Archivo** que aparece, haga clic en **Examinar archivos**. En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.

3. En la sección **Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No se debería haber bloqueado (Falso positivo)**
   - **Se debería haber bloqueado (Falso negativo):** en la sección **Este archivo debería haberse clasificado como** que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**

4. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-file-flyout.png" alt-text="El proceso de envío de nuevos datos adjuntos" lightbox="../../media/submission-file-flyout.png":::

> [!NOTE]
> Si el filtrado de malware ha reemplazado los datos adjuntos del mensaje por el archivo de Text.txt de alerta de malware, debe enviar el mensaje original de la cuarentena que contiene los datos adjuntos originales. Para obtener más información sobre la cuarentena y cómo liberar mensajes con falsos positivos de malware, consulte [Administración de mensajes y archivos en cuarentena como administrador](manage-quarantined-messages-and-files.md).

## <a name="view-email-admin-submissions-to-microsoft"></a>Visualización de envíos de administradores de correo electrónico a Microsoft

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada.

   - Para ordenar las entradas, haga clic en un encabezado de columna disponible. Haga clic en **Personalizar columnas** para seleccionar las columnas que necesita. Todas las columnas se pueden seleccionar y mostrar en la cuadrícula de envío. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):
     - **Nombre del envío**<sup>\*</sup>
     - **Remitente**<sup>\*</sup>
     - **Destinatario**
     - **Fecha de envío**<sup>\*</sup>
     - **Motivo para enviar**<sup>\*</sup>
     - **Estado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Veredicto de filtro**
     - **Motivo de entrega/bloqueo**
     - **Id. de envío**
     - **Id. de mensaje de red o id. de objeto**
     - **Direction**
     - **IP del remitente**
     - **Nivel de cumplimiento masivo (BCL)**
     - **Destino**
     - **Acción de directiva**
     - **Enviado por**
     - **Simulación de phish**
     - **Etiquetas**<sup>\*</sup>
     - **Permitir**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/email-admin-submission-customize-columns.png" alt-text="Opción Personalizar columna para envíos de administrador de correo electrónico." lightbox="../../media/email-admin-submission-customize-columns.png":::

   - Para filtrar las entradas, haga clic en **Filtrar**. Los filtros disponibles son:
     - **Fecha de envío**: **fecha de inicio** y **fecha de finalización**.
     - **Id**. de envío: un valor GUID que se asigna a cada envío.
     - **Identificador de mensaje de red**
     - **Sender**
     - **Destinatario**
     - **Nombre**
     - **Enviado por**
     - **Motivo para enviar**
     - **Estado**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/email-admin-submission-filters.png" alt-text="Opciones de filtro para envíos de administradores de correo electrónico." lightbox="../../media/email-admin-submission-filters.png":::

   - Para agrupar las entradas, haga clic en **Agrupar** y seleccione uno de los siguientes valores en la lista desplegable:
     - **Ninguna**
     - **Motivo**
     - **Estado**
     - **Resultado**
     - **Tags**

   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el archivo .csv.

## <a name="view-email-attachment-admin-submissions-to-microsoft"></a>Visualización de envíos de administrador de datos adjuntos de correo electrónico a Microsoft

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Datos adjuntos de correo electrónico** está seleccionada.

   - Para ordenar las entradas, haga clic en un encabezado de columna disponible. Haga clic en **Personalizar columnas** para seleccionar las columnas que necesita. Todas las columnas se pueden seleccionar y mostrar en la cuadrícula de envío. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):
     - **Nombre de datos adjuntos**<sup>\*</sup>
     - **Fecha de envío**<sup>\*</sup>
     - **Motivo para enviar**<sup>\*</sup>
     - **Estado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Veredicto de filtro**
     - **Motivo de entrega/bloqueo**
     - **Id. de envío**
     - **ID. de objeto**
     - **Acción de directiva**
     - **Enviado por**
     - **Etiquetas**<sup>\*</sup>
     - **Permitir**

     Cuando haya terminado, haga clic en **Aplicar**.

     :::image type="content" source="../../media/email-attachment-admin-submission-customize-columns.png" alt-text="Personalice las opciones de columna para envíos de administrador de datos adjuntos de correo electrónico.":::

   - Para filtrar las entradas, haga clic en **Filtrar**. Los filtros disponibles son:
     - **Fecha de envío**: **fecha de inicio** y **fecha de finalización**.
     - **Id**. de envío: un valor GUID que se asigna a cada envío.
     - **Nombres de archivos adjuntos**
     - **Enviado por**
     - **Motivo para enviar**
     - **Estado**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     :::image type="content" source="../../media/email-attachment-admin-submission-filters.png" alt-text="Opciones de filtro para envíos de administrador de datos adjuntos de correo electrónico.":::

   - Para agrupar las entradas, haga clic en **Agrupar** y seleccione uno de los siguientes valores en la lista desplegable:
     - **Ninguna**
     - **Motivo**
     - **Estado**
     - **Resultado**
     - **Tags**

   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el archivo .csv.

## <a name="view-urls-admin-submissions-to-microsoft"></a>Visualización de envíos de administradores de direcciones URL a Microsoft

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Direcciones URL** está seleccionada.

   - Para ordenar las entradas, haga clic en un encabezado de columna disponible. Haga clic en **Personalizar columnas** para seleccionar las columnas que necesita. Todas las columnas se pueden seleccionar y mostrar en la cuadrícula de envío. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):
     - **URL**<sup>\*</sup>
     - **Fecha de envío**<sup>\*</sup>
     - **Motivo para enviar**<sup>\*</sup>
     - **Estado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Veredicto de filtro**
     - **Motivo de entrega/bloqueo**
     - **Id. de envío**
     - **ID. de objeto**
     - **Acción de directiva**
     - **Enviado por**
     - **Etiquetas**<sup>\*</sup>
     - **Permitir**

     Cuando haya terminado, haga clic en **Aplicar**.

     :::image type="content" source="../../media/url-admin-submission-customize-columns.png" alt-text="Personalice las opciones de columna para envíos de administradores de direcciones URL.":::

   - Para filtrar las entradas, haga clic en **Filtrar**. Los filtros disponibles son:
     - **Fecha de envío**: **fecha de inicio** y **fecha de finalización**.
     - **Id**. de envío: un valor GUID que se asigna a cada envío.
     - **URL**
     - **Enviado por**
     - **Motivo para enviar**
     - **Estado**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     :::image type="content" source="../../media/url-admin-submission-customize-columns.png" alt-text="Opciones de filtro para envíos de administradores de direcciones URL.":::

   - Para agrupar las entradas, haga clic en **Agrupar** y seleccione uno de los siguientes valores en la lista desplegable:
     - **Ninguna**
     - **Motivo**
     - **Estado**
     - **Resultado**
     - **Tags**

   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el archivo .csv.

### <a name="admin-submission-result-details"></a>Administración detalles del resultado del envío

Los mensajes enviados en los envíos de administración se revisan y los resultados se muestran en el control flotante de detalles de envíos:

- Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.
- Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.
- Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.
- Comentarios de los calificadores.

Si se encontró una invalidación, el resultado debería estar disponible en varios minutos. Si no se produjo un problema en la autenticación o entrega de correo electrónico no se ha visto afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.

## <a name="view-user-submissions-to-microsoft"></a>Visualización de envíos de usuarios a Microsoft

Si ha implementado el [complemento Mensaje](enable-the-report-message-add-in.md) de informe, el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe o los usuarios usan los [informes integrados en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están informando en la pestaña **Mensaje notificado** por el usuario.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Mensajes notificados por el usuario** .

   - Para ordenar las entradas, haga clic en un encabezado de columna disponible. Haga clic en **Personalizar columnas** para mostrar las opciones. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):

     - **Asunto del correo electrónico**<sup>\*</sup>
     - **Notificado por**<sup>\*</sup>
     - **Fecha notificada**<sup>\*</sup>
     - **Remitente**<sup>\*</sup>
     - **Motivo notificado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Id. notificado de mensaje**
     - **Identificador de mensaje de red**
     - **IP del remitente**
     - **Notificado desde**
     - **Simulación de phish**
     - **Convertido al envío de administrador**
     - **Etiquetas**<sup>\*</sup>
     - **Marcado como**<sup>\*</sup>
     - **Marcado por**
     - **Fecha marcada**

     Cuando haya terminado, haga clic en **Aplicar**.

   - Para filtrar las entradas, haga clic en **Filtrar**. Los filtros disponibles son:
     - **Fecha notificada**: **fecha de inicio** y **fecha de finalización**.
     - **Informe realizado por**
     - **Asunto del correo electrónico**
     - **Id. notificado de mensaje**
     - **Identificador de mensaje de red**
     - **Sender**
     - **Motivo notificado**: **no basura**, **phish** o **correo no deseado**
     - **Notificado desde**: **complemento de Microsoft** o **complemento de terceros**
     - **Simulación de phish**: **Sí** o **No**
     - **Convertido al envío de administrador**: **Sí** o **No**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-reported-messages.png" alt-text="Opciones de nuevo filtro para envíos de usuarios" lightbox="../../media/admin-submission-reported-messages.png":::

   - Para agrupar las entradas, haga clic en **Agrupar** y seleccione uno de los siguientes valores en la lista desplegable:
     - **Ninguna**
     - **Motivo**
     - **Sender**
     - **Informe realizado por**
     - **Resultado**
     - **Notificado desde**
     - **Simulación de phish**
     - **Convertido al envío de administrador**
     - **Tags**

   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el archivo .csv.

> [!NOTE]
> Si las organizaciones están configuradas para enviar mensajes notificados por el usuario solo al buzón personalizado, los mensajes notificados aparecerán en **Mensajes notificados** por el usuario, pero sus resultados siempre estarán vacíos (ya que no se habrían vuelto a examinar).

## <a name="undo-user-submissions"></a>Deshacer envíos de usuarios

Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen la opción de deshacer el envío. Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo electrónico no deseado.

## <a name="convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>Convertir mensajes notificados por el usuario del buzón personalizado en un envío de administrador

Si ha configurado el buzón personalizado para interceptar los mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede encontrar y enviar mensajes específicos a Microsoft para su análisis.

En la pestaña **Mensajes notificados** por el usuario, seleccione un mensaje en la lista, haga clic en **Enviar a Microsoft para su análisis** y, a continuación, seleccione uno de los siguientes valores en la lista desplegable:

- **Informe limpio**
- **Informar de suplantación de identidad**
- **Informar de malware**
- **Notificar correo no deseado**
- **Investigación del desencadenador**

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/admin-submission-main-action-button.png" alt-text="Las nuevas opciones del botón Acción" lightbox="../../media/admin-submission-main-action-button.png":::

Si el mensaje se notifica a Microsoft, el valor **convertida en envío de administrador** pasa de **no** a **sí**. Para acceder directamente al envío del administrador, haga clic en **Ver el envío del administrador convertido** desde el menú de desbordamiento dentro del control flotante de envío del mensaje notificado por el usuario correspondiente.

:::image type="content" source="../../media/view-converted-admin-submission.png" alt-text="Opción para ver un envío de administrador creado a partir de un mensaje notificado por el usuario.":::

## <a name="view-associated-alert-for-user-and-admin-email-submissions"></a>Visualización de alertas asociadas para envíos de correo electrónico de usuario y administrador

> [!IMPORTANT]
> La información de esta sección solo se aplica a Defender para Office 365 Plan 2 o superior.
>
> Actualmente, los envíos de usuarios generan alertas solo para los mensajes que se notifican como phishing.

Para cada mensaje de suplantación de identidad notificado por el usuario y el envío de correo electrónico del administrador, se genera una alerta correspondiente.

Para ver la alerta correspondiente de un mensaje de suplantación de identidad notificado por el usuario, seleccione la pestaña **Mensajes notificados** por el usuario y, a continuación, haga doble clic en el mensaje para abrir el control flotante de envío. Haga clic en el ![icono Más opciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más opciones** y, a continuación, seleccione  **Ver alerta**.

:::image type="content" source="../../media/alert-from-user-submission.png" alt-text="Opción para ver la alerta relacionada de un mensaje de suplantación de identidad notificado por el usuario.":::

Para ver la alerta correspondiente para envíos de correo electrónico de administrador, seleccione la pestaña **Correos electrónicos** y, a continuación, haga doble clic en el mensaje para abrir el control flotante de envío. Seleccione **Ver alerta** en la opción **Abrir entidad de correo electrónico** .

:::image type="content" source="../../media/alert-from-admin-submission.png" alt-text="Opción para ver la alerta relacionada desde un envío de administrador.":::
