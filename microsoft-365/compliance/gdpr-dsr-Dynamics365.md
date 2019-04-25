---
title: Solicitudes del titular de los datos de Microsoft Dynamics 365 para el RGPD
description: Guía sobre cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar y actuar en datos personales con el fin de responder a las solicitudes de derechos del titular de los datos.
keywords: Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/10/2019
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: f5a7f347dc9b26b54cf6bc1fd3a6bdb55d46fe63
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285219"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>Solicitudes del titular de los datos de Microsoft Dynamics 365 para el RGPD

El Reglamento de protección de datos de la UE (RGPD) ofrece derechos a las personas (que en el reglamento se denominan *“titulares de los datos”*) para procesar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *poseedor de los datos* o *“poseedor”*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los titulares de los datos derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, la restricción de su procesamiento o eliminación, así como el envío en formato electrónico para su transferencia a otro poseedor de los datos. Las solicitudes formales realizadas por un titular de los datos a un poseedor de los datos para realizar una acción en sus datos personales se denominan en este documento *solicitudes de derechos del titular de los datos* o solicitudes del titular de los datos.<span id="_Toc510437912" class="anchor"><span id="_Toc508792504" class="anchor"></span></span>

En esta guía, se explica cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar y actuar sobre datos personales con el fin responder a las solicitudes de derechos del titular de los datos. En concreto, se explica cómo encontrar, obtener acceso y actuar sobre datos personales que residen en la nube de Microsoft. Aquí encontrará un resumen rápido de los procedimientos descritos en esta guía:

1. ***Detección***: use herramientas de búsqueda y detección para encontrar con facilidad datos de clientes que puedan ser el objeto de una solicitud de derechos del titular de los datos. Después de recopilar los documentos que puedan ser el objeto de una solicitud, puede realizar una o varias de las acciones de solicitud de derechos del titular de los datos descritas en los pasos siguientes para responder a la petición. Como alternativa, puede determinar que la solicitud no cumple las directrices de respuesta a solicitudes de derechos del titular de los datos.

2. ***Acceso***: recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.

3. ***Rectificación***: realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.

4.  ***Restricción***: restrinja el tratamiento de datos personales, ya sea al quitar las licencias de distintos servicios en línea o al desactivar los servicios que quiera, siempre que sea posible. También puede quitar los datos de la nube de Microsoft y conservarlos de forma local o en otra ubicación.

5. ***Eliminación***: elimine de forma permanente los datos personales que residen en la nube de Microsoft.

6. ***Exportación***: envíe una copia electrónica (en un formato de lectura mecánica) de datos personales al titular de los datos.

En cada sección de esta guía, se describen los procedimientos técnicos que puede realizar una organización poseedora de los datos para responder a una solicitud de derechos del titular de los datos personales en la nube de Microsoft.

### <a name="gdpr-terminology"></a>Terminología del RGPD

Estas son las definiciones de los términos relacionados con esta guía:

- <em>Poseedor</em>: la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.

- *Datos personales* y <em>titular de los datos</em>: cualquier información sobre una persona física identificada o identificable (“titular de los datos”); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.

- <em>Procesador</em>: persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.

- *Datos de cliente*: todos los datos (incluidos todos los archivos de texto, sonido, vídeo o imagen, y software) proporcionados a Microsoft por un cliente (o en su representación) mediante el uso del servicio empresarial, según se define en los Términos de Microsoft Online Services.

- *Registros* *generados por el sistema*: registros y datos relacionados generados por Microsoft que permiten a Microsoft prestar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos anonimizados parcialmente, como identificadores únicos (por lo general, un número generado por el sistema que no se puede usar para identificar a una persona, pero que se usa para prestar servicios empresariales a los usuarios). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.  

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Modo en que esta guía puede servir para cumplir sus responsabilidades de poseedor

En la guía, dividida en dos partes, se describe cómo usar los productos, servicios y herramientas administrativas de Dynamics 365 para ayudarle a encontrar y actuar en datos en la nube de Microsoft en respuesta a las solicitudes realizadas por los derechos del titular de los datos que deciden ejercer sus derechos según el RGPD. La primera parte trata los datos personales que se incluyen en los datos de clientes, seguido de una parte que trata otros datos personales anonimizados parcialmente capturados en los registros generados por el sistema.

**Parte 1: Responder a solicitudes de derechos del titular de los datos personales incluidos en datos de clientes.** En la parte 1 de esta guía, se explica cómo obtener acceso, rectificar, restringir, eliminar y exportar datos personales de aplicaciones de Dynamics 365 (software como servicio), que se procesan como parte de los datos de clientes que proporcionó el servicio en línea.

**Parte 2: Responder a solicitudes de derechos del titular de los datos para anonimizarlos parcialmente.** Al usar los servicios empresariales de Dynamics 365, Microsoft genera información (denominada en este documento *registros generados por el sistema*) para la prestación del servicio, que está limitada a los datos de uso de los usuarios finales que permiten identificar sus acciones en el sistema. Aunque estos datos no se pueden atribuir a un titular de los datos específico sin el uso de información adicional, algunos pueden considerarse datos personales según el RGPD. En la parte 2 de esta guía, se explica cómo obtener acceso, eliminar y exportar registros generados por el sistema producidos por Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparar las investigaciones de derechos del titular de los datos

Cuando los titulares de los datos ejerzan sus derechos y realicen solicitudes, tenga en cuenta los siguientes puntos:

- Identifique correctamente la persona y el rol (por ejemplo, empleado, cliente, proveedores etc.) con la información que el titular de los datos le proporcionó como parte de su solicitud. Esta información podría ser un nombre, un id. de empleado o un número de cliente, o bien otro identificador.

- Anote la fecha y hora de la solicitud. (Dispone de 30 días para completar la solicitud).

- Confirme que la solicitud cumple con los requisitos de su organización para aceptar o rechazar una solicitud de titular de los datos. Por ejemplo, tiene que asegurarse de que, al ejecutar la solicitud, no se entre en conflicto con otras obligaciones legales, financieras o reglamentarias que tenga, ni infrinja los derechos o libertades de otros.

- Asegúrese de que posee la información relacionada con la solicitud.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-includced-in-customer-data"></a>Parte 1: Responder a las solicitudes de interesados relativas a datos personales incluidos en los datos de clientes

En los artículos siguientes, encontrará información útil para prepararse y responder a solicitudes de derechos del titular de los datos personales incluidos en los datos de clientes procesados en Dynamics 365. Es importante indicar que los datos personales podrían estar presentes en otras categorías de datos procesados por Microsoft durante la prestación del servicio de una suscripción de servicios en línea, como datos del administrador o datos de soporte técnico definidos en la Declaración de privacidad de Microsoft. Este documento se limita a asistirle en el proceso de detección y administración de solicitudes de derechos del titular de los datos que afecten a los datos personales presentes en los datos de clientes proporcionó a Dynamics 365.

Dynamics 365 es un servicio en línea que ofrece varias funciones de procesamiento de datos como software como servicio (SaaS). Como tal, Dynamics 365 ofrece una amplia variedad de funciones cuya intención es procesar una colección de datos diversa, que podrían variar en naturaleza, finalidad u otros atributos específicos, como datos de ventas, transacciones, operaciones financieras, información de recursos humanos, etc. En virtud de esta diversidad, Dynamics 365 ofrece distintos formularios, campos, esquemas, puntos de conexión y lógicas para procesar datos de cliente, que también se reflejan en las distintas formas en que podrían procesarse las solicitudes de derechos del titular de los datos en cada aplicación. Cuando las aplicaciones de Dynamics 365 ofrecen distintas formas de procesar solicitudes de derechos del titular de los datos específicas, las indicaremos en esta guía señalando las descripciones técnicas ofrecidas por cada aplicación.

### <a name="dynamics-365"></a>Dynamics 365
#### <a name="finding-customer-data"></a>Buscar los datos de cliente

El primer paso para responder a una solicitud de derechos del titular de los datos es buscar e identificar los datos de cliente que sean el objeto de la solicitud.

Clasificar correctamente los datos de clientes resulta esencial para trabajar con datos personales en Microsoft Dynamics 365 for Customer Engagement. Dynamics 365 for Customer Engagement ofrece flexibilidad para crear una extensión de aplicación entorno a la clasificación de datos. Una clasificación adecuada le permitirá identificar información como datos personales y, por lo tanto, permite buscarlos y recuperarlos al responder a solicitudes del titular de los datos. También puede facilitar el cumplimiento de requisitos legales y reglamentarios relacionados con la recopilación y el tratamiento de datos personales.

Microsoft proporciona funciones que pueden ayudarle a responder a solicitudes de derechos del titular de los datos y, por lo tanto, obtener acceso a datos de clientes. Pero es su responsabilidad garantizar que los datos personales se clasifiquen y organicen correctamente.

<span id="_Toc511225657" class="anchor"></span>***Dynamics 365 for Customer Engagement*** le ofrece varios métodos de buscar datos personales en registros: Búsqueda avanzada, Búsqueda por relevancia y Búsqueda de registros. Todas estas funciones le permiten identificar (encontrar) datos personales.

-   [Búsqueda avanzada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)

-   [Búsqueda por relevancia](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results) son búsquedas que se pueden guardar para futuras referencias con los paneles.

-   [Búsqueda de registros](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) en varios tipos de registro.

En Dynamics 365 for Marketing, tiene las siguientes funciones adicionales:

1.  [Crear informes de Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) para filtrar e identificar datos de clientes.

2.  Use las vistas de información a los contactos y objetos de ejecución de marketing para identificar puntos de datos adicionales que puedan contener datos de cliente.

Dynamics 365 Customer Service Insights ofrece funcionalidades para responder a solicitudes de copias de datos personales, eliminar datos personales y encontrar datos personales que son objeto de solicitudes de detección de interesados. Para obtener más información, vea [Overview of GDPR compliance for Dynamics 365 Customer Service Insights](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary) (Introducción al cumplimiento del RGPD para Dynamics 365 Customer Service Insights).

<span id="_Toc511225658" class="anchor"></span>***Dynamics 365 Finance and Operations*** le ofrece distintas formas de buscar datos de clientes. Como administrador del espacio empresarial, puede realizar las acciones siguientes para buscar datos de clientes:

-   Organice sus datos de clientes de forma que pueda descubrir rápidamente datos personales (para hacerlo, vea [cómo clasificar un inventario de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)).

-   Use el [Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para encontrar y recopilar datos personales.

-   [Amplíe el Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) (para hacerlo, cree una entidad o amplíe una entidad existente).

-   Use las características de búsqueda y filtrado para encontrar datos personales específicos, y la función Exportar de Microsoft Office le permite exportar esos datos o imprimirlos en un archivo .pdf con extensiones del explorador.

-   Cree un formulario personalizado que busque y exporte datos personales.

-   Cree un sitio web o portal externo que permita a un cliente autenticado ver sus datos personales.


***Dynamics for Business Central*** ofrece diversas formas de buscar datos de clientes. Para más información, vea [Buscar, filtrar y ordenar datos](https://docs.microsoft.com/dynamics-nav-app/ui-enter-criteria-filters).

<span id="_Toc511225660" class="anchor"></span>***Dynamics 365 for Talent*** ofrece características avanzadas de búsqueda y filtrado para encontrar datos personales específicos, y la función Exportar de Microsoft Office le permite exportar esos datos o imprimirlos en un archivo .pdf con extensiones del explorador.

-   Use el [Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para buscar y recopilar datos de clientes.

-   [Amplíe el Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) (para hacerlo, cree una entidad o amplíe una entidad existente).

### <a name="providing-a-copy-of-customer-data"></a>Facilitar una copia de los datos de clientes

Los datos de clientes en ***Dynamics 365 for Customer Engagement*** se pueden exportar con las completas funciones de exportación de entidades. Los datos de clientes se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Después, con Excel puede editar los datos personales que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml.

Además, para Dynamics 365 for Marketing, se proporciona una [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) que permite a los clientes crear extensiones que recuperan registros adicionales de interacciones de clientes registradas que pueden contener datos personales. La API carga toda la información relevante del sistema back-end y la combina en un único documento portátil.

Los datos de clientes en ***Dynamics 365 for Finance and Operations*** se pueden exportar con las completas funciones de exportación de entidades. Con [*Entidades de integración y administración de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), el administrador del espacio empresarial puede usar las entidades proporcionadas, crear entidades o ampliar las entidades de una exportación de datos personales repetible a Excel, o bien a otros formatos comunes con [*Trabajos de importación y exportación de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job). Como alternativa, muchas listas se pueden exportar a un archivo estático de Excel para facilitar una solicitud de portabilidad de datos. Cuando los datos del cliente se exportan a Excel, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml. También puede usar el *Informe de búsqueda de personas * para proporcionar al interesado aquellos datos que clasificó como personales. 

En ***Dynamics 365 Business Central***, puede usar dos características para proporcionar una copia de los datos del cliente a un titular de los datos:

Puede exportar datos de clientes a un archivo de Excel. En Excel, podrá editar los datos de clientes para que se incluyan en la solicitud de portabilidad y guardarlos en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/es-ES/dynamics365/business-central/about-export-data).

En ***Dynamics 365 for Talent***, puede usar el [Informe de búsqueda de personas extendido](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) para recopilar información relacionada con una solicitud de copia de los datos personales del titular de los datos.

### <a name="rectifying-customer-data"></a>Rectificar los datos de cliente

<span id="_Toc511225663" class="anchor"></span>***Dynamics 365 for Customer Engagement*** ofrece los siguientes métodos para corregir datos de clientes incompletos o imprecisos, o bien para borrarlos:

-   Busque datos de clientes con las funciones indicadas en “Buscar datos de clientes”, y edite directamente los datos en formularios de interacción con clientes. Las ediciones se pueden realizar en una única fila, o bien puede modificar varias filas directamente.

-   Al editar de forma masiva varios registros de interacciones con clientes, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel en Dynamics 365 for Customer Engagement.

Además, para Dynamics 365 for Marketing, también puede:

-   Actualizar la página de destino de actualización de datos personales, al editar una o varias filas directamente.

-   Preparar la página [Centro de suscripciones](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center), con todos los campos de contacto editables que se puedan incluir. Esto permite a un usuario final actualizar su propia información en la medida de lo posible.

En ***Dynamics 365 for Finance and Operations***, también puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), pero la decisión y la implementación son su responsabilidad.

<span id="_Toc511225664" class="anchor"></span>***Dynamics 365 Business Central*** ofrece dos formas de corregir datos de clientes incompletos o imprecisos.

Para editar de forma masiva y rápidamente varios registros de Business Central, puede exportar listas a Excel con el [complemento de Excel de Business Central](https://docs.microsoft.com/es-ES/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para corregir varios registros y, después, puede publicar los datos modificados desde Excel en Business Central. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/es-ES/dynamics365/business-central/about-export-data).

- Para cambiar los datos de clientes almacenados en cualquier campo (por ejemplo, información sobre un cliente en la tarjeta Cliente), edite de forma manual el elemento de datos que contiene los datos personales de destino. Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota breve sobre cómo modificar las entradas de las transacciones comerciales
Los registros transaccionales (como entradas generales, de cliente y del libro de retención de impuestos) son esenciales para garantizar la integridad de un sistema de planeamiento de recursos empresariales. Los datos personales que pertenecen a una transacción financiera (o de otro tipo) se mantienen “tal cual” con fines de cumplimiento con leyes financieras (por ejemplo, leyes tributarias), prevención del fraude (como una traza de auditoría de seguridad) o con certificaciones del sector. Por lo tanto, Dynamics 365 for Finance and Operations y Dynamics 365 Business Central restringen la modificación de datos en esos registros.

Si almacena datos personales en registros de transacciones empresariales, la única forma de corregir, eliminar o restringir el procesamiento de datos personales para aceptar una solicitud del titular de los datos es usar las [funciones de personalización](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index) de Dynamics 365 Business Central. La [](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)decisión de aceptar una solicitud del titular de los datos de modificación, así como su implementación posterior, es su responsabilidad.

### <a name="restricting-the-processing-of-customer-data"></a>Restringir el procesamiento de datos de cliente

Al recibir la solicitud de un titular de los datos para restringir el procesamiento de datos de clientes, puede extraer fácilmente los datos de clientes afectados desde servicio en línea y almacenarlos en un contenedor separado (es decir, un almacenamiento local o un servicio web separado con funciones de aislamiento de datos) aislado de las funciones de procesamiento ofrecidas por cualquier aplicación de nube.

***Dynamics 365 Business Central*** ofrece un mecanismo alternativo, como el bloque de procesamiento de datos, donde se permite a los usuarios bloquear datos específicos en el registro del titular de los datos. Para obtener más información, vea [Restringir el procesamiento de datos de un titular de los datos](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Cuando un registro se marca como bloqueado, Dynamics 365 Business Central dejará de procesar los datos de cliente de ese titular de los datos. No se pueden crear transacciones que usen un registro bloqueado (por ejemplo, no puede crear una factura para un cliente cuando el cliente o el comercial están bloqueados).

### <a name="deleting-customer-data"></a>Eliminar datos de cliente

Si un titular de los datos le pide que elimine sus datos de cliente, hay varias formas de hacerlo:

-   Con la edición masiva de varios registros de Dynamics 365, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel el servicio en línea.

-   Puede eliminar los datos de cliente almacenados en cualquier campo; para hacerlo, busque los datos que quiera eliminar y, después, elimine de forma manual el elemento de datos que contenga los datos de cliente de destino (por ejemplo, puede usar una eliminación permanente en el registro del contacto que represente el titular de los datos y otros registros que contengan datos personales).

Además, en Dynamics 365 Marketing, al eliminar un contacto, se asegurará de que se quiten también los datos de interacciones con información personal. Para cualquier entidad o campo personalizado, necesita personalizar el sistema para asegurarse de que se eliminen todos los datos de cliente de los registros relacionados, o bien que se desvinculen del registro del contacto para que pueda quitarse toda la información personal. Más información: [Guía para desarrolladores (marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

Como alternativa, en ***Dynamics 365 for Finance and Operations***, puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) para borrar o modificar datos de cliente.

En ***Dynamics 365 Business Central***, cuando un titular de los datos le pide que elimine sus datos personales y estos se incluyen en los datos de cliente, hay varias formas de procesar la solicitud:

-   Para editar de forma masiva rápidamente varios registros de Business Central, puede exportar los datos a Excel con el [complemento de Excel de Business Central](https://docs.microsoft.com/es-ES/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para eliminar varios registros y, después, puede publicar esos cambios desde Excel en Business Central. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/es-ES/dynamics365/business-central/about-export-data).

-   Puede eliminar los datos de cliente almacenados de forma manual en cualquier campo; para hacerlo, elimine el elemento de datos que contenga los datos de cliente de destino. Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

-   Puede eliminar directamente los datos de cliente (por ejemplo, si elimina un contacto y, después, ejecuta el trabajo por lotes de eliminación de entradas de registro de interacciones canceladas con el fin de eliminar las interacciones de ese contacto).

-   Puede [eliminar documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) que contengan datos de cliente (por ejemplo, memorandos, ventas contabilizadas y facturas de compra).

Además de la eliminación masiva o individual de registros específicos, tenga en cuenta que, desde ***Dynamics 365 for Talent***, solo se pueden eliminar por completo los empleados cesados. [Siga este procedimiento para eliminar los empleados cesados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportar datos de cliente

Para responder a una solicitud de portabilidad de datos, los datos de cliente en ***Dynamics 365 for Customer Engagement*** se pueden exportar con las completas funciones de exportación de entidades. Los datos de clientes se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Después, con Excel puede editar los datos personales que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml.

Además, para Dynamics 365 for Marketing, se proporciona una [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) que permite a los clientes crear extensiones que recuperan registros adicionales de interacciones de clientes registradas que pueden contener datos personales. La API carga toda la información relevante del sistema back-end y la combina en un único documento portátil.

<span id="_Toc511225669" class="anchor"></span>***Dynamics 365 for Finance and Operations*** ofrece [Entidades de integración y administración de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), que permite a las entidades proporcionadas, las nuevas entidades o las entidades extendidas exportar datos personales de forma repetida a Excel o a otros formatos comunes con [Trabajos de importación y exportación de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job). Como alternativa, muchas listas se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Cuando los datos de cliente se exportan a Excel de esta forma, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml.

Tanto Dynamics 365 for Finance and Operations como ***Dynamics 365 for Talent*** ofrecen la característica “Informe de búsqueda de personas” para proporcionar al titular de los datos la información que clasificó como datos personales. 

- <span id="_Toc511225670" class="anchor"></span>***Dynamics 365 Business Central*** ofrece estas características:

- Puede exportar datos de clientes a un archivo de Excel. En Excel, podrá editar los datos de clientes para que se incluyan en la solicitud de portabilidad y guardarlos en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/dynamics-nav-app/about-export-data).

Puede exportar datos de clientes a un archivo de Excel. En Excel, podrá editar los datos de clientes para que se incluyan en la solicitud de portabilidad y guardarlos en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/es-ES/dynamics365/business-central/about-export-data).

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

<span id="_Toc511166412" class="anchor"></span>Como Microsoft Social Engagement procesa datos personales que podían encontrarse en datos de cliente y contenido social, esta aplicación ofrece una forma única de procesar solicitudes de derechos del titular de los datos, ya que está relacionada con los datos personales recuperados de redes sociales. El contenido social está compuesto por contenido público recopilado de redes sociales (como Twitter, Facebook y YouTube) y datos indexados o servicios de agregación de datos en respuesta a consultas de búsqueda de clientes ejecutadas en Microsoft Social Engagement. El contenido social no son datos de cliente. Las restricciones adicionales de procesamiento, uso y almacenamiento de contenido social se describen en los Términos de Microsoft Online Services.

### <a name="finding-personal-data"></a>Buscar datos personales

El primer paso para responder a una solicitud de titular de los datos es buscar e identificar los datos personales que son el objeto de la solicitud. Microsoft Social Engagement almacena los datos siguientes:

#### <a name="for-social-media-users"></a>Para usuarios de redes sociales

- Datos de usuario de red social (conocido como *autor* en Social Engagement) que Social Engagement obtiene de plataformas sociales. Se puede incluir el nombre, el nombre de usuario, la imagen de perfil, la ubicación, el sitio web y la biografía, si esta información es proporcionada por el autor.

- Las etiquetas de autor usadas por los empleados de Social Engagement para agrupar y clasificar autores (por ejemplo, como influyentes, competidores o seguidores).

#### <a name="for-employees"></a>Para empleados

- Perfiles de usuario donde se incluye el nombre del empleado, información de contacto y la imagen de perfil, y se administran en Office 365.

- Direcciones de correo electrónico proporcionadas por empleados que crearon alertas de publicaciones y alertas de tendencias.

- Cuentas de redes sociales (denominados *perfiles sociales* en Social Engagement) que se autentican en Social Engagement por empleados para interactuar con otros en una plataforma social. Pueden ser propiedad de un empleado o de la organización, e incluir datos que los empleados proporcionaron al registrar una cuenta en una plataforma social. Estos perfiles representan a la organización en redes sociales y se usan para interactuar con publicaciones en nombre de la organización desde la aplicación Social Engagement.

- Nombres de usuario en Power BI, si su organización usa el [Paquete de contenido de Social Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) para Power BI para analizar el rendimiento del equipo en las redes sociales.

El primer paso (buscar y revisar los datos personales que sean objeto de la solicitud) le permitirá determinar si la solicitud del titular de los datos cumple con los requisitos de la organización para aceptarla o rechazarla. Por ejemplo, después de identificar y revisar los datos personales, puede determinar que la solicitud no cumple con los requisitos de su organización porque podría afectar de forma negativa a los derechos y libertades de otros.

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)

-   Para encontrar sus datos personales, siga los primeros cuatro pasos de [Buscar y eliminar un autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author).

-   Los empleados pueden crear reglas de Social Engagement que busquen contenido específico en plataformas sociales; estas reglas de búsqueda pueden contener nombres de autor. Para buscar esas reglas, revise las reglas de búsqueda de cuentas de redes sociales para encontrar la cuenta correspondiente (por ejemplo, [Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule), [Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule) y [YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule)).

-   Para encontrar las etiquetas de autor de un actor, primero [filtre las publicaciones](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter) por [autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors) y, después, [vea las etiquetas de autor](https://go.microsoft.com/fwlink/?linkid=864795).

##### <a name="your-employees"></a>Sus empleados 

Para buscar:

-   Un perfil de usuario, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home). En el **Centro de administración**, seleccione **Usuarios**. En la página **Usuarios activos**, busque el usuario en la lista.  
    En Social Engagement, vaya a **Configuración \> Administración de usuarios** para ver la información que se sincroniza automáticamente desde Office 365.

-   El destinatario de una alerta, siga los primeros dos pasos de [Administrar destinatarios de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).

-   Datos de perfiles sociales especificados por los empleados, vaya a **Configuración \> Perfiles sociales**. (Para obtener más información, vea [Administrar perfiles sociales](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles)).

-   Nombres de usuario en Power BI, abra el panel de Power BI de Social Engagement y filtre por nombre de empleado.

### <a name="providing-a-copy-of-personal-data"></a>Facilitar una copia de los datos personales

El RGPD concede a los titulares de los datos el derecho de obtener una copia de datos personales a petición. Cuando encuentre el contenido del cliente que contenga los datos que puedan ser objeto de la solicitud, es responsabilidad de la organización decidir si quiere proporcionar una copia al titular de los datos.

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)

- Para exportar los datos personales de autores, siga los pasos que se indican en [Exportar información de autores](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) para exportar los datos a un archivo de Excel.

- Para extraer las etiquetas de autor que se agregaron a un autor específico, puede [exportar datos de etiquetas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>Sus empleados
Para exportar:

- Datos de cliente de perfiles de usuario, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home). En el **Centro de administración**, seleccione **Usuarios**. En la página **Usuarios activos**, busque el usuario cuyos datos quiera exportar. Elimine todos los usuarios excepto el usuario de destino y, después, seleccione **Exportar** para exportar los datos a un archivo .csv (puede abrirlo en Excel para ver la información).

- Direcciones de correo electrónico de un destinatario de alertas (los únicos datos de cliente de una alerta). Siga los pasos que se indican en [Administrar destinatarios de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Después, seleccione **Exportar** para descargar una lista de Excel de las alertas donde se incluya este destinatario.

- Nombres de usuario de Power BI: [Informes de interacciones](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) donde se muestran nombres de usuario e informes del rendimiento del equipo en redes sociales. Para exportar estos datos, filtre por el usuario en el panel de Power BI o en el [informe](https://docs.microsoft.com/power-bi/power-bi-report-add-filter), y [exporte los datos](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

### <a name="rectifying-personal-data"></a>Rectificar los datos personales

Para corregir datos personales incompletos o imprecisos:

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)

-   Necesita preguntar al propietario de los datos (autor) que realice el cambio en la plataforma social (como Twitter, WordPress o Tumblr). El titular de los datos es el propietario de los datos en la cuenta de red social, por lo que son los únicos datos que puede cambiar. Cuando el autor realice el cambio, Social Engagement sincronizará automáticamente los detalles revisados.

-   Etiquetas de autor, siga los pasos que se indican en [Cambiar etiquetas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags).

##### <a name="your-employees"></a>Sus empleados

-   Perfiles de usuario: para realizar cambios en los datos de cliente de un perfil de usuario, vea [Cambiar un nombre de usuario y una dirección de correo electrónico en Office 365](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297) y [Agregar una foto de perfil en Office 365](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7).  
    Estos cambios se sincronizarán automáticamente en Social Engagement. Para encontrarlos, vaya a **Configuración** \> **Administración de usuarios**.

-   Destinatarios de alertas: puede [cambiar una alerta](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert).

### <a name="restricting-the-processing-of-personal-data"></a>Restringir el procesamiento de datos personales

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)
Para detener el procesamiento de datos de cliente de los autores en Social Engagement, [elimine el autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).

Esto bloqueará el procesamiento futuro de los datos de ese titular de los datos y de todas sus publicaciones futuras, además de eliminar todos los datos sobre el autor. Cada vez que Social Engagement obtenga nuevas publicaciones, comprobará automáticamente si el autor se eliminó anteriormente y descartará las publicaciones de los autores eliminados. Esto no tiene ningún efecto en la cuenta de usuario de la plataforma social.

##### <a name="your-employees"></a>Sus empleados

- Para detener el procesamiento de datos de cliente de los empleados, puede [quitar su licencia](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) en Office 365. De esta forma, se eliminarán todos los elementos relacionados con Social Engagement, como roles de usuario y perfiles, todas las configuraciones personalizadas definidas por el usuario, alertas, mapas de actividad y flujos de contenido. Los temas de búsqueda y perfiles sociales no se eliminan; pero los administradores heredan la propiedad de los perfiles sociales de los usuarios eliminados y pueden eliminarlos a petición.

- Para restringir el envío de mensajes de correo electrónico de alerta, puede quitar una dirección de correo electrónico de todas las alertas que se agregaron; para hacerlo, siga los pasos que se indican en [Administrar destinatarios de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).

### <a name="deleting-personal-data"></a>Eliminar datos personales

El RGPD concede a los titulares de los datos el derecho de solicitar al poseedor la eliminación de los datos personales en determinadas circunstancias. El “derecho a ser olvidado” al quitar esos datos de una organización es una protección clave en el RGPD.

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)

Para eliminar de forma permanente todos los datos personales de un actor en Social Engagement, elimine todo el perfil social de este autor. Vea [](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors)[Eliminar un autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).  
La acción de eliminación no se puede deshacer. Se eliminarán todos los datos del autor en Social Engagement y se impedirá el procesamiento futuro de sus datos y de sus publicaciones. Cada vez que Social Engagement obtenga nuevas publicaciones, comprobará automáticamente si el autor se eliminó anteriormente y descartará las publicaciones de los autores eliminados. Esto no tiene ningún efecto en la cuenta de usuario de la plataforma social.

Para eliminar etiquetas de autor, vea [Quitar etiquetas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags).

>[Nota] Si se le pide que quite información sobre un autor específico, le recomendamos que primero confirme la identidad de ese autor para validar la solicitud. Para confirmar su identidad, puede solicitar un mensaje privado del autor desde su cuenta de red social.

Social Engagement implementó fuentes de cumplimiento de distintas plataformas sociales (como Twitter, WordPress y Tumblr) para actuar en señales, como eliminaciones de publicaciones que se desencadenaron directamente en las plataformas de redes sociales. Esta característica se activa automáticamente con todas las instalaciones de Social Engagement y no necesita la interacción del usuario. Además, Social Engagement ofrece un mecanismo que permite a algunos servicios (como Dynamics 365 for Customer Engagement) que usan contenido social de Social Engagement heredar estas señales.

##### <a name="your-employees"></a>Sus empleados

Para eliminar de forma permanente todos los datos de cliente de un empleado, puede [quitar su licencia](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) en Office 365.

-   De esta forma, se eliminarán todos los elementos relacionados con Social Engagement, como roles de usuario y perfiles, todas las configuraciones personalizadas definidas por el usuario, alertas, mapas de actividad y flujos de contenido. Los temas de búsqueda y los perfiles sociales no se eliminan. (Los administradores heredan la propiedad de los perfiles sociales de los usuarios eliminados y pueden eliminarlos a petición).

-   Estos cambios se sincronizarán automáticamente en Social Engagement. Para encontrarlos, vaya a **Configuración \> Administración de usuarios**.

-   Las entradas de empleado de un informe de interacción de Power BI se anonimizan al eliminar sus datos personales.

Puede eliminar un [perfil social](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile).

Para eliminar una dirección de correo electrónico de todas las alertas a las que se agregaron, siga los pasos que se indican en [Administrar destinatarios de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>Exportar datos personales
Puede proporcionar a los titulares de los datos su información personal en formato electrónico.

#### <a name="social-media-users-authors"></a>Usuarios de redes sociales (autores)

Para exportar los datos personales de autores, siga los pasos que se indican en [Exportar información de autores](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) para exportar los datos a un archivo de Excel.

Para extraer las etiquetas de autor que se agregaron a un autor específico, puede [exportar datos de etiquetas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>Sus empleados
Para exportar:

- Datos de cliente de perfiles de usuario, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home). En el **Centro de administración**, seleccione **Usuarios**. En la página **Usuarios activos**, busque el usuario cuyos datos quiera exportar. Elimine todos los usuarios excepto el usuario de destino y, después, seleccione **Exportar** para exportar los datos a un archivo .csv (puede abrirlo en Excel para ver la información).

- Las direcciones de correo electrónico de un destinatario de alertas (los únicos datos personales de una alerta). Siga los pasos que se indican en [Administrar destinatarios de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Después, seleccione **Exportar** para descargar una lista de Excel de las alertas donde se incluya este destinatario.

- Nombres de usuario de Power BI: [Informes de interacciones](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) donde se muestran nombres de usuario e informes del rendimiento del equipo en redes sociales. Para exportar estos datos, filtre por el usuario en el panel de Power BI o en el [informe](https://docs.microsoft.com/power-bi/power-bi-report-add-filter), y [exporte los datos](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder a solicitudes de interesados relativas a registros generados por el sistema

Microsoft también le permite obtener acceso, exportar y eliminar registros generados por el sistema que pueden considerarse como datos personales según la definición amplia del RGPD de “datos personales”. Estos son algunos ejemplos de registros generados por el sistema que pueden considerarse como datos personales según el RGPD:

-   Datos de uso del servicio de productos, como registros de actividad de usuario.

-   Solicitudes de búsqueda de usuarios y datos de consultas.

-   Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.

<span id="_Toc511045103" class="anchor"><span id="_Toc511043191" class="anchor"><span id="_Toc511041446" class="anchor"><span id="_Toc511030410" class="anchor"><span id="_Toc510769888" class="anchor"></span></span></span></span></span>No se admite la capacidad de restringir o rectificar datos en los registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico, y modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría el fraude y los riesgos de seguridad.

### <a name="accessing-and-exporting-system-generated-logs"></a>Tener acceso a los registros generados por el sistema y exportarlos

Los administradores pueden obtener acceso a registros generados por el sistema asociados con el uso de un usuario específico de las aplicaciones y servicios de Dynamics 365. Para obtener acceso a los registros generados por el sistema y exportarlos:

1.  Vaya al [Portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) e inicie sesión con las credenciales de un administrador global de Dynamics 365.

2.  En la lista desplegable **Privacidad** de la parte superior de la página, haga clic en **Solicitud del titular de los datos**.

3.  En la página **Solicitud del interesado**, en **Registros generados por el sistema**, haga clic en **Exportación de registros de datos**.

> Se mostrará la pantalla **Exportación de registros de datos**. Se mostrará una lista de las solicitudes de datos de exportación enviadas por su organización.

4.  Para crear una solicitud para usuario, haga clic en **Crear solicitud de exportación de datos**.

Después de crear una solicitud, se mostrará en la página **Exportación de registros de datos**, donde puede realizar un seguimiento de su estado. Después de completar una solicitud, puede hacer clic en un vínculo para obtener acceso a los registros generados por el sistema, que se exportarán a la ubicación de Azure Storage de su organización en un plazo de 30 días después de crear la solicitud. Los datos se guardarán en formatos de archivo de lectura mecánica comunes, como JSON o XML. Si no tiene una cuenta de Azure ni una ubicación de Azure Storage, tendrá que crear una cuenta de Azure o una ubicación de Azure Storage para su organización para que la herramienta Exportación de registros de datos pueda exportar los registros generados por el sistema.

Azure facilita esto al permitir que su organización pueda exportar los datos en el formato JSON nativo al contenedor especificado de Azure Storage[. Introducción a Microsoft Azure Storage: Blob Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) (artículo).

**Importante**: Necesita ser un administrador de espacios empresariales para exportar datos de usuario del espacio empresarial.

En la tabla siguiente, se resumen las acciones de acceso y exportación de registros generados por el sistema:

<table>
<tbody>
<tr class="odd">
<td align="left"><strong>¿Cuánto tarda la herramienta Exportación de registros de datos de Microsoft en completar una solicitud?</strong>
<td align="left">Esto puede depender de varios factores. En la mayoría de los casos, suele completarse en uno o dos días, pero puede tardar hasta 30 días.</td>
</tr>
<tr class="odd">
<td align="left"><strong>¿Qué formato tendrá el resultado?</strong></td>
<td align="left">El resultado serán archivos con formato de lectura mecánica estructurados, como XML, CSV o JSON.</td>
</tr>
<tr class="even">
<td align="left"><strong>¿Qué datos devuelve la herramienta Exportación de registros de datos?</strong></td>
<td align="left">La herramienta Exportación de registros de datos devuelve registros generados por el sistema almacenados por Microsoft. Los datos exportados pertenecen a varios servicios Microsoft, como Office 365, Azure y Dynamics.</td>
</tr>
<tr class="odd">
<td align="left"><strong>¿Quién tiene acceso a la herramienta Exportación de registros de datos para enviar solicitudes de acceso de registros generados por el sistema?</strong></td>
<td align="left">Los administradores globales de Dynamics 365 tendrán acceso a la utilidad Administrador de registros del RGPD.</td>
</tr>
<tr class="even">
<td align="left"><strong>¿Cómo se devuelven los datos al usuario?</strong></td>
<td align="left">Los datos se exportarán a la ubicación de Azure Storage de su organización; los administradores de la organización tendrán que determinar cómo mostrarán o enviarán estos datos a los usuarios.</td>
</tr>
<tr class="odd">
<td align="left"><strong>¿Cuál será la apariencia de los datos en los registros generados por el sistema?</strong></td>
<td align="left"><p>Ejemplo de una entrada de registro generada por el sistema en formato JSON:</p>
<p>[{</p>
<p>  &quot;DateTime&quot;: &quot;2017-04-28T12:09:29-07:00&quot;,</p>
<p>  &quot;AppName&quot;: &quot;SharePoint&quot;,</p>
<p>  &quot;Action&quot;: &quot;OpenFile&quot;,</p>
<p>  &quot;IP&quot;: &quot;154.192.13.131&quot;,</p>
<p>  &quot;DevicePlatform&quot;: &quot;Windows 1.0.1607&quot;</p>
<p>}]</p></td>
</tr>
</tbody>
</table>

[Nota] Algunas características no permiten exportar ni eliminar los registros generados por el sistema con información personal para mantener la integridad de dicha información con fines de seguridad y auditoría.

### <a name="deleting-system-generated-logs"></a>Eliminar registros generados por el sistema
Para eliminar los registros generados por el sistema recuperados con una solicitud de acceso, necesita quitar el usuario del servicio y eliminar de forma permanente su cuenta de Azure Active Directory. Para obtener instrucciones sobre cómo eliminar de forma permanente un usuario, vea la sección [Eliminar un usuario](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user) en esta guía. Es importante tener en cuenta que la acción de eliminar una cuenta de usuario de forma permanente es irreversible.

Al eliminar de forma permanente una cuenta de usuario, en un plazo de 30 días, se quitarán los datos del usuario de los registros generados por el sistema de prácticamente todos los servicios de Dynamics 365.

#### <a name="learn-more"></a>Más información

[Centro de confianza de Microsoft](https://www.microsoft.com/es-ES/TrustCenter/Privacy/gdpr/default.aspx)
