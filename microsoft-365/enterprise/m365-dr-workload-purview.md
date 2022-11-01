---
title: Data Residency para Microsoft Purview
description: Data Residency para Microsoft Purview
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: c9eb616409de83bc08ca8140a41cd90ad10ba2dc
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806202"
---
# <a name="data-residency-for-microsoft-purview"></a>Data Residency para Microsoft Purview

Los compromisos de residencia de datos para el conjunto de servicios de Purview, como se describe a continuación, están disponibles con el complemento advanced Data Residency.
Las condiciones necesarias para los compromisos relacionados con los servicios descritos a continuación son:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos de cliente del servicio Purview se aprovisionan en _Geografía de la región local_ o _Geografía expandida de la región local_.

## <a name="migration"></a>Migración

Los datos de cliente que admiten los servicios de Purview están estrechamente alineados con los servicios de Exchange Online y SharePoint Online, y la mayor parte de los datos migrados, si es necesario para cumplir los compromisos de residencia de datos para los servicios de Purview, se controlarán mediante esos servicios. En los casos en los que los datos de cliente auxiliares se mantienen en un servicio de Azure, por ejemplo, la migración de esos datos está asociada a la migración de los datos subyacentes Exchange Online/SharePoint Online.

## <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Estamos en proceso de actualizar la ubicación de datos _real en el_ Centro de Administración inquilinos.  Una vez completado este cambio, podrá ver la ubicación de datos real, para los datos confirmados, navegando a Administración->Settings->Org Settings->Organization Profile->Data Location.  Hasta que ese cambio sea visible, puede ver la información de ubicación de datos Exchange Online para comprender dónde se almacenan los datos confirmados para este servicio.

### <a name="purview-audit-standard"></a>Auditoría de Purview (estándar)

#### <a name="summary"></a>Resumen

Documentación del servicio: [Soluciones de auditoría de Microsoft Purview](/microsoft-365/compliance/auditing-solutions-overview)

Resumen de capacidad: Auditoría de Microsoft Purview (estándar) le proporciona la capacidad de registrar y buscar en los datos las actividades de auditoría y potenciar los esfuerzos forenses, de TI y de cumplimiento e investigaciones legales.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#purview-audit-standard) para conocer el compromiso específico de datos de cliente en reposo de Purview Audit (estándar).

### <a name="purview-audit-premium"></a>Auditoría de Purview (Premium)

#### <a name="summary"></a>Resumen

Documentación del servicio: [Soluciones de auditoría de Microsoft Purview](/microsoft-365/compliance/auditing-solutions-overview)

Resumen de la funcionalidad: Auditoría de Microsoft Purview (Premium) se basa en las funcionalidades de Auditoría (estándar) proporcionando directivas de retención de registros de auditoría, mayor retención de registros de auditoría, capacidad para identificar eventos cruciales de alto valor y mayor acceso de ancho de banda a la API de actividad de administración de Office 365.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#purview-audit-premium) para conocer el compromiso específico de datos de cliente en reposo de Purview Audit (Premium).

### <a name="data-lifecycle-management---data-retention"></a>Administración del ciclo de vida de los datos: retención de datos

#### <a name="summary"></a>Resumen

ADR se aplica a los siguientes servicios dentro de la administración del ciclo de vida de datos de Purview, Retención de datos:

- Etiqueta de retención manuales
- Directivas de retención básicas para toda la organización o para toda la ubicación
- Directivas de retención automática basadas en reglas
- Retención basada en Machine Learning
- Directivas de retención de mensajes de Teams

Documentación del servicio:  [Información sobre las directivas de retención & etiquetas](/microsoft-365/compliance/retention)

Para obtener información más detallada sobre cómo funciona la configuración de retención con distintas cargas de trabajo, consulte los artículos siguientes:

- [Más información sobre las directivas de retención de Exchange](/microsoft-365/compliance/retention-policies-exchange)
- [Obtenga más información sobre la retención de SharePoint y OneDrive](/microsoft-365/compliance/retention-policies-sharepoint)
- [Más información sobre las directivas de retención para Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)

Resumen de funcionalidad: permite conservar o eliminar contenido con la administración de directivas para correo electrónico, documentos y Teams.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#data-lifecycle-management---data-retention) para conocer el compromiso específico de datos de cliente en reposo para la administración del ciclo de vida de los datos: retención de datos.

### <a name="data-lifecycle-management---records-management"></a>Administración del ciclo de vida de los datos: Administración de registros

#### <a name="summary"></a>Resumen

Documentación del servicio: [más información sobre Administración de registros de Microsoft Purview](/microsoft-365/compliance/records-management)

Resumen de funcionalidad: las organizaciones de todos los tipos requieren una solución de administración de registros para administrar registros normativos, legales y críticos para la empresa en sus datos corporativos. La administración de registros de Microsoft Purview ayuda a una organización a administrar sus obligaciones legales, proporciona la capacidad de demostrar el cumplimiento de las regulaciones y aumenta la eficacia con la eliminación regular de los elementos que ya no deben conservarse, ya no tienen valor o ya no son necesarios para fines empresariales.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#data-lifecycle-management---records-management) para conocer el compromiso específico de datos de cliente en reposo para la administración del ciclo de vida de los datos: administración de registros.

### <a name="information-protection---sensitivity-labels"></a>Information Protection: etiquetas de confidencialidad

#### <a name="summary"></a>Resumen

ADR se aplica a los siguientes servicios dentro de purview Information Protection, etiquetas de confidencialidad:

- Etiquetado de confidencialidad manual, predeterminado y obligatorio en Office 365
- Etiquetado de confidencialidad automática en aplicaciones Office 365
- Etiquetas de confidencialidad automáticas en Exchange, SharePoint y OneDrive
- Etiquetas de confidencialidad basadas en la clasificación avanzada
- Etiquetado de confidencialidad para contenedores en Office 365

Documentación del servicio:

- [Información sobre las etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels)
- [Introducción al explorador de actividad](/microsoft-365/compliance/data-classification-activity-explorer)

Resumen de funcionalidad: las etiquetas de confidencialidad de Microsoft Purview Information Protection le permiten clasificar y proteger los datos de su organización, al tiempo que se asegura de que la productividad del usuario y su capacidad de colaborar no se ve obstaculizada.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#information-protection---sensitivity-labels) para conocer el compromiso específico De datos personalizados en reposo para Information Protection - Etiquetas de confidencialidad.

### <a name="information-protection---data-loss-prevention-dlp"></a>Information Protection: Prevención de pérdida de datos (DLP)

#### <a name="summary"></a>Resumen

ADR se aplica a los siguientes servicios dentro de Purview Information Protection, Prevención de pérdida de datos (DLP):

- Office 365 prevención de pérdida de datos (DLP) para correos electrónicos y archivos
- Chat de DLP para Teams

Documentación del servicio: [Más información sobre la prevención de pérdida de datos](/microsoft-365/compliance/dlp-learn-about-dlp)

Resumen de la funcionalidad:

Las organizaciones tienen información confidencial bajo su control, como datos financieros, datos propietarios, números de tarjetas de crédito, registros de salud o números de seguridad social. Para poder proteger estos datos confidenciales y reducir el riesgo, necesitan una manera de evitar que sus usuarios los compartan inapropiadamente con personas que no deberían tenerlos. Esta práctica se denomina prevención de pérdida de datos.

En Microsoft Purview, se implementa la prevención de pérdida de datos mediante la definición y aplicación de directivas DLP. Con una directiva DLP, puede identificar, supervisar y proteger automáticamente elementos confidenciales en:

- Servicios de Microsoft 365 como Teams, Exchange, SharePoint y OneDrive
- Aplicaciones de Office como Word, Excel y PowerPoint
- puntos de conexión Windows 10, Windows 11 y macOS (Catalina 10.15 y versiones posteriores)
- aplicaciones en la nube que no son de Microsoft
- recursos compartidos de archivos locales y SharePoint local.

DLP detecta elementos confidenciales mediante el análisis de contenido profundo, no solo mediante un simple examen de texto. El contenido se analiza para buscar coincidencias de datos principales con palabras clave, mediante la evaluación de expresiones regulares, mediante la validación de funciones internas y las coincidencias de datos secundarios que están cerca de la coincidencia de datos principal. Además, DLP también usa algoritmos de aprendizaje automático y otros métodos para detectar contenido que coincida con las directivas DLP.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#information-protection---data-loss-prevention-dlp) para conocer el compromiso específico de datos de cliente en reposo para Information Protection - Prevención de pérdida de datos (DLP).

### <a name="information-protection---office-message-encryption"></a>Information Protection: Cifrado de mensajes de Office

#### <a name="summary"></a>Resumen

ADR se aplica a los siguientes servicios dentro de Purview Information Protection, Cifrado de mensajes de Office:

- Cifrado básico de mensajes de Office
- Cifrado avanzado de mensajes de Office

Documentación del servicio: [cifrado de mensajes de Office 365: Microsoft Purview](/microsoft-365/compliance/ome)

Resumen de funcionalidad: con Office 365 cifrado de mensajes, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de la organización. El Cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. Email cifrado de mensajes ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#information-protection---office-message-encryption) para conocer el compromiso específico de datos de cliente en reposo para Information Protection: Cifrado de mensajes de Office.

### <a name="insider-risk-management---information-barriers"></a>Administración de riesgos internos: barreras de información

#### <a name="summary"></a>Resumen

Documentación del servicio: [Más información sobre las barreras de información](/microsoft-365/compliance/information-barriers)

Resumen de funcionalidad: Microsoft Purview Information Barriers (IB) es una solución de cumplimiento que permite restringir la comunicación bidireccional y la colaboración entre grupos y usuarios en Microsoft Teams, SharePoint y OneDrive. A menudo utilizado en sectores altamente regulados, el IB puede ayudar a evitar conflictos de interés y a proteger la información interna entre los usuarios y las áreas organizativas.

#### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Compromiso:

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#insider-risk-management---information-barriers) para conocer el compromiso específico de datos de clientes en reposo para Insider Risk Management : Barreras de información.
