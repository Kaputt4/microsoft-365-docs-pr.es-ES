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
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Obtenga información sobre cómo definir la configuración central de prevención de pérdida de datos en el punto de conexión (DLP).
ms.openlocfilehash: edf5d42421aa9fb0c54d0121655e3a31d4a729f6
ms.sourcegitcommit: 1c8f54f9e7a7665bc10b5ef4a3d8c36e3e48f44c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "66078774"
---
# <a name="configure-endpoint-data-loss-prevention-settings"></a>Configuración de la prevención de pérdida de datos de punto de conexión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Muchos aspectos del comportamiento de prevención de pérdida de datos (DLP) en el punto de conexión se controlan mediante opciones configuradas de forma centralizada. La configuración se aplica a todas las directivas DLP para dispositivos.

![Configuración de DLP de punto de conexión](../media/endpoint-dlp-1-using-dlp-settings.png)

Debe configurar estas opciones si desea controlar:

- Restricciones de salida en la nube
- Varios tipos de acciones restrictivas en las actividades de usuario por aplicación.
- Exclusiones de ruta de acceso de Windows y dispositivos macOS.
- Restricciones de explorador y dominio.
- Cómo aparecen las justificaciones empresariales para invalidar directivas en las sugerencias de directiva.
- Si las actividades en archivos de Office, PDF y CSV se auditan automáticamente.

## <a name="dlp-settings"></a>Configuración DLP

Antes de empezar, debe configurar la configuración de DLP. 

### <a name="endpoint-dlp-windows-1011-and-macos-settings"></a>Configuración de Windows 10/11 DLP de punto de conexión y macOS

|Setting |Windows 10, 1809 y versiones posteriores, Windows 11  |macOS Catalina 10.15 o posterior |Notas  |
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

El escaneo y la protección de clasificación avanzada permiten que el servicio de clasificación de datos basado en la nube de Microsoft Purview, más avanzado, escanee elementos, los clasifique y devuelva los resultados a la máquina local. Esto significa que puede aprovechar técnicas de clasificación como [coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) clasificación, [entidades con nombre](named-entities-learn.md)y [clasificadores capacitados](classifier-learn-about.md) en las directivas DLP.

Cuando se activa la clasificación avanzada, el contenido se envía desde el dispositivo local a los servicios en la nube para su examen y clasificación. Si el uso de ancho de banda supone un problema, puede establecer un límite en lo que concierne a cuánto se puede usar en un período de 24 horas. El límite se define en la configuración de DLP de punto de conexión y se aplica por dispositivo. Si establece un límite de uso de ancho de banda y se supera, DLP deja de enviar el contenido del usuario a la nube. En este momento, la clasificación de datos continúa localmente en el dispositivo, pero la clasificación con coincidencia exacta de datos, entidades con nombre y clasificadores capacitados no está disponible. Cuando el uso del ancho de banda acumulado se encuentre por debajo del límite de 24 horas, se reanudará la comunicación con los servicios en la nube.

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

- Ruta de acceso de archivo válida que termina con `\*`, lo que significa solo archivos en subcarpetas, además de los archivos directamente debajo de la carpeta. <br/>Por ejemplo: `C:\Temp\*`

- Ruta de acceso de archivo válida que termina sin `\` o `\*`, lo que significa todos los archivos que se encuentran directamente en la carpeta y en todas las subcarpetas. <br/>Por ejemplo: `C:\Temp`

- Ruta de acceso con comodín entre `\` de cada lado. <br/>Por ejemplo: `C:\Users\*\Desktop\`

- Ruta de acceso con comodín entre `\` de cada lado y con `(number)` para proporcionar el número exacto de subcarpetas. <br/>Por ejemplo: `C:\Users\*(1)\Downloads\`

- Una ruta con variables de entorno del SISTEMA. <br/>Por ejemplo: `%SystemDrive%\Test\*`

- Una combinación de todas las anteriores. <br/>Por ejemplo: `%SystemDrive%\Users\*\Documents\*(2)\Sub\`

#### <a name="macos-devices"></a>dispositivos macOS

Al igual que los dispositivos Windows 10, puede agregar sus propias exclusiones para dispositivos macOS.

- Las definiciones de ruta de acceso del archivo no distinguen mayúsculas de minúsculas, por lo que `User` es igual que `user`.

- Se admiten valores de carácter comodín. Por lo tanto, una definición de ruta de acceso puede contener un `*` a la mitad o al final de la ruta de acceso. Por ejemplo: `/Users/*/Library/Application Support/Microsoft/Teams/*`

#####  <a name="recommended-file-path-exclusions-preview"></a>Exclusiones recomendadas de ruta de acceso del archivo (versión preliminar)

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

Si Notepad.exe se agrega a **Aplicaciones restringidas** y la opción **Actividades de archivo para todas las aplicaciones** está configurada para **Aplicar restricciones a actividades específicas** y ambas se configuran de esta forma:

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

Si una aplicación no está en **Actividades de archivo para aplicaciones en grupos de aplicaciones restringidos** o no está en la lista **Actividades de aplicaciones restringidas** o bien está en la lista **Actividades de aplicaciones restringidas** con una acción de `Audit only` o "Bloquear con invalidación", las restricciones definidas en **Actividades de archivo para todas las aplicaciones** se aplican en la misma regla.  

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

Para los dispositivos de Windows, agregue exploradores, identificados por sus nombres ejecutables, que no tendrán acceso a los archivos que cumplan las condiciones de una directiva DLP aplicada cuya restricción de carga a servicios en la nube esté configurada para bloquearse o bloquear una invalidación. Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Microsoft Edge.

Para dispositivos macOS, debe agregar la ruta de acceso de archivo completa. Para encontrar la ruta de acceso completa de las aplicaciones de Mac:

1. En el dispositivo macOS, abra **Monitor de actividad**. Buscar y hacer doble clic en el proceso que desea restringir

2. Elija la pestaña **Abrir Archivos y Puertos**.
  
3. Para las aplicaciones de macOS, se necesita el nombre completo de la ruta de acceso, incluido el nombre de la aplicación.

#### <a name="service-domains"></a>Dominios de servicio

> [!NOTE]
> La configuración de **Dominios de servicio** solo se aplica a los archivos cargados con Microsoft Edge o Google Chrome con la [extensión Microsoft Purview](dlp-chrome-learn-about.md#learn-about-the-microsoft-purview-extension) instalada.

Puede controlar si los archivos confidenciales protegidos por sus directivas se pueden cargar en dominios de servicio específicos de Microsoft Edge.

Si el modo de lista está configurado en **Bloquear**, el usuario no podrá cargar elementos confidenciales a esos dominios. Cuando se bloquea una acción de carga porque un elemento coincide con una directiva DLP, la DLP genera una advertencia o bloquea la carga del elemento confidencial.

Si el modo de lista está configurado en **Permitir**, los usuarios podrán cargar elementos confidenciales **_solo_** a dichos dominios y no se permitirá el acceso de carga a los demás dominios.

> [!IMPORTANT]
> Cuando el modo de restricción del servicio esté establecido en "Permitir", debe tener al menos un dominio de servicio configurado antes de que las restricciones se apliquen.

Usar el formato FQDN del dominio de servicio sin el final `.` 

Por ejemplo:

 `www.contoso.com` 

No se admiten los caracteres comodín.

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
