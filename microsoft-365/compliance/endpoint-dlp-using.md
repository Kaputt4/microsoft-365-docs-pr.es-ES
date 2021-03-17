---
title: Uso de la prevención de perdida de datos en punto de conexión
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Aprenda cómo configurar las directivas de prevención de pérdida de datos (DLP) para usar las ubicaciones de la Prevención de pérdida de datos de los puntos de conexión (EPDLP) de Microsoft 365.
ms.openlocfilehash: 1bb4013069b8f4890ba420f13a0203eb63973121
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820192"
---
# <a name="using-endpoint-data-loss-prevention"></a>Uso de la prevención de pérdida de datos en punto de conexión

Este artículo le guiará a través de tres escenarios donde puede crear y modificar una directiva DLP que use dispositivos como una ubicación.

## <a name="dlp-settings"></a>Configuración DLP

Antes de empezar, configure las opciones de configuración DLP que se aplican a todas las directivas DLP para dispositivos. Debe configurarlas si tiene previsto crear directivas que cumplan con lo siguiente:

- restricciones de salida de la nube
- restricciones de aplicaciones no permitidas

O bien

- Si desea excluir de la supervisión las rutas de archivo ruidosas

  > [!div class="mx-imgBorder"]
  > ![Configuración DLP](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>Exclusiones de ruta de archivo

Es posible que quiera excluir determinadas rutas de supervisión DLP, alertas DLP y aplicación de directivas DLP en sus dispositivos, ya sea porque tienen demasiado ruido o no contienen archivos que le interesan. Los archivos en esas ubicaciones no se auditarán y los archivos que se creen o modifiquen en esas ubicaciones no se someterán a la aplicación de directivas DLP. Puede configurar exclusiones de ruta en configuración DLP.

Puede usar esta lógica para crear sus rutas de exclusión:

- Una ruta de archivo es válida cuando termina en "\". Esto incluye solo a los archivos que se encuentran directamente dentro de la carpeta. <br/>Por ejemplo: C:\Temp\

- Una ruta de archivo es válida cuando termina en "\*". Esto incluye solo a los archivos que se encuentran dentro de las subcarpetas, además de los archivos ubicados directamente dentro de la carpeta. <br/>Por ejemplo: C:\Temp\*

- Una ruta de archivo es válida cuando termina sin "\" o "\*". Esto incluye a todos los archivos que se encuentran directamente dentro de la carpeta o subcarpetas. <br/>Por ejemplo: C:\Temp

- Una ruta con comodín con "\" en cada lado. <br/>Por ejemplo: C:\Usuarios\*\Escritorio\

- Una ruta con comodín con "\" en cada lado y con "(número)" para dar un número exacto de subcarpetas. <br/>Por ejemplo: C:\Usuarios\*(1)\Descargas\

- Una ruta con variables de entorno del SISTEMA. <br/>Por ejemplo: %SystemDrive%\Test\*

- Una combinación de todas las anteriores. <br/>Por ejemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub\

### <a name="unallowed-apps"></a>Aplicaciones no permitidas

Cuando la configuración de **Acceso por aplicaciones y exploradores no permitidos** de una directiva esté activada y los usuarios intenten usar estas aplicaciones para acceder a un archivo protegido, la actividad se permitirá, se bloqueará, o se bloqueará pero los usuarios podrán invalidar la restricción. Toda actividad es auditada y está disponible para su revisión en el explorador de actividades.

> [!IMPORTANT]
> No incluya la ruta de acceso al archivo ejecutable, solo el nombre del archivo ejecutable (por ejemplo, browser.exe).


### <a name="browser-and-domain-restrictions"></a>Restricciones del dominio y del explorador:
Restrinja el uso compartido de los archivos confidenciales que coincidan con las directivas con dominios de servicio en la nube sin restricciones.

#### <a name="service-domains"></a>Dominios de servicio

Puede controlar si los archivos confidenciales protegidos por sus directivas se pueden cargar en dominios de servicio específicos de Microsoft Edge.

Si el modo de lista está configurado en **Bloquear**, el usuario no podrá cargar elementos confidenciales a esos dominios. Cuando se bloquea una acción de carga porque un elemento coincide con una directiva DLP, la DLP genera una advertencia o bloquea la carga del elemento confidencial.

Si el modo de lista está configurado en **Permitir**, los usuarios podrán cargar elementos confidenciales **_solo_** a dichos dominios y no se permitirá el acceso de carga a los demás dominios.

> [!IMPORTANT]
> Cuando el modo de restricción del servicio esté establecido en "Permitir", debe tener al menos un dominio de servicio configurado antes de que las restricciones se apliquen.

#### <a name="unallowed-browsers"></a>Exploradores no permitidos

Agregue exploradores, identificados por sus nombres ejecutables, que no tendrán acceso a los archivos que cumplan las condiciones de una directiva DLP aplicada cuya restricción de carga a servicios en la nube esté configurada para bloquearse o bloquear una invalidación. Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Edge Chromium.

### <a name="business-justification-in-policy-tips"></a>Justificaciones empresariales en sugerencias de directivas

Puede controlar cómo interactúan los usuarios con la opción de justificación empresarial en las notificaciones de sugerencias de directiva DLP. Esta opción aparece cuando los usuarios realizan una actividad que está protegida por la configuración **Bloquear con anulación** en una directiva DLP. Puede elegir entre una de las siguientes opciones:

- De forma predeterminada, los usuarios pueden seleccionar una justificación integrada o introducir su propio texto.
- Los usuarios solo pueden seleccionar una justificación integrada.
- Los usuarios solo pueden introducir su propia justificación.


## <a name="tying-dlp-settings-together"></a>Vincular las opciones de configuración DLP

Con la DLP de los puntos de conexión y el Explorador web Edge Chromium, puede restringir el uso compartido no intencionado de elementos confidenciales a las aplicaciones y servicios en la nube no permitidos. Edge Chromium comprende cuándo un elemento está restringido por una directiva DLP de los puntos de conexión y aplica las restricciones de acceso.

Cuando usa la DLP de los puntos de conexión como una ubicación en una directiva DLP configurada correctamente y en el explorador Edge Chromium, los exploradores no permitidos que haya definido en esta configuración no tendrán acceso a los elementos confidenciales que coincidan con los controles de la directiva DLP. En su lugar, los usuarios serán redirigidos para usar Edge Chromium y Edge Chromium, con su reconocimiento de las restricciones impuestas por DLP, podrá bloquear o restringir actividades cuando se cumplan las condiciones de la directiva DLP.

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
>- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
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
   > ![configurar bloqueo con acción de invalidación](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. Seleccione **Guardar**.

7. Repita los pasos del 4 al 7 para el **Alto volumen de contenido detectado en la información de identificación personal de Estados Unidos**.

8. Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.

9. Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización. Esto debería activar la directiva.

   Verá un elemento emergente como el siguiente en el dispositivo cliente:

   > [!div class="mx-imgBorder"]
   > ![notificación de invalidación de cliente bloqueado por dlp en punto de conexión](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Compruebe que el evento se encuentre en el Explorador de actividades.

## <a name="see-also"></a>Consulte también

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/)
- [Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Unido a Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Descargue el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
