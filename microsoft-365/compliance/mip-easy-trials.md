---
title: Obtenga información sobre las etiquetas y directivas predeterminadas para Microsoft Information Protection
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
description: Obtenga información sobre las etiquetas y directivas predeterminadas para Microsoft Information Protection (MIP) para clasificar y proteger el contenido confidencial.
ms.openlocfilehash: dd9a2eef45e8ccb7ecb9c637a94f64ad6796a8f9
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221357"
---
# <a name="default-labels-and-policies-for-microsoft-information-protection"></a>Etiquetas y directivas predeterminadas para Microsoft Information Protection

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Los clientes elegibles pueden activar las etiquetas y directivas predeterminadas para Microsoft Information Protection (MIP): 

- Etiquetas de confidencialidad y una directiva de etiquetas de confidencialidad
- Etiquetado automático del lado cliente
- Etiquetado automático del lado servicio
- Directivas de prevención de pérdida de datos (DLP) para Teams y dispositivos

Estas configuraciones predeterminadas le ayudarán a comenzar a trabajar rápidamente con Microsoft Information Protection del Centro de cumplimiento de Microsoft 365. Puede usarlos tal y como están, realizar solo algunos cambios o personalizarlos completamente para que se adapten mejor a sus requisitos empresariales. 

La elegibilidad incluye a aquellos clientes que tengan una [prueba gratuita del Centro de cumplimiento de Microsoft 365](compliance-easy-trials.md) y a algunos clientes que ya tengan un plan de Microsoft 365 E5:

- **Nuevos clientes**: si ha tenido el Centro de cumplimiento de Microsoft 365 durante menos de 30 días, el inquilino puede activar todas las configuraciones predeterminadas listadas. Siempre puede deshabilitarlas, quitarlas o editarlas.

- **Clientes existentes**: si ha tenido el Centro de cumplimiento de Microsoft 365 durante más de 30 días, puede activar las configuraciones predeterminadas si aún no ha configurado una equivalente:

    | Configuración predeterminada| Equivalente |
    |:-----|:-----|
    |Etiquetas de confidencialidad y una directiva de etiquetas de confidencialidad | Etiquetas de confidencialidad publicadas |
    |Etiquetado automático del lado cliente | Una o más etiquetas de confidencialidad configuradas para aplicar automáticamente (o recomendar a los usuarios) en las aplicaciones de Office|
    |Etiquetado automático del lado servicio | Al menos una directiva de etiquetado automático activada|
    |DLP para Teams | Al menos una directiva DLP para Teams|
    |DLP para dispositivos | Al menos una directiva DLP para dispositivos|

## <a name="activate-the-default-labels-and-policies"></a>Activar las directivas y etiquetas predeterminadas

Para obtener estas directivas y etiquetas preconfiguradas: 

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Soluciones** > **Protección de información**
    
    Si no ve esta opción inmediatamente, seleccione primero **Mostrar todo** en el panel de navegación. 
    
2. Si es elegible para las etiquetas y directivas predeterminadas de Microsoft Information Protection, verá la siguiente información, donde puede activar las etiquetas y directivas predeterminadas. Por ejemplo:
    
    :::image type="content" alt-text="Activación de Microsoft Information Protection para etiquetas y directivas preconfiguradas." source="../media/mip-preconfigured.png" lightbox="../media/mip-preconfigured.png":::
    
    Si no ve esta información mostrada con la opción de activación, actualmente no es apto para la creación automática de etiquetas y directivas de confidencialidad. Puede intentar volver a comprobarlo más tarde para ver si este estado ha cambiado o puede usar la información de configuración siguiente para crear manualmente las mismas etiquetas y directivas.

3. Ahora, habilite las etiquetas de confidencialidad para SharePoint y OneDrive. Este paso adicional es un requisito previo para usar etiquetas de confidencialidad en Office para la Web y directivas de etiquetado automático para SharePoint y OneDrive.

    Seleccione la pestaña **Etiquetas** y, a continuación, **Activar ahora**.
    
    Para obtener instrucciones completas, vea [Cómo habilitar etiquetas de confidencialidad para SharePoint y OneDrive (participar)](sensitivity-labels-sharepoint-onedrive-files.md#how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in).

## <a name="default-sensitivity-labels"></a>Etiquetas de confidencialidad predeterminadas

Cuando no tenga etiquetas de confidencialidad que estén publicadas, le crearemos las siguientes etiquetas:


|Nombre de la etiqueta|Etiqueta de descripción para usuarios|Configuraciones|
|-------------------------------|---------------------------|-----------------|
|Personal|Datos no empresariales, únicamente para uso personal.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Público|Datos profesionales preparados y aprobados específicamente para consumo público.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|General|Datos empresariales que no están destinados a uso público. Sin embargo, esto se puede compartir con asociados externos, según sea necesario. Algunos ejemplos incluyen un directorio telefónico interno de la empresa, gráficos organizativos, estándares internos y la mayoría de las comunicaciones internas.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|General <br /> \ Cualquier usuario (sin restricciones)|Datos de la organización que no están destinados al uso público pero que se pueden compartir con asociados externos si procede. Algunos ejemplos incluyen conversaciones de clientes que no incluyen información confidencial ni materiales de marketing publicados.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|General <br /> \ Todos los empleados (sin restricciones)|Datos de la organización que no están destinados al uso público. Si necesita compartir este contenido con socios externos, confirme con otros propietarios de datos que está bien compartir y, a continuación, cambie la etiqueta a General \ Cualquier usuario (sin restricciones). Algunos ejemplos incluyen un directorio telefónico interno de la empresa, gráficos organizativos, estándares internos y la mayoría de las comunicaciones internas.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Confidencial|Datos empresariales confidenciales que podrían causar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: contratos, informes de seguridad, resúmenes de previsión y datos de la cuenta de ventas.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: no<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Confidencial <br /> \ Cualquier usuario (sin restricciones)|Datos confidenciales que no necesitan cifrarse. Use esta opción con cuidado y justificación empresarial adecuada.|Esta etiqueta está seleccionada para el [etiquetado automático del lado cliente](#client-side-auto-labeling) y el [etiquetado automático del lado servicio](#service-side-auto-labeling).<br /><br /> **Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: Pie de página: clasificado como confidencial<br /><br />**Etiquetado automático**: se recomienda que los usuarios apliquen la etiqueta <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Confidencial <br /> \ Todos los empleados|Datos confidenciales que necesitan protección, lo que concede a todos los empleados permisos totales. Los propietarios de datos pueden realizar un seguimiento del contenido y revocarlo.|Esta etiqueta está seleccionada para el [etiquetado automático del lado cliente](#client-side-auto-labeling) y el [etiquetado automático del lado servicio](#service-side-auto-labeling).<br /><br /> **Ámbito**: archivo, correo electrónico <br /><br />**Cifrado**: todos los usuarios y grupos de la organización: trabajar en coautoría<br /><br />**Marcado de contenido**: Pie de página: clasificado como confidencial<br /><br />**Etiquetado automático**: se recomienda que los usuarios apliquen la etiqueta <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no |
|Confidencial <br /> \ Personas de confianza|Datos confidenciales que se pueden compartir con personas de confianza dentro y fuera de la organización. Estas personas también pueden volver a compartir los datos según sea necesario.|**Ámbito**: archivo, correo electrónico <br /><br />**Cifrado**: permite a los usuarios asignar permisos: <br /> - Solo cifrar para Outlook <br />- Solicitar a los usuarios en Word, PowerPoint y Excel<br /><br />**Marcado de contenido**: Pie de página: clasificado como confidencial<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Extremadamente confidencial|Datos empresariales extremadamente confidenciales que podrían provocar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: información de empleados y clientes, contraseñas, código fuente e informes financieros previamente anunciados.|**Ámbito**: archivo, correo electrónico <br /><br />**Marcado de contenido**: marca de agua: ALTAMENTE CONFIDENCIAL<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Extremadamente confidencial <br /> \ Todos los empleados|Datos extremadamente confidenciales que permiten a todos los empleados ver, editar y responder permisos a este contenido. Los propietarios de datos pueden realizar un seguimiento del contenido y revocarlo.|**Ámbito**: archivo, correo electrónico <br /><br />**Cifrado**: todos los usuarios y grupos de la organización: trabajar en coautoría<br /><br />**Marcado de contenido**: pie de página: clasificado como extremadamente confidencial<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|
|Extremadamente confidencial <br /> \ Personas específicas |Datos extremadamente confidenciales que requieren protección y que solo pueden ser vistos por las personas que especifique y con el nivel de permisos que elija.|**Ámbito**: archivo, correo electrónico <br /><br />**Cifrado**: permite a los usuarios asignar permisos: <br />- No reenviar para Outlook <br />- Solicitar a los usuarios en Word, PowerPoint y Excel<br /><br />**Marcado de contenido**: pie de página: clasificado como extremadamente confidencial<br /><br />**Etiquetado automático**: no <br /><br />**Configuración de grupo**: no<br /><br />**Configuración del sitio**: no <br /><br />**Etiquetado automático para las columnas de base de datos**: no|

> [!NOTE]
> Los nombres y descripciones de las etiquetas están disponibles automáticamente para las siguientes configuraciones regionales: inglés de los Estados Unidos, chino simplificado y tradicional, francés, alemán, italiano, japonés, coreano, portugués brasileño, ruso y español.
> 
> Si necesita idiomas adicionales, puede especificar las traducciones [con PowerShell](create-sensitivity-labels.md#example-configuration-to-configure-a-sensitivity-label-for-different-languages).

Para obtener más información acerca de estas opciones de configuración y qué pueden hacer las etiquetas de confidencialidad, consulte [Qué pueden hacer las etiquetas de confidencialidad](sensitivity-labels.md#what-sensitivity-labels-can-do).

Si necesita editar estas etiquetas de confidencialidad predeterminadas, consulte [Crear y configurar etiquetas de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).

## <a name="default-sensitivity-label-policy"></a>Directiva de etiqueta de confidencialidad predeterminada

La directiva de etiqueta de confidencialidad predeterminada hace que las etiquetas estén disponibles para que los usuarios comiencen a etiquetar sus documentos y correos electrónicos con etiquetas de confidencialidad. Tiene la siguiente configuración:

- Publicar las etiquetas predeterminadas para todos los usuarios del espacio empresarial
- Etiqueta predeterminada de **General** \ **Todos los empleados (sin restricciones)** para documentos y correos electrónicos sin etiquetar
- Los usuarios deben proporcionar una justificación para quitar una etiqueta o rebajar su clasificación

Para obtener más información acerca de estas configuraciones de directiva y otras opciones de directiva disponibles, consulte [Qué pueden hacer las directivas de etiquetas](sensitivity-labels.md#what-label-policies-can-do).

Si necesita editar esta configuración de directivas predeterminadas, consulte [Publicar etiquetas de confidencialidad mediante la creación de una directiva de etiquetas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

Al usar estas etiquetas en aplicaciones de Office en Windows, macOS, iOS y Android, los usuarios verán nuevas etiquetas en un plazo de cuatro horas y en una hora para Word, Excel y PowerPoint en la Web al actualizar el explorador. Sin embargo, podría necesitar dar un margen de 24 horas para que los cambios realizados se apliquen a los usuarios y servicios.

## <a name="client-side-auto-labeling"></a>Etiquetado automático del lado cliente

La configuración predeterminada de etiquetado automático del lado cliente recomienda a los usuarios aplicar una etiqueta de confidencialidad cuando se detectan números de tarjeta de crédito en documentos o correos electrónicos con los que están trabajando. Como recomendación, en lugar de aplicarse automáticamente, esta configuración sirve como un buen primer paso para resaltar contenido importante e introduce a los usuarios a la práctica de etiquetar sus documentos y correos electrónicos.

El etiquetado automático del lado cliente solo funciona para documentos y correos electrónicos en uso por las aplicaciones de Office Word, Excel, PowerPoint y Outlook. 

El etiquetado automático predeterminado del lado cliente tiene la siguiente configuración: 

- Si hay de 1 a 9 instancias de números de tarjeta de crédito que se encuentren en un documento o correo electrónico, recomendamos que el usuario aplique la etiqueta de confidencialidad **Confidencial** \ **Cualquier usuario (sin restricciones)** 

- Si hay 10 o más instancias de números de tarjeta de crédito que se encuentren en un documento o correo electrónico, recomendamos que el usuario aplique la etiqueta de confidencialidad **Confidencial** \ **Todos los empleados** 

> [!NOTE]
> Si detectamos que tiene sus propias etiquetas de confidencialidad publicadas, le pediremos que seleccione una de sus propias etiquetas para el etiquetado automático para configurarla automáticamente.

Si quiere editar la configuración de etiquetado automático del lado cliente, consulte [Cómo configurar el etiquetado automático para aplicaciones de Office](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps).

## <a name="service-side-auto-labeling"></a>Etiquetado automático del lado servicio 

El etiquetado automático del lado servicio ayuda a etiquetar documentos confidenciales en reposo y correos electrónicos en tránsito. La directiva de etiquetado automático predeterminada del lado servicio crea una directiva en modo de simulación para los documentos almacenados en todos los sitios de SharePoint o OneDrive y en todos los correos electrónicos que se envían a través de Exchange Online. En el modo de simulación, los elementos no se etiquetan realmente hasta que se activa la directiva. El modo de simulación le permite obtener una vista previa de los elementos que se etiquetarían si la directiva estuviera activada, por lo que usted adquiere confianza en la característica de etiquetado antes de que implemente la directiva en el espacio empresarial para el etiquetado real. 

El etiquetado automático predeterminado del lado servicio tiene la siguiente configuración: 

- Si hay entre 1 y 9 instancias de números de tarjeta de crédito que se encuentran en un documento, aplique la etiqueta de confidencialidad **Confidencial** \ **Cualquier usuario (sin restricciones)**

- Si hay 10 o más instancias de números de tarjeta de crédito que se encuentren en un documento o correo electrónico, recomendamos que el usuario aplique la etiqueta de confidencialidad **Confidencial** \ **Todos los empleados** 

> [!NOTE]
> Si detectamos que tiene sus propias etiquetas de confidencialidad publicadas, le pediremos que seleccione una de sus propias etiquetas para su directiva de etiquetado automático.

Una vez completada la simulación, revise los resultados y, si está contento con ellos, active la directiva.

Para obtener más información sobre el modo de simulación, consulte [Más información sobre el modo de simulación](apply-sensitivity-label-automatically.md#learn-about-simulation-mode).

Si desea editar la directiva de etiquetado automático del lado servicio, consulte [Cómo configurar las directivas de etiquetado automático para SharePoint, OneDrive y Exchange](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

## <a name="dlp-for-teams"></a>DLP para Teams

La directiva DLP predeterminada para Teams detecta la presencia de números de tarjeta de crédito en todos los chat de Teams y los mensajes de canal. Cuando se detecte esta información confidencial, los administradores recibirán una notificación de alerta de gravedad baja.

Esta directiva es discreta para los usuarios sin ninguna sugerencia de directiva visible y sin mensajes bloqueados, pero los administradores tendrán registros de la información confidencial compartida en estos mensajes. Si es necesario, puede editar la configuración para cambiar esta configuración predeterminada.

Para ver los resultados de esta directiva, use el [explorador de actividad de DLP](dlp-learn-about-dlp.md#dlp-activity-explorer).

Si desea editar la directiva DLP, consulte [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md).

## <a name="dlp-for-devices"></a>DLP para dispositivos

La directiva DLP predeterminada para dispositivos detecta la presencia de números de tarjeta de crédito en dispositivos Windows 10 que se hayan incorporado al Centro de cumplimiento de Microsoft 365. A continuación, audita (no bloquea) las siguientes acciones: 

- Cargar en dominios de servicios en la nube o acceder a través de exploradores no permitidos

- Copiar en el portapapeles, USB o recurso compartido de red 

- Acceso de aplicaciones no permitidas 

- Imprimir 

- Copiar o mover mediante una aplicación Bluetooth no permitida 

- Servicios de Escritorio remoto 

Si el contenido contiene 10 o más instancias de tarjetas de crédito y se detecta una o varias de las actividades enumeradas, se envía una notificación de alerta de gravedad media a los administradores.

Esta directiva es discreta para los usuarios sin ninguna sugerencia de directiva visible y sin acciones bloqueadas, pero los administradores tendrán registros de toda actividad sospechosa. Si es necesario, puede editar esta configuración para cambiar esta configuración predeterminada.

Para ver los resultados de esta directiva, use el [explorador de actividad de DLP](dlp-learn-about-dlp.md#dlp-activity-explorer).

Si desea editar la directiva DLP, consulte [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md).

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información sobre las etiquetas de confidencialidad, la prevención de pérdida de datos y todas las funcionalidades disponibles de Microsoft Information Protection, consulte los siguientes recursos:

- [Obtener más información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Microsoft Information Protection en Microsoft 365.](information-protection.md)
