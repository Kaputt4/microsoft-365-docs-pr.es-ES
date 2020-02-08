---
title: Notificación de infracciones
description: Se explica cómo los servicios Microsoft protegen contra una infracción de datos personales y cómo Microsoft responde y le notifica si se produce una infracción.
keywords: Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: ffd5bd81542e2d39a928789c8575178c1b9a7633
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594430"
---
# <a name="gdpr-breach-notification"></a>Notificación de incumplimiento del RGPD

El Reglamento general de protección de datos (RGPD) añade nuevas normas para organizaciones que ofrecen bienes y servicios a los ciudadanos de la Unión Europea (UE) o que recopilan y analizan datos de los residentes de la UE, independientemente de donde estén ubicados usted o su empresa. Puede encontrar más información en el [tema de resumen del RGPD](gdpr.md).<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrZgG] 

Este documento le da información sobre la finalización de las notificaciones de incumplimiento en virtud del GDPR al usar productos y servicios de Microsoft.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>¿Qué constituye una vulneración de datos personales en virtud del RGPD?

Los datos personales se refieren a cualquier información relacionada con un usuario individual que pueda usarse para identificarlo directa o indirectamente. Una vulneración de datos personales es "una vulneración de seguridad que se traduce en la destrucción accidental o ilegal, pérdida, modificación, divulgación no autorizada o acceso a datos personales transmitidos, almacenados o procesados de alguna otra forma".

## <a name="terminology"></a>Terminología

Definiciones útiles de los términos del RGPD utilizados en este documento:

- *Controlador de datos (controlador)*: una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determinan el propósito y el medio del procesamiento de datos personales.  
- *Datos personales * e *interesado*: cualquier información relacionada con una persona física identificada o una persona natural identificable (interesado), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- *Procesador*: una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- *Datos de clientes*: datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="microsoft-and-breach-notification"></a>Microsoft y la notificación de incumplimiento

En Microsoft nos tomamos muy en serio nuestras obligaciones relativas al Reglamento general de protección de datos (RGPD). Un incidente de seguridad o vulneración de datos consiste en eventos como el acceso ilícito a los datos de los clientes almacenados en el equipo de Microsoft o en las instalaciones de Microsoft, o el acceso no autorizado a los mismos, que puede resultar en la pérdida, divulgación o alteración de los datos del cliente.

Al ser un procesador de datos, Microsoft garantiza que los clientes de servicios pueden cumplir los requisitos de notificación de incumplimiento del RGPD como controladores de datos. Nuestra notificación proporciona la información necesaria para realizar la valoración. Microsoft informa a los clientes de cualquier vulneración de datos personales, excepto los casos en los que se confirma que los datos personales son ininteligibles (por ejemplo, datos codificados de forma segura en los que se confirma la integridad de las claves).

Los controladores de datos son responsables de evaluar los riesgos relacionados con la privacidad de los datos y determinar si una vulneración requiere la notificación a la DPA de un cliente. Para realizar esa valoración, Microsoft proporciona la información necesaria, junto con su directiva de cumplimiento del RGPD.

La notificación inicial incluye una descripción de la naturaleza de la vulneración, el impacto aproximado del usuario y los pasos de mitigación (si procede). Si nuestra investigación no se completa en el momento de la notificación inicial, se indicarán los pasos y las escalas de tiempo para las comunicaciones subsiguientes. Para obtener más información sobre cómo Microsoft detecta y responde ante una vulneración de datos personales, vea [Notificación de vulneraciones de datos según el RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) en el Portal de confianza del servicio.

A continuación, se muestra información sobre las notificaciones de incumplimiento de productos y servicios específicos de Microsoft.
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invierte mucho en sistemas, procesos y personal para reducir la posibilidad de que se produzcan vulneraciones de datos personales y para detectar y mitigar rápidamente las consecuencias de las mismas en caso de que se produzcan. Puede leer información adicional en [Inversiones de Office 365 en seguridad de datos](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    Un cliente puede tener constancia de una vulneración y querer ponerse en contacto con Microsoft. En este caso, notifíquelo al Soporte técnico de Microsoft, que se comunicará con los equipos de ingeniería para obtener más información.

2. **[Azure y Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft tiene un servicio ininterrumpido y global de respuesta al incidente que sirve para reducir los efectos de los ataques en Microsoft Azure y Dynamics 365.

    - *Detección de vulneraciones*: ya que tanto Microsoft como el cliente tienen obligaciones de seguridad, los servicios de Azure usan un modelo de responsabilidad compartida para definir las responsabilidades operativas y de seguridad. Microsoft no supervisa ni responde a los incidentes de seguridad dentro del ámbito de responsabilidad del cliente. La respuesta a los incidentes del cliente puede implicar la colaboración con la [asistencia al cliente](https://azure.microsoft.com/support/options/) de Azure con contratos de servicio adecuados. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Security Center](https://azure.microsoft.com/services/security-center/)) que los clientes pueden usar para desarrollar y administrar la respuesta a incidentes de seguridad.

        Para obtener una lista de los eventos que activan una investigación de vulneración de Microsoft Azure, vea [Detección de vulneraciones potenciales](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure y la notificación de incumplimiento en virtud del RGPD](gdpr-breach-azure-dynamics.md) más información sobre cómo Microsoft investiga, administra y responde a incidentes de seguridad en Azure.

    - *Respuesta a la vulneración de datos*: Microsoft determina los niveles de prioridad y gravedad adecuados de una vulneración al investigar el impacto funcional, la capacidad de recuperación y el impacto de la información del incidente. La prioridad y la gravedad pueden cambiar a lo largo de la investigación, en función de nuevos resultados y conclusiones.
    El equipo de respuesta de seguridad de Microsoft trabaja en estrecha colaboración con consejeros jurídicos globales para asegurarse de que los informes forenses se realicen de acuerdo con las obligaciones y los compromisos jurídicos para los clientes. Estos procesos se detallan en la [Respuesta a la vulneración de datos de Azure](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Notificación al cliente*: Microsoft Azure envía notificaciones a los clientes y a las autoridades competentes de las vulneraciones de datos, según sea necesario. Los avisos a los clientes se entregan en no más de 72 horas desde el momento en que se declaró una vulneración, excepto en las siguientes circunstancias:

        - Microsoft cree que el acto de realizar una notificación aumentará el riesgo para otros clientes.
        - La línea de tiempo de 72 horas puede dejar algunos detalles del incidente disponibles. Se le proporcionarán a medida que avanza la investigación.

        Puede encontrar más detalles en [Notificación de cliente](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).

3. **[Soporte técnico y Servicios profesionales de Microsoft](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    La naturaleza de los servicios profesionales significa que algunos incidentes de protección de datos pueden estar dentro del ámbito de responsabilidad del cliente. Cuando los Servicios profesionales de Microsoft identifican un incidente relacionado con la protección de datos, se sigue el plan de respuesta estándar del sector documentado, tal como se describe en el [Ámbito y límites del proceso de respuesta a incidentes de protección de datos](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
