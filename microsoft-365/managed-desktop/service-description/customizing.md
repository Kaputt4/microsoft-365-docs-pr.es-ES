---
title: Excepciones para el plan de servicios
description: Cómo solicitar excepciones al plan de servicio estándar
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 8069a899b9992a0e8b941b6ac53cd2f230a6174a
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825184"
---
# <a name="exceptions-to-the-service-plan"></a>Excepciones para el plan de servicios

Microsoft Managed Desktop proporciona una lista de dispositivos curada [, una](device-policies.md) configuración de dispositivo estándar, requisitos de aplicaciones y determinadas configuraciones [configurables](../working-with-managed-desktop/config-setting-overview.md), todo diseñado para proporcionar una experiencia segura, productiva y agradable para los usuarios.

Es mejor permanecer siempre con el servicio tal como se proporciona. Sin embargo, reconocemos que es posible que algunos detalles del servicio no se ajusten exactamente a las necesidades de su organización. Si cree que necesita modificar el servicio de alguna manera, es importante que siga los siguientes procesos para solicitar esos cambios.

## <a name="types-of-exceptions"></a>Tipos de excepciones

Una excepción es cualquier adición o cambio a la configuración base de Microsoft Managed Desktop. Algunos ejemplos van desde la configuración de puertos USB hasta la implementación de un nuevo controlador de dispositivo. Agrupamos varias excepciones de la siguiente manera:

| Tipos de excepción | Descripción |
| ----- | ----- |
| Software de productividad | Software en primer plano necesario para los usuarios, restringido por los [requisitos de la aplicación](mmd-app-requirements.md). |
| Agentes de seguridad & VPN | Software usado para proteger, supervisar o cambiar el comportamiento del dispositivo o la red. |
| Supervisión de experiencia digital | Software usado para realizar un seguimiento de los datos en el dispositivo de un usuario para informar a LA. |
| Controladores de hardware o software | Controladores de dispositivo, restringidos por los [requisitos de la aplicación](mmd-app-requirements.md). |
| Directivas | Windows 10 o Aplicaciones Microsoft 365 para empresas configuración de un dispositivo administrado. |
| Dispositivos | Dispositivos que no están en la lista de dispositivos de Escritorio [administrado de](device-list.md) Microsoft. |
| Otros | Cualquier cosa no cubierta por las otras áreas. |

## <a name="request-an-exception"></a>Solicitar una excepción

Envíe solicitudes a través del portal de administración de Escritorio administrado de Microsoft mediante la creación de una solicitud de cambio. Asegúrese de incluir estos detalles:

| Detalles de la solicitud de cambio | Descripción |
| ----- | ----- |
| Tipo de exención | ¿Qué tipo de excepción es? (vea la [tabla anterior](#types-of-exceptions)) |
| Requisito | ¿Cuál es el requisito empresarial específico para la excepción? |
| Propuesta | ¿Qué solución está solicitando su empresa? |
| Escala de tiempo | ¿Cuánto tiempo desea que dure esta excepción? |

## <a name="how-we-assess-an-exception-request"></a>Cómo se evalúa una solicitud de excepción

Cuando se revisan las solicitudes de excepción, se evalúan estos factores en este orden:

1. Algunas aplicaciones y directivas que Microsoft Managed Desktop implementa en todos los dispositivos no son negociables. La solicitud no debe afectar a esas aplicaciones y directivas. Para obtener más información, consulta [Configuración del dispositivo](device-policies.md).
2. Probablemente se aprobará el software de productividad restringido requerido por un usuario para realizar su trabajo.
3. Si podemos cumplir con sus requisitos mediante la tecnología de Microsoft, probablemente aprobaremos su solicitud para un período de migración de excepción de tres a 12 meses. El período de migración depende del ámbito del proyecto.
4. Si no podemos cumplir su requisito con la tecnología de Microsoft, probablemente aprobaremos su solicitud a menos que infrinja una de las [condiciones clave](#key-conditions).  

Estos principios garantizan que Microsoft Managed Desktop siempre puede satisfacer sus necesidades mientras se rastrean las desviaciones de nuestra plantilla estándar.

## <a name="key-conditions"></a>Condiciones clave

Se revisan las excepciones para asegurarse de que no infringen ninguna de estas condiciones:

- Una excepción no debe afectar negativamente a la seguridad del sistema.
- Mantener la excepción no debe conllevar un costo significativo para las operaciones o el soporte técnico de Microsoft Managed Desktop.
- Una excepción no debe afectar a la estabilidad del sistema, por ejemplo, al provocar bloqueos o bloqueos del modo kernel.
- El cambio no debe restringirnos el funcionamiento del servicio o conflicto con la tecnología principal de Microsoft Managed Desktop.
- La excepción no puede implicar personalizar la experiencia del usuario, como cambiar la menú Inicio o la barra de tareas.

Estas condiciones podrían cambiar en el futuro. Si hacemos estos cambios, proporcionaremos un aviso de 30 días antes de que esas condiciones entren en vigor.  Si Microsoft Managed Desktop ofrece una forma alternativa de cumplir una excepción aprobada, Microsoft Managed Desktop notificará al cliente si Microsoft Managed Desktop modifica la forma en que admite la excepción.

## <a name="revoking-approval-for-an-exception"></a>Revocar la aprobación de una excepción

Después de aprobar e implementar una excepción solicitada, es posible que descubramos problemas que infringen las condiciones clave que no eran evidentes cuando aprobamos el cambio en primer lugar. En esta situación, es posible que deba revocar la aprobación de la excepción.

Si debemos revocar la aprobación de la excepción, se lo notificaremos mediante el portal de administración de Microsoft Managed Desktop. Desde la primera vez que le notificamos, tiene 90 días para quitar la excepción antes de que los dispositivos con la excepción ya no estén enlazados por los contratos de nivel de servicio de Escritorio administrado de Microsoft.

Te enviaremos varias notificaciones según una escala de tiempo estricta. Sin embargo, un incidente grave o una amenaza puede requerir que cambiemos la escala de tiempo de nuestras decisiones sobre una excepción. No eliminaremos *una excepción* sin su consentimiento. Sin embargo, cualquier dispositivo con una excepción revocada ya no estará vinculado por nuestro contrato de nivel de servicio. La siguiente tabla es la escala de tiempo de las notificaciones que le enviaremos:

| Tipo de aviso | Descripción |
| ----- | ----- |
| Primer aviso | Proporcionamos la siguiente información en el primer aviso: <ul><li>Información sobre por qué la revocamos.</li><li>Las acciones que le recomendamos que lleve a cabo.</li><li>La fecha límite para esas acciones.</li><Li>Pasos a seguir si desea recurrir la decisión.</li></ul> <br>Este aviso se produce con 90 días de antelación antes de que se quite la excepción de todos los dispositivos. |
| Segundo aviso (30 días después) | Proporcionamos un segundo aviso, incluida la misma información proporcionada en el primer aviso. |
| Tercer aviso (60 días después del primer aviso) | Proporcionamos un tercer aviso, incluida la misma información proporcionada en el primer aviso. |
| Aviso final (una semana antes de la fecha límite de 90 días) | Proporcionamos un cuarto aviso, incluida la misma información proporcionada en el primer aviso. |
| 90 días después del primer aviso| Los acuerdos de nivel de servicio de Escritorio administrado de Microsoft ya no se aplican a ningún dispositivo que tenga la excepción revocada. En cualquier momento, puede impugnar la decisión y proporcionar información adicional para su consideración, incluida la actualización, los cambios de configuración o el cambio de software. |
