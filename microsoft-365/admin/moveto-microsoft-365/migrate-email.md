---
title: Migración del calendario y el correo electrónico empresarial desde Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo migrar correo electrónico, contactos y calendario de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: be7637816f80ecba3c56db644114d5ddb00caeb7
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602046"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migración del calendario y el correo electrónico empresarial desde Google Workspace

Consulte la [ayuda para pequeñas empresas de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

## <a name="watch-migrate-business-email-and-calendar-from-google-workspace"></a>Inspección: Migración del calendario y el correo electrónico empresarial desde Google Workspace

Echa un vistazo a este vídeo y a otros usuarios en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198034).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Puede usar una migración ejecutada por el administrador para Exchange Online desde Google Workspace. Puede migrar el correo a la vez o en fases. En los pasos siguientes se muestra cómo migrar los datos de correo electrónico a la vez. Para obtener más información, consulte [Realización de una migración de G Suite](/exchange/mailbox-migration/perform-g-suite-migration).

El proceso de migración realiza varios pasos y puede tardar de varias horas a un par de días en función de la cantidad de datos que va a migrar.

### <a name="create-a-google-service-account"></a>Creación de una cuenta de servicio de Google

1. Con un explorador Chrome, inicie sesión en la consola de administración de Google Workspace en [admin.google.com](https://admin.google.com). 
1. En una nueva pestaña o ventana, vaya a la página [Cuentas de servicio](https://console.developers.google.com/iam-admin/serviceaccounts) . 
1. Seleccione **Crear proyecto**, asigne un nombre al proyecto y elija **Crear**. 
1. Seleccione **Crear cuenta de servicio**, escriba un nombre, elija **Crear** y, a continuación, **Listo**. 
1. Abra el menú **Acciones** , seleccione **Editar** y tome nota del identificador único. Necesitará este identificador más adelante en el proceso. 
1. Abra la sección **Mostrar delegación en todo el dominio** . 
1. Seleccione **Habilitar delegación en todo el dominio de G Suite**, escriba un nombre de producto para la pantalla de consentimiento y elija **Guardar**. 

    > [!NOTE]
    > El proceso de migración no usa el nombre del producto, pero es necesario para guardarlo en el cuadro de diálogo.     

1. Vuelva a abrir el menú **Acciones** y seleccione **Crear clave**. 
1. Elija **JSON** y, a continuación, **Crear**. 

     La clave privada se guarda en la carpeta de descarga del dispositivo.
 
1. Seleccione **Cerrar**. 

### <a name="enable-api-usage-for-the-project"></a>Habilitación del uso de API para el proyecto

1. Vaya a la [página API](https://console.developers.google.com/apis/library). 
1. En la barra de búsqueda, escriba **Gmail API**.
1. Selecciónelo y, a continuación, elija **Habilitar**.
1. Repita este proceso para Google Calendar API, People API y Contacts API. 

### <a name="grant-access-to-the-service-account"></a>Concesión de acceso a la cuenta de servicio

1. Vuelva a la consola de administración de Google Workspace. 
1. Seleccione **Seguridad**, desplácese hacia abajo y abra **controles de API**. 
1. Desplácese hacia abajo y seleccione **Administrar delegación en todo el dominio**.
1. Seleccione **Agregar nuevo** y escriba el identificador de cliente que anotó anteriormente.
1. A continuación, escriba los ámbitos de OAuth para las API de Google. Están disponibles en [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) en el paso 5 y son:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Elija **Autorizar**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Creación de un subdominio para correo que vaya a Microsoft 365

1. Vuelva a la consola de **administración de Google Workspace** .
1. Seleccione **Dominios**, **Administrar dominios** y, a continuación, **Agregar un alias de dominio**. 
1. Escriba un alias de dominio como `m365.contoso.com`.
1. A continuación, seleccione **Continuar y compruebe la propiedad del dominio**. 

    La comprobación del dominio suele tardar unos minutos, pero puede tardar hasta 48 horas.

1. Ve al [Centro de administración de Microsoft 365](https://admin.microsoft.com).
1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, seleccione **Mostrar todos los** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a> **de configuración** >  y, a continuación, **Agregar dominio**. 
1. Escriba el subdominio que creó anteriormente y, a continuación, seleccione **Usar este dominio**. 
1. Para conectar el dominio, seleccione **Continuar**. 
1. Desplácese hacia abajo y tome nota de los registros MX, CNAME y TXT. 
1. Vuelva a la **consola de administración de Google**.
1. Seleccione **Dominios**, **Administrar dominios**, **Comprobar detalles** y, a continuación, **Administrar dominio**. 
1. En el panel de navegación izquierdo, elija **DNS** y desplácese hacia abajo hasta **Registros de recursos personalizados**. 
1. Abra la lista desplegable tipo de registro y seleccione **MX**, escriba o copie y pegue la información de registro MX que anotó anteriormente y, a continuación, elija **Agregar**. 
1. Repita el proceso para el registro CNAME y el registro TXT. 

    Estos cambios pueden tardar algún tiempo en surtir efecto.  

1. Vuelva al lugar donde lo dejó en Centro de administración de Microsoft 365 y seleccione **Continuar**. 

El dominio ya está configurado.  

### <a name="create-email-aliases-in-microsoft-365"></a>Creación de alias de correo electrónico en Microsoft 365

Antes de comenzar la migración, debe crear alias de correo electrónico para los usuarios con el nuevo subdominio. 

1. Para iniciar el paso siguiente, en el Asistente para **agregar dominios** de la Centro de administración de Microsoft 365, seleccione **Ir a usuarios activos**. 
1. Seleccione un usuario y, a continuación, **Administrar nombre de usuario y correo electrónico**. 
1. En la lista desplegable **Dominios** , seleccione el subdominio que creó anteriormente. 
1. Escriba un nombre de usuario, seleccione **Agregar**, **Guardar cambios** y cierre la ventana. 

    Repita este proceso para cada usuario. 

### <a name="start-the-migration-process"></a>Inicio del proceso de migración

Una vez que haya terminado, estará listo para migrar. 

1. En el panel de navegación izquierdo del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, desplácese hacia abajo hasta **Administración centros** y seleccione **Exchange**. 
1. En **destinatarios**, elija **migración**, seleccione **Nuevo**, **Migrar a Exchange Online**, elija **Migración de G Suite** y, a continuación, **Siguiente**. 
1. Cree un archivo CSV con una lista de los buzones que desea migrar. Asegúrese de que el archivo sigue este formato: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Para obtener más información, consulte [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Seleccione **Elegir archivo**, vaya al archivo CSV, selecciónelo, seleccione **Abrir** y, a continuación, **Siguiente**. 
1. Compruebe la dirección de correo electrónico del administrador que desea usar para las pruebas. 
1. Seleccione **Elegir archivo**, vaya al archivo JSON que creó anteriormente (normalmente en la carpeta Descargas del equipo), selecciónelo, seleccione **Abrir** y, a continuación, **Siguiente**. 
1. Escriba un nombre en el **campo Nuevo nombre del lote de migración**.
1. Escriba el subdominio que creó en el campo **Dominio de entrega de destino** , seleccione **Siguiente** y, a continuación, **Nuevo**. 
1. Una vez guardada la información, seleccione **Aceptar**. 

    Ahora puede ver el estado de la migración. 

1. Una vez transcurrido algún tiempo, en función del número de usuarios que va a migrar, seleccione **Actualizar**. 
1. Una vez que el estado haya cambiado a **Sincronizado**, seleccione **Completar este lote de migración** y, a continuación, **Sí**. 
1. Una vez completado el proceso, el estado cambiará a **Completado**. 
1. Si lo desea, puede seleccionar **Ver detalles** para obtener más información sobre la migración. 
1. Seleccione **Cerrar**. 
1. Abra Outlook para comprobar que todos los correos electrónicos de Google Workspace se migraron correctamente.
También puede repetirlo para los elementos y contactos del calendario.
