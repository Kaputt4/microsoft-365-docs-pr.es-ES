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
ms.openlocfilehash: 453c26afd176a1282e466a73992ae4abe1542d68
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177482"
---
# <a name="overview"></a>Información general

Escritorio administrado de Microsoft es un servicio de TI como servicio (ITaaS) para clientes de nube empresariales diseñado para mantener los dispositivos de Windows de los empleados implementados y actualizados. También proporciona operaciones y administración de servicios de TI, supervisa la seguridad y la respuesta a incidentes, así como proporciona soporte al usuario. Esta documentación proporciona detalles adicionales sobre la plataforma de datos y el cumplimiento de la privacidad para Escritorio administrado de Microsoft.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Escritorio administrado de Microsoft y propósito de los orígenes de datos

Escritorio administrado de Microsoft proporciona su servicio a los clientes empresariales y administra correctamente los dispositivos inscritos de los clientes mediante datos de varios orígenes. Estos orígenes, incluidos Azure Active Directory, Microsoft Intune, Microsoft Windows 10 y Microsoft Defender para endpoint, proporcionan una vista completa de los dispositivos que Escritorio administrado de Microsoft administra. El servicio también usa estas servicios Microsoft para habilitar Escritorio administrado de Microsoft para proporcionar funcionalidades de ITaaS:

- [Microsoft Windows 10 Enterprise:](/windows/windows-10/) para administrar la experiencia de configuración de dispositivos, administrar conexiones a otros servicios y soporte operativo para profesionales de TI.
- [Windows update para](/windows/deployment/update/waas-manage-updates-wufb) empresas: usa Windows 10 Enterprise de diagnóstico para proporcionar información adicional sobre Windows 10 actualización. 
- [Microsoft Endpoint Manager:](/mem/endpoint-manager-overview) para la administración de dispositivos y para mantener los datos seguros.
  - [Microsoft Azure Active Directory:](/azure/active-directory/) para la autenticación y la identificación de todas las cuentas de usuario. 
  - [Microsoft Intune:](/mem/intune/) para distribuir configuraciones de dispositivos, administración de dispositivos y administración de aplicaciones.
  - [Endpoint Analytics:](/mem/analytics/overview) para obtener información analítica sobre el uso de dispositivos y aplicaciones.
  - [Windows Autopilot:](/microsoft-365/windows/windows-autopilot) para el aprovisionamiento e implementación de dispositivos.
  - [Microsoft Defender para endpoint:](/microsoft-365/security/defender-endpoint/) proporciona servicios de seguridad como la supervisión de seguridad de dispositivos y los datos de inteligencia de seguridad.
- [Escritorio administrado de Microsoft:](https://endpoint.microsoft.com/#home) datos proporcionados por el cliente o generados por el servicio durante la ejecución del servicio.
- [Microsoft 365 aplicaciones para empresas:](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) para la administración de Aplicaciones Microsoft 365.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Escritorio administrado de Microsoft y almacenamiento de datos

Escritorio administrado de Microsoft se basa en datos de varios productos y servicios de Microsoft para proporcionar su servicio a clientes empresariales. Para lograr el objetivo de proteger y mantener los dispositivos inscritos, procesamos y copiamos datos de estos servicios a Escritorio administrado de Microsoft. Cuando procesamos datos, seguimos las instrucciones documentadas que proporciona, como se hace referencia en los Términos de Servicios en línea y la Declaración de privacidad de Microsoft. Cuando procesamos datos, seguimos las instrucciones documentadas que proporciona, como se hace referencia en los Términos de [Servicios](https://www.microsoft.com/licensing/product-licensing/products) en línea y la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Escritorio administrado de Microsoft tareas del procesador incluyen garantizar la confidencialidad, la seguridad y la resistencia adecuadas. Escritorio administrado de Microsoft emplea medidas adicionales de privacidad y seguridad para garantizar un tratamiento adecuado de los datos de identificación personal. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Escritorio administrado de Microsoft almacenamiento de datos y ubicación del personal

Escritorio administrado de Microsoft sus datos en los centros de datos de Azure en los Estados Unidos. Los datos personales obtenidos por Escritorio administrado de Microsoft y otros servicios son necesarios para mantener el servicio operativo. Si se quita un dispositivo de Escritorio administrado de Microsoft, conservamos los datos personales durante un máximo de 30 días, excepto los datos de alerta recopilados por Microsoft Defender para Endpoint, que se almacenan durante 180 días por motivos de seguridad. Para obtener más información sobre la retención de datos, vea [Data retention, deletion, and destruction in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

Escritorio administrado de Microsoft Los equipos de operaciones de ingeniería y operaciones de seguridad se encuentran en los Estados Unidos e India. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Datos Windows 10 diagnóstico de Microsoft

Escritorio administrado de Microsoft usa [Windows 10 datos](/windows/privacy/windows-diagnostic-data) de diagnóstico mejorados para mantener Windows, actualizados, solucionar problemas y realizar mejoras en el producto. La configuración de datos de diagnóstico mejorada incluye información más detallada sobre los dispositivos inscritos en Escritorio administrado de Microsoft y su configuración, capacidades y estado del dispositivo. Cuando se seleccionan datos de diagnóstico mejorados, se recopilan datos, incluidos los datos de diagnóstico necesarios. Vea [Changes to Windows diagnostic data collection para](/windows/privacy/changes-to-windows-diagnostic-data-collection) obtener más información acerca de la Windows 10 de datos de diagnóstico y la recopilación de datos.

La terminología de los datos de diagnóstico cambiará en versiones futuras de Windows. Escritorio administrado de Microsoft se compromete a procesar solo los datos que necesita el servicio. Aunque esto significará que el nivel de diagnóstico cambiará a **Opcional,** Escritorio administrado de Microsoft implementará las directivas de diagnóstico limitadas para ajustar la recopilación de datos de diagnóstico necesaria para el servicio. Para obtener más información, vea [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Escritorio administrado de Microsoft procesa y almacena datos de nivel del sistema Windows 10 datos de diagnóstico opcionales procedentes de dispositivos inscritos, como información de rendimiento y confiabilidad de aplicaciones y dispositivos. Escritorio administrado de Microsoft procesa y almacena los datos personales de los clientes, como chat e historial del explorador, voz, texto o datos de voz. 

Para obtener más información acerca de la recopilación de datos de diagnóstico de Microsoft Windows 10, vea la sección Dónde almacenamos y procesamos datos [personales](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

## <a name="microsoft-windows-update-for-business"></a>Actualización Windows Microsoft para empresas
Microsoft Windows Update para empresas usa datos de Windows diagnósticos para analizar el estado y los errores de la actualización. Escritorio administrado de Microsoft aprovecha estos datos y los usa para mitigar y resolver problemas para garantizar que todos los dispositivos registrados estén actualizados en función de una cadencia de actualización predefinida.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Azure Active Directory (Azure AD) almacena los datos usados por Escritorio administrado de Microsoft en una ubicación geográfica en función de la ubicación proporcionada por la organización al suscribirse a los servicios en línea de Microsoft, como Microsoft Apps para empresas y Azure. Azure AD almacena los datos usados por Escritorio administrado de Microsoft en una ubicación geográfica en función de la ubicación proporcionada por la organización al suscribirse a servicios en línea de Microsoft, como Microsoft Apps para empresas y Azure. Para obtener más información sobre dónde se encuentran los datos de Azure AD, [vea Azure Active Directory: ¿Dónde se encuentran los datos?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune recopila, procesa y comparte datos con Escritorio administrado de Microsoft para admitir operaciones y servicios empresariales. Consulta [Recopilación de datos en Intune](/mem/intune/protect/privacy-data-collect) para obtener más información sobre los datos recopilados en Intune. 

Para obtener más información sobre Microsoft Intune de datos, vea [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide). Intune respeta las selecciones de ubicación de almacenamiento realizadas por el administrador para los datos del cliente.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión
Microsoft Defender para endpoint recopila y almacena información para dispositivos inscritos en Escritorio administrado de Microsoft con fines de administración, seguimiento e informes. La información recopilada incluye datos de archivos (como nombres de archivo, tamaño y hash), datos de proceso (procesos en ejecución, hashes), datos del Registro, datos de conexión de red y detalles del dispositivo (como identificadores de dispositivo, nombres de dispositivo y la versión del sistema operativo). Consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy?view=o365-worldwide#what-data-does-microsoft-defender-atp-collect) para obtener más información sobre Microsoft Defender para las ubicaciones de almacenamiento y recopilación de datos de Endpoint. 

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas 
Aplicaciones Microsoft 365 para empresas recopila y comparte datos con Escritorio administrado de Microsoft para garantizar que dichas aplicaciones estén actualizadas con la versión más reciente basada en canales de actualización predefinidos administrados por Escritorio administrado de Microsoft. Consulta [Microsoft Defender para El almacenamiento y](/microsoft-365/security/defender-endpoint/data-storage-privacy?view=o365-worldwide#what-data-does-microsoft-defender-atp-collect) privacidad de los datos de punto de conexión para obtener más información sobre Aplicaciones Microsoft 365 de almacenamiento y recopilación de datos de Aplicaciones Microsoft 365.

## <a name="major-data-change-notification"></a>Notificación de cambio de datos principal
Escritorio administrado de Microsoft un proceso de control de cambios tal como se describe en nuestro marco de comunicación de servicio. Notificamos a los clientes a través Microsoft 365 centro de mensajes y el portal de administración Escritorio administrado de Microsoft de incidentes de seguridad y cambios importantes en el servicio. Los cambios en los tipos de datos recopilados y donde se almacenan se consideran un cambio material. Proporcionaremos un mínimo de 30 días de notificación avanzada de este cambio, como es la práctica estándar para Microsoft 365 productos y servicios. Para obtener más información, vea [Service changes and communication](/microsoft-365/managed-desktop/service-description/servicechanges?view=o365-worldwide).

## <a name="compliance"></a>Cumplimiento
Escritorio administrado de Microsoft se ha sometido a auditorías externas y ha obtenido un conjunto completo de ofertas de cumplimiento. Puede encontrar más información en Escritorio administrado de Microsoft [Compliance](/microsoft-365/managed-desktop/intro/compliance). Los informes de auditoría están disponibles para su descarga en Microsoft [Service Trust Portal,](https://aka.ms/stp)que sirve como repositorio central para Microsoft Enterprise Online Services. (Escritorio administrado de Microsoft se incluye en estos documentos en la categoría "Supervisión y administración"). 

## <a name="legal"></a>Legal
Aviso de privacidad de **Microsoft** a los usuarios finales de productos proporcionados por clientes de la organización: la Declaración de privacidad de [Microsoft](https://privacy.microsoft.com/privacystatement) notifica a los usuarios finales que cuando inician sesión en productos de Microsoft con una cuenta profesional, a) su organización puede controlar y administrar su cuenta (incluido el control de la configuración relacionada con la privacidad) y acceder y procesar sus datos, y b) Microsoft puede recopilar y procesar los datos para proporcionar el servicio a la organización y los usuarios finales.
