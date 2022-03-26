---
title: Planear colaboración externa
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
description: Planee qué opciones de colaboración externa usar en Microsoft 365.
ms.openlocfilehash: 56999f3acda0da4f801f3a7ec171c73fe05943a3
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716112"
---
# <a name="plan-external-collaboration"></a>Planear colaboración externa

Microsoft 365 ofrece varias opciones para colaborar con personas fuera de la organización:

- 1:1 y chat en grupo en Teams con personas fuera de la organización
- Teams reuniones con personas fuera de la organización
- Compartir archivos o carpetas individuales con personas fuera de la organización
- Colaboración en un equipo, con conversaciones de canal, colaboración de archivos y aplicaciones compartidas

En este artículo se trata la cuarta opción, colaboración en grupo con conversaciones de canal, colaboración de archivos y aplicaciones compartidas. 

## <a name="terms"></a>Términos

- **Azure AD colaboración B2B**: una característica que permite a los usuarios compartir archivos, carpetas, sitios, grupos y equipos con personas de fuera de la organización. Estas personas tienen acceso a recursos compartidos mediante cuentas de invitado en el directorio.
- **Azure AD conexión directa B2B**: una característica que permite a los usuarios compartir recursos en su organización con personas de otras Azure AD organización. Estas personas tienen acceso a los recursos compartidos mediante su propia cuenta laboral o educativa. No se crea ninguna cuenta de invitado en la organización.
- **Participante externo** : una persona de fuera de la organización que participa en un recurso (como un canal compartido) que usa su propia identidad y no una cuenta de invitado en el directorio.
- **Organización externa** : otra organización con la que comparte recursos.
- **Invitado** : una persona de fuera de la organización que tiene acceso a recursos compartidos iniciando sesión en una cuenta de invitado en el directorio.
- **Organización host** : la organización que hospeda un recurso compartido, como un canal compartido.
- **Canal compartido**: un Teams que se puede compartir con personas fuera del equipo. Estas personas pueden estar dentro de la organización o de otras Azure AD organización.
- **Vínculos de** uso compartido: vínculos con permisos a un archivo o carpeta que se usan para compartir ese archivo o carpeta con otros usuarios. Las personas con las que se comparten pueden estar dentro o fuera de la organización.

## <a name="options-for-collaboration-in-a-team"></a>Opciones de colaboración en un equipo

Al colaborar en un equipo con personas ajenas a la organización, hay dos opciones para obtener acceso a los recursos que comparte con ellos.

**Uso compartido de invitados**

El uso compartido de invitados usa Azure AD colaboración B2B para permitir el uso compartido y la colaboración con personas ajenas a la organización agregando una cuenta de invitado Azure AD para cada persona. Las cuentas de invitado se pueden usar para lo siguiente:

- Pertenencia a invitados en equipos, SharePoint sitios y grupos Microsoft 365 invitados
- Uso compartido individual de archivos y carpetas

Los invitados de un equipo tienen capacidades similares a los miembros del equipo normales.

**Participantes externos en canales compartidos**

Los participantes externos tienen acceso a recursos compartidos de la organización mediante su propia Azure AD o Microsoft 365 identidad. Esto se habilita mediante Azure AD conexión directa B2B a través de una relación organizativa configurada por ambas organizaciones. Las cuentas de invitado no se usan en esta relación.

La principal ventaja de los participantes externos en canales compartidos frente al uso compartido de invitados es que las personas de fuera de la organización pueden colaborar con los usuarios en Teams sin tener que cambiar su contexto de usuario. Al usar cuentas de invitado, los usuarios deben cerrar sesión Teams con su cuenta de trabajo o escuela e iniciar sesión de nuevo con la cuenta de invitado. Como alternativa, pueden tener una copia independiente de Teams en una sesión de explorador privado. Este cambio entre organizaciones lleva tiempo y puede provocar que los usuarios pierdan comunicaciones importantes al salir de una organización determinada.

Con los canales compartidos, los usuarios pueden permanecer iniciados sesión en su organización y acceder a los canales compartidos con ellos desde otras organizaciones. Los canales compartidos de otras organizaciones están disponibles en Teams junto con los equipos y canales de la organización. No es necesario cambiar de organización.

## <a name="feature-comparison"></a>Comparación de características

En la tabla siguiente se describen las experiencias disponibles en función del tipo de cuenta usada.

|Característica|Usuario (su organización)|Invitado (Azure AD colaboración)|Participante externo (Azure AD conexión directa)|
|:-----|:-----|:------|:-------|
|Acceso de equipo|v|v|N|
|Acceso a canales compartidos|v|N|v|
|Permisos a través de vínculos de uso compartido de archivos|v|v|N|
|Usar canales compartidos|v|N|v|
|Usar canales privados|v|v|N|
|Cuenta en el directorio|v|v|N|
|Revisiones de acceso|v|v|v|
            
## <a name="planning-considerations"></a>Consideraciones de planeación

La mayoría de las organizaciones usarán tanto el uso compartido de invitados como los canales compartidos con participantes externos. 

El uso compartido de invitados está habilitado de forma Azure AD y en Microsoft 365 (Teams, Microsoft 365 grupos y SharePoint). Esto permite a los usuarios invitar invitados a equipos y sitios y compartir archivos con ellos sin tener que solicitar asistencia a TI.

Debe usar el uso compartido de invitados si:
- Desea invitar a personas de fuera de la organización al equipo en lugar de canales individuales
- Desea compartir archivos o carpetas en un canal con personas de fuera de la organización que no estén en el canal
- Desea colaborar con personas fuera de la organización que no tienen una cuenta laboral o educativa.

Aunque los canales compartidos están activados de forma predeterminada en Teams, la colaboración externa con canales compartidos requiere que un administrador de Azure AD configure el acceso entre inquilinos entre la organización y la otra organización con la que desea compartir. Cada otra organización también debe configurar el acceso entre inquilinos en su extremo.

Si tiene previsto usar canales compartidos con otras organizaciones, puede elegir entre un modelo de autoservicio y un modelo por solicitud.

- Autoservicio: puede configurar el acceso entre inquilinos para permitir el acceso entrante y saliente a todas las demás Azure AD empresariales. Como alternativa, puede bloquear una lista de organizaciones con las que no desea que los usuarios compartan, dejando todas las demás organizaciones disponibles. Esto permite a los usuarios invitar a personas de fuera de la organización a participar en canales compartidos sin tener que ponerse en contacto con el departamento de soporte técnico o de TI.
- Por solicitud: puede configurar el acceso entre inquilinos para cada organización individual con la que desea permitir canales compartidos. Al elegir este modelo, es importante tener un proceso empresarial documentado que los usuarios puedan seguir para solicitar el acceso entre inquilinos con otra organización.

## <a name="compliance-in-shared-channels"></a>Cumplimiento en canales compartidos

Los canales compartidos se integran con Microsoft 365 de cumplimiento normativo.

##### <a name="communications-compliance"></a>Cumplimiento de comunicaciones

Los administradores pueden establecer directivas para supervisar el contenido de todos los usuarios del canal. Todo el contenido de los mensajes en los canales, incluido el canal compartido, está cubierto por directivas [de cumplimiento de comunicación](/microsoft-365/compliance/communication-compliance). Los canales compartidos heredan la directiva de la organización host.

##### <a name="conditional-access"></a>Acceso condicional

Las directivas de acceso [condicional de la](/azure/active-directory/conditional-access/overview) organización host se aplican a participantes externos, incluidos los usuarios de conexión directa B2B. Las directivas de la organización externa no se usan. Los siguientes tipos de directivas de acceso condicional se admiten con canales compartidos:

- Directivas con ámbito para todos los usuarios invitados, participantes externos, SharePoint aplicaciones en la nube en línea
- Conceda controles de Access que requieran MFA, un dispositivo compatible o un dispositivo híbrido Azure AD dispositivo unido. 

Las directivas basadas en IP se admiten en el SharePoint de archivos. Por lo tanto, un participante externo podría tener acceso al canal compartido desde una ubicación restringida, pero bloquearse al intentar abrir un archivo.

##### <a name="data-loss-prevention-dlp"></a>Prevención de pérdida de datos (DLP)

Los administradores pueden aplicar [directivas DLP](/microsoft-365/compliance/dlp-policy-design) a un equipo en el que todos los canales, incluidos los canales compartidos, hereden la directiva. Los canales compartidos heredan la directiva de la organización host.

##### <a name="retention-policy"></a>Directiva de retención

Los administradores pueden aplicar una directiva [de retención](/microsoft-365/compliance/retention) en un equipo en el que todos los canales, incluidos los canales compartidos, hereden la directiva de retención. Los canales compartidos heredan la directiva del equipo primario.

##### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

[Las etiquetas](/microsoft-365/compliance/sensitivity-labels) de confidencialidad disponibles en la organización host son las únicas etiquetas que se pueden aplicar a los documentos en un sitio de canal compartido. Los participantes externos no pueden abrir un archivo cifrado por una etiqueta de confidencialidad. No se usa el etiquetado automático.

Los canales compartidos y sus SharePoint asociados heredan la etiqueta del equipo primario.

##### <a name="information-barriers"></a>Barreras de información

Los usuarios que no pueden comunicarse por directivas [de barrera](/microsoftteams/information-barriers-in-teams) de información no pueden formar parte del canal compartido. Las directivas de barrera de información solo son eficaces para los usuarios de la organización host. Si los usuarios son participantes externos en el canal compartido de otra organización, no se aplican directivas de barrera de información.

##### <a name="ediscovery"></a>eDiscovery

Los administradores pueden realizar búsquedas para todos los usuarios del canal. Todos los canales, incluido el canal compartido, son reconocibles. El administrador de cumplimiento puede detectar todos los datos de mensajes del canal independientemente de quién agregó los datos.

##### <a name="legal-hold"></a>Suspensión legal

Los administradores pueden poner en espera a los miembros de solo canal de la organización host que no forman parte del equipo. También pueden poner [todo el equipo en espera](/MicrosoftTeams/legal-hold). Los administradores no pueden poner a un participante externo en espera.

##### <a name="audit-logs"></a>Registros de auditoría

Todas las acciones realizadas para [eventos de auditoría existentes](/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) se auditan en canales compartidos.


## <a name="related-topics"></a>Temas relacionados

[Introducción a la colaboración de archivos en Microsoft 365](/sharepoint/intro-to-file-collaboration)

[Planear la colaboración de archivos SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)
