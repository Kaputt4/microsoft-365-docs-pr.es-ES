---
title: Obtener acceso y realizar una copia de seguridad de los datos de un antiguo usuario
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Obtenga información sobre cómo conservar los archivos y los correos electrónicos de un empleado cuando la persona abandona la organización.
ms.openlocfilehash: 38cc44bbe602f3c8c38ca54391d0967fbafbfcf7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906317"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>Obtener acceso y realizar una copia de seguridad de los datos de un antiguo usuario


Cuando un empleado deja la organización, probablemente quiera tener acceso a sus datos (documentos y correos electrónicos) y revisarlo, hacer una copia de seguridad o entregarlo a un nuevo empleado.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>Obtener acceso a los documentos de OneDrive de un usuario anterior

Si quita la licencia de un usuario pero no elimina la cuenta, puede darnos acceso al contenido en OneDrive del usuario. Si elimina la cuenta del usuario, tiene 30 días de forma predeterminada para tener acceso a los datos de OneDrive del usuario anterior. [Obtenga información sobre cómo establecer la retención de OneDrive para usuarios eliminados.](/onedrive/set-retention) Si no restauras [una cuenta de usuario](/office365/admin/add-users/restore-user) en este tiempo, se elimina su contenido de OneDrive. 

Para conservar los archivos de OneDrive de un usuario anterior, primero dé acceso a su OneDrive y, a continuación, mueva los archivos que desee conservar. 

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  
    
2. Seleccione un usuario.

3. En el panel derecho, seleccione **OneDrive**. En **Obtener acceso a archivos,** seleccione Crear vínculo a **archivos**.

4. Seleccione el vínculo para abrir la ubicación del archivo. Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida. 

> [!NOTE]
> Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.<br/>
> Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.  

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione un usuario.

3. En el panel derecho, expanda **Configuración de OneDrive** y, a continuación, junto a **Access**, seleccione Archivos **de Access**.

4. Seleccione el vínculo para abrir la ubicación del archivo. Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida. 

> [!NOTE]
> Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.<br/>
> Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.  

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione un usuario.

3. En el panel derecho, expanda **Configuración de OneDrive** y, a continuación, junto a **Access**, seleccione Archivos **de Access**.

4. Seleccione el vínculo para abrir la ubicación del archivo. Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.  

> [!NOTE]
> Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.<br/>
> Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>Revocar el acceso de administrador a OneDrive de un usuario

Como administrador global, puedes darte acceso al contenido en OneDrive de un usuario, pero es posible que quieras quitar el acceso cuando ya no lo necesites. 

::: moniker range="o365-worldwide"

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint. 

    Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.

::: moniker-end

::: moniker range="o365-germany"

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint.

    Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.

::: moniker-end

::: moniker range="o365-21vianet"

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint.

    Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.

::: moniker-end

2. En el panel izquierdo, seleccione **Centros de administración de** \> **SharePoint**. (Es posible que deba seleccionar **Mostrar todo** para ver la lista de centros de administración).

3. Si aparece el centro de  administración clásico de SharePoint, seleccione Abrir ahora en la parte superior de la página para abrir el Centro de administración de SharePoint.

4. En el panel izquierdo, seleccione **Más características**.

5. En **Perfiles de usuario,** seleccione **Abrir**.

6. En **Personas,** seleccione **Administrar perfiles de usuario**.

7. Escriba el nombre del usuario y seleccione **Buscar**.

8. Haga clic con el botón secundario en el usuario y, a continuación, **elija Administrar propietarios de colecciones de sitios**.

9. Quite la persona que ya no necesita acceso a los datos del usuario y, a continuación, seleccione **Aceptar**.

    
## <a name="access-the-outlook-data-of-a-former-user"></a>Obtener acceso a los datos de Outlook de un usuario anterior

Para guardar los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado, exporte la información a un archivo de datos de Outlook (.pst).
  
1. [Agregue el correo electrónico del](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) antiguo empleado a Outlook (Si restablece la contraseña del usuario, puede establecerlo en algo que solo sepa). [](reset-passwords.md)
    
2. En Outlook, seleccione **Archivo**.
    
    ![Este es el aspecto de la cinta de opciones en Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Seleccione **Abrir &amp; Exportar** \> **importación/exportación**.
    
    ![Comando Import/Export en la vista Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Seleccione **Exportar a un archivo** y, a continuación, seleccione **Siguiente**.
    
    ![Exportar a una opción de archivo en el Asistente para importación y exportación](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Seleccione **Archivo de datos de Outlook (.pst)** y, a continuación, seleccione **Siguiente**.
    
6. Seleccione la cuenta que desea exportar seleccionando el nombre o la dirección de correo electrónico, como Mailbox - Anne Weiler o anne@contoso.com. Si desea exportar todo lo que hay en su cuenta, incluido el correo, el calendario, los contactos, las tareas y las notas, asegúrese de que la casilla Incluir **subcarpetas** está activada. 
    
    > [!NOTE]
    > Puede exportar una cuenta a la vez. Si desea exportar varias cuentas, después de exportar una cuenta, repita estos pasos. 
  
    ![Cuadro de diálogo Exportar archivo de datos de Outlook con la carpeta superior seleccionada e Incluir subcarpetas activadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Seleccione **Siguiente**.
    
8. Seleccione **Examinar** para seleccionar dónde guardar el archivo de datos de Outlook (.pst). Escriba un  *nombre de archivo* y, a continuación, seleccione **Aceptar** para continuar. 
    
    > [!NOTE]
    > Si ha usado la exportación antes, aparecerán la ubicación de la carpeta anterior y el nombre del archivo. Escriba un  *nombre de archivo diferente*  antes de seleccionar **Aceptar**. 
  
9. Si va a exportar a un Archivo de datos de Outlook (.pst) existente, en **Opciones**, especifique qué desea hacer cuando exporte elementos que ya existen en el archivo.
    
10. Seleccione **Finalizar**.
    
Outlook inicia la exportación inmediatamente a menos que se cree un nuevo archivo de datos de Outlook (.pst) o se utilice un archivo protegido con contraseña.
  
   - Si está creando un archivo de datos de Outlook (.pst), una contraseña opcional puede ayudar a proteger el archivo. Cuando aparezca el cuadro de diálogo  Crear archivo de  datos de **Outlook,** escriba la contraseña en los cuadros Contraseña y Comprobar contraseña y, a continuación, **seleccione Aceptar**.  En el cuadro de diálogo Contraseña del archivo de datos de **Outlook,** escriba la  *contraseña* y, a continuación, **seleccione Aceptar**.
    
  - Si está exportando a un archivo de datos de Outlook (.pst) existente protegido con contraseña, en el cuadro de diálogo Contraseña del archivo de datos de **Outlook,** escriba la contraseña y, a continuación, **seleccione Aceptar**.
    
Vea cómo exportar o hacer una copia de seguridad del [correo electrónico, los contactos](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) y el calendario a un archivo .pst de Outlook en Outlook 2010. 
  
  
  > [!NOTE]
  > De forma predeterminada, el correo electrónico está disponible sin conexión durante un período de 12 meses. Si es necesario, vea cómo aumentar [los datos disponibles sin conexión.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)
 
## <a name="give-another-user-access-to-a-former-users-email"></a>Dar acceso a otro usuario al correo electrónico de un usuario anterior 

Para dar acceso a los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado a otro empleado, importe la información a la bandeja de entrada de Outlook de otro empleado.

> [!NOTE]
> También puede convertir [el buzón del usuario](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) anterior en un buzón compartido o reenviar el correo electrónico de un antiguo empleado a otro [empleado](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).

  
1. En Outlook, vaya **a Archivo** \> **Abrir &amp; exportación** \> **Importar/Exportar**.
    
    Esto inicia el Asistente para importación y exportación.
    
2. Seleccione **Importar desde otro programa o archivo y,** a continuación, seleccione **Siguiente**.
    
    ![Asistente para importación y exportación](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Seleccione **Archivo de datos de Outlook (.pst)** y seleccione **Siguiente**.
    
4. Vaya al archivo .pst que desea importar.
    
5. En **Opciones,** elija cómo desea tratar con duplicados
    
6. Seleccione **Siguiente**.
    
7. Si se asignó una contraseña al archivo de datos de Outlook (.pst), escriba la contraseña y, a continuación, **seleccione Aceptar**.
    
8. Establezca las opciones para importar elementos. Normalmente, no es necesario cambiar la configuración predeterminada.
    
9. Seleccione **Finalizar**.

> [!NOTE]
> Los pasos siguen siendo los mismos para obtener acceso a los datos de OneDrive y correo electrónico de un usuario existente.
    
> [!TIP]
> Si desea importar o restaurar solo algunos elementos de un archivo de datos de Outlook (.pst), puede abrir el archivo de datos de Outlook. A continuación, en el panel de navegación, arrastre los elementos de las carpetas del archivo de datos de Outlook a las carpetas existentes de Outlook. 
  
  
## <a name="related-articles"></a>Artículos relacionados
[Quitar un antiguo empleado de Office 365](remove-former-employee.md)

[Agregar y quitar administradores en una cuenta de OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[Restaurar un OneDrive eliminado](/onedrive/restore-deleted-onedrive)
  
[Retención y eliminación de OneDrive](/onedrive/retention-and-deletion)
