---
title: Privacidad y datos personales
description: Detalles de los datos recopilados, almacenados y usados por el servicio
keywords: RGPD, retención, eliminación, almacenamiento, retención, procesamiento, seguridad, auditoría
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3de39e8d10f949856862095ebd204fac1a4d694e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861688"
---
# <a name="privacy-and-personal-data"></a>Privacidad y datos personales

Los usuarios pueden recibir, transmitir y almacenar datos en dispositivos administrados por Escritorio administrado de Microsoft. Confían en que la privacidad de los datos está protegida y se usa solo de forma coherente con sus expectativas. En este artículo se explica Escritorio administrado de Microsoft recopila, almacena, retiene, procesa, protege, comparte, audita y exporta datos personales. También aprenderás cómo un administrador puede ver, corregir y eliminar datos personales.

Escritorio administrado de Microsoft no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Colección de datos de Escritorio administrado de Microsoft

Cuando los usuarios inscriben dispositivos corporativos en Escritorio administrado de Microsoft, la recopilación de datos se controla , en la capa técnica, mediante Windows y Microsoft Intune. Estos orígenes recopilan datos personales sobre los dispositivos de los usuarios, como los nombres de dispositivo de Escritorio administrado de Microsoft para poder identificar el dispositivo que se va a administrar y proporcionar con las experiencias Escritorio administrado de Microsoft usuario.

Escritorio administrado de Microsoft recopila datos por sí mismo para proporcionar su servicio (excepto para la información de contacto [del administrador de TI.](#it-admin-contact-information) En su lugar, Escritorio administrado de Microsoft reutiliza los datos que otros orígenes, como Windows y Microsoft Intune, ya han recopilado. Escritorio administrado de Microsoft datos que estos servicios recopilan de dispositivos inscritos:

- Windows datos de diagnóstico de dispositivos administrados por Escritorio administrado de Microsoft se envían a los almacenes de datos de diagnóstico Windows microsoft.
- Escritorio administrado de Microsoft administración [moderna para](/learn/modules/introduction-to-modern-management-in-microsoft-365/) administrar los dispositivos inscritos. Como parte de la "administración moderna", los dispositivos deben estar inscritos en el Azure Active Directory.
- Para distribuir su configuración altamente optimizada y segura a los dispositivos inscritos, Escritorio administrado de Microsoft usa Microsoft Intune.
- Escritorio administrado de Microsoft datos de inteligencia de seguridad de Protección avanzada de subprocesos de Microsoft Defender para los clientes que usan ese servicio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Almacenamiento de datos y orígenes en Escritorio administrado de Microsoft

Después Escritorio administrado de Microsoft obtiene los datos, debe proporcionar su servicio, almacenamiento y procesamiento de los datos de la siguiente manera:

### <a name="storing-data-storage-location-and-data-retention"></a>Almacenamiento de datos, ubicación de almacenamiento y retención de datos

Escritorio administrado de Microsoft almacena sus datos en uno o varios de los siguientes servicios de almacenamiento de Microsoft:

- Azure SQL
- Almacenamiento de Azure
- Dynamics 365

Escritorio administrado de Microsoft almacena sus datos en Estados Unidos. Los datos personales se conservan Escritorio administrado de Microsoft un máximo de 30 días, excepto los datos de alerta para los dispositivos Escritorio administrado de Microsoft recopilados por Microsoft Defender para endpoint. Los datos de alerta reales (que podrían incluir datos personales) se almacenan durante 180 días. Los datos de alerta con datos personales eliminados se almacenan durante un máximo de dos años. De conformidad con el Reglamento general de protección de datos (RGPD) y la Ley de privacidad del consumidor de California (CCPA), Escritorio administrado de Microsoft respeta los derechos del interesado para los datos personales almacenados en datos de alerta.

### <a name="staff-location"></a>Ubicación del personal

Los Escritorio administrado de Microsoft operaciones de seguridad y operaciones de seguridad se encuentran en los Estados Unidos e India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de datos de Escritorio administrado de Microsoft

Escritorio administrado de Microsoft usa estos datos:


| Orígenes de datos |Usar con Escritorio administrado de Microsoft  |
|---------|---------|
|Azure Active Directory datos     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal Escritorio administrado de Microsoft administración.        |
|Datos de Intune     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal Escritorio administrado de Microsoft administración.        |
|Microsoft Defender para punto de conexión     |  Se usa para abordar las amenazas de seguridad detectadas en dispositivos inscritos por el Centro de operaciones de seguridad (SOC) de Escritorio administrado de Microsoft.  |
|Windows de diagnóstico     |Se usa para determinar el estado de actualización de los dispositivos administrados y para proporcionar y mejorar la oferta de ESCRITORIO ADMINISTRADO DE MICROSOFT de IT como servicio (ITaaS).         |
|Datos de contacto de administrador     | Se usa Escritorio administrado de Microsoft para comunicarse con los administradores de inquilinos.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades procesadas por Escritorio administrado de Microsoft

Escritorio administrado de Microsoft procesa estas entidades para proporcionar el servicio:

- Datos del dispositivo
- Configuración de seguridad del dispositivo
- Hardware y sistema operativo del dispositivo
- Información agregada sobre el estado del dispositivo
- Información de diagnóstico de dispositivos
- Datos de inquilino
- Azure Active Directory recursos
- Datos de directiva y configuración
- Metadatos y datos de alerta de Microsoft Defender para endpoint
- Windows de diagnóstico
- Datos de uso de productos y servicios

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Los datos de identidad usados por Escritorio administrado de Microsoft los almacena Azure Active Directory en una ubicación geográfica en función de la dirección proporcionada por la organización al suscribirse a un servicio en línea de Microsoft, como Office 365 o Azure. Consulte [Microsoft Azure: ¿Dónde están mis datos de cliente?](http://azuredatacentermap.azurewebsites.net/) para obtener un mapa que muestre los centros de datos para Azure Active Directory.

Para obtener más información acerca de las regiones que Azure usa para el almacenamiento de datos, [vea Azure Active Directory–Where is your data located](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Los datos de Intune se pueden almacenar en algunas regiones diferentes, como Europa Norte (Irlanda) y Europa Occidental (Países Bajos). El administrador de TI crea una cuenta de inquilino y elige el país donde se almacenarán los datos cuando se inscriban inicialmente en los servicios de Intune. Para obtener una lista de las ubicaciones de centros de datos usadas por Intune, [vea Microsoft Intune: ¿Dónde están mis datos de cliente?](http://intunedatacentermap.azurewebsites.net/). Para obtener más información sobre el almacenamiento y el uso de datos por Intune, vea [Data collection in Intune](/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Los datos de Microsoft Defender para puntos de conexión se pueden almacenar en varias regiones diferentes. Por este motivo, Defender for Endpoint opera en los centros de datos de Microsoft Azure en la Unión Europea, el Reino Unido y en los Estados Unidos, como se indica en [Microsoft Defender para endpoint:](http://intunedatacentermap.azurewebsites.net/)ubicaciones de almacenamiento de datos . Para obtener más información sobre el almacenamiento de datos y el uso de Defender para endpoint, vea ¿Qué datos recopila [Microsoft Defender para Endpoint?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Como se indica en la Declaración de privacidad de [Microsoft,](https://privacy.microsoft.com/privacystatement)"los datos personales recopilados por Microsoft pueden almacenarse y procesarse en su región, en los Estados Unidos y en cualquier otro país donde Microsoft o sus filiales, subsidiarias o proveedores de servicios operan instalaciones. [...] Normalmente, la ubicación de almacenamiento principal se encuentra en la región del cliente o en Estados Unidos, a menudo con una copia de seguridad en un centro de datos de otra región. Las ubicación(s) de almacenamiento se eligen para funcionar de forma eficiente, mejorar el rendimiento y crear redundancias con el fin de proteger los datos si hay una interrupción u otro problema. Tomamos medidas para asegurarnos de que los datos que recopilamos en esta declaración de privacidad se procesan de acuerdo con las disposiciones de esta declaración y los requisitos de la legislación aplicable donde se encuentran los datos".

Para obtener más información acerca de la recopilación de datos de diagnóstico de Windows 10, vea la sección "Dónde almacenamos y procesamos datos [personales"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

## <a name="data-access-protection"></a>Protección de acceso a datos

El acceso directo a los almacenes de datos internos de Escritorio administrado de Microsoft está restringido de varias maneras:

- Requiere la aprobación del nivel de cliente potencial de ingeniería.
- Se limita al tiempo y se audita.
- Todos los datos se cifran mientras se almacenan.
- El acceso al Escritorio administrado de Microsoft de administración interna de Escritorio administrado de Microsoft requiere una estación de trabajo altamente protegida y restringida.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Procesamiento de datos personales de forma compatible
Escritorio administrado de Microsoft procesa datos personales con sistemas certificados por ISO. Para obtener más información, vea [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Generación de perfiles y marketing

Escritorio administrado de Microsoft no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de los temas de datos del RGPD y CCPA

El Reglamento general de protección de datos [(RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea concede derechos a las personas (conocidas en el reglamento como interesados) para administrar los datos personales recopilados por un empleador u otro tipo de agencia u organización (conocido como controlador de datos o simplemente controlador). Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de tratamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable. Una solicitud formal de un interesado a un responsable para que realice una acción sobre sus datos personales se denomina Solicitud del interesado o DSR.

Del mismo modo, el CCPA proporciona derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los derechos del interesado del RGPD, como el derecho a eliminar, acceder y recibir (portabilidad) su información personal. El CCPA también proporciona ciertas divulgaciones, protecciones contra la discriminación al elegir derechos de ejercicio y requisitos de "no participar o no participar" para determinadas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](/compliance/regulatory/offering-ccpa?view=o365-worldwide) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](/compliance/regulatory/ccpa-faq?view=o365-worldwide).

En la siguiente sección se describe cómo Escritorio administrado de Microsoft ayuda a los controladores a buscar, acceder y actuar sobre los datos personales o la información personal que Escritorio administrado de Microsoft.

> [!NOTE]
> Si está buscando información general sobre el RGPD, consulte la sección [RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Portal de confianza de servicios.

### <a name="it-admin-contact-information"></a>Información de contacto del administrador de TI

Un administrador de inquilinos puede ver, corregir y eliminar sus propios datos personales (como su propia información de contacto) directamente en la sección Contacto de administrador del portal de Escritorio administrado de Microsoft.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Datos de alerta de Microsoft Defender para puntos de conexión

Los administradores de seguridad pueden solicitar una extracción o eliminación de datos personales relacionados con Alertas de punto de conexión de Microsoft Defender en un dispositivo Escritorio administrado de Microsoft administrado en su entorno. El administrador de seguridad debe iniciar sesión en el portal de administración Escritorio administrado de Microsoft [y](https://aka.ms/memadmin) enviar una solicitud de soporte técnico. Seleccione **Tipo de** solicitud de soporte técnico de  **Solicitud** de **cambio,** Categoría de seguridad y **Subcategoría** de Otros y, a continuación, proporcione los nombres de dispositivo relevantes en la descripción junto con la solicitud de extracción o eliminación de datos.

### <a name="user-related-personal-data"></a>Datos personales relacionados con el usuario

Aparte de esto, Escritorio administrado de Microsoft recopila datos personales por sí solos. En su lugar, se basa en los datos personales recopilados por otros servicios en línea de Microsoft Enterprise y usa los datos personales. Los administradores de TI que buscan responder a sus solicitudes de usuario para ver, corregir y eliminar sus datos personales pueden usar la funcionalidad respectiva de los servicios subyacentes de los que Escritorio administrado de Microsoft depende. Si está interesado en ver o eliminar datos personales [usados](/compliance/regulatory/gdpr-dsr-Azure) por estos servicios, consulte primero el artículo Solicitudes del interesado de Azure para el RGPD.

Además, use las siguientes instrucciones para ejercer DSR para los servicios de los que Escritorio administrado de Microsoft depende para la recopilación de datos personales:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)
