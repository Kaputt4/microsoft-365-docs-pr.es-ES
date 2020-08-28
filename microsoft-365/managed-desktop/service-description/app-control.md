---
title: Control de aplicaciones
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289132"
---
# <a name="app-control"></a>Control de aplicaciones

El control de aplicaciones es un procedimiento de seguridad opcional en el escritorio administrado de Microsoft que restringe la ejecución de código en los dispositivos cliente. Este control mitiga el riesgo de los scripts malintencionados o de malware al requerir que solo se pueda ejecutar el código firmado por una lista de publicadores aprobados por el cliente. Hay muchas ventajas de seguridad de este control, pero principalmente se pretende proteger los datos y la identidad de los ataques basados en el cliente.

Microsoft Managed Desktop simplifica la administración de las directivas de control de aplicaciones mediante la creación de una directiva de base que permite escenarios de productividad principales. Puede ampliar la confianza a los firmantes adicionales específicos de las aplicaciones y los scripts de su entorno. 


Cualquier tecnología de seguridad requiere un equilibrio entre la experiencia del usuario, la seguridad y el costo. El control de aplicaciones reduce la amenaza de software malintencionado en su entorno, pero hay consecuencias para el usuario y acciones adicionales para su administrador de ti.

**Seguridad adicional:**

Las aplicaciones o scripts que no son de confianza para la Directiva de control de la aplicación tienen bloqueado su ejecución en dispositivos.

**Sus responsabilidades adicionales:**

- Usted es el responsable de probar las aplicaciones para identificar si podrían ser bloqueadas por la Directiva de control de la aplicación.
- Si una aplicación está (o estaría) bloqueada, usted es responsable de identificar los detalles del firmante necesarios y solicitar un cambio a través del portal de administración.

**Responsabilidades del escritorio administradas de Microsoft:**

- Microsoft Managed Desktop mantiene la Directiva base que habilita los productos principales de Microsoft, como M365 Apps, Windows, Teams, OneDrive, etc.
- Microsoft Managed Desktop inserta los firmantes de confianza e implementa la directiva actualizada en los dispositivos.


## <a name="managing-trust-in-applications"></a>Administrar la confianza en las aplicaciones

Microsoft Managed Desktop curates una directiva básica que confía en los componentes principales de las tecnologías de Microsoft. A continuación, puede *Agregar* confianza para sus propias aplicaciones y scripts informando al escritorio administrado de Microsoft en el que ya confía.

### <a name="base-policy"></a>Directiva de base

Microsoft Managed Desktop, en colaboración con expertos de Microsoft Cybersecurity, crea y mantiene una directiva estándar que permite la mayoría de las aplicaciones que se implementan a través de Microsoft Intune y que bloquea actividades peligrosas como la compilación de código o la ejecución de archivos que no son de confianza.

La Directiva base adopta el siguiente enfoque para restringir la ejecución de software:

- Se permitirá que se ejecuten los archivos ejecutados por los administradores.
- Se permitirá que se ejecuten los archivos de las ubicaciones que *no* estén en Directorios modificables por el usuario.
- Los archivos están firmados por un [firmante de confianza](#signer-requests).
- La mayoría de los archivos firmados por Microsoft se ejecutarán, pero algunos están bloqueados para evitar acciones de alto riesgo como la compilación de código.


Si un usuario que no sea administrador pudiera haber agregado una aplicación o un script a un dispositivo (es decir, en un directorio de escritura de usuario), no permitiría que se ejecutara a menos que un administrador lo haya permitido específicamente. Si se engaña a un usuario para que intente instalar malware, si una vulnerabilidad en una aplicación que el usuario ejecuta intenta instalar malware o si un usuario intenta ejecutar intencionadamente una aplicación o un script no autorizado, la Directiva detendrá la ejecución.

### <a name="signer-requests"></a>Solicitudes de firmante

Nos informamos sobre qué aplicaciones proporcionan los proveedores de software en los que confía mediante la presentación de una *solicitud de firmante*. Al hacerlo, agregamos esa información de confianza a la Directiva de control de la aplicación de línea de base y permite que cualquier software firmado con el certificado de ese editor se ejecute en sus dispositivos.

## <a name="audit-and-enforced-policies"></a>Directivas de auditoría y cumplimiento

Microsoft Managed Desktop usa dos directivas de Microsoft Intune para proporcionar control de aplicaciones:

### <a name="audit-policy"></a>Directiva de auditoría
Esta directiva crea registros para registrar si una aplicación o script estaría bloqueado por la Directiva exigida. Las directivas de auditoría no aplican las reglas de control de aplicaciones y tienen como objetivo realizar pruebas para identificar si una aplicación necesitará una exención de Publisher. Registra las advertencias (8003 o 8006 eventos) en el visor de eventos en lugar de bloquear la ejecución o la instalación de las aplicaciones o scripts especificados.

### <a name="enforced-policy"></a>Directiva forzada
Esta directiva impide que se ejecuten aplicaciones y scripts que no sean de confianza y crea registros siempre que se bloquee una aplicación o un script. Las directivas aplicadas impiden que los usuarios estándar ejecuten aplicaciones o scripts almacenados en directorios de escritura del usuario.

Se aplica una directiva de auditoría a los dispositivos del grupo de prueba para que pueda usarlos para validar si hay alguna aplicación que causará problemas. Todos los demás grupos (primero, rápido y amplio) usan una directiva obligatoria, por lo que los usuarios de esos grupos no podrán ejecutar aplicaciones o scripts que no sean de confianza.







