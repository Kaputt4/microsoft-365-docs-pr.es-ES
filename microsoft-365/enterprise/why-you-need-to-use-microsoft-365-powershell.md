---
title: ¿Por qué necesita usar PowerShell para Microsoft 365?
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Resumen: comprenda por qué debe usar PowerShell para administrar Microsoft 365, en algunos casos de manera más eficiente y, en otros casos, por necesidad.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754111"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="e551b-103">¿Por qué necesita usar PowerShell para Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e551b-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="e551b-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e551b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e551b-105">Con el centro de administración de 365 de Microsoft, puede administrar sus licencias y cuentas de usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="e551b-106">También puede administrar los servicios de Microsoft 365, como Exchange Online, Teams y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e551b-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="e551b-107">Si, en su lugar, usa PowerShell para administrar estos servicios, puede aprovechar el entorno de la línea de comandos y del lenguaje de scripting para la velocidad, la automatización y las capacidades adicionales.</span><span class="sxs-lookup"><span data-stu-id="e551b-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="e551b-108">En este artículo se muestra cómo usar PowerShell para administrar Microsoft 365 para:</span><span class="sxs-lookup"><span data-stu-id="e551b-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="e551b-109">Revelar información adicional que no puede ver en el centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e551b-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="e551b-110">Configurar las características y la configuración solo posible con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e551b-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="e551b-111">Realizar operaciones masivas</span><span class="sxs-lookup"><span data-stu-id="e551b-111">Do bulk operations</span></span>
    
- <span data-ttu-id="e551b-112">Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="e551b-112">Filter data</span></span>
    
- <span data-ttu-id="e551b-113">Imprimir o guardar datos</span><span class="sxs-lookup"><span data-stu-id="e551b-113">Print or save data</span></span>
    
- <span data-ttu-id="e551b-114">Administrar a través de servicios</span><span class="sxs-lookup"><span data-stu-id="e551b-114">Manage across services</span></span>
    
<span data-ttu-id="e551b-115">Tenga en cuenta que PowerShell para Microsoft 365 es un conjunto de módulos para Windows PowerShell, que es un entorno de línea de comandos para plataformas y servicios basados en Windows.</span><span class="sxs-lookup"><span data-stu-id="e551b-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="e551b-116">Este entorno crea un lenguaje de Shell de comandos que se puede extender con módulos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e551b-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="e551b-117">Proporciona una forma de ejecutar comandos o scripts sencillos o complejos.</span><span class="sxs-lookup"><span data-stu-id="e551b-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="e551b-118">Por ejemplo, después de instalar los módulos de PowerShell para Microsoft 365 y conectarse a su suscripción a Microsoft 365, puede ejecutar el siguiente comando para enumerar todos los buzones de usuario para Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e551b-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="e551b-119">También puede obtener la lista de buzones de correo mediante el centro de administración de Microsoft 365, pero no es fácil contar los elementos de todas las listas para todos los sitios de las aplicaciones Web.</span><span class="sxs-lookup"><span data-stu-id="e551b-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="e551b-120">PowerShell para Microsoft 365 está diseñado para ayudarle a administrar la 365 de Microsoft, no para reemplazar el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="e551b-121">Los administradores deben poder usar PowerShell para Microsoft 365 porque existen algunos procedimientos de configuración que solo se pueden realizar a través de PowerShell para los comandos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="e551b-122">En estos casos, debe saber cómo:</span><span class="sxs-lookup"><span data-stu-id="e551b-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="e551b-123">Instale los módulos de PowerShell para Microsoft 365 (solo se realiza una vez para cada equipo de administrador).</span><span class="sxs-lookup"><span data-stu-id="e551b-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="e551b-124">Conéctese a su suscripción de Microsoft 365 (una vez por cada sesión de PowerShell).</span><span class="sxs-lookup"><span data-stu-id="e551b-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="e551b-125">Recopilar la información necesaria para ejecutar los comandos de PowerShell necesarios para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="e551b-126">Ejecute PowerShell para los comandos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="e551b-127">Una vez que haya aprendido estas habilidades básicas, no es necesario que Enumere los usuarios de buzones de correo mediante el comando **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="e551b-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="e551b-128">Tampoco es necesario que comprenda cómo crear un nuevo comando como el comando mencionado anteriormente para contar todos los elementos de todas las listas para todos los sitios de las aplicaciones Web.</span><span class="sxs-lookup"><span data-stu-id="e551b-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="e551b-129">Microsoft y la comunidad de administradores pueden ayudarle con tareas como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e551b-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="e551b-130">PowerShell para Microsoft 365 puede revelar información que no puede ver con el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e551b-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="e551b-131">El centro de administración de 365 de Microsoft muestra una gran cantidad de información útil.</span><span class="sxs-lookup"><span data-stu-id="e551b-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="e551b-132">Pero no muestra toda la información posible que Microsoft 365 almacena sobre los usuarios, las licencias, los buzones de correo y los sitios.</span><span class="sxs-lookup"><span data-stu-id="e551b-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="e551b-133">A continuación, se muestra un ejemplo de *usuarios y grupos* en el centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e551b-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Ejemplo de la presentación de usuarios y grupos en el centro de administración de Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="e551b-135">Esta vista proporciona la información que necesita en muchos casos.</span><span class="sxs-lookup"><span data-stu-id="e551b-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="e551b-136">En cambio, algunas veces necesitará más.</span><span class="sxs-lookup"><span data-stu-id="e551b-136">However, there are times when you need more.</span></span> <span data-ttu-id="e551b-137">Por ejemplo, las licencias de Microsoft 365 (y las características de Microsoft 365 disponibles para un usuario) dependen en parte de la ubicación geográfica del usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="e551b-138">Las directivas y características que puede ampliar a un usuario que vive en Estados Unidos podrían no ser las mismas que las que puede ampliar a un usuario en India o Bélgica.</span><span class="sxs-lookup"><span data-stu-id="e551b-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="e551b-139">Siga estos pasos en el centro de administración de Microsoft 365 para determinar la ubicación geográfica de un usuario:</span><span class="sxs-lookup"><span data-stu-id="e551b-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="e551b-140">Haga doble clic en el **Nombre para mostrar** del usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="e551b-141">En el panel de visualización propiedades de usuario, seleccione **detalles**.</span><span class="sxs-lookup"><span data-stu-id="e551b-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="e551b-142">En la pantalla de detalles, seleccione **detalles adicionales**.</span><span class="sxs-lookup"><span data-stu-id="e551b-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="e551b-143">Desplácese hasta que encuentre el encabezado **país o región**:</span><span class="sxs-lookup"><span data-stu-id="e551b-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Ejemplo de la información de región de un usuario en el centro de administración de Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="e551b-145">Escriba el nombre para mostrar y la ubicación del usuario en una hoja de papel, o cópielo y péguelo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e551b-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="e551b-146">Debe repetir este procedimiento para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="e551b-147">Si tiene muchos usuarios, este proceso puede resultar tedioso.</span><span class="sxs-lookup"><span data-stu-id="e551b-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="e551b-148">Con PowerShell para Microsoft 365, puede mostrar esta información para todos los usuarios con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e551b-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="e551b-149">PowerShell Core no es compatible con el módulo Microsoft Azure Active Directory para el módulo y los cmdlets de Windows PowerShell que tienen *msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e551b-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="e551b-150">Debe ejecutar estos cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e551b-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="e551b-151">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="e551b-152">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de la suscripción actual de Microsoft 365 (**Get-AzureADUser**), pero solo se muestra el nombre y la ubicación de cada usuario (**Seleccione DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="e551b-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="e551b-153">Como PowerShell para Microsoft 365 admite un lenguaje de Shell de comandos, puede seguir manipulando la información obtenida por el comando **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="e551b-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="e551b-154">Por ejemplo, es posible que quiera ordenar estos usuarios por su ubicación, agrupando todos los usuarios de Brasil, todos los usuarios de Estados Unidos juntos, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e551b-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="e551b-155">Este es el comando:</span><span class="sxs-lookup"><span data-stu-id="e551b-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="e551b-156">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="e551b-157">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de la suscripción actual de Microsoft 365, pero solo mostrar el nombre y la ubicación de cada usuario y ordenarlos primero por su ubicación y, a continuación, su nombre (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="e551b-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="e551b-158">También puede usar filtros adicionales.</span><span class="sxs-lookup"><span data-stu-id="e551b-158">You can also use additional filtering.</span></span> <span data-ttu-id="e551b-159">Por ejemplo, si solo quiere ver la información sobre los usuarios que están en Brasil, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e551b-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="e551b-160">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="e551b-161">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de la suscripción a Microsoft 365 actual cuya ubicación es Brasil (**donde {$ \_ . UsageLocation-EQ "BR"}**) y, a continuación, mostrar el nombre y la ubicación de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="e551b-162">**Una nota sobre dominios grandes**</span><span class="sxs-lookup"><span data-stu-id="e551b-162">**A note about large domains**</span></span>
  
<span data-ttu-id="e551b-163">Si tiene un dominio grande con decenas de miles de usuarios, pruebe algunos de los ejemplos que se muestran en este artículo podrían dar como límite la limitación.</span><span class="sxs-lookup"><span data-stu-id="e551b-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="e551b-164">En función de factores como la potencia de procesamiento y el ancho de banda de red disponible, es posible que esté intentando realizar muchas tareas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e551b-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="e551b-165">Es posible que las organizaciones grandes deseen dividir algunas de estas operaciones de PowerShell en dos comandos.</span><span class="sxs-lookup"><span data-stu-id="e551b-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="e551b-166">Por ejemplo, el siguiente comando devuelve todas las cuentas de usuario y muestra el nombre y la ubicación de cada una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e551b-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="e551b-167">Esto funciona muy bien en los dominios más pequeños.</span><span class="sxs-lookup"><span data-stu-id="e551b-167">That works great for smaller domains.</span></span> <span data-ttu-id="e551b-168">Pero en una organización de gran tamaño, es posible que desee dividir esa operación en dos comandos: un comando para almacenar la información de la cuenta de usuario en una variable y otra para mostrar la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="e551b-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="e551b-169">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e551b-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="e551b-170">La interpretación de este conjunto de comandos de PowerShell es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e551b-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="e551b-171">Obtenga todos los usuarios de la suscripción actual de Microsoft 365 y almacene la información en una variable llamada $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="e551b-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="e551b-172">Se muestra el contenido de la variable *$x*, pero solo se incluye el nombre y la ubicación de cada usuario (**$x | Seleccione DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="e551b-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="e551b-173">Microsoft 365 tiene características que solo se pueden configurar con PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e551b-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="e551b-174">El centro de administración de 365 de Microsoft tiene como objetivo proporcionar acceso a tareas administrativas comunes y útiles que se aplican a la mayoría de los entornos.</span><span class="sxs-lookup"><span data-stu-id="e551b-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="e551b-175">En otras palabras, el centro de administración de Microsoft 365 se diseñó para que el administrador normal pudiera llevar a cabo las tareas de administración más comunes.</span><span class="sxs-lookup"><span data-stu-id="e551b-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="e551b-176">Pero hay algunas tareas que no se pueden realizar en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="e551b-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="e551b-177">Por ejemplo, el centro de administración de Skype empresarial online ofrece algunas opciones para crear invitaciones a reuniones personalizadas:</span><span class="sxs-lookup"><span data-stu-id="e551b-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Ejemplo de la presentación de las invitaciones a reuniones personalizadas en el centro de administración de Skype Empresarial Online](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="e551b-179">Con esta configuración, puede agregar un toque de personalización y profesionalidad a las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="e551b-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="e551b-180">Pero hay más cosas a tener en la configuración de reunión que simplemente crear invitaciones a reuniones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e551b-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="e551b-181">Por ejemplo, de forma predeterminada las reuniones permiten lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e551b-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="e551b-182">A los usuarios anónimos obtener entrada automática a cada reunión.</span><span class="sxs-lookup"><span data-stu-id="e551b-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="e551b-183">A los asistentes grabar la reunión.</span><span class="sxs-lookup"><span data-stu-id="e551b-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="e551b-184">A todos los usuarios de la organización poder ser designados como moderadores cuando se unen a la reunión.</span><span class="sxs-lookup"><span data-stu-id="e551b-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="e551b-185">Esta configuración no está disponible en el centro de administración de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e551b-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="e551b-186">Puede controlarlos desde PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="e551b-187">Este es un comando que deshabilita estas tres opciones:</span><span class="sxs-lookup"><span data-stu-id="e551b-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="e551b-188">Para ejecutar este comando, debe instalar el [módulo de PowerShell de Skype empresarial online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="e551b-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="e551b-189">La interpretación de este comando de PowerShell es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e551b-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="e551b-190">En la configuración de las nuevas reuniones de Skype empresarial online (**set-CsMeetingConfiguration**), deshabilite la posibilidad de que los usuarios anónimos obtengan la entrada automática a las reuniones (**-AdmitAnonymousUsersByDefault $false**).</span><span class="sxs-lookup"><span data-stu-id="e551b-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="e551b-191">Deshabilitar la posibilidad de que los asistentes graben reuniones (**-AllowConferenceRecording $false**).</span><span class="sxs-lookup"><span data-stu-id="e551b-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="e551b-192">No designe a todos los usuarios de su organización como moderadores (**-DesignateAsPresenter "none"**).</span><span class="sxs-lookup"><span data-stu-id="e551b-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="e551b-193">Para restaurar esta configuración predeterminada (habilitar las opciones), ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="e551b-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="e551b-194">También existen otros escenarios similares, que son el motivo por el que los administradores deben saber cómo ejecutar PowerShell para los comandos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="e551b-195">PowerShell para Microsoft 365 es excelente para operaciones en masa</span><span class="sxs-lookup"><span data-stu-id="e551b-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="e551b-196">Las interfaces visuales como el centro de administración de Microsoft 365 son más útiles cuando se tiene una única operación que hacer.</span><span class="sxs-lookup"><span data-stu-id="e551b-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="e551b-197">Por ejemplo, si necesita deshabilitar una cuenta de usuario, puede usar el centro de administración para buscar y desactivar rápidamente una casilla.</span><span class="sxs-lookup"><span data-stu-id="e551b-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="e551b-198">Esto puede ser más fácil que realizar una operación similar en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e551b-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="e551b-199">Pero si tiene que cambiar muchas cosas o algunas cosas seleccionadas dentro de un conjunto amplio de otras cosas, es posible que el centro de administración de Microsoft 365 no sea la mejor herramienta.</span><span class="sxs-lookup"><span data-stu-id="e551b-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="e551b-200">Por ejemplo, supongamos que tiene que cambiar el prefijo en miles de números de teléfono o quitar el usuario específico *Ken Myer* de todos sus sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e551b-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="e551b-201">¿Cómo haría esto en el centro de administración de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e551b-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="e551b-202">En el último ejemplo, supongamos que tiene varios cientos de sitios de SharePoint Online y no sabe de cuáles Meyer es miembro.</span><span class="sxs-lookup"><span data-stu-id="e551b-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="e551b-203">Tendría que empezar en el centro de administración de 365 de Microsoft y, a continuación, llevar a cabo este procedimiento para cada sitio:</span><span class="sxs-lookup"><span data-stu-id="e551b-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="e551b-204">Seleccione la **dirección URL** del sitio.</span><span class="sxs-lookup"><span data-stu-id="e551b-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="e551b-205">En el cuadro propiedades de la **colección de sitios** , seleccione el vínculo dirección del **sitio web** para abrir el sitio.</span><span class="sxs-lookup"><span data-stu-id="e551b-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="e551b-206">En el sitio, seleccione **compartir**.</span><span class="sxs-lookup"><span data-stu-id="e551b-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="e551b-207">En el cuadro de diálogo **compartir** , seleccione el vínculo que muestra todos los usuarios que tienen permisos en el sitio:</span><span class="sxs-lookup"><span data-stu-id="e551b-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Ejemplo de visualización de los miembros de un sitio de SharePoint Online en el centro de administración de SharePoint Online](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="e551b-209">En el cuadro de diálogo **compartido con** , seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e551b-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="e551b-210">Desplácese hacia abajo por la lista de usuarios, busque y seleccione Ken Myer (suponiendo que tiene permisos en el sitio) y, a continuación, seleccione **quitar permisos de usuario**.</span><span class="sxs-lookup"><span data-stu-id="e551b-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="e551b-211">Esto puede tardar *mucho* tiempo para varios cientos de sitios.</span><span class="sxs-lookup"><span data-stu-id="e551b-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="e551b-212">La alternativa es ejecutar el siguiente comando en PowerShell para Microsoft 365 para quitar a Ken Myer de todos los sitios:</span><span class="sxs-lookup"><span data-stu-id="e551b-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="e551b-213">Este comando requiere que instale el [módulo de PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="e551b-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="e551b-214">La interpretación de este comando de PowerShell es la siguiente: obtener todos los sitios de SharePoint en la suscripción a Microsoft 365 actual (**Get-SPOSite**) y para cada sitio quitar Ken Meyer de la lista de usuarios que pueden acceder a él (**foreach {Remove-cónyuge-site $ \_ . URL-LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="e551b-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="e551b-215">Se le dice a Microsoft 365 que quite Ken Meyer de cada sitio, incluidos aquellos a los que no tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="e551b-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="e551b-216">Por lo tanto, los resultados mostrarán errores para los sitios a los que no tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="e551b-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="e551b-217">Se puede usar una condición adicional en este comando para quitar Ken Meyer solo de los sitios que le tienen en su lista de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e551b-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="e551b-218">Pero los errores devueltos no causan ningún daño a los sitios.</span><span class="sxs-lookup"><span data-stu-id="e551b-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="e551b-219">Este comando puede tardar unos minutos en ejecutarse en cientos de sitios, en lugar de horas de trabajo a través del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="e551b-220">Este es otro ejemplo de operación masiva.</span><span class="sxs-lookup"><span data-stu-id="e551b-220">Here's another bulk operation example.</span></span> <span data-ttu-id="e551b-221">Use este comando para agregar *Bonnie Kearney*, un nuevo administrador de SharePoint, a todos los sitios de la organización:</span><span class="sxs-lookup"><span data-stu-id="e551b-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="e551b-222">La interpretación de este comando de PowerShell es la siguiente: obtener todos los sitios de SharePoint en la suscripción actual de Microsoft 365 y para cada sitio permitir el acceso a Bonnie Kearney agregando su nombre de inicio de sesión al grupo miembros del sitio (**foreach {Add-cónyuge-site $ \_ . URL-LoginName "bkearney \@ litwareinc.com"-Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="e551b-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="e551b-223">PowerShell para Microsoft 365 es excelente en el filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="e551b-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="e551b-224">El centro de administración de 365 de Microsoft ofrece varias formas de filtrar los datos para encontrar fácilmente un subconjunto de información.</span><span class="sxs-lookup"><span data-stu-id="e551b-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="e551b-225">Por ejemplo, Exchange facilita el filtrado de prácticamente cualquier propiedad de un buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="e551b-226">Por ejemplo, esta es la lista de buzones de correo para todos los usuarios que viven en la ciudad de Bloomington:</span><span class="sxs-lookup"><span data-stu-id="e551b-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Ejemplo de cómo realizar una búsqueda avanzada en el centro de administración de Microsoft 365 para la lista de buzones para todos los usuarios que viven en la ciudad de Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="e551b-228">El Centro de administración de Exchange también le permite combinar criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="e551b-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="e551b-229">Por ejemplo, puede encontrar los buzones de correo de todas las personas que viven en Bloomington y trabajar en el Departamento de finanzas.</span><span class="sxs-lookup"><span data-stu-id="e551b-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="e551b-230">Pero hay limitaciones en lo que puede hacer en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e551b-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="e551b-231">Por ejemplo, no podría encontrar tan fácilmente los buzones de las personas que viven en Bloomington *o* San Diego, o los buzones de correo de todas las personas que no viven en Bloomington.</span><span class="sxs-lookup"><span data-stu-id="e551b-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="e551b-232">Puede usar el siguiente comando de PowerShell para Microsoft 365 para obtener una lista de buzones de correo de todas las personas que viven en Bloomington o San Diego:</span><span class="sxs-lookup"><span data-stu-id="e551b-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="e551b-233">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="e551b-234">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de la suscripción actual de Microsoft 365 que tienen un buzón de correo en la ciudad de San Diego o Bloomington (**donde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-y ($ \_ . City-EQ "San Diego"-o $ \_ . City-EQ "Bloomington")}**) y, a continuación, mostrar el nombre y la ciudad de cada (**Seleccione DisplayName, City**).</span><span class="sxs-lookup"><span data-stu-id="e551b-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="e551b-235">Y este es el comando para enumerar todos los buzones de correo de las personas que viven en cualquier lugar excepto Bloomington:</span><span class="sxs-lookup"><span data-stu-id="e551b-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="e551b-236">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="e551b-237">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de la suscripción de Microsoft 365 actual que tienen un buzón no ubicado en la ciudad de Bloomington (**donde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-y $ \_ . City-ne "Bloomington"}**) y, a continuación, mostrar el nombre y la ciudad de cada uno.</span><span class="sxs-lookup"><span data-stu-id="e551b-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="e551b-238">Usar caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="e551b-238">Use wildcards</span></span>

<span data-ttu-id="e551b-239">También puede usar caracteres comodín en los filtros de PowerShell para hacer coincidir parte de un nombre.</span><span class="sxs-lookup"><span data-stu-id="e551b-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="e551b-240">Por ejemplo, supongamos que está buscando una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="e551b-241">Todo lo que puede recordar es que el apellido del usuario fue *Anderson* o quizá *Henderson* o *Jorgenson*.</span><span class="sxs-lookup"><span data-stu-id="e551b-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="e551b-242">Puede realizar un seguimiento de ese usuario en el centro de administración de Microsoft 365 mediante la herramienta de búsqueda y llevar a cabo tres búsquedas diferentes:</span><span class="sxs-lookup"><span data-stu-id="e551b-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="e551b-243">Una para  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="e551b-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="e551b-244">Otra para  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="e551b-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="e551b-245">Y otra para  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="e551b-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="e551b-246">Como todos los tres nombres terminan en "EZ", puede decirle a PowerShell que muestre todos los usuarios cuyo nombre termina en "hijo".</span><span class="sxs-lookup"><span data-stu-id="e551b-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="e551b-247">Este es el comando:</span><span class="sxs-lookup"><span data-stu-id="e551b-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="e551b-248">La interpretación de este comando de PowerShell es la siguiente: Obtenga todos los usuarios de la suscripción actual de Microsoft 365, pero use un filtro que solo Enumere los usuarios cuyos apellidos terminen en "hijo" (**-Filter ' {LastName-like " \* hijo"} '**).</span><span class="sxs-lookup"><span data-stu-id="e551b-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="e551b-249">Las \* siglas de cualquier conjunto de caracteres, que son letras del apellido del usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="e551b-250">PowerShell para Microsoft 365 simplifica la tarea de imprimir o guardar datos</span><span class="sxs-lookup"><span data-stu-id="e551b-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="e551b-251">El centro de administración de 365 de Microsoft permite ver las listas de datos.</span><span class="sxs-lookup"><span data-stu-id="e551b-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="e551b-252">Este es un ejemplo del centro de administración de Skype empresarial online que muestra una lista de usuarios que se han habilitado para Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="e551b-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Ejemplo del centro de administración de Skype Empresarial Online que muestra una lista de usuarios que han sido habilitados para Skype Empresarial Online](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="e551b-254">Para guardar la información en un archivo, debe pegarla en un documento o en una hoja de cálculo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e551b-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="e551b-255">Cualquier caso puede requerir un formato adicional.</span><span class="sxs-lookup"><span data-stu-id="e551b-255">Either case might require additional formatting.</span></span> <span data-ttu-id="e551b-256">Además, el centro de administración de Microsoft 365 no ofrece una forma de imprimir directamente la lista que se muestra.</span><span class="sxs-lookup"><span data-stu-id="e551b-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="e551b-257">Afortunadamente, puede usar PowerShell para no solo mostrar la lista, sino para guardarla en un archivo que se pueda importar fácilmente a Excel.</span><span class="sxs-lookup"><span data-stu-id="e551b-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="e551b-258">Este es un comando de ejemplo para guardar los datos de usuario de Skype empresarial online en un archivo de valores separados por comas (CSV), que se puede importar fácilmente como una tabla en una hoja de cálculo de Excel:</span><span class="sxs-lookup"><span data-stu-id="e551b-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="e551b-259">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-259">Here's an example of the results:</span></span>
  
![Ejemplo de una tabla importada a una hoja de cálculo de Excel para los datos de usuario de Skype empresarial online que se guardó en un archivo de valores separados por comas.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="e551b-261">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de Skype empresarial online en la suscripción actual de Microsoft 365 (**Get-CsOnlineUser**); Obtenga solo el nombre de usuario, el UPN y la ubicación (**Seleccione DisplayName, UserPrincipalName, UsageLocation**); y, a continuación, guarde esa información en un archivo CSV denominado C: \\ logs \\SfBUsers.csv (**Export-CSV-path "C: \\ logs \\SfBUsers.csv"-NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="e551b-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="e551b-262">También puede usar las opciones para guardar esta lista como un archivo XML o una página HTML.</span><span class="sxs-lookup"><span data-stu-id="e551b-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="e551b-263">De hecho, con comandos de PowerShell adicionales, puede guardarlos directamente como un archivo de Excel, con cualquier formato personalizado que desee.</span><span class="sxs-lookup"><span data-stu-id="e551b-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="e551b-264">También puede enviar el resultado de un comando de PowerShell que muestra una lista directamente en la impresora predeterminada de Windows.</span><span class="sxs-lookup"><span data-stu-id="e551b-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="e551b-265">Este es un comando de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e551b-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="e551b-266">Y este es el aspecto que tendrá el documento impreso:</span><span class="sxs-lookup"><span data-stu-id="e551b-266">Here's what your printed document will look like:</span></span>
  
![Ejemplo de un documento impreso que fue el resultado de un comando de PowerShell enviado directamente a la impresora predeterminada en Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="e551b-268">La interpretación de este comando de PowerShell es la siguiente: obtener todos los usuarios de Skype empresarial online en la suscripción actual de Microsoft 365; Obtenga solo el nombre de usuario, el UPN y la ubicación; y, a continuación, envíe esa información a la impresora predeterminada de Windows (**out-Printer**).</span><span class="sxs-lookup"><span data-stu-id="e551b-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="e551b-269">El documento impreso tiene el mismo formato sencillo que la visualización en la ventana de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e551b-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="e551b-270">Para obtener una copia impresa, solo tiene que agregar **| Fuera** de la impresora al final del comando.</span><span class="sxs-lookup"><span data-stu-id="e551b-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="e551b-271">PowerShell para Microsoft 365 le permite administrar los productos de servidor</span><span class="sxs-lookup"><span data-stu-id="e551b-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="e551b-272">Los componentes que forman Microsoft 365 están diseñados para trabajar juntos.</span><span class="sxs-lookup"><span data-stu-id="e551b-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="e551b-273">Por ejemplo, supongamos que agrega un nuevo usuario a Microsoft 365 y especifica dicha información como el Departamento y el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="e551b-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="e551b-274">La información estará disponible si obtiene acceso a la información del usuario en cualquiera de los servicios de Microsoft 365: Skype empresarial online, Exchange o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e551b-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="e551b-275">Pero eso es para la información habitual que abarca el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="e551b-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="e551b-276">La información específica del producto, como la información sobre el buzón de correo de Exchange de un usuario, no suele estar disponible en todo el conjunto de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e551b-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="e551b-277">Por ejemplo, la información acerca de si el buzón de un usuario está habilitado o no está disponible únicamente en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e551b-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="e551b-278">Suponga que quiere crear un informe que muestre la información siguiente de todos los usuarios:</span><span class="sxs-lookup"><span data-stu-id="e551b-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="e551b-279">El nombre para mostrar del usuario</span><span class="sxs-lookup"><span data-stu-id="e551b-279">The user's display name</span></span>
    
- <span data-ttu-id="e551b-280">Si el usuario tiene licencia para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e551b-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="e551b-281">Si el buzón de Exchange del usuario se ha habilitado</span><span class="sxs-lookup"><span data-stu-id="e551b-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="e551b-282">Si el usuario está habilitado en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e551b-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="e551b-283">No puede crear fácilmente un informe de este tipo en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e551b-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e551b-284">En su lugar, tendría que crear un documento independiente para almacenar la información, como una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="e551b-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="e551b-285">A continuación, obtenga todos los nombres de usuario e información de licencia del centro de administración de Microsoft 365, obtenga información del buzón del centro de administración de Exchange, obtenga información de Skype empresarial online del centro de administración de Skype empresarial online y, a continuación, combine dicha información.</span><span class="sxs-lookup"><span data-stu-id="e551b-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="e551b-286">La alternativa es usar un script de PowerShell para compilar el informe por usted.</span><span class="sxs-lookup"><span data-stu-id="e551b-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="e551b-287">El siguiente script de ejemplo es más complicado que los comandos que ha visto hasta ahora en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e551b-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="e551b-288">Sin embargo, se muestra el potencial de usar PowerShell para crear vistas de información que son difíciles de obtener de otro modo.</span><span class="sxs-lookup"><span data-stu-id="e551b-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="e551b-289">Este es el script para compilar y mostrar la lista que necesita:</span><span class="sxs-lookup"><span data-stu-id="e551b-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="e551b-290">A continuación, se muestra un ejemplo de los resultados:</span><span class="sxs-lookup"><span data-stu-id="e551b-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="e551b-291">La interpretación de este script de PowerShell es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e551b-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="e551b-292">Obtenga todos los usuarios de la suscripción actual de Microsoft 365 y almacene la información en una variable que se denomine *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="e551b-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="e551b-293">Inicie un bucle que se ejecuta en todos los usuarios de la variable $x (**foreach ($i en $x)**).</span><span class="sxs-lookup"><span data-stu-id="e551b-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="e551b-294">Defina una variable llamada *$y* y almacene en ella la información del buzón del usuario (**$y = Get-Mailbox-Identity $i. UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="e551b-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="e551b-295">Agregue una nueva propiedad a la información del usuario que se denomina *IsMailBoxEnabled*.</span><span class="sxs-lookup"><span data-stu-id="e551b-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="e551b-296">Establézcalo en el valor de la propiedad IsMailBoxEnabled del buzón del usuario (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="e551b-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="e551b-297">Defina una variable llamada *$y*y almacene la información de Skype empresarial online del usuario en ella (**$y = Get-CsOnlineUser-Identity $i. UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="e551b-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="e551b-298">Agregue una nueva propiedad a la información del usuario que se denomina *EnabledForSfB*.</span><span class="sxs-lookup"><span data-stu-id="e551b-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="e551b-299">Establézcalo en el valor de la propiedad Enabled de la información de Skype empresarial online del usuario (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y. Enabled**).</span><span class="sxs-lookup"><span data-stu-id="e551b-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="e551b-300">Mostrar la lista de usuarios, pero incluya únicamente su nombre, si tienen licencia y las dos nuevas propiedades que indican si su buzón está habilitado y si están habilitados para Skype empresarial online (**$x | Seleccione DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="e551b-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e551b-301">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e551b-301">See also</span></span>

[<span data-ttu-id="e551b-302">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e551b-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e551b-303">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e551b-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e551b-304">Usar Windows PowerShell para crear informes en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e551b-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
