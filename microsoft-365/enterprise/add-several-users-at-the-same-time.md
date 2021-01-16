---
title: 'Agregar varios usuarios al mismo tiempo a Microsoft 365: Ayuda para administradores'
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'Obtenga información sobre cómo agregar varios usuarios a Microsoft 365 para empresas desde una lista en una hoja de cálculo u otro archivo con formato CSV. Vea un vídeo en YouTube que explica cómo agregar cuentas a Microsoft 365. Al final de este proceso, cada usuario con una cuenta tendrá un buzón de Microsoft 365. '
ms.openlocfilehash: 7629879990facbce57a6fbca1aa543471ad1b05b
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877217"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="6ae5f-105">Agregar varios usuarios al mismo tiempo a Microsoft 365: Ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="6ae5f-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="6ae5f-106">Cada persona de su equipo necesita una cuenta de usuario para poder iniciar sesión y acceder a los servicios de Microsoft 365, como el correo electrónico y Office.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="6ae5f-107">Si son muchas personas, puede agregar sus cuentas de una vez desde una hoja de cálculo de Excel u otro archivo guardado en formato CSV.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> <span data-ttu-id="6ae5f-108">[¿No está seguro de qué es el formato CSV?](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)</span><span class="sxs-lookup"><span data-stu-id="6ae5f-108">[Not sure what CSV format is](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ae5f-109">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6ae5f-110">Agregar varios usuarios en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ae5f-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6ae5f-111">Inicie sesión en Microsoft 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-111">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="6ae5f-112">En el centro de administración, elija **Usuarios** \> **activos.**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="6ae5f-113">Seleccione **Agregar varios usuarios.**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="6ae5f-114">En el panel **Importar varios usuarios**, tiene la opción de descargar un archivo CSV de ejemplo con datos de ejemplo o sin rellenar.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span>

    <span data-ttu-id="6ae5f-115">La hoja de cálculo debe incluir exactamente los **mismos encabezados** de columna que el de ejemplo (Nombre de usuario, Nombre, entre otros).</span><span class="sxs-lookup"><span data-stu-id="6ae5f-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="6ae5f-116">Si usa la plantilla, ábrala en una herramienta de edición de texto, como el Bloc de notas, y considere la posibilidad de dejar solos todos los datos de la fila 1 y solo escribir datos en las filas 2 y adicionales.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span>

    <span data-ttu-id="6ae5f-117">La hoja de cálculo también debe incluir valores para el nombre de usuario (por ejemplo, alberto@contoso.com) y un nombre para mostrar (por ejemplo, Alberto Hermosilla) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span>

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="6ae5f-118">Escriba una ruta de acceso al archivo en el cuadro o elija **Examinar** para ir a la ubicación del archivo CSV y, a continuación, elija **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="6ae5f-p104">Si hay problemas con el archivo, se mostrarán en el panel. También puede descargar un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>

6. <span data-ttu-id="6ae5f-121">En el cuadro de diálogo **Establecer opciones de usuario**, puede establecer el estado de inicio de sesión y elegir qué licencia de producto se asignará a cada uno de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span>

7. <span data-ttu-id="6ae5f-122">En el cuadro de diálogo **Ver el resultado**, puede elegir si desea enviar los resultados a su usuario o a otros usuarios (las contraseñas se mostrarán en texto sin formato). Además, puede ver cuántos usuarios se crearon y, si lo necesita, comprar más licencias para asignárselas a algunos de los nuevos usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ae5f-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6ae5f-123">Next steps</span></span>

- <span data-ttu-id="6ae5f-124">Ahora que estas personas tienen cuentas, deben descargar e instalar o reinstalar [Microsoft 365 u Office 2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)en un equipo PC o Mac.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="6ae5f-125">Cada persona de su equipo puede instalar Microsoft 365 en hasta 5 equipos PC o Mac.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span>

- <span data-ttu-id="6ae5f-126">Cada persona también puede configurar aplicaciones de [Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) y correo electrónico en un dispositivo móvil en hasta 5 tabletas y 5 teléfonos, como iPhone, iPad y teléfonos y tabletas Android.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="6ae5f-127">De esta forma, puede editar archivos de Office desde cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-127">This way they can edit Office files from anywhere.</span></span>

    <span data-ttu-id="6ae5f-128">Consulte [Configurar Microsoft 365 para empresas](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) para obtener una lista completa de los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span>

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="6ae5f-129">Más información sobre cómo agregar usuarios a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ae5f-129">More information about how to add users to Microsoft 365</span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="6ae5f-130">¿No tiene claro qué es un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="6ae5f-130">Not sure what CSV format is?</span></span>

<span data-ttu-id="6ae5f-p107">Un archivo CSV es un archivo con valores separados por comas. Puede crear o editar un archivo como este con cualquier editor de textos o programa de hojas de cálculo, como Excel.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="6ae5f-133">Puede descargar [esta hoja de cálculo de muestra](https://www.microsoft.com/download/details.aspx?id=45485) como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-133">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="6ae5f-134">Recuerde que Microsoft 365 requiere encabezados de columna en la primera fila, así que no los reemplace por otra cosa.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-134">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="6ae5f-135">Guarde el archivo con un nuevo nombre y especifique el formato CSV.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-135">Save the file with a new name, and specify CSV format.</span></span>
  
![Imagen de cómo guardar un archivo de Excel en formato CSV](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="6ae5f-p109">Cuando guarde el archivo, probablemente recibirá un mensaje que le informará de que se perderán algunas características del libro si guarda el archivo en formato CSV. No pasa nada. Haga clic en **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span>
  
![Imagen del mensaje que obtendría en Excel que pregunta si realmente quiere guardar el archivo como formato CSV](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="6ae5f-141">Consejos para aplicar formato a la hoja de cálculo</span><span class="sxs-lookup"><span data-stu-id="6ae5f-141">Tips for formatting your spreadsheet</span></span>

- <span data-ttu-id="6ae5f-142">**¿Debo mantener los mismos encabezados de columna que en la hoja de cálculo de muestra?**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-142">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="6ae5f-143">Sí.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-143">Yes.</span></span> <span data-ttu-id="6ae5f-144">La hoja de cálculo de muestra contiene los encabezados de columna en la primera fila.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-144">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="6ae5f-145">Estos encabezados son necesarios.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-145">These headings are required.</span></span> <span data-ttu-id="6ae5f-146">Para cada usuario que quiera agregar a Microsoft 365, cree una fila bajo el encabezado.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-146">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="6ae5f-147">Si agrega, cambia o elimina cualquiera de los encabezados de columna, es posible que Microsoft 365 no pueda crear usuarios a partir de la información del archivo.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-147">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span>

- <span data-ttu-id="6ae5f-p111">**¿Qué ocurre si no tengo toda la información requerida para cada usuario?** El nombre de usuario y el nombre para mostrar son obligatorios, y no puede agregar un nuevo usuario sin esta información. Si le falta parte de la información, como el fax, puede usar un espacio más una coma para indicar que el campo debe dejarse en blanco.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span>

- <span data-ttu-id="6ae5f-151">**¿Qué tamaño puede tener la hoja de cálculo?**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-151">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="6ae5f-152">La hoja de cálculo debe tener al menos dos filas.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-152">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="6ae5f-153">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-153">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="6ae5f-154">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-154">You cannot have more than 251 rows.</span></span> <span data-ttu-id="6ae5f-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span>

- <span data-ttu-id="6ae5f-156">**¿Qué idiomas puedo usar?**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-156">**What languages can I use?**</span></span> <span data-ttu-id="6ae5f-157">Al crear la hoja de cálculo, puede escribir etiquetas de columna de datos de usuario en cualquier idioma o carácter, pero no debe cambiar el orden de las etiquetas, como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-157">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="6ae5f-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span>

- <span data-ttu-id="6ae5f-p114">**¿Qué ocurre si voy a agregar usuarios de diferentes países o regiones?** Cree una hoja de cálculo para cada área. Deberá seguir los pases del asistente para agregar usuarios en bloque para cada una de las hojas de cálculo y dar una única ubicación a todos los usuarios incluidos en el archivo con los que trabaja.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span>

- <span data-ttu-id="6ae5f-p115">**¿Existe algún límite de caracteres que se pueden usar?** En la siguiente tabla se muestran las etiquetas de las columnas de datos de usuario y la longitud máxima (en caracteres) para cada una en la hoja de cálculo de muestra.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span>

|<span data-ttu-id="6ae5f-164">**Etiquetas columnas datos usuarios**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-164">**User data column label**</span></span>|<span data-ttu-id="6ae5f-165">**Longitud máxima (en caracteres)**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-165">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ae5f-166">Nombre de usuario (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6ae5f-166">User Name (Required)</span></span>  <br/> |<span data-ttu-id="6ae5f-167">79, incluido el signo (@), con el formato name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="6ae5f-167">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="6ae5f-168">El alias del usuario no puede superar los 50 caracteres y el nombre de dominio no puede superar los 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-168">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="6ae5f-169">Nombre</span><span class="sxs-lookup"><span data-stu-id="6ae5f-169">First Name</span></span>  <br/> |<span data-ttu-id="6ae5f-170">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-170">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-171">Apellido</span><span class="sxs-lookup"><span data-stu-id="6ae5f-171">Last Name</span></span>  <br/> |<span data-ttu-id="6ae5f-172">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-172">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-173">Nombre para mostrar (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6ae5f-173">Display Name (required)</span></span>  <br/> |<span data-ttu-id="6ae5f-174">256</span><span class="sxs-lookup"><span data-stu-id="6ae5f-174">256</span></span>  <br/> |
|<span data-ttu-id="6ae5f-175">Puesto</span><span class="sxs-lookup"><span data-stu-id="6ae5f-175">Job Title</span></span>  <br/> |<span data-ttu-id="6ae5f-176">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-176">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-177">Departamento</span><span class="sxs-lookup"><span data-stu-id="6ae5f-177">Department</span></span>  <br/> |<span data-ttu-id="6ae5f-178">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-178">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-179">Número del trabajo</span><span class="sxs-lookup"><span data-stu-id="6ae5f-179">Office Number</span></span>  <br/> |<span data-ttu-id="6ae5f-180">128</span><span class="sxs-lookup"><span data-stu-id="6ae5f-180">128</span></span>  <br/> |
|<span data-ttu-id="6ae5f-181">Teléfono del trabajo</span><span class="sxs-lookup"><span data-stu-id="6ae5f-181">Office Phone</span></span>  <br/> |<span data-ttu-id="6ae5f-182">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-182">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-183">Teléfono móvil</span><span class="sxs-lookup"><span data-stu-id="6ae5f-183">Mobile Phone</span></span>  <br/> |<span data-ttu-id="6ae5f-184">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-184">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-185">Fax</span><span class="sxs-lookup"><span data-stu-id="6ae5f-185">Fax</span></span>  <br/> |<span data-ttu-id="6ae5f-186">64</span><span class="sxs-lookup"><span data-stu-id="6ae5f-186">64</span></span>  <br/> |
|<span data-ttu-id="6ae5f-187">Dirección</span><span class="sxs-lookup"><span data-stu-id="6ae5f-187">Address</span></span>  <br/> |<span data-ttu-id="6ae5f-188">1023</span><span class="sxs-lookup"><span data-stu-id="6ae5f-188">1023</span></span>  <br/> |
|<span data-ttu-id="6ae5f-189">Ciudad</span><span class="sxs-lookup"><span data-stu-id="6ae5f-189">City</span></span>  <br/> |<span data-ttu-id="6ae5f-190">128</span><span class="sxs-lookup"><span data-stu-id="6ae5f-190">128</span></span>  <br/> |
|<span data-ttu-id="6ae5f-191">Estado o provincia</span><span class="sxs-lookup"><span data-stu-id="6ae5f-191">State or Province</span></span>  <br/> |<span data-ttu-id="6ae5f-192">128</span><span class="sxs-lookup"><span data-stu-id="6ae5f-192">128</span></span>  <br/> |
|<span data-ttu-id="6ae5f-193">Código postal</span><span class="sxs-lookup"><span data-stu-id="6ae5f-193">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="6ae5f-194">40</span><span class="sxs-lookup"><span data-stu-id="6ae5f-194">40</span></span>  <br/> |
|<span data-ttu-id="6ae5f-195">País o región</span><span class="sxs-lookup"><span data-stu-id="6ae5f-195">Country or Region</span></span>  <br/> |<span data-ttu-id="6ae5f-196">128</span><span class="sxs-lookup"><span data-stu-id="6ae5f-196">128</span></span>  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="6ae5f-197">¿Sigue teniendo problemas al agregar usuarios a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6ae5f-197">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="6ae5f-p117">**Asegúrese una vez más de que el archivo tenga un formato correcto.** Compruebe que los encabezados de las columnas coincidan con los encabezados del archivo de muestra. Asegúrese de haber respetado los límites de longitud y de que los campos estén separados por comas.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span>

- <span data-ttu-id="6ae5f-201">**Si no ve los nuevos usuarios de Microsoft 365 inmediatamente, espere unos minutos.**</span><span class="sxs-lookup"><span data-stu-id="6ae5f-201">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="6ae5f-202">Los cambios pueden tardar un poco en realizarse en todos los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ae5f-202">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="6ae5f-203">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="6ae5f-203">Related articles</span></span>

[<span data-ttu-id="6ae5f-204">Agregar usuarios individualmente o de forma masiva a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ae5f-204">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
