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
description: Los administradores pueden aprender a usar el portal de envíos en el portal de Microsoft 365 Defender para enviar correos electrónicos sospechosos, correos de suplantación de identidad sospechosos, correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y datos adjuntos de correo electrónico a Microsoft para volver a examinarlos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d699c3344cc16f3e15996139f1d2d8b608ba50
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477157"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar el portal de envíos para enviar correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)


En Microsoft 365 organizaciones con buzones de correo Exchange Online, los administradores pueden usar el portal de envíos en el portal de Microsoft 365 Defender para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para examinarlos.

Cuando envíe un mensaje de correo electrónico para su análisis, recibirá:

- **Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha pasado o no cuando se entregó.
- **Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su inquilino, invalidando nuestros veredictos de filtro de servicio.
- **Reputación/detonación de carga**: examen actualizado de las direcciones URL y datos adjuntos del mensaje.
- **Análisis de calificadores**: revisión realizada por calificadores humanos para confirmar si los mensajes son malintencionados o no.

> [!IMPORTANT]
> El análisis de reputación/detonación y calificador de carga no se realiza en todos los inquilinos. La información se bloquea para que no salga de la organización cuando los datos no deben salir del límite del espacio empresarial con fines de cumplimiento.

Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informar de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la **página Envíos** , use <https://security.microsoft.com/reportsubmission>.

- Para enviar mensajes y archivos a Microsoft, debe tener uno de los siguientes roles:
  - **Administrador de** seguridad **o lector de seguridad** [en el portal Microsoft 365 Defender seguridad](permissions-microsoft-365-security-center.md).
  
    Tenga en cuenta que uno de estos roles es necesario para [ver los envíos](#view-user-submissions-to-microsoft) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.

- Los administradores pueden enviar mensajes tan antiguos como 30 días si aún están disponibles en el buzón y no purgados por el usuario u otro administrador.

- Los envíos de administradores se limitan a las siguientes tasas:
  - Envíos máximos en un período de 15 minutos: 150 envíos
  - Mismos envíos en un período de 24 horas: 3 envíos
  - Mismos envíos en un período de 15 minutos: 1 envío
  
- Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informar de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Informar de contenido sospechoso a Microsoft

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos**\>. Para ir directamente a la **página Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página Envíos, compruebe que la  pestaña Correos  electrónicos o datos  **adjuntos** de correo electrónico o direcciones URL esté seleccionada en función del tipo de contenido que desea notificar y, a continuación, ![haga clic en Enviar a Microsoft para el icono de análisis.](../../media/m365-cc-sc-create-icon.png) **Enviar a Microsoft para su análisis**.

3. Use el **menú desplegable Enviar a Microsoft** para análisis que parece enviar el tipo de contenido correspondiente (correo electrónico, dirección URL o datos adjuntos de correo electrónico) como se describe en las secciones siguientes.

   > [!NOTE]
   > Los envíos de archivos y direcciones URL no están disponibles en las nubes que no permiten que los datos abandone el entorno. La capacidad de seleccionar Archivo o DIRECCIÓN URL se mostrará en gris.

### <a name="notify-users-from-within-the-portal"></a>Notificar a los usuarios desde el portal

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Correo electrónico & envíos de** \> **colaboración**. Para ir directamente a la **página Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la **página Envíos** , seleccione **la pestaña Mensajes** notificados por el usuario y, a continuación, seleccione el mensaje que desea marcar y notificar.

3. Seleccione la **lista desplegable Marcar como y** notificar y, a continuación, **seleccione No se** \> encontraron amenazas **de suplantación de identidad** o **correo no deseado**.

   :::image type="content" source="../../media/unified-submission-user-reported-message.png" alt-text="La página Envíos" lightbox="../../media/unified-submission-user-reported-message.png":::

El mensaje notificado se marcará como un falso positivo o un falso negativo. Una notificación de correo electrónico se envía automáticamente desde el portal al usuario que informó del mensaje.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar un correo electrónico cuestionable a Microsoft

1. En el **cuadro Seleccionar el tipo de envío** , compruebe que **el correo** electrónico está seleccionado en la lista desplegable.

2. En la **sección Agregar el identificador de mensaje de red o cargar** el archivo de correo electrónico, use una de las siguientes opciones:
   - Agregar el identificador de mensaje de red de **correo electrónico:** este es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.
   - **Upload el archivo de correo electrónico (.msg o .eml):** Haga clic **en Examinar archivos**. En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.

3. En el **cuadro Elegir un destinatario con un** problema, especifique el destinatario con el que desea ejecutar una comprobación de directiva. La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.

4. En la **sección Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No debería haber sido bloqueado (Falso positivo)**
   - **Debería haber sido bloqueado (Falso negativo):** En la sección  El correo electrónico debería haber sido categorizado como sección que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**
     - **Correo no deseado**

5. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-flyout-email.png" alt-text="Proceso de envío de nueva dirección URL" lightbox="../../media/submission-flyout-email.png":::

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar una dirección URL sospechosa a Microsoft

1. En el **cuadro Seleccionar el tipo de envío** , seleccione **DIRECCIÓN URL** en la lista desplegable.

2. En el **cuadro Dirección URL** que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html`).

3. En la **sección Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No debería haber sido bloqueado (Falso positivo)**
   - **Debería haber sido bloqueado (Falso negativo):** En la sección Esta **dirección URL** debería haber sido categorizada como sección que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**

4. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-url-flyout.png" alt-text="Proceso de envío de nuevo correo electrónico" lightbox="../../media/submission-url-flyout.png":::

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Enviar datos adjuntos de correo electrónico sospechosos a Microsoft

1. En el **cuadro Seleccionar el tipo de envío** , seleccione **Datos adjuntos de correo electrónico** de la lista desplegable.

2. En la **sección Archivo** que aparece, haga clic **en Examinar archivos**. En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.

3. En la **sección Seleccionar un motivo para enviar a Microsoft** , seleccione una de las siguientes opciones:
   - **No debería haber sido bloqueado (Falso positivo)**
   - **Debería haber sido bloqueado (Falso negativo):** en la sección  Este archivo debería haber sido categorizado como sección que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio):
     - **Suplantación de identidad**
     - **Malware**

4. Cuando haya terminado, haga clic en **Enviar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-file-flyout.png" alt-text="Proceso de envío de nuevos datos adjuntos" lightbox="../../media/submission-file-flyout.png":::

> [!NOTE]
> Si el filtrado de malware ha reemplazado los datos adjuntos del mensaje por el archivo Text.txt de alerta de malware, debe enviar el mensaje original desde la cuarentena que contiene los datos adjuntos originales. Para obtener más información sobre la cuarentena y cómo liberar mensajes con falsos positivos de malware, vea [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

## <a name="view-admin-submissions-to-microsoft"></a>Ver envíos de administrador a Microsoft

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos**\>. Para ir directamente a la **página Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la **página Envíos** , compruebe **que la pestaña** Correos electrónicos, **dirección URL** **o datos** adjuntos de correo electrónico esté seleccionada.

   - Puede ordenar las entradas haciendo clic en un encabezado de columna disponible. Haga **clic en Personalizar columnas** para mostrar un máximo de siete columnas. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):
     - **Nombre del envío**<sup>\*</sup>
     - **Remitente**<sup>\*</sup>
     - **Destinatario**
     - **Fecha enviada**<sup>\*</sup>
     - **Motivo para enviar**<sup>\*</sup>
     - **Estado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Veredicto de filtro**
     - **Motivo de entrega/bloqueo**
     - **Identificador de envío**
     - **Id. de mensaje de red/id. de objeto**
     - **Dirección**
     - **IP del remitente**
     - **Nivel de cumplimiento masivo (BCL)**
     - **Destino**
     - **Acción de directiva**
     - **Enviado por**
     - **Simulación de phishing**
     - **Etiquetas**<sup>\*</sup>
     - **Permitir**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-customize-columns.png" alt-text="Opciones de la columna Nueva personalización para envíos de administrador" lightbox="../../media/admin-submission-customize-columns.png":::

   - Para filtrar las entradas, haga clic **en Filtrar**. Los filtros disponibles son:
     - **Fecha enviada**: **Fecha de inicio y** **Fecha de finalización**.
     - **Identificador de envío**: valor GUID que se asigna a cada envío.
     - **Id. de mensaje de red**
     - **Sender**
     - **Destinatario**
     - **Nombre**
     - **Enviado por**
     - **Motivo para enviar**
     - **Estado**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-filters.png" alt-text="Nuevas opciones de filtro para envíos de administrador" lightbox="../../media/admin-submission-filters.png":::

   - Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:
     - **Ninguna**
     - **Tipo**
     - **Motivo**
     - **Estado**
     - **Resultado**
     - **Tags**

   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el .csv archivo.

### <a name="admin-submission-result-details"></a>Detalles del resultado del envío de administrador

Los mensajes que se envían en envíos de administrador se revisan y los resultados se muestran en el menú desplegable de detalles de envíos:

- Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.
- Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.
- Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.
- Comentarios de los calificadores.

Si se encontró una invalidación, el resultado debería estar disponible en varios minutos. Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.

## <a name="view-user-submissions-to-microsoft"></a>Ver envíos de usuario a Microsoft

Si ha implementado el complemento Report [Message](enable-the-report-message-add-in.md), el complemento [Report Phishing](enable-the-report-phish-add-in.md) o los usuarios usan los informes integrados en [Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están informando en la pestaña Mensaje de usuario notificado.

1. En el Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos**\>. Para ir directamente a la **página Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la **página Envíos** , seleccione la **pestaña Mensajes notificados por el** usuario.

   - Puede ordenar las entradas haciendo clic en un encabezado de columna disponible. Haga **clic en Personalizar columnas** para mostrar las opciones. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):

     - **Asunto del correo electrónico**<sup>\*</sup>
     - **Notificado por**<sup>\*</sup>
     - **Fecha notificada**<sup>\*</sup>
     - **Remitente**<sup>\*</sup>
     - **Motivo notificado**<sup>\*</sup>
     - **Resultado**<sup>\*</sup>
     - **Id. de mensaje notificado**
     - **Id. de mensaje de red**
     - **IP del remitente**
     - **Notificado desde**
     - **Simulación de phishing**
     - **Convertido a envío de administrador**
     - **Etiquetas**<sup>\*</sup>
     - **Marcado como**<sup>\*</sup>
     - **Marcado por**
     - **Fecha marcada**

     Cuando haya terminado, haga clic en **Aplicar**.

   - Para filtrar las entradas, haga clic **en Filtrar**. Los filtros disponibles son:
     - **Fecha notificada**: **Fecha de inicio** y **fecha de finalización**.
     - **Informe realizado por**
     - **Asunto del correo electrónico**
     - **Id. de mensaje notificado**
     - **Id. de mensaje de red**
     - **Sender**
     - **Motivo notificado**: **No es correo no** deseado, **suplantación de identidad** o **correo no deseado**
     - **Notificado desde**: **complemento de Microsoft** **o complemento de terceros**
     - **Simulación de phish**: **Sí** o **No**
     - **Convertido a envío de administrador**: **Sí** o **No**
     - **Tags**

     Cuando haya terminado, haga clic en **Aplicar**.

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-reported-messages.png" alt-text="Nuevas opciones de filtro para envíos de usuarios" lightbox="../../media/admin-submission-reported-messages.png":::

   - Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:
     - **Ninguna**
     - **Motivo**
     - **Sender**
     - **Informe realizado por**
     - **Resultado**
     - **Notificado desde**
     - **Simulación de phishing**
     - **Convertido a envío de administrador**
     - **Tags**
   
   - Para exportar las entradas, haga clic en **Exportar**. En el cuadro de diálogo que aparece, guarde el .csv archivo.

> [!NOTE]
> Si las organizaciones están configuradas para enviar mensajes notificados por el usuario solo al buzón personalizado, los mensajes notificados no se enviarán para  volver a examinarse y los resultados de los mensajes notificados por el usuario siempre estarán vacíos.

### <a name="undo-user-submissions"></a>Deshacer envíos de usuarios

Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen ninguna opción para deshacer el envío. Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.

### <a name="converting-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>Convertir mensajes notificados por el usuario desde el buzón personalizado en un envío de administrador 

Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.

En la **pestaña Mensajes** notificados por el usuario, seleccione un mensaje en la lista, haga clic en Enviar a **Microsoft** para su análisis y, a continuación, seleccione uno de los siguientes valores de la lista desplegable:

- **Informe limpio**
- **Report phishing**
- **Informar de malware**
- **Notificar correo no deseado**
- **Investigación de desencadenadores**

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/admin-submission-main-action-button.png" alt-text="Las nuevas opciones del botón Acción" lightbox="../../media/admin-submission-main-action-button.png":::
