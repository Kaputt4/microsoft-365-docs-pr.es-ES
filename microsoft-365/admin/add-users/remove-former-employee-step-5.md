---
title: 'Paso 5: Dar a otro empleado acceso a los datos de OneDrive y Outlook'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga los pasos de este artículo para acceder a los datos de OneDrive y Outlook de un empleado anterior, realizar una copia de seguridad de ellos y elegir si desea conceder acceso a otro empleado.
ms.openlocfilehash: 9fa2508dbfabe2260bd5946b7b9e57aa8c054317
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721722"
---
# <a name="step-5---give-another-employee-access-to-onedrive-and-outlook-data"></a>Paso 5: Dar a otro empleado acceso a los datos de OneDrive y Outlook

Cuando un empleado abandona la organización, querrá tener acceso a sus datos de OneDrive y Outlook, realizar una copia de seguridad de ellos y elegir si se lo da a otro empleado.
  
## <a name="access-a-former-users-onedrive-documents"></a>Acceso a los documentos de OneDrive de un usuario anterior

Si quita la licencia de un usuario pero no elimina la cuenta, puede acceder al contenido en OneDrive del usuario. Si elimina la cuenta del usuario, tiene 30 días de forma predeterminada para acceder a los datos de OneDrive del usuario anterior. [Obtenga información sobre cómo establecer la retención de OneDrive para usuarios eliminados](/onedrive/set-retention). Si no [restaura una cuenta de usuario](/office365/admin/add-users/restore-user) dentro de este tiempo, se elimina su contenido de OneDrive.

Para conservar los archivos de OneDrive de un usuario anterior, primero dé acceso a su OneDrive y, a continuación, mueva los archivos que desea conservar.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

2. Seleccione un usuario.

3. En la página de propiedades del usuario, seleccione **OneDrive**. En **Obtener acceso a archivos**, seleccione **Crear vínculo a archivos**.

4. Seleccione el vínculo para abrir la ubicación del archivo. Descargue los archivos en el equipo o seleccione **Mover a** o **Copiar en** para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.

> [!NOTE]
> Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.<br/>
> Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.  

También puede conceder acceso a otro usuario para acceder a OneDrive de un antiguo empleado.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> como administrador global o administrador de SharePoint.

    Si recibe un mensaje que indica que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.

2. En el panel izquierdo, seleccione **Administración centros** \> **de SharePoint**. (Es posible que deba seleccionar **Mostrar todo** para ver la lista de centros de administración).

3. Si aparece el Centro de administración de SharePoint clásico, seleccione **Abrir ahora** en la parte superior de la página para abrir el Centro de administración de SharePoint.

4. En el panel izquierdo, seleccione **Más características**.

5. En **Perfiles de usuario**, seleccione **Abrir**.

6. En **Personas**, seleccione **Administrar perfiles de usuario**.

7. Escriba el nombre del empleado anterior y seleccione **Buscar**.

8. Haga clic con el botón derecho en el usuario y elija **Administrar propietarios de colecciones de sitios**.

9. Agregue el usuario a **los administradores de la colección de sitios** y seleccione **Aceptar**.

10. El usuario ahora podrá acceder a OneDrive del antiguo empleado mediante la dirección URL de OneDrive. 

### <a name="revoke-admin-access-to-a-users-onedrive"></a>Revocación del acceso de administrador a OneDrive de un usuario

Puede acceder al contenido en OneDrive de un usuario, pero es posible que quiera quitar el acceso cuando ya no lo necesite.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> como administrador global o administrador de SharePoint.

    Si recibe un mensaje que indica que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.

2. En el panel izquierdo, seleccione **Administración centros** \> **de SharePoint**. (Es posible que deba seleccionar **Mostrar todo** para ver la lista de centros de administración).

3. Si aparece el Centro de administración de SharePoint clásico, seleccione **Abrir ahora** en la parte superior de la página para abrir el Centro de administración de SharePoint.

4. En el panel izquierdo, seleccione **Más características**.

5. En **Perfiles de usuario**, seleccione **Abrir**.

6. En **Personas**, seleccione **Administrar perfiles de usuario**.

7. Escriba el nombre del usuario y seleccione **Buscar**.

8. Haga clic con el botón derecho en el usuario y elija **Administrar propietarios de colecciones de sitios**.

9. Quite la persona que ya no necesita acceso a los datos del usuario y, a continuación, seleccione **Aceptar**.

## <a name="access-the-outlook-data-of-a-former-user"></a>Acceso a los datos de Outlook de un usuario anterior

Para guardar los mensajes de correo electrónico, el calendario, las tareas y los contactos del empleado anterior, exporte la información a un archivo de datos de Outlook (.pst).
  
1. [Agregue el correo electrónico del empleado anterior](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) a Outlook. (Si [restablece la contraseña del usuario](reset-passwords.md), puede establecerla en algo que solo sabe).

2. En Outlook, seleccione **Archivo**.

    ![Así es como se ve la cinta de opciones en Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Seleccione **Abrir &amp; exportar** \> **importación/exportación**.

    ![Comando Import/Export en la vista Backstage.](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Seleccione **Exportar a un archivo** y, a continuación, seleccione **Siguiente**.

    ![Exportar a una opción de archivo en el Asistente para importación y exportación.](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Seleccione **Archivo de datos de Outlook (.pst)** y, después, haga clic en **Siguiente**.

6. Seleccione la cuenta que desea exportar; para ello, seleccione el nombre o la dirección de correo electrónico, como Mailbox - Anne Weiler o anne@contoso.com. Si desea exportar todo lo que hay en su cuenta, incluido el correo, el calendario, los contactos, las tareas y las notas, asegúrese de que la casilla **Incluir subcarpetas** esté activada.

    > [!NOTE]
    > Puede exportar una cuenta a la vez. Si desea exportar varias cuentas, después de exportar una cuenta, repita estos pasos.
  
    ![Cuadro de diálogo Exportar archivo de datos de Outlook con la carpeta superior seleccionada e Incluir subcarpetas activadas.](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Seleccione **Siguiente**.

8. Seleccione **Examinar** para seleccionar dónde guardar el archivo de datos de Outlook (.pst). Escriba un  *nombre de archivo* y, a continuación, seleccione **Aceptar** para continuar.

    > [!NOTE]
    > Si ha usado la exportación antes, aparecerán la ubicación de la carpeta anterior y el nombre de archivo. Escriba un *nombre de archivo diferente* antes de seleccionar **Aceptar**.
  
9. Si va a exportar a un Archivo de datos de Outlook (.pst) existente, en **Opciones**, especifique qué desea hacer cuando exporte elementos que ya existen en el archivo.

10. Seleccione **Finalizar**.

Outlook inicia la exportación inmediatamente a menos que se cree un nuevo archivo de datos de Outlook (.pst) o se use un archivo protegido con contraseña.
  
- Si va a crear un archivo de datos de Outlook (.pst), una contraseña opcional puede ayudar a proteger el archivo. Cuando aparezca el cuadro de diálogo **Crear archivo de datos de Outlook** , escriba la *contraseña* en los cuadros **Contraseña** y **Comprobar contraseña** y, a continuación, seleccione **Aceptar**. En el cuadro **de diálogo Contraseña del archivo de datos de Outlook** , escriba la *contraseña* y, a continuación, seleccione **Aceptar**.

- Si va a exportar a un archivo de datos de Outlook (.pst) existente protegido con contraseña, en el cuadro de diálogo **Contraseña del archivo de datos de Outlook** , escriba la *contraseña* y, a continuación, seleccione **Aceptar**.

Vea cómo [exportar o hacer copias de seguridad de correo electrónico, contactos y calendario a un archivo .pst de Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) en Outlook 2010.

  > [!NOTE]
  > De forma predeterminada, el correo electrónico está disponible sin conexión durante un período de 12 meses. Si es necesario, vea cómo [aumentar los datos disponibles sin conexión](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).

### <a name="give-another-user-access-to-a-former-users-email"></a>Conceder a otro usuario acceso al correo electrónico de un usuario anterior

Para dar acceso a los mensajes de correo electrónico, el calendario, las tareas y los contactos del empleado anterior a otro empleado, importe la información a la bandeja de entrada de Outlook de otro empleado.

> [!NOTE]
> También puede [convertir el buzón del usuario anterior en un buzón compartido](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) o [reenviar el correo electrónico de un antiguo empleado a otro empleado](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).

1. En Outlook, vaya a **Archivo** \> **Abrir &amp; exportación** \> **Importación/Exportación**.

    Se inicia el Asistente para importación y exportación.

2. Seleccione **Importar de otro programa o archivo** y, luego, **Siguiente**.

    ![Asistente para importación y exportación.](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Seleccione **Archivo de datos de Outlook (.pst)** y seleccione **Siguiente**.

4. Vaya al archivo .pst que desea importar.

5. En **Opciones**, elija cómo desea tratar los valores duplicados.

6. Seleccione **Siguiente**.

7. Si se asignó una contraseña al archivo de datos de Outlook (.pst), escriba la contraseña y, a continuación, seleccione **Aceptar**.

8. Establezca las opciones para importar elementos. Normalmente, no es necesario cambiar la configuración predeterminada.

9. Seleccione **Finalizar**.

> [!NOTE]
> Los pasos siguen siendo los mismos para acceder a los datos de OneDrive y correo electrónico de un usuario existente.

> [!TIP]
> Si desea importar o restaurar solo algunos elementos de un archivo de datos de Outlook (.pst), puede abrir el archivo de datos de Outlook. A continuación, en el panel de navegación, arrastre los elementos de las carpetas de archivos de datos de Outlook a las carpetas existentes de Outlook.

## <a name="related-content"></a>Contenido relacionado

[Agregar y quitar administradores en una cuenta de OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (artículo)

[Restauración de un OneDrive eliminado](/onedrive/restore-deleted-onedrive) (artículo)

[Retención y eliminación de OneDrive](/onedrive/retention-and-deletion) (artículo)

[Compartir archivos y carpetas de OneDrive](https://support.microsoft.com/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07)
