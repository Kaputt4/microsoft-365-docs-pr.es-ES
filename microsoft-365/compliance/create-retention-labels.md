---
title: Crear, publicar y aplicar automáticamente etiquetas de retención
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
description: Instrucciones para crear, publicar y aplicar automáticamente etiquetas de retención para retener lo que se necesita, eliminar lo que no se necesita y declarar un elemento como un registro en el entorno de Office 365.
ms.openlocfilehash: a3ba321c9eae91bf701646a45271d3edcbc8dccc
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545962"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a>Crear, publicar y aplicar automáticamente etiquetas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Utilice la siguiente información para ayudarle a crear [etiquetas de retención](labels.md), y luego aplicarlas automáticamente a los documentos y correos electrónicos, o publicarlas para que los usuarios puedan aplicarlas manualmente.

Las etiquetas de retención lo ayudan a retener lo que necesita y a eliminar lo que no. También se utilizan para declarar un artículo como registro como parte de una solución de[administración de registros](records-management.md) para sus datos de Microsoft 365.

El lugar donde se crean y configuran las etiquetas de retención depende de si se utiliza la administración de registros o no. Se proporcionan instrucciones para ambos escenarios.

## <a name="before-you-begin"></a>Antes de empezar

Los miembros de su equipo de cumplimiento que vayan a crear las etiquetas de retención necesitan permisos para el Centro de &amp;Seguridad y Cumplimiento. De forma predeterminada, el administrador de inquilinos tendrá acceso a esta ubicación y puede otorgar acceso a los oficiales de cumplimiento y a otros usuarios al Centro de &amp;Cumplimiento y Seguridad, sin concederles todos los permisos de un administrador de inquilinos. Para hacerlo, le recomendamos que vaya a la página **Permisos** del Centro de &amp;Cumplimiento y Seguridad, edite el grupo de roles del **Administrador de Cumplimiento** y agregue miembros a ese grupo de roles. 
  
Para obtener más información, vea [Conceder acceso a los usuarios al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Estos permisos solo son necesarios para crear y aplicar etiquetas de retención y una directiva de etiquetas. La aplicación de directivas no necesita acceso al contenido.

## <a name="create-and-configure-retention-labels"></a>Crear y configurar las etiquetas de retención

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:
    
    - Si utiliza la administración de registros:
        - **Soluciones** > **Administración de registros** > pestaña**Plan de archivos** tab > **+ Crear una etiqueta** > **Etiqueta de retención**
        
    - Si no está utilizando la administración de registros:
       - **Soluciones** > **Gobierno de información** > pestaña**Etiquetas** > + **Crear una etiqueta**
    
    ¿No ve su opción inmediatamente? Primero seleccione **Mostrar todo**. 

2. Siga las instrucciones del asistente. Si utiliza la administración de registros:
    
    - Para obtener información sobre los descriptores del plan de archivos, consulte [Usar plan de archivos para administrar etiquetas de retención](file-plan-manager.md) 
    
    - Para utilizar la etiqueta de retención para declarar el contenido como un registro, active la casilla de verificación**Utilizar la etiqueta para clasificar el contenido como "Registro"**.

3. Repita estos pasos para crear más etiquetas.

Para editar una etiqueta existente, selecciónela y después seleccione **Editar etiqueta** para iniciar el mismo asistente que le permite cambiar las descripciones de las etiquetas y cualquier [configuración elegible](#updating-retention-labels-and-their-policies) del paso 2. Como alternativa, seleccione cualquiera de las opciones disponibles de **Editar** para ir directamente a la página correspondiente y actualizar.

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a>Publicar etiquetas de retención creando una directiva de etiquetas de retención

Publicar etiquetas de retención para que puedan ser aplicadas manualmente por los usuarios.

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:
    
    - Si utiliza la administración de registros:
        - **Soluciones** > **Administración de registros ** > > pestaña**Directivas de etiquetas** > **Etiquetas publicadas**
    
    - Si no está utilizando la administración de registros:
        - **Soluciones** > **Gobierno de información** > pestaña**Directivas de etiquetas** > **Publicar etiquetas**
    
    ¿No ve su opción inmediatamente? Primero seleccione **Mostrar todo**. 

2. Siga las instrucciones del asistente.
    
    Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](labels.md#retention-label-policies-and-locations). 

Para editar una directiva de etiqueta de retención existente, selecciónela y después seleccione **Editar directiva** para iniciar el mismo asistente que le permite cambiar la descripción de la directiva y las [configuraciones elegibles](#updating-retention-labels-and-their-policies) del paso 2. Como alternativa, seleccione cualquiera de las opciones disponibles de **Editar** para ir directamente a la página correspondiente y actualizar.

## <a name="auto-apply-a-retention-label"></a>Aplicar automáticamente una etiqueta de retención

Aplica automáticamente una etiqueta de retención, basada en las condiciones que especifiques.

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:
    
    - Si utiliza la administración de registros:**Gobierno de información**:
        - **Soluciones** > **Administración de registros ** > pestaña**Directivas de etiquetas **>** Aplicar automáticamente etiquetas**
    
    - Si no está utilizando la administración de registros:
        - **Soluciones** > **Gobierno de información** > pestaña**Directivas de etiquetas** > **Aplicar automáticamente etiquetas**
    
    ¿No ve su opción inmediatamente? Primero seleccione **Mostrar todo**. 

2. Siga las instrucciones del asistente.
    
    Para obtener información sobre la configuración de las condiciones que aplican automáticamente la etiqueta de retención, consulte la sección [Configuración de las condiciones para la aplicación automática de etiquetas de retención en](#configuring-conditions-for-auto-apply-retention-labels) esta página.
    
    Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](labels.md#retention-label-policies-and-locations).

Para editar una directiva de etiqueta de aplicación automática existente, selecciónela y después seleccione **Editar directiva** para iniciar el mismo asistente que le permite cambiar la descripción de la directiva y las [configuraciones elegibles](#updating-retention-labels-and-their-policies) del paso 2. Como alternativa, seleccione cualquiera de las opciones disponibles de **Editar** para ir directamente a la página correspondiente y actualizar.


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Configurar las condiciones para la aplicación automática de etiquetas de retención

Puede aplicar etiquetas de retención al contenido automáticamente cuando éste contiene:
  
- [Tipos específicos de información confidencial](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [Palabras clave específicas que coinciden con una consulta que haya creado](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Una coincidencia para clasificadores que se pueden entrenar](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Página de selección de condición para una etiqueta de aplicación automática](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

Las etiquetas de retención aplicadas automáticamente puede tardar hasta siete días en aplicarse a todo el contenido que coincida con las condiciones que ha configurado.

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Aplicar automáticamente etiquetas a los contenidos con tipos específicos de información sensible

Al crear etiquetas de retención de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que cuando se crea una directiva de prevención de pérdida de datos (DLP). Cada plantilla de directiva está preconfigurada para buscar determinados tipos de información confidencial. Por ejemplo, la plantilla que se muestra aquí busca números de ITIN, SSN y pasaporte de Estados Unidos. Para obtener más información sobre DLP, vea [Información general sobre directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
![Plantillas de directiva con tipos de información confidencial](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
Después de seleccionar una plantilla de directiva, puede agregar o quitar los tipos de información confidencial, así como cambiar el recuento de instancias y la precisión de coincidencia. En el ejemplo que se muestra aquí, solo se aplicará automáticamente una etiqueta de retención cuando:
  
- El contenido tenga entre 1 y 9 instancias de alguno de estos tres tipos de información confidencial. Puede eliminar el valor **máximo** para que cambie a **cualquiera**.
    
- El tipo de información confidencial detectado tiene una precisión de coincidencia (o nivel de confianza) mínima de 75. Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una precisión de coincidencia más alta necesita encontrar más evidencias (como palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior necesita menos evidencias. En resumen, cuanto menor sea la precisión de coincidencia **mínima**, más fácil será que el contenido coincida con la condición. 
    
Para obtener más información acerca de estas opciones, vea [Ajustar reglas para que sea más o menos fáciles que coincidan](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).
    
![Opciones para identificar tipos de información confidencial](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Aplicar automáticamente etiquetas a contenido con palabras clave o propiedades que se puedan buscar

Puede aplicar automáticamente etiquetas a contenido que cumpla determinadas condiciones. Las condiciones disponibles ahora permiten aplicar una etiqueta a contenido que coincida con palabras, frases o propiedades que puedan buscarse. Puede restringir la consulta con operadores de búsqueda como Y, O y NO.

Para obtener más información sobre la sintaxis de consultas, vea:

- [Referencia de la sintaxis del lenguaje de consultas de palabras clave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

Las etiquetas basadas en consultas usan el índice de búsqueda para identificar el contenido. Para obtener más información sobre las propiedades de búsqueda válidas, vea:

- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
- [Información general sobre las propiedades administradas y rastreadas en SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

Consultas de ejemplos:

- Exchange
    - asunto:"Finanzas trimestrales"
    - destinatarios: jorgem<!--nolink-->@contoso.com
- SharePoint y OneDrive
    - contenttype:contract
    - sitio:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![Editor de consultas](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Aplicar automáticamente etiquetas al contenido con clasificadores que se pueden entrenar

Si elige la opción para un clasificador que se puede entrenar, puede seleccionar uno de los clasificadores integrado o un clasificador personalizado. Los clasificadores integrados incluyen **Currículum**, **Código fuente**, **Código fuente**, **Acoso selectivo**, **Amenazas**:

![Elegir clasificador que se puede entrenar](../media/retention-label-classifers.png)

Para aplicar una etiqueta automáticamente usando esta opción, los buzones y sitios de SharePoint Online deben tener al menos 10 MB de datos.

Para obtener más información sobre los clasificadores que se pueden entrenar, consulte [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md).

Para obtener un ejemplo de configuración, consulte [cómo preparar y usar un clasificador integrado](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Tiempo que tardan las etiquetas de retención en aplicarse

Al publicar o aplicar automáticamente etiquetas de retención, no surten efecto inmediatamente:
  
1. Primero, la directiva de etiquetas tiene que sincronizarse desde el centro de administración con las ubicaciones en la directiva.
    
2. Entonces la ubicación podría requerir tiempo para poner a disposición de los usuarios finales las etiquetas de retención publicadas o tiempo para aplicar automáticamente las etiquetas al contenido. El tiempo que se tarda depende de la ubicación y el tipo de etiqueta de retención.
    
### <a name="published-retention-labels"></a>Etiquetas de retención publicadas

Si publica etiquetas de retención en SharePoint o OneDrive, puede que tarden un día en mostrarse a los usuarios finales. Además, si publica etiquetas de retención en Exchange, pueden tardar hasta siete días en mostrarse a los usuarios finales y, además, el buzón necesita contener como mínimo 10 MB de datos.
  
![Diagrama de cuándo entran en vigor las etiquetas manuales](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>Aplicar automáticamente etiquetas de retención

Si aplica automáticamente etiquetas de retención a contenido que coincida con condiciones específicas, estas pueden tardar hasta siete días en aplicarse a todo el contenido existente que coincida con las condiciones.
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Cómo comprobar el estado de las etiquetas de retención publicadas en Exchange

En Exchange Online, las etiquetas de retención están disponibles para los usuarios finales mediante un proceso que se ejecuta cada siete días. Mediante el uso de Powershell, se puede ver cuándo se ejecutó este proceso por última vez y así identificar cuándo se volverá a ejecutar.
  
1. [Conéctese al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. Ejecute estos comandos.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

En los resultados, la propiedad `ELCLastSuccessTimeStamp` (UTC) muestra cuándo fue la última vez que el sistema procesó el buzón. Si esto no ha ocurrido desde el momento en que se creó la directiva, las etiquetas no van a aparecer. Para forzar el procesamiento, ejecute `Start-ManagedFolderAssistant -Identity <user>`.
    
Si las etiquetas no aparecen en Outlook en la Web y cree que tendrían que aparecer, asegúrese de vaciar la caché del explorador (CTRL+F5).
    

## <a name="updating-retention-labels-and-their-policies"></a>Actualización de las etiquetas de retención y sus directivas

Cuando edita una etiqueta de retención, una directiva de etiquetas de retención o una directiva de aplicación automática y la etiqueta de retención o directiva ya se aplica al contenido, la configuración actualizada se aplicará automáticamente a este contenido además del contenido recién identificado.

Después de crear y guardar la etiqueta o la directiva, no se pueden cambiar algunas opciones de configuración, entre las que se incluyen:
- La configuración de retención excepto el período de retención, a menos que haya configurado la etiqueta para conservar o eliminar el contenido en función de cuándo se creó.
- La opción para clasificar como un registro.

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a>Encuentra los cmdlets de PowerShell para las etiquetas de retención

Para usar la etiqueta de retención cmdlets:
  
1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use estos cmdlets del Centro de seguridad y cumplimiento de Office 365:
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
