---
title: Solicitudes de Intune Data Subject para GDPR y CCPA
description: Obtenga información acerca de cómo encontrar datos personales, realizar acciones con ellos y responder a las solicitudes relacionadas con DSR y CCPA de los clientes que utilizan Microsoft Intune.
keywords: Microsoft 365, Educación de Microsoft 365, documentación de Microsoft 365, RGPD, CCPA
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: aef0b7e00e16c1632ff78b565e1ec8eef31481ee
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305310"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de Intune Data Subject para GDPR y CCPA

El [Reglamento de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas (que se denominan *interesados* en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *responsable de los datos* o simplemente *responsable*). Los datos personales se definen de forma amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro responsable. Las solicitudes formales realizadas por un interesado a un responsable para realizar una acción con sus datos personales se denominan *solicitudes de interesado* DSR, por sus siglas en inglés.

De manera similar, la Ley de privacidad del consumidor de California (CCPA), establece derechos y obligaciones de privacidad para los consumidores de California, incluyendo derechos similares a los Derechos de los sujetos de datos de la GDPR, como el derecho a borrar, acceder y recibir (portabilidad) su información personal.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Guía sobre cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar y actuar en datos personales con el fin de responder a las solicitudes de derechos del titular de los datos. En concreto, esta guía incluye cómo encontrar datos personales o información personal que residen en la nube de Microsoft, obtener acceso a los mismos y actuar sobre ellos. Este es un breve resumen de los procesos descritos en esta guía:

- **Búsqueda**: use herramientas de búsqueda y detección para encontrar más fácilmente los datos personales que pueden ser objeto de una solicitud de DSR. Una vez recopilados los documentos de respuesta, puede realizar una o varias de las acciones de DSR siguientes para responder a la solicitud. También puede determinar que la solicitud no cumple con las directrices de la organización para responder a las solicitudes de sujeto de datos.
- **Acceso:** recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.
- **Rectificación:** realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.
- **Restricción:** restrinja el tratamiento de datos personales, ya sea al quitar las licencias de distintos servicios de Azure o al desactivar los servicios que quiera, siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de manera local o en otra ubicación.
- **Eliminación:** elimine de forma permanente los datos personales que residen en la nube de Microsoft.
- **Exportar o recibir (portabilidad):** envíe una copia electrónica (en un formato legible por máquina) de datos o información personal al titular de los datos. La información personal bajo la CCPA es cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. La definición del término "información personal" es, a grandes rasgos, similar a la que el RGPD da al término "datos personales". Sin embargo, la CCPA también incluye datos domésticos y familiares. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización responsable de los datos para responder a una solicitud del interesado de datos personales en la nube de Microsoft.

#### <a name="terminology"></a>Terminología

En la siguiente lista, se proporcionan definiciones de términos relevantes para esta guía.

- **Poseedor:** la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable ("interesado"); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Datos de cliente:** todos los datos, incluidos todos los archivos de texto, sonido, vídeo o imagen, y software, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. Los datos del cliente incluyen tanto (1) información identificable de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) como el contenido del cliente que un cliente carga o crea en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, el contenido del cliente de Azure SQL Database o la imagen de la máquina virtual de un cliente en máquinas virtuales Azure).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios empresariales a los usuarios, pero que no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

#### <a name="how-to-use-this-guide"></a>Uso de esta guía

Esta guía consta de dos partes:

- **Parte 1: responda a las solicitudes de los datos de los clientes:** En la parte 1 de esta guía se explica cómo tener acceso a los datos, rectificarlos, restringirlos, eliminarlos y exportarlos desde aplicaciones en las que haya creado datos. En esta sección, se explica cómo ejecutar DSRs en el contenido de los clientes y también la información que puede identificar los usuarios finales.
- **Parte 2: Responder a las solicitudes de los sujetos de datos para los registros generados por el sistema:** Cuando se utilizan los servicios empresariales de Microsoft, Microsoft genera cierta información, conocida como registros generados por el sistema, con el fin de proporcionar el servicio. En la parte 2 de esta guía se explica cómo tener acceso, eliminar y exportar este tipo de información para Azure.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Comprender las solicitudes de interesados para Azure Active Directory y Microsoft Intune

Al plantear servicios proporcionados a clientes empresariales, siempre debe entenderse la ejecución de solicitudes de interesados en el contexto de un inquilino específico de Azure Active Directory. En concreto, este siempre se ejecuta en un inquilino determinado de Azure Active Directory. Si un usuario forma parte de varios inquilinos, es importante destacar que una solicitud de interesado *solo* se ejecuta en el contexto del inquilino específico que ha recibido la solicitud. El contexto es fundamental para comprender que la ejecución de una solicitud de interesado por parte de un cliente empresarial **no** afecta a los datos de otro cliente empresarial adyacente.

Lo mismo es válido en Microsoft Intune en el contexto de los servicios que presta un cliente empresarial: la ejecución de una solicitud de interesado de una cuenta de Intune *asociada a un cliente Azure Active Directory* **solo** estará relacionada con los datos del cliente. Además, es importante comprender lo siguiente al gestionar cuentas de Intune en un cliente:

- Si un usuario de Intune crea una suscripción de Azure, la suscripción se tratará como si fuera un inquilino de Azure Active Directory. Por lo tanto, las solicitudes de interesado se rastrean en el interior del cliente tal y como se ha descrito anteriormente.
- Si se elimina una suscripción de Azure creada con una cuenta de Intune, esta última **no se verá afectada**. Como se indicó anteriormente, las solicitudes de interesado que se ejecutan en la suscripción de Azure se limitan al ámbito del mismo inquilino.

Las solicitudes de interesados en una cuenta de Intune, **fuera de un determinado inquilino**, se ejecutan por medio del panel de privacidad del consumidor. Consulte la Guía de solicitud de datos de Windows para más información.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guía de solicitud de interesado para datos de cliente

### <a name="executing-dsrs-against-customer-data"></a>Ejecutar solicitudes de interesado en datos de cliente

Microsoft ofrece la posibilidad de acceder a determinados datos de cliente, eliminarlos y exportarlos a través de Azure Portal y también directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) existentes para servicios específicos (también denominados *experiencias de producto*). Los detalles sobre estas experiencias de producto se describen en la documentación de referencia de los servicios respectivos.

>[!IMPORTANT]  
>Los servicios que admiten DSR en el producto requieren el uso directo de una interfaz de programación de aplicaciones (API) o de una interfaz de usuario (UI) del servicio, que describa las operaciones CRUD (crear, leer, actualizar y eliminar) aplicables. Por lo tanto, la ejecución de una DSR en un servicio específico debe realizarse de manera adicional a la ejecución de una DSR en Azure Portal a fin de completar la solicitud de un interesado. Consulte la documentación de referencia de los servicios específicos para obtener más detalles.

### <a name="step-1-discover"></a>Paso 1: Detección

El primer paso para responder a una DSR consiste en encontrar los datos personales que se solicitan. Este primer paso, encontrar y revisar los datos personales, le ayudará a determinar si una DSR cumple los requisitos de la organización a fin de atenderla o rechazarla. Por ejemplo, después de encontrar y revisar los datos personales, puede determinar que la solicitud no cumple los requisitos de la organización porque darle curso puede afectar negativamente los derechos y libertades de terceros.

Tras encontrar los datos, puede realizar la acción específica para satisfacer la solicitud interesado. Consulte los siguientes recursos para obtener más detalles:

- [Recopilación de datos](https://docs.microsoft.com/intune/privacy-data-collect)
- [Procesamiento y almacenamiento de datos](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Ver datos personales](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Paso 2: Acceso

Una vez que haya encontrado datos de clientes que contengan datos personales que puedan corresponder a una DSR, dependerá de usted y de su organización decidir qué datos proporcionar al interesado. Puede proporcionarle una copia del documento, una versión con los datos censurados o una captura de pantalla con las porciones que considere adecuado compartir. Para cada una de estas respuestas a una solicitud de acceso, deberá recuperar una copia del documento u otro elemento que contenga los datos correspondientes.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.

A continuación se explica cómo obtener una copia de los datos en respuesta a una solicitud de acceso a los datos del interesado.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de productos que proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar las solicitudes de acceso al DSR. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluidos (a) información de identificación sobre un usuario final y (b) registros generados por el servicio.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft Intune permite [encontrar datos de clientes](#step-1-discover) directamente a través de interfaces de usuario (IU) o de interfaces de programación de aplicaciones (API) ya existentes.

### <a name="step-3-rectify"></a>Paso 3: Rectificar

Si un interesado le ha solicitado rectificar datos personales que se encuentran en los datos de la organización, usted y la organización deberán decidir si es adecuado atender dicha solicitud. Rectificar los datos puede requerir acciones como editar, censurar o eliminar datos personales de un documento u otro tipo de elemento.

Como encargado de los datos, Microsoft no ofrece la posibilidad de corregir los registros generados por el sistema, ya que reflejan actividades reales y constituyen un registro histórico de los eventos que han tenido lugar en los servicios Microsoft. En cuanto a Intune, los administradores no pueden actualizar la información específica de un dispositivo o una aplicación. Si un usuario final desea corregir algún dato personal (por ejemplo, el nombre del dispositivo), deberá hacerlo directamente en el dispositivo. Estos cambios se sincronizarán la próxima vez que el usuario se conecte a Intune.

### <a name="step-4-restrict"></a>Paso 4: Restricción

Los interesados pueden pedir que restrinja el procesamiento de sus datos personales. Proporcionamos tanto Azure Portal como interfaces de programación de aplicaciones (API) o interfaces de usuario (IU) ya existentes. Estas experiencias proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar esos DSR mediante una combinación de exportación y eliminación de datos. Para obtener más información vea[, procesamiento de datos personales](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

### <a name="step-5-delete"></a>Paso 5: Eliminar

El “derecho a la eliminación” de datos personales de los datos de cliente de una organización es una protección clave en el RGPD. Cuando se quitan datos personales, esto incluye todos los datos personales y los registros generados por el sistema, salvo la información de registros de auditoría. Para obtener detalles, consulte [Eliminación de los datos personales del usuario final](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>Parte 2: Registros generados por el sistema

Los registros de auditoría proporcionan a los administradores de inquilinos un registro de actividades que generan un cambio en Microsoft Intune. Hay registros de auditoría disponibles relativos a muchas actividades de administración y a las acciones habituales de creación, actualización (edición), eliminación y asignación. También se pueden revisar las tareas remotas que generan eventos de auditoría. Estos registros de auditoría pueden contener datos personales de los usuarios cuyos dispositivos están inscritos en Intune. Los administradores no pueden eliminar los registros de auditoría. Para obtener detalles, vea [Auditar datos personales](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación

Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
