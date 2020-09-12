---
title: Privacidad y datos personales
description: Detalles los datos recopilados, almacenados y usados por el servicio
keywords: RGPD, retención, eliminación, almacenamiento, retención, procesamiento, seguridad, auditoría
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e7eb3eaa6961993f8c77645c8d6760e6701817e2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547943"
---
# <a name="privacy-and-personal-data"></a>Privacidad y datos personales

Los usuarios pueden recibir, transmitir y almacenar datos en dispositivos administrados por el escritorio administrado por Microsoft. Confían en que la privacidad de los datos está protegida y solo se usa de manera que sea coherente con sus expectativas. En este artículo se explica cómo Microsoft Managed Desktop recopila, almacena, retiene, procesa, protege, comparte, audita y exporta datos personales. También aprenderá cómo un administrador puede ver, corregir y eliminar datos personales.

El escritorio administrado de Microsoft no usa ningún dato personal recopilado como parte del suministro del servicio para la generación de perfiles, publicidad o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Recopilación de datos del escritorio administrado por Microsoft

Cuando los usuarios inscriben dispositivos corporativos en el escritorio administrado de Microsoft, la recopilación de datos se controla en la capa técnica mediante Windows y Microsoft Intune. Estos orígenes recopilan datos personales sobre los dispositivos de los usuarios, como nombres de dispositivo para el escritorio administrado por Microsoft para poder identificar el dispositivo que se va a administrar y que se proporciona con las experiencias de escritorio administradas por Microsoft.

Microsoft Managed Desktop no recopila datos por sí mismo para proporcionar su servicio (excepto para la [información de contacto del administrador de ti](#it-admin-contact-information). En su lugar, el escritorio administrado por Microsoft reutiliza datos que otros orígenes, como Windows y Microsoft Intune, ya han recopilado. Microsoft Managed Desktop usa datos que estos servicios recopilan desde dispositivos inscritos:

- Los datos de diagnóstico de Windows de dispositivos administrados por el escritorio administrado de Microsoft se envían a los almacenes de datos de diagnóstico de Windows de Microsoft.
- Microsoft Managed Desktop usa la [Administración moderna](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) para administrar los dispositivos inscritos. Como parte de esto, los dispositivos deben estar inscritos en el Azure Active Directory del inquilino.
- Para distribuir una configuración altamente optimizada y segura a los dispositivos inscritos, Microsoft Managed Desktop usa Microsoft Intune.
- Microsoft Managed Desktop usa datos de inteligencia de seguridad de la protección de subprocesos avanzada de Microsoft defender para los clientes que usan ese servicio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Almacenamiento de datos y orígenes en el escritorio administrado por Microsoft

Una vez que Microsoft administró los datos, debe proporcionar el servicio, el almacenamiento y el procesamiento de los datos que se realicen de la siguiente manera:

### <a name="storing-data-storage-location-and-data-retention"></a>Almacenamiento de datos, ubicación de almacenamiento y retención de datos

Microsoft Managed Desktop almacena sus datos en uno o varios de los siguientes servicios de almacenamiento de Microsoft:

- SQL de Azure
- Azure Storage

El escritorio administrado de Microsoft almacena sus datos en los Estados Unidos. El escritorio administrado de Microsoft conserva los datos personales durante un máximo de 30 días.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de datos del escritorio administrado por Microsoft

Microsoft Managed Desktop usa estos datos:


| Orígenes de datos |Usar con Microsoft Managed Desktop  |
|---------|---------|
|Datos de Azure Active Directory     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de escritorio administrado de Microsoft.        |
|Datos de Intune     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de escritorio administrado de Microsoft.        |
|Protección contra amenazas avanzada de Microsoft Defender (ATP).     |  Se usa para solucionar las amenazas de seguridad que detecta el centro de operaciones de seguridad de Microsoft Managed Desktop (SOC) sobre los dispositivos inscritos.  |
|Datos de diagnóstico de Windows     |Se usa para determinar el estado de actualización de los dispositivos administrados, así como para proporcionar y mejorar la oferta de ti como servicio (ITaaS) del escritorio administrado de Microsoft.         |
|Datos de contacto de administración     | Lo usa el escritorio administrado por Microsoft para comunicarse con los administradores de espacios empresariales.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades procesadas por el escritorio administrado por Microsoft

El escritorio administrado de Microsoft procesa estas entidades para proporcionar el servicio:

- Datos del dispositivo
- Configuración de seguridad del dispositivo
- Sistema operativo y hardware del dispositivo
- Información agregada sobre el estado del dispositivo
- Información de diagnóstico de dispositivos
- Datos del espacio empresarial
- Recursos de Azure Active Directory
- Datos de configuración y directivas
- Metadatos ATP de Microsoft defender
- Datos de diagnóstico de Windows
- Datos de uso de productos y servicios

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Los datos de identidad usados por el escritorio administrado de Microsoft se almacenan en Azure Active Directory en una ubicación geográfica en función de la dirección proporcionada por la organización al suscribirse a un servicio de Microsoft online como Office 365 o Azure. Consulte [Microsoft Azure, donde es mis datos de clientes,](http://azuredatacentermap.azurewebsites.net/) para obtener un mapa que muestre los centros de datos de Azure Active Directory.

Para obtener más información sobre las regiones que Azure usa para el almacenamiento de datos, consulte [Azure Active Directory – dónde están los datos ubicados](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Los datos de Intune se pueden almacenar en varias regiones diferentes, como Europa del norte (Irlanda) y Europa occidental (Países Bajos). El administrador de ti crea una cuenta de inquilino y elige el país en el que se almacenarán los datos cuando se inscriban inicialmente en los servicios de Intune. Para obtener una lista de las ubicaciones de centros de datos usadas por Intune, consulte [Microsoft Intune, donde es mis datos de clientes](http://intunedatacentermap.azurewebsites.net/). Para obtener más información sobre el almacenamiento de datos y el uso de Intune, consulte [recopilación de datos en Intune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-advanced-threat-protection"></a>Protección contra amenazas avanzada de Microsoft Defender

Los datos de la protección contra amenazas avanzada (ATP) de Microsoft defender se pueden almacenar en algunas regiones diferentes. Por este motivo, Microsoft defender ATP opera en los centros de datos de Microsoft Azure de la Unión Europea, el Reino Unido y en Estados Unidos, como se indica en [Microsoft defender ATP, ubicaciones de almacenamiento de datos](http://intunedatacentermap.azurewebsites.net/). Para obtener más información sobre el almacenamiento de datos y el uso de ATP de Microsoft defender, vea [¿qué datos recopila ATP Microsoft defender ATP?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Como se indica en la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement), "los datos personales recopilados por Microsoft se pueden almacenar y procesar en su región, en Estados Unidos y en cualquier otro país donde Microsoft o sus filiales, subsidiarias o proveedores de servicios operen con instalaciones. [...] Normalmente, la ubicación de almacenamiento principal está en la región del cliente o en Estados Unidos, a menudo con una copia de seguridad en un centro de recursos de otra región. Las ubicaciones de almacenamiento se eligen para funcionar de forma eficaz, mejorar el rendimiento y crear redundancias con el fin de proteger los datos si se produce una interrupción u otro problema. Se deben seguir los pasos para garantizar que los datos recopilados en esta declaración de privacidad se procesan de acuerdo con las disposiciones de esta declaración y los requisitos de la ley vigente dondequiera que se encuentren los datos. "

Para obtener más información acerca de la recopilación de datos de diagnóstico de Windows 10, vea la sección ["dónde almacenar y procesar datos personales"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la declaración de privacidad de Microsoft.

## <a name="data-access-protection"></a>Protección de acceso a datos

El acceso directo a los almacenes de datos internos de escritorio administrado de Microsoft se restringe de varias maneras:

- Requiere la aprobación del nivel de liderazgo de ingeniería.
- Se trata tanto de auditorías como de tiempo limitado.
- Requiere el uso de una estación de trabajo altamente protegida y restringida.
- Todos los datos se cifran mientras se almacenan.
- No hay acceso permanente.
- El acceso al portal de administración interna de escritorio administrado de Microsoft requiere una estación de trabajo altamente protegida y restringida.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Procesamiento de datos personales de manera conforme
El escritorio administrado de Microsoft procesa datos personales con sistemas certificados por ISO. Para obtener más información, consulte [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Generación de perfiles y marketing

El escritorio administrado de Microsoft no usa ningún dato personal recopilado como parte del suministro del servicio para la generación de perfiles, publicidad o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de los temas de datos del RGPD y CCPA

El Reglamento de [protección general de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea concede derechos a personas (conocidas en el Reglamento como interesados) para administrar los datos personales recopilados por un empresario u otro tipo de agencia u organización (conocido como el controlador de datos o simplemente el controlador). Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de tratamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable. Una solicitud formal de un interesado a un responsable para que realice una acción sobre sus datos personales se denomina Solicitud del interesado o DSR.

De forma similar, la ley de privacidad del consumidor de California (CCPA) proporciona derechos y obligaciones de privacidad a los consumidores de California, incluidos los derechos similares a los derechos de los interesados de RGPD, como el derecho a eliminar, obtener acceso y recibir (portabilidad) su información personal. La CCPA también proporciona ciertas divulgaciones, protecciones contra la discriminación cuando se eligen los derechos de ejercicio y "cancelación opcional/suscripción" para determinadas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

En la siguiente sección se describe cómo Microsoft Managed Desktop ayuda a los controladores a buscar, tener acceso y actuar en datos personales o información personal que usa el escritorio administrado por Microsoft.

> [!NOTE]
> Si está buscando información general sobre la RGPD, consulte la [sección RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del portal de confianza de servicios.

### <a name="it-admin-contact-information"></a>Información de contacto de administrador de ti

Un administrador de inquilinos puede ver, corregir y eliminar sus datos personales directamente en la sección de contacto de administrador del portal de escritorio administrado de Microsoft.

### <a name="user-related-personal-data"></a>Datos personales relacionados con el usuario

Aparte de esto, el escritorio administrado de Microsoft no recopila datos personales por sí mismo. En su lugar, se basa en los datos personales que recopilan otros servicios en línea de Microsoft Enterprise y los usan. Los administradores de ti que buscan responder a sus solicitudes de usuario para ver, corregir y eliminar sus datos personales pueden usar la funcionalidad respectiva de los servicios subyacentes de los que depende Microsoft administrada en el escritorio. Si está interesado en ver o eliminar datos personales usados por estos servicios, vea primero las [solicitudes del interesado de Azure para el artículo de RGPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) .

Además, use las siguientes instrucciones para ejercitar interesado para los servicios que Microsoft Managed Desktop depende para la recopilación de datos personales:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [ATP de Microsoft Defender](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
