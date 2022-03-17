---
title: Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aplica hash y carga la tabla de origen de información confidencial para obtener datos exactos que coincidan con los tipos de información confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d3effe3d46375ffcaec268e4b3fc6d53fc5044e
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526504"
---
# <a name="hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types"></a>Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial

En este artículo se muestra cómo hash y cargar la tabla de origen de información confidencial.

## <a name="hash-and-upload-the-sensitive-information-source-table"></a>Hash y cargar la tabla de origen de información confidencial

En esta fase:

1. configurar un grupo de seguridad personalizado y una cuenta de usuario
2. configurar la herramienta agente de Upload EDM
3. Use la herramienta agente Upload EDM para hash, con un valor de sal, la tabla de origen de información confidencial y cargarla.

El algoritmo hash y la carga se pueden realizar con un equipo o puede separar el paso de hash del paso de carga para mayor seguridad.

Si desea aplicar un algoritmo hash y cargar desde un equipo, tendrá que hacerlo desde un equipo que pueda conectarse directamente a su espacio empresarial de Microsoft 365. Esto requiere que el archivo de tabla de origen de información confidencial de texto sin formato esté en ese equipo para el hash.

Si no desea exponer el archivo de tabla de origen de información confidencial de texto sin formato en el equipo de acceso directo, puede realizar un hash en un equipo que se encuentra en una ubicación segura y, a continuación, copiar el archivo hash y el archivo de sal en un equipo que pueda conectarse directamente al inquilino de Microsoft 365 para cargarlo. En el escenario de hash y carga separados, necesitará el EDMUploadAgent en ambos equipos.

> [!IMPORTANT]
> Si usó el esquema coincidencia exacta de datos y el asistente para tipos de información confidencial para crear el  archivo de esquema, debe descargar el esquema para este procedimiento si aún no lo ha hecho. Vea Export [of the EDM schema file in XML format](sit-get-started-exact-data-match-create-schema.md#export-of-the-edm-schema-file-in-xml-format).

> [!NOTE]
> Si su organización ha configurado la clave de cliente [para Microsoft 365](customer-key-overview.md) en el nivel de inquilino, la coincidencia exacta de datos hará uso de su funcionalidad de cifrado automáticamente. Esto solo está disponible para los inquilinos con licencia E5 en la nube comercial.

### <a name="best-practices"></a>Procedimientos recomendados

Separe los procesos de hashing y carga de los datos confidenciales para que pueda aislar más fácilmente cualquier problema en el proceso.
 
Una vez en producción, mantenga los dos pasos separados en la mayoría de los casos. Al realizar el proceso de hash en un equipo aislado y, a continuación, transferir el archivo para cargarlo en un equipo con conexión a Internet, se asegura de que los datos reales nunca estén disponibles en forma de texto sin formato en un equipo que podría haber estado en peligro debido a su conexión a Internet.

### <a name="ensure-your-sensitive-data-table-doesnt-have-formatting-issues"></a>Asegúrese de que la tabla de datos confidenciales no tiene problemas de formato. 

Antes de hash y cargar los datos confidenciales, realice una búsqueda para validar la presencia de caracteres especiales que pueden causar problemas al analizar el contenido. Puede validar que la tabla está en un formato adecuado para usar con EDM mediante el agente de carga de EDM con la sintaxis siguiente:

```powershell
EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file] 
```

Si la herramienta indica un error de coincidencia en el número de columnas, puede deberse a la presencia de comas o caracteres de comillas dentro de los valores de la tabla que se confunden con delimitadores de columna. A menos que estén rodeando un valor completo, las comillas simples y dobles pueden hacer que la herramienta se desidentifique erróneamente dónde comienza o termina una columna individual. 

**Si encuentra caracteres de comillas sencillas o dobles que rodean valores completos**: puede dejarlos tal como están.

Si encuentras caracteres de comilla única **o comas** dentro de un valor: por ejemplo, el nombre de la persona Tom O'Neil o la ciudad 's-Gravenhage que comienza con un carácter apóstrofe, deberás modificar el proceso de exportación de datos usado para generar la tabla de información confidencial para rodear dichas columnas con comillas dobles.

**Si se encuentran** caracteres de comilla doble dentro de los valores, puede ser preferible usar el formato delimitado por tabulación para la tabla que sea menos susceptible a estos problemas.

### <a name="prerequisites"></a>Requisitos previos

- una cuenta profesional o educativa de Microsoft 365 que se agregará al grupo de seguridad de **EDM\_DataUploaders**
- un Windows 10 o Windows Server 2016 con .NET versión 4.6.2 <!--4.7.2 un comment this around 9/29-->para ejecutar EDMUploadAgent
- un directorio en el equipo de carga para lo siguiente:
  - [Agente de Upload EDM](#links-to-edm-upload-agent-by-subscription-type)
  - el archivo de elemento confidencial en .csv, .tsv o pipe (|), **PatientRecords.csven nuestros** ejemplos
  - los archivos hash y sal de salida creados en este procedimiento
  - el nombre del almacén de datos del archivo **edm.xml** que para este ejemplo es `PatientRecords`

#### <a name="set-up-the-security-group-and-user-account"></a>Configuración de la cuenta de usuario y del grupo de seguridad personalizado

1. Como administrador global, vaya al Centro de administración mediante el [vínculo apropiado para su suscripción](sit-get-started-exact-data-match-based-sits-overview.md#portal-links-for-your-subscription) y [cree un grupo de seguridad](/office365/admin/email/create-edit-or-delete-a-security-group)llamado **EDM\_DataUploaders**.

2. Agregue uno o más usuarios al grupo de seguridad **EDM\_DataUploaders**. (Estos usuarios administrarán la base de datos de información confidencial).

### <a name="hash-and-upload-from-one-computer"></a>Crear un hash y cargar desde un equipo

Este equipo debe tener acceso directo a su espacio empresarial de Microsoft 365.

> [!NOTE]
> Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad **EDM\_DataUploaders**.

> [!TIP] 
>Opcionalmente, puede ejecutar una validación en el archivo de tabla de origen de información confidencial para comprobar si hay errores antes de cargarlo ejecutando:
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> Para obtener más información sobre todos los EdmUploadAgent.exe se ejecutan los parámetros admitidos
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>Vínculos al agente de carga de EDM por tipo de suscripción

- [Comercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): la mayoría de los clientes comerciales deben usarlo
- [GCC alto](https://go.microsoft.com/fwlink/?linkid=2137521): está específicamente diseñado para los suscriptores de nube de administración pública de alta seguridad
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) : está específicamente diseñado para los clientes de la nube del Departamento de defensa de Estados Unidos

1. Cree un directorio de trabajo para EDMUploadAgent. Por ejemplo: **C:\EDM\Data**. Coloque el archivo **RegistrosPacientes.csv** dentro.

2. Descargue e instale el [Agente de carga de EDM](#links-to-edm-upload-agent-by-subscription-type) adecuado para su suscripción en el directorio que creó en el paso 1.

   > [!NOTE]
   > El EDMUploadAgent de los vínculos anteriores se ha actualizado para agregar automáticamente un valor de sal a los datos hash. De forma alternativa, puede brindar su propio valor de sal. Una vez que haya usado esta versión, no podrá usar la versión anterior de EDMUploadAgent.
   >
   > Puede cargar datos con EDMUploadAgent en cualquier almacén de datos determinado solo dos veces al día.

3. Autorizar el agente de Upload EDM, abrir la ventana del símbolo del sistema como administrador, cambiar al directorio **C:\EDM\Data** y, a continuación, ejecutar el siguiente comando:

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> Debe ejecutar el **EdmUploadAgent** desde la carpeta donde está instalado e indicar la ruta de acceso completa a los archivos de datos. 

4. Inicie sesión con su cuenta profesional o educativa de Microsoft 365 que se ha agregado al grupo de seguridad de EDM_DataUploaders. La información de inquilino se extrae de la cuenta de usuario para establecer una conexión.

   OPCIONAL: si usó el esquema coincidencia exacta de datos y el asistente para tipos de información confidencial para crear  el esquema, debe descargarlo para usarlo en estos procedimientos si aún no lo ha hecho. Ejecute este comando en una ventana del símbolo del sistema:

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. Para crear un hash y cargar los datos confidenciales, ejecute el siguiente comando en la ventana del Símbolo del sistema:

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```
   > [!NOTE]
> El formato predeterminado del archivo de datos confidenciales son valores separados por comas. Puede especificar un archivo separado por tabulaciones indicando la opción "{Tab}" con el parámetro /ColumnSeparator, o bien puede especificar un archivo separado por canalización indicando la opción "|".

   Ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5**

Si la tabla de información confidencial tiene algunos valores con formato incorrecto, pero desea importar los datos restantes ignorando filas no válidas de todos modos, puede usar el parámetro */AllowedBadLinesPercentage* en el comando. En el ejemplo anterior se especifica un umbral del cinco por ciento. Esto significa que la herramienta hash y cargará la tabla de información confidencial incluso si hasta el cinco por ciento de las filas no son válidas. 

Este comando agregará automáticamente un valor de sal generado aleatoriamente al hash para mayor seguridad. De forma opcional, si quiere usar su propio valor de sal, agregue **/Salt <saltvalue>** al comando. Este valor debe tener 64 caracteres de longitud y solo puede contener los caracteres a-z y 0-9.

6. Compruebe el estado de la carga al ejecutar este comando:

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   Ejemplo: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

   Verifique que el estado se encuentre en **ProcesamientoEnCurso**. Verifique nuevamente cada pocos minutos hasta que el estado cambie a **Completado**. Una vez que el estado se muestre como completado, los datos de EDM ya están listos para su uso. Según el tamaño del archivo de tabla de origen de información confidencial, esto puede tardar de unos minutos a varias horas. 

> [!TIP]
> Si desea recibir una notificación una vez que los datos confidenciales cargados estén listos para usarse, siga los procedimientos descritos en Crear notificaciones para las actividades [exactas de coincidencia de datos](sit-edm-notifications-activities.md#create-notifications-for-exact-data-match-activities).

### <a name="separate-hash-and-upload"></a>Separe el hash y cargue

Aplique el algoritmo hash en un equipo en un entorno seguro. Debe tener el **EDMUploadAgent** instalado en ambos equipos.

OPCIONAL: si usó el esquema coincidencia exacta de datos y el asistente para tipos de información confidencial para crear el esquema y aún no lo ha descargado, ejecute el siguiente comando en una ventana del símbolo del sistema para descargar el archivo en formato XML:

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. En el equipo del entorno seguro, ejecute el siguiente comando en ventanas del símbolo del sistema:

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   Por ejemplo:

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

> [!NOTE]
> El formato predeterminado del archivo de datos confidenciales son valores separados por comas. Puede especificar un archivo separado por tabulaciones indicando la opción "{Tab}" con el parámetro /ColumnSeparator, o bien puede especificar un archivo separado por canalización indicando la opción "|".


   De este forma, se obtendrá un archivo con hash y un archivo de sal con estas extensiones si no ha especificado la opción **/Salt <saltvalue>**:

   - .EdmHash
   - .EdmSalt


2. Copie estos archivos de forma segura en el equipo que usará para cargar el archivo de tabla de origen de información confidencial (PatientRecords) en su inquilino.

3. Autorizar el agente de Upload EDM, abrir la ventana del símbolo del sistema como administrador, cambiar al directorio **C:\EDM\Data** y, a continuación, ejecutar el siguiente comando:

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> Debe ejecutar el **EdmUploadAgent** desde la carpeta donde está instalado e indicar la ruta de acceso completa a los archivos de datos. 

4. Inicie sesión con su cuenta profesional o educativa de Microsoft 365 que se ha agregado al grupo de seguridad de EDM_DataUploaders. La información de inquilino se extrae de la cuenta de usuario para establecer una conexión.

5. Para cargar los datos con hash, ejecute el siguiente comando en el Símbolo del sistema de Windows:

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\ /ColumnSeparator ["{Tab}"|"|"]
   ```

   Por ejemplo:

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\**PatientRecords.EdmHash**
   ```

6. Para comprobar que se hayan cargado los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```
   Verá una lista de almacenes de datos y la última vez que se actualizaron.

7. Si desea ver todas las cargas de datos en un almacén determinado, ejecute el siguiente comando en un símbolo del sistema de Windows para ver una lista de todos los almacenes de datos y cuándo se actualizaron:

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```
     
## <a name="next-step"></a>Paso siguiente

- [Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package)

