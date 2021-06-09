---
title: Migrar el calendario y el correo electrónico empresarial desde Google Workspace
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
description: Aprende a migrar el correo electrónico, los contactos y el calendario de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913627"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="4ad90-103">Migrar el calendario y el correo electrónico empresarial desde Google Workspace</span><span class="sxs-lookup"><span data-stu-id="4ad90-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="4ad90-104">Puedes usar una migración de administración a Exchange Online desde Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="4ad90-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="4ad90-105">Puede migrar el correo a la vez o por fases.</span><span class="sxs-lookup"><span data-stu-id="4ad90-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="4ad90-106">Los pasos siguientes muestran cómo migrar los datos de correo electrónico a la vez.</span><span class="sxs-lookup"><span data-stu-id="4ad90-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="4ad90-107">Para obtener más información, [consulta Realizar una migración de G Suite](/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="4ad90-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="4ad90-108">El proceso de migración toma varios pasos y puede tardar de varias horas a un par de días en función de la cantidad de datos que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="4ad90-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="4ad90-109">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="4ad90-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="4ad90-110">Crear una cuenta de servicio de Google</span><span class="sxs-lookup"><span data-stu-id="4ad90-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="4ad90-111">Con un explorador Chrome, inicie sesión en la consola de administración de Google Workspace en [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="4ad90-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="4ad90-112">En una nueva pestaña o ventana, vaya a la página [Cuentas de](https://console.developers.google.com/iam-admin/serviceaccounts) servicio.</span><span class="sxs-lookup"><span data-stu-id="4ad90-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="4ad90-113">Seleccione **Crear proyecto,** asigne un nombre al proyecto y elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="4ad90-114">Seleccione **Crear cuenta de servicio,** escriba un nombre, elija **Crear** y, a continuación, **Listo**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="4ad90-115">Abra el **menú** Acciones, **seleccione Editar** y tome nota del identificador único.</span><span class="sxs-lookup"><span data-stu-id="4ad90-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="4ad90-116">Necesitará este identificador más adelante en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4ad90-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="4ad90-117">Abra la **sección Mostrar delegación de todo el** dominio.</span><span class="sxs-lookup"><span data-stu-id="4ad90-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="4ad90-118">Seleccione Habilitar la delegación de todo el dominio de **G Suite,** escriba un nombre de producto para la pantalla de consentimiento y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="4ad90-119">El proceso de migración no usa el nombre del producto, pero es necesario guardarlo en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4ad90-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="4ad90-120">Vuelva a **abrir el menú** Acciones y seleccione Crear **clave**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="4ad90-121">Elija **JSON** y, a **continuación, Cree**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="4ad90-122">La clave privada se guarda en la carpeta de descarga del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ad90-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="4ad90-123">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="4ad90-124">Habilitar el uso de la API para el proyecto</span><span class="sxs-lookup"><span data-stu-id="4ad90-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="4ad90-125">Vaya a la [página API](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="4ad90-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="4ad90-126">En la barra de búsqueda, escriba **API de Gmail**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="4ad90-127">Selecciónelo y, a continuación, **elija Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="4ad90-128">Repita este proceso para la API de Calendario de Google y la API de contactos.</span><span class="sxs-lookup"><span data-stu-id="4ad90-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="4ad90-129">Conceder acceso a la cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="4ad90-129">Grant access to the service account</span></span>

1. <span data-ttu-id="4ad90-130">Vuelva a la consola de administración de Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="4ad90-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="4ad90-131">Seleccione **Seguridad,** desplácese hacia abajo y abra **los controles de API**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="4ad90-132">Desplácese hacia abajo y **seleccione Administrar delegación en todo el dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="4ad90-133">Seleccione **Agregar nuevo** y escriba el id. de cliente del que hizo nota anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4ad90-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="4ad90-134">A continuación, escriba los ámbitos de OAuth para las API de Google.</span><span class="sxs-lookup"><span data-stu-id="4ad90-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="4ad90-135">Estas están disponibles en [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) en el paso 5 y son:</span><span class="sxs-lookup"><span data-stu-id="4ad90-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="4ad90-136">Elija **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="4ad90-137">Crear un subdominio para correo que vaya a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ad90-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="4ad90-138">Vuelva a la consola **de administración de Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="4ad90-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="4ad90-139">Seleccione **Dominios**, **Administrar dominios** y, a continuación, Agregar un alias de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="4ad90-140">Escriba un alias de dominio como `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="4ad90-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="4ad90-141">A **continuación, seleccione Continuar y compruebe la propiedad del dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="4ad90-142">La comprobación del dominio suele tardar unos minutos, pero puede tardar hasta 48 horas.</span><span class="sxs-lookup"><span data-stu-id="4ad90-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="4ad90-143">Vaya al Centro [Microsoft 365 administración.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4ad90-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="4ad90-144">En el **Microsoft 365 de administración**, en la navegación izquierda, seleccione **Mostrar** todo , **Configuración**, **Dominios** y, a continuación, **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="4ad90-145">Escriba el subdominio que creó anteriormente y, a continuación, **seleccione Usar este dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="4ad90-146">Para conectar el dominio, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="4ad90-147">Desplácese hacia abajo y tome nota de los registros MX, los registros CNAME y los registros TXT.</span><span class="sxs-lookup"><span data-stu-id="4ad90-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="4ad90-148">Vuelva a la **consola de administración de Google**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="4ad90-149">Seleccione **Dominios**, seleccione **Administrar dominios**, Comprobar **detalles** y, a continuación, Administrar **dominio**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="4ad90-150">En la navegación izquierda, elija **DNS** y desplácese hacia abajo hasta **Registros de recursos personalizados.**</span><span class="sxs-lookup"><span data-stu-id="4ad90-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="4ad90-151">Abra el desplegable tipo de registro y **seleccione MX**, escriba o copie y pegue la información de registro MX que ha indicado anteriormente y, a continuación, **elija Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="4ad90-152">Repita el proceso para el registro CNAME y el registro TXT.</span><span class="sxs-lookup"><span data-stu-id="4ad90-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="4ad90-153">Estos cambios pueden tardar algún tiempo en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="4ad90-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="4ad90-154">Vuelva a donde lo dejó en Microsoft 365 **centro de administración** y seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="4ad90-155">El dominio ya está configurado.</span><span class="sxs-lookup"><span data-stu-id="4ad90-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="4ad90-156">Crear alias de correo electrónico en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ad90-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="4ad90-157">Antes de que pueda comenzar la migración, debe crear alias de correo electrónico para los usuarios con el nuevo subdominio.</span><span class="sxs-lookup"><span data-stu-id="4ad90-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="4ad90-158">Para iniciar el siguiente  paso, en el Asistente para agregar dominios en el Centro de administración de Microsoft 365, seleccione **Ir a Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="4ad90-159">Seleccione un usuario y, a continuación, **Administrar nombre de usuario y correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="4ad90-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="4ad90-160">En el **desplegable Dominios,** seleccione el subdominio que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4ad90-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="4ad90-161">Escriba un nombre de usuario, **seleccione Agregar**, **Guardar cambios** y cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="4ad90-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="4ad90-162">Repita este proceso para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="4ad90-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="4ad90-163">Iniciar el proceso de migración</span><span class="sxs-lookup"><span data-stu-id="4ad90-163">Start the migration process</span></span>

<span data-ttu-id="4ad90-164">Una vez que haya terminado, estará listo para migrar.</span><span class="sxs-lookup"><span data-stu-id="4ad90-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="4ad90-165">En el navegador izquierdo del centro **de administración Microsoft 365**, desplácese hacia abajo hasta **Centros** de administración y **seleccione Exchange**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="4ad90-166">En **destinatarios**, elija **migración**, seleccione **Nuevo**, Migrar **a Exchange Online**, elija Migración de G **Suite** y, a continuación, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="4ad90-167">Cree un archivo CSV con una lista de los buzones que desea migrar.</span><span class="sxs-lookup"><span data-stu-id="4ad90-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="4ad90-168">Asegúrese de que el archivo sigue este formato:</span><span class="sxs-lookup"><span data-stu-id="4ad90-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="4ad90-169">Para obtener más [información, vea aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="4ad90-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="4ad90-170">Seleccione **Elegir archivo**, vaya al archivo CSV, selecciónelo, seleccione **Abrir** y, a continuación, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="4ad90-171">Compruebe la dirección de correo electrónico de administrador que desea usar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="4ad90-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="4ad90-172">Seleccione **Elegir archivo**, vaya al archivo JSON que creó anteriormente (normalmente en la carpeta Descargas del equipo), selecciónelo, seleccione **Abrir** y, a continuación, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="4ad90-173">Escriba un nombre en el **campo Nuevo nombre de lote de migración.**</span><span class="sxs-lookup"><span data-stu-id="4ad90-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="4ad90-174">Escriba el subdominio que creó en el **campo Dominio** de entrega de destino, **seleccione Siguiente** y, a continuación, **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="4ad90-175">Una vez guardada la información, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="4ad90-176">Ahora puede ver el estado de la migración.</span><span class="sxs-lookup"><span data-stu-id="4ad90-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="4ad90-177">Una vez transcurrido algún tiempo, según el número de usuarios que va a migrar, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="4ad90-178">Una vez que el estado ha cambiado **a Sincronizado,** seleccione **Completar este lote de migración,** a continuación, **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="4ad90-179">Una vez completado el proceso, el estado cambiará a **Completado.**</span><span class="sxs-lookup"><span data-stu-id="4ad90-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="4ad90-180">Si lo desea, puede seleccionar **Ver detalles** para obtener más información sobre la migración.</span><span class="sxs-lookup"><span data-stu-id="4ad90-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="4ad90-181">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4ad90-181">Select **Close**.</span></span> 
1. <span data-ttu-id="4ad90-182">Abra Outlook para comprobar que todos los correos electrónicos de Google Workspace se migraron correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ad90-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="4ad90-183">También puedes repetir esto para los elementos y contactos del calendario.</span><span class="sxs-lookup"><span data-stu-id="4ad90-183">You can repeat this for calendar items and contacts as well.</span></span>