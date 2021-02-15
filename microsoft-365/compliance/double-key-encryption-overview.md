---
title: Información general sobre el cifrado de doble clave y preguntas más frecuentes
description: Preguntas más frecuentes sobre cifrado de clave doble para Microsoft 365.
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
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663065"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Preguntas más frecuentes sobre cifrado de doble clave

¿Tiene alguna pregunta sobre cómo funciona el cifrado de doble clave? Busca una respuesta aquí.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>¿Qué es el cifrado de doble clave para Microsoft 365 (DKE)?

El cifrado de doble clave para Microsoft 365 permite a los clientes proteger sus datos altamente confidenciales para satisfacer requisitos especializados. Ayuda a los clientes a mantener el control total de sus claves de cifrado. Usa dos claves para proteger los datos; una clave en el control y una segunda clave almacenada de forma segura en Microsoft Azure. La visualización de datos protegidos con cifrado de doble clave requiere acceso a ambas claves. Dado que Microsoft solo puede acceder a una de estas claves, los datos protegidos permanecen inaccesibles para Microsoft, lo que garantiza que tiene control total sobre la privacidad y seguridad de los datos.  

Puede hospedar el servicio cifrado de doble clave que se usa para solicitar la clave, en una ubicación de su elección (servidor de administración de claves local o en la nube). El servicio se mantiene como lo haría con cualquier otra aplicación. El cifrado de doble clave le permite controlar el acceso al servicio cifrado de doble clave. Puede almacenar los datos altamente confidenciales localmente o moverlo a la nube. Puede estar seguro de impedir el acceso de terceros porque mantiene el control total de la clave. Cifrado de doble clave le permite almacenar los datos y la clave en la misma ubicación.

DKE le ayuda a cumplir los requisitos normativos de varias normativas y estándares, como el Reglamento general de protección de datos (RGPD), la Ley de portabilidad y responsabilidad de seguros de salud (HIPAA), la Ley Gramm-Leach-Bliley (GLBA), la ley de localización de datos de Rusia – Ley Federal No. 242-FZ, ley federal de privacidad de Australia de 1988 y ley de privacidad de Nueva Zelanda de 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>¿Puedo usar cifrado de doble clave Microsoft Office etiquetas de confidencialidad integradas?

Deberá usar el cliente de etiquetado unificado de Azure Information Protection para proteger los documentos con cifrado de doble clave. Actualmente, no puede usar Microsoft Office etiquetas de confidencialidad integradas.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>¿Qué aplicaciones de Microsoft 365 puedo usar con DKE?

Puede usar etiquetas DKE para proteger documentos con las versiones de escritorio de Word, Excel y PowerPoint en Windows. Asegúrese de que usa *.12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>¿En qué se diferencia el cifrado de doble clave de la solución existente de retención de su propia clave (HYOK)?

Cifrado de doble clave cifra los datos con dos claves. La clave de cifrado está en su control y la segunda clave se almacena en Microsoft Azure, lo que le permite mover los datos cifrados a la nube. HYOK protege el contenido con una sola clave y la clave siempre está local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>¿Se pueden compartir documentos cifrados con doble clave externamente?

Puede compartir documentos cifrados con clave doble con usuarios de un inquilino independiente siempre y cuando estos usuarios:

- Tenga el permiso necesario para obtener acceso a la clave en el servicio de cifrado de doble clave.

- Tener el permiso necesario para acceder a la clave en Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>¿Qué sucede con los documentos protegidos con HYOK?

La implementación del cifrado de doble clave no afectará a la configuración de HYOK existente. Sin embargo, se recomienda empezar a usar cifrado de doble clave en paralelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>¿Puedo ejecutar cifrado de doble clave en mi entorno que no es de Microsoft?

DKE no admite estos entornos porque el servicio requiere acceso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>¿Dónde puedo almacenar documentos cifrados con doble clave?

Puede almacenar documentos cifrados con doble clave local o en la nube. En la nube, puede mover contenido cifrado a SharePoint Online y OneDrive para la Empresa. Dado que Microsoft no tiene acceso a la clave privada, los datos cifrados permanecen opacos para Microsoft. Esto también significa que no puede ver los documentos cifrados en línea en Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>¿En qué regiones e idiomas está disponible el cifrado de doble clave? ¿El cifrado de doble clave está disponible en todo el mundo?

Las etiquetas DKE se localizan a los mismos idiomas que otras etiquetas de confidencialidad en Microsoft Information Protection. El cifrado de doble clave está disponible en todo el mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>¿Puedo convertir una etiqueta que no es DKE en una etiqueta DKE?

No. No puede agregar DKE a una etiqueta después de crearla. En su lugar, debe elegir Usar cifrado **de doble clave** y proporcionar la dirección URL del servicio de cifrado de doble clave al crear la etiqueta.

## <a name="how-do-i-roll-my-dke-keys"></a>¿Cómo puedo deshacer mis claves DKE?

Para obtener instrucciones sobre cómo implementar (también denominada rotación o reclave) la clave que almacena en Azure, vea Operaciones para la clave de inquilino [de Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)

Consulte [la configuración del inquilino y la clave](double-key-encryption.md#tenant-and-key-settings) para obtener información sobre cómo crear una nueva clave para el servicio DKE.

Al crear una clave, se configura un nombre y un GUID. A continuación, si gira una clave, se mantiene el registro antiguo con el nombre y el GUID, pero se agrega un nuevo registro con el mismo nombre pero un GUID diferente. La nueva clave se establece como activa para que la API de clave pública empiece a devolverla para el nuevo cifrado. Ambas claves están disponibles para el descifrado de modo que se puedan descifrar el contenido nuevo y el contenido antiguo.
