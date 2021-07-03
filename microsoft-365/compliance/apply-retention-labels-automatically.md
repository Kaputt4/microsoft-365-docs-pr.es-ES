---
title: Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Cree etiquetas de retención y directivas de etiquetado automático para aplicar etiquetas de manera automática y así conservar lo que necesita y eliminar lo que no
ms.openlocfilehash: be5df165ee64a890fbf762e81668420d5d3c88de
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287154"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Este escenario no es compatible con los [registros normativos](records-management.md#records).

Una de las características más eficaces de las [etiquetas de retención](retention.md) es la capacidad de aplicarlas automáticamente al contenido que coincide con condiciones especificadas. En este caso, no es necesario que las personas de la organización apliquen las etiquetas de retención. Microsoft 365 realiza el trabajo por ellos.
  
Las etiquetas de retención auto aplicadas son poderosas porque:
  
- No es necesario formar a los usuarios para que conozcan todas las clasificaciones.
    
- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
    
- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.
    
Las etiquetas de retención se pueden aplicar a contenido automáticamente cuando dicho contenido contiene información confidencial, palabras clave o propiedades que permiten búsquedas, o una coincidencia para [clasificadores que se puedan entrenar](classifier-get-started-with.md).

> [!TIP]
> Según las publicaciones recientes, en la versión preliminar, puede utilizar las propiedades que permiten búsquedas para identificar las [grabaciones de reuniones de Teams](#microsoft-teams-meeting-recordings).

Los procesos para aplicar automáticamente una etiqueta de retención se basan en estas condiciones:

![Diagrama de roles y tareas para etiquetas de aplicación automática](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

Utilice las siguientes instrucciones para los dos pasos de administrador.

> [!NOTE]
> Las directivas automáticas emplean etiquetado del lado del servicio con condiciones para aplicar etiquetas de retención automáticamente. También puede aplicar automáticamente una etiqueta de retención con una directiva de etiqueta al hacer lo siguiente: 
>
> - Puede aplicar fácilmente una etiqueta de retención a un modelo de comprensión mediante documentos en SharePoint Syntex.
> - Aplicar una etiqueta de retención predeterminada para SharePoint y Outlook
>- Aplicar una etiqueta de retención al correo electrónico mediante el uso de reglas de Outlook
>
> Para estos escenarios, consulte [Crear y aplicar etiquetas de retención en aplicaciones](create-apply-retention-labels.md).

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y modificar etiquetas de retención y las directivas de las mismas. Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-auto-apply-a-retention-label"></a>Cómo aplicar automáticamente una etiqueta de retención

En primer lugar, cree la etiqueta de retención. A continuación, cree una directiva automática para aplicar dicha etiqueta. Si ya ha creado la etiqueta de retención, consulte [Crear una directiva automática](#step-2-create-an-auto-apply-policy).

Las instrucciones de navegación dependerán de si está usando o no la [administración de registros](records-management.md). Se proporcionan instrucciones para ambos escenarios.

### <a name="step-1-create-a-retention-label"></a>Paso 1: Cree una etiqueta de retención

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes ubicaciones:
    
    - Si utiliza la administración de registros:
        - **Soluciones** > **Administración de registros** > pestaña **Plan de archivos** tab > **+ Crear una etiqueta** > **Etiqueta de retención**
        
    - Si no está utilizando la administración de registros:
       - **Soluciones** > **Gobierno de información** > pestaña **Etiquetas** > + **Crear una etiqueta**
    
    ¿No ve su opción inmediatamente? Primero seleccione **Mostrar todo**. 

2. Siga las instrucciones del asistente. Si utiliza la administración de registros:
    
    - Para obtener información sobre los descriptores del plan de archivos, consulte [Usar plan de archivos para administrar etiquetas de retención](file-plan-manager.md) 
    
    - Para usar la etiqueta de retención para declarar registros, seleccione **Marcar elementos como registros** o **Marcar elementos como registros normativos**. Para obtener más información, vea [Configurar etiquetas de retención para declarar registros](declare-records.md#configuring-retention-labels-to-declare-records).

3. Después de crear la etiqueta y ver las opciones para publicar la etiqueta, aplique la etiqueta automáticamente o simplemente guárdela: seleccione **Aplicar esta etiqueta automáticamente a un tipo de contenido específico** y luego, seleccione **Finalizado** para iniciar el Asistente para la creación de etiquetas automáticas, que lo llevará directamente al paso 2 del procedimiento siguiente.

Para editar una etiqueta existente, selecciónela y después seleccione la opción **Editar etiqueta** para iniciar el Asistente de edición de etiquetas de retención, el cual le permite cambiar las descripciones de las etiquetas, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.

### <a name="step-2-create-an-auto-apply-policy"></a>Paso 2: Cree una directiva de aplicación automática

Cuando se crea una directiva de aplicación automática, se selecciona una etiqueta de retención para aplicarla automáticamente a contenido, en función de las condiciones especificadas.

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:
    
    - Si utiliza la administración de registros:**Gobierno de información**:
        - **Soluciones** > **Administración de registros** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**
    
    - Si no está utilizando la administración de registros:
        - **Soluciones** > **Gobierno de información** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**
    
    ¿No ve su opción inmediatamente? Primero seleccione **Mostrar todo**. 

2. Siga las indicaciones del Asistente para la creación de etiquetas automáticas.
    
    Para obtener información sobre la configuración de las condiciones que aplican automáticamente la etiqueta de retención, consulte la sección [Configuración de las condiciones para la aplicación automática de etiquetas de retención en](#configuring-conditions-for-auto-apply-retention-labels) esta página.
    
    Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](retention.md#retention-label-policies-and-locations).

Para editar una directiva existente de aplicación automática, selecciónela para iniciar el Asistente para editar directivas de retención, el cual le permite cambiar la etiqueta de retención seleccionada, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.

Después de etiquetar el contenido con una directiva de la etiqueta de aplicación automática, la etiqueta aplicada no se puede quitar o cambiar automáticamente cambiando el contenido o la directiva, o una nueva directiva de etiqueta de aplicación automática. Para obtener más información, vea [Solo una etiqueta de retención al mismo tiempo](retention.md#only-one-retention-label-at-a-time).

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Configurar las condiciones para la aplicación automática de etiquetas de retención

Puede aplicar etiquetas de retención al contenido automáticamente cuando éste contiene:

- [Tipos específicos de información confidencial](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [Palabras clave específicas o propiedades que permiten búsquedas que coinciden con una consulta que usted creó](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Una coincidencia para clasificadores que se pueden entrenar](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Aplicar automáticamente etiquetas a los contenidos con tipos específicos de información sensible

> [!WARNING]
> Actualmente, esta configuración tiene una limitación conocida, por la que todos los correos electrónicos sin etiqueta siempre tienen la etiqueta de retención seleccionada aplicada cuando hay una coincidencia para los tipos de información confidencial seleccionados. Por ejemplo, incluso si especifica el ámbito de la directiva de aplicación automática para usuarios específicos o para seleccionar ubicaciones distintas de Exchange para la directiva, la etiqueta siempre se aplicará a los correos electrónicos sin etiqueta cuando haya una coincidencia.

Al crear directivas de etiquetas de retención de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que cuando se crea una directiva de prevención de pérdida de datos (DLP). Cada plantilla está preconfigurada para buscar determinados tipos de información confidencial. En el siguiente ejemplo, los tipos de información confidencial son de la categoría **Privacidad**, y **la plantilla de datos de información personal identificable (PII) de Estados Unidos** :

![Plantillas de directiva con tipos de información confidencial](../media/sensitive-info-configuration.png)

Para obtener más información sobre los tipos de información confidencial, consulte [Definiciones de entidad del tipo de información confidencial](sensitive-information-type-entity-definitions.md). Actualmente, las [coincidencias exactas de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) y la [creación de huella digital de documento](document-fingerprinting.md) no son compatibles con este escenario.

Después de seleccionar una plantilla de política, puede añadir o eliminar cualquier tipo de información sensible, y puede cambiar el nivel de confianza y el recuento de instancias. En la captura de pantalla del ejemplo anterior, estas opciones se han cambiado para que se aplique automáticamente una etiqueta de retención sólo cuando:
  
- El tipo de información confidencial que se detecta tiene una precisión de coincidencia (o [nivel de confianza](sensitive-information-type-learn-about.md#more-on-confidence-levels)) de al menos **media confianza** para dos de los tipos de información confidencial, y **alta confianza** para uno. Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una mayor precisión de coincidencia requiere más pruebas para ser encontrado (por ejemplo, palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior requiere menos pruebas. Cuanto menor sea el nivel de confianza, más fácil será que el contenido coincida con la condición, pero con la posibilidad de que haya más falsos positivos.

- El contenido tiene entre 1 y 9 instancias de cualquiera de estos tres tipos de información confidencial. El valor predeterminado para **a** es **Cualquiera**.

Para obtener más información sobre estas opciones, consulte las siguientes instrucciones de la documentación DLP: [Ajustar las reglas para que sea más o menos fácil que coincidan](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Que debe tener en cuenta al usar tipos de información confidencial para aplicar las etiquetas de retención automáticamente:

- Se pueden usar etiquetas automáticamente para los elementos nuevos y modificados.

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Aplicar automáticamente etiquetas a contenido con palabras clave o propiedades que se puedan buscar

Puede aplicar etiquetas automáticamente al contenido mediante una consulta que contenga palabras, frases o valores de propiedades que permiten búsquedas específicos. Puede restringir la consulta con operadores de búsqueda como Y, O y NO.

![Editor de consultas](../media/new-retention-query-editor.png)

Para obtener más información sobre la sintaxis de consulta que usa el Lenguaje de consultas de palabras clave (KQL), vea [Referencia de la sintaxis del Lenguaje de consultas de palabras clave (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

Las directivas de aplicación automática basadas en consultas usan el mismo índice de búsqueda que la búsqueda de contenido en eDiscovery para identificar el contenido. Para obtener más información sobre las propiedades utilizables en búsqueda que puede usar, vea [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de contenido](keyword-queries-and-search-conditions.md).

Aspectos que debe tener en cuenta al usar palabras clave o propiedades utilizables en búsqueda para las etiquetas de retención de aplicación automática:

- Los elementos nuevos, modificados y existentes se etiquetarán automáticamente para SharePoint, OneDrive y Exchange.

- Para SharePoint, las propiedades rastreadas y las propiedades personalizadas no son compatibles con estas consultas de KQL y solo debe usar propiedades administradas predefinidas para documentos. Sin embargo, puede usar las asignaciones en el nivel de espacio empresarial con las propiedades administradas predefinidas que se habilitan como refinadores de forma predeterminada (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 y RefinableDouble00-09). Para obtener más información, vea [Información general de propiedades administradas y rastreadas en SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview) y para obtener instrucciones, consulte [Crear una nueva propiedad administrada](/sharepoint/manage-search-schema#create-a-new-managed-property).

- Si asigna una propiedad personalizada a una de las propiedades de refinador, espere 24 horas antes de usarla en la consulta de KQL para una etiqueta de retención.

- Aunque se puede cambiar el nombre de las propiedades administradas de SharePoint mediante alias, no los use para las consultas de KQL en las etiquetas. Siempre debe especificar el nombre real de la propiedad administrada, por ejemplo, "RefinableString01".

- Para buscar valores que contengan espacios o caracteres especiales, use comillas dobles (`" "`) en la frase. Por ejemplo, `subject:"Financial Statements"`.

- Use la propiedad *DocumentLink* en lugar de *Path* para hacer coincidir un elemento basándose en su URL. 

- No se admiten las búsquedas con caracteres comodín de sufijo (como `*cat`) o las búsquedas con caracteres comodín de subcadena (como `*cat*`). Sin embargo, se admiten las búsquedas comodín de prefijo (como `cat*`).

- Tenga en cuenta que los elementos parcialmente indexados pueden causar que no se etiquete los elementos que espera, o que se etiquete los elementos que esperaba excluir de la etiquetación cuando use el operador NOT. Para más información, vea [Elementos parcialmente indexados en la Búsqueda de contenido](partially-indexed-items-in-content-search.md).


Consultas de ejemplos:

| Carga de trabajo | Ejemplo |
|:-----|:-----|
|Exchange   | `subject:"Financial Statements"` |
|Exchange   | `recipients:garthf@contoso.com` |
|SharePoint | `contenttype:document` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|Exchange o SharePoint | `"customer information" OR "private"`|

Ejemplos más complejos:

La siguiente consulta para SharePoint identifica documentos de Word u hojas de cálculo de Excel cuando contienen las palabras clave **contraseña**, **contraseñas** o **clave**:

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

La siguiente consulta para Exchange identifica cualquier documento de Word o PDF que contenga la palabra **nda** o la frase **acuerdo de no divulgación** cuando estos documentos se adjuntan a un correo electrónico:

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

La siguiente consulta para SharePoint identifica documentos que contienen un número de tarjeta de crédito: 

```
sensitivetype:"credit card number"
```

La siguiente consulta contiene algunas de las palabras clave típicas para identificar documentos o correos electrónicos que incluyan contenido legal válido:

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

La siguiente consulta contiene palabras clave típicas para identificar documentos o correos electrónicos para recursos humanos: 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

Tenga en cuenta que este último ejemplo usa el procedimiento recomendado para incluir siempre operadores entre palabras clave. Usar un espacio entre palabras clave (o dos expresiones propiedad:valor) es igual que usar AND. Al ir agregando los operadores, resulta más fácil ver que esta consulta de ejemplo identifica solo contenido que incluya todas las palabras clave, y no contenido con solo alguna de ellas. Si su intención es identificar el contenido que incluya alguna de las palabras clave, especifique OR en lugar de AND. Como se muestra en este ejemplo, al especificar siempre los operadores, es más fácil interpretarlos correctamente. 

##### <a name="microsoft-teams-meeting-recordings"></a>Grabaciones de reuniones de Microsoft Teams

> [!NOTE]
> La posibilidad de conservar y eliminar las grabaciones de reuniones de Teams no funcionará antes de guardar las grabaciones en OneDrive o SharePoint. Para más información, consulte [Usar OneDrive para la Empresa y SharePoint Online o Stream para las grabaciones de reuniones](/MicrosoftTeams/tmr-meeting-recording-change).

Para identificar las grabaciones de reuniones de Microsoft Teams almacenadas en cuentas de OneDrive de los usuarios o en SharePoint, especifique lo siguiente para el **Editor de consultas de palabras clave**:

```
ProgID:Media AND ProgID:Meeting
```

La mayoría de las veces, las grabaciones de reuniones se guardan en OneDrive. Pero, en el caso de las reuniones de canal, las grabaciones se guardan en SharePoint.


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Aplicar automáticamente etiquetas al contenido con clasificadores que se pueden entrenar

Si elige la opción para un clasificador que se puede entrenar, puede seleccionar uno de los clasificadores integrado o un clasificador personalizado. Los clasificadores integrados incluyen **Currículum**, **Código fuente**, **Código fuente**, **Acoso selectivo**, **Amenazas**:

![Elegir clasificador que se puede entrenar](../media/retention-label-classifers.png)

> [!CAUTION]
> Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No use este clasificador incorporado y si lo está usando actualmente, debería mover sus procesos de negocios fuera de él. Recomendamos que usen los clasificadores integrados de **Acoso selectivo**, **Blasfemias**, **Amenazas**

Para aplicar una etiqueta automáticamente usando esta opción, los buzones y sitios de SharePoint deben tener al menos 10 MB de datos.

Para más información sobre los clasificadores que se pueden entrenar, consulte [Información sobre los clasificadores que se pueden entrenar (versión preliminar)](classifier-learn-about.md).

> [!TIP]
> Si usa clasificadores que se pueden entrenar para Exchange, consulte [Cómo volver a entrenar a un clasificador en el explorador de contenido (versión preliminar)](classifier-how-to-retrain-content-explorer.md).

Que debe tener en cuenta al usar clasificadores que se pueden entrenar para aplicar las etiquetas de retención automáticamente:

- Se pueden usar etiquetas automáticamente para los elementos nuevos y modificados, y los elementos existentes de los últimos seis meses.

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Tiempo que tardan las etiquetas de retención en aplicarse

Si aplica automáticamente las etiquetas de retención, puede tardar hasta siete días en aplicar las etiquetas de retención a todo el contenido existente que coincida con las condiciones.
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

Si las etiquetas que esperaba no aparecen después de siete días, compruebe el **Estado** de la directiva de aplicación automática seleccionándola en la página **Directivas de etiqueta** en el Centro de cumplimiento. Si ve el estado como **Desactivado (error)** y, en los detalles de las ubicaciones, un mensaje indica que se está tardando más de lo esperado en implementar la directiva (para SharePoint) o en probar la implementación de la directiva (para OneDrive), pruebe a ejecutar el comando [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) en PowerShell para volver a intentar la distribución de la directiva:

1. [Conéctese al Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando:
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a>Actualización de las etiquetas de retención y de sus directivas

Si edita una etiqueta de retención o una directiva de aplicación automática y la etiqueta de retención ya se aplica al contenido, la configuración actualizada se aplicará automáticamente a este contenido, además de al contenido recién identificado.

Después de crear y guardar la etiqueta o la directiva, no se pueden cambiar algunas opciones de configuración, entre las que se incluyen:
- El nombre de la etiqueta de retención, la directiva de retención, y la configuración de retención, excepto el período de retención. Sin embargo, no se puede cambiar el período de retención cuando el período de retención se basa en la etiqueta de los elementos.
- La opción de marcar los elementos como un registro.

### <a name="deleting-retention-labels"></a>Eliminar etiquetas de retención

Puede eliminar las etiquetas de retención que no estén actualmente incluidas en ninguna directiva de etiquetas de retención, que no estén configuradas para la retención basada en eventos o que marquen elementos como registros normativos.

En el caso de las etiquetas de retención que sí puede eliminar, si fueron aplicadas a los elementos, se producirá un error en la eliminación y aparece un vínculo al explorador de contenido para identificar los elementos etiquetados.

Sin embargo, podría tomarle hasta dos días al explorador de contenido mostrar los elementos que están etiquetados. En este escenario, es posible que la etiqueta de retención se elimine sin mostrarle el vínculo al explorador de contenido.

## <a name="locking-the-policy-to-prevent-changes"></a>Bloquear la directiva para impedir que se realicen cambios

Si necesita asegurarse de que nadie pueda inhabilitar la directiva, eliminar la directiva o hacer que sea menos restrictiva, consulte [Usar el Bloqueo de conservación para restringir los cambios en directivas de retención y directivas de etiquetas de retención](retention-preservation-lock.md).

## <a name="next-steps"></a>Siguientes pasos

Consulte [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md) para obtener un escenario de ejemplo que usa una directiva de etiqueta de retención de aplicación automática con propiedades administradas en SharePoint y una retención basada en eventos para iniciar el período de retención.