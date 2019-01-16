---
title: Configuraciones de acceso de identidad y dispositivo - Microsoft 365 Enterprise
description: Se describen las recomendaciones de Microsoft y los conceptos básicos para implementar el correo electrónico seguro, documentos y las directivas de aplicaciones y configuraciones.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ea03143c7c42952ab6963d38ae44e79822d0b90a
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871180"
---
# <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

Esta serie de artículos describe cómo configurar el acceso seguro a los servicios de nube a través de movilidad en la empresa + productos de seguridad mediante la implementación de un entorno recomendado y la configuración, incluido un conjunto recomendado de las directivas de acceso condicional y capacidades de relacionados. Puede usar esta guía para proteger el acceso a todos los servicios que se integran con Azure Active Directory, incluidos los servicios de Office 365, otros servicios de SaaS y aplicaciones local publicaron con Proxy de aplicación de Azure AD. 

Estas recomendaciones se alinean con puntuación seguro de Microsoft así como [identidad puntuación en Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)y aumentarán estas puntuaciones para su organización. Estas recomendaciones también le ayudarán a implementar estos [cinco pasos para proteger la infraestructura de identidad](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps). 

Microsoft es consciente de que algunas organizaciones tienen requisitos de entorno único o complejidad. Si una de estas organizaciones, usar estas recomendaciones como punto de partida. Sin embargo, la mayoría de las organizaciones pueden implementar estas recomendaciones prescritos. 

## <a name="intended-audience"></a>Público objetivo

Estas recomendaciones están diseñadas para arquitectos de empresa y los profesionales de TI que están familiarizados con [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) y [Microsoft Enterprise movilidad + seguridad](http://microsoft.com/ems), que incluye, entre otros, Azure Active Directory (identidad), Microsoft Intune (administración de dispositivos) y la protección de información de Azure (protección de datos).

### <a name="customer-environment"></a>Entorno de cliente

Las directivas recomendadas son aplicables a las organizaciones empresariales operativo completamente dentro de la nube de Microsoft y para los clientes con la infraestructura híbrida (implementado local y la nube de Microsoft).

Muchas de las recomendaciones proporcionadas se basan en los servicios disponibles únicamente con empresa movilidad + licencias E5 de seguridad (EMS). Recomendaciones que presenta suponen las capacidades de licencia de EMS E5 completas.

Para las organizaciones que no disponen de movilidad en la empresa + licencias E5 de seguridad, Microsoft recomienda que al menos implementar capacidades de protección de línea de base de Azure AD que se incluyen con todos los planes. Puede encontrar más información en el artículo, [¿Qué es la protección de línea de base](/azure/active-directory/active-directory-conditional-access-baseline-protection), en la biblioteca de Azure AD.

### <a name="caveats"></a>Advertencias

Su organización puede estar sujeto a los requisitos de cumplimiento de normas legales o de otro, incluidas recomendaciones específicas que pueden requerir que se aplican las directivas que difieren de estas configuraciones recomendadas. Estas configuraciones recomienda controles de uso que históricamente no han sido disponibles. Estos controles, se recomienda porque pensamos que representan un equilibrio entre la seguridad y la productividad.  

Hemos hecho nuestro mejor para tener en cuenta para una amplia variedad de requisitos de protección organizativa, pero no podemos a cuenta para todos los requisitos posibles o para todos los aspectos exclusivos de su organización.

## <a name="three-tiers-of-protection"></a>Tres niveles de protección

La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento jurídico y los administradores de Office 365 pueden necesitar seguridad adicional y controles de protección de la información en torno a la correspondencia de correo electrónico que no son necesarios para usuarios de otras unidades de negocio. 

Cada industria también tiene su propio conjunto de reglamentos especializados. En lugar de proporcionar una lista de todas las opciones de seguridad posibles o una recomendación por función de segmento o trabajo del sector, se han proporcionado recomendaciones para tres diferentes niveles de seguridad y protección que se puede aplicar en función de la granularidad de sus necesidades .

- **Protección de línea de base**: se recomienda establecer un estándar mínimo para la protección de datos, así como las identidades y los dispositivos que tienen acceso a los datos. Puede seguir estas recomendaciones de línea base para proporcionar una protección seguro predeterminada que satisfaga las necesidades de muchas organizaciones.
- **Protección confidencial**: algunos clientes tienen un subconjunto de datos que se deben proteger en los niveles superiores, o bien es posible que requieren todos los datos que se deben proteger en un nivel superior. Puede aplicar una mayor protección a todos o establecen datos específicos en el entorno de Office 365. Se recomienda proteger las identidades y los dispositivos que tienen acceso a los datos confidenciales con comparables niveles de seguridad.  
- **Altamente regulado**: algunas organizaciones pueden tener una pequeña cantidad de datos que se clasificarán altamente, consititutes comerciales secretos o datos regulado. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida la protección se ha agregado para las identidades y dispositivos.

![Cono de seguridad - todos los clientes > algunos clientes > clientes específicos. Amplia aplicación en la aplicación específica](../images/M365-idquality-threetiers.png)

Esta guía muestra cómo implementar la protección de las identidades y dispositivos para cada uno de estos niveles de protección. Use esta guía como punto de partida para su organización y ajustar las directivas para satisfacer los requisitos específicos de su organización.

Es importante usar coherentes niveles de protección a través de los datos, las identidades y dispositivos. Por ejemplo, si implementa esta guía, asegúrese de proteger los datos en niveles comparables. Estos modelos de arquitectura muestran las características que estarán comparables.

**Protección de identidades y dispositivos para Office 365**<br/>
![Miniatura de póster "identidad y dispositivo protection para Office 365"](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)

**Soluciones de protección de archivos en Office 365**<br/>
![Miniatura de póster "Soluciones de protección de archivo en Office 365"](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad

Implementación de cualquier estrategia de seguridad requiere el equilibrio entre la seguridad y la productividad. Es útil evaluar cómo cada decisión afecta al saldo de seguridad, funcionalidad y facilidad de uso.

![Seguridad grupo de tres personas equilibrio de seguridad, funcionalidad y facilidad de uso.](media/policies-configurations/security-triad.png)

Las recomendaciones proporcionadas se basan en los siguientes principios:

- Conocer a la audiencia y ser flexible a sus requisitos funcionales y seguridad.
- Aplicar una directiva de seguridad en el momento y asegurarse de que es significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Protección de acceso a servicios y conceptos de identidad y dispositivos

Microsoft 365 Enterprise está diseñado para organizaciones de gran tamaño y se integra Office 365 Enterprise, creative Windows Enterprise 10 y movilidad en la empresa + seguridad (EMS), para permitir que todos y funcionan juntos de forma segura.

En esta sección se proporciona una visión general de los servicios de Microsoft 365 y las funcionalidades que son importantes para el acceso de identidad y de dispositivo.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD proporciona un completo conjunto de aplicaciones de identidad funcionalidades de administración. Para proteger el acceso, se recomienda usar las siguientes capacidades:

- **[Restablecimiento de contraseñas de autoservicio (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: permitir a los usuarios restablecer sus contraseñas de forma segura y sin la intervención del departamento de soporte técnico, proporcionando comprobación de varios métodos de autenticación que el administrador puede controlar.

- **[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: MFA requiere que los usuarios proporcionan dos formas de comprobación, como una contraseña de usuario además de una notificación de la aplicación Microsoft Authenticator o una llamada telefónica. MFA reduce en gran medida el riesgo de que puede ser una identidad robada utilizado para tener acceso a su entorno de Office 365.

- **[Acceso condicional](/azure/active-directory/conditional-access/overview)**: Azure AD evalúa las condiciones de inicio de sesión de usuario y usa directivas de acceso condicional que cree para permitir el acceso. Por ejemplo, en esta guía se explica cómo crear una directiva de acceso condicional para exigir el cumplimiento de dispositivo para el acceso a datos confidenciales. Esto reduce considerablemente el riesgo de que un intruso con una identidad robado puede obtener acceso a los datos confidenciales. También protege los datos confidenciales de los dispositivos, debido a que los dispositivos cumplan requisitos específicos para la salud y seguridad.

- **[Grupos de Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)**: las reglas de acceso condicional, administración de dispositivos con Intune e incluso permisos para archivos y sitios de la organización, se basan en asignación a usuarios o grupos de Azure AD. Se recomienda que crear grupos de Azure AD que corresponden a los niveles de protección que se va a implementar. Por ejemplo, su personal ejecutivo es probablemente mayor valor los objetivos de los intrusos. Por lo tanto, tiene sentido para asignar a estos empleados a un grupo de Azure AD y asignar a este grupo a las directivas de acceso condicional y otras directivas que exigen un mayor nivel de protección para el acceso.

- **[Registro de dispositivo](/azure/active-directory/devices/overview)**: registrar un dispositivo en Azure AD para proporcionar una identidad en el dispositivo. Esta identidad se utiliza para autenticar el dispositivo cuando un usuario inicia sesión en y se pueden aplicar las reglas de acceso condicional que requieren equipos unidos a un dominio o compatible. Para esta guía, usamos el registro de dispositivo para registrar automáticamente los equipos unidos a un dominio de Windows. Registro de dispositivo es un requisito previo para la administración de dispositivos con Intune. 

- **[Protección de la identidad de Azure AD](/azure/active-directory/identity-protection/overview)**: protección de la identidad de Azure AD le permite detectar posibles vulnerabilidades que afectan a las identidades de la organización y configurar la directiva de la corrección automatizada a bajo, medio y el inicio de sesión de alto riesgo y el riesgo de usuario. Esta guía se basa en esta evaluación de riesgos para aplicar las directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambiar su contraseña si se detecta actividad de alto riesgo por su cuenta.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) es el servicio de administración de dispositivo móvil basada en la nube de Microsoft. Esta guía recomienda la administración de dispositivos de Windows PCs con Intune y recomienda las configuraciones de directivas de cumplimiento de dispositivo. Intune determina si los dispositivos son compatibles con y envía estos datos a Azure AD a utilizar al aplicar las directivas de acceso condicional.

#### <a name="intune-app-protection"></a>Protección de aplicación Intune

Las directivas de [protección de aplicación Intune](https://docs.microsoft.com/intune/app-protection-policy) pueden utilizarse para proteger los datos de la organización en aplicaciones móviles, con o sin que se inscriben en administración de dispositivos. Intune ayuda a proteger la información de Office 365, asegurándose de que sus empleados aún pueden ser una pérdida de productividad y, a continuación, lo que impide datos. Mediante la implementación de directivas de nivel de aplicación, puede restringir el acceso a recursos de la compañía y mantener los datos bajo el control de su departamento de TI.

Esta guía le enseña a crear directivas recomendadas para exigir el uso de aplicaciones aprobadas y para determinar cómo estas aplicaciones pueden usarse con los datos profesionales.

### <a name="office-365"></a>Office 365

Esta guía muestra cómo implementar un conjunto de directivas para proteger el acceso a Office 365, como Exchange Online, SharePoint Online y OneDrive para la empresa. Además de implementar estas directivas, se recomienda que también eleva el nivel de protección para el inquilino de Office 365 con estos recursos:

- [Configure el inquilino de Office 365 para aumentar la seguridad](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): estas recomendaciones se aplican a la seguridad de línea de base para el inquilino de Office 365.
- [Guía de seguridad de office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): estas recomendaciones incluyen el registro, el gobierno de datos, acceso de administrador y protección contra amenazas.
- [Archivos y sitios de SharePoint Online seguro](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files): esta serie de artículos describe cómo proteger los archivos y los sitios en los niveles apropiados para la protección de línea de base, confidencial y altamente confidencial.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 y Office 365 ProPlus

10 de Windows y Office 365 ProPlus es el entorno de cliente que se recomienda para equipos. 10 de Windows, se recomienda como Azure está diseñada para proporcionar la experiencia más fluida posible para local y Azure AD. 10 de Windows también incluye capacidades avanzadas de seguridad que se pueden administrar mediante Intune. Office 365 ProPlus incluye las últimas versiones de las aplicaciones de Office. Estos usar autenticación moderna, que es más segura y un requisito para el acceso condicional. Estas aplicaciones también incluyen herramientas mejoradas de seguridad y cumplimiento de normas.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicar estas capacidades a través de tres niveles de protección

En la siguiente tabla se resume nuestras recomendaciones para el uso de estas capacidades a través de tres niveles de protección.

|Mecanismo de protección|Línea de base|Confidencial|Extremadamente regulado|
|:-------------------|:-------|:--------|:---------------|
|**Exigir MFA**|En riesgo de inicio de sesión medio o superior|En riesgo de inicio de sesión bajo o superior|En todas las sesiones nuevas|
|**Aplicar el cambio de contraseña**|Para los usuarios de alto riesgo|Para los usuarios de alto riesgo|Para los usuarios de alto riesgo|
|**Aplicar la protección de la aplicación Intune**|Sí|Sí|Sí|
|**Exigir la aplicación de inscripción Intune (COD)**|Requieren un equipo unido a un dominio o compatible con, pero permitir que los teléfonos y tabletas BYOD|Requiere un dispositivo compatible con o unido a un dominio|Requiere un dispositivo compatible con o unido a un dominio|

## <a name="device-ownership"></a>Propiedad del dispositivo

En la tabla anterior refleja la tendencia de muchas organizaciones admitir una mezcla de dispositivos que pertenecen corporativa, así como dispositivos personales o incorporar sus propias (BYODs) para permitir la productividad móvil a través de la mano de obra. Las directivas de protección de aplicación Intune Asegúrese de que el correo electrónico está protegido contra exfiltrating fuera de la aplicación móvil de Outlook y otras aplicaciones de Office móviles, en los dispositivos que pertenecen corporativo y BYODs.  

Se recomienda que pertenecen corporativo dispositivos ser administrada por Intune o Unidos a un dominio para aplicar protecciones adicionales y control. Dependiendo de la confidencialidad de datos, su organización puede optar por no permitir BYODs para grupos de usuarios específicos o aplicaciones específicas.

## <a name="next-steps"></a>Pasos siguientes

[Trabajo de requisitos previos para la implementación de directivas de acceso de identidad y dispositivos](identity-access-prerequisites.md)
