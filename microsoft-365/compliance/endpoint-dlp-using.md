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
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Aprenda cómo configurar las directivas de prevención de pérdida de datos (DLP) para usar las ubicaciones de la Prevención de pérdida de datos de punto de conexión.
ms.openlocfilehash: 9107759e137d7b8dd86253f9c6567b76686d2518
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632385"
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

## <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Escenario 1: crear una directiva a partir de una plantilla, solo auditoría

Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades. Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).

1. Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija **Crear directiva**.

3. Para este escenario, elija **Privacidad**, después **Datos de información de identificación personal (PII) de Estados Unidos**, y elija **Siguiente**.

4. Desactive el campo **Estado** para todas las ubicaciones, excepto para **Dispositivos**. A continuación, elija **Siguiente**.

5. Acepte la selección predeterminada **Revisar y personalizar la configuración a partir de la plantilla** y elija **Siguiente**.

6. Acepte los valores predeterminados **Acciones de protección** y elija **Siguiente**.

7. Seleccione **Auditar o restringir actividades en dispositivos Windows** y deje las acciones configuradas en **Solo auditar**. A continuación, elija **Siguiente**.

8. Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**. A continuación, elija **Siguiente**.

9. Revise la configuración y elija **Enviar**.

10. La nueva directiva DLP se mostrará en la lista de directivas.

11. Compruebe el Explorador de actividades para obtener los datos de los puntos de conexión supervisados. Configure el filtro por ubicación para los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver su impacto. Consulte [Introducción al Explorador de actividades](data-classification-activity-explorer.md), de ser necesario.

12. Intente compartir una prueba que incluya contenido que desencadene la condición de datos de información de identificación personal (DCP) de EE. UU. con alguien ajeno a su organización. Esto debería desencadenar la directiva.

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

9. Intente compartir una prueba que incluya contenido que desencadene la condición de datos de información de identificación personal (DCP) de EE. UU. con alguien ajeno a su organización. Esto debería desencadenar la directiva.

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

9. Intente compartir una prueba que incluya contenido que desencadene la condición de datos de información de identificación personal (DCP) de EE. UU. con alguien ajeno a su organización. Esto debería desencadenar la directiva.

   Verá un elemento emergente como el siguiente en el dispositivo cliente:

   > [!div class="mx-imgBorder"]
   > ![notificación de invalidación de cliente bloqueado por dlp en punto de conexión.](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>Escenario 4: evitar el bucle de notificaciones de la DLP en las aplicaciones con sincronización en la nube con cuarentena automática (vista previa)

### <a name="before-you-begin"></a>Antes de empezar

En este escenario, se bloquea la sincronización de archivos con la etiqueta de confidencialidad **Extremadamente confidencial** para OneDrive. Se trata de un escenario complejo con varios componentes y procedimientos. Necesitará:

- Una cuenta de usuario de AAD de destino y un equipo Windows 10 incorporado que ya esté sincronizando una carpeta local de OneDrive con el almacenamiento en la nube de OneDrive.
- Microsoft Word instalado en el equipo Windows 10 de destino
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

7. Escriba la ruta de acceso a la carpeta de los equipos locales a las que quiere mover los archivos confidenciales originales. Por ejemplo:
   
    **'%homedrive%%homepath%\Microsoft DLP\Quarantine'** para el nombre de usuario *Isaiah Langer* colocará los elementos movidos en una carpeta llmada:  

    *C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive*

    y anexará una marca de fecha y hora al nombre de archivo original.
    
    > [!NOTE]
    > La cuarentena automática de la DLP creará subcarpetas para los archivos de cada aplicación no permitida. Por lo tanto, si tiene tanto el *Bloc de notas* como *OneDrive* en la lista de aplicaciones no permitidas, se creará una subcarpeta para **\OneDrive** y otra subcarpeta para **\Bloc de notas**.

8. Elija **Reemplazar los archivos por un archivo .txt que contenga el siguiente de texto** y escriba el texto que desee en el archivo de marcador de posición. Por ejemplo, para un archivo denominado *cuarentena automática 1.docx*:
    
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

9. Elija **Activar inmediatamente**. Elija **siguiente**.

10. Revise la configuración y elija **Enviar**.

    > [!NOTE]
    > Espere al menos una hora para que la nueva directiva se replique y se aplique al equipo de Windows 10 de destino.

11. La nueva directiva DLP se mostrará en la lista de directivas.

### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Probar la cuarentena automática en el dispositivo Windows 10

1. Inicie sesión en el equipo Windows 10 con la cuenta de usuario que especificó en [Configure una directiva para bloquear la sincronización de archivos de OneDrive con la etiqueta de confidencialidad Extremadamente confidencial](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential) paso 5.

2. Cree una carpeta con un contenido que no se sincronizará en OneDrive. Por ejemplo:

    *carpeta de origen C:\auto-cuarentena*

3. Abra Microsoft Word y cree un archivo en la carpeta de origen de cuarentena automática. Aplique la etiqueta de confidencialidad **Extremadamente confidencial**; vea [Aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

4. Copie el archivo que acaba de crear en la carpeta de sincronización de OneDrive. Debe aparecer una notificación del sistema para el usuario que indica que la acción no está permitida y que el archivo se pondrá en cuarentena. Por ejemplo, para el nombre de usuario *Isaiah Langer* y un documento titulado *doc auto-cuarentena 1.docx* vería este mensaje:

    ![Ventana emergente de notificación de prevención de pérdida de datos para el usuario que indica que la acción de sincronización de OneDrive no está permitida para el archivo especificado y que el archivo se pondrá en cuarentena.](../media/auto-quarantine-user-notification-toast.png)
    
    El mensaje indica:
    
    > No se permite abrir el documento 1.docx con esta aplicación. El archivo se pondrá en cuarentena en "C:\Users\IsaiahLanger\Microsoft DLP\OneDrive".

5. Elija **Descartar**.

6. Abra el archivo de texto del marcador de posición. Se denominará **doc auto-cuarentena 1.docx_ *fecha_hora*.txt**. 

7. Abra la carpeta de cuarentena y confirme que el archivo original está allí.
 
8. Compruebe el Explorador de actividades para obtener los datos de los puntos de conexión supervisados. Configure el filtro por ubicación para los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver su impacto. Consulte [Introducción al Explorador de actividades](data-classification-activity-explorer.md), de ser necesario.

9. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="scenario-5-restrict-unintentional-sharing-to-unallowed-cloud-apps-and-services"></a>Escenario 5: Restringir el uso compartido accidental a servicios y aplicaciones en la nube no permitidos

Con DLP de puntos de conexión y el Explorador web Edge, puede restringir el uso compartido accidental de elementos confidenciales a las aplicaciones y servicios en la nube no permitidos. Edge sabe si un elemento está restringido por una directiva DLP de puntos de conexión y aplica las restricciones de acceso.

Al seleccionar **Dispositivos** como ubicación en una directiva DLP configurada correctamente y usar el explorador Microsoft Edge, los exploradores no permitidos que haya definido en esta configuración no podrán acceder a los elementos confidenciales que coincidan con los controles de directiva DLP. En su lugar, se redirigirá a los usuarios para que usen Microsoft Edge que, con su comprensión de las restricciones impuestas por DLP, puede bloquear o restringir las actividades cuando se cumplan las condiciones de la directiva DLP.

Para usar esta restricción, tendrá que configurar tres partes importantes:

1. Especifique los sitios (servicios, dominios y direcciones IP) con los que no quiere que se compartan elementos confidenciales.

2. Agregue los exploradores que no tienen permitido acceder a ciertos elementos confidenciales cuando se produzca una coincidencia de directiva DLP.

3. Configure directivas DLP para definir los tipos de elementos confidenciales que deberían tener carga restringida a estos lugares activando **Cargar a los servicios en la nube** y **Acceso desde un explorador no permitido**.

Puede continuar agregando nuevos servicios, aplicaciones y directivas para ampliar y aumentar las restricciones para satisfacer las necesidades de su empresa y proteger los datos confidenciales. 

Esta configuración garantizará que sus datos estén seguros, evitando así las restricciones innecesarias que impiden o restringen a los usuarios el acceso y el uso compartido de elementos no confidenciales.
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
