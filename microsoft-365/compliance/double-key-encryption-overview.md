---
title: Introducción al cifrado de doble clave y preguntas más frecuentes
description: Preguntas más frecuentes sobre el cifrado de doble clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 02/28/2022
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- tier1
ms.openlocfilehash: 71f3dd312b6ccd87079b3f5f958481ee3a229bd0
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634770"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Preguntas más frecuentes sobre el cifrado de doble clave

¿Tienes alguna pregunta sobre cómo funciona el cifrado de doble clave? Busque una respuesta aquí.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="what-is-double-key-encryption-dke"></a>¿Qué es el cifrado de doble clave (DKE)?

Double Key Encryption permite a los clientes proteger sus datos altamente confidenciales para satisfacer los requisitos especializados. Le ayuda a mantener el control total de sus claves de cifrado. Usa dos claves para proteger los datos; una clave en el control y una segunda clave almacenada de forma segura en Microsoft Azure. La visualización de datos protegidos con el cifrado de doble clave requiere acceso a ambas claves. Dado que Microsoft solo puede acceder a una de estas claves, los datos protegidos siguen siendo inaccesibles para Microsoft, lo que garantiza que tiene control total sobre la privacidad y la seguridad de los datos.  

Puede hospedar el servicio de cifrado de claves doble que se usa para solicitar la clave, en una ubicación de su elección (servidor de administración de claves local o en la nube). El servicio se mantiene como lo haría con cualquier otra aplicación. El cifrado de doble clave permite controlar el acceso al servicio de cifrado de doble clave. Puede almacenar los datos altamente confidenciales en el entorno local o moverlos a la nube. Puede estar seguro de evitar el acceso de terceros porque mantiene el control total de la clave. El cifrado de clave doble permite almacenar los datos y la clave en la misma ubicación.

DKE le ayuda a cumplir los requisitos normativos en varias regulaciones y estándares, como el Reglamento General de Protección de Datos (RGPD), la Ley de Portabilidad y Responsabilidad de Seguros De Salud (HIPAA), la Ley Gramm-Leach-Bliley (GLBA), la ley de localización de datos de Rusia: Ley Federal No. 242-FZ, la Ley Federal de Privacidad de Australia de 1988 y la Ley de Privacidad de Nueva Zelanda de 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>¿Puedo usar el cifrado de doble clave con el etiquetado de confidencialidad integrado de Microsoft Office?

Tendrá que usar el cliente de etiquetado unificado de Azure Information Protection para proteger documentos con el cifrado de doble clave. Actualmente, no puede usar el etiquetado de confidencialidad integrado de Microsoft Office.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>¿Qué Aplicaciones Microsoft 365 puedo usar con DKE?

Puede usar etiquetas DKE para proteger documentos mediante las versiones de escritorio de Word, Excel y PowerPoint en Windows. Asegúrese de que usa *.12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>¿En qué se diferencia el cifrado de doble clave de la solución de almacenamiento de su propia clave (HYOK) existente?

Double Key Encryption cifra los datos con dos claves. La clave de cifrado está en el control y la segunda clave se almacena en Microsoft Azure, lo que le permite mover los datos cifrados a la nube. HYOK protege el contenido con una sola clave y la clave siempre está en el entorno local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>¿Se pueden compartir documentos de Double Key Encrypted externamente?

Puede compartir documentos de Double Key Encrypted con los usuarios de un inquilino independiente, siempre que esos usuarios:

- Tenga el permiso necesario para acceder a la clave en el servicio de cifrado de claves dobles.

- Tenga el permiso necesario para acceder a la clave en Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>¿Qué ocurre con los documentos protegidos con HYOK?

La implementación del cifrado de doble clave no afectará a la configuración de HYOK existente. Sin embargo, se recomienda empezar a usar el cifrado de doble clave en paralelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>¿Puedo ejecutar el cifrado de doble clave en mi entorno que no sea de Microsoft?

DKE no admite estos entornos porque el servicio requiere acceso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>¿Dónde puedo almacenar documentos cifrados con doble clave?

Puede almacenar documentos de Double Key Encrypted en el entorno local o en la nube. En la nube, puede mover contenido cifrado a SharePoint Online y OneDrive para la Empresa. Dado que Microsoft no tiene acceso a la clave privada, los datos cifrados permanecen opacos para Microsoft. Esto también significa que no puede ver los documentos cifrados en línea en Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>¿En qué regiones e idiomas está disponible el cifrado de doble clave? ¿Está disponible el cifrado de doble clave en todo el mundo?

Las etiquetas DKE se localizan en los mismos idiomas que otras etiquetas de confidencialidad en Microsoft Purview Information Protection. El cifrado de doble clave está disponible en todo el mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>¿Puedo convertir una etiqueta que no sea DKE en una etiqueta DKE?

No. No puede agregar DKE a una etiqueta después de crearla. En su lugar, debe elegir **Usar cifrado de doble clave** y proporcionar la dirección URL del servicio de cifrado de claves dobles al crear la etiqueta.

## <a name="how-do-i-roll-my-dke-keys"></a>मैले कसरी lanzar mis llaves DKE?

Para obtener instrucciones sobre la rotación (también denominada rotación o nueva clave) de la clave que se almacena en Azure, consulte [Operaciones para la clave de inquilino de Azure Information Protection](/azure/information-protection/operations-customer-managed-tenant-key).

Consulte [Configuración de inquilinos y claves](double-key-encryption.md#tenant-and-key-settings) para obtener información sobre cómo crear una nueva clave para el servicio DKE.

Al crear una clave, configura un nombre y un GUID. A continuación, si gira una clave, conservará el registro anterior con el nombre y el GUID, pero agregará un nuevo registro con el mismo nombre pero con un GUID diferente. La nueva clave se establece como activa para que la API de clave pública empiece a devolverla para el nuevo cifrado. Ambas claves están disponibles para el descifrado, de modo que se pueda descifrar el contenido nuevo y el contenido antiguo.
