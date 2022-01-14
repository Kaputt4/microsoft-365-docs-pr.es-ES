---
title: Privacidad y datos personales
description: Detalles de los datos recopilados, almacenados y usados por el servicio
keywords: RGPD, retención, eliminación, almacenamiento, retención, procesamiento, seguridad, auditoría
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
manager: dougeby
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: medium
ms.openlocfilehash: 6544aed693d9f2e7249ce44ed3ef6185ab32af9b
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035527"
---
# <a name="overview"></a>Información general

Microsoft Managed Desktop es un servicio de TI como servicio (ITaaS) para clientes de la nube empresarial diseñado para mantener los dispositivos de Windows de los empleados implementados y actualizados. También proporciona operaciones y administración de servicios de TI, supervisa la seguridad y la respuesta a incidentes, así como proporciona soporte al usuario. Esta documentación proporciona detalles adicionales sobre la plataforma de datos y el cumplimiento de la privacidad para Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Finalidad y orígenes de datos de Escritorio administrado de Microsoft

Microsoft Managed Desktop proporciona su servicio a los clientes empresariales y administra correctamente los dispositivos inscritos de los clientes mediante datos de varios orígenes. Estos orígenes, incluidos Azure Active Directory, Microsoft Intune, Microsoft Windows 10 y Microsoft Defender para endpoint, proporcionan una vista completa de los dispositivos que administra Microsoft Managed Desktop. El servicio también usa estas servicios Microsoft para permitir que Microsoft Managed Desktop proporcione funcionalidades de ITaaS:

- [Microsoft Windows 10 Enterprise:](/windows/windows-10/) para administrar la experiencia de configuración de dispositivos, administrar conexiones a otros servicios y soporte operativo para profesionales de TI.
- [Windows update para](/windows/deployment/update/waas-manage-updates-wufb) empresas: usa Windows 10 Enterprise de diagnóstico para proporcionar información adicional sobre Windows 10 actualización. 
- [Microsoft Endpoint Manager:](/mem/endpoint-manager-overview) para la administración de dispositivos y para mantener los datos seguros.
  - [Microsoft Azure Active Directory:](/azure/active-directory/) para la autenticación y la identificación de todas las cuentas de usuario. 
  - [Microsoft Intune:](/mem/intune/) para distribuir configuraciones de dispositivos, administración de dispositivos y administración de aplicaciones.
  - [Endpoint Analytics:](/mem/analytics/overview) para obtener información analítica sobre el uso de dispositivos y aplicaciones.
  - [Windows Autopilot:](/microsoft-365/windows/windows-autopilot) para el aprovisionamiento e implementación de dispositivos.
  - [Microsoft Defender para endpoint:](/microsoft-365/security/defender-endpoint/) proporciona servicios de seguridad como la supervisión de seguridad de dispositivos y los datos de inteligencia de seguridad.
- [Escritorio administrado de Microsoft:](https://endpoint.microsoft.com/#home)  datos proporcionados por el cliente o generados por el servicio durante la ejecución del servicio.
- [Aplicaciones de Microsoft 365 para empresas](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1): para la administración de Aplicaciones Microsoft 365.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Almacenamiento y proceso de datos de Escritorio administrado de Microsoft

Microsoft Managed Desktop se basa en datos de varios productos y servicios de Microsoft para proporcionar su servicio a clientes empresariales. Para lograr el objetivo de proteger y mantener los dispositivos inscritos, procesamos y copiamos datos de estos servicios en Microsoft Managed Desktop.  Cuando procesamos datos, seguimos las instrucciones documentadas que proporciona, como se hace referencia en los Términos de [Servicios](https://www.microsoft.com/licensing/product-licensing/products) en línea y la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Las tareas del procesador de Microsoft Managed Desktop incluyen garantizar la confidencialidad, la seguridad y la resistencia adecuadas. Microsoft Managed Desktop emplea medidas adicionales de privacidad y seguridad para garantizar un tratamiento adecuado de los datos de identificación personal. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Almacenamiento de datos de Escritorio administrado de Microsoft y ubicación del personal

Microsoft Managed Desktop almacena sus datos en los centros de datos de Azure en Los Estados Unidos. Los datos personales obtenidos por Microsoft Managed Desktop y otros servicios son necesarios para mantener el servicio operativo. Si se quita un dispositivo del Escritorio administrado de Microsoft, conservamos los datos personales durante un máximo de 30 días, excepto los datos de alerta recopilados por Microsoft Defender para Endpoint, que se almacenan durante 180 días por motivos de seguridad. Para obtener más información sobre la retención de datos, vea [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

Los equipos de operaciones de ingeniería de escritorio administrado de Microsoft y operaciones de seguridad se encuentran en los Estados Unidos e India. 

### <a name="microsoft-windows-10-diagnostic-data"></a>Datos Windows 10 diagnóstico de Microsoft

Microsoft Managed Desktop usa [Windows 10 datos](/windows/privacy/windows-diagnostic-data) de diagnóstico mejorados para mantener Windows, actualizados, solucionar problemas y realizar mejoras en el producto. La configuración de datos de diagnóstico mejorada incluye información más detallada sobre los dispositivos inscritos en El escritorio administrado de Microsoft y su configuración, capacidades y estado del dispositivo. Cuando se seleccionan datos de diagnóstico mejorados, se recopilan datos, incluidos los datos de diagnóstico necesarios. Vea [Changes to Windows diagnostic data collection para](/windows/privacy/changes-to-windows-diagnostic-data-collection) obtener más información acerca de la Windows 10 de datos de diagnóstico y la recopilación de datos.

La terminología de los datos de diagnóstico cambiará en versiones futuras de Windows. Microsoft Managed Desktop se compromete a procesar solo los datos que necesita el servicio. Aunque esto significa que el nivel de diagnóstico cambiará a **Opcional,** Microsoft Managed Desktop implementará las directivas de diagnóstico limitadas para ajustar la recopilación de datos de diagnóstico necesaria para el servicio. Para obtener más información, vea [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Microsoft Managed Desktop solo procesa y almacena datos de nivel del sistema Windows 10 datos de diagnóstico opcionales procedentes de dispositivos inscritos, como información de rendimiento y confiabilidad de aplicaciones y dispositivos. Microsoft Managed Desktop no procesa ni almacena los datos personales de los clientes, como el chat y el historial del explorador, la voz, el texto o los datos de voz. 

Para obtener más información acerca de la recopilación de datos de diagnóstico de Microsoft Windows 10, vea la sección Dónde almacenamos y procesamos datos [personales](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

### <a name="microsoft-windows-update-for-business"></a>Actualización Windows Microsoft para empresas
Microsoft Windows Update para empresas usa datos de Windows diagnósticos para analizar el estado y los errores de la actualización. Microsoft Managed Desktop aprovecha estos datos y los usa para mitigar y resolver problemas para garantizar que todos los dispositivos registrados estén actualizados en función de una cadencia de actualización predefinida.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Azure Active Directory (Azure AD) almacena los datos que usa Microsoft Managed Desktop en una ubicación geográfica en función de la ubicación proporcionada por la organización al suscribirse a los servicios en línea de Microsoft, como Microsoft Apps para empresas y Azure. La identificación de los datos usados por Microsoft Managed Desktop la almacena Azure AD en una ubicación geográfica basada en la ubicación proporcionada por la organización al suscribirse a servicios en línea de Microsoft, como Microsoft Apps para empresas y Azure. Para obtener más información sobre dónde se encuentran los Azure AD, [vea Azure Active Directory: ¿Dónde se encuentran los datos?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune recopila, procesa y comparte datos con Microsoft Managed Desktop para admitir operaciones y servicios empresariales. Consulta [Recopilación de datos en Intune](/mem/intune/protect/privacy-data-collect) para obtener más información sobre los datos recopilados en Intune. 

Para obtener más información sobre Microsoft Intune de datos, vea [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations). Intune respeta las selecciones de ubicación de almacenamiento realizadas por el administrador para los datos del cliente.

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión
Microsoft Defender para endpoint recopila y almacena información para dispositivos inscritos en Microsoft Managed Desktop con fines de administración, seguimiento e informes. La información recopilada incluye datos de archivos (como nombres de archivo, tamaño y hash), datos de proceso (procesos en ejecución, hashes), datos del Registro, datos de conexión de red y detalles del dispositivo (como identificadores de dispositivo, nombres de dispositivo y la versión del sistema operativo). Consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) para obtener más información sobre Microsoft Defender para las ubicaciones de almacenamiento y recopilación de datos de Endpoint. 

### <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas 
Aplicaciones Microsoft 365 para empresas recopila y comparte datos con Microsoft Managed Desktop para garantizar que dichas aplicaciones estén actualizadas con la versión más reciente basada en canales de actualización predefinidos administrados por Microsoft Managed Desktop. Consulta [Microsoft Defender para El almacenamiento y](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) privacidad de los datos de punto de conexión para obtener más información sobre Aplicaciones Microsoft 365 de almacenamiento y recopilación de datos de Aplicaciones Microsoft 365.

## <a name="major-data-change-notification"></a>Notificación de cambio de datos principal
Microsoft Managed Desktop sigue un proceso de control de cambios tal como se describe en nuestro marco de comunicación de servicio. Notificamos a los clientes a través del centro Microsoft 365 mensajes y el portal de administración de escritorio administrado de Microsoft de incidentes de seguridad y cambios importantes en el servicio. Los cambios en los tipos de datos recopilados y donde se almacenan se consideran un cambio material. Proporcionaremos un mínimo de 30 días de notificación avanzada de este cambio, como es la práctica estándar para Microsoft 365 productos y servicios. Para obtener más información, vea [Service changes and communication](/microsoft-365/managed-desktop/service-description/servicechanges).

## <a name="compliance"></a>Cumplimiento
Microsoft Managed Desktop se ha sometido a auditorías externas y ha obtenido un conjunto completo de ofertas de cumplimiento. Encontrará más información en Cumplimiento de escritorio [administrado](/microsoft-365/managed-desktop/intro/compliance)de Microsoft. Los informes de auditoría están disponibles para su descarga en Microsoft [Service Trust Portal,](https://aka.ms/stp)que sirve como repositorio central para Microsoft Enterprise Online Services. (Microsoft Managed Desktop aparece en estos documentos en la categoría "Supervisión y administración").

### <a name="data-subject-requests"></a>Solicitudes de interesados
Microsoft Managed Desktop sigue las normativas de privacidad rgpd y CCPA, que dan a los interesados derechos específicos sobre sus datos personales. Estos derechos incluyen la obtención de copias de datos personales, la solicitud de correcciones, la restricción del procesamiento de los mismos, la eliminación o la recepción en un formato electrónico para que se puedan mover a otro controlador. Para obtener más información sobre solicitudes de interesados (DSR) en general, vea Solicitudes del interesado y [el RGPD y CCPA](/compliance/regulatory/gdpr-data-subject-requests).

Para realizar solicitudes de interesados en los datos recopilados por el sistema de administración de casos de Escritorio administrado de Microsoft, vea lo siguiente:

- Datos de Microsoft Defender para alertas de extremo: el administrador de seguridad puede solicitar la eliminación o extracción de datos personales relacionados con las alertas de Extremo de Microsoft Defender enviando una solicitud de informe en el [Portal de administración.](https://aka.ms/memadmin) En la solicitud, seleccione tipo de solicitud **Cambiar solicitud**, categoría **Seguridad** y subcategoría **Otros**. Proporcione los nombres de dispositivo relevantes en la descripción de la solicitud.
- Datos de solicitudes de soporte técnico de Microsoft Managed Desktop: el administrador de TI puede solicitar la eliminación o extracción de solicitudes de soporte técnico relacionadas con datos personales mediante el envío de una solicitud de informe en el [Portal de administración.](https://aka.ms/memadmin) En la solicitud, seleccione tipo de solicitud **Cambiar solicitud**, categoría **Seguridad** y subcategoría **Otros**. Proporcione los nombres de dispositivo o los nombres de usuario relevantes en la descripción de la solicitud.

Para obtener DSR de otros productos relacionados con el servicio, vea los siguientes artículos:

- Windows de [diagnóstico](/compliance/regulatory/gdpr-dsr-windows)
- Datos de Microsoft [Intune](/compliance/regulatory/gdpr-dsr-intune)
- Datos de Azure Active [Directory](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>Legal
**Aviso de privacidad de Microsoft a los usuarios finales de productos proporcionados por clientes de la organización**: la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement) notifica a los usuarios finales que cuando inician sesión en productos de Microsoft con una cuenta profesional, a) su organización puede controlar y administrar su cuenta (incluido el control de la configuración relacionada con la privacidad) y acceder y procesar sus datos, y b) Microsoft puede recopilar y procesar los datos para proporcionar el servicio a la organización y a los usuarios finales.
