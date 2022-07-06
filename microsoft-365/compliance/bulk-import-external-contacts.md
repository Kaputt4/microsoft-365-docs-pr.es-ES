---
title: Importación masiva de contactos externos a Exchange Online
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
ms.custom: admindeeplinkEXCHANGE
description: Obtenga información sobre cómo los administradores pueden usar Exchange Online PowerShell y un archivo CSV para importar de forma masiva contactos externos a la lista global de direcciones.
ms.openlocfilehash: 40e8c44a45e8d8d0c416f3f00df57e24504a4e70
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633815"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importación masiva de contactos externos a Exchange Online

**Este artículo está destinado a administradores. ¿Está intentando importar contactos a su propio buzón? Consulte [Importación de contactos a Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
¿Su empresa tiene muchos contactos empresariales existentes que desea incluir en la libreta de direcciones compartida (también denominada lista global de direcciones) en Exchange Online? ¿Desea agregar contactos externos como miembros de grupos de distribución, como puede hacer con los usuarios de su empresa? Si es así, puede usar Exchange Online PowerShell y un archivo CSV (valores separados por comas) para importar de forma masiva contactos externos en Exchange Online. Se trata de un proceso de tres pasos:
  
[Paso 1: Crear un archivo CSV que contenga información sobre los contactos externos](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Paso 2: Crear los contactos externos con PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Paso 3: Agregar información a las propiedades de los contactos externos](#step-3-add-information-to-the-properties-of-the-external-contacts)

Después de completar estos pasos para importar contactos, puede realizar estas tareas adicionales:
  
- [Agregar más contactos externos](#add-more-external-contacts)
  
- [Ocultar contactos externos de la libreta de direcciones compartida](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Paso 1: Crear un archivo CSV que contenga información sobre los contactos externos

El primer paso consiste en crear un archivo CSV que contenga información sobre cada contacto externo que quiera importar a Exchange Online. 
  
1. Copie el texto siguiente en un archivo de texto en el Bloc de notas y guárdelo en el escritorio como un archivo CSV con un sufijo de nombre de archivo de .csv; por ejemplo, ExternalContacts.csv.
    
    > [!TIP]
    > Si su idioma contiene caracteres especiales (como **å**, **ä** y **ö** en sueco) guarde el archivo CSV con UTF-8 u otra codificación Unicode al guardar el archivo en el Bloc de notas. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    La primera fila, o fila de encabezado, del archivo CSV muestra las propiedades de los contactos que se pueden usar al importarlos a Exchange Online. Cada nombre de propiedad está separado por una coma. Cada fila de la fila de encabezado representa los valores de propiedad para importar un único contacto externo. 
    
    > [!NOTE]
    > Este texto incluye datos de ejemplo, que puede eliminar. Pero no elimine ni cambie la primera fila (encabezado). Contiene todas las propiedades de los contactos externos. 
  
2. Abra el archivo CSV en Microsoft Excel para editar el archivo CSV, ya que es mucho más fácil usar Excel para editar el archivo CSV.
    
3. Cree una fila para cada contacto que quiera importar a Exchange Online. Rellene tantas celdas como sea posible. Esta información se mostrará en la libreta de direcciones compartida de cada contacto. 
    
    > [!IMPORTANT]
    >  Las siguientes propiedades (que son los cuatro primeros elementos de la fila de encabezado) son necesarias para crear un contacto externo y deben rellenarse en el archivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. El comando de PowerShell que ejecute en el paso 2 usará los valores de estas propiedades para crear los contactos. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Paso 2: Crear los contactos externos con PowerShell

El siguiente paso es usar el archivo CSV que creó en el paso 1 y PowerShell para importar de forma masiva los contactos externos enumerados en el archivo CSV para Exchange Online. 
  
1.  Conecte PowerShell a la organización Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Asegúrese de usar el nombre de usuario y la contraseña de la cuenta de administrador global al conectarse a Exchange Online PowerShell. 
    
2. Después de conectar PowerShell a Exchange Online, vaya a la carpeta de escritorio donde guardó el archivo CSV en el paso 1; por ejemplo`C:\Users\Administrator\desktop`, .
    
3. Ejecute el siguiente comando para crear los contactos externos:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Puede tardar un tiempo en crear los nuevos contactos, en función de cuántos importes. Cuando el comando termina de ejecutarse, PowerShell muestra una lista de los nuevos contactos que se crearon. 
    
4. Para ver los nuevos contactos externos, vaya al Centro de administración de Exchange (EAC) y, a continuación, haga clic en **Contactos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2182970" target="_blank"></a> 
    
    > [!TIP]
    > Para obtener instrucciones para conectarse al EAC, consulte [Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center). 
  
5. Si es necesario, haga clic en **Actualizar** para actualizar la lista y ver los contactos externos que se importaron. 
    
    Los contactos importados aparecerán en la libreta de direcciones compartida en Outlook y Outlook en la Web.
    
    > [!NOTE]
    > También puede ver los contactos en el Centro de administración de Microsoft 365 yendo a **Contactos de los usuarios**\>. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Paso 3: Agregar información a las propiedades de los contactos externos

Después de ejecutar el comando en el paso 2, se crean los contactos externos, pero no contienen ninguna información de contacto u organización, que es la información de la mayoría de las celdas del archivo CSV. Esto se debe a que al crear nuevos contactos externos, solo se rellenan las propiedades necesarias. No se preocupe si no tiene toda la información rellenada en el archivo CSV. Si no está allí, no se agregará.
  
1.  Conecte PowerShell a la organización Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Vaya a la carpeta de escritorio donde guardó el archivo CSV en el paso 1; por ejemplo, `C:\Users\Administrator\desktop`.
    
3. Ejecute los dos comandos siguientes para agregar las otras propiedades del archivo CSV a los contactos externos que creó en el paso 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > El parámetro  _Manager_ puede ser problemático. Si la celda está en blanco en el archivo CSV, obtendrá un error y no se agregará ninguna información de la propiedad al contacto. Si no necesita especificar un administrador, simplemente elimine  ` -Manager $_.Manager ` del comando de PowerShell anterior. 
  
    De nuevo, es posible que tarde un tiempo en actualizar los contactos, en función de cuántos haya importado en el paso 1. 
    
4. Para comprobar que las propiedades se agregaron a los contactos: 
    
1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>, vaya a **Contactos de destinatarios**\>.
    
2. Haga clic en un contacto y, a continuación, haga clic en **editar** ![icono de edición.](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) para mostrar las propiedades del contacto. 
    
Y eso es todo. Los usuarios pueden ver los contactos y la información adicional en la libreta de direcciones de Outlook y Outlook en la Web.
  
## <a name="add-more-external-contacts"></a>Agregar más contactos externos

Puede repetir los pasos del 1 al 3 para agregar nuevos contactos externos en Exchange Online. Usted o los usuarios de su empresa solo pueden agregar una nueva fila en el archivo CSV para el nuevo contacto. A continuación, puede ejecutar los comandos de PowerShell de los pasos 2 y 3 para crear y agregar información a los nuevos contactos.
  
> [!NOTE]
> Al ejecutar el comando para crear nuevos contactos, es posible que reciba un error que indica que los contactos creados anteriormente ya existen. Pero se crea cualquier nuevo contacto agregado al archivo CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ocultar contactos externos de la libreta de direcciones compartida>

Algunas empresas solo pueden usar contactos externos para que se puedan agregar como miembros de grupos de distribución. En este escenario, es posible que quieran ocultar los contactos externos de la libreta de direcciones compartida. A continuación se muestra cómo hacerlo:
  
1.  Conecte PowerShell a la organización Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Para ocultar un único contacto externo, ejecute el siguiente comando.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Por ejemplo, para ocultar Pilar Pinilla de la libreta de direcciones compartida, ejecute este comando:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Para ocultar todos los contactos externos de la libreta de direcciones compartida, ejecute este comando:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Después de ocultarlos, los contactos externos no se muestran en la libreta de direcciones compartida, pero puede agregarlos como miembros de un grupo de distribución.