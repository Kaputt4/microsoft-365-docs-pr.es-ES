---
title: Uso de la prevención de perdida de datos en punto de conexión
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
description: Aprenda cómo configurar las directivas de prevención de pérdida de datos (DLP) para usar las ubicaciones de la Prevención de pérdida de datos de los puntos de conexión (EPDLP) de Microsoft 365.
ms.openlocfilehash: eb42d43db8edf0bad02e66a5ee4e2853b8d42878
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756030"
---
# <a name="using-endpoint-data-loss-prevention"></a>Uso de la prevención de pérdida de datos en punto de conexión

Este artículo le guiará a través de cuatro escenarios en los que puede crear y modificar una directiva DLP que use dispositivos como una ubicación.

## <a name="dlp-settings"></a>Configuración DLP

Antes de empezar, debe configurar la configuración de DLP. La configuración se aplica a todas las directivas DLP para dispositivos. Debe configurarlas si tiene previsto crear directivas que cumplan con lo siguiente:

- restricciones de salida de la nube
- restricciones de aplicaciones no permitidas

O bien

- Si desea excluir de la supervisión las rutas de archivo ruidosas

  > [!div class="mx-imgBorder"]
  > ![Configuración DLP](../media/endpoint-dlp-1-using-dlp-settings.png).

### <a name="advanced-classification-scanning-and-protection"></a>Escaneo y protección de clasificación avanzada

#### <a name="get-registered"></a>Registrarse

Para obtener acceso a esta característica, debe registrar el espacio empresarial con Microsoft. Vea, [obtener registrado](https://aka.ms/Ignite2021DLP).

Cuando está habilitada, **la protección y el examen de clasificación avanzada** permiten al servicio de clasificación de datos basado en la nube más avanzado de Microsoft 365 examinar elementos, clasificarlos y devolver los resultados a la máquina local. Esto significa que puede aprovechar la clasificación [exacta de coincidencia de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), técnicas de clasificación de entidades [con nombre (versión preliminar)](named-entities-learn.md#learn-about-named-entities-preview) en las directivas DLP.

En la clasificación avanzada, el contenido se envía desde el dispositivo local a los servicios en la nube para su examen y clasificación. Si el uso del ancho de banda es una preocupación, puede establecer un límite en esta configuración global que se aplica por dispositivo en cuanto se puede usar en un período de 24 horas. Si estableces un límite de uso de ancho de banda y se supera, DLP deja de enviar el contenido del usuario a la nube y la clasificación de datos continuará localmente en el dispositivo. Cuando el uso del ancho de banda acumulado se encuentra por debajo del límite de 24 horas, se reanudará la comunicación con los servicios en la nube.

Si el uso del ancho de banda no es un problema, no puede establecer un límite y permitir el uso ilimitado.

> [!NOTE]
> La evaluación de directivas DLP siempre se produce en la nube, incluso si el contenido del usuario no se envía.

### <a name="endpoint-dlp-windows-10-and-macos-settings"></a>Configuración de Windows 10 DLP de punto de conexión y macOS

Para obtener acceso al soporte técnico de macOS, debe registrar el espacio empresarial con Microsoft. Vea, [obtener registrado](https://aka.ms/Ignite2021DLP).

|Setting |Windows 10, 1809 y versiones posteriores  |macOS Catalina 10.15 o posterior (versión preliminar)  |Notas  |
|---------|---------|---------|---------|
|Exclusiones de ruta de archivo     |Compatible         |Compatible         |macOS incluye una lista recomendada de exclusiones que está predeterminada          |
|Aplicaciones no permitidas     |Compatible         |Compatible         |         |
|Aplicaciones de Bluetooth no permitidas    |Compatible         |no compatible         |         |
|Restricciones de explorador y dominio a los elementos confidenciales      |Compatible         |Compatible         |         |
|Configuración adicional para DLP de punto de conexión     |Compatible         |Compatible         |Solo se admiten las justificaciones empresariales predeterminadas para dispositivos macOS         |
|Auditar siempre la actividad de archivos para dispositivos     |Compatible         |Compatible         |         |



### <a name="file-path-exclusions"></a>Exclusiones de ruta de archivo

Abra [Centro de cumplimiento](https://compliance.microsoft.com) > **Prevención de pérdida de datos** > **Configuración de DLP de punto de conexión** > **Exclusiones de ruta de acceso del archivo**.

Es posible que quiera excluir determinadas rutas de supervisión DLP, alertas DLP y aplicación de directivas DLP en sus dispositivos, ya sea porque tienen demasiado ruido o no contienen archivos que le interesan. Los archivos en esas ubicaciones no se auditarán y los archivos que se creen o modifiquen en esas ubicaciones no se someterán a la aplicación de directivas DLP. Puede configurar exclusiones de ruta en configuración DLP.

#### <a name="windows-10-devices"></a>Dispositivos con Windows 10

Puede usar esta lógica para crear sus rutas de exclusión para dispositivos Windows 10:

- Una ruta de archivo es válida cuando termina en "\". Esto incluye solo a los archivos que se encuentran directamente dentro de la carpeta. <br/>Por ejemplo: C:\Temp\

- Una ruta de archivo es válida cuando termina en "\*", que incluye solo a los archivos que se encuentran dentro de las subcarpetas, además de los archivos ubicados directamente dentro de la carpeta. <br/>Por ejemplo: C:\Temp\*

- Una ruta de archivo es válida cuando termina sin "\" o "\*". Esto incluye a todos los archivos que se encuentran directamente dentro de la carpeta o subcarpetas. <br/>Por ejemplo: C:\Temp

- Una ruta con comodín con "\" en cada lado. <br/>Por ejemplo: C:\Usuarios\*\Escritorio\

- Una ruta con comodín con "\" en cada lado y con "(número)" para dar un número exacto de subcarpetas. <br/>Por ejemplo: C:\Usuarios\*(1)\Descargas\

- Una ruta con variables de entorno del SISTEMA. <br/>Por ejemplo: %SystemDrive%\Test\*

- Una combinación de todas las anteriores. <br/>Por ejemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub\

#### <a name="macos-devices-preview"></a>macOS devices (preview)

Al igual que los dispositivos Windows 10, puede agregar sus propias exclusiones para dispositivos macOS.

- Las definiciones de ruta de acceso del archivo no distinguen mayúsculas de minúsculas, por lo que `User` es igual que `user`.

- Admite valores carácter comodín. Por lo tanto, una definición de ruta de acceso puede contener un `*` en medio de la ruta de acceso o al final de la ruta de acceso. Por ejemplo: `/Users/*/Library/Application Support/Microsoft/Teams/*`

#####  <a name="recommended-file-path-exclusions-preview"></a>Exclusiones recomendadas de ruta de acceso del archivo (versión preliminar)

Por motivos de rendimiento, DLP de punto de conexión incluye una lista de exclusiones recomendadas de ruta de acceso del archivo para dispositivos macOS. Estas exclusiones están activadas de manera predeterminada. Puede deshabilitarlas si quiere al alternar la alternancia **Incluir exclusiones recomendadas de ruta de acceso de archivo para Mac**. La lista incluye:

- /Applications/*
- /System/*
- /usr/*
- /Library/*
- /private/*
- /opt/*
- /Users/*/Library/Application Support/Microsoft/Teams/*

### <a name="unallowed-apps"></a>Aplicaciones no permitidas

Las aplicaciones no permitidas son una serie de aplicaciones que crea que no tienen acceso a un archivo protegido por la prevención de pérdida de datos (DLP). Está disponible para dispositivos Windows 10 y macOS (versión preliminar).

Cuando la configuración de **Acceso por parte de aplicaciones y exploradores no permitidos** de una directiva esté activada y una aplicación que esté en esta lista de aplicaciones no permitidas intente acceder a un archivo protegido, la actividad se permitirá, se bloqueará o se bloqueará, y los usuarios podrán invalidar la restricción. Toda actividad es auditada y está disponible para su revisión en el explorador de actividades.

> [!IMPORTANT]
> No incluya la ruta de acceso al archivo ejecutable, solo el nombre del archivo ejecutable (por ejemplo, browser.exe).

#### <a name="macos-devices-preview"></a>macOS devices (preview)

Al igual que los dispositivos Windows, ahora podrá impedir que las aplicaciones de macOS tengan acceso a datos confidenciales definiéndolos en la lista **Aplicaciones no permitidas**. 

> [!NOTE]
> Tenga en cuenta que las aplicaciones entre plataformas deben especificarse con sus rutas de acceso únicas respectivas al sistema operativo en el que se ejecutan.

Para encontrar la ruta de acceso completa de las aplicaciones de Mac:
1. En el dispositivo macOS, abra **Monitor de actividad**. Buscar y hacer doble clic en el proceso que desea restringir

2. Elija la pestaña **Abrir Archivos y Puertos**.
  
3. El nombre de la aplicación se encuentra al final de la ruta de acceso completa.


#### <a name="protect-sensitive-data-from-cloud-synchronization-apps"></a>Protección de datos confidenciales de aplicaciones con sincronización en la nube

Para evitar que las aplicaciones con sincronización en la nube sincronicen elementos confidenciales en la nube, como *onedrive.exe*, agregue la aplicación de sincronización en la nube a la lista **Aplicaciones no permitidas**. Cuando una aplicación con sincronización en la nube no permitida intenta acceder a un elemento protegido por una directiva DLP de bloqueo, la DLP puede generar notificaciones repetidas. Puede evitar estas notificaciones repetidas habilitando la opción **Cuarentena automática** en **Aplicaciones no permitidas**.  

##### <a name="auto-quarantine-preview"></a>Cuarentena automática (vista previa)

> [!NOTE]
> La cuarentena automática solo se admite Windows 10

Cuando está habilitada, la cuarentena automática se inicia en el momento en el que una aplicación no permitida intenta acceder a un elemento confidencial protegido por una DLP. La cuarentena automática mueve el elemento confidencial a una carpeta configurada por el administrador y puede dejar un archivo **.txt** como marcador de posición en el lugar del original. Puede configurar el texto del archivo del marcador de posición para indicar a los usuarios a dónde se movió el elemento y cualquier otra información pertinente.  

Puede usar la cuarentena automática para evitar una cadena infinita de notificaciones de la DLP dirigida al usuario y los administradores. Vea [Escenario 4: evitar el bucle de notificaciones de la DLP en las aplicaciones con sincronización en la nube con cuarentena automática (vista previa)](#scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview).

### <a name="unallowed-bluetooth-apps"></a>Aplicaciones de Bluetooth no permitidas

Evite que los usuarios transfieran archivos protegidos por las directivas a través de aplicaciones Bluetooth específicas.

### <a name="browser-and-domain-restrictions-to-sensitive-data"></a>Restricciones de explorador y dominio a los datos confidenciales

Restrinja el uso compartido de los archivos confidenciales que coincidan con las directivas con dominios de servicio en la nube sin restricciones.

#### <a name="unallowed-browsers"></a>Exploradores no permitidos

Agregue exploradores, identificados por sus nombres ejecutables, que no tendrán acceso a los archivos que cumplan las condiciones de una directiva DLP aplicada cuya restricción de carga a servicios en la nube esté configurada para bloquearse o bloquear una invalidación. Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Edge Chromium.

#### <a name="service-domains"></a>Dominios de servicio

Puede controlar si los archivos confidenciales protegidos por sus directivas se pueden cargar en dominios de servicio específicos de Microsoft Edge.

Si el modo de lista está configurado en **Bloquear**, el usuario no podrá cargar elementos confidenciales a esos dominios. Cuando se bloquea una acción de carga porque un elemento coincide con una directiva DLP, la DLP genera una advertencia o bloquea la carga del elemento confidencial.

Si el modo de lista está configurado en **Permitir**, los usuarios podrán cargar elementos confidenciales **_solo_** a dichos dominios y no se permitirá el acceso de carga a los demás dominios.

> [!IMPORTANT]
> Cuando el modo de restricción del servicio esté establecido en "Permitir", debe tener al menos un dominio de servicio configurado antes de que las restricciones se apliquen.

### <a name="additional-settings-for-endpoint-dlp"></a>Configuración adicional para DLP de punto de conexión

#### <a name="business-justification-in-policy-tips"></a>Justificaciones empresariales en sugerencias de directivas

Puede controlar cómo interactúan los usuarios con la opción de justificación empresarial en las notificaciones de sugerencias de directiva DLP. Esta opción aparece cuando los usuarios realizan una actividad que está protegida por la configuración **Bloquear con anulación** en una directiva DLP. Esta es una configuración global. Puede elegir entre una de las siguientes opciones:

- **Mostrar opciones predeterminadas y cuadro de texto personalizado**: los usuarios pueden, de forma predeterminada, seleccionar una justificación integrada o escribir su propio texto.
- **Mostrar solo las opciones predeterminadas**: los usuarios solo pueden seleccionar una justificación integrada.
- **Mostrar solo el cuadro de texto personalizado**: los usuarios solo pueden escribir su propia justificación. Solo el cuadro de texto aparecerá en la notificación de sugerencia de directiva del usuario final. 

##### <a name="customizing-the-options-in-the-drop-down-menu"></a>Personalización de las opciones en el menú desplegable

Puede crear hasta cinco opciones personalizadas que aparecerán cuando los usuarios interactúen con la sugerencia de notificación de la directiva seleccionando **Personalizar el menú desplegable de opciones**. 


|Opción |Texto predeterminado  |
|---------|---------|
|opción 1    | **Esto forma parte de un flujo de trabajo empresarial establecido**  o puede escribir texto personalizado        |
|opción 2  |**Mi administrador ha aprobado esta acción** o puede escribir texto personalizado         |
|opción 3   |**Se requiere acceso urgente; notificaré a mi administrador por separado** o puede escribir texto personalizado          |
|Mostrar opción de falsos positivos     |**La información de estos archivos no es confidencial** o puede escribir texto personalizado          |
|opción 5    |**Otro** o puede escribir texto personalizado         |

<!--See, [Scenario 5: Configure a policy to use the customized business justification](#scenario-5-configure-a-policy-to-use-the-customized-business-justification)-->

### <a name="always-audit-file-activity-for-devices"></a>Auditar siempre la actividad de archivos para dispositivos

De forma predeterminada cuando los dispositivos están integrados, la actividad de los archivos Office, PDF y CSV se audita automáticamente y está disponible para su revisión en el Explorador de actividades. Desactive esta característica si quiere que esta actividad se audite solo cuando los dispositivos integrados estén incluidos en una directiva activa.

La actividad de archivo se auditará siempre en los dispositivos integrados, independientemente de si están o no incluidos en una directiva activa.

## <a name="tying-dlp-settings-together"></a>Vincular las opciones de configuración DLP

Con la DLP de los puntos de conexión y el Explorador web Edge Chromium, puede restringir el uso compartido no intencionado de elementos confidenciales a las aplicaciones y servicios en la nube no permitidos. Edge Chromium comprende cuándo un elemento está restringido por una directiva DLP de los puntos de conexión y aplica las restricciones de acceso.

Cuando usa la DLP de los puntos de conexión como una ubicación en una directiva DLP configurada correctamente y en el explorador Edge Chromium, los exploradores no permitidos que haya definido en esta configuración no tendrán acceso a los elementos confidenciales que coincidan con los controles de la directiva DLP. En su lugar, se redirigirá a los usuarios para que usen Edge Chromium que, con su comprensión de las restricciones impuestas por DLP, puede bloquear o restringir las actividades cuando se cumplan las condiciones de la directiva DLP.

Para usar esta restricción, tendrá que configurar tres partes importantes:

1. Especifique los sitios (servicios, dominios y direcciones IP) con los que no quiere que se compartan elementos confidenciales.

2. Agregue los exploradores que no tienen permitido acceder a ciertos elementos confidenciales cuando se produzca una coincidencia de directiva DLP.

3. Configure directivas DLP para definir los tipos de elementos confidenciales que deberían tener carga restringida a estos lugares activando **Cargar a los servicios en la nube** y **Acceso desde un explorador no permitido**.

Puede continuar agregando nuevos servicios, aplicaciones y directivas para ampliar y aumentar las restricciones para satisfacer las necesidades de su empresa y proteger los datos confidenciales. 

Esta configuración garantizará que sus datos estén seguros, evitando así las restricciones innecesarias que impiden o restringen a los usuarios el acceso y el uso compartido de elementos no confidenciales.

## <a name="endpoint-dlp-policy-scenarios"></a>Escenarios de directiva DLP de los puntos de conexión

Para ayudarle a familiarizarse con las características de DLP de los puntos de conexión y cómo se muestran en las directivas DLP, hemos recopilado algunos escenarios para que los siga.

> [!IMPORTANT]
> Estos escenarios DLP de los puntos de conexión no son los procedimientos oficiales para crear y optimizar directivas DLP. Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:

>- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
>- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
>- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
>- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Escenario 1: crear una directiva a partir de una plantilla, solo auditoría

Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades. Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).

1. Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija **Crear directiva**.

3. Para este escenario, elija **Privacidad**, después **Datos de información de identificación personal (PII) de Estados Unidos**, y elija **Siguiente**.

4. Desactive el campo **Estado** para todas las ubicaciones excepto para **Dispositivos**. Elija **Siguiente**.

5. Acepte la selección predeterminada **Revisar y personalizar la configuración a partir de la plantilla** y elija **Siguiente**.

6. Acepte los valores predeterminados **Acciones de protección** y elija **Siguiente**.

7. Seleccione **Auditar o restringir actividades en dispositivos Windows** y deje las acciones configuradas en **Solo auditar**. Elija **Siguiente**.

8. Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**. Elija **Siguiente**.

9. Revise la configuración y elija **Enviar**.

10. La nueva directiva DLP se mostrará en la lista de directivas.

11. Compruebe que los datos de los puntos de conexión supervisados se encuentren en el Explorador de actividades. Configure el filtro por ubicación de los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver el impacto de esta directiva. Consulte [Introducción al explorador de actividades](data-classification-activity-explorer.md), de ser necesario. 

12. Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización. Esto debería activar la directiva.

13. Compruebe que el evento se encuentre en el Explorador de actividades.

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>Escenario 2: modificar la directiva existente, configurar una alerta

1. Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.

3. Elija **editar directiva**.

4. Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.

5. Desplácese hacia abajo hasta la sección **Informes de incidentes** y configure **Enviar una alerta a los administradores cuando se produzca una coincidencia de regla** en **Activado**. Las alertas por correo electrónico se enviarán automáticamente al administrador y a cualquier persona que agregue a la lista de destinatarios. 

   > [!div class="mx-imgBorder"]
   > ![activar-informes-de-incidentes](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. Para este escenario, elija **Enviar una alerta cada vez que una actividad coincida con la regla**.

7. Seleccione **Guardar**.

8. Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.

9. Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización. Esto debería activar la directiva.

10. Compruebe que el evento se encuentre en el Explorador de actividades.

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>Caso 3: modificar la directiva existente, bloquear la acción con permitir invalidación

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

9. Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización. Esto debería activar la directiva.

   Verá un elemento emergente como el siguiente en el dispositivo cliente:

   > [!div class="mx-imgBorder"]
   > ![notificación de invalidación de cliente bloqueado por dlp en punto de conexión.](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Compruebe que el evento se encuentre en el Explorador de actividades.

### <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>Escenario 4: evitar el bucle de notificaciones de la DLP en las aplicaciones con sincronización en la nube con cuarentena automática (vista previa)

#### <a name="before-you-begin"></a>Antes de empezar

En este escenario, se bloquea la sincronización de archivos con la etiqueta de confidencialidad **Extremadamente confidencial** para OneDrive. Se trata de un escenario complejo con varios componentes y procedimientos. Necesitará:

- Una cuenta de usuario de AAD de destino y un equipo Windows 10 incorporado que ya esté sincronizando una carpeta local de OneDrive con el almacenamiento en la nube de OneDrive.
- Microsoft Word instalado en el equipo Windows 10 de destino
- Etiquetas de confidencialidad configuradas y publicadas. Vea [Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels) y [Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies)

Hay tres pasos:

1. Configure las opciones de cuarentena automática de la DLP del punto de conexión.
2. Cree una directiva que bloquee los elementos confidenciales que tengan la etiqueta de confidencialidad **Extremadamente confidencial**.
3. Cree un documento de Word en el dispositivo Windows 10 al que se destina la directiva, aplique la etiqueta y cópiela en la carpeta local de OneDrive de las cuentas de usuario que se está sincronizando.  

#### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>Configure las aplicaciones no permitidas y la configuración de cuarentena automática de la DLP.

1. Abra la [configuración del punto de conexión de la DLP](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings)

2. Expanda las **Aplicaciones no permitidas**.

3. Elija **Agregar o editar aplicaciones no permitidas** y agregue *OneDrive* como nombre para mostrar y *onedrive.exe* como nombre del ejecutable para impedir que onedrive.exe acceda a los elementos con la etiqueta **Extremadamente confidencial**.

4. Seleccione **cuarentena automática** y **Guardar**.

5. En **Configuración de la cuarentena automática** elija **Editar la configuración de la cuarentena automática**.

6. Habilite **Cuarentena automática para las aplicaciones no permitidas**.

7. Escriba la ruta de acceso a la carpeta de los equipos locales a las que quiere mover los archivos confidenciales originales. Por ejemplo:
   
**'%homedrive%%homepath%\Microsoft DLP\Cuarentena'** para el nombre de usuario *Isaiah Langer* colocará los elementos movidos en una 

carpeta *C:\Usuarios\IsaiahLanger\Microsoft DLP\Cuarentena\OneDrive* y se anexará una marca de fecha y hora al nombre de archivo original.

> [!NOTE]
> La cuarentena automática de la DLP creará subcarpetas para los archivos de cada aplicación no permitida. Por lo tanto, si tiene tanto el *Bloc de notas* como *OneDrive* en la lista de aplicaciones no permitidas, se creará una subcarpeta para **\OneDrive** y otra subcarpeta para **\Bloc de notas**.

8. Elija **Reemplazar los archivos por un archivo .txt que contenga el siguiente de texto** y escriba el texto que desee en el archivo de marcador de posición. Por ejemplo, para un archivo denominado *cuarentena automática 1.docx*:
    
**%%FileName%% contiene información confidencial que su empresa está protegiendo con la directiva de prevención de pérdida de datos (DLP) %%PolicyName%% y se ha movido a la carpeta en cuarentena: %%QuarantinePath%%.** 

dejará un archivo .txt que contiene este mensaje

*cuar auto 1.docx contiene información confidencial que su empresa está protegiendo con la directiva de prevención de pérdida de datos (DLP) y se ha movido a la carpeta en cuarentena: C:\Usuarios\IsaiahLanger\Microsoft DLP\Cuarentena\OneDrive\cuar auto 1_20210728_151541.docx.*

9. Elija **Guardar**

#### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>Configurar una directiva para bloquear la sincronización de archivos de OneDrive con la etiqueta de confidencialidad Extremadamente confidencial

1. Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Elija **Crear directiva**.

3. En este escenario, elija **Personalizado** y, a continuación, **Directiva personalizada** y elija **Siguiente**.

4. Rellene los campos **Nombre** y **Descripción** y elija **Siguiente**.

5. Desactive el campo **Estado** para todas las ubicaciones excepto para **Dispositivos**. Si tiene una cuenta de usuario final específica desde la que desea hacer una prueba, asegúrese de seleccionarla en el ámbito de búsqueda. Elija **Siguiente**.

6. Acepte la selección **Crear o personalizar reglas DLP avanzadas** que viene predeterminada y elija **Siguiente**.

7. Cree una regla con estos valores:
    1. **Nombre** > *Escenario 4 de la cuarentena automática*
    1. **Condiciones** > **Contenido contiene** > **Etiquetas de confidencialidad** > **Extremadamente confidencial**
    1.  **Acciones** > **Auditar o restringir actividades en dispositivos Windows** > **Acceso de aplicaciones no permitidas** > **Bloquear**. Para los fines de este escenario, borre todas las demás actividades.
    1. **Notificaciones del usuario** > **Activadas**
    1. **Dispositivos de punto de conexión** > Elegir **Mostrar a los usuarios una notificación de sugerencia de directiva cuando una actividad** siempre que no esté ya activada.
    
8. Elija **Guardar** y **Siguiente**.

9. Elija **Activar inmediatamente**. Elija **siguiente**.

10. Revise la configuración y elija **Enviar**.

> [!NOTE]
> Espere al menos una hora para que la nueva directiva se replique y se aplique al equipo de Windows 10 de destino.

11. La nueva directiva DLP se mostrará en la lista de directivas.

#### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Probar la cuarentena automática en el dispositivo Windows 10

1. Inicie sesión en el equipo Windows 10 con la cuenta de usuario que especificó en [Configurar una directiva para bloquear la sincronización de archivos de OneDrive con la etiqueta de confidencialidad Extremadamente confidencial](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential) del paso 5.

2. Cree una carpeta con un contenido que no se sincronizará en OneDrive. Por ejemplo:

    *carpeta de origen C:\auto-cuarentena*

3. Abra Microsoft Word y cree un archivo en la carpeta de origen de cuarentena automática. Aplique la etiqueta de confidencialidad **Extremadamente confidencial**. Consulte [Aplicar etiquetas de confidencialidad a sus archivos y correos electrónicos en Office](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

4. Copie el archivo que acaba de crear en la carpeta de sincronización de OneDrive. Debe aparecer una notificación del sistema para el usuario que indica que la acción no está permitida y que el archivo se pondrá en cuarentena. Por ejemplo, para el nombre de usuario *Isaiah Langer* y un documento titulado *doc auto-cuarentena 1.docx* vería este mensaje:

![Ventana emergente de notificación de prevención de pérdida de datos para el usuario que indica que la acción de sincronización de OneDrive no está permitida para el archivo especificado y que el archivo se pondrá en cuarentena.](../media/auto-quarantine-user-notification-toast.png)

El mensaje indica:

«No se permite abrir doc auto-cuarentena 1.docx con esta aplicación. El archivo se pondrá en cuarentena en 'C:\Usuarios\IsaiahLanger\Microsoft DLP\OneDrive'».

5. Elija **Descartar**

6. Abra el archivo .txt del marcador de posición. Se denominará **doc auto-cuarentena 1.docx_ *fecha_hora*.txt**. 

7. Abra la carpeta de cuarentena y confirme que el archivo original está allí.
 
8. Compruebe que los datos de los puntos de conexión supervisados se encuentren en el Explorador de actividades. Configure el filtro por ubicación de los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver el impacto de esta directiva. Consulte [Introducción al explorador de actividades](data-classification-activity-explorer.md), de ser necesario. 

9. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="see-also"></a>Consulte también

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Herramientas y métodos de incorporación para equipos con Windows 10](/microsoft-365/compliance/dlp-configure-endpoints).
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Unido a Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join)
- [Descargue el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
