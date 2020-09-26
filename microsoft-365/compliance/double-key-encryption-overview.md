---
title: Información general y preguntas más frecuentes sobre el cifrado de doble clave
description: Preguntas más frecuentes sobre el cifrado de doble clave para Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277663"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Preguntas más frecuentes sobre el cifrado de doble clave

¿Tiene alguna pregunta sobre cómo funciona el cifrado doble de claves? Compruebe si hay una respuesta aquí.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>¿Qué es el cifrado de doble clave para Microsoft 365 (DKE)?

El cifrado de doble clave para Microsoft 365 permite a los clientes proteger sus datos extremadamente confidenciales para cumplir con los requisitos especializados. Ayuda a los clientes a mantener un control total sobre sus claves de cifrado. Utiliza dos claves para proteger los datos; una clave en el control y una segunda clave almacenada de forma segura en Microsoft Azure. Ver los datos protegidos con el cifrado doble de clave requiere acceso a ambas claves. Dado que Microsoft solo puede tener acceso a una de estas claves, los datos protegidos permanecen inaccesibles para Microsoft, lo que garantiza que tendrá un control total sobre la privacidad y la seguridad de los datos.  

Puede hospedar el servicio de cifrado de doble clave que se usa para solicitar la clave, en una ubicación de su elección (servidor de administración de claves local o en la nube). El servicio se mantiene como lo haría con cualquier otra aplicación. El cifrado de doble clave permite controlar el acceso al servicio de cifrado de doble clave. Puede almacenar los datos extremadamente confidenciales de forma local o moverlos a la nube. Puede tener la certeza de evitar el acceso de terceros porque mantiene el control total de la clave. El cifrado de doble clave permite almacenar los datos y la clave en la misma ubicación.

DKE ayuda a cumplir los requisitos normativos en varias regulaciones y estándares, como el Reglamento General de protección de datos (RGPD), la ley de transferencia y responsabilidad de seguros de salud (HIPAA), la Ley Gramm-Leach-Bliley (GLBA), la ley de localización de datos de Rusia: ley federal no. 242-FZ, la ley de privacidad federal de Australia 1988 y la ley de privacidad de Nueva Zelanda 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>¿Se puede usar el cifrado de doble clave con la etiqueta de confidencialidad integrada de Microsoft Office?

Deberá usar el cliente de etiquetado Unificado de Azure Information Protection para proteger documentos con cifrado doble de clave. Actualmente, no puede usar la etiqueta de confidencialidad integrada de Microsoft Office. 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>¿Qué aplicaciones de Microsoft 365 puedo usar con DKE?

Puede usar etiquetas DKE para proteger documentos con las versiones de escritorio de Word, Excel y PowerPoint en Windows. Asegúrese de que está usando *. 12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>¿En qué se diferencia el cifrado doble de clave de la solución existente de retención de clave (HYOK)?

El cifrado de doble clave cifra los datos con dos claves. La clave de cifrado se encuentra en el control y la segunda clave se almacena en Microsoft Azure, lo que le permite mover los datos cifrados a la nube. HYOK protege el contenido con una sola clave y la clave siempre está local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>¿Es posible compartir de forma externa documentos cifrados de doble clave?

Puede compartir documentos cifrados de doble clave con los usuarios de un inquilino independiente siempre que estos usuarios:

- Tiene el permiso necesario para obtener acceso a la clave en el servicio de cifrado de doble clave.

- Tiene el permiso necesario para obtener acceso a su clave en Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>¿Qué ocurre con los documentos que están protegidos con HYOK?

La implementación de un cifrado doble de clave no afectará a la configuración de HYOK existente. Sin embargo, se recomienda empezar a usar el cifrado de doble clave en paralelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>¿Puedo ejecutar el cifrado doble de clave en mi entorno que no sea de Microsoft?

DKE no admite estos entornos porque el servicio necesita acceso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>¿Dónde puedo almacenar los documentos cifrados de doble clave?

Puede almacenar documentos cifrados de doble clave local o en la nube. En la nube, puede mover contenido cifrado a SharePoint Online y OneDrive para la empresa. Como Microsoft no tiene acceso a la clave privada, los datos cifrados permanecen opacos para Microsoft. Esto también significa que no puede ver los documentos cifrados en línea en Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>¿Qué regiones e idiomas son el cifrado de doble clave disponible en? ¿El cifrado de doble clave está disponible en todo el mundo?

Las etiquetas DKE se localizan en los mismos idiomas que otras etiquetas de confidencialidad en Microsoft Information Protection. El cifrado de doble clave está disponible en todo el mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>¿Puedo convertir una etiqueta que no es DKE en una etiqueta DKE?

No. No puede Agregar DKE a una etiqueta después de crearla. En su lugar, debe elegir **usar el cifrado de doble clave** y proporcionar la dirección URL del servicio de cifrado de doble clave cuando cree la etiqueta.

## <a name="how-do-i-roll-my-dke-keys"></a>¿Cómo se retiran las claves de DKE?

Para obtener instrucciones sobre el desplazamiento (también denominado girar o volver a incrustar claves) la clave que almacene en Azure, consulte [Operations for your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).

Consulte [configuración de inquilinos y claves](double-key-encryption.md#tenant-and-key-settings) para obtener información sobre cómo crear una nueva clave para el servicio DKE.

Cuando se crea una clave, se configura un nombre y un GUID. A continuación, si gira una clave, conserva el registro antiguo con el nombre y el GUID pero agrega un nuevo registro con el mismo nombre pero GUID diferente. La nueva clave se establece como activa para que la API de clave pública comience a devolverla para el nuevo cifrado. Ambas claves están disponibles para el descifrado, de modo que se pueda descifrar el contenido nuevo y el contenido antiguo.
