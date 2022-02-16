---
title: Control de aplicaciones
description: Cómo usar el control de aplicaciones y la confianza con las aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 108c4d3d64f503d2221aed9df9724faee85b2998
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825474"
---
# <a name="app-control"></a>Control de aplicaciones

El control de aplicaciones es una práctica de seguridad opcional en Microsoft Managed Desktop que restringe la ejecución de código en dispositivos cliente.

Este control mitiga el riesgo de malware o scripts malintencionados. El control requiere que solo se puedan ejecutar códigos firmados por una lista de editores aprobada por el cliente. Este control ofrece muchas ventajas de seguridad, pero principalmente tiene como objetivo proteger los datos y la identidad de vulnerabilidades basadas en cliente.

Microsoft Managed Desktop simplifica la administración de directivas de control de aplicaciones mediante la creación de una directiva base que permite escenarios de productividad principales. Puedes extender la confianza a otros firmantes que son específicos de las aplicaciones y scripts de tu entorno.

Cualquier tecnología de seguridad requiere un equilibrio entre la experiencia del usuario, la seguridad y el costo. El control de aplicaciones reduce la amenaza de software malintencionado en el entorno, pero hay consecuencias para el usuario y otras acciones para el administrador de TI.

| Seguridad y responsabilidades adicionales | Descripción |
| ------ | ------ |
| Seguridad adicional | Las aplicaciones o scripts que no son de confianza en la directiva de control de aplicaciones se bloquean para que no se ejecuten en dispositivos. |
| Sus responsabilidades adicionales | <ul><li>Eres responsable de probar las aplicaciones para identificar si la directiva de control de aplicaciones las bloquearía.</li><li>Si una aplicación está (o estaría) bloqueada, eres responsable de identificar los detalles de firmante necesarios. Debe solicitar un cambio a través del portal de administración.</li></ul>
| Responsabilidades de Escritorio administrado de Microsoft | <ul><li>Microsoft Managed Desktop mantiene la directiva base que habilita los productos principales de Microsoft como Aplicaciones Microsoft 365, Windows, Teams, OneDrive, y así sucesivamente.</li><li>Microsoft Managed Desktop inserta los firmantes de confianza e implementa la directiva actualizada en los dispositivos.</li></ul>

## <a name="managing-trust-in-applications"></a>Administración de confianza en aplicaciones

Microsoft Managed Desktop cura una directiva base que confía en los componentes principales de las tecnologías de Microsoft. Después, *agregas* confianza para tus propias aplicaciones y scripts al informar a Microsoft Managed Desktop de las aplicaciones y scripts en los que ya confías.

### <a name="base-policy"></a>Directiva base

Microsoft Managed Desktop, en colaboración con expertos en ciberseguridad de Microsoft, crea y mantiene una directiva estándar. Esta directiva estándar:

- Habilita la mayoría de las aplicaciones implementadas Microsoft Intune.
- Bloquea actividades peligrosas como la compilación de código o la ejecución de archivos que no son de confianza.

La directiva base adopta el siguiente enfoque para restringir la ejecución de software:

- Los archivos ejecutados por los administradores podrán ejecutarse.
- Se permitirá la ejecución de archivos *en ubicaciones que* no estén en directorios que puedan escribirse por el usuario.
- Los archivos están firmados por [un firmante de confianza](#signer-requests).
- La mayoría de los archivos firmados por Microsoft se ejecutarán, pero algunos se bloquean para evitar acciones de alto riesgo como la compilación de código.

Si un usuario, aparte de un administrador, podría haber agregado una aplicación o un script a un dispositivo (es decir, está en un directorio que se puede escribir por el usuario), no permitiremos que se ejecute. Permitiremos la ejecución si un administrador ya ha permitido la aplicación o el script.

Nuestra directiva detendrá la ejecución de aplicaciones en los siguientes escenarios:

- Si un usuario es engañado para intentar instalar malware.
- Si una vulnerabilidad en una aplicación el usuario ejecuta intentos de instalar malware.
- Si un usuario intenta ejecutar intencionadamente una aplicación o un script no autorizados.

### <a name="signer-requests"></a>Solicitudes de firmante

Nos informa de las aplicaciones que proporcionan los editores de software en los que confía al archivar una *solicitud de firmante*. Al hacerlo, se hace lo siguiente:

- Agregue esa información de confianza a la directiva de control de aplicaciones de línea base.
- Permitir que cualquier software firmado con el certificado de ese editor se ejecute en los dispositivos.

## <a name="audit-and-enforced-policies"></a>Auditoría y directivas aplicadas

Microsoft Managed Desktop usa Microsoft Intune directivas para proporcionar control de aplicaciones:

### <a name="audit-policy"></a>Directiva de auditoría

Esta directiva crea registros para registrar si la directiva aplicada bloquearía una aplicación o un script.

Las directivas de auditoría no aplican reglas de control de aplicaciones. Están diseñados para fines de prueba para identificar si una aplicación requerirá una exención de editor. Registra advertencias (8003 o 8006 eventos) en el Visor de eventos en lugar de bloquear la ejecución o instalación de aplicaciones o scripts especificados.

### <a name="enforced-policy"></a>Directiva aplicada

Esta directiva bloquea la ejecución de aplicaciones y scripts que no son de confianza y crea registros cada vez que se bloquea una aplicación o un script. Las directivas aplicadas impiden que los usuarios estándar ejecuten aplicaciones o scripts almacenados en directorios que se pueden escribir por el usuario.

Los dispositivos del grupo De prueba tienen una directiva de auditoría aplicada para validar si alguna aplicación causará problemas. Todos los demás grupos (First, Fast y Broad) usan una directiva aplicada. Los usuarios de esos grupos no podrán ejecutar aplicaciones o scripts que no sean de confianza.
