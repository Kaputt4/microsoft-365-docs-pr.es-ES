---
title: Control de aplicaciones
description: Cómo usar el control de aplicaciones y la confianza con las aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841308"
---
# <a name="app-control"></a>Control de aplicaciones

El control de aplicaciones es una práctica de seguridad opcional en el Escritorio administrado de Microsoft que restringe la ejecución de código en los dispositivos cliente. Este control mitiga el riesgo de malware o scripts malintencionados al requerir que solo se pueda ejecutar el código firmado por una lista de editores aprobada por el cliente. Este control ofrece muchas ventajas de seguridad, pero principalmente tiene como objetivo proteger los datos y la identidad de las vulnerabilidades de seguridad basadas en el cliente.

Escritorio administrado de Microsoft simplifica la administración de directivas de control de aplicaciones mediante la creación de una directiva base que permite escenarios de productividad principales. Puedes ampliar la confianza a otros firmantes específicos de las aplicaciones y scripts de tu entorno. 


Cualquier tecnología de seguridad requiere un equilibrio entre la experiencia del usuario, la seguridad y el costo. El control de aplicaciones reduce la amenaza de software malintencionado en su entorno, pero hay consecuencias para el usuario y otras acciones para el administrador de TI.

**Seguridad adicional:**

Las aplicaciones o scripts que no son de confianza para la directiva de control de aplicaciones están bloqueadas para que no se ejecuten en dispositivos.

**Sus responsabilidades adicionales:**

- Eres responsable de probar las aplicaciones para identificar si la directiva de control de aplicaciones las bloquearía.
- Si una aplicación está (o estaría) bloqueada, eres responsable de identificar los detalles de firmante necesarios y de solicitar un cambio a través del portal de administración.

**Responsabilidades de Escritorio administrado de Microsoft:**

- Escritorio administrado de Microsoft mantiene la directiva base que habilita los productos principales de Microsoft como Aplicaciones de M365, Windows, Teams, OneDrive, entre otros.
- Escritorio administrado de Microsoft inserta los firmantes de confianza e implementa la directiva actualizada en los dispositivos.


## <a name="managing-trust-in-applications"></a>Administración de la confianza en las aplicaciones

Escritorio administrado de Microsoft administra una directiva base que confía en los componentes principales de las tecnologías de Microsoft. A *continuación,* agregue confianza para sus propias aplicaciones y scripts informando a Escritorio administrado de Microsoft de cuáles ya confía.

### <a name="base-policy"></a>Directiva base

Escritorio administrado de Microsoft, en colaboración con expertos en ciberseguridad de Microsoft, crea y mantiene una directiva estándar que habilita la mayoría de las aplicaciones implementadas a través de Microsoft Intune, al tiempo que bloquea actividades peligrosas como la compilación de código o la ejecución de archivos que no son de confianza.

La directiva base adopta el siguiente enfoque para restringir la ejecución de software:

- Los archivos ejecutados por los administradores podrán ejecutarse.
- Se permitirá la ejecución *de* archivos en ubicaciones que no estén en directorios modificables por el usuario.
- Los archivos están firmados por un [firmante de confianza.](#signer-requests)
- La mayoría de los archivos firmados por Microsoft se ejecutarán, pero algunos se bloquean para evitar acciones de alto riesgo, como la compilación de código.


Si un usuario que no es un administrador puede haber agregado una aplicación o script a un dispositivo (es decir, está en un directorio que se puede escribir por el usuario), no le permitiremos que se ejecute a menos que un administrador ya la haya permitido específicamente. Si se engañará a un usuario para que intente instalar malware, si una vulnerabilidad de una aplicación ejecuta intentos de instalar malware o si un usuario intenta ejecutar intencionalmente una aplicación o un script no autorizados, nuestra directiva detendrá la ejecución.

### <a name="signer-requests"></a>Solicitudes del firmante

Para informarnos de las aplicaciones que proporcionan los editores de software de confianza, presenta una solicitud *de firmante.* Al hacerlo, agregamos esa información de confianza a la directiva de control de aplicaciones de línea base y permitimos que cualquier software firmado con el certificado de ese editor se ejecute en los dispositivos.

## <a name="audit-and-enforced-policies"></a>Auditoría y directivas aplicadas

Escritorio administrado de Microsoft usa dos directivas de Microsoft Intune para proporcionar control de aplicaciones:

### <a name="audit-policy"></a>Directiva de auditoría
Esta directiva crea registros para registrar si la directiva aplicada bloquearía una aplicación o un script. Las directivas de auditoría no aplican reglas de control de aplicaciones y están pensadas para realizar pruebas con el fin de identificar si una aplicación requerirá una exención de editor. Registra advertencias (8003 o 8006 eventos) en el Visor de eventos en lugar de bloquear la ejecución o instalación de aplicaciones o scripts especificados.

### <a name="enforced-policy"></a>Directiva aplicada
Esta directiva bloquea la ejecución de aplicaciones y scripts que no son de confianza y crea registros cada vez que se bloquea una aplicación o un script. Las directivas aplicadas impiden que los usuarios estándar ejecuten aplicaciones o scripts almacenados en directorios que se pueden escribir por el usuario.

Los dispositivos del grupo De prueba tienen aplicada una directiva de auditoría para que puedas usarlos para validar si alguna aplicación causará problemas. Todos los demás grupos (First, Fast y Broad) usan una directiva aplicada, por lo que los usuarios de esos grupos no podrán ejecutar aplicaciones o scripts que no sean de confianza.







