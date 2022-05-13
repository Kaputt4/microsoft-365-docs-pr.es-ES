---
title: Personalización de una directiva de archivo y eliminación (MRM) para buzones
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Cómo crear una directiva personalizada de archivado y eliminación de la administración de registros de mensajería (MRM) para mover automáticamente los elementos al buzón de archivo de un usuario.
ms.openlocfilehash: 892f10b7cb57fcc85a7eb364d35730adb2d9c99d
ms.sourcegitcommit: 54bc063818779e351ca24f04ba571f762d85751d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393510"
---
# <a name="customize-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Personalización de una directiva de archivo y eliminación para buzones de correo de la organización

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview los administradores pueden crear una directiva de archivado y eliminación que mueve automáticamente los elementos al [buzón de archivo](archive-mailboxes.md) de un usuario y elimina automáticamente los elementos del buzón.

Para ello, cree una directiva de retención de administración de registros de mensajería (MRM) que luego asigne a los buzones. Esta directiva mueve los elementos al buzón de archivo de un usuario después de un período de tiempo especificado y también elimina los elementos del buzón después de alcanzar un límite de edad determinado.

Las reglas reales que determinan qué elementos se mueven o eliminan y cuando esto sucede se denominan etiquetas de retención. Las etiquetas de retención están vinculadas a una directiva de retención de MRM, que a su vez se asigna al buzón de un usuario. Una etiqueta de retención aplica la configuración de retención a mensajes y carpetas individuales en el buzón de un usuario. Define cuánto tiempo permanece un mensaje en el buzón y qué acción se realiza cuando el mensaje alcanza la antigüedad de retención especificada. Cuando un mensaje alcanza su antigüedad de retención, se mueve al buzón de archivo del usuario o se elimina.
  
Los pasos de este artículo configuraron una directiva de archivado y retención para una organización ficticia llamada Alpine House. La configuración de esta directiva incluye las siguientes tareas:
  
- Habilite un buzón de archivo para cada usuario de la organización. Este procedimiento proporciona a los usuarios más almacenamiento de buzón de correo y es necesario para que una directiva de retención pueda mover automáticamente los elementos al buzón de archivo. Un usuario también puede mover manualmente los elementos a su buzón de archivo para el almacenamiento de archivo.

- Cree tres etiquetas de retención personalizadas para realizar las siguientes acciones:

  - Mueva automáticamente los elementos con una antigüedad de 3 años al buzón de archivo del usuario. Mover elementos al buzón de archivo libera espacio en el buzón principal de un usuario.

  - Elimine automáticamente los elementos que tienen 5 años de edad de la carpeta Elementos eliminados. Esto también libera espacio en el buzón principal del usuario. Los usuarios tendrán la oportunidad de recuperar estos elementos si es necesario. Consulte la nota al pie de la sección [Más información](#more-information) para obtener más información. 

  - Elimine automáticamente (y permanentemente) los elementos que tienen 7 años tanto del buzón principal como del buzón de archivo. Debido a las regulaciones de cumplimiento, algunas organizaciones deben conservar el correo electrónico durante un período de tiempo específico. Cuando expire este período de tiempo, es posible que una organización quiera quitar permanentemente estos elementos de los buzones de usuario.

- Cree una nueva directiva de retención y agregue las nuevas etiquetas de retención personalizadas. Además, también agregará etiquetas de retención integradas a la nueva directiva de retención. Esto incluye etiquetas personales que los usuarios pueden asignar a los elementos de su buzón. También agregará una etiqueta de retención que mueve los elementos de la carpeta Elementos recuperables del buzón principal del usuario a la carpeta Elementos recuperables de su buzón de archivo. Esta acción ayuda a liberar espacio en la carpeta Elementos recuperables de un usuario cuando su buzón está en espera.

Puede seguir algunos o todos los pasos de este artículo para configurar una directiva de archivo y eliminación para buzones de su propia organización. Se recomienda probar este proceso en algunos buzones antes de implementarlo en todos los buzones de su organización.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Antes de configurar una directiva de archivo y eliminación

- Debe ser administrador global de su organización para realizar los pasos de este artículo.

- Al crear una nueva cuenta de usuario y asignar al usuario una licencia de Exchange Online, se crea automáticamente un buzón para el usuario. Cuando se crea el buzón, se le asigna automáticamente una directiva de retención predeterminada, denominada Directiva de MRM predeterminada. En este artículo, creará una nueva directiva de retención de MRM y, a continuación, la asignará a los buzones de usuario, reemplazando la directiva de MRM predeterminada. Un buzón de correo solo puede tener asignada una directiva de retención de MRM al mismo tiempo.

- Para obtener más información sobre las etiquetas de retención y las directivas de retención de MRM en Exchange Online, consulte [Etiquetas de retención y directivas de retención](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Paso 1: Habilitar buzones de archivo para los usuarios

El primer paso es asegurarse de que cada usuario de la organización tiene un buzón de archivo. El buzón de archivo de un usuario debe estar habilitado para que una etiqueta de retención con una acción de retención "Mover a archivo" pueda mover el elemento después de que expire la antigüedad de retención.

Para obtener instrucciones para habilitar los buzones de archivo, consulte [Habilitar buzones de archivo en el portal de cumplimiento Microsoft Purview](enable-archive-mailboxes.md).
  
> [!NOTE]
> Puede habilitar los buzones de archivo en cualquier momento durante este proceso, siempre y cuando estén habilitados en algún momento antes de completar el proceso. Si un buzón de archivo no está habilitado, no se realiza ninguna acción en los elementos que tengan asignada una directiva de archivo o eliminación.

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación

En este paso, creará las tres etiquetas de retención personalizadas que se describieron anteriormente.
  
- Alpine House 3 Year Move to Archive (directiva de archivo personalizado)

- Alpine House 7 Year Permanently Delete (directiva de eliminación personalizada)

- Alpine House Deleted Items 5 Years Delete and Allow Recovery (etiqueta personalizada para la carpeta Elementos eliminados)

Para crear nuevas etiquetas de retención, usará el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> en la organización de Exchange Online. Asegúrese de usar la versión clásica del EAC.
  
1. Vaya a [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) e inicie sesión con sus credenciales.
  
2. En el EAC, vaya a **Administración de** >  **cumplimientoEtiquetas de cumplimiento**

    Se muestra una lista de las etiquetas de retención de su organización.

### <a name="create-a-custom-archive-default-policy-tag"></a>Creación de una etiqueta de directiva predeterminada de archivo personalizado
  
En primer lugar, creará una etiqueta de directiva predeterminada de archivo (DPT) personalizada que moverá los elementos al buzón de archivo después de 3 años.
  
1. En la página **Etiquetas de retención**, seleccione **Nueva etiquetaNuevo**![ icono](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) y, a continuación, seleccione **Aplicado automáticamente a todo el buzón (valor predeterminado).**

2. En la página **Nueva etiqueta aplicada automáticamente a todo el buzón (valor predeterminado),** complete los campos siguientes: 

    ![Configuración crear una nueva etiqueta de directiva predeterminada de archivo.](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 

   2. **Acción de retención** Seleccione **Mover al archivo** para mover elementos al buzón de archivo cuando expire el período de retención.

   3. **Período de retención** Seleccione **Cuando el elemento alcance la edad siguiente (en días)** y, a continuación, escriba la duración del período de retención. En este escenario, los elementos se moverán al buzón de archivo después de 1095 días (3 años).

   4. **Comentario** (opcional) Escriba un comentario que explique el propósito de la etiqueta de retención personalizada.

3. Seleccione **Guardar** para crear el archivo DPT personalizado.

    El nuevo archivo DPT se muestra en la lista de etiquetas de retención.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Creación de una etiqueta de directiva predeterminada de eliminación personalizada
  
A continuación, creará otro DPT personalizado, pero este será una directiva de eliminación que elimina de forma permanente los elementos después de 7 años.
  
1. En la página **Etiquetas de retención**, seleccione **Nueva etiquetaNuevo**![ icono](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) y, a continuación, seleccione **Aplicado automáticamente a todo el buzón (valor predeterminado).**

2. En la página **Nueva etiqueta aplicada automáticamente a todo el buzón (valor predeterminado),** complete los campos siguientes: 

    ![Configuración para crear una nueva etiqueta de directiva predeterminada de eliminación.](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 

   2. **Acción de retención** Seleccione **Eliminar permanentemente** para purgar elementos del buzón cuando expire el período de retención.

   3. **Período de retención** Seleccione **Cuando el elemento alcance la edad siguiente (en días)** y, a continuación, escriba la duración del período de retención. En este escenario, los elementos se purgarán después de 2555 días (7 años).

   4. **Comentario** (opcional) Escriba un comentario que explique el propósito de la etiqueta de retención personalizada. 

3. Seleccione **Guardar** para crear el DPT de eliminación personalizada. 

    El nuevo DPT de eliminación se muestra en la lista de etiquetas de retención.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Creación de una etiqueta de directiva de retención personalizada para la carpeta Elementos eliminados
  
La última etiqueta de retención que se va a crear es una etiqueta de directiva de retención personalizada (RPT) para la carpeta Elementos eliminados. Esta etiqueta eliminará los elementos de la carpeta Elementos eliminados después de 5 años y proporciona un período de recuperación en el que los usuarios pueden usar la herramienta Recuperar elementos eliminados para recuperar un elemento.
  
1. En la página **Etiquetas de retención**, seleccione **Nuevo icono**](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) Nueva etiqueta ![y, a continuación, seleccione **Aplicado automáticamente a una carpeta predeterminada**.

2. En la página **Nueva etiqueta aplicada automáticamente a una carpeta predeterminada** , complete los campos siguientes:

    ![Configuración crear una nueva etiqueta de directiva de retención para la carpeta Elementos eliminados.](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 

   2. **Aplicar esta etiqueta a la siguiente carpeta predeterminada** En la lista desplegable, seleccione **Elementos eliminados**.

   3. **Acción de retención** Seleccione **Eliminar y Permitir que la recuperación** elimine elementos cuando expire el período de retención, pero permitir que los usuarios recuperen un elemento eliminado dentro del período de retención de elementos eliminados (que de forma predeterminada es de 14 días).

   4. **Período de retención** Seleccione **Cuando el elemento alcance la edad siguiente (en días)** y, a continuación, escriba la duración del período de retención. En este escenario, los elementos se eliminarán después de 1825 días (5 años).

   5. **Comentario** (opcional) Escriba un comentario que explique el propósito de la etiqueta de retención personalizada. 

3. Seleccione **Guardar** para crear el RPT personalizado para la carpeta Elementos eliminados.

    El nuevo RPT se muestra en la lista de etiquetas de retención.

## <a name="step-3-create-a-new-retention-policy"></a>Paso 3: Crear una nueva directiva de retención

Después de crear las etiquetas de retención personalizadas, el siguiente paso es crear una nueva directiva de retención y agregar las etiquetas de retención. Agregará las tres etiquetas de retención personalizadas que creó en el paso 2 y las etiquetas integradas que se mencionaron en la primera sección. En el paso 4, asignará esta nueva directiva de retención a los buzones de usuario.
  
1. En el EAC, vaya a **Administración de cumplimientoDirectivas** >  **de cumplimiento**.

2. En la página **Directivas de retención**, seleccione **Nuevo** ![nuevo icono.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)

3. En el cuadro **Nombre** , escriba un nombre para la nueva directiva de retención; por ejemplo, **Alpine House Archive and Deletion Policy**.

4. En **Etiquetas de retención**, seleccione **Agregar** ![nuevo icono.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)

    Se muestra una lista de las etiquetas de retención de la organización. Tenga en cuenta que se muestran las etiquetas personalizadas que creó en el paso 2.

5. Agregue las 9 etiquetas de retención resaltadas en la captura de pantalla siguiente (estas etiquetas se describen con más detalle en la sección [Más información](#more-information) ). Para agregar una etiqueta de retención, selecciónela y, a continuación, seleccione **Agregar**.

    ![Agregue etiquetas de retención a la nueva directiva de retención.](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Puede seleccionar varias etiquetas de retención manteniendo presionada la tecla **Ctrl** y, a continuación, haciendo clic en cada etiqueta. 
  
6. Después de agregar las etiquetas de retención, seleccione **Aceptar**.

7. En la página **Nueva directiva de retención** , seleccione **Guardar** para crear la nueva directiva.

    La nueva directiva de retención se muestra en la lista. Selecciónelo para mostrar las etiquetas de retención vinculadas a ella en el panel de detalles.

    ![La nueva directiva de retención y la lista de etiquetas de retención vinculadas.](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Paso 4: Asignar la nueva directiva de retención a buzones de usuario

Cuando se crea un nuevo buzón de correo, se le asigna de forma predeterminada una directiva de retención denominada Directiva de MRM predeterminada. En este paso, reemplazará esta directiva de retención asignando la nueva directiva de retención que creó en el paso 3 a los buzones de usuario de su organización. El reemplazo es necesario porque un buzón solo puede tener asignada una directiva de retención de MRM a la vez. En este paso se supone que asignará la nueva directiva a todos los buzones de correo de la organización.
  
1. En el EAC, vaya a **RecipientsMailboxes** > .

    Se muestra una lista de todos los buzones de correo de usuario de la organización.

2. Seleccione todos los buzones haciendo clic en el primero de la lista, manteniendo presionada la tecla **Mayús** y, a continuación, haciendo clic en el último de la lista. 

3. En el panel de detalles del EAC, en **Edición masiva**, seleccione **Más opciones**.

4. En **Directiva de retención**, seleccione **Actualizar**.

5. En la página Asignación masiva de directivas de **retención** , en la lista desplegable **Seleccionar la directiva de retención** , seleccione la directiva de retención que creó en el paso 3; por ejemplo, **Alpine House Archive y Retention Policy**.

6. Seleccione **Guardar** para guardar la nueva asignación de directiva de retención.

7. Para comprobar que la nueva directiva de retención se asignó a los buzones:

   1. Seleccione un buzón en la página **Buzones** y, a continuación, seleccione **Editar** ![edición](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).

   2. En la página de propiedades del buzón del usuario seleccionado, seleccione **Características del buzón**.

   El nombre de la nueva directiva asignada al buzón se muestra en la lista desplegable **Directiva de retención** .

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Opcional) Paso 5: Ejecución del Asistente para carpetas administradas para aplicar la nueva configuración

Después de aplicar la nueva directiva de retención a los buzones del paso 4, puede tardar hasta 7 días en Exchange Online para que la nueva configuración de retención se aplique a los buzones. Esto se debe a que un proceso denominado *Asistente para carpetas administradas* procesa buzones al menos una vez cada 7 días. En lugar de esperar a que se ejecute el Asistente para carpetas administradas, puede forzarlo ejecutando el cmdlet **Start-ManagedFolderAssistant** en Exchange Online PowerShell.

 **¿Qué ocurre cuando se ejecuta el Asistente para carpetas administradas?** Aplica la configuración de la directiva de retención inspeccionando los elementos del buzón y determinando si están sujetos a retención. A continuación, marca los elementos sujetos a retención con la etiqueta de retención adecuada y, a continuación, realiza la acción de retención especificada en los elementos que han superado su antigüedad de retención.
  
Estos son los pasos para conectarse a Exchange Online PowerShell y, a continuación, ejecutar el Asistente para carpetas administradas en cada buzón de correo de la organización.

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Ejecute los dos comandos siguientes para iniciar el Asistente para carpetas administradas para todos los buzones de correo de usuario de la organización.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Y eso es todo. Ha configurado una directiva de archivo y eliminación para la organización Alpine House.

### <a name="more-information-about-the-managed-folder-assistant"></a>Más información sobre el Asistente para carpetas administradas

Como se indicó anteriormente, el Asistente para carpetas administradas procesa buzones al menos una vez cada 7 días. Por lo tanto, es posible que el Asistente para carpetas administradas pueda procesar un buzón con más frecuencia. Además, los administradores no pueden predecir la próxima vez que el Asistente para carpetas administradas procese un buzón, que es una de las razones por las que es posible que quiera ejecutarlo manualmente. 

Sin embargo, si quiere evitar temporalmente que el Asistente para carpetas administradas aplique la nueva configuración de retención a un buzón, puede ejecutar el `Set-Mailbox -ElcProcessingDisabled $true` comando para deshabilitar temporalmente el Asistente para carpetas administradas para que no procese un buzón. 

Para volver a habilitar el Asistente para carpetas administradas para un buzón de correo, ejecute el `Set-Mailbox -ElcProcessingDisabled $false` comando . 

Por último, si un usuario de buzón de correo tiene una cuenta deshabilitada, los elementos no se mueven al buzón de archivo para ese buzón.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(Opcional) Paso 6: Hacer que la nueva directiva de retención sea la predeterminada para su organización

En el paso 4, debe asignar la nueva directiva de retención a los buzones existentes. Pero puede configurar Exchange Online para que la nueva directiva de retención se asigne a los nuevos buzones que se creen en el futuro. 

Para ello, use Exchange Online PowerShell para actualizar el plan de buzón predeterminado de su organización. Un *plan de buzón de correo* es una plantilla que configura automáticamente las propiedades en los nuevos buzones.  En este paso opcional, puede reemplazar la directiva de retención actual asignada al plan de buzón de correo (de forma predeterminada, la directiva de MRM predeterminada) por la directiva de retención de MRM que creó en el paso 3. Después de actualizar el plan de buzón de correo, la nueva directiva de retención de MRM se asignará a los nuevos buzones.

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para mostrar información sobre los planes de buzón de correo de su organización.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    
    Tenga en cuenta el plan de buzón establecido como predeterminado.

3. Ejecute el siguiente comando para asignar la nueva directiva de retención de MRM que creó en el paso 3 (por ejemplo, **Alpine House Archive and Retention Policy**) al plan de buzón predeterminado. En este ejemplo se supone que el nombre del plan de buzón predeterminado es **ExchangeOnlineEnterprise**.
    
    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Puede volver a ejecutar el comando en el paso 2 para comprobar que se ha cambiado la directiva de retención de MRM asignada al plan de buzón predeterminado.

## <a name="more-information"></a>Más información

- La antigüedad de retención de los elementos de buzón se calcula a partir de la fecha de entrega. O a partir de la fecha de creación de elementos como borradores de mensajes que no se envían pero que el usuario crea. Cuando el asistente para carpeta administrada procesa los elementos en un buzón de correo, coloca una fecha de inicio y una fecha de expiración para todos los elementos que poseen etiquetas de retención con la acción de retención Eliminar y permitir la recuperación o Eliminar permanentemente. Los elementos que tienen una etiqueta de archivo se marcan con una fecha de traslado.

- En la tabla siguiente se proporciona más información sobre cada etiqueta de retención de la directiva de retención de MRM personalizada de este artículo.

    | Etiqueta de retención | Lo que hace esta etiqueta | ¿Integrado o personalizado? | Tipo |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Year Move to Archive  <br/> |Mueve los elementos que tienen 1095 días (3 años) de antigüedad al buzón de archivo.  <br/> |Personalizado (consulte [Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva predeterminada (archivo); esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Alpine House 7 Year Permanently Delete  <br/> |Elimina permanentemente los elementos del buzón principal o del buzón de archivo cuando tienen 7 años.  <br/> |Personalizado (consulte [Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva predeterminada (eliminación); esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Alpine House elementos eliminados 5 años eliminar y permitir la recuperación  <br/> |Elimina elementos de la carpeta Elementos eliminados que tienen 5 años. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Personalizado (consulte [Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva de retención (elementos eliminados); esta etiqueta se aplica automáticamente a los elementos de la carpeta Elementos eliminados.  <br/> |
    |Elementos recuperables 14 días Mover al archivo  <br/> |Mueve los elementos que han estado en la carpeta Elementos recuperables durante 14 días a la carpeta Elementos recuperables del buzón de archivo.  <br/> |Integrado  <br/> |Etiqueta de directiva de retención (elementos recuperables); esta etiqueta se aplica automáticamente a los elementos de la carpeta Elementos recuperables.  <br/> |
    |Correo electrónico no deseado  <br/> |Elimina permanentemente los elementos que han estado en la carpeta Correo no deseado durante 30 días. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Etiqueta de directiva de retención (correo electrónico no deseado); esta etiqueta se aplica automáticamente a los elementos de la carpeta Correo no deseado.  <br/> |
    |Eliminar después de un mes  <br/> |Elimina permanentemente los elementos que tienen 30 días de antigüedad. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Personal; los usuarios pueden aplicar esta etiqueta.  <br/> |
    |Eliminar después de un año  <br/> |Elimina permanentemente los elementos que tienen 365 días de antigüedad. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Personal; los usuarios pueden aplicar esta etiqueta.  <br/> |
    |No eliminar nunca  <br/> |Esta etiqueta impide que una directiva de retención elimine los elementos.  <br/> |Integrado  <br/> |Personal; los usuarios pueden aplicar esta etiqueta.  <br/> |
    |Mover al archivo después de 1 años en forma personal  <br/> |Mueve los elementos al buzón de archivo después de 1 año.  <br/> |Integrado  <br/> |Personal; los usuarios pueden aplicar esta etiqueta.  <br/> |

    > <sup>\*</sup>Los usuarios pueden usar la herramienta Recuperar elementos eliminados en Outlook y Outlook en la Web (anteriormente conocida como Outlook Web App) para recuperar un elemento eliminado dentro del período de retención de elementos eliminados, que de forma predeterminada es de 14 días en Exchange Online. Un administrador puede usar Windows PowerShell para aumentar el período de retención de elementos eliminados a un máximo de 30 días. Para obtener más información, vea: [Recuperar elementos eliminados en Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) y [Cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).
  
- El uso de la etiqueta de retención **Mover a archivo de elementos recuperables durante 14 días** ayuda a liberar espacio de almacenamiento en la carpeta Elementos recuperables del buzón principal del usuario. Esto resulta útil cuando el buzón de un usuario se coloca en espera, lo que significa que nada se elimina permanentemente del buzón del usuario. Sin mover elementos al buzón de archivo, es posible que se alcance la cuota de almacenamiento para la carpeta Elementos recuperables del buzón principal. Para obtener más información sobre esto y cómo evitarlo, consulte [Aumento de la cuota de elementos recuperables para buzones en espera](./increase-the-recoverable-quota-for-mailboxes-on-hold.md).
