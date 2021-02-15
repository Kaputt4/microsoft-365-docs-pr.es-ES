---
title: Privacidad y datos personales
description: Detalles de los datos recopilados, almacenados y usados por el servicio
keywords: RGPD, retención, eliminación, almacenamiento, retención, procesamiento, seguridad, auditoría
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7005e09d5a3df158569e132d2954f3b9a0ebf371
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840486"
---
# <a name="privacy-and-personal-data"></a>Privacidad y datos personales

Los usuarios pueden recibir, transmitir y almacenar datos en dispositivos administrados por Escritorio administrado de Microsoft. Confían en que la privacidad de los datos está protegida y se usa solo de forma coherente con sus expectativas. En este artículo se explica cómo El Escritorio administrado de Microsoft recopila, almacena, retiene, procesa, protege, comparte, audita y exporta datos personales. También aprenderá cómo un administrador puede ver, corregir y eliminar datos personales.

Escritorio administrado de Microsoft no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Recopilación de datos de Escritorio administrado de Microsoft

Cuando los usuarios inscriben dispositivos corporativos en el Escritorio administrado de Microsoft, la recopilación de datos se controla , en el nivel técnico, mediante Windows y Microsoft Intune. Estos orígenes recopilan datos personales sobre los dispositivos de los usuarios, como los nombres de dispositivo del Escritorio administrado de Microsoft para poder identificar el dispositivo que se va a administrar y proporcionar con las experiencias de Escritorio administrado de Microsoft.

Escritorio administrado de Microsoft no recopila datos por sí mismo para proporcionar su servicio (excepto la información de contacto [del administrador de TI.](#it-admin-contact-information) En su lugar, Escritorio administrado de Microsoft reutiliza los datos que otros orígenes, como Windows y Microsoft Intune, ya han recopilado. Escritorio administrado de Microsoft usa datos que estos servicios recopilan de los dispositivos inscritos:

- Los datos de diagnóstico de Windows de dispositivos administrados por Escritorio administrado de Microsoft se envían a los almacenes de datos de diagnóstico de Windows de Microsoft.
- Escritorio administrado de Microsoft usa [la administración moderna](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) para administrar los dispositivos inscritos. Como parte de la "administración moderna", los dispositivos deben inscribirse en Azure Active Directory del espacio empresarial.
- Para distribuir su configuración altamente optimizada y segura a los dispositivos inscritos, Escritorio administrado de Microsoft usa Microsoft Intune.
- Escritorio administrado de Microsoft usa datos de inteligencia de seguridad de Protección avanzada de subprocesos de Microsoft Defender para aquellos clientes que usan ese servicio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Almacenamiento de datos y orígenes en escritorio administrado de Microsoft

Una vez que el Escritorio administrado de Microsoft obtiene los datos, debe proporcionar su servicio, almacenamiento y procesamiento de los datos de la siguiente manera:

### <a name="storing-data-storage-location-and-data-retention"></a>Almacenar datos, ubicación de almacenamiento y retención de datos

Escritorio administrado de Microsoft almacena sus datos en uno o varios de los siguientes servicios de almacenamiento de Microsoft:

- Azure SQL
- Azure Storage

Escritorio administrado de Microsoft almacena sus datos en Estados Unidos. El Escritorio administrado de Microsoft conserva los datos personales durante un máximo de 30 días.

### <a name="staff-location"></a>Ubicación del personal

Los equipos de operaciones de seguridad MMD y MMD se encuentran en Estados Unidos e India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de datos del Escritorio administrado de Microsoft

Escritorio administrado de Microsoft usa estos datos:


| Orígenes de datos |Usar con escritorio administrado de Microsoft  |
|---------|---------|
|Datos de Azure Active Directory     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de Escritorio administrado de Microsoft.        |
|Datos de Intune     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de Escritorio administrado de Microsoft.        |
|Microsoft Defender para punto de conexión     |  Se usa para abordar las amenazas de seguridad detectadas en dispositivos inscritos por el Centro de operaciones de seguridad (SOC) del Escritorio administrado de Microsoft.  |
|Datos de diagnóstico de Windows     |Se usa para determinar el estado de actualización de los dispositivos administrados y para proporcionar y mejorar la oferta de It-as-a-Service (ITaaS) de Escritorio administrado de Microsoft.         |
|Datos de contacto de administrador     | El Escritorio administrado de Microsoft lo usa para comunicarse con los administradores de inquilinos.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades procesadas por escritorio administrado de Microsoft

Escritorio administrado de Microsoft procesa estas entidades para proporcionar el servicio:

- Datos del dispositivo
- Configuración de seguridad del dispositivo
- Hardware y sistema operativo del dispositivo
- Información agregada sobre el estado del dispositivo
- Información de diagnóstico de dispositivos
- Datos del espacio empresarial
- Recursos de Azure Active Directory
- Datos de directiva y configuración
- Metadatos de Microsoft Defender para puntos de conexión
- Datos de diagnóstico de Windows
- Datos de uso de productos y servicios

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure Active Directory almacena los datos de identidad que usa el Escritorio administrado de Microsoft en una ubicación geográfica en función de la dirección proporcionada por la organización al suscribirse a un servicio en línea de Microsoft, como Office 365 o Azure. Consulte [Microsoft Azure: ¿Dónde están mis datos de cliente?](http://azuredatacentermap.azurewebsites.net/) para obtener un mapa que muestre los centros de datos de Azure Active Directory.

Para obtener más información sobre las regiones que Azure usa para el almacenamiento de datos, vea [Azure Active Directory: dónde](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)se encuentran los datos.

### <a name="microsoft-intune"></a>Microsoft Intune

Los datos de Intune se pueden almacenar en algunas regiones diferentes, como Europa Norte (Irlanda) y Europa Occidental (Países Bajos). El administrador de TI crea una cuenta de inquilino y elige el país donde se almacenarán los datos cuando se inscriban inicialmente en los servicios de Intune. Para obtener una lista de las ubicaciones de centros de datos usadas por Intune, vea [Microsoft Intune: ¿Dónde están mis datos de cliente?](http://intunedatacentermap.azurewebsites.net/). Para obtener más información sobre el almacenamiento de datos y el uso de Intune, vea [Recopilación de datos en Intune.](https://docs.microsoft.com/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Los datos de Microsoft Defender para puntos de conexión se pueden almacenar en algunas regiones diferentes. Por este motivo, Defender para puntos de conexión opera en los centros de datos de Microsoft Azure en la Unión Europea, el Reino Unido y en Estados Unidos, como se indica en [Microsoft Defender para](http://intunedatacentermap.azurewebsites.net/)Endpoint: ubicaciones de almacenamiento de datos. Para obtener más información sobre el almacenamiento de datos y el uso de Defender para Endpoint, consulta ¿Qué datos recopila [Microsoft Defender para Endpoint?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Como se indica en la Declaración de privacidad de [Microsoft,](https://privacy.microsoft.com/privacystatement)"los datos personales recopilados por Microsoft pueden almacenarse y procesarse en su región, en Los Estados Unidos y en cualquier otro país donde Microsoft o sus filiales, subsidiarias o proveedores de servicios operan instalaciones. [...] Normalmente, la ubicación de almacenamiento principal se encuentra en la región del cliente o en Estados Unidos, a menudo con una copia de seguridad en un centro de datos de otra región. Las ubicación o las ubicación de almacenamiento se eligen para funcionar de forma eficaz, mejorar el rendimiento y crear redundancias con el fin de proteger los datos si hay una interrupción u otro problema. Tomamos medidas para asegurarnos de que los datos que recopilamos en esta declaración de privacidad se procesan de acuerdo con las disposiciones de esta declaración y los requisitos de la legislación aplicable donde se encuentran los datos".

Para obtener más información sobre la recopilación de datos de diagnóstico de Windows 10, consulta la sección "Dónde almacenamos y procesamos datos [personales"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

## <a name="data-access-protection"></a>Protección de acceso a datos

El acceso directo a los almacenes de datos internos de Escritorio administrado de Microsoft está restringido de varias maneras:

- Requiere la aprobación del nivel de clientes potenciales de ingeniería.
- Se audita y el tiempo es limitado.
- Requiere el uso de una estación de trabajo de alta seguridad y restringida.
- Todos los datos se cifran mientras se almacenan.
- No hay acceso permanente.
- El acceso al portal de administración interna de Escritorio administrado de Microsoft requiere una estación de trabajo altamente protegida y restringida.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Procesamiento de datos personales de forma compatible
Escritorio administrado de Microsoft procesa datos personales con sistemas certificados por ISO. Para obtener más información, vea [Cumplimiento.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Generación de perfiles y marketing

Escritorio administrado de Microsoft no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de los temas de datos del RGPD y CCPA

El Reglamento general de protección de datos [(RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea otorga derechos a las personas (conocidas en el reglamento como interesados) para administrar los datos personales recopilados por un empresa u otro tipo de agencia u organización (conocido como controlador de datos o simplemente responsable). Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de tratamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable. Una solicitud formal de un interesado a un responsable para que realice una acción sobre sus datos personales se denomina Solicitud del interesado o DSR.

De forma similar, la Ley de Privacidad del Consumidor de California (CCPA) proporciona derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los derechos del interesado del RGPD, como el derecho a eliminar, acceder y recibir (portabilidad) su información personal. La CCPA también proporciona ciertas divulgaciones, protecciones contra la discriminación al elegir ejercer derechos y requisitos de "no participar o participar" para determinadas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

En la siguiente sección se describe cómo El Escritorio administrado de Microsoft ayuda a los controladores a buscar, tener acceso y actuar sobre datos personales o información personal que usa el Escritorio administrado de Microsoft.

> [!NOTE]
> Si busca información general sobre el RGPD, consulte la sección [RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Portal de confianza de servicios.

### <a name="it-admin-contact-information"></a>Información de contacto del administrador de TI

Un administrador de inquilinos puede ver, corregir y eliminar sus propios datos personales (como su propia información de contacto) directamente en la sección De contacto de administrador del Portal de escritorio administrado de Microsoft.

### <a name="user-related-personal-data"></a>Datos personales relacionados con el usuario

Aparte de esto, el Escritorio administrado de Microsoft no recopila datos personales por sí mismo. En su lugar, se basa y usa datos personales recopilados por otros Servicios en línea de Microsoft Enterprise. Los administradores de TI que buscan responder a sus solicitudes de usuario para ver, corregir y eliminar sus datos personales pueden usar la funcionalidad respectiva de los servicios subyacentes de los que depende el Escritorio administrado de Microsoft. Si está interesado en ver o eliminar datos personales [usados](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) por estos servicios, consulte primero el artículo Solicitudes del interesado de Azure para el RGPD.

Además, use las siguientes instrucciones para ejercer las DSR para los servicios de los que depende el Escritorio administrado de Microsoft para la recopilación de datos personales:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender para punto de conexión](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
