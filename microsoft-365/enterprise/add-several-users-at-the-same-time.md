---
title: 'Agregar varios usuarios al mismo tiempo a Microsoft 365: Ayuda Administración'
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
- admindeeplinkMAC
ms.collection:
- Tier1
- scotvorg
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'Obtenga información sobre cómo agregar varios usuarios a Microsoft 365 para empresas desde una lista en una hoja de cálculo u otro archivo con formato CSV. Vea un vídeo en YouTube en el que se explica cómo agregar cuentas a Microsoft 365. Al final de este proceso, cada usuario con una cuenta tendrá un buzón de Microsoft 365. '
ms.openlocfilehash: a6e58dea7eb1aeb277e319f2cef6c03ef431d6bf
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730741"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Agregar varios usuarios al mismo tiempo a Microsoft 365: Ayuda Administración

Cada persona del equipo necesita una cuenta de usuario para poder iniciar sesión y acceder a los servicios de Microsoft 365, como el correo electrónico y Office. Si son muchas personas, puede agregar sus cuentas de una vez desde una hoja de cálculo de Excel u otro archivo guardado en formato CSV. [¿No está seguro de qué formato CSV es](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?
  
> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Agregar varios usuarios en el Centro de administración de Microsoft 365

1. Inicie sesión en Microsoft 365 con su cuenta profesional o educativa.

2. En el centro de administración, elija **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**usuarios activos**</a>.

3. Seleccione **Agregar varios usuarios**.

4. En el panel **Importar varios usuarios**, tiene la opción de descargar un archivo CSV de ejemplo con datos de ejemplo o sin rellenar.

    La hoja de cálculo debe incluir exactamente los **mismos encabezados de columna** que el de ejemplo (Nombre de usuario, Nombre, etc.). Si usa la plantilla, ábrala en una herramienta de edición de texto, como el Bloc de notas, y considere la posibilidad de dejar solos todos los datos de la fila 1 y escribir solo los datos en las filas 2 y posteriores.

    La hoja de cálculo también debe incluir valores para el nombre de usuario (por ejemplo, alberto@contoso.com) y un nombre para mostrar (por ejemplo, Alberto Hermosilla) para cada usuario.

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Escriba una ruta de acceso al archivo en el cuadro o elija **Examinar** para ir a la ubicación del archivo CSV y, a continuación, elija **Comprobar**.
  
    Si hay problemas con el archivo, se mostrarán en el panel. También puede descargar un archivo de registro.

6. En el cuadro de diálogo **Establecer opciones de usuario**, puede establecer el estado de inicio de sesión y elegir qué licencia de producto se asignará a cada uno de los usuarios.

7. En el cuadro de diálogo **Ver el resultado**, puede elegir si desea enviar los resultados a su usuario o a otros usuarios (las contraseñas se mostrarán en texto sin formato). Además, puede ver cuántos usuarios se crearon y, si lo necesita, comprar más licencias para asignárselas a algunos de los nuevos usuarios.

## <a name="next-steps"></a>Pasos siguientes

- Ahora que estas personas tienen cuentas, deben [descargar e instalar o reinstalar Microsoft 365 u Office 2016 en un equipo o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658). Cada persona del equipo puede instalar Microsoft 365 en un máximo de 5 EQUIPOS o Mac.

- Cada persona también puede [configurar aplicaciones de Office y correo electrónico en un dispositivo móvil](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) en hasta 5 tabletas y 5 teléfonos, como iPhones, iPads y teléfonos y tabletas Android. De esta forma, puede editar archivos de Office desde cualquier lugar.

    Consulte [Configuración de Microsoft 365 para empresas para](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) obtener una lista completa de los pasos de configuración.

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Más información sobre cómo agregar usuarios a Microsoft 365

### <a name="not-sure-what-csv-format-is"></a>¿No tiene claro qué es un archivo CSV?

A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.
  
Puede descargar [esta hoja de cálculo de muestra](https://www.microsoft.com/download/details.aspx?id=45485) como punto de partida. Recuerde que Microsoft 365 requiere encabezados de columna en la primera fila, por lo que no los reemplace por otra cosa. 
  
Guarde el archivo con un nuevo nombre y especifique el formato CSV.
  
![Imagen de cómo guardar un archivo en Excel en formato CSV.](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.
  
![Imagen del símbolo del sistema que puede obtener de Excel en la que se le pregunta si realmente desea guardar el archivo como formato CSV.](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Consejos para aplicar formato a la hoja de cálculo

- **¿Debo mantener los mismos encabezados de columna que en la hoja de cálculo de muestra?** Sí. La hoja de cálculo de muestra contiene los encabezados de columna en la primera fila. Estos encabezados son necesarios. Para cada usuario que quiera agregar a Microsoft 365, cree una fila bajo el encabezado. Si agrega, cambia o elimina cualquiera de los encabezados de columna, es posible que Microsoft 365 no pueda crear usuarios a partir de la información del archivo.

- **What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.

- **¿Cuán pequeña o grande puede ser la hoja de cálculo?** La hoja de cálculo debe tener al menos dos filas. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet.

- **¿Qué idiomas puedo usar?** Al crear la hoja de cálculo, puede escribir etiquetas de columna de datos de usuario en cualquier idioma o caracteres, pero no debe cambiar el orden de las etiquetas, como se muestra en el ejemplo. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.

- **What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.

- **Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.

|**Etiquetas columnas datos usuarios**|**Longitud máxima (en caracteres)**|
|:-----|:-----|
|Nombre de usuario (obligatorio)  <br/> |79 incluido el signo de inicio de sesión (@), en el formato name@domain.\<extension\>. El alias del usuario no puede superar los 50 caracteres y el nombre de dominio no puede superar los 48 caracteres.  <br/> |
|Nombre  <br/> |64  <br/> |
|Apellido  <br/> |64  <br/> |
|Nombre para mostrar (obligatorio)  <br/> |256  <br/> |
|Puesto  <br/> |64  <br/> |
|Departamento  <br/> |64  <br/> |
|Número del trabajo  <br/> |128  <br/> |
|Teléfono del trabajo  <br/> |64  <br/> |
|Teléfono móvil  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Dirección  <br/> |1023  <br/> |
|Ciudad  <br/> |128  <br/> |
|Estado o provincia  <br/> |128  <br/> |
|Código postal  <br/> |40  <br/> |
|País o región  <br/> |128  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>¿Sigue teniendo problemas al agregar usuarios a Microsoft 365?

- **Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.

- **Si no ve los nuevos usuarios en Microsoft 365 de inmediato, espere unos minutos.** Los cambios pueden tardar un poco en recorrer todos los servicios de Microsoft 365. 

## <a name="related-articles"></a>Artículos relacionados

[Agregar usuarios de forma individual o masiva a Microsoft 365](/office365/admin/add-users/add-users)