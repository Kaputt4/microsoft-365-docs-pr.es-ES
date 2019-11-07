---
title: Excepciones al plan de servicio
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c9e53278f76665d1b48da0fbeb4555565c183aa
ms.sourcegitcommit: 543ac29a15412a348b61db2297e7bcdcca842206
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38020383"
---
# <a name="exceptions-to-the-service-plan"></a>Excepciones al plan de servicio

Microsoft Managed Desktop proporciona una lista de dispositivos de creados, una [configuración de dispositivo estándar](device-policies.md), requisitos de aplicaciones y algunas [Opciones configurables](../working-with-managed-desktop/config-setting-overview.md), todas diseñadas para proporcionar una experiencia segura, productiva y agradable a los usuarios finales. Es mejor permanecer siempre con el servicio tal y como se proporciona. Sin embargo, reconocemos que algunos detalles del servicio podrían no ajustarse exactamente a las necesidades de su organización. Si cree que debe modificar el servicio de alguna manera, es importante seguir los siguientes procesos para solicitar dichos cambios.

 
## <a name="types-of-exceptions"></a>Tipos de excepciones
Una excepción es cualquier adición o cambio de la configuración de base de escritorio administrada de Microsoft; los ejemplos abarcan desde la configuración de puertos USB hasta la implementación de un nuevo agente de seguridad. Agrupamos varias excepciones de la siguiente manera:


|Tipo  |Description  |
|---------|---------|
|Software de productividad     |  Software de primer plano necesario para los usuarios finales, restringido por los requisitos de la [aplicación](mmd-app-requirements.md)       |
|Agentes de seguridad & VPN     |  Software usado para proteger, supervisar o cambiar el comportamiento del dispositivo o la red       |
|Supervisión de la experiencia digital     |  Software que se usa para realizar un seguimiento de los datos en el dispositivo de un usuario para generar informes       |
|Controladores de hardware o software     |   Controladores de dispositivo, restringidos por los requisitos de la [aplicación](mmd-app-requirements.md)      |
|Directivas     | Configuración de Windows 10 u Office 365 ProPlus en un dispositivo administrado        |
|Dispositivos     | Dispositivos que no se encuentran en la lista de [dispositivos](device-list.md) de escritorio administrados de Microsoft        |
|Otros     |  Todo lo que no cubre el resto de áreas       |



 
## <a name="request-an-exception"></a>Solicitar una excepción

Envíe solicitudes a través del portal de administración de escritorio administrado de Microsoft mediante la creación de una solicitud de cambio. Asegúrese de incluir estos detalles:
-    tipo: ¿qué categoría de excmption? (vea la tabla anterior)
-   Requisito: ¿Cuáles son los requisitos empresariales específicos para el?
-   Propuesta: ¿Qué solución es la que solicita la empresa?
-   Escala de tiempo: ¿Cuánto tiempo desea que dure esta excepción? 


## <a name="how-we-assess-an-exception-request"></a>Cómo evaluaremos una solicitud de excepción

Cuando se revisan las solicitudes de excepción, se evalúan estos factores en este orden:
 
1.  Algunas aplicaciones y directivas que Microsoft administraba escritorio implementa en todos los dispositivos no son negociables, por lo que la solicitud no debe afectar a las mismas. Vea [configuración de dispositivos](device-policies.md) para obtener más información.
2.  Es probable que se apruebe el software de productividad restringido requerido por un usuario final para realizar su trabajo. 
3.  Si podemos cumplir sus requisitos con la tecnología de Microsoft, probablemente aprobamos su solicitud para un período de migración de excepciones de tres a doce meses (según el ámbito del proyecto).
4.  Si no podemos cumplir sus requisitos con la tecnología de Microsoft, probablemente aprobará su solicitud a menos que infrinja una de las condiciones siguientes.  

Estos principios garantizan que Microsoft Managed Desktop siempre satisfaga sus necesidades mientras realiza un seguimiento de las desviaciones de nuestra plantilla estándar. 

## <a name="key-conditions"></a>Condiciones clave

Se revisan las excepciones para asegurarse de que no infringen ninguna de estas condiciones:

-   Una excepción no debe afectar negativamente a la seguridad del sistema. 
-   El mantenimiento de la excepción no debe incurrir en un costo significativo para las operaciones de escritorio administradas de Microsoft o el soporte técnico.
-   Una excepción no debe afectar a la estabilidad del sistema, por ejemplo, al provocar bloqueos de modo de kernel o bloqueos.
-   El cambio no debe restringirnos para operar el servicio o entrar en conflicto con la tecnología de escritorio administrada principal de Microsoft.

Estas condiciones podrían cambiar en el futuro. Si hacemos estos cambios, proporcionaremos un aviso de 30 días antes de que estas condiciones entren en vigor.

## <a name="revoking-approval-for-an-exception"></a>Revocar la aprobación para una excepción

Después de que se apruebe e implemente una excepción solicitada, es posible que se detecten problemas que infrinjan las condiciones clave que no eran evidentes cuando se aprobó el cambio en primer lugar. En esta situación, es posible que tenga que revocar la aprobación para el.
 
Si esto ocurre, le enviaremos una notificación mediante el portal de administración de escritorio administrado de Microsoft. Desde la primera vez que le notificamos, tiene 90 días para quitar la excepción antes de que los dispositivos con la excepción ya no estén asociados por los contratos de nivel de servicio de escritorio administrado por Microsoft. Le enviaremos varias notificaciones de acuerdo con una escala de tiempo estricta, pero es posible que un incidente o una amenaza graves deban cambiar la escala de tiempo o nuestras decisiones sobre una excepción. No se *elimina* una excepción sin su consentimiento, pero los dispositivos con una excepción revocada dejarán de estar vinculados por nuestro contrato de nivel de servicio. Esta es la escala de tiempo de las notificaciones que le enviaremos:

- **Primer aviso:** Le proporcionamos el primer aviso de nuestra decisión de revocar la aprobación, que incluye información sobre por qué la revocación, las acciones que le aconsejamos realizar, la fecha límite para esas acciones y los pasos que debe seguir si desea apelar la decisión. Esto es de 90 días antes de que la excepción deba quitarse de todos los dispositivos. 
- **Segundo aviso (30 días después):** Proporcionamos un segundo aviso, que incluye la misma información que se proporciona en el primer aviso. 
- **Tercer aviso (60 días después del primer aviso):** Se proporciona un tercer aviso, que incluye la misma información que se proporciona en el primer aviso. 
- **Aviso final (1 semana antes de la fecha límite de 90 días):** Proporcionamos un cuarto aviso, que incluye la misma información que se proporciona en el primer aviso.
- **90 días después de la primera notificación:** Los contratos de nivel de servicio de escritorio administrados por Microsoft ya no se aplican a los dispositivos que tengan la revocación. En cualquier momento, puede desafiar la decisión y proporcionar información adicional para tener en cuenta, como la actualización, los cambios de configuración o el cambio de software. 

