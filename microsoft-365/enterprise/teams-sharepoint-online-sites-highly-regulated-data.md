---
title: Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un sitio de grupo de SharePoint Online o un equipo de Microsoft Teams para almacenar los recursos digitales más valiosos y confidenciales.
ms.openlocfilehash: 4342ba5e5d1c83ed0c9d26100afd86afa1e62723
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289811"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados

*Este escenario se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Microsoft 365 Enterprise incluye un conjunto completo de servicios en la nube para crear, guardar y proteger sus datos altamente regulados. Esto incluye:

- Datos sujetos a regulaciones regionales.
- Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.

Una solución basada en nube de Microsoft 365 Enterprise que cumpla estas necesidades de negocio requiere que usted:

- Almacene los activos digitales (documentos, diapositivas, hojas de cálculo, etc.) en un sitio de grupo de SharePoint Online o en la pestaña **Archivos** de un equipo de Microsoft Teams.
- Bloquee el sitio o equipo para evitar:
   - El acceso únicamente a un conjunto específico de cuentas a través de la pertenencia a grupos, lo que incluye aquellas que pueden acceder al sitio de grupo de SharePoint Online y el nivel de permiso con el que cuentan, además de aquellas que pueden administrarlo.
   - Que miembros del sitio concedan acceso a terceros.
   - Que aquellos que no sean miembros del sitio soliciten acceso.
- Configure una etiqueta de retención de Office 365 para los sitios de SharePoint Online o equipos de forma predeterminada para definir directivas de retención en los documentos del sitio o equipo.
- Bloquea la capacidad de los usuarios de enviar archivos fuera de la organización.
- Cifre los recursos digitales confidenciales del sitio o grupo.
- Agregue permisos a los recursos digitales más confidenciales de modo que requieran las credenciales válidas de una cuenta de usuario para abrirse si se comparten fuera del sitio.

La tabla siguiente asigna los requisitos de esta solución a una característica de Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Requisito** | **Característica de Microsoft 365 Enterprise** |
| Almacenar recursos digitales | Sitios de grupo de SharePoint Online y equipos en Office 365 |
| Bloquear el sitio | Permisos de sitios de grupo de SharePoint Online y grupos de Azure AD |
| Etiquetar los recursos digitales del sitio | Etiquetas de retención de Office 365 |
| Bloquear a los usuarios cuando envían archivos fuera de la organización | Directivas de prevención de pérdida de datos (DLP) en Office 365 |
| Cifrar todos los recursos digitales del sitio | Etiquetas secundarias de Azure Information Protection en Enterprise Mobility + Security (EMS) |
| Añadir permisos a los recursos digitales del sitio | Etiquetas secundarias de Azure Information Protection en EMS |
|||

Esta solución requiere que haya implementado con anterioridad:

- La fase de [identidad](identity-infrastructure.md) y los pasos 1 y 2 de la fase de [protección de la información](infoprotect-infrastructure.md) de la infraestructura de base. 
- Para datos altamente regulados en sitios de grupo de SharePoint Online, [SharePoint Online](sharepoint-online-onedrive-workload.md).
- Para datos altamente regulados en equipos de Microsoft Teams, [Microsoft Teams](teams-workload.md).

Las siguientes fases le guiarán a través del diseño, la configuración y la adopción de impulso de los sitios y grupos de datos altamente regulados de SharePoint Online.

Para ver cómo Contoso Corporation, una organización multinacional ficticia pero representativa, diseñó un sitio de SharePoint Online para los equipos de investigación, vea esta [configuración de ejemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).

>[!Note]
>Un grupo de datos altamente regulados requiere crear primero un sitio de grupo de SharePoint Online para datos altamente regulados. A continuación, se debe crear un equipo que use el grupo de Office 365 del sitio de grupo de SharePoint Online. Consulte el paso 4 de la fase 2 para obtener más información.
>

## <a name="identity-and-device-access-prerequisites"></a>Requisitos previos de acceso a dispositivos e identidades

Para proteger el acceso al sitio o grupo de SharePoint Online, asegúrese de haber configurado [directivas de acceso de identidades y dispositivos](identity-access-policies.md) y [directivas de acceso recomendadas de SharePoint Online](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fase 1: Diseño

Para crear un sitio o grupo de SharePoint Online para datos altamente regulados, primero debe identificar su propósito. Por ejemplo, el departamento de investigación y desarrollo de una empresa de fabricación tiene un sitio de SharePoint Online para almacenar las especificaciones de diseño actuales de los productos existentes y un sitio para colaborar en nuevos productos. Solo los miembros del departamento de investigación y desarrollo y determinados directivos podrán tener acceso al sitio.

Ese propósito impulsará la determinación de los elementos de configuración esenciales, como:

- Los conjuntos de permisos de SharePoint Online y los grupos de SharePoint
- El conjunto de grupos de acceso, los grupos de seguridad de Azure AD y sus miembros que se agregarán a los grupos de SharePoint
- La etiqueta de retención de Office 365 para asignar al sitio y el conjunto de directivas DLP para la etiqueta
- La configuración de una etiqueta secundaria de Azure Information Protection que los usuarios aplican a los recursos digitales más confidenciales almacenados en el sitio

Una vez determinadas, use estas opciones para configurar el sitio en la fase 2. 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>Paso 1: Sitio de SharePoint Online aislado

La versión bloqueada de un sitio de grupo de SharePoint Online recibe el nombre de sitio aislado. A diferencia de la configuración predeterminada de los sitios de grupo privados, los sitios aislados están configurados para impedir:

- El acceso a los usuarios que no son miembros de grupos específicos.
- La solicitud de acceso.
- La concesión de acceso no autorizado por parte de los miembros actuales de grupos específicos.
- La administración del sitio por parte de miembros con acceso al grupo.

La seguridad de los sitios de grupo de SharePoint Online que contienen recursos altamente regulados no cambia a menos que lo haga un administrador de SharePoint del sitio.

Consulte [Diseñar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) para obtener los detalles que determinan el conjunto de niveles de permisos, grupos de SharePoint, grupos de acceso y miembros del grupo.

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>Paso 2: Etiquetas de retención de Office 365 y directivas DLP

Cuando se aplican a un sitio de grupo de SharePoint Online, las etiquetas de retención de Office 365 proporcionan un método predeterminado de clasificación para todos los recursos digitales almacenados en el sitio.
 
En los sitios de SharePoint Online para datos altamente regulados, debe determinar qué etiqueta de retención de Office 365 usar.

Para conocer las consideraciones de diseño de las etiquetas de Office 365, consulte [Etiquetas y clasificación de Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Use directivas DLP para proteger la información confidencial y evitar su divulgación accidental o intencionada. Para obtener más información, consulte esta [introducción](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

En los sitios de SharePoint Online con datos altamente regulados, debe configurar una directiva DLP para la etiqueta de retención de Office 365 asignada al sitio; esta directiva deberá bloquear a los usuarios cuando intenten compartir recursos digitales con usuarios externos. 

### <a name="step-3-your-azure-information-protection-sub-label"></a>Paso 3: Etiqueta secundaria de Azure Information Protection

Para cifrar los recursos digitales más sensibles y establecer en ellos un conjunto de permisos, los usuarios deben aplicar una etiqueta de Azure Information Protection. Para usar las etiquetas de Azure Information Protection en sitios de SharePoint Online para datos altamente regulados, debe configurar una etiqueta secundaria de Azure Information Protection en una directiva con ámbito. 

Las etiquetas secundarias se encuentran bajo etiquetas existentes. Por ejemplo, puede crear la etiqueta secundaria Investigación y desarrollo en la etiqueta Muy confidencial. Una directiva con ámbito es aquella que se aplica únicamente a un subconjunto de usuarios. Para los sitios de SharePoint Online para datos altamente regulados, el ámbito es el conjunto de usuarios que sean miembros de los grupos de acceso del sitio.

La configuración de la etiqueta secundaria aplicada se asocia al recurso. Aunque se descargue y comparta fuera del sitio, solo las cuentas de usuario autenticadas que tengan permisos podrán abrirlo.

### <a name="design-results"></a>Resultados de diseño

Ha decidido lo siguiente:

- El conjunto de grupos de SharePoint y los niveles de permisos
- El conjunto de grupos de acceso y sus miembros en cada nivel de permisos
- La etiqueta de retención adecuada de Office 365 y la directiva DLP que tiene asociada
- La configuración de la etiqueta secundaria de Azure Information Protection que incluye cifrado y permisos

## <a name="phase-2-configure"></a>Fase 2: Configurar

En esta fase, debe tomar la configuración determinada en la fase 1 e implementarla para crear un sitio de SharePoint Online para datos altamente regulados.

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>Paso 1: Crear y configurar un sitio de grupo de SharePoint Online aislado

Siga las instrucciones de [Implementar un sitio de grupo aislado de SharePoint Online](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) para:

- Crear y rellenar los grupos de acceso para cada nivel de permiso de SharePoint usado en el sitio.
- Crear y configurar el sitio de grupo aislado.

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>Paso 2: Configurar el sitio para una directiva DLP de etiquetas de retención de Office 365

Siga las instrucciones de [Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

- Identificar o crear la etiqueta de retención de Office 365 y aplicarla a su sitio de SharePoint Online aislado.
- Crear y configurar la directiva DLP que bloquee a los usuarios cuando intenten compartir un recurso digital de su sitio de SharePoint Online fuera de la organización.

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>Paso 3: Crear una etiqueta secundaria de Azure Information Protection para el sitio

Siga las instrucciones de [Proteger archivos de SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) para: 

- Crear y configurar una etiqueta secundaria de Azure Information Protection en una directiva con ámbito.
- Implementar el cliente de Azure Information Protection en los equipos usuarios.

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>Paso 4 (opcional): Crear un grupo para los datos altamente regulados

Si desea un grupo para datos altamente regulados, primero debe crear un sitio de SharePoint Online para datos altamente regulados. Al crear el sitio de grupo de SharePoint Online privado inicial, especifique un nombre de grupo de Office 365.

Cuando el sitio de SharePoint Online para datos altamente regulados esté completamente configurado, siga estos pasos para convertirlo en un equipo para datos altamente regulados:

1. Inicie sesión en Office 365.
2. En la pestaña **Página principal de Microsoft Office**, haga clic en **Grupos**.
3. Desde la pestaña **Microsoft Teams**, en el panel **Unirse o crear un equipo**, haga clic en **Crear equipo**.
4. En el panel **Crear su equipo**, haga clic en **Crear un equipo de un grupo existente de Office 365**.
5. En la lista de grupos de Office 365, seleccione el nombre del grupo de Office 365 correspondiente al sitio de SharePoint Online para datos altamente regulados y, a continuación, haga clic en **Elegir equipo**.

La pestaña **Archivos** del equipo nuevo incluye el contenido de la carpeta **General** del área **Documentos** del sitio de SharePoint Online correspondiente. Para ver el resto de los recursos del sitio de SharePoint Online para el equipo, haga clic en los puntos suspensivos y, a continuación, haga clic en **Abrir en SharePoint**.

### <a name="configuration-results"></a>Resultados de la configuración

Ha configurado lo siguiente:

- Un sitio de SharePoint Online aislado
- Una etiqueta de retención de Office 365 asignada al sitio de SharePoint Online aislado
- Una directiva DLP para la etiqueta de retención de Office 365
- Una etiqueta secundaria de Azure Information Protection de una directiva con ámbito que los usuarios pueden aplicar a los recursos digitales más confidenciales almacenados en el sitio que cifra el recurso y exige permisos
- Si es necesario, un equipo para datos altamente regulados basado en el sitio de SharePoint Online

## <a name="phase-3-drive-user-adoption"></a>Fase 3: Adopción por parte de los usuarios de la unidad

Un sitio o grupo de SharePoint Online para datos altamente regulados solo puede proteger esos datos si siempre se usa para el almacenamiento y el acceso de recursos digitales confidenciales. Esta es la fase más difícil porque depende de que los usuarios cambien sus hábitos. 

Por ejemplo, los directivos acostumbrados a almacenar archivos confidenciales en unidades USB o en almacenamiento personal basado en la nube, ahora tendrán que almacenarlos de forma exclusiva en el sitio o grupo de SharePoint Online para datos altamente regulados.

### <a name="step-1-train-your-users"></a>Paso 1: Entrenar a los usuarios

Tras completar su configuración, tome un conjunto de usuarios que pertenezcan a los grupos de acceso del sitio y fórmelos sobre los siguiente:

- La importancia de usar el nuevo sitio o equipo para proteger recursos valiosos y las consecuencias de la filtración de datos altamente regulados, como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.
- Cómo obtener acceso al sitio y a sus recursos.
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Cómo la directiva DLP les impide compartir archivos de forma externa.
- Cómo usar el cliente de Azure Information Protection para etiquetar los recursos digitales más confidenciales con la etiqueta secundaria configurada.
- Cómo la etiqueta secundaria de Azure Information Protection protege un recurso incluso tras su filtración fuera del sitio o equipo.

Esta formación debe incluir ejercicios prácticos para que los usuarios puedan experimentar con estas operaciones y sus resultados.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Paso 2: Realizar revisiones periódicas de uso y archivos

En las semanas posteriores a la formación, el administrador de SharePoint del sitio o grupo de SharePoint Online puede:

- Analizar el uso del sitio o grupo y compararlo con las expectativas de uso.
- Comprobar que los archivos más confidenciales se han etiquetado de forma correcta con la etiqueta secundaria de Azure Information Protection.

Volver a dar formación a los usuarios que lo necesiten.

### <a name="user-adoption-results"></a>Resultados de la adopción de usuarios

Los recursos digitales confidenciales se almacenan de forma exclusiva en sitios o grupos de SharePoint Online para datos altamente regulados y los datos más confidenciales tienen aplicada la etiqueta secundaria de Azure Information Protection.

## <a name="see-also"></a>Vea también

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)

[Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
