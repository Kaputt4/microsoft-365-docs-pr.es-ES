---
title: Información general y preguntas más frecuentes sobre el cifrado de clave doble
description: Preguntas más frecuentes acerca del cifrado de clave doble para Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922054"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Preguntas más frecuentes sobre cifrado de clave doble

¿Tiene alguna pregunta sobre cómo funciona el cifrado de doble clave? Busca una respuesta aquí.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>¿Qué es el cifrado de clave doble Microsoft 365 (DKE)?

Double Key Encryption for Microsoft 365 permite a los clientes proteger sus datos altamente confidenciales para cumplir los requisitos especializados. Ayuda a los clientes a mantener el control total de sus claves de cifrado. Usa dos claves para proteger los datos; una clave en el control y una segunda clave almacenada de forma segura en Microsoft Azure. La visualización de datos protegidos con cifrado de clave doble requiere acceso a ambas claves. Dado que Microsoft solo puede tener acceso a una de estas claves, los datos protegidos siguen siendo inaccesibles para Microsoft, lo que garantiza que tenga control total sobre la privacidad y la seguridad de los datos.  

Puede hospedar el servicio de cifrado de clave doble que se usa para solicitar la clave, en una ubicación de su elección (servidor de administración de claves local o en la nube). El servicio se mantiene como lo haría con cualquier otra aplicación. Double Key Encryption permite controlar el acceso al servicio de cifrado de clave doble. Puede almacenar los datos altamente confidenciales localmente o moverlo a la nube. Puede estar seguro de impedir el acceso de terceros porque mantiene el control total de la clave. Double Key Encryption te permite almacenar los datos y la clave en la misma ubicación.

DKE le ayuda a cumplir los requisitos normativos en varios reglamentos y estándares, como el Reglamento general de protección de datos (RGPD), la Ley de portabilidad y responsabilidad de seguros de salud (HIPAA), la Ley Gramm-Leach-Bliley (GLBA), la ley de localización de datos de Rusia – Ley Federal No. 242-FZ, la Ley federal de privacidad de Australia de 1988 y la Ley de privacidad de Nueva Zelanda de 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>¿Puedo usar el cifrado de clave doble Microsoft Office etiquetado de confidencialidad integrado?

Deberá usar el cliente de etiquetado unificado de Azure Information Protection para proteger los documentos con cifrado de clave doble. Actualmente, no puede usar el Microsoft Office de confidencialidad integrado.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>¿Aplicaciones Microsoft 365 puedo usar con DKE?

Puede usar etiquetas DKE para proteger documentos mediante las versiones de escritorio de Word, Excel y PowerPoint en Windows. Asegúrese de que está usando *.12711 o versiones posteriores (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>¿En qué se diferencia el cifrado de clave doble de la solución de retención existente de su propia clave (HYOK)?

Double Key Encryption cifra los datos con dos claves. La clave de cifrado está en su control y la segunda clave se almacena en Microsoft Azure, lo que le permite mover los datos cifrados a la nube. HYOK protege el contenido con una sola clave y la clave siempre está local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>¿Los documentos cifrados con doble clave se pueden compartir externamente?

Puede compartir documentos cifrados de doble clave con usuarios de un inquilino independiente siempre que estos usuarios:

- Tenga el permiso necesario para obtener acceso a la clave en el servicio de cifrado de clave doble.

- Tenga el permiso necesario para obtener acceso a la clave en Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>¿Qué sucede con los documentos protegidos con HYOK?

La implementación del cifrado de clave doble no afectará a la configuración hyok existente. Sin embargo, se recomienda empezar a usar cifrado de clave doble en paralelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>¿Puedo ejecutar el cifrado de clave doble en mi entorno que no es de Microsoft?

DKE no admite estos entornos porque el servicio requiere acceso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>¿Dónde puedo almacenar documentos cifrados de doble clave?

Puede almacenar documentos cifrados de doble clave local o en la nube. En la nube, puede mover contenido cifrado a SharePoint Online y OneDrive para la Empresa. Dado que Microsoft no tiene acceso a la clave privada, los datos cifrados permanecen opacos para Microsoft. Esto también significa que no puede ver los documentos cifrados en línea en Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>¿En qué regiones e idiomas está disponible el cifrado de clave doble? ¿El cifrado de clave doble está disponible en todo el mundo?

Las etiquetas DKE se localizan en los mismos idiomas que otras etiquetas de confidencialidad en Microsoft Information Protection. El cifrado de clave doble está disponible en todo el mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>¿Puedo convertir una etiqueta que no es DKE en una etiqueta DKE?

No. No puede agregar DKE a una etiqueta después de crearla. En su lugar, debe elegir **Usar cifrado de clave** doble y proporcionar la dirección URL del servicio de cifrado de clave doble al crear la etiqueta.

## <a name="how-do-i-roll-my-dke-keys"></a>¿Cómo se ruedan las claves DKE?

Para obtener instrucciones sobre cómo implementar (también denominada rotación o reclave) la clave que almacena en Azure, vea [Operations for your Azure Information Protection tenant key](/azure/information-protection/operations-customer-managed-tenant-key).

Consulte [Configuración de inquilino y clave](double-key-encryption.md#tenant-and-key-settings) para obtener información sobre cómo crear una nueva clave para el servicio DKE.

Al crear una clave, se configura un nombre y un GUID. A continuación, si gira una clave, se mantiene el registro antiguo con el nombre y el GUID, pero se agrega un nuevo registro con el mismo nombre pero guid diferente. La nueva clave se establece como activa para que la API de clave pública empiece a devolverla para el nuevo cifrado. Ambas claves están disponibles para el descifrado de modo que se puedan descifrar el contenido nuevo y el contenido antiguo.