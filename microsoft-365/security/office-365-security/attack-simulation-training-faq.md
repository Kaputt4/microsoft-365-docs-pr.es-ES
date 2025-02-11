---
title: 'Implementación y preguntas más frecuentes del aprendizaje de simulación de ataques  '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection: m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las consideraciones de implementación y las preguntas más frecuentes sobre la simulación de ataques y el entrenamiento en organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 75dfa3281785dc06906ed66384e63d3867f617b2
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68088715"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Implementación y preguntas más frecuentes del aprendizaje de simulación de ataques  

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Entrenamiento de simulación de ataque permite a las organizaciones Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 medir y administrar el riesgo de ingeniería social al permitir la creación y administración de simulaciones de suplantación de identidad (phishing) con tecnología real, cargas de phishing des armas. El entrenamiento hiperesparáfico, ofrecido en asociación con la seguridad de Terranova, ayuda a mejorar el conocimiento y a cambiar el comportamiento de los empleados.

Para obtener más información sobre cómo empezar a trabajar con Entrenamiento de simulación de ataque, consulte [Introducción al uso de Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md).

Aunque toda la experiencia de creación y programación de simulaciones se ha diseñado para que sea de flujo libre y sin fricción, la ejecución de simulaciones a escala empresarial a menudo requiere planeamiento. Este artículo ayuda a abordar desafíos específicos que vemos cuando nuestros clientes ejecutan simulaciones en sus propios entornos.

## <a name="issues-with-end-user-experiences"></a>Problemas con las experiencias del usuario final

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Direcciones URL de simulación de suplantación de identidad bloqueadas por la exploración segura de Google

Un servicio de reputación de direcciones URL podría identificar una o varias de las direcciones URL que usa Entrenamiento de simulación de ataque como no seguras. Google Safe Browsing en Google Chrome bloquea algunas de las direcciones URL de suplantación de identidad simuladas con un mensaje **de anticipación de un sitio engañoso** . Aunque trabajamos con muchos proveedores de reputación de direcciones URL para permitir siempre nuestras direcciones URL de simulación, no siempre tenemos cobertura completa.

:::image type="content" source="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png" alt-text="Advertencia previa del sitio engañoso en Google Chrome" lightbox="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png":::

Tenga en cuenta que este problema no afecta a Microsoft Edge.

Como parte de la fase de planeación, asegúrese de comprobar la disponibilidad de la dirección URL en los exploradores web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing). Si Google Safe Browsing bloquea las direcciones URL, [siga esta guía](https://support.google.com/chrome/a/answer/7532419) de Google para permitir el acceso a las direcciones URL.

Consulte [Introducción al uso de Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md) para obtener la lista de direcciones URL que usa actualmente Entrenamiento de simulación de ataque.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>Simulación de suplantación de identidad (phishing) y direcciones URL de administración bloqueadas por soluciones de proxy de red y controladores de filtro

Tanto las direcciones URL de simulación de suplantación de identidad como las direcciones URL de administrador pueden bloquearse o quitarse mediante los filtros o dispositivos de seguridad intermedios. Por ejemplo:

- Firewalls
- soluciones de Web Application Firewall (WAF)
- Controladores de filtro de terceros (por ejemplo, filtros de modo kernel)

Aunque hemos visto que pocos clientes están bloqueados en esta capa, sí sucede. Si tiene problemas, considere la posibilidad de configurar las siguientes direcciones URL para omitir el examen por parte de los dispositivos de seguridad o filtros según sea necesario:

- Las direcciones URL de suplantación de identidad simuladas como se describe en [Introducción al uso de Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md).
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Mensajes de simulación que no se entregan a todos los usuarios de destino

Es posible que el número de usuarios que reciben realmente los mensajes de correo electrónico de simulación sea menor que el número de usuarios a los que se ha dirigido la simulación. Los siguientes tipos de usuarios se excluirán como parte de la validación de destino:

- Direcciones de correo electrónico de destinatario no válidas.
- Usuarios invitados.
- Usuarios que ya no están activos en Azure Active Directory (Azure AD).

Solo se incluirán en simulaciones los usuarios válidos que no sean invitados con un buzón válido. Si usa grupos de distribución o grupos de seguridad habilitados para correo para dirigirse a los usuarios, puede usar el cmdlet [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ver y validar los miembros del grupo de distribución.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problemas con los informes de Entrenamiento de simulación de ataque

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>Entrenamiento de simulación de ataque informes no contienen detalles de actividad

Entrenamiento de simulación de ataque incluye información enriquecida y procesable que le mantiene informado del progreso de preparación de amenazas de sus empleados. Si Entrenamiento de simulación de ataque informes no se rellenan con datos, compruebe que la búsqueda de registros de auditoría está activada en su organización (está activada de forma predeterminada).

La búsqueda de registros de auditoría es necesaria por Entrenamiento de simulación de ataque para que los eventos se puedan capturar, grabar y leer. La desactivación de la búsqueda de registros de auditoría tiene las siguientes consecuencias para Entrenamiento de simulación de ataque:

- Los datos de informes no están disponibles en todos los informes. Los informes aparecerán vacíos.
- Las asignaciones de entrenamiento están bloqueadas, ya que los datos no están disponibles.

Para activar la búsqueda de registros de auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

> [!NOTE]
> Los detalles de actividad vacíos también pueden deberse a que no se asignan licencias E5 a los usuarios. Compruebe que se asigna al menos una licencia E5 a un usuario activo para asegurarse de que los eventos de informes se capturan y registran.

### <a name="simulation-reports-are-not-updated-immediately"></a>Los informes de simulación no se actualizan inmediatamente

Los informes detallados de simulación no se actualizan inmediatamente después de iniciar una campaña. No te preocupes; se espera este comportamiento.

Cada campaña de simulación tiene un ciclo de vida. Cuando se crea por primera vez, la simulación está en estado **Programado** . Cuando se inicia la simulación, pasa al estado **En curso** . Cuando se completa, la simulación pasa al estado **Completado** .

Mientras una simulación está en estado **Programado** , los informes de simulación estarán principalmente vacíos. Durante esta fase, el motor de simulación está resolviendo las direcciones de correo electrónico de usuario de destino, expandiendo grupos de distribución, quitando usuarios invitados de la lista, etc.:

:::image type="content" source="../../media/attack-sim-training-faq-scheduled-state.png" alt-text="Detalles de la simulación que muestran la simulación en estado Programado" lightbox="../../media/attack-sim-training-faq-scheduled-state.png":::

Una vez que la simulación entra en la fase **En curso** , observará que la información empieza a llegar a la generación de informes:

:::image type="content" source="../../media/attack-sim-training-faq-in-progress-state.png" alt-text="Detalles de la simulación que muestran la simulación en el estado En curso" lightbox="../../media/attack-sim-training-faq-in-progress-state.png":::

Los informes de simulación individuales pueden tardar hasta 30 minutos en actualizarse después de la transición al estado **En curso** . Los datos del informe continúan compilando hasta que la simulación alcanza el estado **Completado** . Las actualizaciones de informes se producen a los intervalos siguientes:

- Cada 10 minutos durante los primeros 60 minutos.
- Cada 15 minutos después de 60 minutos hasta 2 días.
- Cada 30 minutos después de 2 días hasta 7 días.
- Cada 60 minutos después de 7 días.

Los widgets de la página **Información general** proporcionan una instantánea rápida de la posición de seguridad basada en simulación de su organización a lo largo del tiempo. Dado que estos widgets reflejan la posición de seguridad general y el recorrido a lo largo del tiempo, se actualizan una vez completada cada campaña de simulación.

> [!NOTE]
> Puede usar la opción **Exportar** en las distintas páginas de informes para extraer datos.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>Los mensajes notificados como suplantación de identidad (phishing) por los usuarios no aparecen en los informes de simulación

Los informes de simulación del entrenamiento del simulador de ataques proporcionan detalles sobre la actividad del usuario. Por ejemplo:

- Usuarios que han hecho clic en el vínculo del mensaje.
- Usuarios que han renunciado a sus credenciales.
- Usuarios que notificaron el mensaje como suplantación de identidad (phishing).

Si los mensajes que los usuarios notifican como suplantación de identidad no se capturan en Entrenamiento de simulación de ataque informes de simulación, puede haber una regla de flujo de correo de Exchange (también conocida como regla de transporte) que bloquee la entrega de los mensajes notificados a Microsoft. Compruebe que las reglas de flujo de correo no bloquean la entrega a las siguientes direcciones de correo electrónico:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- no\_junk@office365.microsoft.com

### <a name="users-are-assigned-training-after-they-report-a-simulated-message"></a>A los usuarios se les asigna un entrenamiento después de informar de un mensaje simulado

Si a los usuarios se les asigna un entrenamiento después de informar de un mensaje de simulación de suplantación de identidad (phishing), compruebe si su organización tiene un **buzón personalizado** configurado en la **directiva de envío de usuarios**. Al configurar un **buzón personalizado**, este buzón debe excluirse de las directivas vínculos seguros y datos adjuntos seguros según los [requisitos previos del buzón personalizado](user-submission.md).

Si su organización tiene configurado un **buzón personalizado** y no ha configurado las exclusiones necesarias, estos mensajes pueden detonarse, lo que provoca asignaciones de entrenamiento.

## <a name="other-frequently-asked-questions"></a>Otras preguntas más frecuentes

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>P: ¿Cuál es el método recomendado para dirigirse a los usuarios para las campañas de simulación?

R: Hay varias opciones disponibles para los usuarios de destino:

- Incluya todos los usuarios (actualmente disponibles para organizaciones con menos de 40 000 usuarios).
- Elija usuarios específicos.
- Seleccione usuarios de un archivo CSV (una dirección de correo electrónico por línea).
- Destino basado en grupos de Azure AD.

Hemos descubierto que las campañas en las que los grupos de Azure AD identifican a los usuarios de destino suelen ser más fáciles de administrar.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>P: ¿Hay límites en el destino de los usuarios al importar desde un ARCHIVO CSV o agregar usuarios?

R: El límite para importar destinatarios desde un archivo CSV o agregar destinatarios individuales a una simulación es de 40 000.

Un destinatario puede ser un usuario individual o un grupo. Un grupo puede contener cientos o miles de destinatarios, por lo que no se coloca un límite real en el número de usuarios individuales.

Administrar un archivo CSV grande o agregar muchos destinatarios individuales puede resultar complicado. El uso de grupos de Azure AD simplificará la administración general de la simulación.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>P: ¿Proporciona Microsoft cargas útiles en otros idiomas?

R: Actualmente, hay más de 40 cargas localizadas disponibles en más de 10 idiomas: chino (simplificado), chino (tradicional), inglés, francés, alemán, italiano, japonés, coreano, portugués, ruso, español y holandés. Hemos observado que las traducciones directas o automáticas de cargas útiles existentes a otros lenguajes provocarán imprecisiones y una menor relevancia.

Dicho esto, puede crear su propia carga en el lenguaje que prefiera mediante la experiencia de creación de carga personalizada. También se recomienda encarecidamente recopilar las cargas existentes que se usaron para dirigirse a los usuarios de una geografía específica. En otras palabras, deje que los atacantes localicen el contenido por usted.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>P: ¿Cómo puedo cambiar a otros idiomas para mi portal de administración y experiencia de entrenamiento?

R: En Microsoft 365 o Office 365, la configuración del lenguaje es específica y centralizada para cada cuenta de usuario. Para obtener instrucciones sobre cómo cambiar la configuración de idioma, vea [Cambiar el idioma de visualización y la zona horaria en Microsoft 365 para empresas](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).

Tenga en cuenta que el cambio de configuración puede tardar hasta 30 minutos en sincronizarse entre todos los servicios.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>P: ¿Puedo desencadenar una simulación de prueba para comprender su aspecto antes de iniciar una campaña completa?

R: ¡Sí se puede! En la última página **Revisar simulación** del asistente para crear una nueva simulación, hay una opción para **Enviar una prueba**. Esta opción enviará un mensaje de simulación de suplantación de identidad (phishing) de ejemplo al usuario que ha iniciado sesión actualmente. Después de validar el mensaje de suplantación de identidad en la Bandeja de entrada, puede enviar la simulación.

:::image type="content" source="../../media/attack-sim-training-simulations-review-simulation.png" alt-text="Botón Enviar una prueba en la página Revisar simulación" lightbox="../../media/attack-sim-training-simulations-review-simulation.png":::

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>P: ¿Puedo dirigirme a usuarios que pertenecen a un inquilino diferente como parte de la misma campaña de simulación?

R: No. Actualmente, no se admiten simulaciones entre inquilinos. Compruebe que todos los usuarios de destino están en el mismo inquilino. Los usuarios entre inquilinos o los usuarios invitados se excluirán de la campaña de simulación.

### <a name="q-how-does-region-aware-delivery-work"></a>P: ¿Cómo funciona la entrega con reconocimiento de la región?

R: La entrega compatible con la región usa el atributo TimeZone del buzón de correo del usuario de destino y la lógica "no antes" para determinar cuándo entregar el mensaje. Por ejemplo, imagine la situación siguiente:

- A las 7:00 am en la zona horaria del Pacífico (UTC-8), un administrador crea y programa una campaña para que comience a las 9:00 AM del mismo día.
- UserA está en la zona horaria oriental (UTC-5).
- UserB también está en la zona horaria del Pacífico.

A las 9:00 am del mismo día, el mensaje de simulación se envía a UserB. Con la entrega compatible con la región, el mensaje no se envía a UserA el mismo día, ya que la hora del Pacífico a las 9:00 es la hora del Este a las 12:00 p.m. En su lugar, el mensaje se envía a UserA a las 9:00 a.m. hora del Este del día siguiente.

Por lo tanto, en la ejecución inicial de una campaña con la entrega compatible con la región habilitada, podría parecer que el mensaje de simulación se envió solo a los usuarios de una zona horaria específica. Sin embargo, a medida que pase el tiempo y más usuarios entren en el ámbito, los usuarios de destino aumentarán.


### <a name="q-does-microsoft-collect-or-store-any-information-that-users-enter-at-the-credential-harvest-sign-in-page-used-in-the-credential-harvest-simulation-technique"></a>P: ¿Recopila Microsoft o almacena información que los usuarios escriben en la página de inicio de sesión de Credential Harvest, usada en la técnica de simulación de Credential Harvest?

R: No. Cualquier información especificada en la página de inicio de sesión de la cosecha de credenciales se descarta silenciosamente. Solo se registra el "clic" para capturar el evento de riesgo. Microsoft no recopila, registra ni almacena los detalles que los usuarios escriben en este paso.
