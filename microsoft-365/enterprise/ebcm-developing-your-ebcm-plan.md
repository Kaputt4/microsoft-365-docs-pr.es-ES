---
title: Aspectos a considerar para el plan de administración de la continuidad empresarial
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Aspectos que debe tener en cuenta a la hora de desarrollar un plan de continuidad empresarial preparado para la nube.
ms.openlocfilehash: 35aa5fb74b8281a089ef0b58998cd297507cc46f
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083522"
---
# <a name="developing-your-continuity-plan"></a>Desarrollo de un plan de continuidad

Este tema proporciona instrucciones para el desarrollo de un plan de continuidad empresarial que tenga en cuenta las dependencias de Microsoft 365. Aquí le recomendamos métodos para analizar las funciones de su empresa e identificar aquellas que dependen de los servicios de Microsoft 365. Realizará este análisis teniendo en cuenta que habrá errores de servicio y de que tiene que prepararse para las posibilidades.

En general, la planeación de la continuidad empresarial implica cuatro aspectos, la evaluación, la planificación, la validación de la capacidad, la comunicación y la coordinación.

## <a name="assessment"></a>Evaluación
En primer lugar, debe identificar las funciones empresariales de su organización y los servicios y procesos que las admiten. Esto incluye completar un análisis de impacto empresarial, donde cada función empresarial es clasificada según su importancia y usted identifica los procesos y servicios de los que depende cada una de ellas. Esta es una tabla de muestra que puede consultar para empezar a trabajar con su propia evaluación.

**Ejemplo de evaluación de impacto empresarial (BIA)**

Este es un documento BIA para `name of the service, system, process, or function`

|Campos del BIA|Descripción|
|---------|---------|
|Tipo de BIA|`is it a business process or technology, service or system?`|
|Nombre del BIA|`name of the service/system/function/process`|
|descripción del servicio|`give a full description of the service, process, or function`|
|función empresarial|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|año fiscal|`the current fiscal year, re-evaluate these on a regular basis`|
|importancia|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|unidad empresarial|`name of the business unit that owns this business function`|
|proceso (servicio, función)|`the name of the process, service, or feature`|
|alto dirigente del grupo empresarial|`the name and contact information of the senior leader of the business group that owns this business process`|
|¿Tiene la tecnología un SLA **interno** u OLA establecido?|`please explain in as much detail as possible`|
|¿Tiene la tecnología un SLA **externo** u OLA establecido?|`please explain in as much detail as possible`|
|¿Tiene la tecnología alguna orden ejecutiva conocida que impulse un SLA de procesos específico? Si es así, explíquelo detalladamente.|`details here`|
|¿La pérdida o la exposición de los datos asociados con estos servicios ocasionan un evento importante? Si es así, explíquelo detalladamente.|`details here`|
|¿El servicio tiene una solución alternativa u otras alternativas en lugar de algunas de las funciones y características fundamentales? Si es así, explíquelo detalladamente.|`details here`|
|¿Procesa, almacena o transmite el servicio datos de clientes, como información de identificación personal (PII)? Si es así, explíquelo detalladamente.|`details here`|
|Estado del BIA|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|Fecha de finalización|`the date this BIA was completed`|
|moderador del BIA|`name of the person or group who is responsible for developing and maintaining this BIA`|
|Aprobación del BIA|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|colaboradores|`optional list of the people who helped develop this BIA and their contact information`|
|Ubicación de aprobación del BIA|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Planificación

Después, busque en los procesos de negocios para ver dónde se encuentra cualquier relación de dependencia en cascada. Basándose en el resultado, priorice y cree estrategias de resiliencia y procedimientos de operación estándar que sean compatibles con dichas estrategias.

Puede usar [Microsoft Service Map](https://docs.microsoft.com/azure/azure-monitor/insights/service-map) para ayudarle con esta asignación. Microsoft Service Map descubre automáticamente los componentes de la aplicación en los sistemas Windows y Linux, asigna todas las dependencias TCP e identifica conexiones y sistemas de terceros remotos de los que depende la aplicación. Asimismo, asigna dependencias a áreas de la red que tradicionalmente son oscuras, como Active Directory.

Este es un análisis de dependencia de muestra (DA) desde el que puede empezar. En el análisis de dependencia (DA), debe identificar y examinar las dependencias del proceso. Asegúrese de incluir personas, proveedores, clientes, asociaciones y centros. Los datos de este análisis se usarán para identificar las diferencias entre los requisitos de recuperación de un proceso y las funcionalidades de recuperación de las dependencias de soporte.


|campo|description|
|---------|---------|
|tipo de proceso|         |
|moderador|         |
|completado por|         |
|fecha de finalización|         |
|colaboradores|         |
  
## <a name="capability-validation"></a>Capacidad de validación

Una vez que se han inventariado los procesos de negocio y se han trazado relaciones con otros procesos y tecnologías, es necesario crear escenarios de validación para todos los procesos. Básicamente, determinar cómo va a validar sus planes de continuidad del proceso empresarial. Probablemente encontrará que algunos son más importantes que otros y querrá priorizarlos.
No olvide que una vez establecido el plan, es importante capacitar regularmente a los empleados sobre las medidas de respuesta a incidentes y continuidad. Las revisiones posteriores a los incidentes deben utilizarse para mejorar sus estrategias de resiliencia incorporando los aprendizajes de cada validación o prueba.

![Capacidad de validación de visio](../media/ebcm/capability-validation-visio.png)

## <a name="incident-coordination-and-communication"></a>Coordinación y comunicación de incidentes

Durante un incidente de servicio, los canales de comunicación habituales pueden estar afectados o caídos, por lo que debe organizar previamente alternativas para ayudar a su organización a mantenerse conectada durante un incidente. Es fundamental establecer los canales de comunicación, verificar la seguridad y el cumplimiento, además de capacitar a los usuarios sobre su uso antes de que se produzcan interrupciones. Si se produce un error de un estado conocido a otro es mucho más aconsejable para los usuarios que presenten soluciones desconocidas ad-hoc en mitad de una urgencia

En Microsoft, cada equipo de servicio ha establecido canales de comunicación alternativos internos para ayudarnos a coordinarnos cuando nuestros canales de comunicación habituales no están disponibles. Entre estos, se incluyen soluciones de telefonía auxiliar y de audioconferencia, grupos de Yammer, grupos de Teams, paneles de estado del servicio interno y software de administración de incidentes internos.

Durante el análisis de impacto empresarial y el análisis de dependencia, estará asignando procesos importantes y las tecnologías o servicios de los que dependen. Preste especial atención a la comunicación durante esta fase de la planificación y piense en alternativas. A continuación se describen algunos ejemplos:

- Si el correo electrónico es el método principal para que los usuarios y las partes interesadas estén informados y el servicio de correo electrónico se cae o no está disponible, puede usar otro servicio como Microsoft Teams, Yammer u otro servicio de terceros como respaldo. La clave es establecerlos con anticipación y capacitar a sus usuarios para que sepan qué hacer. Una conversación de Yammer no será útil si nadie sabe que existe o si nadie lo tiene.  
- Si los procesos internos de la administración de incidentes dependen en las comunicaciones de voz para coordinar sus respuestas, establezca una solución de telefonía alternativa para usarla durante una urgencia. En esta solución no es necesario tener paridad completa con el servicio principal, pero se debe proporcionar el nivel mínimo de colaboración para coordinar los equipos de administración de incidentes y continuidad empresarial. Además, preguntar a los usuarios para publicar sus números de teléfono móvil en la lista global de direcciones puede ofrecer un nivel adicional de comunicación auxiliar en casos extremos.
- Es posible que desee crear un panel personalizado de estado del servicio, u otro tipo de sitio, que pueda proporcionar actualizaciones de estado durante un incidente. Capacitar a los usuarios sobre a dónde acudir para obtener información de antemano ayudará a reducir las llamadas innecesarias al departamento de soporte técnico e infundirá la seguridad en su lista de usuarios de que la situación se está manejando de manera rápida y eficiente. Utilice la API de comunicaciones de servicio O365 para vincularla al M365 y obtener un nivel de visibilidad aún mayor.  
- Es fundamental que se conozca la ubicación de los planes de continuidad empresarial y los procedimientos de operación estándar. Recomendamos mantener copias de la documentación importante en línea y fuera de línea, por ejemplo con SharePoint Online o OneDrive empresarial configurado para la sincronización automática con dispositivos locales. Para los Centros de Operaciones de Servicio/Red y otros equipos similares que serán absolutamente importantes para la recuperación, es posible que también desee mantener copias impresas disponibles para ser utilizadas en caso de emergencia.

## <a name="know-your-external-points-of-integration"></a>Se conocen los puntos de integración externos

Independientemente del modelo empresarial, cada empresa tiene puntos de integración con sus clientes, asociados y proveedores. La cadena de suministro de valor empresarial se basa en la integración con entidades externas. Mejorar la continuidad empresarial en caso de interrupción del servicio requiere la consideración, y protección, de cada punto de integración.  
Al analizar su cadena de suministro, las comunicaciones externas deben considerarse de la misma manera que las comunicaciones internas. ¿Los clientes dependen de sus servidores de Exchange online como único método para ponerse en contacto con usted? ¿Se ha determinado y ha comprobado que sus proveedores conocen métodos de comunicación alternativos en caso de que se produzcan impactos en los eventos? Aquí tiene una tabla de ejemplo que sugiere cómo organizar su idea.

|nombre de la entidad externa|escenario del incidente impactante|Servicios Microsoft 365 integrados|alternativas|
|---------|---------|---------|---------|
|`vendor name`|flujo de correo|Exchange Online es el único medio de comunicación con Contoso|Configure canales externos de Microsoft Teams o un software de colaboración de terceros          |
|`service supplier name`|chat|Microsoft Teams|mensajería instantánea de terceros|
|`partner name`|voz|Microsoft Teams|RTC móviles o públicos      |
|`supplier name`|uso compartido de archivos|sitios de SharePoint y OneDrive compartidos externamente|uso compartido de archivos de terceros         |
