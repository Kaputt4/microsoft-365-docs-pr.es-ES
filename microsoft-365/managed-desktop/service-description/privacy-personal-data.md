---
title: Privacidad y datos personales
description: Detalles de los datos recopilados, almacenados y utilizados por el servicio
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
ms.openlocfilehash: e7c9912e3890d9b13003c7f3264490f67c4fc305
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128354"
---
# <a name="privacy"></a>Privacidad

Microsoft Managed Desktop es un servicio de TI como servicio (ITaaS) para clientes de la nube empresarial diseñado para mantener los dispositivos Windows de los empleados implementados y actualizados.

También proporciona operaciones y administración de servicios de TI, supervisa la seguridad y la respuesta a incidentes, y el soporte técnico del usuario. En este artículo se proporcionan más detalles sobre el cumplimiento de la privacidad y la plataforma de datos para Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop orígenes de datos y propósito

Microsoft Managed Desktop proporciona su servicio a los clientes empresariales y administra correctamente los dispositivos inscritos de los clientes mediante datos de varios orígenes.

Estos orígenes incluyen Azure Active Directory, Microsoft Intune, Microsoft Windows 10 y Microsoft Defender para punto de conexión. Proporcionan una vista completa de los dispositivos que Microsoft Managed Desktop administra. El servicio también usa estos servicios Microsoft para habilitar Microsoft Managed Desktop para proporcionar funcionalidades de ITaaS:

| Origen de datos | Objetivo |
| ------ | ------ |
| [Microsoft Windows 10 Enterprise](/windows/windows-10/) | Administración de la experiencia de configuración de dispositivos, administración de conexiones a otros servicios y compatibilidad operativa con profesionales de TI. |
| [Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb) | Usa Windows 10 Enterprise datos de diagnóstico para proporcionar información adicional sobre Windows 10 actualización. |
| [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) | Administración de dispositivos y para mantener los datos seguros. Los siguientes orígenes de datos se encuentran en Microsoft Endpoint Manager:<br><ul><li>[Microsoft Azure Active Directory](/azure/active-directory/): Autenticación e identificación de todas las cuentas de usuario.</li><li>[Microsoft Intune](/mem/intune/): Distribución de configuraciones de dispositivos, administración de dispositivos y administración de aplicaciones.</li><li>[Análisis de puntos de conexión](/mem/analytics/overview): información analítica sobre el uso de dispositivos y aplicaciones.</li><li>[Windows Autopilot](/microsoft-365/windows/windows-autopilot): aprovisionamiento e implementación de dispositivos.</li><li>[Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/): proporciona servicios de seguridad, como la supervisión de seguridad de dispositivos y los datos de inteligencia de seguridad.</li></ul>
| [Escritorio administrado por Microsoft](https://endpoint.microsoft.com/#home) | Datos proporcionados por el cliente o generados por el servicio durante la ejecución del servicio. |
| [aplicaciones de Microsoft 365 para empresas](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)| Administración de Aplicaciones Microsoft 365.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop proceso de datos y almacenamiento

Microsoft Managed Desktop se basa en datos de varios productos y servicios de Microsoft para proporcionar su servicio a los clientes empresariales.

Para proteger y mantener los dispositivos inscritos, procesamos y copiamos datos de estos servicios en Microsoft Managed Desktop. Cuando procesamos datos, seguimos las instrucciones documentadas que usted proporciona, como se hace referencia en los [Términos de servicios en línea](https://www.microsoft.com/licensing/product-licensing/products) y la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

las tareas del procesador de Microsoft Managed Desktop incluyen garantizar la confidencialidad, la seguridad y la resistencia adecuadas. Microsoft Managed Desktop emplea medidas adicionales de privacidad y seguridad para garantizar el tratamiento adecuado de los datos de identificación personal.

## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop almacenamiento de datos y ubicación del personal

Microsoft Managed Desktop almacena sus datos en los centros de datos de Azure en el Estados Unidos.

Los datos personales obtenidos por Microsoft Managed Desktop y otros servicios son necesarios para mantener el servicio operativo. Si se quita un dispositivo de Microsoft Managed Desktop, conservamos los datos personales durante un máximo de 30 días. Sin embargo, los datos de alerta, recopilados por Microsoft Defender para punto de conexión, se almacenan durante 180 días por motivos de seguridad. Para obtener más información sobre la retención de datos, vea [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

Microsoft Managed Desktop equipos de operaciones de ingeniería y operaciones de seguridad se encuentran en la Estados Unidos, India y Rumania.

### <a name="microsoft-windows-10-diagnostic-data"></a>Datos de diagnóstico de Microsoft Windows 10

Microsoft Managed Desktop usa [Windows 10 datos de diagnóstico mejorados](/windows/privacy/windows-diagnostic-data) para mantener Windows seguros, actualizados, solucionar problemas y realizar mejoras en el producto.

La configuración de datos de diagnóstico mejorada incluye información más detallada sobre los dispositivos inscritos en Microsoft Managed Desktop y su configuración, funcionalidades y estado del dispositivo. Cuando se seleccionan datos de diagnóstico mejorados, se recopilan los datos, incluidos los datos de diagnóstico necesarios. Para obtener más información, consulte [Cambios para Windows recopilación de datos de diagnóstico](/windows/privacy/changes-to-windows-diagnostic-data-collection) sobre la configuración de datos de diagnóstico y la recopilación de datos de Windows 10.

La terminología de datos de diagnóstico cambiará en futuras versiones de Windows. Microsoft Managed Desktop se compromete a procesar solo los datos que necesita el servicio. Aunque esto significará que el nivel de diagnóstico cambiará a **Opcional**, Microsoft Managed Desktop implementará las directivas de diagnóstico limitadas para ajustar la recopilación de datos de diagnóstico necesaria para el servicio. Para obtener más información, consulte [Cambios en Windows recopilación de datos de diagnóstico](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Microsoft Managed Desktop solo procesa y almacena datos de nivel de sistema a partir de Windows 10 datos de diagnóstico opcionales que se originan en dispositivos inscritos, como la confiabilidad de aplicaciones y dispositivos, y la información de rendimiento. Microsoft Managed Desktop no procesa ni almacena los datos personales de los clientes, como el historial de chats y exploradores, la voz, el texto o los datos de voz.

Para obtener más información sobre la recopilación de datos de diagnóstico de Microsoft Windows 10, consulte la sección [Dónde almacenamos y procesamos datos personales](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) de la Declaración de privacidad de Microsoft.

### <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update para empresas

Microsoft Windows Update para empresas usa datos de diagnósticos de Windows para analizar el estado y los errores de actualización. Microsoft Managed Desktop usa estos datos y los usa para mitigar y resolver problemas para asegurarse de que todos los dispositivos registrados están actualizados en función de una cadencia de actualización predefinida.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

La identificación de los datos utilizados por Microsoft Managed Desktop se almacena mediante Azure Active Directory (Azure AD) en una ubicación geográfica. La ubicación geográfica se basa en la ubicación proporcionada por la organización al suscribirse a Microsoft servicios en línea, como Microsoft Apps para Enterprise y Azure. Para obtener más información sobre dónde se encuentran los datos de Azure AD, consulte [Azure Active Directory : ¿Dónde se encuentran los datos?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune recopila, procesa y comparte datos para Microsoft Managed Desktop para admitir operaciones y servicios empresariales. Para obtener más información sobre los datos recopilados en Intune, consulte [Recopilación de datos en Intune](/mem/intune/protect/privacy-data-collect)

Para obtener más información sobre Microsoft Intune ubicaciones de datos, consulte [Dónde se almacenan los datos de Microsoft 365 cliente](/microsoft-365/enterprise/o365-data-locations). Intune respeta las selecciones de ubicación de almacenamiento realizadas por el administrador para los datos del cliente.

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Microsoft Defender para punto de conexión recopila y almacena información para los dispositivos inscritos en Microsoft Managed Desktop con fines de administración, seguimiento e informes. La información recopilada incluye:

- Datos de archivo (como nombres de archivo, tamaño y hashes)
- Procesar datos (procesos en ejecución, hashes)
- Datos del Registro
- Datos de conexión de red
- Detalles del dispositivo (como identificadores de dispositivo, nombres de dispositivo y la versión del sistema operativo)

Para obtener más información sobre las ubicaciones de almacenamiento y recopilación de datos de Microsoft Defender para punto de conexión, consulte [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect).

### <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

Aplicaciones Microsoft 365 para Enterprise recopila y comparte datos con Microsoft Managed Desktop para asegurarse de que esas aplicaciones están actualizadas con la versión más reciente. Estas actualizaciones se basan en canales de actualización predefinidos administrados por Microsoft Managed Desktop. Para obtener más información sobre las ubicaciones de almacenamiento y recopilación de datos de Aplicaciones Microsoft 365, consulte [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect).

## <a name="major-data-change-notification"></a>Notificación de cambios de datos principales

Microsoft Managed Desktop sigue un proceso de control de cambios como se describe en nuestro marco de comunicación de servicio.

Notificamos a los clientes a través del Centro de mensajes de Microsoft 365 y Microsoft Managed Desktop portal de administración de incidentes de seguridad y cambios importantes en el servicio.

Los cambios en los tipos de datos recopilados y dónde se almacenan se consideran un cambio importante. Proporcionaremos un mínimo de 30 días de notificación avanzada de este cambio, como es la práctica estándar para Microsoft 365 productos y servicios. Para obtener más información, vea [Cambios de servicio y comunicación](/microsoft-365/managed-desktop/service-description/servicechanges).

## <a name="compliance"></a>Cumplimiento

Microsoft Managed Desktop se ha sometido a auditorías externas y ha obtenido un conjunto completo de ofertas de cumplimiento. Puede encontrar más información en [Cumplimiento](/microsoft-365/managed-desktop/intro/compliance). Los informes de auditoría están disponibles para su descarga en el [Portal de confianza](https://aka.ms/stp) de servicios de Microsoft, que actúa como repositorio central para Microsoft Enterprise Online Services. Microsoft Managed Desktop aparece en estos documentos en la categoría "Supervisión y administración".

### <a name="data-subject-requests"></a>Solicitudes de los interesados

Microsoft Managed Desktop sigue las regulaciones de privacidad de RGPD y CCPA, que conceden a los interesados derechos específicos sobre sus datos personales.

Estos derechos incluyen:

- Obtención de copias de datos personales
- Solicitar correcciones
- Restricción del procesamiento
- Eliminarlo
- Recibirlo en un formato electrónico para que se pueda mover a otro controlador.

Para obtener más información general sobre las solicitudes de interesados (DSR), consulte [Solicitudes de interesados y rgpd y CCPA](/compliance/regulatory/gdpr-data-subject-requests).

Para ejercer las solicitudes del interesado sobre los datos recopilados por el sistema de administración de casos de Microsoft Managed Desktop, consulte las siguientes solicitudes del interesado:

| Solicitudes de los interesados | Descripción |
| ------ | ------ |
| Datos de alertas de Microsoft Defender para punto de conexión | El administrador de seguridad puede solicitar la eliminación o extracción de datos personales relacionados con Microsoft Defender para punto de conexión alertas mediante el envío de una solicitud de informe en el [Portal de administración](https://aka.ms/memadmin). <br><br> Proporcione la siguiente información de envío: <br><ul><li>Tipo de solicitud: Solicitud de cambio</li><li>Categoría: Seguridad</li><li>Subcategoría: Otras</li><li>Descripción: proporcione los nombres de dispositivo pertinentes.</li></ul> |
| Datos de solicitudes de soporte técnico de Microsoft Managed Desktop | El administrador de TI puede solicitar la eliminación o extracción de solicitudes de soporte técnico relacionadas con datos personales mediante el envío de una solicitud de informe en el [Portal de administración](https://aka.ms/memadmin). <br><br> Proporcione la siguiente información de envío: <ul><li>Tipo de solicitud: Solicitud de cambio</li><li>Categoría: Seguridad</li><li>Subcategoría: Otras</li><li>Descripción: proporcione los nombres de dispositivo o nombres de usuario pertinentes.</li></ul>

Para los DSR de otros productos relacionados con el servicio, consulte los artículos siguientes:

- datos de [diagnóstico](/compliance/regulatory/gdpr-dsr-windows) de Windows
- [Datos de Microsoft Intune](/compliance/regulatory/gdpr-dsr-intune)
- Datos de Azure Active [Directory](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>Legal

**Aviso de privacidad de Microsoft para los usuarios finales de los productos proporcionados por los clientes de la organización**:

La [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement) notifica a los usuarios finales que cuando inician sesión en productos de Microsoft con una cuenta profesional:

1. Su organización puede controlar y administrar su cuenta (incluido el control de la configuración relacionada con la privacidad) y acceder a sus datos y procesarlos.
1. Microsoft puede recopilar y procesar los datos para proporcionar el servicio a la organización y a los usuarios finales.
