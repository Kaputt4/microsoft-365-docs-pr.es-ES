---
title: Solicitudes del interesado de Dynamics 365 para el RGPD y la CCPA
description: Esta guía le ayudará a comprender cómo encontrar y actuar en datos personales y responder a las solicitudes de DSR y CCPA realizadas por los clientes de Dynamics 365.
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
ms.openlocfilehash: e8a13821aaec16f66546f78be69394222ad5d41c
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44579195"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes del interesado de Dynamics 365 para el RGPD y la CCPA

El [Reglamento de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas (que en el reglamento se denominan *titulares de los datos*) para procesar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *poseedor de los datos* o *poseedor*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los titulares de los datos derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, la restricción de su procesamiento o eliminación, así como el envío en formato electrónico para su transferencia a otro poseedor de los datos. Las solicitudes formales realizadas por un titular de los datos a un poseedor de los datos para realizar una acción en sus datos personales se denominan en este documento *solicitudes de derechos del titular de los datos* o solicitudes DSR (por sus siglas en inglés).

De forma similar, la Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés), ofrece derechos y obligaciones de privacidad a los consumidores de California, incluyendo derechos similares a los Derechos del Sujeto de Datos de GDPR, como el derecho de eliminar, acceder y recibir (portabilidad) su información personal.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

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
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable (“titular de los datos”); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Datos de cliente:** todos los datos, incluidos todos los archivos de texto, sonido, vídeo o imagen, y software, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. En los datos de clientes, se incluye (1) información de identificación personal de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) y contenido del cliente cargado o creado por clientes en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, contenido del cliente de la base de datos de Azure SQL, o la imagen de la máquina virtual de un cliente en Azure Virtual Machines).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios a los usuarios, pero no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Modo en que esta guía puede servir para cumplir sus responsabilidades de poseedor

En la guía, dividida en dos partes, se describe cómo usar los productos, servicios y herramientas administrativas de Dynamics 365 para ayudarle a encontrar y actuar en datos en la nube de Microsoft en respuesta a las solicitudes realizadas por los interesados que deciden ejercer sus derechos según el RGPD. La primera parte trata los datos personales que se incluyen en los datos de clientes, seguido de una parte que trata otros datos personales anonimizados parcialmente capturados en los registros generados por el sistema.

- **Parte 1: Responder a solicitudes de derechos de los interesados sobre datos personales incluidos en datos de clientes.** En la parte 1 de esta guía, se explica cómo obtener acceso, rectificar, restringir, eliminar y exportar datos personales de aplicaciones de Dynamics 365 (software como servicio), que se tratan como parte de los datos de clientes que proporcionó el servicio en línea.
- **Parte 2: Responder a solicitudes de derechos de los interesados sobre datos anonimizados:** Cuando utiliza los servicios de Dynamics 365 Enterprise, Microsoft genera cierta información (denominada en este documento como *registros generados por el sistema*) para proporcionar el servicio, el cual está limitado a la superficie de uso que dejan los usuarios finales para identificar sus acciones en el sistema. Aunque estos datos no pueden atribuirse a un interesado específico sin el uso de información adicional, algunos pueden ser considerados personales dentro del RGPD. La parte 2 de esta guía trata acerca de cómo acceder a, eliminar y exportar registros generados por el sistema producidos por Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparar las investigaciones de derechos de los interesados

Cuando los titulares de los datos ejerzan sus derechos y realicen solicitudes, tenga en cuenta los siguientes puntos:

- Identifique correctamente la persona y el rol (por ejemplo, empleado, cliente, proveedores, etc.) con la información que el interesado le proporcionó como parte de su solicitud. Esta información podría ser un nombre, un id. de empleado o un número de cliente, o bien otro identificador.
- Anote la fecha y hora de la solicitud. (Dispone de 30 días para completar la solicitud).
- Confirme que la solicitud cumple con los requisitos de su organización para aceptar o rechazar una solicitud de titular de los datos. Por ejemplo, tiene que asegurarse de que, al ejecutar la solicitud, no se entre en conflicto con otras obligaciones legales, financieras o reglamentarias que tenga, ni infrinja los derechos o libertades de otros.
- Asegúrese de que posee la información relacionada con la solicitud.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Parte 1: Responder a las solicitudes de interesados relativas a datos personales incluidos en los datos de clientes

En los artículos siguientes, encontrará información útil para prepararse y responder a solicitudes de DSR sobre datos personales incluidos en los datos de clientes tratados en Dynamics 365. Es importante indicar que los datos personales podrían estar presentes en otras categorías de datos tratados por Microsoft durante la prestación del servicio de una suscripción de servicios en línea, como datos del administrador o datos de soporte técnico definidos en la Declaración de privacidad de Microsoft. Este documento se limita a asistirle en el proceso de detección y administración de solicitudes de DSR que afecten a los datos personales presentes en los datos de clientes proporcionó a Dynamics 365.

Dynamics 365 es un servicio en línea que ofrece varias funciones de procesamiento de datos como software como servicio (SaaS). Como tal, Dynamics 365 ofrece una amplia variedad de funciones cuya intención es procesar una colección de datos diversa, que podrían variar en naturaleza, finalidad u otros atributos específicos, como datos de ventas, transacciones, operaciones financieras, información de recursos humanos, etc. En virtud de esta diversidad, Dynamics 365 ofrece distintos formularios, campos, esquemas, puntos de conexión y lógicas para procesar datos de cliente, que también se reflejan en las distintas formas en que podrían tratarse las DSR en cada aplicación. Cuando las aplicaciones de Dynamics 365 ofrezcan distintas formas de tratar solicitudes DSR específicas, las indicaremos en esta guía señalando las descripciones técnicas ofrecidas por cada aplicación.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Buscar los datos de cliente

El primer paso para responder a una solicitud de derechos del titular de los datos es buscar e identificar los datos de cliente que sean el objeto de la solicitud.

Clasificar correctamente los datos de clientes resulta esencial para trabajar con datos personales en las aplicaciones empresariales de Dynamics 365 for Customer Engagement. Dynamics 365 for Customer Engagement ofrece flexibilidad para crear una extensión de aplicación en torno a la clasificación de datos. Una clasificación adecuada le permitirá identificar información como datos personales y, por lo tanto, permite buscarlos y recuperarlos al responder a solicitudes del titular de los datos. También puede facilitar el cumplimiento de requisitos legales y reglamentarios relacionados con la recopilación y el tratamiento de datos personales.

Microsoft proporciona funciones que le ayudan a responder a solicitudes de derechos de los interesados y, por lo tanto, a obtener acceso a datos de clientes. Pero es su responsabilidad garantizar que los datos personales se clasifiquen y organicen correctamente.

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

Además, para Dynamics 365 for Marketing, se proporciona una [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) que permite a los clientes crear extensiones que recuperan registros adicionales de interacciones de clientes registradas que pueden contener datos personales. La API carga toda la información relevante del sistema back-end y la combina en un único documento portátil.

***Dynamics 365 Customer Service Insights***, le permite [proporcionar una copia de los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) mediante exportación de datos.

Los datos de clientes en ***Dynamics 365 for Finance and Operations*** se pueden exportar con las completas funciones de exportación de entidades. Con [*Entidades de integración y administración de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), el administrador del espacio empresarial puede usar las entidades proporcionadas, crear entidades o ampliar las entidades de una exportación de datos personales repetible a Excel, o bien a otros formatos comunes con [*Trabajos de importación y exportación de datos*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Como alternativa, muchas listas se pueden exportar a un archivo estático de Excel para facilitar una solicitud de portabilidad de datos.  Cuando los datos del cliente se exportan a Excel, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml. También puede usar el *Informe de búsqueda de personas* para proporcionar al interesado aquellos datos que clasificó como personales.

En ***Dynamics 365 Business Central***, puede usar dos características para proporcionar una copia de los datos del cliente a un titular de los datos:

Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)

En ***Dynamics 365 for Talent***, puede usar el [Informe de búsqueda de personas extendido](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) para recopilar información relacionada con una solicitud de copia de los datos personales del titular de los datos.

### <a name="rectifying-customer-data"></a>Rectificar los datos de cliente

***Dynamics 365 for Customer Engagement*** le ofrece los métodos siguientes para corregir datos de clientes incompletos o imprecisos, o bien para borrar los datos de clientes:

- Busque datos de clientes con las funciones indicadas en “Buscar datos de clientes”, y edite directamente los datos en formularios de interacción con clientes. Las ediciones se pueden realizar en una única fila, o bien puede modificar varias filas directamente.
- Al editar de forma masiva varios registros de interacciones con clientes, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel en Dynamics 365 for Customer Engagement.

Además, para Dynamics 365 for Marketing, también puede:

- Actualizar la página de destino de actualización de datos personales, al editar una o varias filas directamente.
- Preparar la página [Centro de suscripciones](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center), con todos los campos de contacto editables que se puedan incluir. Esto permite a un usuario final actualizar su propia información en la medida de lo posible.

***Dynamics 365 Customer Service Insights*** también ofrece funcionalidades que permiten a las organizaciones [rectificar o hacer cambios en los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary).

En ***Dynamics 365 for Finance and Operations***, también puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), pero la decisión y la implementación son su responsabilidad.

***Dynamics 365 Business Central*** ofrece dos formas de corregir datos de clientes incompletos o imprecisos.

Para editar de forma masiva y rápidamente varios registros de Business Central, puede exportar listas a Excel con el [complemento de Excel de Business Central](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para corregir varios registros y, después, puede publicar los datos modificados desde Excel en Business Central. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Para cambiar los datos de clientes almacenados en cualquier campo (por ejemplo, información sobre un cliente en la tarjeta Cliente), edite de forma manual el elemento de datos que contiene los datos personales de destino. Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota breve sobre cómo modificar las entradas de las transacciones comerciales

Los registros transaccionales (como entradas generales, de cliente y del libro de retención de impuestos) son esenciales para garantizar la integridad de un sistema de planeamiento de recursos empresariales. Los datos personales que pertenecen a una transacción financiera (o de otro tipo) se mantienen “tal cual” con fines de cumplimiento con leyes financieras (por ejemplo, leyes tributarias), prevención del fraude (como una traza de auditoría de seguridad) o con certificaciones del sector. Por lo tanto, Dynamics 365 for Finance and Operations y Dynamics 365 Business Central restringen la modificación de datos en esos registros.

Si almacena datos personales en registros de transacciones empresariales, la única forma de corregir, eliminar o restringir el procesamiento de datos personales para aceptar una solicitud del titular de los datos es usar las [funciones de personalización](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index) de Dynamics 365 Business Central. La [](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)decisión de aceptar una solicitud del titular de los datos de modificación, así como su implementación posterior, es su responsabilidad.

### <a name="restricting-the-processing-of-customer-data"></a>Restringir el tratamiento de datos de cliente

Al recibir la solicitud de un titular de los datos para restringir el procesamiento de datos de clientes, puede extraer fácilmente los datos de clientes afectados desde servicio en línea y almacenarlos en un contenedor separado (es decir, un almacenamiento local o un servicio web separado con funciones de aislamiento de datos) aislado de las funciones de procesamiento ofrecidas por cualquier aplicación de nube.

***Dynamics 365 Business Central*** ofrece un mecanismo alternativo, como el bloque de procesamiento de datos, donde se permite a los usuarios bloquear datos específicos en el registro del titular de los datos. Para obtener más información, vea [Restringir el procesamiento de datos de un titular de los datos](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Cuando un registro se marca como bloqueado, Dynamics 365 Business Central dejará de procesar los datos de cliente de ese titular de los datos. No se pueden crear transacciones que usen un registro bloqueado; por ejemplo, no puede crear una factura para un cliente cuando el cliente o el comercial están bloqueados.

### <a name="deleting-customer-data"></a>Eliminar datos de cliente

Si un titular de los datos le pide que elimine sus datos de cliente, hay varias formas de hacerlo:

- Con la edición masiva de varios registros de Dynamics 365, puede usar el complemento de Microsoft Office para exportar datos a Microsoft Excel, realizar los cambios y, después, importar esos datos modificados desde Excel el servicio en línea.
- Puede eliminar los datos de cliente almacenados en cualquier campo; para hacerlo, busque los datos que quiera eliminar y, elimine de forma manual el elemento de datos que contenga los datos de cliente de destino. Por ejemplo, puede usar una eliminación permanente en el registro del contacto que represente el titular de los datos y otros registros que contengan datos personales

Además, en Dynamics 365 Marketing, al eliminar un contacto, se asegurará de que se quiten también los datos de interacciones con información personal. Para cualquier entidad o campo personalizado, necesita personalizar el sistema para asegurarse de que se eliminen todos los datos de cliente de los registros relacionados, o bien que se desvinculen del registro del contacto para que pueda quitarse toda la información personal. Más información: [Guía para desarrolladores (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** también ofrece a las organizaciones funcionalidades para [borrar los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Como alternativa, en ***Dynamics 365 for Finance and Operations***, puede usar [*herramientas de personalización*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) para borrar o modificar datos de cliente.

En ***Dynamics 365 Business Central***, cuando un titular de los datos le pide que elimine sus datos personales y estos se incluyen en los datos de cliente, hay varias formas de procesar la solicitud:

- Para editar de forma masiva rápidamente varios registros de Business Central, puede exportar los datos a Excel con el [complemento de Excel de Business Central](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para eliminar varios registros y, después, puede publicar esos cambios desde Excel en Business Central. Para obtener más información, vea [Exportar sus datos empresariales a Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Puede eliminar los datos de cliente almacenados de forma manual en cualquier campo; para hacerlo, elimine el elemento de datos que contenga los datos de cliente de destino.  Para obtener más información, vea [Entrada de datos](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Puede eliminar directamente los datos de cliente, por ejemplo, si elimina un contacto y ejecuta el trabajo por lotes de eliminación de entradas de registro de interacciones canceladas con el fin de eliminar las interacciones de ese contacto.
- Puede [eliminar documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) que contengan datos de cliente (por ejemplo, memorandos, ventas contabilizadas y facturas de compra).

Además de la eliminación masiva o individual de registros específicos, tenga en cuenta que, desde ***Dynamics 365 for Talent***, solo se pueden eliminar por completo los empleados cesados. [Siga este procedimiento para eliminar los empleados cesados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportar datos de cliente

Para responder a una solicitud de portabilidad de datos, en ***Dynamics 365 for Customer Engagement*** se pueden exportar los datos de cliente con las completas funciones de exportación de entidades. Los datos de clientes se pueden exportar a un archivo de Excel estático para facilitar una solicitud de portabilidad de datos. Con Excel puede editar los datos personales que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml.

Además, para Dynamics 365 for Marketing, se proporciona una [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) que permite a los clientes crear extensiones que recuperan registros adicionales de interacciones de clientes registradas que pueden contener datos personales. La API carga toda la información relevante del sistema back-end y la combina en un único documento portátil.

Para ***Dynamics 365 Customer Service Insights***, [exporte los datos del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) a través del portal de administración de Azure. 

***Dynamics 365 for Finance and Operations*** ofrece [Entidades de integración y administración de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), que permiten a las entidades proporcionadas, las nuevas entidades o las entidades extendidas exportar datos personales de forma repetida a Excel o a otros formatos comunes con [Trabajos de importación y exportación de datos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Como alternativa, muchas listas se pueden exportar a un archivo estático de Excel para facilitar una solicitud de portabilidad de datos.  Cuando los datos de cliente se exportan a Excel de esta forma, puede editar los datos personales que se incluirán en la solicitud de portabilidad y, después, guardar el archivo con un formato de lectura mecánica de uso habitual, como .csv o .xml.

Tanto Dynamics 365 for Finance and Operations como ***Dynamics 365 for Talent*** ofrecen la característica "Informe de búsqueda de personas" para proporcionar al interesado la información que clasificó como datos personales. 

***Dynamics 365 Business Central*** ofrece estas características:

- Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)
- Puede exportar los datos del cliente a un archivo de Excel. En Excel puede editar los datos del cliente que se incluirán en la solicitud de portabilidad y guardarlo en un formato de lectura mecánica de uso habitual, como .csv o .xml. Para obtener más información, vea [Exportar los datos profesionales a Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder a solicitudes de interesados relativas a registros generados por el sistema

Microsoft también le permite obtener acceso, exportar y eliminar registros generados por el sistema que pueden considerarse como datos personales según la definición amplia del RGPD de “datos personales”. Estos son algunos ejemplos de registros generados por el sistema que pueden considerarse como datos personales según el RGPD:

- Datos de uso del servicio de productos, como registros de actividad de usuario.
- Solicitudes de búsqueda de usuarios y datos de consultas.
- Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.

No se admite la capacidad de restringir o rectificar datos en los registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico, y modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría el fraude y los riesgos de seguridad.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acceder a registros generados por el sistema y exportarlos

Los administradores pueden obtener acceso a registros generados por el sistema asociados con el uso de un usuario específico de las aplicaciones y servicios de Dynamics 365. Para obtener acceso a los registros generados por el sistema y exportarlos:

1. Vaya al [Portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) e inicie sesión con las credenciales de un administrador global de Dynamics 365.
2. En la lista desplegable **Privacidad** de la parte superior de la página, haga clic en **Solicitud del titular de los datos**.
3. En la página **Solicitud del interesado**, en **Registros generados por el sistema**, haga clic en **Exportación de registros de datos**.
    > [!NOTE]
    > Se mostrará la pantalla **Exportación de registros de datos**. Se mostrará una lista de las solicitudes de datos de exportación enviadas por su organización.
4. Para crear una solicitud para usuario, haga clic en **Crear solicitud de exportación de datos**.

Después de crear una solicitud, se mostrará en la página **Exportación de registros de datos**, donde puede realizar un seguimiento de su estado. Después de completar una solicitud, puede hacer clic en un vínculo para obtener acceso a los registros generados por el sistema, que se exportarán a la ubicación de Azure Storage de su organización en un plazo de 30 días después de crear la solicitud. Los datos se guardarán en formatos de archivo de lectura mecánica comunes, como JSON o XML. Si no tiene una cuenta de Azure ni una ubicación de Azure Storage, tendrá que crear una cuenta de Azure o una ubicación de Azure Storage para su organización para que la herramienta Exportación de registros de datos pueda exportar los registros generados por el sistema.

Azure facilita esto al permitir que su organización pueda exportar los datos en el formato JSON nativo al contenedor especificado de Azure Storage[. Introducción a Microsoft Azure Storage: Blob Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) (artículo). Los datos recuperados no incluirán datos que puedan comprometer la seguridad y estabilidad del servicio.

> [!IMPORTANT]
> Debe ser un administrador de espacios empresariales para exportar datos de usuario del espacio empresarial.

En la tabla siguiente, se resumen las acciones de acceso y exportación de registros generados por el sistema:

| | |
|:----|:---|
| | |
|**¿Cuánto tarda la herramienta Exportación de registros de datos de Microsoft en completar una solicitud?**| Esto puede depender de varios factores. En la mayoría de los casos, suele completarse en uno o dos días, pero puede tardar hasta 30 días. |
|**¿Qué formato tendrá el resultado?**| El resultado serán archivos con formato de lectura mecánica estructurados, como XML, CSV o JSON. |
|**¿Qué datos devuelve la herramienta Exportación de registros de datos?**| La herramienta Exportación de registros de datos devuelve registros generados por el sistema almacenados por Microsoft. Los datos exportados pertenecen a varios servicios Microsoft, como Office 365, Azure y Dynamics. |
|***¿Quién tiene acceso a la herramienta Exportación de registros de datos para enviar solicitudes de acceso de registros generados por el sistema?**| Los administradores globales de Dynamics 365 tendrán acceso a la utilidad Administrador de registros del RGPD. |
|**¿Cómo se devuelven los datos al usuario?**| Los datos se exportarán a la ubicación de Azure Storage de su organización; los administradores de la organización tendrán que determinar cómo mostrarán o enviarán estos datos a los usuarios. |
|**¿Cuál será la apariencia de los datos en los registros generados por el sistema?**| Ejemplo de una entrada de registro generada por el sistema en formato JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Eliminar registros generados por el sistema

Para eliminar los registros generados por el sistema recuperados con una solicitud de acceso, necesita quitar el usuario del servicio y eliminar de forma permanente su cuenta de Active Directory de Azure. Para obtener instrucciones sobre cómo eliminar un usuario de forma permanente, vea la sección [Paso 5: Eliminar](gdpr-dsr-azure.md#step-5-delete) en el tema Solicitudes de los interesados de Azure. Es importante tener en cuenta que la eliminación permanente de una cuenta de usuario es irreversible una vez iniciada. Al eliminar de forma permanente una cuenta de usuario, en un plazo de 30 días se quitan los datos del usuario de los registros generados por el sistema de prácticamente todos los servicios de Dynamics 365, a excepción de los datos que pueden comprometer la seguridad o la estabilidad del servicio.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
