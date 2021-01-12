---
title: Migrar el correo electrónico y el calendario empresariales desde Google Workspace
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo migrar el correo electrónico, los contactos y el calendario de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794710"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrar el correo electrónico y el calendario empresariales desde Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Puede usar una migración ejecutado por el administrador a Exchange Online desde Google Workspace. Puede migrar el correo a la vez o por fases. Los siguientes pasos muestran cómo migrar los datos de correo electrónico a la vez. Para obtener más información, vea [Realizar una migración de G Suite.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

El proceso de migración toma varios pasos y puede tardar de varias horas a un par de días según la cantidad de datos que se va a migrar.

## <a name="try-it"></a>¿Se atreve?

### <a name="create-a-google-service-account"></a>Crear una cuenta de servicio de Google

1. Con un explorador Chrome, inicie sesión en la consola de administración de Google Workspace [en admin.google.com](https://admin.google.com). 
1. En una nueva pestaña o ventana, vaya a la página [Cuentas de](https://console.developers.google.com/iam-admin/serviceaccounts) servicio. 
1. Seleccione **Crear proyecto,** asigne un nombre al proyecto y elija **Crear**. 
1. Seleccione **Crear cuenta de servicio,** escriba un nombre, elija **Crear** y, a continuación, **Listo.** 
1. Abra el **menú** Acciones, **seleccione Editar** y tome nota del identificador único. Necesitará este identificador más adelante en el proceso. 
1. Abra la **sección Mostrar delegación en todo el** dominio. 
1. Seleccione **Habilitar delegación en todo el dominio de G Suite,** escriba un nombre de producto para la pantalla de consentimiento y elija **Guardar.** 

    > [!NOTE]
> El proceso de migración no usa el nombre del producto, pero es necesario para guardarlo en el cuadro de diálogo.     

1. Vuelva a abrir **el menú** Acciones y seleccione **Crear clave.** 
1. Elija **JSON** y, a **continuación, cree**. 

     La clave privada se guarda en la carpeta de descarga del dispositivo.
 
1. Seleccione **Cerrar**. 

### <a name="enable-api-usage-for-the-project"></a>Habilitar el uso de api para el proyecto

1. Vaya a la [página API.](https://console.developers.google.com/apis/library) 
1. En la barra de búsqueda, escriba **la API de Gmail.**
1. Selecciónelo y, a continuación, **elija Habilitar**.
1. Repita este proceso para la API de calendario de Google y la API de contactos. 

### <a name="grant-access-to-the-service-account"></a>Conceder acceso a la cuenta de servicio

1. Vuelva a la consola de administración de Google Workspace. 
1. Seleccione **Seguridad,** desplácese hacia abajo y abra los controles **de la API.** 
1. Desplácese hacia abajo y seleccione **Administrar delegación en todo el dominio.**
1. Seleccione **Agregar nuevo** y escriba el id. de cliente del que hizo nota anteriormente.
1. A continuación, escribe los ámbitos de OAuth para las API de Google. Están disponibles en [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) paso 5 y son:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Elija **Autorizar**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Crear un subdominio para el correo que va a Microsoft 365

1. Vuelva a la consola **de administración de Google Workspace.**
1. Seleccione **Dominios**, **Administrar dominios** y, a continuación, Agregue un alias de **dominio.** 
1. Escriba un alias de dominio como `m365.contoso.com` .
1. A **continuación, seleccione Continuar y compruebe la propiedad del dominio.** 

    La comprobación del dominio suele tardar unos minutos, pero puede tardar hasta 48 horas.

1. Vaya al Centro [de administración de Microsoft 365.](https://admin.microsoft.com)
1. En el **Centro de administración de Microsoft 365,** en el panel de navegación izquierdo, seleccione Mostrar todo **,** **Configuración,** Dominios **y,** a continuación, **Agregar dominio.** 
1. Escriba el subdominio que creó anteriormente y, a continuación, **seleccione Usar este dominio.** 
1. Para conectar el dominio, seleccione **Continuar**. 
1. Desplácese hacia abajo y tome nota de los registros MX, CNAME y TXT. 
1. Vuelva a la consola **de administración de Google.**
1. Seleccione **Dominios,** seleccione **Administrar dominios,** **Comprobar detalles** y, a continuación, **Administrar dominio.** 
1. En el panel de navegación izquierdo, elija **DNS** y desplácese hacia abajo hasta **Registros de recursos personalizados.** 
1. Abra la lista desplegable de tipos de registro y **seleccione MX**, escriba o copie y pegue la información del registro MX que anotó anteriormente y, a continuación, **elija Agregar**. 
1. Repita el proceso para el registro CNAME y el registro TXT. 

    Estos cambios pueden tardar algún tiempo en tener efecto.  

1. Vuelva al lugar donde lo dejó en el Centro de administración de **Microsoft 365** y seleccione **Continuar.** 

Su dominio ya está configurado.  

### <a name="create-email-aliases-in-microsoft-365"></a>Crear alias de correo electrónico en Microsoft 365

Antes de que pueda comenzar la migración, debe crear alias de correo electrónico para los usuarios con el nuevo subdominio. 

1. Para iniciar el siguiente  paso, en el Asistente para agregar dominios en el Centro de administración de Microsoft 365, seleccione **Ir a Usuarios activos.** 
1. Seleccione un usuario y, a continuación, **administre el nombre de usuario y el correo electrónico.** 
1. En la **lista** desplegable Dominios, seleccione el subdominio que creó anteriormente. 
1. Escriba un nombre de usuario, **seleccione Agregar**, **Guardar cambios** y cierre la ventana. 

    Repita este proceso para cada usuario. 

### <a name="start-the-migration-process"></a>Iniciar el proceso de migración

Una vez que haya terminado, estará listo para migrar. 

1. En el panel de navegación izquierdo del Centro de administración de **Microsoft 365,** desplácese hacia abajo hasta centros de **administración** y seleccione **Exchange.** 
1. En **destinatarios,** elija **migración**, seleccione **Nuevo**, Migrar a **Exchange Online**, elija Migración de G **Suite** y, a continuación, **Siguiente**. 
1. Cree un archivo CSV con una lista de los buzones que desea migrar. Asegúrese de que el archivo tiene este formato: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Para obtener más [información, aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Seleccione **Elegir archivo,** vaya al archivo CSV, selecciónelo, **seleccione Abrir** y, a **continuación, siguiente.** 
1. Compruebe la dirección de correo electrónico de administrador que desea usar para las pruebas. 
1. Seleccione **Elegir archivo,** vaya al archivo JSON que creó anteriormente (normalmente en la carpeta Descargas del equipo), selecciónelo, seleccione **Abrir** y, a continuación, **siguiente.** 
1. Escriba un nombre en el campo **Nuevo nombre de lote de migración.**
1. Escriba el subdominio que creó en el campo Dominio de entrega **de** destino, seleccione **Siguiente** y, a continuación, **Nuevo**. 
1. Una vez guardada la información, seleccione **Aceptar**. 

    Ahora puede ver el estado de la migración. 

1. Una vez transcurrido algún tiempo, en función del número de usuarios que va a migrar, seleccione **Actualizar**. 
1. Una vez que el estado ha cambiado **a Sincronizado,** seleccione **Completar este lote de migración** y, a continuación, **Sí**. 
1. Una vez completado el proceso, el estado cambiará a **Completado.** 
1. Si lo desea, puede seleccionar Ver **detalles** para obtener más información sobre la migración. 
1. Seleccione **Cerrar**. 
1. Abra Outlook para comprobar que todos los correos electrónicos de Google Workspace se hayan migrado correctamente.
Puede repetir esto también para elementos de calendario y contactos.