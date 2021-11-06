---
title: 'Migrar a Microsoft Defender para Office 365 fase 3: Incorporación'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: Complete los pasos para migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a40ee22ee843d250c90a8b03526ab61fe3ad56f6
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2021
ms.locfileid: "60804646"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>Migrar a Microsoft Defender para Office 365- Fase 3: Incorporación

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|[![Fase 1: Preparar.](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [Fase 1: Preparación](migrate-to-defender-for-office-365-prepare.md)|[![Fase 2: Configurar.](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [Fase 2: Configuración](migrate-to-defender-for-office-365-setup.md)|![Fase 3: Incorporación.](../../media/phase-diagrams/onboard.png) <br> Fase 3: Incorporación|
|---|---|---|
|||*¡Estás aquí!*|

Bienvenido a **la fase 3: Incorporación** de la migración a Microsoft Defender para **[Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los siguientes pasos:

1. [Empezar a incorporar seguridad Teams](#step-1-begin-onboarding-security-teams)
2. [(Opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [Ajustar la inteligencia de suplantación](#step-3-tune-spoof-intelligence)
4. [Ajustar la protección de suplantación y la inteligencia de buzones](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [Usar datos de envíos de usuarios para medir y ajustar](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [(Opcional) Agregar más usuarios al piloto e iterar](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [Extender Microsoft 365 protección a todos los usuarios y desactivar la regla de flujo de correo SCL=-1](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [Cambiar los registros MX](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>Paso 1: Empezar a incorporar seguridad Teams

Si su organización tiene un equipo de respuesta de seguridad, ahora es el momento de empezar a integrar Microsoft Defender para Office 365 en los procesos de respuesta, incluidos los sistemas de vales. Este es un tema completo en sí mismo, pero a veces se pasa por alto. La participación anticipada del equipo de respuesta de seguridad garantizará que su organización esté lista para hacer frente a las amenazas al cambiar los registros MX. La respuesta a incidentes debe estar bien equipada para administrar las siguientes tareas:

- Obtenga información sobre las nuevas herramientas e inténtelas en los flujos existentes. Por ejemplo:
  - La administración de los mensajes en cuarentena es importante. Para obtener instrucciones, consulte [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).
  - El seguimiento de mensajes le permite ver lo que sucedió con los mensajes a medida que entran o dejan Microsoft 365. Para obtener más información, vea [Seguimiento de mensajes en el centro](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)de administración Exchange moderna en Exchange Online .
- Identificar los riesgos que se pueden haber dejado entrar en la organización.
- Ajustar y personalizar [alertas para](../../compliance/alert-policies.md) procesos organizativos.
- Administre la cola de incidentes y corrija los posibles riesgos.

Si su organización ha comprado Microsoft Defender para Office 365 Plan 2, debe empezar a familiarizarse con y usar características como explorador de amenazas, búsqueda avanzada e incidentes. Para obtener cursos relevantes, vea <https://aka.ms/mdoninja> .

Si el equipo de respuesta de seguridad recopila y analiza mensajes sin filtrar, puede configurar un buzón de SecOps para recibir estos mensajes sin filtrar. Para obtener instrucciones, vea [Configure SecOps mailboxes in the advanced delivery policy](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).

### <a name="siemsoar"></a>SIEM/SOAR

Para obtener más información acerca de la integración con SIEM/SOAR, consulte los siguientes artículos:

- [Información general sobre las API de Microsoft 365 Defender](/microsoft-365/security/defender/api-overview)
- [API de streaming](/microsoft-365/security/defender/streaming-api)
- [API de Búsqueda avanzada de amenazas](/microsoft-365/security/defender/api-advanced-hunting)
- [API de incidentes](/microsoft-365/security/defender/api-incident)

Si su organización no tiene un equipo de respuesta de seguridad o flujos de procesos existentes, puede usar este tiempo para familiarizarse con las características básicas de búsqueda y respuesta en Defender para Office 365. Para obtener más información, vea [Threat investigation and response](office-365-ti.md).

### <a name="rbac-roles"></a>Roles RBAC

Los permisos de Defender para Office 365 se basan en el control de acceso basado en roles (RBAC) y se explican en Permisos en el [portal de](permissions-microsoft-365-security-center.md)Microsoft 365 Defender . Estos son los puntos importantes a tener en cuenta:

- Azure AD roles dan permisos a **todas las** cargas de trabajo de Microsoft 365. Por ejemplo, si agrega un usuario al administrador de seguridad en Azure Portal, tienen permisos de administrador de seguridad en todas partes.
- Los & de colaboración de correo electrónico en el portal de Microsoft 365 Defender conceden permisos al portal de Microsoft 365 Defender, al Centro de cumplimiento de Microsoft 365 y al centro de cumplimiento de & seguridad anterior. Por ejemplo, si agrega un usuario al administrador de seguridad en el  portal de Microsoft 365 Defender, solo tienen acceso de administrador de seguridad en el Portal de Microsoft 365 Defender, el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad & cumplimiento.
- Muchas características del portal de Microsoft 365 Defender se basan en cmdlets de PowerShell de Exchange Online y, por lo tanto, requieren la pertenencia a grupos de roles en los roles correspondientes (técnicamente, grupos de roles) en Exchange Online (en particular, para obtener acceso Exchange Online Cmdlets de PowerShell).
- Hay roles de colaboración de correo electrónico & en el portal de Microsoft 365 Defender que no tienen equivalente Azure AD roles y son importantes para las operaciones de seguridad (por ejemplo, el rol Vista previa y el rol Buscar y purgar).

Normalmente, solo un subconjunto de personal de seguridad necesitará derechos adicionales para descargar mensajes directamente desde los buzones de usuario. Esto requiere un permiso adicional que el Lector de seguridad no tiene de forma predeterminada.

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>Paso 2: (opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente

Aunque este paso no es necesario, debe considerar la posibilidad de configurar los usuarios piloto para omitir el filtrado por parte del servicio de protección existente. Esta acción permite a Defender Office 365 **controlar** todas las tareas de filtrado y protección para los usuarios piloto. Si no exime a los usuarios piloto del servicio de protección existente, Defender for Office 365 funciona de forma eficaz solo en las pérdidas del otro servicio (filtrando mensajes que ya se han filtrado).

> [!NOTE]
> Este paso es explícitamente necesario si el servicio de protección actual proporciona ajuste de vínculos, pero desea realizar pruebas piloto Caja fuerte vínculos. No se admite el ajuste doble de vínculos.

## <a name="step-3-tune-spoof-intelligence"></a>Paso 3: Ajustar la inteligencia de suplantación

Compruebe la [información](learn-about-spoof-intelligence.md) de inteligencia de suplantación para ver lo que se permite o se bloquea como suplantación de dominio y para determinar si necesita invalidar el veredicto del sistema por suplantación. Algunos orígenes de su correo electrónico crítico para la empresa pueden haber configurado incorrectamente registros de autenticación de correo electrónico en DNS (SPF, DKIM y DMARC) y puede que esté usando invalidaciones en el servicio de protección existente para enmascarar sus problemas de dominio.

La inteligencia suplantada puede rescatar el correo electrónico de dominios sin registros de autenticación de correo electrónico adecuados en DNS, pero la característica a veces necesita ayuda para distinguir la suplantación de buena de la suplantación mala. Céntrate en los siguientes tipos de orígenes de mensajes:

- Orígenes de mensajes que están fuera de los intervalos de direcciones IP definidos en [Filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Orígenes de mensajes que tienen el mayor número de mensajes.
- Orígenes de mensajes que tienen el mayor impacto en la organización.

La inteligencia de suplantación se ajustará después de configurar los envíos de los usuarios, por lo que no es necesario que se perfeccione.

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>Paso 4: Ajustar la protección de suplantación y la inteligencia de buzones

Después de tener suficiente tiempo para observar los resultados de la protección contra suplantación en **No** aplicar ningún modo de acción, puede activar individualmente cada acción de protección de suplantación en las directivas contra suplantación:

- Protección de suplantación de usuario: **ponga en cuarentena el mensaje** para Standard y Strict.
- Protección de suplantación de dominio: **ponga en cuarentena el mensaje** para Standard y Strict.
- Protección de inteligencia de buzones de correo: mover el mensaje a las **carpetas de correo no** deseado de los destinatarios para Standard; **Poner en cuarentena el mensaje** para Strict.

Cuanto más tiempo monitoree los resultados de la protección de suplantación sin actuar en los mensajes, más datos tendrá que identificar los bloqueos o los posibles bloqueos necesarios. Considere la posibilidad de usar un retraso entre activar cada protección que sea lo suficientemente importante como para permitir la observación y el ajuste.

> [!NOTE]
> Es importante la supervisión y el ajuste continuos y frecuentes de estas protecciones. Si sospecha que hay un falso positivo, investigue la causa y use invalidaciones solo según sea necesario y solo para la característica de detección que lo requiera.

### <a name="tune-mailbox-intelligence"></a>Ajustar la inteligencia de buzones

Aunque la inteligencia de buzones de correo [](impersonation-insight.md)se ha configurado para no realizar ninguna acción en los mensajes que se determinaron como intentos de suplantación, ha estado en y aprendiendo los patrones de envío y recepción de correo electrónico de los usuarios piloto. Si un usuario externo está en contacto con uno de los usuarios piloto, los mensajes de ese usuario externo no se identificarán como intentos de suplantación por parte de la inteligencia de buzones (lo que reduce los falsos positivos).

Cuando esté listo, siga estos pasos para permitir que la inteligencia de buzones actúe en los mensajes detectados como intentos de suplantación:

- En la directiva contra suplantación de identidad con la configuración de protección estándar, cambie el valor de If **mailbox intelligence detects an suersonated user** to Move message to **recipients' Junk Email folders**.

- En la directiva contra suplantación de identidad con la configuración de protección estricta, cambie el valor de **If mailbox intelligence detects and suersonated user** from to Quarantine the **message**.

Para modificar las directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

Después de haber observado los resultados y realizado los ajustes, vaya a la siguiente sección para poner en cuarentena los mensajes detectados por la suplantación de usuario.

### <a name="tune-user-impersonation-protection"></a>Ajustar la protección de suplantación de usuario

En ambas directivas contra la suplantación de identidad basadas en la configuración estándar y estricta, cambie el valor de **If message is detected as an suersonated user to** Quarantine the **message**.

Compruebe la [información de suplantación](impersonation-insight.md) para ver lo que se está bloqueando como intentos de suplantación de usuario.

Para modificar las directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

Después de haber observado los resultados y realizado los ajustes, vaya a la siguiente sección para poner en cuarentena los mensajes detectados por suplantación de dominio.

### <a name="tune-domain-impersonation-protection"></a>Ajustar la protección de suplantación de dominio

En ambas directivas contra suplantación de identidad basadas en la configuración estándar y estricta, cambie el valor de **If message is detected as an suersonated domain** a Quarantine the **message**.

Compruebe la [información de suplantación](impersonation-insight.md) para ver lo que se está bloqueando como intentos de suplantación de dominio.

Para modificar las directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

Observe los resultados y realice los ajustes necesarios.

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>Paso 5: Usar datos de envíos de usuarios para medir y ajustar

A medida que los usuarios piloto informen de falsos positivos y falsos negativos, los mensajes aparecerán en la página Envíos del [portal de Microsoft 365 Defender.](admin-submission.md) Puede notificar los mensajes mal identificados a Microsoft para su análisis y usar la información para ajustar la configuración y las excepciones en las policías piloto según sea necesario.

Use las siguientes características para supervisar e iterar la configuración de protección en Defender para Office 365:

- [Cuarentena](manage-quarantined-messages-and-files.md)
- [Explorador de amenazas](email-security-in-microsoft-defender.md)
- [Informes de seguridad de correo electrónico](view-email-security-reports.md)
- [Defender para Office 365 informes](view-reports-for-mdo.md)
- [Información sobre el flujo de correo](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [Informes de flujo de correo](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

Si su organización usa un servicio de terceros para los informes de usuario, puede integrar los datos en el bucle de comentarios.

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>Paso 6: (opcional) Agregar más usuarios al piloto e iterar

A medida que encuentre y solucione problemas, puede agregar más usuarios a los grupos piloto (y, en consecuencia, eximir a los nuevos usuarios piloto del examen por el servicio de protección existente según corresponda). Entre más pruebas realice ahora, menos problemas de usuario tendrá que tratar más adelante. Este enfoque de "cascada" permite ajustar con partes más grandes de la organización y da a los equipos de seguridad tiempo para ajustarse a las nuevas herramientas y procesos.

- Microsoft 365 genera alertas cuando las directivas de la organización permiten mensajes de suplantación de identidad de elevada confianza. Para identificar estos mensajes, tiene las siguientes opciones:
  - Invalidaciones en el informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
  - Filtra en el Explorador de amenazas para identificar los mensajes.
  - Filtra en Búsqueda avanzada para identificar los mensajes.

  Notificar cualquier falso positivo a Microsoft lo antes posible a través de envíos de administrador, use la característica [Permitir espacio empresarial/Lista](tenant-allow-block-list.md) de bloqueo para configurar invalidaciones seguras para esos falsos positivos.

- También es buena idea examinar invalidaciones innecesarias. En otras palabras, mira los veredictos que Microsoft 365 hubiera proporcionado en los mensajes. Si Microsoft365 representó el veredicto correcto, la necesidad de invalidación se reduce o elimina en gran parte.

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>Paso 7: Ampliar la Microsoft 365 a todos los usuarios y desactivar la regla de flujo de correo SCL=-1

Siga los pasos de esta sección cuando esté listo para cambiar los registros MX para que apunten a Microsoft 365.

1. Extender las directivas piloto a toda la organización. Fundamentalmente, hay diferentes maneras de hacerlo:
   - Usa [directivas de seguridad](preset-security-policies.md) preestablecidas y divide a los usuarios entre el perfil de protección estándar y el perfil de protección estricta (asegúrate de que todos están cubiertos). Las directivas de seguridad preestablecidas se aplican antes de las directivas personalizadas que haya creado o de las directivas predeterminadas. Puede desactivar las directivas piloto individuales sin eliminarlas.

     El inconveniente de las directivas de seguridad preestablecidas es que no puede cambiar muchas de las configuraciones importantes después de crearlas.

   - Cambie el ámbito de las directivas que creó y ajustó durante el piloto para incluir a todos los usuarios (por ejemplo, todos los destinatarios de todos los dominios). Recuerde que si varias directivas del mismo tipo (por ejemplo, directivas contra suplantación de identidad) se aplican al mismo usuario (individualmente, por pertenencia a grupos o dominio de correo electrónico), solo se aplica la configuración de la directiva con la prioridad más alta (número de prioridad más baja) y el procesamiento se detiene para ese tipo de directiva.

2. Desactive la regla de flujo de correo SCL=-1 (puede desactivarla sin eliminarla).

3. Compruebe que los cambios anteriores han tenido efecto y que Defender para Office 365 está habilitado correctamente para todos los usuarios. En este momento, todas las características de protección de Defender para Office 365 ahora pueden actuar en correo para todos los destinatarios, pero ese correo ya ha sido examinado por el servicio de protección existente.

Puede pausar en esta fase para obtener más optimización y registro de datos a gran escala.

## <a name="step-8-switch-your-mx-records"></a>Paso 8: Cambiar los registros MX

> [!NOTE]
>
> - Al cambiar el registro MX del dominio, los cambios pueden tardar hasta 48 horas en propagarse por Internet.
>
> - Se recomienda reducir el valor TTL de los registros DNS para permitir una respuesta más rápida y una posible reversión (si es necesario). Puede volver al valor TTL original una vez completado y comprobado el cambio.
>
> - Debe considerar empezar por cambiar los dominios que se usan con menos frecuencia. Puede pausar y supervisar antes de pasar a dominios más grandes. Sin embargo, incluso si lo hace, debe asegurarse de que todos los usuarios y dominios están cubiertos por directivas, ya que los dominios SMTP secundarios se resuelven en dominios principales antes de la aplicación de directiva.
>   
> - Varios registros MX para un único dominio funcionarán técnicamente, lo que le permitirá tener enrutamiento dividido, siempre que haya seguido todas las instrucciones de este artículo. En concreto, debe asegurarse de que las directivas se aplican a todos los usuarios, que la regla de flujo de correo SCL=-1 se aplica solo al correo que pasa a través del servicio de protección existente, tal como se describe en Setup [Step 3: Maintain or create the SCL=-1 mail flow rule](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule). Sin embargo, esta configuración introduce un comportamiento que hace que la solución de problemas sea mucho más difícil y, por lo tanto, no lo recomendamos normalmente, especialmente durante períodos prolongados de tiempo.
>
> - Antes de cambiar los registros MX, compruebe que la siguiente configuración no está habilitada en el conector entrante desde el servicio de protección a Microsoft 365. Normalmente, el conector tendrá una o varias de las siguientes opciones configuradas:
>
>   - **y requerir que el nombre de sujeto en** el certificado que el asociado usa para autenticarse con Office 365 coincide con este nombre de dominio (*RestrictDomainsToCertificate*)
>   - **Rechazar mensajes de correo electrónico si no se envían desde este intervalo de direcciones IP** (*RestrictDomainsToIPAddresses*)
>
>   Si el tipo de conector es **Partner** y cualquiera de estas opciones de configuración está activada, se producirá un error en toda la entrega de correo a los dominios después de cambiar los registros MX. Debe deshabilitar esta configuración antes de continuar. Si el conector es un conector local que se usa para híbrido, no es necesario modificar el conector local. Sin embargo, aún puede comprobar la presencia de un **conector de** partner.
>   
> - Si la puerta de enlace de correo actual también proporciona validación de destinatarios, es posible que desee comprobar que el dominio está configurado como [Autoritativo](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en Microsoft 365. Esto puede evitar mensajes de rebote innecesarios.

Cuando esté listo, cambie el registro MX de los dominios. Puede migrar todos los dominios a la vez. O bien, puede migrar primero los dominios usados con menos frecuencia y, a continuación, migrar el resto más adelante.

No dude en pausar y evaluar aquí en cualquier momento. Pero, recuerde: una vez desactivada la regla de flujo de correo SCL=-1, es posible que los usuarios tengan dos experiencias diferentes para comprobar falsos positivos. Cuanto antes pueda proporcionar una experiencia única y coherente, más felices estarán los usuarios y los equipos de asistencia cuando tengan que solucionar un mensaje que falta.

## <a name="next-steps"></a>Siguientes pasos

¡Enhorabuena! Ha completado la migración [a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)! Dado que ha seguido los pasos de esta guía de migración, los primeros días en los que el correo se entrega directamente en Microsoft 365 debe ser mucho más suave.

Ahora comienza el funcionamiento normal y el mantenimiento de Defender para Office 365. Supervise y observe problemas similares a los que experimentó durante el piloto, pero a mayor escala. La [información de inteligencia](learn-about-spoof-intelligence.md) [](impersonation-insight.md) suplantación y la información de suplantación serán más útiles, pero considere la posibilidad de convertir las siguientes actividades en una repetición regular:

- Revise los envíos de usuarios, especialmente los mensajes de [suplantación de identidad notificados por el usuario.](/microsoft-365/security/office-365-security/automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- Revisar invalidaciones en el informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- Usa [consultas de](/microsoft-365/security/defender/advanced-hunting-example) búsqueda avanzada para buscar oportunidades de ajuste y mensajes arriesgados.
