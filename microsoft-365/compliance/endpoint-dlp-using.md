---
title: Uso de DLP de punto de conexión
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- highpri
- purview-compliance
- SPO_Content
search.appverid:
- MET150
description: Aprenda cómo configurar las directivas de prevención de pérdida de datos (DLP) para usar las ubicaciones de la Prevención de pérdida de datos de punto de conexión.
ms.openlocfilehash: f8e74219a796b46f681caceefdb532e1678f0a74
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537014"
---
# <a name="using-endpoint-data-loss-prevention"></a>Uso de la prevención de pérdida de datos en punto de conexión

Para ayudarle a familiarizarse con las características de DLP de los puntos de conexión y cómo se muestran en las directivas DLP, hemos recopilado algunos escenarios para que los siga.

> [!IMPORTANT]
> Estos escenarios DLP de los puntos de conexión no son los procedimientos oficiales para crear y optimizar directivas DLP. Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:
>
>- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
>- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
>- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
>- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)


[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Para obtener información completa sobre licencias, vea [Guía de licencias para la protección de la información de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

## <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Escenario 1: crear una directiva a partir de una plantilla, solo auditoría

Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades. Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).

1. Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija **Crear directiva**.

3. Para este escenario, elija **Privacidad**, después **Datos de información de identificación personal (PII) de Estados Unidos**, y elija **Siguiente**.

4. Toggle the **Status** field to off for all locations except **Devices**. Choose **Next**.

5. Acepte la selección predeterminada **Revisar y personalizar la configuración a partir de la plantilla** y elija **Siguiente**.

6. Acepte los valores predeterminados **Acciones de protección** y elija **Siguiente**.

7. Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**. Choose **Next**.

8. Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**. Choose **Next**.

9. Revise la configuración y elija **Enviar**.

10. La nueva directiva DLP se mostrará en la lista de directivas.

11. Check Activity explorer for data from the monitored endpoints. Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy; see [Get started with activity explorer](data-classification-activity-explorer.md), if needed.

12. Attempt to share a test item that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.

13. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>Escenario 2: modificar la directiva existente, configurar una alerta

1. Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.

3. Elija **editar directiva**.

4. Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.

5. Desplácese hacia abajo hasta la sección **Informes de incidentes** y configure **Enviar una alerta a los administradores cuando se produzca una coincidencia de regla** en **Activado**. Las alertas por correo electrónico se enviarán automáticamente al administrador y a cualquier persona que agregue a la lista de destinatarios. 

![activar-informes-de-incidentes](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. Para este escenario, elija **Enviar una alerta cada vez que una actividad coincida con la regla**.

7. Seleccione **Guardar**.

8. Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.

9. Attempt to share a test item that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.

10. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>Caso 3: modificar la directiva existente, bloquear la acción con permitir invalidación

1. Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.

3. Elija **editar directiva**.

4. Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.

5. Desplácese hacia abajo hasta la sección **Auditar o restringir actividades en dispositivos Windows** y configure la acción correspondiente en **Bloquear con invalidación** para cada actividad.

   > [!div class="mx-imgBorder"]
   > ![configurar bloqueo con acción de invalidación.](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. Seleccione **Guardar**.

7. Repita los pasos del 4 al 7 para el **Alto volumen de contenido detectado en la información de identificación personal de Estados Unidos**.

8. Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.

9. Attempt to share a test item that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.

   Verá un elemento emergente como el siguiente en el dispositivo cliente:

   > [!div class="mx-imgBorder"]
   > ![notificación de invalidación de cliente bloqueado por dlp en punto de conexión.](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>Escenario 4: evitar el bucle de notificaciones de la DLP en las aplicaciones con sincronización en la nube con cuarentena automática (vista previa)

## <a name="before-you-begin-scenario-4"></a>Antes de comenzar el escenario 4

En este escenario, se bloquea la sincronización de archivos con la etiqueta de confidencialidad **Extremadamente confidencial** para OneDrive. Se trata de un escenario complejo con varios componentes y procedimientos. Necesitará:

- Una cuenta de usuario de AAD de destino y un equipo Windows 10 incorporado que ya esté sincronizando una carpeta local de OneDrive con el almacenamiento en la nube de OneDrive.
- Etiquetas de confidencialidad configuradas y publicadas. Vea [Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels) y [Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies).

Hay tres pasos:

1. Configure las opciones de cuarentena automática de la DLP del punto de conexión.
2. Cree una directiva que bloquee los elementos confidenciales que tengan la etiqueta de confidencialidad **Extremadamente confidencial**.
3. Cree un documento de Word en el dispositivo Windows 10 al que se destina la directiva, aplique la etiqueta y cópiela en la carpeta local de OneDrive de las cuentas de usuario que se está sincronizando.  

### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>Configure las aplicaciones no permitidas y la configuración de cuarentena automática de la DLP.

1. Abra la [configuración del punto de conexión de la DLP](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings)

2. Expanda las **Aplicaciones no permitidas**.

3. Elija **Agregar o editar aplicaciones no permitidas** y agregue *OneDrive* como nombre para mostrar y el nombre ejecutable *onedrive.exe*  para impedir que onedrive.exe acceda a los elementos con la etiqueta **Extremadamente confidencial**.

4. Seleccione **cuarentena automática** y **Guardar**.

5. En **Configuración de la cuarentena automática** elija **Editar la configuración de la cuarentena automática**.

6. Habilite **Cuarentena automática para las aplicaciones no permitidas**.

7. Enter the path to the folder on local machines where you want the original sensitive files to be moved to. For example:
   
    **'%homedrive%%homepath%\Microsoft DLP\Quarantine'** para el nombre de usuario *Isaiah Langer* colocará los elementos movidos en una carpeta llmada:  

    *C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive*

    y anexará una marca de fecha y hora al nombre de archivo original.
    
    > [!NOTE]
    > La cuarentena automática de la DLP creará subcarpetas para los archivos de cada aplicación no permitida. Por lo tanto, si tiene tanto el *Bloc de notas* como *OneDrive* en la lista de aplicaciones no permitidas, se creará una subcarpeta para **\OneDrive** y otra subcarpeta para **\Bloc de notas**.

8. Choose **Replace the files with a .txt file that contains the following text** and enter the text you want in the placeholder file. For example for a file named *auto quar 1.docx*:
    
    > %%FileName%% contiene información confidencial que su empresa está protegiendo con la directiva de prevención de pérdida de datos (DLP) %%PolicyName%% y se ha movido a la carpeta en cuarentena: %%QuarantinePath%%.
    
    dejará un archivo de texto que contiene este mensaje:
    
    > cuar auto 1.docx contiene información confidencial que su empresa está protegiendo con la directiva de prevención de pérdida de datos (DLP) y se ha movido a la carpeta en cuarentena: C:\Usuarios\IsaiahLanger\Microsoft DLP\Cuarentena\OneDrive\cuar auto 1_20210728_151541.docx.

9. Elija **Guardar**

### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>Configurar una directiva para bloquear la sincronización de archivos de OneDrive con la etiqueta de confidencialidad Extremadamente confidencial

1. Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija **Crear directiva**.

3. En este escenario, elija **Personalizado** y, a continuación, **Directiva personalizada** y elija **Siguiente**.

4. Rellene los campos **Nombre** y **Descripción** y elija **Siguiente**.

5. Desactive el campo **Estado** para todas las ubicaciones excepto para **Dispositivos**. Si tiene una cuenta de usuario final específica desde la que desea hacer una prueba, asegúrese de seleccionarla en el ámbito de búsqueda. Elija **Siguiente**.

6. Acepte la selección **Crear o personalizar reglas DLP avanzadas** que viene predeterminada y elija **Siguiente**.

7. Cree una regla con estos valores:
    1. **Nombre** > *Escenario 4 de cuarentena automática*
    1. **Condiciones** > **El contenido contiene** > **Etiquetas de confidencialidad** > **Extremadamente confidencial**
    1.  **Acciones** > **Auditar o restringir actividades en dispositivos Windows** > **Acceso de aplicaciones no permitidas** > **Bloquear**. Para los fines de este escenario, borre todas las demás actividades.
    1. **Notificaciones del usuario** > **Activadas**
    1. **Dispositivos de punto de conexión** > Elegir **Mostrar a los usuarios una notificación de sugerencia de directiva cuando una actividad** siempre que no esté ya activada.
    
8. Elija **Guardar** y **Siguiente**.

9. Choose **Turn it on right away**. Choose **Next**.

10. Revise la configuración y elija **Enviar**.

    > [!NOTE]
    > Espere al menos una hora para que la nueva directiva se replique y se aplique al equipo de Windows 10 de destino.

11. La nueva directiva DLP se mostrará en la lista de directivas.

### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Probar la cuarentena automática en el dispositivo Windows 10

1. Inicie sesión en el equipo Windows 10 con la cuenta de usuario que especificó en [Configure una directiva para bloquear la sincronización de archivos de OneDrive con la etiqueta de confidencialidad Extremadamente confidencial](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential) paso 5.

2. Create a folder whose contents will not be synchronized to OneDrive. For example:

    *carpeta de origen C:\auto-cuarentena*

3. Abra Microsoft Word y cree un archivo en la carpeta de origen de cuarentena automática. Aplique la etiqueta de confidencialidad **Extremadamente confidencial**; vea [Aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

4. Copie el archivo que acaba de crear en la carpeta de sincronización de OneDrive. Debe aparecer una notificación del sistema para el usuario que indica que la acción no está permitida y que el archivo se pondrá en cuarentena. Por ejemplo, para el nombre de usuario *Isaiah Langer* y un documento titulado *doc auto-cuarentena 1.docx* vería este mensaje:

    ![Ventana emergente de notificación de prevención de pérdida de datos para el usuario que indica que la acción de sincronización de OneDrive no está permitida para el archivo especificado y que el archivo se pondrá en cuarentena.](../media/auto-quarantine-user-notification-toast.png)
    
    El mensaje indica:
    
    > No se permite abrir el documento 1.docx con esta aplicación. El archivo se pondrá en cuarentena en "C:\Users\IsaiahLanger\Microsoft DLP\OneDrive".

5. Elija **Descartar**.

6. Abra el archivo de texto del marcador de posición. Se denominará **doc auto-cuarentena 1.docx_ *fecha_hora*.txt**. 

7. Abra la carpeta de cuarentena y confirme que el archivo original está allí.
 
8. Check Activity explorer for data from the monitored endpoints. Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy; see [Get started with activity explorer](data-classification-activity-explorer.md), if needed.

9. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-5-restrict-unintentional-sharing-to-unallowed-cloud-apps-and-services"></a>Escenario 5: Restringir el uso compartido accidental a servicios y aplicaciones en la nube no permitidos

Con DLP de punto de conexión y explorador web de Microsoft Edge, puede restringir el uso compartido involuntario de elementos confidenciales a servicios y aplicaciones en la nube no permitidos. Edge sabe si un elemento está restringido por una directiva DLP de puntos de conexión y aplica las restricciones de acceso.

Al seleccionar **Dispositivos** como ubicación en una directiva DLP configurada correctamente y usar el explorador Microsoft Edge, los exploradores no permitidos que haya definido en esta configuración no podrán acceder a los elementos confidenciales que coincidan con los controles de directiva DLP. En su lugar, se redirigirá a los usuarios para que usen Microsoft Edge que, con su comprensión de las restricciones impuestas por DLP, puede bloquear o restringir las actividades cuando se cumplan las condiciones de la directiva DLP.

Para usar esta restricción, tendrá que configurar tres partes importantes:

1. Especifique los sitios (servicios, dominios y direcciones IP) con los que no quiere que se compartan elementos confidenciales.

2. Agregue los exploradores que no tienen permitido acceder a ciertos elementos confidenciales cuando se produzca una coincidencia de directiva DLP.

3. Configure directivas DLP para definir los tipos de elementos confidenciales que deberían tener carga restringida a estos lugares activando **Cargar a los servicios en la nube** y **Acceso desde un explorador no permitido**.

Puede continuar agregando nuevos servicios, aplicaciones y directivas para ampliar y aumentar las restricciones para satisfacer las necesidades de su empresa y proteger los datos confidenciales. 

Esta configuración garantizará que sus datos estén seguros, evitando así las restricciones innecesarias que impiden o restringen a los usuarios el acceso y el uso compartido de elementos no confidenciales.

## <a name="scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains"></a>Escenario 6 Supervisar o restringir las actividades del usuario en dominios de servicio confidenciales

Use este escenario cuando quiera auditar, bloquear con invalidación o bloquear estas actividades de usuario en un sitio web.

- imprimir desde un sitio web
- copiar datos de un sitio web
- guardar un sitio web como archivos locales

El usuario debe estar accediendo al sitio web a través de Microsoft Edge.

### <a name="supported-syntax-for-designating-websites-in-a-website-group"></a>Sintaxis admitida para designar sitios web en un grupo de sitios web

Puede usar una sintaxis flexible para incluir y excluir dominios, subdominios, sitios web y subsitios en los grupos de sitios web.

- use `*` como carácter comodín para especificar todos los dominios o todos los subdominios.
- use `/` como terminador al final de una dirección URL para limitar únicamente a ese sitio específico.

Cuando agrega una dirección URL sin un `/` final, esa dirección URL se limita a ese sitio y a todos los subsitios.

Esta sintaxis se aplica a todos los sitios web http/https.

Estos son algunos ejemplos:


|Dirección URL que se agrega al grupo de sitios web  |La dirección URL coincidirá  | La dirección URL no coincidirá|
|---------|---------|---------|
|contoso.com  | //<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/ </br> //<!--nourl-->contoso.com/todoslossubsitios1 </br> //<!--nourl-->contoso.com/todoslossubsitios1/todoslossubsitios2|        //<!--nourl-->todoslossubdominios.contoso.com </br> //<!--nourl-->todoslossubdominios.contoso.com.au    |
|contoso.com/     |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/         |//<!--nourl-->contoso.com/todoslossubsitios1 </br> //<!--nourl-->contoso.com/todoslossubsitios1/todoslossubsitios2 </br> //<!--nourl-->todoslossubdominios.contoso.com </br> //<!--nourl-->todoslossubdominios.contoso.com/au   |
|*.contoso.com   | //<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/todoslossubsitios </br> //<!--nourl-->contoso.com/todoslossubsitios1/todoslossubsitios2 </br> //<!--nourl-->todoslossubdominios.contoso.com </br> //<!--nourl-->todoslossubdominios.contoso.com/todoslossubsitios </br> //<!--nourl-->todoslossubdominios1/todoslossubdominios2/contoso.com/todoslossubsitios1/todoslossubsitios2         | //<!--nourl-->todoslossubdominios.contoso.com.au|
|*.contoso.com/xyz     |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/xyz </br> //<!--nourl-->contoso.con/xyz/todoslossubsitios/ </br> //<!--nourl-->todoslossubdominios.contoso.com/xyz </br> //<!--nourl-->todoslossubdominios.contoso.com/xyz/todoslossubsitios </br> //<!--nourl-->todoslossubdominios1.todoslossubdominios2.contoso.com/xyz/todoslossubsitios </br> //<!--nourl-->todoslossubdominios1.todoslossubdominios2.contoso.com/xyz/todoslossubsitios1/todoslossubsitios2         | //<!--nourl-->contoso.com/xyz </br> //<!--nourl-->todoslossubdominios.contoso.com/xyz/|
|*.contoso.com/xyz/     |//<!--nourl-->contoso.com/xyz </br> //<!--nourl-->todoslossubdominios.contoso.com/xyz         |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/xyz/todoslossubsitios/ </br> //<!--nourl-->todoslossubdominios.contoso.com/xyz/todoslossubsitios/ </br> //<!--nourl-->todoslossubdominios1.todoslossubdominios2.contoso.com/xyz/todoslossubsitios/ </br> //<!--nourl-->todoslossubdominios1.todoslossubdominios2.contoso.com/xyz/todoslossubsitios1/todoslossubsitios2|


### <a name="configure-sensitive-service-domains"></a>Configurar dominios de servicio confidencial

1. En el portal de cumplimiento de Microsoft Purview, abra **Prevención de pérdida de datos** > **Configuración DLP de punto de conexión** > **Restricciones de dominio y explorador para datos confidenciales** > **Dominios de servicio confidencial**.
1. Seleccione **Agregar un nuevo grupo de dominios de servicio confidencial**.
1. Asigne un nombre al grupo.
1. Seleccione el **Tipo de coincidencia** que quiera. Puede seleccionar entre **URL**, **Dirección IP**, **Intervalo de direcciones IP**.
1. Escriba el valor adecuado en **Agregar nuevos dominios de servicio a este grupo**. Puede agregar varios sitios web a un grupo y usar caracteres comodín para cubrir subdominios.  Por ejemplo, `www.contoso.com` solo para el sitio web de nivel superior o \*.contoso.com para corp.contoso.com, hr.contoso.com, fin.contoso.com
1. Haga clic en **Guardar**.
1. Seleccione **Directivas**.
1. Cree y defina el ámbito de una directiva que solo se aplica a **Dispositivos**. Vea, [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para más información sobre cómo crear una directiva.
1. Cree una regla que use el **acceso del usuario a un sitio confidencial desde Edge** y la acción **Auditar o restringir las actividades en los dispositivos**.
1. En **Service domain and browser activities (Actividades de dominio y explorador** de servicio), seleccione **Upload to a restricted cloud service domain or access from an unllowed browser (Cargar en un dominio de servicio en la nube restringido o acceso desde un explorador no permitido** ) y establezca la acción **en Solo auditoría**. Esto establece la acción general para todos los grupos de sitios.
1. Seleccione los **Grupos de sitios confidenciales** que quiera.
1. Seleccione **Agregar**.
1. OPCIONAL: si desea crear una excepción (normalmente una lista de permitidos) en la acción general para uno o varios grupos de sitios, seleccione **Configurar excepciones de dominio de servicio confidencial**, agregue el grupo de sitios para el que desea la excepción, configure la acción deseada y **Guarde** la configuración.
1. Seleccione las actividades de usuario que quiera supervisar o restringir y las acciones que DLP realizará en respuesta a esas actividades.
1. Termine de configurar la regla y la directiva y aplíquela.

## <a name="scenario-7-authorization-groups-preview"></a>Escenarios 7 Grupos de autorización (versión preliminar)

> [!IMPORTANT]
> Para poder usar **grupos de impresoras**, **grupos de dispositivos de almacenamiento extraíbles**, **grupos de recursos compartidos de red** y **excepciones de red o VPN** , debe registrarse [aquí](https://forms.office.com/r/GNVTFvxuZv).

Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades. Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).

Los grupos de autorización se usan principalmente como listas de permitidos. Ha asignado acciones de directiva al grupo que son diferentes de las acciones de directiva global. En este escenario, pasaremos por definir un grupo de impresoras y, a continuación, configurar una directiva con acciones de bloque para todas las actividades de impresión excepto para las impresoras del grupo. Estos procedimientos son básicamente los mismos para los **grupos de dispositivos de almacenamiento extraíbles** y los **grupos de recursos compartidos de red**.

En este escenario, definiremos un grupo de impresoras que el departamento legal usa para los contratos de impresión. Se bloquean los contratos de impresión en cualquier otra impresora.

### <a name="create-and-use-printer-groups"></a>Creación y uso de grupos de impresoras

1. En el portal de cumplimiento Microsoft Purview abra Configuración **dlp de punto de conexión de** **prevención** >  de pérdida de  >  datos Grupos **de impresoras**.
1. Seleccione **Crear grupo de impresoras** y asigne un nombre al grupo. En este escenario, usaremos `Legal printers`.
1. Seleccione **Agregar impresora** y proporcione un nombre. Puede definir impresoras mediante:
    1. Nombre descriptivo de la impresora 
    1. Id. de producto USB
    1. Identificador de proveedor USB
    1. Intervalo IP
    1. Imprimir en el archivo
    1. Impresión universal implementada en una impresora
    1. Impresora corporativa
    1. Imprimir en local
1. Seleccione **Cerrar**.

### <a name="configure-policy-printing-actions"></a>Configuración de acciones de impresión de directivas

1. Abra la pestaña **Directivas** .

1. Seleccione **Crear directiva** y seleccione la plantilla de directiva personalizada.
1. Establezca el ámbito de la ubicación solo en **Dispositivos**.

1. Cree una regla en la que:
    1. **El contenido contiene** =  **Clasificadores entrenables**, **Asuntos Jurídicos**
    1. **Acciones** =  **Auditoría o restricción de actividades en dispositivos**
    1. A continuación, elija **Actividades de archivo en todas las aplicaciones**.
    1. Seleccione **Aplicar restricciones a una actividad específica**.
    1. Seleccionar **bloque de impresión** = 
1. Seleccione **Elegir restricciones de impresión diferentes**
1. En **Restricciones del grupo de impresoras**, seleccione **Agregar grupo** y seleccione **Impresoras legales**.
1. Establezca **Action** Allow (Permitir acción = **).**
    > [!TIP]
    > El evento **Allow** action wil record and audit en el registro de auditoría, pero no genera una alerta o notificación. 
10. Guardar.
11. Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**. Elija **Siguiente**.

12. Revise la configuración y elija **Enviar**.

13. La nueva directiva DLP se mostrará en la lista de directivas.

## <a name="scenario-8-network-exceptions-preview"></a>Escenario 8 Excepciones de red (versión preliminar)

> [!IMPORTANT]
> Para poder usar **grupos de impresoras**, **grupos de dispositivos de almacenamiento extraíbles**, **grupos de recursos compartidos de red** y **excepciones de red o VPN** , debe registrarse [aquí](https://forms.office.com/r/GNVTFvxuZv).

Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades. Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).

En este escenario, definiremos una lista de VPN que usan los trabajadores híbridos para acceder a los recursos de la organización.

### <a name="create-and-use-a-network-exception"></a>Creación y uso de una excepción de red

Las excepciones de red le permiten configurar las acciones Permitir, Solo auditoría, Bloquear con invalidación y Bloquear en las actividades de archivo basadas en la red desde la que los usuarios acceden al archivo. Puede seleccionar en la lista [configuración de VPN](dlp-configure-endpoint-settings.md#vpn-settings-preview) que definió y en **la opción Red corporativa** . Las acciones se pueden aplicar individual o colectivamente a estas actividades de usuario:

- Copiar en el portapapeles
- Copia en un dispositivo extraíble USB
- Copiar en un recurso compartido de red
- Imprimir
- Copiar o mover mediante una aplicación Bluetooth no permitida
- Copia o movimiento mediante RDP

#### <a name="get-the-server-address-or-network-address"></a>Obtener la dirección del servidor o la dirección de red

1. En un dispositivo Windows supervisado por DLP, abra una ventana **de Windows PowerShell** como administrador.
1. Ejecución de este cmdlet

```powershell-interactive
Get-VpnConnection
```

3. La ejecución de este cmdlet devuelve varios campos y valores.
1. Busque el campo **ServerAddress** y registre ese valor. Lo usará al crear una entrada VPN en la lista de VPN.
1. Busque el campo **Nombre** y registre ese valor. El campo **Nombre** se asigna al campo **Dirección de** red al crear una entrada VPN en la lista VPN.

#### <a name="add-a-vpn"></a>Adición de una VPN

1. Abra [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) >  **Configuración** > **de VPN** de prevención de pérdida de datos **dlp de** >  punto de conexión.
1. Seleccione **Agregar o editar direcciones VPN**.
1. Proporcione la **dirección del servidor** o **la dirección de red** de la ejecución de Get-VpnConnection.
1. Seleccione **Guardar**.
1. Cierre el elemento.

#### <a name="configure-policy-actions"></a>Configuración de acciones de directiva

1. Abra la pestaña **Directivas** .

1. Seleccione **Crear directiva** y seleccione la plantilla de directiva personalizada.
1. Establezca el ámbito de la ubicación solo en **Dispositivos**.

1. Cree una regla en la que:
    1. **El contenido contiene** =  **Clasificadores entrenables**, **Asuntos Jurídicos**
    1. **Acciones** =  **Auditoría o restricción de actividades en dispositivos**
    1. A continuación, elija **Actividades de archivo en todas las aplicaciones**.
    1. Seleccione **Aplicar restricciones a una actividad específica**.
    1. Seleccione las acciones para las que desea configurar **excepciones de red** .
1. Seleccione **Copiar en el Portapapeles** y la acción **Solo auditoría** .
1. Seleccione **Elegir distintas restricciones de copia en el Portapapeles**.
1. Seleccione **VPN** y establezca la acción en **Bloquear con invalidación**.

> [!IMPORTANT]
> Si desea controlar las actividades de un usuario cuando está conectado a través de una VPN *, debe* seleccionar la VPN y convertirla en la prioridad principal en la configuración **Excepciones** de red. De lo contrario, si se selecciona la opción **Red corporativa** , se aplicará esa acción definida para la entrada **de red corporativa** .

> [!CAUTION]
> La opción **Aplicar a todas las actividades** copiará las excepciones de red que se definen aquí y las aplicará a todas las demás actividades específicas configuradas, como **Imprimir** y **Copiar en un recurso compartido de red**. **_Esto sobrescribirá las excepciones de red en las otras actividades La última configuración guardada gana._**  

8. Guardar.
1. Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**. Elija **Siguiente**.

1. Revise la configuración y elija **Enviar**.

1. La nueva directiva DLP se mostrará en la lista de directivas.
 
 
## <a name="see-also"></a>Consulte también

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Introducción a la incorporación de dispositivos Windows 10 y Windows 11 a Microsoft Purview](/microsoft-365/compliance/device-onboarding-overview)
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Unido a Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join)
- [Descargue el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
