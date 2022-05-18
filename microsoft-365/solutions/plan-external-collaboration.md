---
title: Planear la colaboración externa con conversaciones de canal, colaboración de archivos y aplicaciones compartidas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre la diferencia entre la colaboración de invitados y los canales compartidos en Teams y cómo elegir cuál usar.
ms.openlocfilehash: 09948b49d0c4f3e21d03c1e3994e4dd2d609ed13
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465787"
---
# <a name="plan-external-collaboration-with-channel-conversations-file-collaboration-and-shared-apps"></a>Planear la colaboración externa con conversaciones de canal, colaboración de archivos y aplicaciones compartidas

Microsoft 365 ofrece varias opciones para colaborar con personas ajenas a la organización:

- 1:1 y chat grupal en Teams con personas ajenas a la organización
- Teams reuniones con personas ajenas a la organización
- Uso compartido de archivos o carpetas individuales con personas ajenas a la organización
- Colaboración en un equipo, con conversaciones de canal, colaboración de archivos y aplicaciones compartidas

En este artículo se describe la cuarta opción, la colaboración en grupos con conversaciones de canal, la colaboración de archivos y las aplicaciones compartidas. (Para obtener información general sobre todas las opciones, consulte [Información general sobre las opciones de colaboración externa en Microsoft 365](/microsoft-365/enterprise/external-guest-access)).

## <a name="terms"></a>Términos

- **Colaboración B2B de Azure AD** : una característica que permite a los usuarios compartir archivos, carpetas, sitios, grupos y equipos con personas de fuera de la organización. Estos usuarios tienen acceso a recursos compartidos mediante cuentas de invitado en el directorio.
- **Conexión directa B2B de Azure AD** : una característica que permite a los usuarios compartir recursos de su organización con personas de otras organizaciones de Azure AD. Estas personas acceden a los recursos compartidos mediante su propia cuenta profesional o educativa. No se crea ninguna cuenta de invitado en la organización.
- **Participante externo** : una persona de fuera de la organización que participa en un recurso(por ejemplo, un canal compartido) que usa su propia identidad y no una cuenta de invitado en el directorio.
- **Organización externa** : otra organización con la que comparte recursos.
- **Invitado** : una persona de fuera de la organización que accede a recursos compartidos iniciando sesión en una cuenta de invitado en el directorio.
- **Organización host** : la organización que hospeda un recurso compartido, como un canal compartido.
- **Canal compartido**: un canal Teams que se puede compartir con personas ajenas al equipo. Estas personas pueden estar dentro de su organización o de otras organizaciones de Azure AD.
- **Compartir vínculos** : vínculos con permisos a un archivo o carpeta que se usan para compartir ese archivo o carpeta con otros usuarios. Las personas con las que se comparten pueden estar dentro o fuera de su organización.

## <a name="options-for-collaboration-in-a-team"></a>Opciones para la colaboración en un equipo

Al colaborar en un equipo con personas ajenas a su organización, hay dos opciones para cómo esas personas acceden a los recursos que comparte con ellos.

### <a name="guest-sharing"></a>Uso compartido de invitados

El uso compartido de invitados usa la colaboración B2B de Azure AD para permitir el uso compartido y la colaboración con personas ajenas a la organización mediante la adición de una cuenta de invitado en Azure AD para cada persona. Las cuentas de invitado se pueden usar para lo siguiente:

- Pertenencia de invitado a equipos, sitios de SharePoint y grupos de Microsoft 365
- Uso compartido de archivos y carpetas individuales

Los invitados de un equipo tienen funcionalidades similares a las de los miembros normales del equipo.

### <a name="external-participants-in-shared-channels"></a>Participantes externos en canales compartidos

Los participantes externos acceden a los recursos compartidos de su organización mediante su propia identidad de Azure AD o Microsoft 365. Esto se habilita mediante la conexión directa de Azure AD B2B a través de una relación organizativa configurada por ambas organizaciones. Las cuentas de invitado no se usan en esta relación.

La principal ventaja de los participantes externos en los canales compartidos frente al uso compartido de invitados es que las personas de fuera de su organización pueden colaborar con los usuarios en Teams sin tener que cambiar su contexto de usuario. Al usar cuentas de invitado, los usuarios deben cerrar la sesión de Teams con su cuenta profesional o educativa e iniciar sesión de nuevo con la cuenta de invitado. Como alternativa, pueden tener una copia independiente de Teams en ejecución en una sesión del explorador privado. Este cambio entre organizaciones tarda tiempo y puede hacer que los usuarios pierdan comunicaciones importantes mientras cierran sesión en una organización determinada.

Con los canales compartidos, los usuarios pueden permanecer conectados a su organización y acceder a los canales compartidos con ellos desde otras organizaciones. Los canales compartidos de otras organizaciones están disponibles en Teams junto con los equipos y canales de la organización. No es necesario cambiar de organización.

## <a name="feature-comparison"></a>Comparación de características

En la tabla siguiente se describen las experiencias disponibles en función del tipo de cuenta utilizada.

|Característica|Usuario (su organización)|Invitado (colaboración de Azure AD)|Participante externo (Conexión directa de Azure AD)|
|:-----|:-----|:------|:-------|
|Acceso al equipo|v|v|N|
|Acceso a canales compartidos|v|N|v|
|Permisos a través de vínculos de uso compartido de archivos|v|v|N|
|Uso de canales compartidos|v|N|v|
|Uso de canales privados|v|v|N|
|Cuenta en el directorio|v|v|N|
|Revisiones de acceso|v|v|v|

## <a name="planning-considerations"></a>Consideraciones de planeación

La mayoría de las organizaciones usarán tanto el uso compartido de invitados como los canales compartidos con participantes externos.

El uso compartido de invitados está habilitado de forma predeterminada en Azure AD y en Microsoft 365 (Teams, Grupos de Microsoft 365 y SharePoint). Esto permite a los usuarios invitar a los invitados a equipos y sitios y compartir archivos con ellos sin tener que solicitar asistencia de TI.

Debe usar el uso compartido de invitados si:

- Quiere invitar a personas de fuera de la organización al equipo en lugar de canales individuales
- Quiere compartir archivos o carpetas en un canal con personas ajenas a la organización que no están en el canal.
- Quiere colaborar con personas ajenas a su organización que no tengan una cuenta profesional o educativa.

Aunque los canales compartidos están activados de forma predeterminada en Teams, la colaboración externa con canales compartidos requiere que un administrador de Azure AD configure el acceso entre inquilinos entre la organización y la otra organización con la que desea compartir. Cada otra organización también debe configurar el acceso entre inquilinos en su extremo.

Si tiene previsto usar canales compartidos con otras organizaciones, puede elegir entre un modelo de autoservicio y un modelo por solicitud.

- Autoservicio: puede configurar el acceso entre inquilinos para permitir el acceso entrante y saliente a todas las demás organizaciones de Azure AD. Como alternativa, puede bloquear una lista de organizaciones con las que no quiere que los usuarios compartan, dejando todas las demás organizaciones disponibles. Esto permite a los usuarios invitar a personas ajenas a la organización a participar en canales compartidos sin tener que ponerse en contacto con su departamento de soporte técnico o departamento de TI.
- Por solicitud: puede configurar el acceso entre inquilinos para cada organización individual con la que desea permitir canales compartidos. Al elegir este modelo, es importante tener un proceso empresarial documentado que los usuarios puedan seguir para solicitar acceso entre inquilinos con otra organización.

## <a name="compliance-in-shared-channels"></a>Cumplimiento en canales compartidos

Los canales compartidos se integran con características Microsoft Purview.

### <a name="communications-compliance"></a>Cumplimiento de comunicaciones

Los administradores pueden establecer directivas para supervisar el contenido de todos los usuarios del canal. Todo el contenido de los mensajes de los canales, incluidos los canales compartidos, está cubierto por [las directivas de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance). Los canales compartidos heredan la directiva de la organización host.

### <a name="conditional-access"></a>Acceso condicional

Las [directivas de acceso condicional](/azure/active-directory/conditional-access/overview) admitidas de la organización host se pueden aplicar a los usuarios de conexión directa B2B. (No se usan las directivas de la organización externa). Los siguientes tipos de directivas de acceso condicional se admiten con canales compartidos:

- Directivas que tienen como ámbito **Todos los usuarios invitados y externos**, y la **aplicación en la nube Office 365 SharePoint Online**.
- Conceda controles de acceso que requieran MFA, un dispositivo compatible o un dispositivo unido a Azure AD híbrido.

Las directivas basadas en IP se admiten en el nivel de archivo SharePoint. Por lo tanto, un participante externo podría acceder al canal compartido desde una ubicación restringida, pero bloquearse al intentar abrir un archivo.

Para obtener más información sobre el acceso condicional para identidades externas, consulte [Autenticación y acceso condicional para identidades externas](/azure/active-directory/external-identities/authentication-conditional-access).

### <a name="data-loss-prevention-dlp"></a>Prevención de pérdida de datos (DLP)

Los administradores pueden aplicar [Microsoft Purview directivas DLP](/microsoft-365/compliance/dlp-policy-design) a un equipo donde todos los canales, incluidos los canales compartidos, heredan la directiva. Los canales compartidos heredan la directiva de la organización host.

### <a name="retention-policy"></a>Directiva de retención

Los administradores pueden aplicar una [directiva de retención](/microsoft-365/compliance/retention) en un equipo donde todos los canales, incluidos los canales compartidos, heredan la directiva de retención. Los canales compartidos heredan la directiva del equipo primario.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

[Las etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels) disponibles en la organización host son las únicas etiquetas que se pueden aplicar a los documentos de un sitio de canal compartido. Los participantes externos no pueden abrir un archivo cifrado mediante una etiqueta de confidencialidad. No se usa el etiquetado automático.

Los canales compartidos y sus sitios de SharePoint asociados heredan la etiqueta del equipo primario.

### <a name="information-barriers"></a>Barreras de información

Los usuarios que no pueden comunicarse por [directivas de barrera de información](/microsoftteams/information-barriers-in-teams) no pueden formar parte del canal compartido. Las directivas de barrera de información solo son eficaces para los usuarios de la organización host. Si los usuarios son participantes externos en el canal compartido de otra organización, no se aplican directivas de barrera de información.

### <a name="ediscovery"></a>eDiscovery

Los administradores pueden realizar búsquedas de todos los usuarios del canal. Todos los canales, incluido el canal compartido, se pueden detectar. El administrador de cumplimiento puede detectar todos los datos de mensaje del canal independientemente de quién haya agregado los datos.

### <a name="legal-hold"></a>Suspensión legal

Los administradores pueden poner en espera a los miembros de solo canal de la organización host que no formen parte del equipo. También pueden [poner a todo el equipo en espera](/MicrosoftTeams/legal-hold). Los administradores no pueden poner a un participante externo en espera.

### <a name="audit-logs"></a>Registros de auditoría

Todas las acciones realizadas para [los eventos de auditoría existentes](/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) se auditan en canales compartidos.

## <a name="related-topics"></a>Temas relacionados

[Introducción a la colaboración de archivos en Microsoft 365](/sharepoint/intro-to-file-collaboration)

[Planear la colaboración de archivos en SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)
