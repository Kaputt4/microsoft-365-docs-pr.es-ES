---
title: Solicitudes de Intune Data Subject para GDPR y CCPA
description: Obtenga información acerca de cómo encontrar datos personales, realizar acciones con ellos y responder a las solicitudes relacionadas con DSR y CCPA de los clientes que utilizan Microsoft Intune.
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
ms.custom:
- seo-marvel-mar2020
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9dd161edd740aa97e97afa02a6c53933a6ac211
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817659"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de Intune Data Subject para GDPR y CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.

De forma similar, la Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés), ofrece derechos y obligaciones de privacidad a los consumidores de California, incluyendo derechos similares a los Derechos del Interesado de GDPR, como el derecho de eliminar, acceder y recibir (portabilidad) su información personal.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Guía sobre cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar y actuar en datos personales con el fin de responder a las solicitudes de derechos del titular de los datos. En concreto, esto incluye cómo encontrar, obtener acceso y actuar sobre datos personales o información personal que residen en la nube de Microsoft. Este es un breve resumen de los procesos descritos en esta guía:

- **Búsqueda**: use herramientas de búsqueda y detección para encontrar más fácilmente los datos personales que pueden ser objeto de una solicitud de DSR. Una vez recopilados los documentos de respuesta, puede realizar una o varias de las acciones de DSR siguientes para responder a la solicitud. También puede determinar que la solicitud no cumple con las directrices de la organización para responder a las solicitudes de sujeto de datos.
- **Acceso:** recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.
- **Rectificación:** realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.
- **Restricción:** restrinja el tratamiento de datos personales, ya sea al quitar las licencias de distintos servicios de Azure o al desactivar los servicios que quiera, siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de manera local o en otra ubicación.
- **Eliminación:** elimine de forma permanente los datos personales que residen en la nube de Microsoft.
- **Exportar o recibir (portabilidad):** envíe una copia electrónica (en un formato legible por máquina) de datos o información personal al titular de los datos. La información personal bajo la CCPA es cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. La definición de la CCPA de la "información personal" es a grandes rasgos similar a la que el RGPD hace de los "datos personales". Sin embargo, la CCPA también incluye datos domésticos y familiares. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización responsable de los datos para responder a una solicitud del interesado de datos personales en la nube de Microsoft.

#### <a name="terminology"></a>Terminología

A continuación se ofrecen definiciones de términos relacionados con esta guía.

- **Poseedor:** la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable ("interesado"); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Datos de cliente:** todos los datos, incluidos todos los archivos de texto, sonido, vídeo o imagen, y software, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. Los datos del cliente incluyen tanto (1) información identificable de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) como el contenido del cliente que un cliente carga o crea en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, el contenido del cliente de Azure SQL Database o la imagen de la máquina virtual de un cliente en máquinas virtuales Azure).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios a los usuarios, pero no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

#### <a name="how-to-use-this-guide"></a>Uso de esta guía

Esta guía consta de dos partes:

- **Parte 1: responda a las solicitudes de los datos de los clientes:** En la parte 1 de esta guía se explica cómo tener acceso a los datos, rectificarlos, restringirlos, eliminarlos y exportarlos desde aplicaciones en las que haya creado datos. En esta sección, se explica cómo ejecutar DSRs en el contenido de los clientes y también la información que puede identificar los usuarios finales.
- **Parte 2: Responder a las solicitudes de los sujetos de datos para los registros generados por el sistema:** Cuando se utilizan los servicios empresariales de Microsoft, Microsoft genera cierta información, conocida como registros generados por el sistema, con el fin de proporcionar el servicio. En la parte 2 de esta guía se explica cómo tener acceso, eliminar y exportar esta información para Azure.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Comprender las solicitudes de interesados para Azure Active Directory y Microsoft Intune

When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.

The same also applies for Microsoft Intune provided to an enterprise customer: execution of a DSR against an Intune account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling Intune accounts within a tenant:

- If an Intune user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.
- If an Azure subscription created via an Intune account is deleted, **it will not affect** the actual Intune account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.

DSRs against an Intune account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guía de solicitud de interesado para datos de cliente

### <a name="executing-dsrs-against-customer-data"></a>Ejecutar solicitudes de interesado en datos de cliente

Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services' reference documentation.

>[!IMPORTANT]  
>Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.

### <a name="step-1-discover"></a>Paso 1: Detección

The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.

After you find the data, you can then perform the specific action to satisfy the request by the data subject. For details, see the following:

- [Recopilación de datos](https://docs.microsoft.com/intune/privacy-data-collect)
- [Procesamiento y almacenamiento de datos](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Ver datos personales](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Paso 2: Acceso

After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.

A continuación se explica cómo obtener una copia de los datos en respuesta a una solicitud de acceso a los datos del interesado.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de productos que proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar las solicitudes de acceso al DSR. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el servicio.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft Intune permite [encontrar datos de clientes](#step-1-discover) directamente a través de interfaces de usuario (IU) o de interfaces de programación de aplicaciones (API) ya existentes.

### <a name="step-3-rectify"></a>Paso 3: Rectificar

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Intune, admins can't update device or app specific information. If an end user wants to correct any personal data (like the device name), they must do so directly on their device. Such changes are synchronized the next time they connect to Intune.

### <a name="step-4-restrict"></a>Paso 4: Restricción

Los interesados pueden pedir que restrinja el procesamiento de sus datos personales. Proporcionamos tanto Azure Portal como interfaces de programación de aplicaciones (API) o interfaces de usuario (IU) ya existentes. Estas experiencias proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar esos DSR mediante una combinación de exportación y eliminación de datos. Para obtener más información vea[, procesamiento de datos personales](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

### <a name="step-5-delete"></a>Paso 5: Eliminar

The "right to erasure" by the removal of personal data from an organization's Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see [Delete end user personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>Parte 2: Registros generados por el sistema

Audit logs provide tenant admins with a record of activities that generate a change in Microsoft Intune. Audit logs are available for many manage activities and typically create, update (edit), delete, and assign actions. Remote tasks that generate audit events can also be reviewed. These audit logs may contain personal data from users whose devices are enrolled in Intune. Admins can't delete audit logs. For details, see [Audit personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación

Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
