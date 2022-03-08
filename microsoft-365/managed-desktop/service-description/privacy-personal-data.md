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
ms.openlocfilehash: c70b15a3d35dc4b19c5961e9fbe0404780c12309
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330263"
---
# <a name="privacy"></a>Privacidad

Microsoft Managed Desktop es un servicio de TI como servicio (ITaaS) para clientes empresariales en la nube diseñado para mantener los dispositivos Windows de los empleados implementados y actualizados.

También proporciona operaciones y administración de servicios de TI, supervisa la seguridad y la respuesta a incidentes, y la compatibilidad con los usuarios. En este artículo se proporcionan más detalles sobre la plataforma de datos y el cumplimiento de la privacidad de Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Finalidad y orígenes de datos de Escritorio administrado de Microsoft

Microsoft Managed Desktop proporciona su servicio a los clientes empresariales y administra correctamente los dispositivos inscritos de los clientes mediante datos de varios orígenes.

Estos orígenes incluyen Azure Active Directory, Microsoft Intune, Microsoft Windows 10 y Microsoft Defender para endpoint. Proporcionan una vista completa de los dispositivos que administra Microsoft Managed Desktop. El servicio también usa estas servicios Microsoft para permitir que Microsoft Managed Desktop proporcione funcionalidades de ITaaS:

| Origen de datos | Objetivo |
| ------ | ------ |
| [Microsoft Windows 10 Enterprise](/windows/windows-10/) | Administración de la experiencia de configuración de dispositivos, administración de conexiones a otros servicios y soporte operativo para profesionales de TI. |
| [Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb) | Usa Windows 10 Enterprise de diagnóstico para proporcionar información adicional sobre Windows 10 actualización. |
| [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) | Administración de dispositivos y para mantener los datos seguros. Los siguientes orígenes de datos se Microsoft Endpoint Manager:<br><ul><li>[Microsoft Azure Active Directory](/azure/active-directory/): Autenticación e identificación de todas las cuentas de usuario.</li><li>[Microsoft Intune](/mem/intune/): Distribución de configuraciones de dispositivos, administración de dispositivos y administración de aplicaciones.</li><li>[Endpoint Analytics](/mem/analytics/overview): información analítica sobre el uso de dispositivos y aplicaciones.</li><li>[Windows Autopilot](/microsoft-365/windows/windows-autopilot): aprovisionamiento e implementación de dispositivos.</li><li>[Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/): proporciona servicios de seguridad como la supervisión de seguridad de dispositivos y los datos de inteligencia de seguridad.</li></ul>
| [Escritorio administrado por Microsoft](https://endpoint.microsoft.com/#home) | Datos proporcionados por el cliente o generados por el servicio durante la ejecución del servicio. |
| [Microsoft 365 aplicaciones para empresas](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)| Administración de Aplicaciones Microsoft 365.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Almacenamiento y proceso de datos de Escritorio administrado de Microsoft

Microsoft Managed Desktop se basa en datos de varios productos y servicios de Microsoft para proporcionar su servicio a clientes empresariales.

Para proteger y mantener los dispositivos inscritos, procesamos y copiamos datos de estos servicios en Microsoft Managed Desktop. Cuando procesamos datos, seguimos las instrucciones documentadas que proporciona, como se hace referencia en los Términos de [Servicios](https://www.microsoft.com/licensing/product-licensing/products) en línea y la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

Las tareas del procesador de Microsoft Managed Desktop incluyen garantizar la confidencialidad, la seguridad y la resistencia adecuadas. Microsoft Managed Desktop emplea medidas adicionales de privacidad y seguridad para garantizar un tratamiento adecuado de los datos de identificación personal.

## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Almacenamiento de datos de Escritorio administrado de Microsoft y ubicación del personal

Microsoft Managed Desktop almacena sus datos en los centros de datos de Azure en Los Estados Unidos.

Los datos personales obtenidos por Microsoft Managed Desktop y otros servicios son necesarios para mantener el servicio operativo. Si se quita un dispositivo del Escritorio administrado de Microsoft, conservaremos los datos personales durante un máximo de 30 días. Sin embargo, los datos de alerta, recopilados por Microsoft Defender para Endpoint, se almacenan durante 180 días por motivos de seguridad. Para obtener más información sobre la retención de datos, vea [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

Los equipos de operaciones de ingeniería de escritorio administrado de Microsoft y operaciones de seguridad se encuentran en los Estados Unidos e India.

### <a name="microsoft-windows-10-diagnostic-data"></a>Datos Windows 10 diagnóstico de Microsoft

Microsoft Managed Desktop usa Windows 10 [datos de](/windows/privacy/windows-diagnostic-data) diagnóstico mejorados para mantener Windows, actualizados, solucionar problemas y realizar mejoras en el producto.

La configuración de datos de diagnóstico mejorada incluye información más detallada sobre los dispositivos inscritos en El escritorio administrado de Microsoft y su configuración, capacidades y estado del dispositivo. Cuando se seleccionan datos de diagnóstico mejorados, se recopilan datos, incluidos los datos de diagnóstico necesarios. Para obtener más información, vea [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection) about the Windows 10 diagnostic data setting and data collection.

La terminología de los datos de diagnóstico cambiará en versiones futuras de Windows. Microsoft Managed Desktop se compromete a procesar solo los datos que necesita el servicio. Aunque esto significa que el nivel de diagnóstico cambiará a **Opcional, Microsoft** Managed Desktop implementará las directivas de diagnóstico limitadas para ajustar la recopilación de datos de diagnóstico necesaria para el servicio. Para obtener más información, vea [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Microsoft Managed Desktop solo procesa y almacena datos de nivel del sistema Windows 10 datos de diagnóstico opcionales que se originan a partir de dispositivos inscritos, como la confiabilidad de aplicaciones y dispositivos, y la información de rendimiento. Microsoft Managed Desktop no procesa ni almacena los datos personales de los clientes, como el chat y el historial del explorador, la voz, el texto o los datos de voz.

Para obtener más información acerca de la recopilación de datos de diagnóstico de Microsoft Windows 10, [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) vea la sección Dónde almacenamos y procesamos datos personales de la Declaración de privacidad de Microsoft.

### <a name="microsoft-windows-update-for-business"></a>Actualización Windows Microsoft para empresas

Microsoft Windows Update para empresas usa datos de Windows diagnósticos para analizar el estado y los errores de la actualización. Microsoft Managed Desktop usa estos datos y los usa para mitigar y resolver problemas para garantizar que todos los dispositivos registrados estén actualizados en función de una cadencia de actualización predefinida.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

La identificación de los datos usados por Microsoft Managed Desktop se almacena Azure Active Directory (Azure AD) en una ubicación geográfica. La ubicación geográfica se basa en la ubicación proporcionada por la organización al suscribirse a los servicios en línea de Microsoft, como Microsoft Apps para Enterprise y Azure. Para obtener más información sobre dónde se encuentran los Azure AD, [vea Azure Active Directory: ¿Dónde se encuentran los datos?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune recopila, procesa y comparte datos con Microsoft Managed Desktop para admitir operaciones y servicios empresariales. Para obtener más información acerca de los datos recopilados en Intune, vea [Recopilación de datos en Intune](/mem/intune/protect/privacy-data-collect)

Para obtener más información sobre Microsoft Intune de datos, vea [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations). Intune respeta las selecciones de ubicación de almacenamiento realizadas por el administrador para los datos del cliente.

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Microsoft Defender para endpoint recopila y almacena información para dispositivos inscritos en Microsoft Managed Desktop con fines de administración, seguimiento e informes. La información recopilada incluye:

- Datos de archivo (como nombres de archivo, tamaño y hashes)
- Datos de proceso (procesos en ejecución, hashes)
- Datos del Registro
- Datos de conexión de red
- Detalles del dispositivo (como identificadores de dispositivo, nombres de dispositivo y la versión del sistema operativo)

Para obtener más información sobre Microsoft Defender para las ubicaciones de almacenamiento y recopilación de datos de Endpoint, consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect).

### <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

Aplicaciones Microsoft 365 para Enterprise recopila y comparte datos con Microsoft Managed Desktop para garantizar que dichas aplicaciones estén actualizadas con la versión más reciente. Estas actualizaciones se basan en canales de actualización predefinidos administrados por Microsoft Managed Desktop. Para obtener más información sobre las ubicaciones de almacenamiento y recopilación de datos de Aplicaciones Microsoft 365, consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect).

## <a name="major-data-change-notification"></a>Notificación de cambio de datos principal

Microsoft Managed Desktop sigue un proceso de control de cambios tal como se describe en nuestro marco de comunicación de servicio.

Notificamos a los clientes Microsoft 365 el Centro de mensajes y el portal de administración de escritorio administrado de Microsoft de incidentes de seguridad y cambios importantes en el servicio.

Los cambios en los tipos de datos recopilados y dónde se almacenan se consideran un cambio material. Proporcionaremos un mínimo de 30 días de notificación avanzada de este cambio, como es la práctica estándar para Microsoft 365 productos y servicios. Para obtener más información, vea [Cambios de servicio y comunicación](/microsoft-365/managed-desktop/service-description/servicechanges).

## <a name="compliance"></a>Cumplimiento

Microsoft Managed Desktop se ha sometido a auditorías externas y ha obtenido un conjunto completo de ofertas de cumplimiento. Encontrará más información en [Cumplimiento](/microsoft-365/managed-desktop/intro/compliance). Los informes de auditoría están disponibles para su descarga en el [Portal](https://aka.ms/stp) de confianza de servicio de Microsoft, que sirve como repositorio central para Microsoft Enterprise Online Services. Microsoft Managed Desktop se incluye en estos documentos en la categoría "Supervisión y administración".

### <a name="data-subject-requests"></a>Solicitudes de los interesados

Microsoft Managed Desktop sigue las normativas de privacidad rgpd y CCPA, que dan a los interesados derechos específicos sobre sus datos personales.

Estos derechos incluyen:

- Obtención de copias de datos personales
- Solicitar correcciones
- Restringir el procesamiento del mismo
- Eliminarlo
- Recibirlo en formato electrónico para que se pueda mover a otro controlador.

Para obtener más información general acerca de las solicitudes de interesados (DSR), vea Solicitudes del interesado y [el RGPD y CCPA](/compliance/regulatory/gdpr-data-subject-requests).

Para ejercer las solicitudes del interesado en los datos recopilados por el sistema de administración de casos de Escritorio administrado de Microsoft, consulte las siguientes solicitudes del interesado:

| Solicitudes de los interesados | Descripción |
| ------ | ------ |
| Datos de Microsoft Defender para alertas de extremo | El administrador de seguridad puede solicitar la eliminación o extracción de datos personales relacionados con alertas de Microsoft Defender para puntos de conexión mediante el envío de una solicitud de informe en el [Portal de administración](https://aka.ms/memadmin). <br><br> Proporcione la siguiente información de envío: <br><ul><li>Tipo de solicitud: Solicitud de cambio</li><li>Categoría: Seguridad</li><li>Subcategoría: Otros</li><li>Descripción: proporcione los nombres de dispositivo relevantes.</li></ul> |
| Datos de solicitudes de soporte técnico de Microsoft Managed Desktop | El administrador de TI puede solicitar la eliminación o extracción de solicitudes de soporte relacionados con datos personales mediante el envío de una solicitud de informe en el [Portal de administración](https://aka.ms/memadmin). <br><br> Proporcione la siguiente información de envío: <ul><li>Tipo de solicitud: Solicitud de cambio</li><li>Categoría: Seguridad</li><li>Subcategoría: Otros</li><li>Descripción: proporcione los nombres de dispositivo o nombres de usuario relevantes.</li></ul>

Para obtener DSR de otros productos relacionados con el servicio, vea los siguientes artículos:

- Windows [de diagnóstico](/compliance/regulatory/gdpr-dsr-windows)
- Datos [de Microsoft Intune](/compliance/regulatory/gdpr-dsr-intune)
- Datos de Azure Active [Directory](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>Legal

**Aviso de privacidad de Microsoft para usuarios finales de productos proporcionados por clientes de la organización**:

La [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement) notifica a los usuarios finales que cuando inician sesión en productos de Microsoft con una cuenta de trabajo:

1. Su organización puede controlar y administrar su cuenta (incluido el control de la configuración relacionada con la privacidad) y acceder y procesar sus datos.
1. Microsoft puede recopilar y procesar los datos para proporcionar el servicio a la organización y a los usuarios finales.
