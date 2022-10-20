---
title: Configurar las opciones de DLP de punto de conexión
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
- purview-compliance
- SPO_Content
search.appverid:
- MET150
description: Obtenga información sobre cómo definir la configuración central de prevención de pérdida de datos en el punto de conexión (DLP).
ms.openlocfilehash: d3b38a9125979f33e4d22277b8967f4f3d37c349
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621370"
---
# <a name="configure-endpoint-data-loss-prevention-settings"></a>Configuración de la prevención de pérdida de datos de punto de conexión

Muchos aspectos del comportamiento de prevención de pérdida de datos (DLP) en el punto de conexión se controlan mediante opciones configuradas de forma centralizada. La configuración se aplica a todas las directivas DLP para dispositivos.

![Configuración de DLP de punto de conexión](../media/endpoint-dlp-1-using-dlp-settings.png)

Debe configurar estas opciones si desea controlar:

- Restricciones de salida en la nube
- Varios tipos de acciones restrictivas en las actividades de usuario por aplicación.
- Exclusiones de ruta de acceso de Windows y dispositivos macOS.
- Restricciones de explorador y dominio.
- Cómo aparecen las justificaciones empresariales para invalidar directivas en las sugerencias de directiva.
- Si las actividades en archivos de Office, PDF y CSV se auditan automáticamente.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="dlp-settings"></a>Configuración DLP

Antes de empezar, debe configurar la configuración de DLP. 

### <a name="endpoint-dlp-windows-1011-and-macos-settings"></a>Configuración de Windows 10/11 DLP de punto de conexión y macOS

|Setting |Windows 10, 1809 y versiones posteriores, Windows 11  |macOS (tres versiones más recientes) |Notas  |
|---------|---------|---------|---------|
|Exclusiones de ruta de archivo     |Compatible         |Compatible         |macOS incluye una lista recomendada de exclusiones que está predeterminada          |
|Aplicaciones restringidas     |Compatible         |Compatible         |         |
|Grupos de aplicaciones restringidos |Compatible |No se admite
|Aplicaciones de Bluetooth no permitidas    |Compatible         |No se admite         |         |
|Restricciones de explorador y dominio a los elementos confidenciales      |Compatible         |Compatible         |         |
|Configuración adicional para DLP de punto de conexión     |Compatible         |Compatible         |Solo se admiten las justificaciones empresariales predeterminadas para dispositivos macOS         |
|Auditar siempre la actividad de archivos para dispositivos     |Compatible         |Compatible         |         |
|Archivo de cuarentena automática de aplicaciones no permitidas | Compatible | No se admite| |
|Clasificación avanzada | Compatible | No se admite| |
|Justificaciones empresariales en sugerencias de directivas | Compatible | Compatible| |

### <a name="advanced-classification-scanning-and-protection"></a>Escaneo y protección de clasificación avanzada

El escaneo y la protección de clasificación avanzada permiten que el servicio de clasificación de datos basado en la nube de Microsoft Purview, más avanzado, escanee elementos, los clasifique y devuelva los resultados a la máquina local. Esto significa que puede aprovechar las técnicas de clasificación, como la clasificación [de coincidencia de datos exacta](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) y las [entidades con nombre](named-entities-learn.md) en las directivas DLP.

Cuando se activa la clasificación avanzada, el contenido se envía desde el dispositivo local a los servicios en la nube para su examen y clasificación. Si el uso de ancho de banda supone un problema, puede establecer un límite en lo que concierne a cuánto se puede usar en un período de 24 horas. El límite se define en la configuración de DLP de punto de conexión y se aplica por dispositivo. Si establece un límite de uso de ancho de banda y se supera, DLP deja de enviar el contenido del usuario a la nube. En este momento, la clasificación de datos continúa localmente en el dispositivo, pero la clasificación con coincidencia exacta de datos, entidades con nombre y clasificadores capacitados no está disponible. Cuando el uso del ancho de banda acumulado se encuentra por debajo del límite de 24 horas, se reanudará la comunicación con los servicios en la nube.

Si el uso del ancho de banda no supone un problema, seleccione **Sin límite** para permitir el uso ilimitado del ancho de banda.

Estas versiones de Windows admiten la protección y el escaneo de clasificación avanzada:

- Windows 10 versiones 20H1/20H2/21H1 (KB 5006738)
- Windows 10 versiones 19H1/19H2 (KB 5007189)
- Windows 10 RS5 (KB 5006744)

> [!NOTE]
> La compatibilidad con la clasificación avanzada está disponible para archivos de Office (Word, Excel, PowerPoint) y de PDF.

> [!NOTE]
> La evaluación de directivas DLP siempre se produce en la nube, incluso si el contenido del usuario no se envía.

### <a name="file-path-exclusions"></a>Exclusiones de ruta de archivo

Abra el [Portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com) > **Prevención de pérdida de datos** > **Configuración DLP de punto de conexión** > **Exclusiones de ruta de acceso de archivo**.

Es posible que quiera excluir determinadas rutas de supervisión DLP, alertas DLP y la aplicación de directivas DLP en sus dispositivos, ya sea porque provocan demasiado ruido o no contienen archivos que le interesan. Los archivos en esas ubicaciones no se auditarán y los archivos que se creen o modifiquen en esas ubicaciones no se someterán a la aplicación de directivas DLP. Puede configurar exclusiones de ruta en configuración DLP.

#### <a name="windows-10-devices"></a>Dispositivos con Windows 10

Puede usar esta lógica para crear sus rutas de exclusión para dispositivos Windows 10:

- Ruta de acceso de archivo válida que termina con `\`, lo que significa solo archivos que están directamente en la carpeta. <br/>Por ejemplo: `C:\Temp\`

- Ruta de acceso de archivo válida que termina con `\*`, lo que significa solo archivos en subcarpetas. Los archivos directamente en la carpeta no se excluyen. <br/>Por ejemplo: `C:\Temp\*`

- Ruta de acceso de archivo válida que termina sin `\` o `\*`, lo que significa todos los archivos que se encuentran directamente en la carpeta y en todas las subcarpetas. <br/>Por ejemplo: `C:\Temp`

- Ruta de acceso con comodín entre `\` de cada lado. <br/>Por ejemplo: `C:\Users\*\Desktop\`

- Ruta de acceso con comodín entre `\` de cada lado y con `(number)` para proporcionar el número exacto de subcarpetas. <br/>Por ejemplo: `C:\Users\*(1)\Downloads\`

- Una ruta con variables de entorno del SISTEMA. <br/>Por ejemplo: `%SystemDrive%\Test\*`

- Una combinación de todas las anteriores. <br/>Por ejemplo: `%SystemDrive%\Users\*\Documents\*(2)\Sub\`

#### <a name="macos-devices"></a>dispositivos macOS

Al igual que los dispositivos Windows 10, puede agregar sus propias exclusiones para dispositivos macOS.

- Las definiciones de ruta de acceso del archivo no distinguen mayúsculas de minúsculas, por lo que `User` es igual que `user`.

- Wildcard values are supported. So a path definition can contain a `*` in the middle of the path or at the end of the path. For example: `/Users/*/Library/Application Support/Microsoft/Teams/*`

##### <a name="recommended-file-path-exclusions-preview"></a>Exclusiones recomendadas de ruta de acceso del archivo (versión preliminar)

Por motivos de rendimiento, DLP de punto de conexión incluye una lista de exclusiones recomendadas de ruta de acceso del archivo para dispositivos macOS. Estas exclusiones están activadas de manera predeterminada. Puede deshabilitarlas si quiere al alternar la alternancia **Incluir exclusiones recomendadas de ruta de acceso de archivo para Mac**. La lista incluye:

- /Applications/*
- /System/*
- /usr/*
- /Library/*
- /private/*
- /opt/*
- /Users/*/Library/Application Support/Microsoft/Teams/*

### <a name="restricted-apps-and-app-groups"></a>Aplicaciones y grupos de aplicaciones restringidos

#### <a name="restricted-apps"></a>Aplicaciones restringidas

Las **aplicaciones restringidas** (anteriormente denominadas **aplicaciones no permitidas**) son una lista de aplicaciones que crea. Configure las acciones que realizará DLP cuando un usuario use una aplicación de la lista para **_acceder_** a un archivo protegido de DLP en un dispositivo. Está disponible para dispositivos Windows 10 y macOS.

Cuando se selecciona **Acceso por aplicaciones restringidas** en una directiva y un usuario usa una aplicación que se encuentra en la lista de aplicaciones restringidas para acceder a un archivo protegido, la actividad se `audited`, `blocked` o `blocked with override` en función de cómo la haya configurado. Es decir, a menos que la misma aplicación sea miembro de un **grupo de aplicaciones restringidas**, las acciones configuradas para las actividades del **Grupo de aplicaciones restringidas** invalidan las acciones configuradas para la actividad de acceso de la lista de **Aplicaciones restringidas**. Toda actividad es auditada y está disponible para su revisión en el explorador de actividades.

> [!IMPORTANT]
> No incluya la ruta de acceso al archivo ejecutable, solo el nombre del archivo ejecutable (por ejemplo, browser.exe).

> [!IMPORTANT]
> La acción (`audit`, `block with override`o `block`) definida para las aplicaciones que están en la lista de aplicaciones restringidas solo se aplica cuando un usuario intenta ***acceder*** a un elemento protegido. 

#### <a name="file-activities-for-apps-in-restricted-app-groups"></a>Actividades de archivo para aplicaciones en grupos de aplicaciones restringidos

Los grupos de aplicaciones restringidos son colecciones de aplicaciones que crea en la configuración de DLP y luego agrega a una regla de una directiva. Al agregar un grupo de aplicaciones restringido a una directiva, puede realizar las acciones definidas en esta tabla.

|Opción de grupo de aplicaciones restringidas  |Qué le permite hacer  |
|---------|---------|
|No restringir la actividad de archivos     |Indica a DLP que permita a los usuarios tener acceso a los elementos protegidos de DLP mediante aplicaciones del grupo de aplicaciones y no realice ninguna acción cuando el usuario intenta **Copiar en el portapapeles**, **Copiar en una unidad extraíble USB**, **Copiar en una unidad de red** e **Imprimir** desde la aplicación.          |
|Aplicar una restricción a toda la actividad     |Indica a DLP que `Audit only`, `Block with override`o `Block` cuando un usuario intenta acceder a un elemento protegido de DLP mediante una aplicación que se encuentra en este grupo de aplicaciones         |
|Aplicar restricciones a una actividad específica     |Esta configuración permite a un usuario acceder a un elemento protegido de DLP mediante una aplicación que se encuentra en el grupo de aplicaciones y le permite seleccionar una acción predeterminada (`Audit only`, `Block`o `Block with override`) que DLP realizará cuando un usuario intente **Copiar en el portapapeles**, **Copiar en una unidad extraíble USB**, **Copiar en una unidad de red** e **Imprimir**.          |

> [!IMPORTANT]
> La configuración de un grupo de aplicaciones restringido invalida las restricciones establecidas en la lista de aplicaciones restringidas cuando están en la misma regla. Por lo tanto, si una aplicación está en la lista de aplicaciones restringidas y es miembro de un grupo de aplicaciones restringidas, se aplica la configuración del grupo de aplicaciones restringidas.

#### <a name="how-dlp-applies-restrictions-to-activities"></a>Cómo aplica DLP restricciones a las actividades

Las interacciones entre **Actividades de archivo para aplicaciones en grupos de aplicaciones restringidos**, **Actividades de archivo para todas las aplicaciones** y la lista **Actividades de aplicaciones restringidas** se limitan a la misma regla.

##### <a name="restricted-app-groups-overrides"></a>Invalidaciones de grupos de aplicaciones restringidos

Las configuraciones definidas en **Actividades de archivo para aplicaciones en grupos de aplicaciones restringidos** invalidan las configuraciones de la lista **Actividades de aplicaciones restringidas** y de **Actividades de archivo para todas las aplicaciones** en la misma regla.

##### <a name="restricted-app-activities-and-file-activities-for-all-apps"></a>Actividades de aplicación restringidas y actividades de archivo para todas las aplicaciones

Las configuraciones de **Actividades de aplicaciones restringidas** y **Actividades de archivo para todas las aplicaciones** funcionan de forma conjunta si la acción definida para **Actividades de aplicaciones restringidas** es `Audit only`, `Block with override` o en la misma regla. Esto se debe a que las acciones definidas para **Actividades de aplicaciones restringidas** solo se aplican cuando un usuario accede a un archivo mediante una aplicación que está en la lista. Una vez que el usuario tiene acceso, se aplican las acciones definidas para las actividades de **Actividades de archivo para todas las aplicaciones**. 

Aquí le mostramos un ejemplo:

Si Notepad.exe se agrega a **aplicaciones restringidas** y **las actividades de archivo para todas las aplicaciones** está configurado para **Aplicar restricciones a una actividad específica** y ambas se configuran de la siguiente manera:

|Configuración en directiva  |Nombre de la aplicación  |Actividad de usuario  |Acción DLP que se debe realizar  |
|---------|---------|---------|---------|
|Actividades de aplicación restringidas     |Bloc de notas        |Obtener acceso a un elemento protegido de DLP         |Solo auditoría         |
|Actividades de archivo para todas las aplicaciones   |Todas las aplicaciones        | Copiar en el portapapeles        |Solo auditoría         |
|Actividades de archivo para todas las aplicaciones     |Todas las aplicaciones         |Copiar en un dispositivo extraíble USB | Bloquear       |
|Actividades de archivo para todas las aplicaciones     |Todas las aplicaciones         |Copiar en un recurso compartido de red         |Solo auditoría         |
|Actividades de archivo para todas las aplicaciones   |Todas las aplicaciones         |Imprimir         |Bloquear         |
|Actividades de archivo para todas las aplicaciones     |Todas las aplicaciones         |Copiar o mover mediante una aplicación Bluetooth no permitida         |Blocked         |
|Actividades de archivo para todas las aplicaciones     |Todas las aplicaciones         |Servicios de Escritorio remoto         |Bloqueo con invalidación         |

El usuario A abre un archivo DLP protegido mediante el bloc de notas. DLP permite el acceso y audita la actividad. Mientras sigue en el bloc de notas, el usuario A intenta copiar en el portapapeles desde el elemento protegido, lo cual funciona y DLP audita la actividad. A continuación, el usuario A intenta imprimir el elemento protegido desde el bloc de notas y la actividad está bloqueada.

> [!NOTE]
> Cuando la acción de DLP que se va a realizar en **Actividades de aplicación restringidas** se establece en `block`, se bloquea todo el acceso y el usuario no puede realizar ninguna actividad en el archivo.
   
##### <a name="file-activities-for-all-apps-only"></a>Actividades de archivo solo para todas las aplicaciones

Si una aplicación no está en **Actividades de archivo para aplicaciones de grupos de aplicaciones restringidos** o no está en la lista **Actividades de aplicación restringida** o está en la lista **Actividades de aplicación restringida** con una acción de `Audit only`o "Bloquear con invalidación", las restricciones definidas en las **actividades Archivo para todas las aplicaciones** se aplican en la misma regla.  

#### <a name="macos-devices"></a>dispositivos macOS

Al igual que en los dispositivos Windows, ahora podrá impedir que las aplicaciones macOS accedan a datos confidenciales definiéndolos en la **Lista de actividades de aplicaciones restringidas**. 

> [!NOTE]
> Tenga en cuenta que las aplicaciones entre plataformas deben especificarse con sus rutas de acceso únicas respectivas al sistema operativo en el que se ejecutan.

Para encontrar la ruta de acceso completa de las aplicaciones de Mac:

1. En el dispositivo macOS, abra **Monitor de actividad**. Buscar y hacer doble clic en el proceso que desea restringir

2. Elija la pestaña **Abrir Archivos y Puertos**.
  
3. Para las aplicaciones de macOS, se necesita el nombre completo de la ruta de acceso, incluido el nombre de la aplicación.

#### <a name="protect-sensitive-data-from-cloud-synchronization-apps"></a>Protección de datos confidenciales de aplicaciones con sincronización en la nube

Para evitar que las aplicaciones con sincronización en la nube sincronicen elementos confidenciales en la nube, como *onedrive.exe*, agregue la aplicación de sincronización en la nube a la lista **Aplicaciones no permitidas**. Cuando una aplicación con sincronización en la nube no permitida intenta acceder a un elemento protegido por una directiva DLP de bloqueo, la DLP puede generar notificaciones repetidas. Puede evitar estas notificaciones repetidas habilitando la opción **Cuarentena automática** en **Aplicaciones no permitidas**.  

##### <a name="auto-quarantine-preview"></a>Cuarentena automática (vista previa)

> [!NOTE]
> La cuarentena automática solo se admite Windows 10

Cuando está habilitada, la cuarentena automática se inicia en el momento en el que una aplicación no permitida intenta acceder a un elemento confidencial protegido por una DLP. La cuarentena automática mueve el elemento confidencial a una carpeta configurada por el administrador y puede dejar un archivo **.txt** como marcador de posición en el lugar del original. Puede configurar el texto del archivo del marcador de posición para indicar a los usuarios a dónde se movió el elemento y cualquier otra información pertinente.  

Puede usar la cuarentena automática para evitar una cadena infinita de notificaciones DLP para el usuario y los administradores, vea [Escenario 4: evitar el bucle de notificaciones de la DLP en las aplicaciones con sincronización en la nube con cuarentena automática (vista previa)](endpoint-dlp-using.md#scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview).

### <a name="unallowed-bluetooth-apps"></a>Aplicaciones de Bluetooth no permitidas

Evite que los usuarios transfieran archivos protegidos por las directivas a través de aplicaciones Bluetooth específicas.

### <a name="browser-and-domain-restrictions-to-sensitive-data"></a>Restricciones de explorador y dominio a los datos confidenciales

Restrinja el uso compartido de los archivos confidenciales que coincidan con las directivas con dominios de servicio en la nube sin restricciones.

#### <a name="unallowed-browsers"></a>Exploradores no permitidos

En el caso de los dispositivos Windows, agrega exploradores, identificados por sus nombres ejecutables, que se bloquearán para que no accedan a los archivos que coincidan con las condiciones de una directiva DLP aplicada en la que la restricción de carga en los servicios en la nube está establecida para bloquear o bloquear la invalidación. Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Microsoft Edge.

Para dispositivos macOS, debe agregar la ruta de acceso de archivo completa. Para encontrar la ruta de acceso completa de las aplicaciones de Mac:

1. En el dispositivo macOS, abra **Monitor de actividad**. Buscar y hacer doble clic en el proceso que desea restringir

2. Elija la pestaña **Abrir Archivos y Puertos**.
  
3. Para las aplicaciones de macOS, se necesita el nombre completo de la ruta de acceso, incluido el nombre de la aplicación.

#### <a name="service-domains"></a>Dominios de servicio

> [!NOTE]
> La configuración de **Dominios de servicio** solo se aplica a los archivos cargados con Microsoft Edge o Google Chrome con la [extensión Microsoft Purview](dlp-chrome-learn-about.md#learn-about-the-microsoft-purview-extension) instalada.

Puede controlar si los archivos confidenciales protegidos por las directivas se pueden cargar en dominios de servicio específicos desde Microsoft Edge.

##### <a name="allow"></a>Permitir

Cuando la lista **Dominios de servicio** está establecida en **Permitir**, las directivas DLP no se aplicarán cuando un usuario intente cargar un archivo confidencial en ninguno de los dominios de la lista.

Si el modo de lista está establecido en **Permitir**, se auditará cualquier actividad de usuario que implique un elemento confidencial y un dominio que esté en la lista. Se permite la actividad. Cuando un usuario intenta una actividad que implica un elemento confidencial y un dominio que *no está* en la lista, se aplican las directivas DLP y las acciones definidas en las directivas.

Por ejemplo, con esta configuración:

- **El modo de lista de dominios de servicio** está establecido en **Permitir**.
    - Contoso.com está en la lista.
-  Una directiva DLP se establece en **Bloquear** la carga de elementos confidenciales que contienen números de tarjeta de crédito.
 
El usuario intenta:

- Cargue un archivo confidencial con números de tarjeta de crédito en contoso.com.
    - Se permite la actividad de usuario, se audita, se genera un evento, pero no se muestra el nombre de la directiva ni el nombre de la regla desencadenante en los detalles del evento y no se genera ninguna alerta. 

pero si un usuario intenta: 

- Cargue un archivo confidencial con números de tarjeta de crédito en wingtiptoys.com (que no está en la lista).
    - Se aplica la directiva y se bloquea la actividad del usuario. Se genera un evento y se genera una alerta. 
 
##### <a name="block"></a>Bloquear
 
Cuando la lista **Dominios de servicio** se establece en **Bloquear**, se aplicarán directivas DLP cuando un usuario intente cargar un archivo confidencial en cualquiera de los dominios de la lista.

Si el modo de lista está establecido en **Bloquear**, cuando un usuario intenta una actividad que implica un elemento confidencial y un dominio que se encuentra en la lista, se aplican las directivas DLP y las acciones definidas en las directivas. Cualquier actividad que implique un elemento confidencial y un dominio que no esté en la lista se auditará y se permitirá la actividad del usuario.

Por ejemplo, con esta configuración:

- **El modo de lista de dominios de servicio** está establecido en **Bloquear**.
    - Contoso.com está en la lista.
-  Una directiva DLP se establece en **Bloquear con invalidación** para la carga de elementos confidenciales que contienen números de tarjeta de crédito.
 
El usuario intenta:

- Cargue un archivo confidencial con números de tarjeta de crédito en contoso.com.
    - La actividad de usuario está bloqueada, pero el usuario puede invalidar el bloque, se genera un evento y se desencadena una alerta.

pero si un usuario intenta: 

- Cargue un archivo confidencial con números de tarjeta de crédito en wingtiptoys.com (que no está en la lista).
    - La directiva *no se* aplica y la actividad del usuario se audita. Se genera un evento, pero no enumerará el nombre de la directiva ni el nombre de la regla desencadenante en los detalles del evento y no se genera ninguna alerta. 

> [!IMPORTANT]
> Cuando el modo de restricción del servicio esté establecido en "Permitir", debe tener al menos un dominio de servicio configurado antes de que las restricciones se apliquen.

Use el formato FQDN del dominio de servicio sin finalizar `.` al agregar un dominio a la lista.

Por ejemplo:

| Input | Comportamiento de coincidencia de direcciones URL |
|---|---|
| **CONTOSO.COM** |**Coincide con el nombre de dominio especificado y cualquier subsitio**: <p>*://contoso.com<p>*://contoso.com/ <p>*://contoso.com/anysubsite1 <p>*:/ /contoso.com/anysubsite1/anysubsite2 (etc.) <p>**No coincide con subdominios o dominios no especificados**: <p>*://anysubdomain.contoso.com <p>*://anysubdomain.contoso.com.AU |
| ***.CONTOSO.COM** |**Coincide con el nombre de dominio especificado, cualquier subdominio y cualquier sitio**: <p>*://contoso.com <p>*://contoso.com/anysubsite <p>*://contoso.com/anysubsite1/anysubsite2 <p>*://anysubdomain.contoso.com/ <p>*://anysubdomain.contoso.com/anysubsite/ <p>*://anysubdomain1.anysubdomain2.contoso.com/anysubsite/ <p>*://anysubdomain1.anysubdomain2.contoso.com/anysubsite1/anysubsite2 (etc.) <p>**No coincide con dominios no especificados** <p>*://anysubdomain.contoso.com.AU/ |
| **`www.contoso.com`** |**Coincide con el nombre de dominio especificado**: <p>`www.contoso.com` <p>**No coincide con dominios o subdominios no especificados** <p>*://anysubdomain.contoso.com/, en este caso, tiene que colocar el propio nombre de dominio FQDN `www.contoso.com`|

#### <a name="sensitive-service-domains"></a>Dominios de servicio confidenciales

Al enumerar un sitio web en dominios de servicios confidenciales, puede auditar, bloquear con invalidación o bloquear usuarios cuando intenten:

- imprimir desde un sitio web
- copiar datos de un sitio web
- guardar un sitio web como archivos locales
- cargar un archivo confidencial en un sitio web excluido (se configura en la directiva)

Para las acciones de impresión, copia y guardado, cada sitio web debe aparecer en un grupo de sitios web y el usuario debe acceder al sitio web a través de Microsoft Edge. Para la acción de carga, el usuario puede usar Microsoft Edge o Google Chrome con la extensión Purview. Los dominios de servicio confidenciales se usan junto con una directiva DLP para dispositivos. También puede definir los grupos de sitios web a los que desea asignar acciones de directiva distintas de las acciones de grupo de sitios web globales. Consulte [Escenario 6 Supervisar o restringir las actividades del usuario en dominios de servicio confidenciales](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) para obtener más información.


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

### <a name="always-audit-file-activity-for-devices"></a>Auditar siempre la actividad de archivos para dispositivos

De forma predeterminada cuando los dispositivos están integrados, la actividad de los archivos Office, PDF y CSV se audita automáticamente y está disponible para su revisión en el Explorador de actividades. Desactive esta característica si quiere que esta actividad se audite solo cuando los dispositivos integrados estén incluidos en una directiva activa.

La actividad de archivo se auditará siempre en los dispositivos integrados, independientemente de si están o no incluidos en una directiva activa.

> [!IMPORTANT]
> Para poder usar [los grupos de impresoras (versión preliminar),](#printer-groups-preview) [los grupos de dispositivos de almacenamiento extraíbles](#removable-storage-device-groups-preview), los [grupos de recursos compartidos de red](#network-share-groups-preview) y la [configuración de VPN](#vpn-settings-preview) , debe registrarse [aquí](https://forms.office.com/r/GNVTFvxuZv).

### <a name="printer-groups-preview"></a>Grupos de impresoras (versión preliminar)

Use esta configuración para definir grupos de impresoras a los que desea asignar acciones de directiva distintas de las acciones de impresión globales. Por ejemplo, supongamos que quiere que la directiva DLP bloquee la impresión de contratos en todas las impresoras, excepto en las impresoras que están en el departamento legal.

Esta característica está disponible para dispositivos que ejecutan cualquiera de las siguientes versiones de Windows:  

- Windows 10 y versiones posteriores (20H2, 21H1, 21H2) 
- Ganar 11 21H2, 22H2
- Windows Server 2022

Una impresora se define mediante estos parámetros:

- Nombre descriptivo de la impresora: obtenga el valor Nombre descriptivo de la impresora de los detalles de la propiedad del dispositivo de impresora en el administrador de dispositivos.
- Id. de producto USB: obtenga el valor de ruta de acceso de la instancia de dispositivo de los detalles de la propiedad del dispositivo de impresora en el administrador de dispositivos. Conviértalo en el formato id. de producto y de id. de proveedor, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers).
- Id. de proveedor USB: obtenga el valor de ruta de acceso de la instancia de dispositivo de los detalles de la propiedad del dispositivo de impresora en el administrador de dispositivos. Conviértalo en el formato id. de producto y de id. de proveedor, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers).
- Intervalo IP
- Imprimir en archivo: por ejemplo, Microsoft Print to PDF o Microsoft XPS Document Writer.
- Impresión universal implementada en una impresora: consulte [Configuración de la impresión universal](/universal-print/fundamentals/universal-print-getting-started.md) para obtener más información sobre las impresoras universales.
- Impresora corporativa: es una cola de impresión compartida a través del servidor de impresión local de Windows del dominio. Su ruta de acceso podría parecerse  \\a print-server\contoso.com\legal_printer_001
- Imprimir en local

Asigne un **nombre para mostrar** a cada impresora del grupo. El nombre solo aparece en la consola de Purview. Por lo tanto, continuando con el ejemplo, crearía un grupo de **impresoras denominado Impresoras legales** y agregaría impresoras individuales (con un alias) por su nombre descriptivo, como `legal_printer_001`, `legal_printer_002` y `legal_color_printer`.

Puede seleccionar varios parámetros para ayudarle a identificar inequívocamente una impresora específica.

Puede asignar estas acciones de directiva al grupo en una directiva DLP:

- Permitir (auditoría sin notificaciones ni alertas de usuario)
- Solo auditoría (puede agregar notificaciones y alertas)
- Bloquear con invalidación (bloquea la acción, pero el usuario puede invalidarla)
- Bloquear (bloques independientemente de qué)

#### <a name="create-a-printer-group"></a>Creación de un grupo de impresoras

1. Abra [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) >  **Configuración dlp de puntos de conexión de** prevención  >  de  > **pérdida de datos****Grupos de impresoras**.
1. Seleccione **Crear grupo de impresoras**.
1. Asigne un nombre al grupo.
1. Seleccione **Agregar impresora**.
1. Asigne a la impresora un **Alias que solo aparecerá aquí.
1. Seleccione los parámetros y proporcione los valores para identificar inequívocamente la impresora específica.
1. Seleccione **Agregar**.
1. Agregue otras impresoras según sea necesario.
1. Seleccione **Cerrar**.

El caso de uso más común es usar grupos de impresoras como lista de permitidos, como en el ejemplo anterior, para permitir la impresión de contratos solo en impresoras que están en el departamento legal. Después de definir un grupo de impresoras aquí, está disponible para usarse en las directivas que tienen como ámbito **Dispositivos**. Consulte [Grupos de autorización del escenario 7](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) para obtener más información sobre cómo configurar acciones de directiva para usar grupos de autorización.

### <a name="removable-storage-device-groups-preview"></a>Grupos de dispositivos de almacenamiento extraíbles (versión preliminar)

Use esta configuración para definir grupos de dispositivos de almacenamiento extraíbles, como unidades usb, a los que desea asignar acciones de directiva distintas de las acciones de impresión globales. Por ejemplo, supongamos que quiere que la directiva DLP bloquee la copia de elementos con especificaciones de ingeniería en todos los dispositivos de almacenamiento extraíbles, excepto en el caso de las unidades de disco duro conectadas por USB que se usan para realizar copias de seguridad de datos y que, a continuación, se envían fuera del sitio.

Esta característica está disponible para dispositivos que ejecutan cualquiera de las siguientes versiones de Windows:  

- Windows 10 y versiones posteriores (20H2, 21H1, 21H2) 
- Ganar 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744) y Windows Server 2022 

Puede definir dispositivos de almacenamiento extraíbles mediante estos parámetros:

- Nombre descriptivo del dispositivo de almacenamiento: obtenga el valor nombre descriptivo de los detalles de la propiedad del dispositivo de almacenamiento en el administrador de dispositivos.
- Id. de producto USB: obtenga el valor de ruta de acceso de la instancia de dispositivo de los detalles de la propiedad del dispositivo de impresora en el administrador de dispositivos. Conviértalo en el formato id. de producto y de id. de proveedor, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers).
- Id. de proveedor USB: obtenga el valor de ruta de acceso de la instancia de dispositivo de los detalles de la propiedad del dispositivo de impresora en el administrador de dispositivos. Conviértalo en el formato id. de producto y de id. de proveedor, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers).
- Id. de número de serie: obtenga el valor de id. de número de serie de los detalles de la propiedad del dispositivo de almacenamiento en el administrador de dispositivos.
- Id. de dispositivo: obtenga el valor de id. de dispositivo de los detalles de la propiedad del dispositivo de almacenamiento en el administrador de dispositivos.
- Id. de ruta de acceso de instancia: obtenga el valor de id. de dispositivo de los detalles de la propiedad del dispositivo de almacenamiento en el administrador de dispositivos.
- Id. de hardware: obtenga el valor de id. de hardware de los detalles de la propiedad del dispositivo de almacenamiento en el administrador de dispositivos.

Asigne un **alias** a cada dispositivo de almacenamiento extraíble del grupo. El alias es un nombre que solo aparece en la consola de Purview. Por lo tanto, continuando con el ejemplo, crearía un grupo de dispositivos de almacenamiento extraíble denominado **Copia de seguridad** y agregaría dispositivos individuales (con un alias) por su nombre descriptivo, como `backup_drive_001`, y `backup_drive_002`.

Puede seleccionar varios parámetros y el grupo de impresoras incluirá todos los dispositivos que cumplan esos parámetros.

Puede asignar estas acciones de directiva al grupo en una directiva DLP:

- Permitir (auditoría sin notificaciones ni alertas de usuario)
- Solo auditoría (puede agregar notificaciones y alertas)
- Bloquear con invalidación (bloquea la acción, pero el usuario puede invalidarla)
- Bloquear (bloques independientemente de qué)

#### <a name="create-a-removable-storage-device-group"></a>Creación de un grupo de dispositivos de almacenamiento extraíble

1. Abra [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) >  **Configuración DLP de punto de conexión** de **prevención** >  de  >  pérdida de **datos Grupos de dispositivos de almacenamiento extraíbles**.
1. Seleccione **Crear grupo de dispositivos de almacenamiento extraíble**.
1. Proporcione un **nombre de grupo**.
1. Seleccione **Agregar dispositivo de almacenamiento extraíble**.
1. Proporcione un **alias**.
1. Seleccione los parámetros y proporcione los valores para identificar de forma inequívoca el dispositivo específico.
1. Seleccione **Agregar**.
1. Agregue otros dispositivos al grupo según sea necesario.
1. Seleccione **Cerrar**.

El caso de uso más común es usar grupos de dispositivos de almacenamiento extraíbles como una lista de permitidos, como en el ejemplo anterior, para permitir la copia de archivos solo en los dispositivos que se encuentran en el grupo **Copia de seguridad** . Después de definir un grupo de dispositivos de almacenamiento extraíble aquí, está disponible para usarse en las directivas que tienen como ámbito **Dispositivos**. Consulte [Grupos de autorización del escenario 7](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) para obtener más información sobre cómo configurar acciones de directiva para usar grupos de autorización. Aunque el escenario 7 usa grupos de autorización de impresora como ejemplo, los principios son idénticos. Lo único que cambia son los nombres de los grupos y las acciones que seleccione.

### <a name="network-share-groups-preview"></a>Grupos de recursos compartidos de red (versión preliminar)

Use esta configuración para definir grupos de rutas de acceso de recurso compartido de red a los que desea asignar acciones de directiva distintas de las acciones de ruta de acceso del recurso compartido de red global. Por ejemplo, supongamos que quiere que la directiva DLP se bloquee cuando los usuarios intenten guardar o copiar archivos protegidos en recursos compartidos de red excepto los recursos compartidos de red de este grupo.


Esta característica está disponible para dispositivos que ejecutan cualquiera de las siguientes versiones de Windows:  

- Windows 10 y versiones posteriores (20H2, 21H1, 21H2) 
- Ganar 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744) y Windows Server 2022 


Para incluir rutas de acceso de recurso compartido de red, defina el prefijo con el que comienzan todos. Por ejemplo:

- "\\Biblioteca" coincidirá con:
    -  Carpeta \Library y todas sus subcarpetas.

- Puede usar caracteres comodín; por ejemplo, "\\Usuarios\*\Escritorio" coincidirá:
    - "\\USers\user1\Desktop"
    - "\\USers\user1\user2\Desktop"
    - "\\Users\*\Desktop"

- Puede usar variables de entorno, por ejemplo:
    - %AppData%\app123

Puede asignar estas acciones de directiva al grupo en una directiva DLP:

- Permitir (auditoría sin notificaciones ni alertas de usuario)
- Solo auditoría (puede agregar notificaciones y alertas)
- Bloquear con invalidación (bloquea la acción, pero el usuario puede invalidarla)
- Bloquear (bloques independientemente de qué)

#### <a name="create-a-network-share-group"></a>Creación de un grupo de recursos compartidos de red

1. Abra [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) >  **Configuración** dlp de puntos de conexión de prevención  >  de  > **pérdida de datos****Grupos compartidos de red**.
1.Seleccione **Crear grupo de recursos compartidos de red**.
1. Proporcione un **nombre de grupo**.
1. Agregue la ruta de acceso del archivo al recurso compartido.
1. Seleccione **Agregar**.
1. Agregue otras rutas de acceso de recurso compartido al grupo según sea necesario.
1. Seleccione **Cerrar**.


El caso de uso más común es usar el grupo de recursos compartidos de red como una lista de permitidos, como en el ejemplo anterior, para permitir a los usuarios guardar o copiar archivos protegidos solo en los recursos compartidos de red definidos en el grupo. Después de definir un grupo de recursos compartidos de redes aquí, está disponible para usarse en las directivas que tienen como ámbito **dispositivos**. Consulte [Grupos de autorización del escenario 7](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) para obtener más información sobre cómo configurar acciones de directiva para usar grupos de autorización.

### <a name="vpn-settings-preview"></a>Configuración de VPN (versión preliminar)

Use la lista de VPN para controlar solo las acciones que se llevan a cabo a través de esa VPN.

Esta característica está disponible para dispositivos que ejecutan cualquiera de estas versiones de Windows:  
    
- Windows 10 y versiones posteriores (20H2, 21H1, 21H2) 
- Windows 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744)

Al enumerar una VPN en **configuración de VPN** , puede asignarles estas acciones de directiva:

- Permitir (auditoría sin notificaciones ni alertas de usuario)
- Solo auditoría (puede agregar notificaciones y alertas)
- Bloquear con invalidación (bloquea la acción, pero el usuario puede invalidarla)
- Bloquear (bloques independientemente de qué)

Estas acciones se pueden aplicar individual o colectivamente a estas actividades de usuario:

- Copiar en el portapapeles
- Copia en un dispositivo extraíble USB
- Copiar en un recurso compartido de red
- Imprimir
- Copiar o mover mediante una aplicación Bluetooth no permitida
- Copia o movimiento mediante RDP

Al configurar una directiva DLP para restringir la actividad en los dispositivos, puede controlar lo que sucede con cada actividad realizada cuando los usuarios están conectados a su organización dentro de cualquiera de las VPN enumeradas.

La VPN se define mediante estos parámetros **Dirección del servidor** o **Dirección de red**. 

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

> [!IMPORTANT]
> Cuando use la lista vpn para definir las acciones de una directiva, también verá **Red corporativa** como una opción. **Las conexiones de red corporativas** son todas conexiones a los recursos de la organización. Estas conexiones pueden incluir VPN. 

Consulte [Excepciones de red del escenario 8](endpoint-dlp-using.md#scenario-8-network-exceptions-preview)para obtener más información sobre cómo configurar acciones de directiva para usar excepciones de red.

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
