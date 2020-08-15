---
title: Responsabilidades de continuidad empresarial de Enterprise de clientes y partners de la nube
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre las acciones que Microsoft realiza durante una incidencia en el servicio para que pueda preparar mejor sus planes de continuidad empresarial.
ms.openlocfilehash: 5486ad2ae8c2e5d97b466a8cbd2a4dbab416b29b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686123"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>Responsabilidades de clientes y partners de la nube de administración de continuidad empresarial de Enterprise

Hacer llegar los servicios en la nube de Microsoft 365 a sus usuarios supone una colaboración entre su organización y Microsoft. Microsoft proporciona los servicios y usted es el responsable de conectarse a los puntos de conexión del cliente, administrar la identidad y el acceso y cómo se usan estos servicios. También hay responsabilidades compartidas, como la infraestructura de identidades y directorios. Este artículo trata algunos de los elementos críticos que necesita conocer para mantener su empresa en funcionamiento en caso de que se produzca una incidencia en el servicio y le ayuda a establecer las expectativas sobre lo que realizará Microsoft durante una incidencia en el servicio.

## <a name="transparency-during-service-incidents"></a>Transparencia durante incidencias en el servicio

Como partner de confianza, Microsoft ofrece servicios en la nube muy resilientes y sigue procedimientos estructurados para resolver las incidencias en el servicio cuando se producen. Cuando se produce una incidencia en el servicio, Microsoft es consciente de que una comunicación **inmediata**, **dirigida al interlocutor adecuado** y **de elevada disponibilidad** resulta fundamental para los clientes.

## <a name="timely"></a>Inmediata
Microsoft informa a los administradores de Office 365 mediante la actualización en el portal de administración de Office 365 del panel de estado del servicio (SHD) específico para sus inquilinos. Normalmente, las actualizaciones de incidencias en el servicio se proporcionan cada hora. Si es necesaria una frecuencia diferente, le mantendremos informado en las publicaciones de comunicación del panel de estado del servicio.

## <a name="targeted"></a>Dirigida
En la mayoría de los casos, cuando nuestros sistemas de supervisión detectan un problema, podemos identificar la base de clientes afectada, desde un único cliente hasta la región correspondiente, o incluso más, y dirigir las comunicaciones necesarias a esos clientes. Esto le ayudará a conocer lo que necesita para su empresa y a que no se distraiga por notificaciones irrelevantes que no les afecten. Por ejemplo, si se ve afectada una base de datos de buzones específica, podemos identificar exactamente qué clientes tienen usuarios en la infraestructura afectada y definir el ámbito de las comunicaciones. Si el alcance de la incidencia no está claro, ampliamos las comunicaciones al grupo más amplio de clientes que puedan verse afectados.

## <a name="highly-available"></a>Alta disponibilidad
Microsoft mantiene varios canales para las comunicaciones de estado del servicio que los clientes pueden usar.

- En caso de que el centro de administración o el panel de estado del servicio del centro de administración no estén disponibles, puede supervisar el estado del servicio con nuestro [sitio de copia de seguridad](https://status.office365.com/).
- Disponemos de una cuenta de Twitter [@MSFT365Status](https://twitter.com/msft365status?lang=en) en la que responderemos a los informes sobre el impacto y las actualizaciones posteriores sobre eventos que afecten al panel de estado del servicio.
- La aplicación de administración para administradores de inquilinos de Microsoft 365 le proporciona la capacidad de conectarse al estado del servicio de Microsoft 365 de su organización desde cualquier lugar. Los administradores de inquilinos tendrán la posibilidad de ver desde sus dispositivos móviles las actualizaciones de estado de mantenimiento e información de estado del servicio. Para obtener más información, visite la [Preguntas más frecuentes (FAQ) de la aplicación de administración](https://docs.microsoft.com/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide).
- La [API de comunicaciones de servicio de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) le permite tener acceso a las comunicaciones de servicio para que pueda supervisar su entorno más fácilmente. Puede conectarse a la API, recibir datos de estado del servicio en tiempo real y publicar la información en un panel interno para informar a los usuarios de la empresa sobre incidencias. La distribución de la información de forma interna puede disminuir el tráfico del departamento de soporte técnico durante una interrupción.
- Para incidencias importantes, Microsoft publica revisiones posteriores a las incidencias (PIR) en el panel de estado del servicio (SHD) del centro de administración. Las PIR contienen información clave de la incidencia para ayudarle a comprender la naturaleza de la interrupción. Generalmente, contienen las secciones siguientes:
    - impacto en el usuario
    - alcance del impacto
    - fecha y hora de inicio de la incidencia
    - causa principal
    - acciones realizadas
    - siguientes pasos
- La comunicación auxiliar está disponible en el centro de mensajes de Microsoft 365, como avisos de los próximos cambios, nuevas características o mantenimiento planeado.
- Para obtener más información, consulte [la guía de estado y continuidad del servicio](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) para obtener más información sobre los diferentes canales de comunicación y cómo supervisar el estado del servicio.
 
Proporcionar acceso a los servicios en línea de Microsoft 365 supone una colaboración entre su organización y Microsoft. En el gráfico siguiente se resume el equilibrio de las responsabilidades de Microsoft y del cliente durante una incidencia en el servicio y durante las operaciones habituales.

![equilibrio de responsabilidades de clientes y Microsoft](../media/ebcm/responsibilities.png)

## <a name="your-environment---service-continuity"></a>El entorno: continuidad del servicio
Cuando piense en su plan de continuidad, tenga en cuenta los eventos que pueden afectar a su organización y su capacidad global de comunicación. A un alto nivel, hay tres factores que pueden afectar a su empresa.

### <a name="people"></a>Personas
Considere eventos que podrían afectar a sus empleados como un desastre natural o un pandemia. Esto se suele pasar por alto, ya que es improbable que se produzca un impacto a gran escala en caso de que los empleados estén muy distribuidos. Sin embargo, si un gran porcentaje de los trabajadores está fuera de la oficina, ¿su empresa seguiría funcionando? ¿Cómo se puede mitiga esto?

### <a name="location"></a>Ubicación
Muchas organizaciones necesitan que los empleados estén en ubicaciones de red o físicas específicas para conectarse a los servicios empresariales y en la nube.  
Microsoft publica los[principios de conectividad de red](microsoft-365-network-connectivity-principles.md) que guían a las empresas a través de procedimientos recomendados para configurar la conectividad de red a los recursos de la nube. Algunos ejemplos de optimización son la implementación de VPN de túnel dividido para permitir conexiones directamente desde la red de un usuario, en lugar de hacerlo por un túnel VPN.  Mientras que estos principios de conectividad son importantes para el mantenimiento de las conexiones de baja latencia, la resiliencia del servicio requiere métodos alternativos para conectarse a los recursos corporativos para una colaboración general.

### <a name="systems"></a>Sistemas
Muchas soluciones de colaboración dependen de sistemas, como la red de área extensa (WAN) de la empresa. Cuando estos sistemas no estén disponibles, cómo responderá su organización?
Este gráfico representa los problemas que pueden afectar a más de un área. En la tabla adjunta se ofrecen ejemplos que debe tener en cuenta

![diagrama de Venn](../media/ebcm/venn-diagram.png)

Sus planes de continuidad deben tener en cuenta cada una de estas áreas. Por ejemplo: Si necesita que los usuarios estén en la red corporativa y hay una tormenta de nieve, ¿cómo tienen estos usuarios acceso a los recursos clave? Si la nieve impide que lleguen a la oficina y se necesita que los ingenieros de mantenimiento conecten la red corporativa, ¿hay alguna directiva que les exige tener sus equipos portátiles corporativos en su poder en casa?
