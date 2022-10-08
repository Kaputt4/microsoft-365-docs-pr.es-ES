---
title: 'Migración a Microsoft Defender para Office 365 Fase 3: Incorporación'
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
- m365-security
- m365solution-mdo-migration
- highpri
ms.custom: migrationguides
description: Complete los pasos para migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ce2f5011de4cce53a5ca4a03228e9563da59d996
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68079983"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>Migración a Microsoft Defender para Office 365: Fase 3: Incorporación

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|[![Fase 1: Preparación.](../../media/phase-diagrams/prepare.png#lightbox)](migrate-to-defender-for-office-365-prepare.md) <br> [Fase 1: Preparación](migrate-to-defender-for-office-365-prepare.md)|[![Fase 2: Configurar.](../../media/phase-diagrams/setup.png#lightbox)](migrate-to-defender-for-office-365-setup.md) <br> [Fase 2: Configuración](migrate-to-defender-for-office-365-setup.md)|![Fase 3: Incorporación.](../../media/phase-diagrams/onboard.png) <br> Fase 3: Incorporación|
|---|---|---|
|||*¡Estás aquí!*|

Bienvenido a **Fase 3: Incorporación** de la **[migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los pasos siguientes:

1. [Inicio de la incorporación de Security Teams](#step-1-begin-onboarding-security-teams)
2. [(Opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [Optimizar la inteligencia de suplantación de identidad](#step-3-tune-spoof-intelligence)
4. [Optimización de la protección de suplantación y la inteligencia de buzones](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [Uso de datos de envíos de usuarios para medir y ajustar](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [(Opcional) Agregar más usuarios al piloto e iterar](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [Ampliar la protección de Microsoft 365 a todos los usuarios y desactivar la regla de flujo de correo SCL=-1](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [Cambiar los registros MX](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>Paso 1: Inicio de la incorporación de Security Teams

Si su organización tiene un equipo de respuesta de seguridad, ahora es el momento de empezar a integrar Microsoft Defender para Office 365 en los procesos de respuesta, incluidos los sistemas de vales. Este es un tema entero para sí mismo, pero a veces se pasa por alto. Al hacer que el equipo de respuesta de seguridad participe al principio, se asegurará de que su organización esté lista para hacer frente a las amenazas cuando cambie los registros MX. La respuesta a incidentes debe estar bien equipada para controlar las tareas siguientes:

- Obtenga información sobre las nuevas herramientas e intégrelas en flujos existentes. Por ejemplo:
  - Administración es importante administrar los mensajes en cuarentena. Para obtener instrucciones, consulte [Administración de mensajes y archivos en cuarentena como administrador](manage-quarantined-messages-and-files.md).
  - El seguimiento de mensajes le permite ver qué pasó con los mensajes a medida que entran o salen de Microsoft 365. Para obtener más información, vea [Seguimiento de mensajes en el centro de administración moderno de Exchange en Exchange Online](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).
- Identificar los riesgos que se pueden haber dejado entrar en la organización.
- Ajuste y personalización de [alertas](../../compliance/alert-policies.md) para los procesos de la organización.
- Administre la cola de incidentes y corrija los posibles riesgos.

Si su organización ha adquirido Microsoft Defender para Office 365 plan 2, debería empezar a familiarizarse con características como Explorador de amenazas, Búsqueda avanzada e Incidentes. Para obtener los entrenamientos pertinentes, vea <https://aka.ms/mdoninja>.

Si el equipo de respuesta de seguridad recopila y analiza mensajes sin filtrar, puede configurar un buzón de SecOps para recibir estos mensajes sin filtrar. Para obtener instrucciones, consulte [Configuración de buzones de SecOps en la directiva de entrega avanzada](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).

### <a name="siemsoar"></a>SIEM/SOAR

Para obtener más información sobre la integración con SIEM/SOAR, consulte los artículos siguientes:

- [Información general sobre las API de Microsoft 365 Defender](/microsoft-365/security/defender/api-overview)
- [API de streaming](/microsoft-365/security/defender/streaming-api)
- [API de Búsqueda avanzada de amenazas](/microsoft-365/security/defender/api-advanced-hunting)
- [API de incidentes](/microsoft-365/security/defender/api-incident)

Si su organización no tiene un equipo de respuesta de seguridad o flujos de proceso existentes, puede usar este tiempo para familiarizarse con las características básicas de búsqueda y respuesta en Defender para Office 365. Para obtener más información, consulte [Investigación y respuesta de amenazas](office-365-ti.md).

### <a name="rbac-roles"></a>Roles de RBAC

Los permisos de Defender para Office 365 se basan en el control de acceso basado en rol (RBAC) y se explican en Permisos en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md). Estos son los puntos importantes a tener en cuenta:

- Los roles de Azure AD conceden permisos a **todas las** cargas de trabajo de Microsoft 365. Por ejemplo, si agrega un usuario al administrador de seguridad en el Azure Portal, tiene permisos de administrador de seguridad en todas partes.
- Email & roles de colaboración en el portal de Microsoft 365 Defender conceden permisos al portal de Microsoft 365 Defender, al portal de cumplimiento Microsoft Purview y al Centro de cumplimiento de seguridad & anterior. Por ejemplo, si agrega un usuario al administrador de seguridad en el portal de Microsoft 365 Defender, **solo** tiene acceso de administrador de seguridad en el portal de Microsoft 365 Defender, el portal de cumplimiento Microsoft Purview y el cumplimiento de seguridad & Centro.
- Muchas características del portal de Microsoft 365 Defender se basan en Exchange Online cmdlets de PowerShell y, por tanto, requieren la pertenencia a grupos de roles en los roles correspondientes (técnicamente, grupos de roles) en Exchange Online (en particular, para acceder a los Exchange Online correspondientes).  Cmdlets de PowerShell).
- Hay Email & roles de colaboración en el portal de Microsoft 365 Defender que no tienen ningún equivalente a los roles de Azure AD y son importantes para las operaciones de seguridad (por ejemplo, el rol Vista previa y el rol Buscar y purgar).

Normalmente, solo un subconjunto de personal de seguridad necesitará derechos adicionales para descargar mensajes directamente desde buzones de usuario. Esto requiere un permiso adicional que el Lector de seguridad no tiene de forma predeterminada.

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>Paso 2: (Opcional) Excluir a los usuarios piloto del filtrado por el servicio de protección existente

Aunque este paso no es necesario, debe considerar la posibilidad de configurar los usuarios piloto para omitir el filtrado por el servicio de protección existente. Esta acción permite Defender para Office 365 controlar **todas las** tareas de filtrado y protección de los usuarios piloto. Si no exime a los usuarios piloto del servicio de protección existente, Defender para Office 365 funciona eficazmente solo en caso de errores del otro servicio (filtrado de mensajes que ya se han filtrado).

> [!NOTE]
> Este paso es necesario explícitamente si el servicio de protección actual proporciona ajuste de vínculos, pero quiere probar la funcionalidad vínculos seguros. No se admite el ajuste doble de vínculos.

## <a name="step-3-tune-spoof-intelligence"></a>Paso 3: Ajustar la inteligencia de suplantación de identidad

Compruebe la [información de inteligencia sobre suplantación](learn-about-spoof-intelligence.md) de identidad para ver lo que se permite o se bloquea como suplantación de identidad y para determinar si necesita invalidar el veredicto del sistema para la suplantación de identidad. Es posible que algunos orígenes del correo electrónico crítico para la empresa hayan configurado incorrectamente los registros de autenticación de correo electrónico en DNS (SPF, DKIM y DMARC) y que esté usando invalidaciones en el servicio de protección existente para enmascarar sus problemas de dominio.

La inteligencia sobre suplantación de identidad puede rescatar el correo electrónico de dominios sin registros de autenticación de correo electrónico adecuados en DNS, pero la característica a veces necesita ayuda para distinguir la buena suplantación de identidad de la suplantación de identidad incorrecta. Céntrese en los siguientes tipos de orígenes de mensajes:

- Orígenes de mensajes que están fuera de los intervalos de direcciones IP definidos en [Filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Orígenes de mensajes que tienen el mayor número de mensajes.
- Orígenes de mensajes que tienen el mayor impacto en la organización.

La inteligencia de suplantación de identidad finalmente se ajustará después de configurar los envíos de los usuarios, por lo que no hay necesidad de perfección.

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>Paso 4: Optimizar la protección de suplantación y la inteligencia de buzones

Después de haber tenido suficiente tiempo para observar los resultados de la protección contra suplantación en **No aplicar ningún** modo de acción, puede activar individualmente cada acción de protección contra suplantación en las directivas contra suplantación de identidad:

- Protección de suplantación de usuario: **ponga en cuarentena el mensaje** para Estándar y Estricto.
- Protección de suplantación de dominio: **ponga en cuarentena el mensaje** para Estándar y Estricto.
- Protección de inteligencia del buzón de correo: **mueva el mensaje a las carpetas de Email no deseado de los destinatarios** para Standard; **Ponga en cuarentena el mensaje** para Strict.

Cuanto más tiempo supervise los resultados de la protección de suplantación sin actuar en los mensajes, más datos tendrá que identificar los permisos o bloques que podrían ser necesarios. Considere la posibilidad de usar un retraso entre activar cada protección lo suficientemente importante como para permitir la observación y el ajuste.

> [!NOTE]
> La supervisión y el ajuste frecuentes y continuos de estas protecciones son importantes. Si sospecha que se trata de un falso positivo, investigue la causa y use invalidaciones solo según sea necesario y solo para la característica de detección que lo requiera.

### <a name="tune-mailbox-intelligence"></a>Optimización de la inteligencia de buzones

Aunque la inteligencia del buzón de correo se ha configurado para no realizar ninguna acción en los mensajes que se [determinaron como intentos de suplantación](impersonation-insight.md), ha estado en y aprendiendo los patrones de envío y recepción de correo electrónico de los usuarios piloto. Si un usuario externo está en contacto con uno de los usuarios piloto, los mensajes de ese usuario externo no se identificarán como intentos de suplantación por parte de la inteligencia del buzón de correo (lo que reduce los falsos positivos).

Cuando esté listo, siga estos pasos para permitir que la inteligencia del buzón actúe sobre los mensajes que se detectan como intentos de suplantación:

- En la directiva contra suplantación de identidad (phishing) con la configuración de protección estándar, cambie el valor de **If mailbox intelligence detects an impersonated user** to Move message to recipients'Junk Email folders (Si la inteligencia del buzón de correo detecta a un usuario suplantado) **para mover el mensaje a las carpetas de Email no deseado de los destinatarios**.

- En la directiva contra suplantación de identidad (phishing) con la configuración de protección estricta, cambie el valor de **If mailbox intelligence detects and impersonated user (Si la inteligencia del buzón detecta y suplanta al usuario** ) de a **Poner en cuarentena el mensaje**.

Para modificar las directivas, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

Una vez que haya observado los resultados y realizado ajustes, vaya a la sección siguiente para poner en cuarentena los mensajes detectados por la suplantación de usuario.

### <a name="tune-user-impersonation-protection"></a>Optimización de la protección de suplantación de usuario

En ambas directivas de anti-phishing basadas en la configuración Estándar y Estricta, cambie el valor de **Si se detecta el mensaje como un usuario suplantado** para **poner en cuarentena el mensaje**.

Compruebe la [información de suplantación](impersonation-insight.md) para ver lo que se está bloqueando cuando se intenta suplantar al usuario.

Para modificar las directivas, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

Después de observar los resultados y realizar ajustes, vaya a la sección siguiente para poner en cuarentena los mensajes detectados por la suplantación de dominio.

### <a name="tune-domain-impersonation-protection"></a>Optimización de la protección de suplantación de dominio

En ambas directivas de anti-phishing basadas en la configuración estándar y estricta, cambie el valor de **Si se detecta el mensaje como un dominio suplantado** a **Poner en cuarentena el mensaje**.

Compruebe la [información de suplantación](impersonation-insight.md) para ver lo que se bloquea como intentos de suplantación de dominio.

Para modificar las directivas, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

Observe los resultados y realice los ajustes necesarios.

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>Paso 5: Uso de datos de envíos de usuarios para medir y ajustar

A medida que los usuarios piloto notifiquen falsos positivos y falsos negativos, los mensajes aparecerán en la [página Envíos del portal de Microsoft 365 Defender](admin-submission.md). Puede informar de los mensajes identificados erróneamente a Microsoft para su análisis y usar la información para ajustar la configuración y las excepciones en las directivas piloto según sea necesario.

Use las siguientes características para supervisar y recorrer en iteración la configuración de protección en Defender para Office 365:

- [Cuarentena](manage-quarantined-messages-and-files.md)
- [Explorador de amenazas](email-security-in-microsoft-defender.md)
- [Email informes de seguridad](view-email-security-reports.md)
- [Informes de Defender para Office 365](view-reports-for-mdo.md)
- [Conclusiones de flujo de correo](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [Informes de flujo de correo](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

Si su organización usa un servicio de terceros para informes de usuarios, puede integrar esos datos en el bucle de comentarios.

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>Paso 6: (Opcional) Agregar más usuarios al piloto e iterar

A medida que encuentre y corrija los problemas, puede agregar más usuarios a los grupos piloto (y excluir correspondientemente a esos nuevos usuarios piloto del examen por el servicio de protección existente según corresponda). Cuantos más pruebas realice ahora, menos problemas de usuario tendrá que tratar más adelante. Este enfoque de "cascada" permite ajustarse a partes más grandes de la organización y proporciona a los equipos de seguridad tiempo para ajustarse a las nuevas herramientas y procesos.

- Microsoft 365 genera alertas cuando las directivas de la organización permiten mensajes de suplantación de identidad de alta confianza. Para identificar estos mensajes, tiene las siguientes opciones:
  - Invalida en el [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
  - Filtre en el Explorador de amenazas para identificar los mensajes.
  - Filtre en Búsqueda avanzada para identificar los mensajes.

  Informe de los falsos positivos a Microsoft lo antes posible a través de envíos de administrador, use la característica [Permitir o bloquear lista](manage-tenant-allow-block-list.md) de inquilinos para configurar invalidaciones seguras para esos falsos positivos.

- También es una buena idea examinar invalidaciones innecesarias. En otras palabras, examine los veredictos que Microsoft 365 habría proporcionado en los mensajes. Si Microsoft365 representó el veredicto correcto, la necesidad de invalidación se reduce o elimina en gran medida.

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>Paso 7: Extender la protección de Microsoft 365 a todos los usuarios y desactivar la regla de flujo de correo SCL=-1

Siga los pasos de esta sección cuando esté listo para cambiar los registros MX para que apunten a Microsoft 365.

1. Extienda las directivas piloto a toda la organización. Fundamentalmente, hay diferentes maneras de hacerlo:
   - Use directivas de [seguridad preestablecidas](preset-security-policies.md) y divida los usuarios entre el perfil de protección estándar y el perfil de protección estricta (asegúrese de que todos están cubiertos). Las directivas de seguridad preestablecidas se aplican antes que las directivas personalizadas que haya creado o las directivas predeterminadas. Puede desactivar las directivas piloto individuales sin eliminarlas.

     El inconveniente de las directivas de seguridad preestablecidas es que no se pueden cambiar muchas de las configuraciones importantes después de crearlas.

   - Cambie el ámbito de las directivas que creó y ajustó durante el piloto para incluir a todos los usuarios (por ejemplo, todos los destinatarios de todos los dominios). Recuerde que si se aplican varias directivas del mismo tipo (por ejemplo, directivas anti phishing) al mismo usuario (individualmente, por pertenencia a grupos o dominio de correo electrónico), solo se aplica la configuración de la directiva con la prioridad más alta (número de prioridad más baja) y el procesamiento se detiene para ese tipo de directiva.

2. Desactive la regla de flujo de correo SCL=-1 (puede desactivarla sin eliminarla).

3. Compruebe que los cambios anteriores han surtido efecto y que Defender para Office 365 ahora está habilitado correctamente para todos los usuarios. En este momento, todas las características de protección de Defender para Office 365 ahora pueden actuar por correo para todos los destinatarios, pero el servicio de protección existente ya ha digitalizado ese correo.

Puede pausar en esta fase para realizar una grabación y ajuste de datos más a gran escala.

## <a name="step-8-switch-your-mx-records"></a>Paso 8: Cambiar los registros MX

> [!NOTE]
>
> - Al cambiar el registro MX de su dominio, los cambios pueden tardar hasta 48 horas en propagarse a través de Internet.
> - Se recomienda reducir el valor de TTL de los registros DNS para permitir una respuesta más rápida y una posible reversión (si es necesario). Puede revertir al valor TTL original una vez completada y comprobada la conmutación.
> - Debe considerar la posibilidad de empezar con el cambio de dominios que se usan con menos frecuencia. Puede pausar y supervisar antes de pasar a dominios más grandes. Sin embargo, incluso si lo hace, debe asegurarse de que todos los usuarios y dominios están cubiertos por directivas, ya que los dominios SMTP secundarios se resuelven en dominios principales antes de la aplicación de directiva.
> - Técnicamente funcionarán varios registros MX para un solo dominio, lo que le permite tener enrutamiento dividido, siempre que haya seguido todas las instrucciones de este artículo. En concreto, debe asegurarse de que las directivas se aplican a todos los usuarios, de que la regla de flujo de correo SCL=-1 solo se aplica al correo que pasa a través del servicio de protección existente, tal como se describe en [El paso de instalación 3: Mantener o crear la regla de flujo de correo SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule). Sin embargo, esta configuración presenta un comportamiento que dificulta mucho más la solución de problemas y, por lo tanto, no se recomienda normalmente, especialmente durante períodos de tiempo prolongados.
> - Antes de cambiar los registros MX, compruebe que la siguiente configuración no está habilitada en el conector de entrada desde el servicio de protección a Microsoft 365. Normalmente, el conector tendrá una o varias de las siguientes opciones configuradas:
>   - **y requieren que el nombre del firmante en el certificado que el asociado usa para autenticarse con Office 365 coincida con este nombre de dominio** (*RestrictDomainsToCertificate*)
>   - **Rechace los mensajes de correo electrónico si no se envían desde dentro de este intervalo de direcciones IP** (*RestrictDomainsToIPAddresses*) Si el tipo de conector es **Asociado** y cualquiera de estas opciones está activada, se producirá un error en toda la entrega de correo a los dominios después de cambiar los registros MX. Debe deshabilitar esta configuración antes de continuar. Si el conector es un conector local que se usa para el híbrido, no es necesario modificar el conector local. Sin embargo, todavía puede comprobar la presencia de un conector de **asociado** .
> - Si la puerta de enlace de correo actual también proporciona validación de destinatarios, es posible que desee comprobar que el dominio está configurado como [Autoritativo](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en Microsoft 365. Esto puede evitar mensajes de rebote innecesarios.

Cuando esté listo, cambie el registro MX de los dominios. Puede migrar todos los dominios a la vez. O bien, puede migrar primero los dominios usados con menos frecuencia y, después, migrar el resto más adelante.

No dude en pausar y evaluar aquí en cualquier momento. Pero recuerde: una vez que desactive la regla de flujo de correo SCL=-1, los usuarios pueden tener dos experiencias diferentes para comprobar falsos positivos. Cuanto antes pueda proporcionar una experiencia única y coherente, más felices serán los usuarios y los equipos de soporte técnico cuando tengan que solucionar un mensaje que falta.

## <a name="next-steps"></a>Pasos siguientes

¡Enhorabuena! Ha completado [la migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process). Dado que ha seguido los pasos de esta guía de migración, los primeros días en los que el correo se entrega directamente en Microsoft 365 debe ser mucho más sencillo.

Ahora comienza el funcionamiento normal y el mantenimiento de Defender para Office 365. Supervise y observe los problemas que son similares a los que experimentó durante el piloto, pero a mayor escala. La [información de inteligencia de](learn-about-spoof-intelligence.md) [suplantación y la información de suplantación](impersonation-insight.md) serán más útiles, pero considere la posibilidad de hacer que las actividades siguientes se produzcan con regularidad:

- Revisar los envíos de usuarios, especialmente los [mensajes de suplantación de identidad notificados por el usuario](automated-investigation-response-office.md)
- Revise las invalidaciones en el [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- Use consultas [de búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-example) para buscar oportunidades de ajuste y mensajes de riesgo.
