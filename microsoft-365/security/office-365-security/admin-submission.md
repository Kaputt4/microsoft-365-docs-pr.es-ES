---
title: Envíos de administración en Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente perjudiciales, direcciones URL y archivos de la empresa a Microsoft para su análisis.
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034205"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft

Si es administrador de una organización de Microsoft 365 con buzones en Exchange Online, puede usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.

Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo. Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).

Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página de **envío** , <https://protection.office.com/reportsubmission>use.

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para agregar, modificar y eliminar directivas contra correo no deseado, debe ser miembro de los grupos de funciones **Administración**de la organización, **Administrador de seguridad**o **lector de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Informar sobre contenido sospechoso a Microsoft

1. En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .

2. En la página envíos que aparece, haga clic **en el botón** **nuevo envío** .

3. Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar un correo electrónico cuestionable a Microsoft

1. En la sección **tipo de objeto** , seleccione **correo electrónico**. En la sección **formato de envío** , use una de las siguientes opciones:

   - **Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-ID** del mensaje.

   - **Archivo**: haga clic en **elegir archivo**. En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.

2. En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva. La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.

3. En la sección **motivo de envío** , seleccione una de las siguientes opciones:

   - **No se debe haber bloqueado**

   - **Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing**o **malware**. Si no está seguro, use su mejor criterio.

4. Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.

   Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos. Para ver más información sobre el envío, haga clic en el vínculo estado. Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo. Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.

5. Cuando haya terminado, haga clic en el botón **Enviar** .

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar una dirección URL sospechosa a Microsoft

1. En la sección **tipo de objeto** , seleccione **dirección URL**. En el cuadro que aparece, escriba la dirección URL completa (por ejemplo <https://www.fabrikam.com/marketing.html>,).

2. En la sección **motivo de envío** , seleccione una de las siguientes opciones:

   - **No se debe haber bloqueado**

   - **Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.

3. Cuando haya terminado, haga clic en el botón **Enviar** .

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar un archivo sospechoso a Microsoft

1. En la sección **tipo de objeto** , seleccione **datos adjuntos**.

2. Haga clic en **elegir archivo**. En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.

3. En la sección **motivo de envío** , seleccione una de las siguientes opciones:

   - **No se debe haber bloqueado**

   - **Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..

4. Cuando haya terminado, haga clic en el botón **Enviar** .

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Ver envíos de administración

1. En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .

2. En la página **envíos** que aparece, compruebe que la pestaña **envíos administrativos** está seleccionada.

Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** introduciendo un valor ![en el](../../media/scc-quarantine-refresh.png)cuadro y haciendo clic en el botón actualizar. Update

Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:

- **Sender**
- **Asunto/URL/nombre de archivo**
- **Enviado por**
- **Tipo de envío**
- **Estado**

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** . En el cuadro de diálogo que aparece, guarde el archivo. csv.

Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL**y **datos adjuntos**.

### <a name="view-admin-email-submissions"></a>Ver envíos de correo electrónico de administrador

Haga clic en la pestaña **correo electrónico** .

Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **IDENTIFICADOR de envío**
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**
- **Motivo de la entrega**
- **Estatus**<sup>\*</sup>
- **Tipo de control**
- **Origen del control**

  <sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.

### <a name="view-admin-url-submissions"></a>Ver envíos de direcciones URL de administración

Haga clic en la ficha **dirección URL** .

Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **IDENTIFICADOR de envío**
- **Enviado por**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo de envío**
- **Estatus**<sup>\*</sup>

  <sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.

### <a name="view-admin-attachment-submissions"></a>Ver envíos de datos adjuntos de administración

Haga clic en la pestaña **datos adjuntos** .

Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **IDENTIFICADOR de envío**
- **Enviado por**<sup>\*</sup>
- **Nombre de archivo**<sup>\*</sup>
- **Tipo de envío**
- **Estatus**<sup>\*</sup>

  <sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.

## <a name="view-user-submissions-to-microsoft"></a>Ver envíos de usuarios a Microsoft

Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .

1. En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .

2. En la página **envíos** que aparece, haga clic en la pestaña **envíos de usuarios** .

Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Enviado el**
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**

<sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.

Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el ![cuadro y](../../media/scc-quarantine-refresh.png)haciendo clic en el botón actualizar. Update

Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:

- **Dominio del remitente**
- **Asunto**
- **Enviado por**
- **Tipo de envío**
- **IP del remitente**

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** . En el cuadro de diálogo que aparece, guarde el archivo. csv.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Ver los envíos de usuarios al buzón personalizado

Si ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.

1. En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .

2. En la página **envíos** que aparece, haga clic en la ficha **buzón personalizado** .

Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Enviado el**
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**

Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el ![cuadro y](../../media/scc-quarantine-refresh.png)haciendo clic en el botón actualizar. Update

Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** . En el cuadro de diálogo que aparece, guarde el archivo. csv.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Enviar mensajes a Microsoft desde el buzón personalizado

Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis. Esto mueve eficazmente un envío de usuario a un envío de administración.

En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:

- **Limpiar informe**
- **Notificar phishing**
- **Notificar malware**
- **Informar del correo no deseado**

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
