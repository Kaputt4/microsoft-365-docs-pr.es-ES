---
title: Aplicar Information Rights Management (IRM) a una lista o biblioteca
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233356"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Aplicar Information Rights Management (IRM) a una lista o biblioteca

Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas. Esta característica solo se admite en la nube global de Microsoft. IRM no es compatible con SharePoint listas y bibliotecas en implementaciones de nube nacionales.
  
## <a name="administrator-preparations-before-applying-irm"></a>Preparación del administrador antes de aplicar IRM

- El Azure Rights Management (Azure RMS) de Azure Information Protection y el equivalente local, Active Directory Rights Management Services (AD RMS), admiten Information Rights Management para sitios. No se requieren instalaciones independientes ni adicionales.

- Antes de aplicar IRM a una lista o biblioteca, debe habilitar IRM para el sitio. Necesitará permisos de administrador para habilitar IRM.

- Para aplicar IRM a una lista o biblioteca, debe tener permisos de administrador para esa lista o biblioteca.

- Si usas SharePoint Online, es posible que los usuarios experimente tiempos de espera al descargar archivos protegidos por IRM más grandes. Para evitar tiempos de espera, use los programas Office para aplicar la protección IRM y almacenar archivos más grandes en una biblioteca de SharePoint que no use IRM.

> [!NOTE]
> Si usa SharePoint Server 2013, un administrador del servidor debe instalar protectores en todos los servidores front-end web para cada tipo de archivo que las personas de su organización quieran proteger mediante IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>Aplicar IRM a una lista o biblioteca
<a name="__toc256598179"> </a>

![Information Rights Management Configuración](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Vaya a la lista o biblioteca para la que desea configurar IRM.

2. En la cinta de opciones, seleccione la **pestaña** Biblioteca y, a continuación, **seleccione Biblioteca Configuración**. (Si está trabajando en una lista, seleccione la pestaña **Lista** y, a continuación, seleccione **Lista Configuración**).
    
    ![SharePoint Botones Configuración biblioteca en la cinta de opciones](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. En **Permisos y administración,** seleccione **Information Rights Management**. Si no aparece el vínculo Information Rights Management, es posible que IRM no esté habilitado para el sitio. Póngase en contacto con el administrador del servidor para ver si puede habilitar IRM para su sitio. El **vínculo Information Rights Management** no aparece para las bibliotecas de imágenes.

4. En la página de Configuración Information Rights  **Management,** active la casilla Restringir permisos a documentos de esta biblioteca al descargar para aplicar permisos restringidos a los documentos que los usuarios descargan de esta lista o biblioteca.

5. En el **cuadro Crear un título de directiva de permisos,** escriba un nombre descriptivo para la directiva. Use un nombre que le ayude a identificar esta directiva desde otras directivas. Por ejemplo, use **Company Confidential** para aplicar permisos restringidos a una lista o biblioteca que contenga documentos confidenciales de la empresa.

6. En el cuadro Agregar una descripción de directiva de permisos, escriba una descripción que se mostrará **a** las personas que usan esta lista o biblioteca que explique cómo deben controlar los documentos de esta lista o biblioteca. Por ejemplo, puede escribir **Analizar** el contenido de este documento solo con otros empleados si desea restringir el acceso a la información de estos documentos a los empleados internos. 

7. Para aplicar restricciones adicionales a los documentos de esta lista o biblioteca, seleccione **Mostrar opciones** y realice una de las siguientes acciones:

|**Para ello:**|**Haga lo siguiente:**|
|:-----|:-----|
|Permitir que las personas impriman documentos de esta lista o biblioteca|Active la **casilla Permitir que los visores impriman.**|
|Permitir que las personas con al menos el permiso Ver elementos ejecuten código incrustado o macros en un documento.|Active la **casilla Permitir que los visores ejecuten el script y** el lector de pantalla para que funcionen en documentos descargados. Si selecciona esta opción, los usuarios podrían ejecutar código para extraer el contenido de un documento.           |
|Seleccione esta opción si desea restringir el acceso al contenido a un período de tiempo especificado. Si selecciona esta opción, las licencias de emisión de personas para obtener acceso al contenido expirarán después del número de días especificado y los usuarios tendrán que volver al servidor para comprobar sus credenciales y descargar una nueva copia.|Active la casilla Después de la descarga, los derechos de acceso de documentos expirarán después de este número de días **(1-365)** y, a continuación, especifique el número de días para los que desea que el documento se pueda ver.|
| Impedir que los usuarios carguen documentos que no admitan IRM en esta lista o biblioteca. Si selecciona esta opción, los usuarios no podrán cargar ninguno de los siguientes tipos de archivo: tipos de archivo que no tienen instalados protectores IRM correspondientes en todos los servidores front-end web. Los tipos de archivo SharePoint Server 2010 no se pueden descifrar. Tipos de archivo protegidos por IRM en otro programa.|Active la **casilla No permitir que los usuarios carguen documentos que no admitan IRM.**|
|Quite los permisos restringidos de esta lista o biblioteca en una fecha específica.|Active la **casilla Dejar de restringir el acceso** a la biblioteca en y, a continuación, seleccione la fecha que desee.|
|Controle el intervalo que las credenciales se almacenan en caché para el programa con licencia para abrir el documento.|Active la casilla Los usuarios deben comprobar sus credenciales con este intervalo **(días)** y, a continuación, escriba el intervalo para las credenciales de almacenamiento en caché en número de días.|
|Permitir la protección de grupos para que los usuarios puedan compartir con miembros del mismo grupo.|Seleccione **Permitir protección de** grupo y escriba el nombre del grupo para compartir.|

8. Una vez que termine de seleccionar las opciones que desee, seleccione **Aceptar**.
  
## <a name="what-is-information-rights-management"></a>¿Qué es Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) permite limitar las acciones que los usuarios pueden realizar en los archivos que se han descargado de listas o bibliotecas. IRM cifra los archivos descargados y limita el conjunto de usuarios y programas que pueden descifrarlos. IRM también puede limitar los derechos de los usuarios con permiso para leer archivos, de modo que no puedan realizar acciones como, por ejemplo, imprimir copias o copiar el texto de los mismos.
  
Puede usar IRM en listas o bibliotecas para limitar la difusión de contenido confidencial. Por ejemplo, si va a crear una biblioteca de documentos para compartir información sobre los próximos productos con representantes de marketing seleccionados, puede usar IRM para evitar que estas personas compartan este contenido con otros empleados de la empresa.
  
En un sitio, se aplica IRM a una lista o biblioteca completa, en lugar de a archivos individuales. Esto facilita garantizar un nivel coherente de protección para todo un conjunto de documentos o archivos. Por lo tanto, IRM puede ayudar a su organización a aplicar directivas corporativas que rigen el uso y la difusión de información confidencial o de propiedad.
  
> [!NOTE]
> La información de esta página sobre Information Rights Management reemplaza los términos que hacen referencia a "Information Rights Management" en cualquier contrato de términos de licencia de Microsoft SharePoint Server 2013 y SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Cómo IRM puede ayudar a proteger el contenido
<a name="__toc256598176"> </a>

IRM ayuda a proteger el contenido restringido de las siguientes maneras:
  
- Ayuda a evitar que un visor autorizado copie, modifique, imprima, envíe faxes o copie y pega el contenido para un uso no autorizado
    
- Ayuda a evitar que un visor autorizado copie el contenido mediante la característica Imprimir pantalla en Microsoft Windows
    
- Ayuda a evitar que un visor no autorizado vea el contenido si se envía por correo electrónico después de descargarlo del servidor
    
- Restringe el acceso al contenido a un período de tiempo especificado, tras el cual los usuarios deben confirmar sus credenciales y volver a descargar el contenido
    
- Ayuda a aplicar directivas corporativas que rigen el uso y la difusión de contenido dentro de la organización
    
### <a name="how-irm-cannot-help-protect-content"></a>Cómo IRM no puede ayudar a proteger el contenido
<a name="__toc256598177"> </a>

IRM no puede proteger el contenido restringido de lo siguiente:
  
- Borrado, robo, captura o transmisión por programas malintencionados como troyanos, registradores de pulsaciones de teclas y ciertos tipos de spyware
    
- Pérdida o daños debido a las acciones de virus informáticos
    
- Copiar o volver a copiar manualmente el contenido de la pantalla en una pantalla
    
- Fotografía digital o cinematográfica de contenido que se muestra en una pantalla
    
- Copiar mediante el uso de programas de captura de pantalla de terceros
    
- Copia de metadatos de contenido (valores de columna) mediante el uso de programas de captura de pantalla de terceros o la acción de copiar y pegar
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Cómo funciona IRM para listas y bibliotecas
<a name="__toc256598178"> </a>

La protección de IRM se aplica a los archivos en el nivel de lista o biblioteca. Cuando IRM está habilitado para una biblioteca, la administración de derechos se aplica a todos los archivos de esa biblioteca. Cuando IRM está habilitado para una lista, la administración de derechos solo se aplica a los archivos adjuntos a los elementos de lista, no a los elementos de lista reales.
  
Cuando las personas descargan archivos en una lista o biblioteca habilitada para IRM, los archivos se cifran para que solo los usuarios autorizados puedan verlos. Cada archivo administrado por derechos también contiene una licencia de emisión que impone restricciones a las personas que ven el archivo. Entre las restricciones típicas se incluyen hacer un archivo de solo lectura, deshabilitar la copia de texto, impedir que los usuarios guarden una copia local y evitar que los usuarios impriman el archivo. Los programas cliente que pueden leer tipos de archivo compatibles con IRM usan la licencia de emisión dentro del archivo administrado por derechos para aplicar estas restricciones. Así es como un archivo administrado por derechos conserva su protección incluso después de descargarlo del servidor.
  
Los tipos de restricciones que se aplican a un archivo cuando se descarga de una lista o biblioteca se basan en los permisos del usuario individual en el sitio que contiene el archivo. En la tabla siguiente se explica cómo los permisos de los sitios corresponden a los permisos de IRM.
  
|**Permisos**|**Permisos de IRM**|
|:-----|:-----|
|Administrar permisos, administrar sitio web|**Control total** (tal como lo define el programa cliente): este permiso generalmente permite a un usuario leer, editar, copiar, guardar y modificar permisos de contenido administrado con derechos.|
|Editar elementos, administrar listas, agregar y personalizar páginas|**Editar**, **Copiar** y **Guardar:** un usuario solo  puede imprimir un archivo si la casilla Permitir que los usuarios impriman documentos está activada en la página Information Rights Management Configuración para la lista o biblioteca.|
|Ver elementos|**Lea:** Un usuario puede leer el documento, pero no puede copiar ni modificar su contenido. Un usuario solo puede  imprimir si la casilla Permitir que los usuarios impriman documentos está activada en la página Information Rights Management Configuración la lista o biblioteca.|
|Otros|Ningún otro permiso corresponde directamente a los permisos de IRM.|
   
Cuando habilita IRM para una lista o biblioteca en SharePoint Server 2013, solo puede proteger los tipos de archivo de esa lista o biblioteca para la que está instalado un protector en todos los servidores front-end web. Un protector es un programa que controla el cifrado y descifrado de archivos administrados con derechos de un formato de archivo específico. SharePoint incluye protectores para los siguientes tipos de archivo:
  
- Microsoft Office Formularios de InfoPath
    
- Los formatos de archivo 97-2003 para los siguientes Microsoft Office: Word, Excel y PowerPoint
    
- El Office open XML para los siguientes Microsoft Office: Word, Excel y PowerPoint
    
- Formato de especificación de papel XML (XPS)
    
Si su organización planea usar IRM para proteger cualquier otro tipo de archivo además de los enumerados anteriormente, el administrador del servidor debe instalar protectores para estos formatos de archivo adicionales.
  

