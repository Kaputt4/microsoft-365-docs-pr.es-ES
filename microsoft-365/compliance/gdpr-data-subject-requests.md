---
title: Solicitudes de los temas de datos del RGPD y CCPA
description: ''
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: fc5f4f8752d17595cfafaa39626f0d36675d7c82
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558060"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a>Solicitudes de los temas de datos del RGPD y Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés)

El Reglamento General de Protección de Datos (GDPR, por sus siglas en inglés) establece nuevas reglas para las organizaciones que suministran bienes y servicios a las personas en la Unión Europea (UE), o que recolectan y analizan los datos de los residentes de la UE, independientemente de su ubicación o de la de la empresa en la que trabajen. Puede encontrar más información en el [tema de resumen del RGPD](gdpr.md).

De forma similar, la Ley de Privacidad de Consumidores de California (CCPA) establece derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los sancionados por el RGPD, como el derecho a eliminar, obtener acceso y recibir (portabilidad) sus datos personales.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Este documento le informa sobre la finalización de solicitudes de interesados en virtud del RGPD al usar productos y servicios de Microsoft.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Familia de Visual Studio](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Soporte técnico y servicios profesionales de Microsoft](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>Terminología

Definiciones útiles de los términos del RGPD utilizados en este documento:

- *Controlador de datos (controlador)*: una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determinan el propósito y el medio del procesamiento de datos personales.  
- *Datos personales * e *interesado*: cualquier información relacionada con una persona física identificada o una persona natural identificable (interesado), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- *Procesador*: una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- *Datos de clientes*: datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="what-is-a-dsr"></a>¿Qué es un DSR?

El Reglamento General de Protección de Datos (RGPD) otorga derechos a las personas (denominadas "interesados" en el reglamento) para administrar los datos personales recopilados por un empresario u otro tipo de agencia u organización (denominado "responsable del tratamiento de los datos" o simplemente "responsable"). El Reglamento general de protección de datos (RGPD) le da a los sujetos de los datos derechos específicos sobre sus datos personales; entre estos derechos se incluyen la obtención de copias de los datos, la solicitud de cambios en ellos, la restricción de su tratamiento, su eliminación o su recepción en formato electrónico para que pueda ser trasladado a otro responsable.

La Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés), ofrece derechos y obligaciones de privacidad a los consumidores de California, incluyendo derechos similares a los Derechos del Sujeto de Datos del RGPD, como el derecho de eliminar, acceder y recibir (portabilidad) su información personal.  

En su calidad de responsable de la gestión, usted está obligado a considerar rápidamente cada DSR y a proporcionar una respuesta sustantiva, ya sea adoptando las medidas necesarias o explicando las causas por las que el responsable de la gestión del DSR no puede adaptarse a las necesidades del responsable.. Un controlador debe consultar con sus propios consejeros jurídicos o asesores de cumplimiento sobre la disposición adecuada de un DSR.

Es posible se requieran varios procesos para completar un DSR, según las reglas de cumplimiento del RGPD de su organización.
  
- **Descubrimiento** El proceso de determinar qué datos son necesarios para completar un DSR.
- **Acceso** La extracción y transmisión potencial al interesado de la información descubierta.
- **Rectificado** La implementación de modificaciones u otros cambios solicitados respecto a los datos personales.
- **Restricción** Limitar el acceso o el procesamiento de los datos, restringiendo el acceso o quitando los datos de la nube de Microsoft.
- **Exportar** Ofrecer los datos en un «formato de datos personales estructurado, de uso común y legible por máquina», como se indica en el «Derecho de portabilidad de datos» del RGPD.
- **Eliminar** Eliminar permanente los datos personales de la nube de Microsoft.

## <a name="specific-dsr-considerations"></a>Consideraciones específicas de DSR

### <a name="insights-generated-by-microsoft-products-or-services"></a>Información generada por los productos o servicios de Microsoft

[La información](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) pueden ser generada por servicios (como MyAnalytics, etc.). Office 365 también incluye servicios en línea con información a los usuarios y a las organizaciones que los usan. Los datos generados por estos servicios pueden producir datos personales pertinentes para un DSR. Siga el vínculo en la lista siguiente para obtener más información sobre los procesos de DSR específicos de servicios.  

### <a name="dsrs-for-system-generated-logs"></a>DSR para registros generados por el sistema

Los registros y datos relacionados generados por Microsoft pueden considerarse, según la definición de "datos personales" de RGPD, datos personales. No se permite restringir o rectificar los datos de los registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico, y modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría el fraude y los riesgos de seguridad. Microsoft permite acceder, exportar y eliminar los registros generados por el sistema que puedan ser necesarios para completar un DSR. Entre los ejemplos de estos datos se pueden incluir:  

- Datos de uso del servicio de productos, como registros de actividad de usuario.
- Solicitudes de búsqueda de usuarios y datos de consultas.
- Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.  

### <a name="yammer-and-kaizala"></a>Yammer y Kaizala

La eliminación de una cuenta de usuario no quitará los registros generados por los sistemas de Yammer y Kaizala. Para quitar los datos de estas aplicaciones, consulte uno de los siguientes recursos:

- [Gestión de solicitudes del interesado de RGPD en Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Exportar o eliminar datos de la organización de un usuario en Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>Nubes nacionales

En algunas nubes nacionales, un administrador de TI global necesita eliminar los registros generados por el sistema.

### <a name="microsoft-services"></a>Servicios de Microsoft

Si su organización o sus usuarios se relacionan con Microsoft para recibir soporte técnico de nuestros productos y servicios, es posible que algunos de estos datos contengan datos personales. Para más información, vea [Solicitudes de interesados del soporte técnico y los servicios profesionales de Microsoft para el RGPD](gdpr-dsr-prof-services.md)

### <a name="microsoft-controller-products"></a>Productos para los que Microsoft es el controlador

En algunas circunstancias, los usuarios de su organización pueden acceder a los productos o servicios de Microsoft, para los que Microsoft es el controlador de datos. En estos casos, los usuarios tienen que iniciar su propio DSR directamente con Microsoft y Microsoft satisface las solicitudes directamente con el usuario.

### <a name="third-party-products"></a>Productos de terceros

Para los productos y servicios de terceros a los que se accede a través de la autenticación de cuentas de Microsoft, cualquier solicitud del interesado debe dirigirse al tercero correspondiente.

## <a name="data-subject-request-admin-tools"></a>Herramientas de administración de solicitudes del titular de los datos

- **Centro de cumplimiento y seguridad**: los datos generados por el usuario se exportan a través del [Centro de cumplimiento y seguridad](https://aka.ms/stpsecurityandcompliance) o de funciones integradas en la aplicación.
- **Centro de administración de Azure AD**: eliminar un sujeto de datos de Azure Active Directory y los servicios relacionados empleando el [Centro de administración de Azure AD](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/).
- **Exportación de registros de datos de Microsoft**: los administradores de cuentas empresariales pueden exportar los registros generados por el sistema mediante la [Exportación de registros de datos de Microsoft](https://aka.ms/MicrosoftGDPR).

## <a name="learn-more"></a>Obtén más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
