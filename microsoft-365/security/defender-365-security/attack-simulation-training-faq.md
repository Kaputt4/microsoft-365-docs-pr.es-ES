---
title: 'Implementación y preguntas más frecuentes del aprendizaje de simulación de ataques  '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las consideraciones de implementación y las preguntas más frecuentes sobre la simulación de ataques y el aprendizaje en organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073568"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Implementación y preguntas más frecuentes del aprendizaje de simulación de ataques  

El entrenamiento de simulación de ataques [ya está disponible en general.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291) El aprendizaje de simulación de ataques permite a las organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 medir y administrar los riesgos de ingeniería social al permitir la creación y administración de simulaciones de suplantación de identidad (phishing) que funcionan con cargas de suplantación de identidad sin armas reales. El aprendizaje hiperespacio, impartido en asociación con la seguridad de Terranova, ayuda a mejorar el conocimiento y cambiar el comportamiento de los empleados.

Para obtener más información sobre cómo empezar con el aprendizaje de simulación de ataques, consulta [Introducción al entrenamiento de simulación de ataques.](attack-simulation-training-get-started.md)

Aunque toda la experiencia de creación y programación de simulación se ha diseñado para que fluya libremente y sin fricción, la ejecución de simulaciones a escala empresarial a menudo requiere planeación. Este artículo ayuda a abordar desafíos específicos que vemos cuando nuestros clientes ejecutan simulaciones en sus propios entornos.

## <a name="issues-with-end-user-experiences"></a>Problemas con las experiencias del usuario final

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Direcciones URL de simulación de suplantación de identidad bloqueadas por Google Safe Browsing

Un servicio de reputación de direcciones URL puede identificar una o varias de las direcciones URL que usa el entrenamiento de simulación de ataques como no seguras. Google Safe Browsing en Google Chrome bloquea algunas de las direcciones URL de suplantación de identidad simuladas con un mensaje de sitio **engañoso** delante. Aunque trabajamos con muchos proveedores de reputación de direcciones URL para permitir siempre nuestras direcciones URL de simulación, no siempre tenemos cobertura completa.

![Advertencia de sitio engañoso en Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

Tenga en cuenta que este problema no afecta a Microsoft Edge.

Como parte de la fase de planeación, asegúrese de comprobar la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad. Si Google Safe Browsing bloquea las direcciones URL, [sigue](https://support.google.com/chrome/a/answer/7532419) estas instrucciones de Google para permitir el acceso a las direcciones URL.

Consulta Introducción [al aprendizaje de simulación de ataque](attack-simulation-training-get-started.md) para obtener la lista de direcciones URL que usa actualmente el entrenamiento de simulación de ataques.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>Direcciones URL de administrador y simulación de suplantación de identidad bloqueadas por soluciones de proxy de red y controladores de filtro

Las direcciones URL de simulación de suplantación de identidad (phishing) y las direcciones URL de administrador pueden bloquearse o eliminarse mediante los filtros o dispositivos de seguridad intermedios. Por ejemplo:

- Firewalls
- Soluciones de Firewall de aplicaciones web (WAF)
- Controladores de filtro de terceros (por ejemplo, filtros de modo kernel)

Aunque hemos visto pocos clientes bloqueados en esta capa, esto sucede. Si tiene problemas, considere la posibilidad de configurar las siguientes direcciones URL para omitir el examen de los dispositivos de seguridad o filtros según sea necesario:

- Las direcciones URL de suplantación de identidad simuladas, como se describe en [Introducción al aprendizaje de simulación de ataques.](attack-simulation-training-get-started.md)
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Mensajes de simulación no entregados a todos los usuarios dirigidos

Es posible que el número de usuarios que reciben realmente los mensajes de correo electrónico de simulación sea menor que el número de usuarios dirigidos por la simulación. Los siguientes tipos de usuarios se excluirán como parte de la validación de destino:

- Direcciones de correo electrónico de destinatarios no válidas.
- Usuarios invitados.
- Usuarios que ya no están activos en Azure Active Directory (Azure AD).

Solo se incluirán en las simulaciones los usuarios válidos que no sean invitados con un buzón válido. Si usa grupos de distribución o grupos de seguridad habilitados para correo para dirigirse a los usuarios, puede usar el cmdlet [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ver y validar miembros del grupo de distribución.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problemas con los informes de aprendizaje de simulación de ataques

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>Los informes de aprendizaje de simulación de ataques no contienen detalles de actividad

El aprendizaje de simulación de ataques incluye información amplia y útil que te mantiene informado del progreso de preparación de amenazas de tus empleados. Si los informes de aprendizaje de simulación de ataque no se rellenan con datos, compruebe que la búsqueda del registro de auditoría está activada en su organización (está activada de forma predeterminada).

El entrenamiento de simulación de ataque requiere la búsqueda del registro de auditoría para que los eventos se puedan capturar, grabar y leer de nuevo. Desactivar la búsqueda del registro de auditoría tiene las siguientes consecuencias para el aprendizaje de simulación de ataques:

- Los datos de informes no están disponibles en todos los informes. Los informes aparecerán vacíos.
- Las asignaciones de aprendizaje se bloquean, ya que los datos no están disponibles.

Para activar o desactivar la búsqueda del registro de auditoría, vea Activar o desactivar la búsqueda del registro [de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> Los detalles de actividad vacíos también pueden deberse a que no se asignan licencias E5 a los usuarios. Compruebe que al menos una licencia de E5 está asignada a un usuario activo para asegurarse de que los eventos de informes se capturan y se registran.

### <a name="simulation-reports-are-not-updated-immediately"></a>Los informes de simulación no se actualizan inmediatamente

Los informes de simulación detallados no se actualizan inmediatamente después de iniciar una campaña. No se preocupe; se espera este comportamiento.

Cada campaña de simulación tiene un ciclo de vida. Cuando se crea por primera vez, la simulación se encuentra en **el estado Programado.** Cuando se inicia la simulación, se pasa al **estado En** curso. Cuando se completa, la simulación pasa al **estado Completado.**

Mientras una simulación está en **estado programado,** los informes de simulación estarán en su mayoría vacíos. Durante esta fase, el motor de simulación está resolviendo las direcciones de correo electrónico del usuario de destino, expandiendo grupos de distribución, quitando usuarios invitados de la lista, etc.:

![Informes en estado programado](../../media/attack-sim-empty-reporting.png)

Una vez que la simulación entra en la **fase en** curso, observará que la información empieza a engañarse en los informes:

![Informes en el estado En curso](../../media/attack-sim-in-progress.png)

Los informes de simulación individuales pueden tardar hasta 30 minutos en actualizarse después de la transición al **estado En** curso. Los datos del informe siguen compilando hasta que la simulación alcanza el **estado Completado.** Las actualizaciones de informes se producen en los siguientes intervalos:

- Cada 10 minutos durante los primeros 60 minutos.
- Cada 15 minutos después de 60 minutos hasta 2 días.
- Cada 30 minutos después de 2 días hasta 7 días.
- Cada 60 minutos después de 7 días.

Los widgets de la **página Información** general proporcionan una instantánea rápida de la posición de seguridad basada en simulación de la organización con el tiempo. Dado que estos widgets reflejan la posición general de seguridad y el recorrido con el tiempo, se actualizan después de que se complete cada campaña de simulación.

> [!NOTE]
> Puede usar la opción **Exportar** en las distintas páginas de informes para extraer datos.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>Los mensajes notificados como suplantación de identidad por parte de los usuarios no aparecen en los informes de simulación

Los informes de simulación en el entrenamiento del simulador de ataque proporcionan detalles sobre la actividad del usuario. Por ejemplo:

- Usuarios que han hecho clic en el vínculo del mensaje.
- Usuarios que entregaron sus credenciales.
- Usuarios que informaron del mensaje como suplantación de identidad.

Si los mensajes que los usuarios informaron como suplantación de identidad no se capturan en los informes de simulación de simulación de ataques, puede haber una regla de flujo de correo de Exchange (también conocida como regla de transporte) que bloquee la entrega de los mensajes notificados a Microsoft. Compruebe que las reglas de flujo de correo no bloquean la entrega a las siguientes direcciones de correo electrónico:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- no \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>Otras preguntas más frecuentes

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>P: ¿Cuál es el método recomendado para dirigirse a los usuarios para campañas de simulación?

A: Hay varias opciones disponibles para los usuarios de destino:

- Incluya todos los usuarios (actualmente disponibles para organizaciones con menos de 40 000 usuarios).
- Elija usuarios específicos.
- Seleccione usuarios de un archivo CSV.
- Destino basado en grupos de Azure AD.

Hemos encontrado que las campañas en las que los grupos de Azure AD identifican a los usuarios dirigidos suelen ser más fáciles de administrar.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>P: ¿Hay límites en la segmentación de usuarios al importar desde un CSV o agregar usuarios?

A: El límite para importar destinatarios desde un archivo CSV o agregar destinatarios individuales a una simulación es de 40 000.

Un destinatario puede ser un usuario individual o un grupo. Un grupo puede contener cientos o miles de destinatarios, por lo que un límite real no se coloca en el número de usuarios individuales.

Administrar un archivo CSV grande o agregar muchos destinatarios individuales puede resultar engorroso. El uso de grupos de Azure AD simplificará la administración general de la simulación.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>P: ¿Microsoft proporciona cargas en otros idiomas?

A: Actualmente, hay 5 cargas localizadas disponibles. Hemos observado que las traducciones directas o automáticas de cargas existentes a otros idiomas provocarán imprecisiones y una menor relevancia.

Dicho esto, puede crear su propia carga en el idioma que prefiera con la experiencia de creación de carga personalizada. También se recomienda encarecidamente que recolecte las cargas existentes que se usaron para dirigirse a los usuarios en una geografía específica. En otras palabras, deja que los atacantes localicen el contenido por ti.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>P: ¿Cómo puedo cambiar a otros idiomas para mi experiencia de aprendizaje y portal de administración?

A: En Microsoft 365 u Office 365, la configuración de idioma es específica y centralizada para cada cuenta de usuario. Para obtener instrucciones sobre cómo cambiar la configuración de idioma, vea Cambiar el idioma para mostrar y la zona horaria [en Microsoft 365 para empresas](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).

Tenga en cuenta que el cambio de configuración puede tardar hasta 30 minutos en sincronizarse en todos los servicios.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>P: ¿Puedo desencadenar una simulación de prueba para comprender cómo es antes de iniciar una campaña completa?

A: ¡Sí se puede! En la última página **Revisar simulación** del asistente para crear una nueva simulación, hay una opción para **Enviar una prueba**. Esta opción enviará un mensaje de simulación de suplantación de identidad (phishing) de ejemplo al usuario que ha iniciado sesión actualmente. Después de validar el mensaje de suplantación de identidad en la Bandeja de entrada, puede enviar la simulación.

![Enviar un botón de prueba en la página Revisar simulación](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>P: ¿Puedo dirigirme a usuarios que pertenecen a un inquilino diferente como parte de la misma campaña de simulación?

R: No. Actualmente, no se admiten simulaciones entre inquilinos. Compruebe que todos los usuarios de destino se encuentran en el mismo espacio empresarial. Los usuarios entre inquilinos o usuarios invitados se excluirán de la campaña de simulación.

### <a name="q-how-does-region-aware-delivery-work"></a>P: ¿Cómo funciona la entrega consciente de la región?

A: La entrega consciente de región usa el atributo TimeZone del buzón del usuario de destino y la lógica "no antes" para determinar cuándo entregar el mensaje. Por ejemplo, considere el siguiente escenario:

- A las 7:00 a.m. en la zona horaria del Pacífico (UTC-8), un administrador crea y programa una campaña para que comience a las 9:00 a.m. del mismo día.
- UserA está en la zona horaria oriental (UTC-5).
- UserB también está en la zona horaria del Pacífico.

A las 9:00 a.m. del mismo día, el mensaje de simulación se envía a UserB. Con la entrega consciente de la región, el mensaje no se envía a UserA el mismo día, ya que la hora del Pacífico de las 9:00 a.m. es a las 12:00 p.m. hora del este. En su lugar, el mensaje se envía a UserA a las 9:00 a.m. hora del este del día siguiente.

Por lo tanto, en la ejecución inicial de una campaña con la entrega consciente de región habilitada, puede parecer que el mensaje de simulación se envió solo a los usuarios de una zona horaria específica. Pero, a medida que pase el tiempo y más usuarios entren en el ámbito, los usuarios dirigidos aumentarán.