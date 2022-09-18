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
description: Cómo crear una directiva de archivado y eliminación de registros de mensajería personalizados (MRM) para mover automáticamente los elementos al buzón de archivo de un usuario.
ms.openlocfilehash: 2ac1b70efcda7d6fb48e5c5da9bddb2bcec684c2
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67798811"
---
# <a name="customize-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Personalización de una directiva de archivo y eliminación para buzones de correo de la organización

Para conservar y eliminar correos electrónicos, se recomienda usar [directivas de retención y etiquetas de retención de Microsoft 365 en](retention.md) lugar de la administración de registros de mensajería (MRM) anterior de Exchange Online. Sin embargo, una razón válida para seguir usando esta característica anterior es mover automáticamente los correos electrónicos del buzón principal de un usuario a su [buzón de archivo](archive-mailboxes.md). También es posible que tenga que usar MRM para aplicar la configuración de retención y eliminación a carpetas específicas del buzón, en lugar de a todo el buzón.

Use este artículo como implementación de ejemplo por estos dos motivos válidos para usar directivas de retención de MRM y etiquetas de retención. Para todos los demás escenarios de retención y eliminación, use directivas de retención y etiquetas de retención de Microsoft 365.

La configuración requiere que cree una directiva de retención de MRM que luego asigne a los buzones de correo. Esta directiva mueve los elementos al buzón de archivo de un usuario después de un período de tiempo especificado y también elimina los elementos de la carpeta Elementos eliminados después de alcanzar un límite de edad específico.

Las reglas reales que determinan qué elementos se mueven o eliminan y cuando esto sucede se denominan etiquetas de retención. Las etiquetas de retención están vinculadas a una directiva de retención de MRM, que a su vez se asigna al buzón de un usuario. Una etiqueta de retención aplica la configuración de retención a mensajes y carpetas individuales en el buzón de un usuario. Define cuánto tiempo permanece un mensaje en el buzón y qué acción se realiza cuando el mensaje alcanza la antigüedad de retención especificada. Cuando un mensaje alcanza su antigüedad de retención, se mueve al buzón de archivo del usuario o se elimina.
  
Los pasos de este artículo configuraron una directiva de archivado y retención para una organización ficticia llamada Alpine House. La configuración de esta directiva incluye las siguientes tareas:
  
- Habilite un buzón de archivo para cada usuario de la organización. Este procedimiento proporciona a los usuarios más almacenamiento de buzón de correo y es necesario para que una directiva de retención pueda mover automáticamente los elementos al buzón de archivo. Un usuario también puede mover manualmente los elementos a su buzón de archivo para el almacenamiento de archivo.

- Cree dos etiquetas de retención personalizadas para realizar las siguientes acciones:
    
    - Mueva automáticamente los elementos con una antigüedad de 3 años al buzón de archivo del usuario. Mover elementos al buzón de archivo libera espacio en el buzón principal de un usuario.
    
    - Elimine automáticamente los elementos que tienen 5 años de edad de la carpeta Elementos eliminados. Esto también libera espacio en el buzón principal del usuario. Los usuarios tendrán la oportunidad de recuperar estos elementos si es necesario. Consulte la nota al pie de la sección [Más información](#more-information) para obtener más información. 

- Cree una nueva directiva de retención y agréguele las nuevas etiquetas de retención personalizadas. Además, agregará una etiqueta de retención integrada que no se puede lograr con una etiqueta de retención recomendada de Microsoft 365 porque también mueve elementos al buzón de archivo. Es una etiqueta personal para el archivado después de 1 año que los usuarios pueden asignar a los elementos de su buzón cuando quieren un período de archivo más corto que el predeterminado de 3 años.

Puede seguir algunos o todos los pasos de este artículo para configurar una directiva de archivo y eliminación para buzones de su propia organización. Se recomienda probar este proceso en algunos buzones antes de implementarlo en todos los buzones de su organización.

> [!NOTE]
> Las instrucciones de este artículo usan el [portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md) y el [nuevo Centro de administración de Exchange](/exchange/features-in-new-eac).

## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Antes de configurar una directiva de archivo y eliminación

- Debe ser administrador global de su organización para realizar los pasos de este artículo.

- Al crear una nueva cuenta de usuario y asignar al usuario una licencia de Exchange Online, se crea automáticamente un buzón para el usuario. Cuando se crea el buzón, se le asigna automáticamente una directiva de retención predeterminada, denominada Directiva de MRM predeterminada. En este artículo, creará una nueva directiva de retención de MRM y, a continuación, la asignará a los buzones de usuario, reemplazando la directiva de MRM predeterminada. Un buzón de correo solo puede tener asignada una directiva de retención de MRM al mismo tiempo.

- Para obtener más información sobre las etiquetas de retención y las directivas de retención de MRM en Exchange Online, consulte [Etiquetas de retención y directivas de retención](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Paso 1: Habilitar buzones de archivo para los usuarios

El primer paso es asegurarse de que cada usuario de la organización tiene un buzón de archivo. El buzón de archivo de un usuario debe estar habilitado para que una etiqueta de retención con una acción de retención "Mover a archivo" pueda mover el elemento después de que expire la antigüedad de retención.

Para obtener instrucciones para habilitar los buzones de archivo, consulte [Habilitar buzones de archivo en Microsoft 365](enable-archive-mailboxes.md).
  
> [!NOTE]
> Puede habilitar los buzones de archivo en cualquier momento durante este proceso, siempre y cuando estén habilitados en algún momento antes de completar el proceso. Si un buzón de archivo no está habilitado, no se realiza ninguna acción en los elementos que tengan asignada una directiva de archivo o eliminación.

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación

En este paso, creará las dos etiquetas de retención personalizadas que se describieron anteriormente.
  
- Alpine House 3 Year Move to Archive (directiva de archivo personalizado)

- Alpine House Deleted Items 5 Years Delete and Allow Recovery (etiqueta personalizada para la carpeta Elementos eliminados)

Para crear nuevas etiquetas de retención, usará el [portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md).
  
1. Vaya al [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/) e inicie sesión con sus credenciales.
  
2. En el portal de cumplimiento, vaya a **Soluciones Administración** \> **del ciclo de vida de** \> datos **Exchange (heredado)** > **Etiquetas de retención de MRM**
    
    Se muestra una lista de las etiquetas de retención de su organización.

### <a name="create-a-custom-archive-default-policy-tag"></a>Creación de una etiqueta de directiva predeterminada de archivo personalizado
  
En primer lugar, creará una etiqueta de directiva predeterminada de archivo (DPT) personalizada que moverá los elementos al buzón de archivo después de 3 años.
  
1. En la página **Etiquetas de retención de MRM** , seleccione **+ Nueva etiqueta** y, a continuación, en la página Nombre de la **etiqueta** , escriba un nombre para la nueva etiqueta de retención y una descripción opcional que explique el propósito de la etiqueta de retención personalizada.
    
    En nuestro escenario de ejemplo, se denominará esta etiqueta "Alpine House 3 Year Move to Archive".

2. En la página **Definir cómo se aplicará la etiqueta**, seleccione **Automáticamente en todo el buzón (valor predeterminado).**

2. En la página **Definir configuración de retención** , complete los campos siguientes: 
  
   1. **Cuando los elementos alcanzan la edad siguiente (en días)** Escriba la duración del período de retención. En este escenario, los elementos se moverán al buzón de archivo después de 1095 días (3 años). 

   2. Para la **acción de retención** , seleccione **Mover elemento al archivo** para mover elementos al buzón de archivo cuando expire el período de retención.

4. Seleccione **Siguiente** y, a continuación, revise y envíe para crear el DPT de archivo personalizado.

El nuevo archivo DPT se muestra en la lista de etiquetas de retención.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Creación de una etiqueta de directiva de retención personalizada para la carpeta Elementos eliminados
  
La segunda etiqueta de retención que se va a crear es una etiqueta de directiva de retención personalizada (RPT) para la carpeta Elementos eliminados. Esta etiqueta eliminará los elementos de la carpeta Elementos eliminados después de 5 años y proporciona un período de recuperación en el que los usuarios pueden usar la herramienta Recuperar elementos eliminados para recuperar un elemento.

1. De nuevo en la página **Etiquetas de retención de MRM** , seleccione **+ Nueva etiqueta** y, en la página Nombre de la **etiqueta** , escriba un nombre para la nueva etiqueta de retención y una descripción opcional que explique el propósito de la etiqueta de retención personalizada.
    
    En nuestro escenario de ejemplo, denominaremos esta etiqueta "Alpine House Deleted Items 5 Years Delete and Allow Recovery".

2. En la página **Definir cómo se aplicará la etiqueta** , seleccione **Automáticamente en la carpeta predeterminada** y, a continuación, en la opción **Aplicar etiqueta a esta carpeta** , seleccione **Elementos eliminados**.

3. En la página **Definir configuración de retención** , complete los campos siguientes: 
  
   1. **Cuando los elementos alcanzan la edad siguiente (en días)** Escriba la duración del período de retención. En este escenario, los elementos se eliminarán después de 1825 días (5 años).

   2. Para la **acción de retención** , seleccione **Eliminar y permita** que la recuperación elimine elementos cuando expire el período de retención, pero permita a los usuarios recuperar un elemento eliminado dentro del período de retención de elementos eliminados (que de forma predeterminada es de 14 días).

4. Seleccione **Siguiente** y, a continuación, revise y envíe para crear el DPT de eliminación personalizada.

El nuevo RPT se muestra en la lista de etiquetas de retención.

## <a name="step-3-create-a-new-retention-policy"></a>Paso 3: Crear una nueva directiva de retención

Después de crear las etiquetas de retención personalizadas, el siguiente paso es crear una nueva directiva de retención y agregar las etiquetas de retención. Agregará las dos etiquetas de retención personalizadas que creó en el paso 2 y las etiquetas integradas que se mencionaron en la primera sección. En el paso 4, asignará esta nueva directiva de retención a los buzones de usuario.
  
1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Data Lifecycle Management** \> **Exchange (legacy)****MRM Retention policies (Directivas de retención de MRM** de Administración del ciclo de vida de datos (heredado). > 

2. En la página **Directivas de retención de MRM** , seleccione **Nueva directiva**.

3. En el cuadro **Nombre** , escriba un nombre para la nueva directiva de retención; por ejemplo, **Alpine House Archive and Deletion Policy**.

4. Seleccione **+ Agregar etiqueta**.
    
    Se muestra una lista de las etiquetas de retención de su organización, que incluye las etiquetas personalizadas que creó en el paso 2.

5. Agregue las 3 etiquetas de retención que se describen con más detalle en la sección [Más información](#more-information) :
    
    - **Alpine House 3 Year Move to Archive** : la etiqueta de directiva predeterminada de archivo personalizada creada en el paso 2 de estas instrucciones
    - **Alpine House Deleted Items 5 Years Delete and Allow Recovery** - the custom tag for the Deleted Items folder created in step 2 of these instructions
    - **Traslado personal de 1 año al archivo** : una etiqueta integrada preconfigurada
    
    Para agregar estas etiquetas de retención, selecciónelas y, a continuación, seleccione **Agregar**.

7. En la página **Configurar la directiva** , seleccione **Siguiente** para revisar y enviar la nueva directiva.

La nueva directiva de retención se muestra en la lista. Selecciónelo para mostrar las etiquetas de retención vinculadas a ella en el panel de detalles.

## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Paso 4: Asignar la nueva directiva de retención a buzones de usuario

Cuando se crea un nuevo buzón de correo, se le asigna de forma predeterminada una directiva de retención denominada Directiva de MRM predeterminada. En este paso, reemplazará esta directiva de retención asignando la nueva directiva de retención que creó en el paso 3 a los buzones de usuario de su organización. 

El reemplazo es necesario porque un buzón solo puede tener asignada una directiva de retención de MRM a la vez. En este paso se supone que asignará la nueva directiva a todos los buzones de correo de la organización.

Para seguir estos pasos, asegúrese de usar el [nuevo Centro de administración de Exchange](/exchange/features-in-new-eac), en lugar de la versión clásica.
  
1. Inicie sesión en el nuevo [Centro de administración de Exchange (EAC)](https://admin.exchange.microsoft.com/) y vaya a **Buzones de destinatarios** > .

    Se muestra una lista de todos los buzones de correo de usuario de la organización.

2. Seleccione todos los buzones seleccionando el cuadro Nombre para **mostrar**. 

3. Seleccione la opción **Directivas de buzón** .

4. En el panel flotante **Directivas de buzón** , en **Directiva de retención**, seleccione la directiva de retención que creó en el paso 3; por ejemplo, **Alpine House Archive y Retention Policy**.

5. Seleccione **Guardar** para guardar la nueva asignación de directiva de retención.

6. Para comprobar que la nueva directiva de retención se asignó a los buzones:

   1. Seleccione un buzón en la página **Buzones** .

   2. En la página de propiedades del buzón del usuario seleccionado, seleccione **Buzón**.
    
    El nombre de la nueva directiva asignada al buzón se muestra para la **directiva de retención**.

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
    |Alpine House elementos eliminados 5 años eliminar y permitir la recuperación  <br/> |Elimina elementos de la carpeta Elementos eliminados que tienen 5 años. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación. Consulte la siguiente entrada de lista para obtener más información. <br/> |Personalizado (consulte [Paso 2: Crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva de retención (elementos eliminados); esta etiqueta se aplica automáticamente a los elementos de la carpeta Elementos eliminados.  <br/> |
    |Mover al archivo después de 1 años en forma personal  <br/> |Mueve los elementos al buzón de archivo después de 1 año.  <br/> |Integrado  <br/> |Personal; los usuarios pueden aplicar esta etiqueta.   |
    
    
- Los usuarios pueden usar la herramienta Recuperar elementos eliminados en Outlook y Outlook en la Web (anteriormente conocida como Outlook Web App) para recuperar un elemento eliminado dentro del período de retención de elementos eliminados, que de forma predeterminada es de 14 días en Exchange Online. Un administrador puede usar Exchange Online PowerShell para aumentar el período de retención de elementos eliminados a un máximo de 30 días. Para obtener más información, vea: [Recuperar elementos eliminados en Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) y [Cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).
  
