---
title: Programador para Microsoft 365 preguntas frecuentes
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Programador para Microsoft 365 preguntas frecuentes
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286266"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Programador para Microsoft 365 preguntas frecuentes

**Pregunta:** ¿Cómo se integra Scheduler con otras características de Cortana, como *Cortana para Windows,* *Daily Briefing Email* y *Reproducir Mis correos electrónicos?*</br>
Scheduler es un servicio independiente de otras características de Cortana. Otras características de Cortana se pueden deshabilitar en el nivel de inquilino y el Programador aún se puede habilitar mediante el uso de la cortana@yourdomain.com de correo electrónico. Actualmente, los usuarios solo pueden interactuar con el Programador por correo electrónico.

**Pregunta:** ¿Funciona solo con Outlook? ¿Se admiten otros productos de correo electrónico?</br>
Siempre que tenga una licencia, aparte de los tres requisitos anteriores, los usuarios pueden enviar cortana@yourdomain.com correo electrónico desde cualquier cliente de correo electrónico en cualquier dispositivo.

**Pregunta:** ¿Los contactos pueden estar en una lista de contactos personal en Outlook y GAL u otra empresa equivalente?</br>
Los asistentes a la reunión pueden ser cualquier persona con una dirección de correo electrónico dentro o fuera de la empresa. Desafortunadamente, el Programador no puede traducir automáticamente nombres a direcciones de correo electrónico o alias si lo busca en la GAL actual.

**Pregunta:** ¿Puedo usar Scheduler con mi versión instalada (local) de Outlook?</br>
El programador requiere Exchange Online. No funciona con Exchange Server (on-prem). Funciona con cualquier cliente de correo electrónico, Outlook escritorio, OWA, iOS, android, gmail, y así sucesivamente.

**Pregunta:** ¿Outlook debe estar abierto en segundo plano?</br>
Outlook no es necesario que esté abierto en segundo plano. Todo lo que necesita hacer es enviar un correo a Cortana y confiar en él para realizar la mayor parte del trabajo.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Preguntas más frecuentes sobre confianza y privacidad

**Pregunta:** ¿Cómo funciona scheduler?</br>
El programador usa inteligencia de programación (IA) aumentada con asistentes humanos. Si los modelos de IA generan una necesidad de soporte técnico en el lenguaje natural de comunicación con Cortana, la solicitud de reunión se escala a un humano para su revisión y finalización.

**Pregunta:** Quién son los humanos que revisan solicitudes escaladas? </br>
Los asistentes del programador están certificados por Microsoft Supplier Security and Privacy Assurance (SSPA) para obtener información personal y extremadamente confidencial. 

**Pregunta:** ¿Qué pueden ver los asistentes de SSPA?</br>
El programador y los asistentes de SSPA pueden ver los correos electrónicos dirigidos a Cortana. En un intercambio de correo electrónico con subprocesos, solo se procesarán los correos electrónicos que incluyan la dirección de correo electrónico de Cortana, no los correos electrónicos anteriores en el subproceso antes de agregar Cortana.   

**Pregunta:** ¿Se conservan los datos del cliente en el objeto Data Flow? </br>
El programador almacena todo el contenido del cliente dentro de los límites del espacio empresarial y retiene los datos de acuerdo con las directrices del RGPD, las directivas de Microsoft 365 confianza & privacidad y las directivas de correo electrónico del inquilino.

**Pregunta:** ¿Cómo procesa scheduler los datos de disponibilidad de los asistentes internos? </br>
La automatización del programador usa el *servicio findMeetingTimes* para identificar las horas que están disponibles mutuamente para los asistentes y el organizador. Este servicio ofrece otras Outlook experiencias como *Horarios sugeridos* en el Outlook de reunión. La información de los asistentes de disponibilidad no se consume explícitamente como bloques de disponibilidad. 

**Pregunta:** ¿Es compatible el RGPD del programador? </br>
Sí.

**Pregunta:** Quién tiene acceso al buzón de Cortana? </br>
El programador procesa las solicitudes de reunión y los correos electrónicos asociados que se envían al buzón de Cortana del inquilino. Microsoft no tiene ningún otro acceso al buzón de Cortana excepto a través de la aprobación de la caja de seguridad a petición del administrador del espacio empresarial.  

**Pregunta:** ¿Se usan datos de clientes para entrenar modelos de inteligencia artificial?</br>
No se puede usar ningún contenido de cliente de Scheduler Microsoft 365 para conjuntos de aprendizaje de datos. Todo el contenido del cliente reside en el inquilino del cliente.  

**Pregunta:** ¿El programador procesará el correo cifrado?</br>
No, el flujo de trabajo del Programador rechazará el correo cifrado. 




