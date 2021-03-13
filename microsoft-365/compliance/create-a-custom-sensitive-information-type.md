---
title: Introducción a los tipos de información confidencial personalizados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear, modificar, quitar y probar tipos personalizados de información confidencial para DLP en la interfaz gráfica de usuario del Centro de seguridad y cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 049c3c123053b4bd833ea95a2413b81366586870
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766371"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>Introducción a los tipos de información confidencial personalizados

Si los tipos de información confidencial predefinidos no satisfacen sus necesidades, puede crear sus propios tipos de información confidencial personalizados. Al hacerlo, puede copiar uno de los tipos predefinidos y modificarlo o definirlo completamente usted mismo.

Los tipos de información confidencial personalizados se agregan al paquete de reglas denominado Microsoft.SCCManaged.CustomRulePack `Microsoft.SCCManaged.CustomRulePack`.

Hay dos formas de crear un tipo de información confidencial:

- [Desde cero (usted define completamente todos los elementos)](#create-a-custom-sensitive-information-type)
- [Copiando un tipo de información confidencial existente y modificándolo](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Antes de empezar

- Debe estar familiarizado con los tipos de información confidencial y saber de qué se componen. Consulte [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md). Es fundamental comprender los roles de:
    - [Las expresiones regulares](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/): los tipos de información confidencial de Microsoft 365 usan el motor Boost.RegEx 5.1.3
    - Listas de palabras clave: puede crear las suyas a medida que defina el tipo de información confidencial o elegir entre listas de palabras clave existentes.
    - [Diccionario de palabras clave](create-a-keyword-dictionary.md)
    - [Funciones](what-the-dlp-functions-look-for.md)
    - [Niveles de confianza](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- Debe contar con los permisos de administrador global o de administrador de cumplimiento para crear, probar e implementar un tipo de información confidencial personalizada por medio de la interfaz de usuario. Vea [Acerca de las funciones de administración](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)en Office 365.


- Su organización debe tener una suscripción, como Office 365 Enterprise, que incluye la prevención de pérdida de datos (DLP). [Ver Política de Mensajería y Servicio de ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc) 


> [!IMPORTANT]
> El soporte técnico y el servicio al cliente de Microsoft no puede ayudar a crear clasificaciones personalizadas o patrones de expresiones regulares. Los ingenieros de soporte técnico pueden ofrecer soporte limitado para la característica como, por ejemplo, proporcionar patrones de expresiones regulares de ejemplo para propósitos de prueba o ayudar con la solución de problemas de un patrón de expresión regular existente que no se activa de la forma esperada. Pero no pueden garantizar que el desarrollo personalizado que coincida con el contenido cumplirá sus requisitos u obligaciones.

## <a name="create-a-custom-sensitive-information-type"></a>Crear un tipo de información confidencial personalizado

Use este procedimiento para crear un nuevo tipo de información confidencial y definirlo usted mismo por completo. 

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial** y elija **Crear tipo de información**.
2. Rellene los valores de **Nombre** y **Descripción** y elija **Siguiente**.
3. Elija **Crear patrón**. Puede crear varios patrones, cada uno con diferentes elementos y niveles de confianza, a medida que defina el nuevo tipo de información confidencial.
4. Elija el valor predeterminado del Nivel de confianza para el patrón. Los valores son **Confianza baja**, **Confianza media** y **Confianza alta**.
5. Elegir y definir el **Elemento principal**. El elemento principal puede ser una **Expresión regular** con un validador opcional, una **lista de palabras clave**, un **diccionario de palabras clave** o una de las **funciones preconfiguradas**. Para obtener más información sobre las funciones DLP, vea [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md).
6. Rellene un valor para **Proximidad de caracteres**.
7. (Opcional) Si los tiene, agregue elementos de soporte. Los elementos de soporte pueden ser una expresión regular con un validador opcional, una lista de palabras clave, un diccionario de palabras clave o una de las funciones predefinidas. 
8.  (Opcional) Agregar [**comprobaciones adicionales**](#more-information-on-additional-checks) de la lista de comprobaciones disponibles.
9. Seleccione **Crear**.
10. Elija **Siguiente**.
11. Elija el **nivel de confianza recomendado** de este tipo de información confidencial.
12. Revise la configuración y elija **Enviar**.

> [!IMPORTANT]
> Microsoft 365 usa el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios de SharePoint Online y OneDrive para la Empresa. Para identificar el nuevo tipo de información confidencial personalizado en el contenido existente, se necesita volver a rastrear el contenido. El contenido se rastrea en función de una programación, pero puede volver a rastrear de forma manual el contenido de una colección de sitios, lista o biblioteca. Para obtener más información, vea [Solicitar manualmente el rastreo y una nueva indexación de un sitio, una biblioteca o una lista](https://docs.microsoft.com/sharepoint/crawl-site-content).

13. En la **clasificación de datos**, verá todos los tipos de información confidencial. Elija **Actualizar** y luego encuentre el tipo de información confidencial que ha creado con la herramienta de búsqueda o explorando.

## <a name="test-a-sensitive-information-type"></a>Cómo probar un tipo de información confidencial personalizado

Puede probar cualquier tipo de información confidencial en la lista. Le recomendamos que pruebe todos los tipos de información confidencial que cree antes de usarlos en una directiva.

1. Prepare dos archivos, por ejemplo documentos de Word. Uno debe tener contenido que coincida con los elementos especificados en el tipo de información confidencial y el otro elementos que no coincidan.
2. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista para abrir el panel de detalles y elija **Probar**.
3. Cargue un archivo y elija **Probar**.
4. En la página **Resultados de coincidencia**, revise los resultados y, después, seleccione **Finalizar**.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Modificar tipos personalizados de información confidencial en el Centro de cumplimiento

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista que desee modificar y seleccione **Editar**.
2. Puede agregar otros patrones, con elementos únicos principales y compatibles, niveles de confianza, proximidad de caracteres y [**comprobaciones adicionales**](#more-information-on-additional-checks), o editar o quitar los existentes.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Quitar tipos personalizados de información confidencial en el Centro de cumplimiento 

> [!NOTE]
> Solo se pueden quitar los tipos personalizados de información confidencial; no se pueden quitar los tipos de información confidencial integrados.

> [!IMPORTANT]
> Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista que desee quitar.
2. En el menú desplegable que se abre, elija **Eliminar**.

## <a name="copy-and-modify-a-sensitive-information-type"></a>Copiar y modificar un tipo de información confidencial existente

Use este procedimiento para crear un nuevo tipo de información confidencial que se base en un tipo de información confidencial existente. 

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial que desee copiar.
2. En el menú flotante, elija **Copiar**.
3. En la lista de tipos de información confidencial, seleccione **Actualizar** y examine o busque la copia que acaba de hacer. Se admite la búsqueda de cadenas parciales, por lo que puede buscar `copy` y la búsqueda le devolverá todos los tipos de información confidencial con la cadena `copy` en el nombre. 
4. Rellene los valores de **Nombre** y **Descripción** y elija **Siguiente**.
5. Elija su copia del tipo de información confidencial y seleccione **Editar**. 
6. Asigne al tipo de información confidencial un **Nombre** y **Descripción** nuevos.
7. Puede elegir editar o quitar los patrones existentes y agregar otros nuevos. Elija el valor predeterminado del Nivel de confianza para el nuevo patrón. Los valores son **Confianza baja**, **Confianza media** y **Confianza alta**.
8. Elegir y definir el **Elemento principal**. El elemento principal puede ser una **Expresión regular**, una **lista de palabras clave**, un **diccionario de palabras clave** o una de las **funciones preconfiguradas**. Consulte [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md).
9. Rellene un valor para **Proximidad de caracteres**.
10. (Opcional) Si tiene **Elementos de apoyo** o [**Controles adicionales**](#more-information-on-additional-checks), agruégelos. Si es necesario, puede agrupar los **Elementos de apoyo**.
11. Seleccione **Crear**.
12. Elija **Siguiente**.
13. Elija el **nivel de confianza recomendado** de este tipo de información confidencial.
14. Revise la configuración y elija **Enviar**.

También puede crear tipos de información confidencial con PowerShell y usar las funciones de coincidencia de datos exacta. Para obtener más información sobre estos métodos, vea:
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Cree un tipo de información confidencial personalizada para DLP con Exact Data Match (EDM) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-additional-checks"></a>Más información sobre comprobaciones adicionales

Aquí tiene las definiciones y algunos ejemplos de las comprobaciones adicionales disponibles.

**Excluir coincidencias específicas**: Esta comprobación le permite definir palabras clave para excluir al detectar coincidencias del patrón que esté editando. Por ejemplo, puede excluir números de prueba de tarjeta de crédito como "4111111111111111", para que no aparezcan como número válido.

**Empezar o no empezar con caracteres**: Esta comprobación le permite definir los caracteres con que los elementos coincidentes pueden o no pueden empezar. Por ejemplo, si quiere que el patrón detecte solo números de tarjeta de crédito que empiece con 41, 42 o 43, seleccione **Empieza con** y agregue 41, 42 y 43 a la lista, separados por comas. 

**Terminar o no terminar con caracteres**: Esta comprobación le permite definir los caracteres con que los elementos coincidentes pueden o no pueden terminar. Por ejemplo, si su número de Id. de empleado no puede terminar con 0 o 1, seleccione **No termina con** y agregue 0 y 1 a la lista, separados por comas.

**Excluir caracteres duplicados**: esta comprobación le permite ignorar coincidencias en las que todos los dígitos son los mismos. Por ejemplo, si el número de Id. de empleado tiene seis dígitos y no son iguales, puede seleccionar **Excluir caracteres duplicados** para excluir 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999, y 000000 de la lista de coincidencias válidas para la Id. del empleado.

**Incluir o excluir prefijos**: Esta comprobación le permite definir las palabras clave que deben o no deben aparecer inmediatamente antes de la entidad coincidente. En función de su selección, las entidades aparecerán o no como coincidencias si son precedidas por los prefijos que incluya aquí. Por ejemplo, si **Excluye** el prefijo **GUID:**, toda entidad precedida por **GUID:** no se considerará una coincidencia.

**Incluir o excluir sufijos**: Esta comprobación le permite definir las palabras clave que deben o no deben aparecer inmediatamente después de la entidad coincidente. En función de su selección, las entidades aparecerán o no como coincidencias si aparecen seguidas de los sufijos que incluya aquí. Por ejemplo, si **Excluye** el sufijo **GUID:**, cualquier texto seguido de **GUID:** no se considerará una coincidencia.


> [!NOTE]
> Information Protection de Microsoft 365 es compatible, en modo de versión preliminar, con el conjunto de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
>Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).