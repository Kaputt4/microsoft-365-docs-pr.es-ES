---
title: Excepciones para el plan de servicios
description: Cómo solicitar excepciones al plan de servicio estándar
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 97fe3fe1734908c46dcfff4acd76ce9ae5b8b1a5
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841272"
---
# <a name="exceptions-to-the-service-plan"></a>Excepciones para el plan de servicios

Escritorio administrado de Microsoft proporciona una lista de dispositivos [protegida,](device-policies.md)configuración estándar de dispositivos, requisitos de aplicaciones y determinadas configuraciones [configurables,](../working-with-managed-desktop/config-setting-overview.md)todo ello diseñado para proporcionar una experiencia segura, productiva y agradable para los usuarios. Es mejor permanecer siempre con el servicio según lo proporcionado. Sin embargo, reconocemos que es posible que algunos detalles del servicio no se ajusten exactamente a las necesidades de su organización. Si cree que necesita modificar el servicio de alguna manera, es importante que siga los siguientes procesos para solicitar esos cambios.
 
## <a name="types-of-exceptions"></a>Tipos de excepciones

Una excepción es cualquier adición o cambio a la configuración base de Escritorio administrado de Microsoft; Algunos ejemplos van desde la configuración de puertos USB hasta la implementación de un nuevo controlador de dispositivo. Agrupamos varias excepciones de la siguiente manera:

|Tipo  |Description  |
|---------|---------|
|Software de productividad     |  Software en primer plano que necesitan los usuarios, restringido por los [requisitos de la aplicación](mmd-app-requirements.md)       |
|Agentes de seguridad & VPN     |  Software usado para proteger, supervisar o cambiar el comportamiento del dispositivo o la red       |
|Supervisión de la experiencia digital     |  Software usado para realizar un seguimiento de los datos del dispositivo de un usuario para informar a LA       |
|Controladores de hardware o software     |   Controladores de dispositivo, restringidos por los [requisitos de la aplicación](mmd-app-requirements.md)      |
|Directivas     | Configuración de Aplicaciones de Windows 10 o Aplicaciones de Microsoft 365 para empresas en un dispositivo administrado        |
|Dispositivos     | Dispositivos que no están en la lista de dispositivos de Escritorio [administrado de](device-list.md) Microsoft        |
|Otros     |  Todo lo que no está cubierto por las otras áreas       |
 
## <a name="request-an-exception"></a>Solicitar una excepción

Envíe solicitudes a través del portal de administración de escritorio administrado de Microsoft mediante la creación de una solicitud de cambio. Asegúrese de incluir estos detalles:

-   Tipo de exención: ¿Qué categoría de excepción es? (vea la tabla anterior)
-   Requisito: ¿Cuál es el requisito empresarial específico para la excepción?
-   Propuesta: ¿Qué solución está solicitando su empresa?
-   Escala de tiempo: ¿Cuánto tiempo desea que dure esta excepción? 

## <a name="how-we-assess-an-exception-request"></a>Cómo se evalúa una solicitud de excepción

Cuando se revisan las solicitudes de excepción, se evalúan estos factores en este orden:
 
1.  Algunas aplicaciones y directivas que el Escritorio administrado de Microsoft implementa en todos los dispositivos no son negociables, por lo que su solicitud no debe afectar a ellos. Consulta [Configuración del dispositivo](device-policies.md) para obtener más información.
2.  Es probable que se apruebe el software de productividad restringido que requiere un usuario para realizar su trabajo. 
3.  Si podemos cumplir su requisito con la tecnología de Microsoft, es probable que apruebemos su solicitud para un período de migración de excepción de tres a 12 meses (según el ámbito del proyecto).
4.  Si no podemos cumplir su requisito con la tecnología de Microsoft, es probable que apruebemos su solicitud a menos que infrinja una de las siguientes condiciones.  

Estos principios garantizan que el Escritorio administrado de Microsoft siempre pueda satisfacer sus necesidades mientras se rastrean las desviaciones de nuestra plantilla estándar. 

## <a name="key-conditions"></a>Condiciones clave

Se revisan las excepciones para asegurarse de que no infringen ninguna de estas condiciones:

-   Una excepción no debe afectar negativamente a la seguridad del sistema. 
-   Mantener la excepción no debe implicar un costo significativo para las operaciones o el soporte técnico de Escritorio administrado de Microsoft.
-   Una excepción no debe afectar a la estabilidad del sistema, por ejemplo, al provocar bloqueos o bloqueos en el modo kernel.
-   El cambio no nos debe restringir el funcionamiento del servicio ni entra en conflicto con la tecnología principal de Escritorio administrado de Microsoft.

Estas condiciones podrían cambiar en el futuro. Si hacemos estos cambios, proporcionaremos un aviso de 30 días antes de que esas condiciones entren en vigor.  Si El Escritorio administrado de Microsoft ofrece una forma alternativa de cumplir una excepción aprobada, Escritorio administrado de Microsoft notificará al cliente si El Escritorio administrado de Microsoft modifica la forma de admitir la excepción. 

## <a name="revoking-approval-for-an-exception"></a>Revocar la aprobación de una excepción

Después de aprobar e implementar una excepción solicitada, es posible que descubramos problemas que infringen las condiciones clave que no eran evidentes cuando aprobamos el cambio en primer lugar. En esta situación, es posible que deba revocar la aprobación de la excepción.
 
Si esto ocurre, se lo notificaremos mediante el portal de administración de Escritorio administrado de Microsoft. Desde la primera vez que le notificamos, tiene 90 días para quitar la excepción antes de que los dispositivos con la excepción ya no estén enlazados por los contratos de nivel de servicio de Escritorio administrado de Microsoft. Le enviaremos varias notificaciones según una escala de tiempo estricta; sin embargo, un incidente grave o una amenaza puede requerir que cambiemos la escala de tiempo o nuestras decisiones sobre una excepción. No quitaremos *una* excepción sin su consentimiento, pero cualquier dispositivo con una excepción revocada ya no estará enlazado por nuestro contrato de nivel de servicio. Esta es la escala de tiempo de las notificaciones que te enviaremos:

- **Primer aviso:** Proporcionamos el primer aviso de nuestra decisión de revocar la aprobación, incluida información sobre por qué lo revocamos, las acciones que le recomendamos que realice, la fecha límite para esas acciones y los pasos que debe seguir si desea recurrir la decisión. Este aviso se produce con 90 días de antelación antes de que la excepción deba quitarse de todos los dispositivos. 
- **Segundo aviso (30 días más tarde):** Proporcionamos un segundo aviso, incluida la misma información proporcionada en el primer aviso. 
- **Tercer aviso (60 días después del primer aviso):** Proporcionamos un tercer aviso, incluida la misma información proporcionada en el primer aviso. 
- **Aviso final (una semana antes de la fecha límite de 90 días):** Proporcionamos un cuarto aviso, incluida la misma información proporcionada en el primer aviso.
- **90 días después del primer aviso:** Los contratos de nivel de servicio de Escritorio administrado de Microsoft ya no se aplican a ningún dispositivo que tenga la excepción revocada. En cualquier momento, puede impugnar la decisión y proporcionar información adicional para su consideración, incluida la actualización, los cambios de configuración o el cambio de software. 


