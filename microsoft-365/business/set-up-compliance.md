---
title: Aumentar la protección contra amenazas para Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Configurar la protección contra amenazas avanzada de Office 365 y proteger los datos confidenciales.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668407"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a367b-103">Configurar las características de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a367b-103">Set up compliance features</span></span>

<span data-ttu-id="a367b-104">Su empresa de Microsoft 365 incluye características para proteger sus datos y dispositivos, y ayudarle a mantener seguros a los suyos y a los clientes la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="a367b-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a367b-105">Configurar las características de DLP</span><span class="sxs-lookup"><span data-stu-id="a367b-105">Set up DLP features</span></span>

<span data-ttu-id="a367b-106">Consulte [crear una directiva DLP a partir de una plantilla](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obtener un ejemplo sobre cómo configurar una directiva para protegerla contra información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="a367b-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a367b-107">DLP incluye varias plantillas de directiva listas para usarse para muchas configuraciones regionales diferentes.</span><span class="sxs-lookup"><span data-stu-id="a367b-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a367b-108">Por ejemplo, datos financieros de Australia, Act de información personal de Canadá, datos financieros de Estados Unidos, etc. Vea [Qué incluyen las plantillas de directiva de DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para obtener una lista completa.</span><span class="sxs-lookup"><span data-stu-id="a367b-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="a367b-109">Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla PII.</span><span class="sxs-lookup"><span data-stu-id="a367b-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a367b-110">Configurar la retención de correo electrónico con el archivado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a367b-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a367b-111">Las características de licencia de archivado de **Exchange Online** ayudan a mantener el cumplimiento normativo y preservar el contenido de correo electrónico para eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a367b-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a367b-112">También ayuda a reducir el riesgo en el caso de un litigio y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando se necesitan recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="a367b-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="a367b-113">Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="a367b-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a367b-114">**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="a367b-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a367b-115">Para poner un buzón de correo en retención por juicio, en el centro de administración:</span><span class="sxs-lookup"><span data-stu-id="a367b-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a367b-116">En el panel de navegación izquierdo, \*\*\*\* \> vaya a usuarios **activos**.</span><span class="sxs-lookup"><span data-stu-id="a367b-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a367b-117">Seleccione un usuario cuyo buzón quiera poner en retención por juicio y, en el panel usuario, expanda **configuración de correo** y, junto a **configuración adicional** , elija **Editar propiedades de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a367b-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a367b-118">En la página buzón del usuario, elija \* \* características de buzón \* \* en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **retención por juicio**.</span><span class="sxs-lookup"><span data-stu-id="a367b-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a367b-119">En el cuadro de diálogo **retención por juicio** , puede especificar la duración de retención por juicio en el campo **duración** de retención por juicio, deje el campo vacío si desea realizar una suspensión infinita.</span><span class="sxs-lookup"><span data-stu-id="a367b-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a367b-120">También puede agregar notas y dirigir el propietario del buzón de correo a un sitio web que tenga que explicar más sobre la retención \> \*\*\*\* por juicio.</span><span class="sxs-lookup"><span data-stu-id="a367b-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="a367b-121">**Retención:** Puede habilitar las directivas de retención personalizadas, por ejemplo, para conservarlas durante un período de tiempo determinado o eliminar el contenido de forma permanente al final del período de retención.</span><span class="sxs-lookup"><span data-stu-id="a367b-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a367b-122">Para obtener más información, vea [información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="a367b-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="a367b-123">Configurar las características de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="a367b-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="a367b-124">Azure Information Protection (AIP) le ayuda a clasificar y, de manera opcional, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a367b-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a367b-125">Las etiquetas pueden ser aplicadas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios obtienen recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="a367b-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a367b-126">En Outlook en la web, puede aplicar las siguientes restricciones y etiquetas integradas a sus correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="a367b-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="a367b-127">\*\*\*\* No reenviar: los destinatarios pueden leer el mensaje, pero no pueden reenviar, imprimir o copiar contenido</span><span class="sxs-lookup"><span data-stu-id="a367b-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="a367b-128">**Encrypt**: todo el mensaje está cifrado.</span><span class="sxs-lookup"><span data-stu-id="a367b-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="a367b-129">Los destinatarios deben confirmar su identidad antes de obtener acceso al contenido cifrado y no pueden quitar el cifrado.</span><span class="sxs-lookup"><span data-stu-id="a367b-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="a367b-130">**Confidencial**: proporciona a los empleados de su organización permisos totales para el contenido de correo electrónico y los datos adjuntos, pero no para los usuarios ajenos a la organización.</span><span class="sxs-lookup"><span data-stu-id="a367b-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="a367b-131">Los propietarios de datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a367b-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="a367b-132">**Extremadamente confidencial**: esta restricción se puede aplicar a datos extremadamente confidenciales, lo que permite a los empleados ver, editar y responder, pero no reenviar, imprimir o copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="a367b-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="a367b-133">Los propietarios de datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a367b-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="a367b-134">Asegurarse de que Azure Information Protection está activado</span><span class="sxs-lookup"><span data-stu-id="a367b-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="a367b-135">Para comprobar que se ha activado AIP:</span><span class="sxs-lookup"><span data-stu-id="a367b-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="a367b-136">Inicie sesión en [Azure portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a367b-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="a367b-137">Seleccione **todos los servicios** y escriba *Azure Information Protection* en el **cuadro de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="a367b-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="a367b-138">Una vez que se muestren los resultados, haga clic en el inicio junto a **Azure Information Protection** para que sea un favorito y fácil de encontrar más adelante.</span><span class="sxs-lookup"><span data-stu-id="a367b-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="a367b-139">Seleccione **activación de protección** de **Azure Information Protection** \> y asegúrese de que el estado está establecido en activado.</span><span class="sxs-lookup"><span data-stu-id="a367b-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="a367b-140">Ver la Directiva de Azure Information Protection y las etiquetas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="a367b-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="a367b-141">Para ver y modificar las etiquetas existentes:</span><span class="sxs-lookup"><span data-stu-id="a367b-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="a367b-142">En el panel de Azure Information Protection, seleccione **etiquetas**de **clasificación** \> .</span><span class="sxs-lookup"><span data-stu-id="a367b-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="a367b-143">![Etiquetas estándar para Azure Information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="a367b-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="a367b-144">Puede elegir cualquier etiqueta para ver las opciones, puede cambiar el nombre para mostrar, los colores, etc.</span><span class="sxs-lookup"><span data-stu-id="a367b-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="a367b-145">Vea [modificar y crear etiquetas nuevas](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) si desea crear las suyas propias.</span><span class="sxs-lookup"><span data-stu-id="a367b-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a367b-146">Instalar el cliente de Azure Information Protection de forma manual</span><span class="sxs-lookup"><span data-stu-id="a367b-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a367b-147">Para instalar manualmente el cliente de AIP:</span><span class="sxs-lookup"><span data-stu-id="a367b-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a367b-148">Descargue **AzInfoProtection. exe** desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a367b-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a367b-149">Puede comprobar que la instalación ha funcionado viendo un documento de Word y asegurándose de que la opción **proteger** está disponible en la ficha **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="a367b-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="a367b-150">![Cuadro desplegable de la pestaña protección en un documento de Word.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="a367b-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="a367b-151">Para obtener más información, vea [instalar el cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="a367b-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
