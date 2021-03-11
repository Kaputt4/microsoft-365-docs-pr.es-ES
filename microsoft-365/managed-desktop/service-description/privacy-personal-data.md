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
ms.openlocfilehash: e98d42e79ac270e6ccce46e88e3b8ff00f8bfc0a
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712311"
---
# <a name="privacy-and-personal-data"></a>Privacidad y datos personales

Los usuarios pueden recibir, transmitir y almacenar datos en dispositivos administrados por Microsoft Managed Desktop. Confían en que la privacidad de los datos está protegida y se usa solo de forma coherente con sus expectativas. En este artículo se explica cómo Microsoft Managed Desktop recopila, almacena, retiene, procesa, protege, comparte, audita y exporta datos personales. También aprenderás cómo un administrador puede ver, corregir y eliminar datos personales.

Microsoft Managed Desktop no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Recopilación de datos de Escritorio administrado de Microsoft

Cuando los usuarios inscriben dispositivos corporativos en el Escritorio administrado de Microsoft, la recopilación de datos se controla ,en el nivel técnico, mediante Windows y Microsoft Intune. Estos orígenes recopilan datos personales sobre los dispositivos de los usuarios, como los nombres de dispositivos de Escritorio administrado de Microsoft para poder identificar el dispositivo que se va a administrar y proporcionar con las experiencias de Escritorio administrado de Microsoft.

Microsoft Managed Desktop no recopila datos por sí mismo para proporcionar su servicio (excepto para la información de contacto [del administrador de TI.](#it-admin-contact-information) En su lugar, Microsoft Managed Desktop reutiliza los datos que otros orígenes, como Windows y Microsoft Intune, ya han recopilado. Microsoft Managed Desktop usa datos que estos servicios recopilan de dispositivos inscritos:

- Los datos de diagnóstico de Windows de dispositivos administrados por Microsoft Managed Desktop se envían a los almacenes de datos de diagnóstico de Windows de Microsoft.
- Microsoft Managed Desktop usa [la administración moderna](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) para administrar los dispositivos inscritos. Como parte de la "administración moderna", los dispositivos deben estar inscritos en Azure Active Directory del inquilino.
- Para distribuir su configuración altamente optimizada y segura a los dispositivos inscritos, Microsoft Managed Desktop usa Microsoft Intune.
- Microsoft Managed Desktop usa datos de inteligencia de seguridad de Protección avanzada de subprocesos de Microsoft Defender para aquellos clientes que usan ese servicio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Almacenamiento de datos y orígenes en Microsoft Managed Desktop

Una vez que Microsoft Managed Desktop obtiene los datos, debe proporcionar su servicio, almacenamiento y procesamiento de los datos de la siguiente manera:

### <a name="storing-data-storage-location-and-data-retention"></a>Almacenamiento de datos, ubicación de almacenamiento y retención de datos

Microsoft Managed Desktop almacena sus datos en uno o varios de los siguientes servicios de almacenamiento de Microsoft:

- Azure SQL
- Almacenamiento de Azure
- Dynamics 365

Microsoft Managed Desktop almacena sus datos en Estados Unidos. Microsoft Managed Desktop retiene los datos personales durante un máximo de 30 días, excepto los datos de alerta para dispositivos de Escritorio administrado de Microsoft recopilados por Microsoft Defender para endpoint. Los datos de alerta reales (que podrían incluir datos personales) se almacenan durante 180 días. Los datos de alerta con datos personales eliminados se almacenan durante un máximo de dos años. De conformidad con el Reglamento general de protección de datos (RGPD) y la Ley de privacidad del consumidor de California (CCPA), Microsoft Managed Desktop respeta los derechos del interesado para los datos personales almacenados en datos de alerta.

### <a name="staff-location"></a>Ubicación del personal

Los equipos de operaciones de escritorio administrado de Microsoft y operaciones de seguridad se encuentran en los Estados Unidos e India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de datos de Escritorio administrado de Microsoft

Microsoft Managed Desktop usa estos datos:


| Orígenes de datos |Usar con Escritorio administrado de Microsoft  |
|---------|---------|
|Datos de Azure Active Directory     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de Escritorio administrado de Microsoft.        |
|Datos de Intune     | Se usa en informes creados para administradores de inquilinos, que están disponibles en el portal de administración de Escritorio administrado de Microsoft.        |
|Microsoft Defender para punto de conexión     |  Se usa para abordar las amenazas de seguridad detectadas en dispositivos inscritos por el Centro de operaciones de seguridad (SOC) de Microsoft Managed Desktop.  |
|Datos de diagnóstico de Windows     |Se usa para determinar el estado de actualización de los dispositivos administrados y para proporcionar y mejorar la oferta de IT-as-a-Service (ITaaS) de Microsoft Managed Desktop.         |
|Datos de contacto de administrador     | Usado por Microsoft Managed Desktop para comunicarse con los administradores de inquilinos.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades procesadas por Microsoft Managed Desktop

Microsoft Managed Desktop procesa estas entidades para proporcionar el servicio:

- Datos del dispositivo
- Configuración de seguridad del dispositivo
- Hardware y sistema operativo del dispositivo
- Información agregada sobre el estado del dispositivo
- Información de diagnóstico de dispositivos
- Datos de inquilino
- Recursos de Azure Active Directory
- Datos de directiva y configuración
- Metadatos y datos de alerta de Microsoft Defender para endpoint
- Datos de diagnóstico de Windows
- Datos de uso de productos y servicios

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure Active Directory almacena los datos de identidad usados por Microsoft Managed Desktop en una ubicación geográfica en función de la dirección proporcionada por la organización al suscribirse a un servicio en línea de Microsoft, como Office 365 o Azure. Consulte [Microsoft Azure: ¿Dónde están mis datos de cliente?](http://azuredatacentermap.azurewebsites.net/) para obtener un mapa que muestre los centros de datos de Azure Active Directory.

Para obtener más información acerca de las regiones que Azure usa para el almacenamiento de datos, vea [Azure Active Directory–Where is your data located](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Los datos de Intune se pueden almacenar en algunas regiones diferentes, como Europa Norte (Irlanda) y Europa Occidental (Países Bajos). El administrador de TI crea una cuenta de inquilino y elige el país donde se almacenarán los datos cuando se inscriban inicialmente en los servicios de Intune. Para obtener una lista de las ubicaciones de centros de datos usadas por Intune, vea [Microsoft Intune: ¿Dónde están mis datos de cliente?](http://intunedatacentermap.azurewebsites.net/). Para obtener más información sobre el almacenamiento y el uso de datos por Intune, vea [Data collection in Intune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Los datos de Microsoft Defender para puntos de conexión se pueden almacenar en varias regiones diferentes. Por este motivo, Defender for Endpoint opera en los centros de datos de Microsoft Azure en la Unión Europea, el Reino Unido y en los Estados Unidos, como se indica en [Microsoft Defender para endpoint:](http://intunedatacentermap.azurewebsites.net/)ubicaciones de almacenamiento de datos . Para obtener más información sobre el almacenamiento de datos y el uso de Defender para endpoint, vea ¿Qué datos recopila [Microsoft Defender para Endpoint?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Como se indica en la Declaración de privacidad de [Microsoft,](https://privacy.microsoft.com/privacystatement)"los datos personales recopilados por Microsoft pueden almacenarse y procesarse en su región, en los Estados Unidos y en cualquier otro país donde Microsoft o sus filiales, subsidiarias o proveedores de servicios operan instalaciones. [...] Normalmente, la ubicación de almacenamiento principal se encuentra en la región del cliente o en Estados Unidos, a menudo con una copia de seguridad en un centro de datos de otra región. Las ubicación(s) de almacenamiento se eligen para funcionar de forma eficiente, mejorar el rendimiento y crear redundancias con el fin de proteger los datos si hay una interrupción u otro problema. Tomamos medidas para asegurarnos de que los datos que recopilamos en esta declaración de privacidad se procesan de acuerdo con las disposiciones de esta declaración y los requisitos de la legislación aplicable donde se encuentran los datos".

Para obtener más información acerca de la recopilación de datos de diagnóstico de Windows 10, consulta la sección "Dónde almacenamos y procesamos datos [personales"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

## <a name="data-access-protection"></a>Protección de acceso a datos

El acceso directo a los almacenes de datos internos de Microsoft Managed Desktop está restringido de varias maneras:

- Requiere la aprobación del nivel de cliente potencial de ingeniería.
- Se audita y el tiempo es limitado.
- Requiere el uso de una estación de trabajo altamente protegida y restringida.
- Todos los datos se cifran mientras se almacenan.
- No hay acceso permanente.
- El acceso al portal de administración interna de Microsoft Managed Desktop requiere una estación de trabajo altamente protegida y restringida.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Procesamiento de datos personales de forma compatible
Microsoft Managed Desktop procesa datos personales con sistemas certificados por ISO. Para obtener más información, vea [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Generación de perfiles y marketing

Microsoft Managed Desktop no usa datos personales recopilados como parte de la prestación del servicio con fines de generación de perfiles, publicidad o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de los temas de datos del RGPD y CCPA

El Reglamento general de protección de datos [(RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea concede derechos a las personas (conocidas en el reglamento como interesados) para administrar los datos personales recopilados por un empleador u otro tipo de agencia u organización (conocido como controlador de datos o simplemente controlador). Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de tratamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable. Una solicitud formal de un interesado a un responsable para que realice una acción sobre sus datos personales se denomina Solicitud del interesado o DSR.

Del mismo modo, el CCPA proporciona derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los derechos del interesado del RGPD, como el derecho a eliminar, acceder y recibir (portabilidad) su información personal. El CCPA también proporciona ciertas divulgaciones, protecciones contra la discriminación al elegir derechos de ejercicio y requisitos de "no participar o no participar" para determinadas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

En la siguiente sección se describe cómo Microsoft Managed Desktop ayuda a los controladores a buscar, acceder y actuar sobre los datos personales o la información personal que usa Microsoft Managed Desktop.

> [!NOTE]
> Si está buscando información general sobre el RGPD, consulte la sección [RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Portal de confianza de servicios.

### <a name="it-admin-contact-information"></a>Información de contacto del administrador de TI

Un administrador de inquilinos puede ver, corregir y eliminar sus propios datos personales (como su propia información de contacto) directamente en la sección Contacto de administrador del Portal de escritorio administrado de Microsoft.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Datos de alerta de Microsoft Defender para puntos de conexión

Los administradores de seguridad pueden solicitar una extracción o eliminación de datos personales relacionados con Alertas de Punto de conexión de Microsoft Defender en un dispositivo administrado de Escritorio administrado de Microsoft en su entorno. El administrador de seguridad debe iniciar sesión en el [Portal](https://aka.ms/memadmin) de administración de Escritorio administrado de Microsoft y enviar una solicitud de soporte técnico. Seleccione **Tipo de** solicitud de soporte técnico de  **Solicitud** de **cambio,** Categoría de seguridad y **Subcategoría** de Otros y, a continuación, proporcione los nombres de dispositivo relevantes en la descripción junto con la solicitud de extracción o eliminación de datos.

### <a name="user-related-personal-data"></a>Datos personales relacionados con el usuario

Aparte de esto, Microsoft Managed Desktop no recopila datos personales por sí solo. En su lugar, se basa en y usa datos personales recopilados por otros Servicios en línea de Microsoft Enterprise. Los administradores de TI que buscan responder a sus solicitudes de usuario para ver, corregir y eliminar sus datos personales pueden usar la funcionalidad respectiva de los servicios subyacentes de los que depende Microsoft Managed Desktop. Si está interesado en ver o eliminar datos personales [usados](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) por estos servicios, consulte primero el artículo Solicitudes del interesado de Azure para el RGPD.

Además, use las siguientes instrucciones para ejercer las DSR para los servicios de los que depende Microsoft Managed Desktop para la recopilación de datos personales:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
