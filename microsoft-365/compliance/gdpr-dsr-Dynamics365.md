---
title: Solicitudes del interesado de Dynamics 365 para el RGPD y la CCPA
description: Obtenga información acerca de cómo encontrar datos personales, realizar acciones con ellos y responder a las solicitudes relacionadas con DSR y CCPA de los clientes que utilizan Dynamics 365.
keywords: Microsoft 365, Educación de Microsoft 365, documentación de Microsoft 365, RGPD, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817669"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes del interesado de Dynamics 365 para el RGPD y la CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

De forma similar, la Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés), ofrece derechos y obligaciones de privacidad a los consumidores de California, incluyendo derechos similares a los Derechos del Interesado de GDPR, como el derecho de eliminar, acceder y recibir (portabilidad) su información personal.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Guía sobre cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar y actuar en datos personales con el fin de responder a las solicitudes de derechos del titular de los datos. En concreto, esto incluye cómo encontrar y acceder a los datos e información personales que residen en la nube de Microsoft y actuar en base a ellos. Este es un breve resumen de los procesos descritos en esta guía:

- **Búsqueda**: use herramientas de búsqueda y detección para encontrar más fácilmente los datos personales del cliente que pueden ser objeto de una solicitud de DSR. Una vez recopilados los documentos de respuesta, puede realizar una o varias de las acciones de DSR siguientes para responder a la solicitud. También puede determinar que la solicitud no cumple con las directrices de la organización para responder a las solicitudes de DSR.
- **Acceso:** recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.
- **Rectificación:** realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.
- **Restricción**: Restrinja el procesamiento de datos personales, ya sea mediante la eliminación de licencias para varios servicios en línea o mediante la desactivación de los servicios deseados cuando sea posible. Puedes
- **Eliminación:** elimine de forma permanente los datos personales que residen en la nube de Microsoft.
- **Exportar o recibir (portabilidad):** envíe una copia electrónica (en un formato legible por máquina) de datos o información personal al titular de los datos. La información personal bajo la CCPA es cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. La definición de la CCPA de la "información personal" es a grandes rasgos similar a la que el RGPD hace de los "datos personales". Sin embargo, la CCPA también incluye datos domésticos y familiares. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

En cada sección de esta guía, se describen los procedimientos técnicos que puede realizar una organización poseedora de los datos para responder a una solicitud de derechos del titular de los datos personales en la nube de Microsoft.

### <a name="gdpr-terminology"></a>Terminología del RGPD

Estas son las definiciones de los términos relacionados con esta guía:

- **Poseedor:** la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable ("interesado"); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Datos de cliente:** todos los datos, incluidos todos los archivos de texto, sonido, vídeo o imagen, y software, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. Los datos del cliente incluyen tanto (1) información identificable de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) como el contenido del cliente que un cliente carga o crea en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, el contenido del cliente de Azure SQL Database o la imagen de la máquina virtual de un cliente en máquinas virtuales Azure).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios a los usuarios, pero no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Modo en que esta guía puede servir para cumplir sus responsabilidades de poseedor

En la guía, dividida en dos partes, se describe cómo usar los productos, servicios y herramientas administrativas de Dynamics 365 para ayudarle a encontrar y actuar en datos en la nube de Microsoft en respuesta a las solicitudes realizadas por los interesados que deciden ejercer sus derechos según el RGPD. La primera parte trata los datos personales que se incluyen en los datos de clientes, seguido de una parte que trata otros datos personales anonimizados parcialmente capturados en los registros generados por el sistema.

- **Parte 1: Responder a solicitudes de derechos de los interesados sobre datos personales incluidos en datos de clientes.** En la parte 1 de esta guía, se explica cómo obtener acceso, rectificar, restringir, eliminar y exportar datos personales de aplicaciones de Dynamics 365 (software como servicio), que se tratan como parte de los datos de clientes que proporcionó el servicio en línea.
- **Parte 2: Responder a solicitudes de derechos de los interesados sobre datos anonimizados:** Cuando utiliza los servicios de Dynamics 365 Enterprise, Microsoft genera cierta información (denominada en este documento como *registros generados por el sistema*) para proporcionar el servicio, el cual está limitado a la superficie de uso que dejan los usuarios finales para identificar sus acciones en el sistema. Aunque estos datos no pueden atribuirse a un interesado específico sin el uso de información adicional, algunos pueden ser considerados personales dentro del RGPD. La parte 2 de esta guía trata acerca de cómo acceder a, eliminar y exportar registros generados por el sistema producidos por Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparar las investigaciones de derechos de los interesados

Cuando los titulares de los datos ejerzan sus derechos y realicen solicitudes, tenga en cuenta los siguientes puntos:

- Identifique correctamente la persona y el rol (por ejemplo, empleado, cliente, proveedores, etc.) con la información que el interesado le proporcionó como parte de su solicitud. Esta información podría ser un nombre, un id. de empleado o un número de cliente, o bien otro identificador.
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Asegúrese de que posee la información relacionada con la solicitud.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Parte 1: Responder a las solicitudes de interesados relativas a datos personales incluidos en los datos de clientes

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Buscar los datos de cliente

El primer paso para responder a una solicitud de derechos del titular de los datos es buscar e identificar los datos de cliente que sean el objeto de la solicitud.

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

***Dynamics 365 for Customer Engagement*** le ofrece varios métodos para buscar datos personales en registros, como: Búsqueda avanzada y Búsqueda de registros. Todas estas funciones le permiten identificar (encontrar) datos personales.

- [Búsqueda avanzada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Búsqueda de registros](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) en varios tipos de registro.

En Dynamics 365 for Marketing, tiene las siguientes funciones adicionales:

1. [Crear informes de Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) para filtrar e identificar datos de clientes.
2. Use las vistas de información a los contactos y objetos de ejecución de marketing para identificar puntos de datos adicionales que puedan contener datos de cliente.

***Dynamics 365 Customer Service Insights*** ofrece una lista de recursos para ayudarle a [buscar datos de cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery) para responder a solicitudes GDPR de clientes. 

***Dynamics 365 for Finance and Operations*** le ofrece distintas formas de buscar datos de clientes. Como administrador del espacio empresarial, puede realizar las acciones siguientes para buscar datos de clientes:

- Organizar sus datos de clientes de forma que pueda descubrir rápidamente datos personales. Para hacerlo vea [cómo clasificar un inventario de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Use el [Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para encontrar y recopilar datos personales.
- [Amplíe el Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) (para hacerlo, cree una entidad o amplíe una entidad existente).
- Use las características de búsqueda y filtrado para encontrar datos personales específicos, y la función Exportar de Microsoft Office le permite exportar esos datos o imprimirlos en un archivo .pdf con extensiones del explorador.
- Cree un formulario personalizado que busque y exporte datos personales.
- Cree un sitio web o portal externo que permita a un cliente autenticado ver sus datos personales.

***Dynamics 365 Business Central*** le ofrece distintas formas de buscar datos de clientes. Para más información, vea [Buscar, filtrar y ordenar datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters).

***Dynamics 365 for Talent*** ofrece características avanzadas de búsqueda y filtrado para encontrar datos personales específicos, y la función Exportar de Microsoft Office le permite exportar esos datos o imprimirlos en un archivo .pdf con extensiones del explorador.

- Use el [Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para buscar y recopilar datos de clientes.
- [Amplíe el Informe de búsqueda de personas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) (para hacerlo, cree una entidad o amplíe una entidad existente).

### <a name="providing-a-copy-of-customer-data"></a>Facilitar una copia de los datos de clientes

Los datos de clientes en ***Dynamics 365 for Customer Engagement*** se pueden exportar con las completas funciones de exportación de entidades. Los datos de clientes se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Con Excel puede editar los datos personales que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Los registros de Dynamics 365 for Customer Engagement también pueden exportarse con el [API web del servicio de datos comunes](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview).

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights***, le permite [proporcionar una copia de los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) mediante exportación de datos.

Los datos de clientes en ***Dynamics 365 for Finance and Operations*** se pueden exportar con las completas funciones de exportación de entidades. Con [*Entidades de integración y administración de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), el administrador del espacio empresarial puede usar las entidades proporcionadas, crear entidades o ampliar las entidades de una exportación de datos personales repetible a Excel, o bien a otros formatos comunes con [*Trabajos de importación y exportación de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Como alternativa, muchas listas se pueden exportar a un archivo estático de Excel para facilitar una solicitud de portabilidad de datos.  Cuando los datos del cliente se exportan a Excel, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml. También puede usar el *Informe de búsqueda de personas* para proporcionar al interesado aquellos datos que clasificó como personales.

En ***Dynamics 365 Business Central***, puede usar dos características para proporcionar una copia de los datos del cliente a un titular de los datos:

Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)

En ***Dynamics 365 for Talent***, puede usar el [Informe de búsqueda de personas extendido](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) para recopilar información relacionada con una solicitud de copia de los datos personales del titular de los datos.

### <a name="rectifying-customer-data"></a>Rectificar los datos de cliente

***Dynamics 365 for Customer Engagement*** le ofrece los métodos siguientes para corregir datos de clientes incompletos o imprecisos, o bien para borrar los datos de clientes:

- Busque datos de clientes con las funciones indicadas en “Buscar datos de clientes” y edítelos directamente en formularios de interacción con clientes. Las ediciones se pueden realizar en una única fila, o bien puede modificar varias filas directamente.
- Al editar de forma masiva varios registros de interacciones con clientes, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel en Dynamics 365 for Customer Engagement.

Además, para Dynamics 365 for Marketing, también puede:

- Actualizar la página de destino de actualización de datos personales, al editar una o varias filas directamente.
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** también ofrece funcionalidades que permiten a las organizaciones [rectificar o hacer cambios en los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary).

En ***Dynamics 365 for Finance and Operations***, también puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), pero la decisión y la implementación son su responsabilidad.

***Dynamics 365 Business Central*** ofrece dos formas de corregir datos de clientes incompletos o imprecisos.

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Para cambiar los datos de clientes almacenados en cualquier campo (por ejemplo, información sobre un cliente en la tarjeta Cliente), edite de forma manual el elemento de datos que contiene los datos personales de destino. Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota breve sobre cómo modificar las entradas de las transacciones comerciales

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>Restringir el tratamiento de datos de cliente

Al recibir la solicitud de un titular de los datos para restringir el procesamiento de datos de clientes, puede extraer fácilmente los datos de clientes afectados desde servicio en línea y almacenarlos en un contenedor separado (es decir, un almacenamiento local o un servicio web separado con funciones de aislamiento de datos) aislado de las funciones de procesamiento ofrecidas por cualquier aplicación de nube.

***Dynamics 365 Business Central*** ofrece mecanismos alternativos, como el bloqueo de procesamiento de datos mediante el que se permite a los usuarios la posibilidad de bloquear el registro de un interesado específico. Para obtener más información, vea [Restringir el procesamiento de datos de un titular de los datos](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Cuando un registro se marca como bloqueado, Dynamics 365 Business Central dejará de procesar los datos de cliente de ese titular de los datos. No se pueden crear transacciones que usen un registro bloqueado; por ejemplo, no puede crear una factura para un cliente cuando el cliente o el comercial están bloqueados.

### <a name="deleting-customer-data"></a>Eliminar datos de cliente

Si un titular de los datos le pide que elimine sus datos de cliente, hay varias formas de hacerlo:

- Con la edición masiva de varios registros de Dynamics 365, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel el servicio en línea.
- Puede eliminar los datos de cliente almacenados en cualquier campo; para hacerlo, busque los datos que quiera eliminar y, elimine de forma manual el elemento de datos que contenga los datos de cliente de destino. Por ejemplo, puede usar una eliminación permanente en el registro del contacto que represente el titular de los datos y otros registros que contengan datos personales

Además, en Dynamics 365 Marketing, al eliminar un contacto, se asegurará de que se quiten también los datos de interacciones con información personal. Para cualquier entidad o campo personalizado, necesita personalizar el sistema para asegurarse de que se eliminen todos los datos de cliente de los registros relacionados, o bien que se desvinculen del registro del contacto para que pueda quitarse toda la información personal. Más información: [Guía para desarrolladores (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** también ofrece a las organizaciones funcionalidades para [borrar los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Como alternativa, en ***Dynamics 365 for Finance and Operations***, puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) para borrar o modificar datos de cliente.

En ***Dynamics 365 Business Central***, cuando un titular de los datos le pide que elimine sus datos personales y estos se incluyen en los datos de cliente, hay varias formas de procesar la solicitud:

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Puede eliminar los datos de cliente almacenados de forma manual en cualquier campo; para hacerlo, elimine el elemento de datos que contenga los datos de cliente de destino.  Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Puede eliminar directamente los datos de cliente, por ejemplo, si elimina un contacto y ejecuta el trabajo por lotes de eliminación de entradas de registro de interacciones canceladas con el fin de eliminar las interacciones de ese contacto.
- Puede [eliminar documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) que contengan datos de cliente (por ejemplo, memorandos, ventas contabilizadas y facturas de compra).

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportar datos de cliente

Para responder a una solicitud de portabilidad de datos, en ***Dynamics 365 for Customer Engagement*** se pueden exportar los datos de cliente con las completas funciones de exportación de entidades. Los datos de clientes se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Con Excel puede editar los datos personales que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml.

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

Para ***Dynamics 365 Customer Service Insights***, [exporte los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) a través del portal de administración de Azure. 

***Dynamics 365 for Finance and Operations*** ofrece [Entidades de integración y administración de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), que permiten a las entidades proporcionadas, las nuevas entidades o las entidades extendidas exportar datos personales de forma repetida a Excel o a otros formatos comunes con [Trabajos de importación y exportación de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Como alternativa, muchas listas se pueden exportar a un archivo estático de Excel para facilitar una solicitud de portabilidad de datos.  Cuando los datos de cliente se exportan a Excel de esta forma, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml.

Tanto Dynamics 365 for Finance and Operations como ***Dynamics 365 for Talent*** ofrecen la característica "Informe de búsqueda de personas" para proporcionar al interesado la información que clasificó como datos personales. 

***Dynamics 365 Business Central*** ofrece estas características:

- Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)
- Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder a solicitudes de interesados relativas a registros generados por el sistema

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Datos de uso del servicio de productos, como registros de actividad de usuario.
- Solicitudes de búsqueda de usuarios y datos de consultas.
- Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acceder a registros generados por el sistema y exportarlos

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. Vaya al [Portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) e inicie sesión con las credenciales de un administrador global de Dynamics 365.
2. En la lista desplegable **Privacidad** de la parte superior de la página, haga clic en **Solicitud del titular de los datos**.
3. En la página **Solicitud del interesado**, en **Registros generados por el sistema**, haga clic en **Exportación de registros de datos**.
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. Para crear una solicitud para usuario, haga clic en **Crear solicitud de exportación de datos**.

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure facilita esto al permitir que su organización pueda exportar los datos en el formato JSON nativo al contenedor especificado de Azure Storage[. Introducción a Microsoft Azure Storage: Blob Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) (artículo). Los datos recuperados no incluirán datos que puedan comprometer la seguridad y estabilidad del servicio.

> [!IMPORTANT]
> Debe ser un administrador de espacios empresariales para exportar datos de usuario del espacio empresarial.

En la tabla siguiente, se resumen las acciones de acceso y exportación de registros generados por el sistema:

| | |
|:----|:---|
| | |
|**¿Cuánto tarda la herramienta Exportación de registros de datos de Microsoft en completar una solicitud?**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**¿Qué formato tendrá el resultado?**| El resultado serán archivos con formato de lectura mecánica estructurados, como XML, CSV o JSON. |
|**¿Qué datos devuelve la herramienta Exportación de registros de datos?**| La herramienta Exportación de registros de datos devuelve registros generados por el sistema almacenados por Microsoft. Los datos exportados pertenecen a varios servicios Microsoft, como Office 365, Azure y Dynamics. |
|***¿Quién tiene acceso a la herramienta Exportación de registros de datos para enviar solicitudes de acceso de registros generados por el sistema?**| Los administradores globales de Dynamics 365 tendrán acceso a la utilidad Administrador de registros del RGPD. |
|**¿Cómo se devuelven los datos al usuario?**| Los datos se exportarán a la ubicación de Azure Storage de su organización; los administradores de la organización tendrán que determinar cómo mostrarán o enviarán estos datos a los usuarios. |
|**¿Cuál será la apariencia de los datos en los registros generados por el sistema?**| Ejemplo de una entrada de registro generada por el sistema en formato JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Eliminar registros generados por el sistema

Para eliminar los registros generados por el sistema recuperados con una solicitud de acceso, necesita quitar el usuario del servicio y eliminar de forma permanente su cuenta de Active Directory de Azure. Para obtener instrucciones sobre cómo eliminar un usuario de forma permanente, vea la sección [Paso 5: Eliminar](gdpr-dsr-azure.md#step-5-delete) en el tema Solicitudes de los interesados de Azure. Es importante tener en cuenta que la eliminación permanente de una cuenta de usuario es irreversible una vez iniciada. Al eliminar de forma permanente una cuenta de usuario, en un plazo de 30 días se quitan los datos del usuario de los registros generados por el sistema de prácticamente todos los servicios de Dynamics 365, a excepción de los datos que pueden comprometer la seguridad o la estabilidad del servicio.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
