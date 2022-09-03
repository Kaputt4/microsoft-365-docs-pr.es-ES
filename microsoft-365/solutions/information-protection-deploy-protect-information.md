---
title: Protección de la información sujeta a la normativa de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Implemente las características de seguridad y cumplimiento de Microsoft 365 y proteja su información personal.
ms.openlocfilehash: c6c3a824eba7f7a15df258157d45c4d46a6024dd
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67575741"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Protección de la información sujeta a la normativa de privacidad de datos

Se pueden usar varios controles de protección de la información en su suscripción para ayudar a abordar las necesidades y regulaciones de cumplimiento de la privacidad de los datos. Estos incluyen el Reglamento General de Protección de Datos (RGPD), HIPAA-HITECH (el Estados Unidos ley de privacidad del cuidado de la salud), la Ley de Protección del Consumidor de California (CCPA) y la Ley de Protección de Datos de Brasil (LGPD).

Estos controles se encuentran dentro de las siguientes áreas de solución:

- Etiquetas de confidencialidad
- Prevención de pérdida de datos de Microsoft Purview (DLP)
- Cifrado de mensajes de Microsoft Purview
- Controles de acceso de teams y sitios

![Servicios clave para proteger la información personal sujeta a la regulación de privacidad de datos.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

> [!NOTE]
> Esta solución describe las características de seguridad y cumplimiento para proteger la información sujeta a las regulaciones de privacidad de datos. Para obtener una lista completa de las características de seguridad de Microsoft 365, consulte [la documentación de seguridad de Microsoft 365](../security/index.yml). Para obtener una lista completa de las características de cumplimiento de Microsoft 365, consulte [la documentación de Microsoft Purview](../compliance/index.yml).

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Normativas de privacidad de datos que afectan a los controles de protección de la información

Esta es una lista de ejemplo de las regulaciones de privacidad de datos que pueden estar relacionadas con los controles de protección de la información:

- Artículo 5(1)(f)) del RGPD)
- Artículo del RGPD (32)(1)(a)
- Artículo 46 de la LGPD
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Consulte el [artículo evaluación de riesgos de privacidad de datos e identificación de elementos confidenciales](information-protection-deploy-assess.md) para obtener más información sobre cada uno de los elementos anteriores.

Las regulaciones de privacidad de datos para la protección de la información recomiendan:

- Protección contra pérdidas o acceso no autorizado, uso o transmisión.
- Aplicación basada en riesgos de mecanismos de protección.
- Uso del cifrado cuando corresponda.

Es posible que su organización también quiera proteger el contenido de Microsoft 365 para otros fines, como otras necesidades de cumplimiento o por motivos empresariales. El establecimiento del esquema de protección de la información para la privacidad de los datos debe realizarse como parte del planeamiento, la implementación y la administración generales de la protección de la información.

Para ayudarle a empezar a trabajar con un esquema de protección de la información en Microsoft 365, en la sección siguiente se incluye una breve lista de funcionalidades relacionadas y acciones de mejora para Microsoft 365. La lista incluye funcionalidades y acciones de mejora que se aplican a las regulaciones de privacidad de datos. Sin embargo, la lista no incluye tecnologías anteriores si hay una funcionalidad más reciente que reemplaza en gran medida a la anterior. Por ejemplo, Information Rights Management (IRM) para SharePoint y OneDrive no se incluye en la lista, pero se incluyen etiquetas de confidencialidad.

## <a name="managing-information-protection-in-microsoft-365"></a>Administración de la protección de la información en Microsoft 365

Las [soluciones de protección de la información](../compliance/information-protection.md) de Microsoft incluyen una serie de funcionalidades integradas en Microsoft 365, Microsoft Azure y Microsoft Windows. En Microsoft 365, las soluciones de protección de la información incluyen:

- [Tipos de información confidencial](../compliance/sensitive-information-type-entity-definitions.md) (descritos en el [artículo evaluación de riesgos de privacidad de datos e identificación de elementos confidenciales)](information-protection-deploy-assess.md)
- [Etiquetas de confidencialidad](../compliance/sensitivity-labels.md)
  - Nivel de servicio o contenedor
  - Nivel de contenido o lado cliente
  - Automatizado para datos en reposo en SharePoint y OneDrive
- Prevención de pérdida de datos (DLP)
- [Prevención de perdida de datos en el punto de conexión](../compliance/endpoint-dlp-learn-about.md)
- [Office 365 nuevas funcionalidades de cifrado de mensajes (OME)](../compliance/ome.md) y [cifrado avanzado de mensajes](../compliance/ome-advanced-message-encryption.md) de OME

Además, la protección de nivel de sitio y biblioteca son mecanismos importantes para incluir en cualquier esquema de protección.

Para obtener información sobre otras funcionalidades de protección de la información fuera de Microsoft 365, consulte:

- [Microsoft Defender for Cloud Apps](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Las etiquetas de confidencialidad de Microsoft Purview Information Protection permiten clasificar y proteger los datos de su organización sin afectar a la productividad de los usuarios y a su capacidad de colaboración.

> [!div class="mx-imgBorder"]
> ![Etiquetas de confidencialidad en Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Requisitos previos para etiquetas de confidencialidad

Complete estas actividades antes de implementar cualquiera de las funcionalidades basadas en etiquetas de confidencialidad resaltadas a continuación:

1. Comprenda lo siguiente:
   - **Requisitos empresariales.** Establezca los motivos empresariales para aplicar etiquetas de confidencialidad en su empresa. Por ejemplo, los requisitos de privacidad de datos para la protección de la información.
   - **Capacidades de etiqueta de confidencialidad.** El etiquetado de confidencialidad puede ser complejo, por lo que asegúrese de leer la [documentación de etiquetas de confidencialidad](../compliance/sensitivity-labels.md) antes de empezar.
   - **Aspectos clave que hay que recordar** Las etiquetas de confidencialidad se administran en el portal de cumplimiento Microsoft Purview, pero las opciones de destino y aplicación varían significativamente.
      - Hay etiquetas de confidencialidad para sitios, grupos y Teams en el nivel de contenedor (la configuración no se aplica al contenido dentro del contenedor). Se publican en usuarios y grupos que los aplican cuando se aprovisiona un sitio, un grupo o un equipo.
      - Hay etiquetas de confidencialidad para el contenido activo. También se publican en usuarios o grupos, que los aplican manualmente, o se aplican automáticamente cuando:
        - El archivo se abre, edita o guarda, ya sea en el escritorio del usuario o en un sitio de SharePoint.
        - Se redacta y se envía un correo electrónico.
      - Hay etiquetas de confidencialidad para la aplicación automática a los archivos en reposo en SharePoint y OneDrive, además de los correos electrónicos en tránsito a través de Exchange. Estos están destinados a todos los sitios o específicos y se aplican automáticamente a los archivos en reposo en estos entornos.

2. Racionalización del etiquetado de confidencialidad actual con métodos pasados o alternativos

   - Azure Information Protection

      Es posible que sea necesario conciliar el esquema de etiquetado de confidencialidad actual con cualquier implementación de etiquetado [de Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) existente.
   - Ome

      Si tiene previsto usar el etiquetado de confidencialidad moderno para la protección del correo electrónico y existen métodos de cifrado de correo electrónico como OME, pueden coexistir, pero debe comprender los escenarios en los que se debe aplicar cualquiera de ellas. Consulte [Office 365 nuevas funcionalidades de cifrado de mensajes (OME),](#office-365-message-encryption-ome-new-capabilities) que incluye una tabla que compara la protección moderna del tipo de etiqueta de confidencialidad con la protección basada en OME.

3. Planee la integración en un esquema de protección de la información más amplio. Además de la coexistencia con OME, las etiquetas de confidencialidad se pueden usar a lo largo de las funcionalidades del lado, como Prevención de pérdida de datos de Microsoft Purview (DLP) y Microsoft Defender for Cloud Apps. Consulte [Protección de los datos con Microsoft Purview](../compliance/information-protection.md) para lograr los objetivos de protección de la información relacionados con la privacidad de los datos.

4. Desarrolle un esquema de control y clasificación de etiquetas de confidencialidad. Consulte [Taxonomía de etiquetas de confidencialidad y clasificación de datos](https://aka.ms/dataclassificationwhitepaper).

### <a name="general-guidance"></a>Instrucciones generales

1. **Definición de esquema.** Antes de usar funcionalidades técnicas para aplicar etiquetas y protección, trabaje en toda la organización para definir un esquema de clasificación. Es posible que ya tenga un esquema de clasificación, lo que facilita la incorporación de datos personales.
2. **Empezar.** Empiece por decidir el número y los nombres de las etiquetas que se van a implementar. Realice esta actividad sin preocuparse por qué tecnología usar y cómo se aplicarán las etiquetas. Aplique este esquema universalmente en toda la organización, incluidos los datos que residen en el entorno local y en otros servicios en la nube.
3. **Recomendaciones adicionales** Al diseñar e implementar directivas, etiquetas y condiciones, considere la posibilidad de seguir estas recomendaciones:

   - **Use el esquema de clasificación existente (si existe).** Muchas organizaciones ya usan la clasificación de datos de alguna forma. Evalúe cuidadosamente el esquema de etiqueta existente y, si es posible, úselo tal cual. El uso de etiquetas conocidas que son reconocibles para los usuarios finales impulsará la adopción.
   - **Empieza pequeño.** Prácticamente no hay ningún límite en el número de etiquetas que puede crear. Sin embargo, un gran número de etiquetas y subetiquetas puede ralentizar la adopción.
   - **Use escenarios y casos de uso.** Identifique casos de uso comunes dentro de su organización y escenarios de uso derivados de las regulaciones de privacidad de datos a las que está sujeto. Compruebe si la configuración de clasificación y la etiqueta aprovisionadas funcionarán en la práctica.
   - **Pregunta cada solicitud de una nueva etiqueta.** ¿Todos los escenarios o casos de uso necesitan realmente una nueva etiqueta o puede usar lo que ya tiene? Mantener el número mínimo de etiquetas mejora la adopción.
   - **Use subetiquetas para los departamentos clave.** Algunos departamentos tendrán necesidades específicas que requieren etiquetas específicas. Defina estas etiquetas como subetiquetas en una etiqueta existente y considere la posibilidad de usar directivas con ámbito asignadas a grupos de usuarios en lugar de globalmente.
   - **Considere las directivas con ámbito.** Las directivas destinadas a subconjuntos de usuarios evitarán la sobrecarga de etiquetas. Una directiva con ámbito permite asignar etiquetas o subetiquetas específicas de roles o departamentos solo a los empleados que trabajan para ese departamento específico.
   - **Use nombres de etiqueta significativos.** Intente no usar jerga, estándares o acrónimos como nombres de etiqueta. Intente usar nombres que resuenan con el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, MBI y HBI, tenga en cuenta nombres como Non-Business, Public, General, Confidential y Highly Confidential.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Creación e implementación de etiquetas de confidencialidad para sitios, grupos y equipos

Al crear [etiquetas de confidencialidad](../compliance/sensitivity-labels-teams-groups-sites.md) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, ahora puede aplicarlas a estos contenedores:

- Sitios de Microsoft Teams
- Grupos de Microsoft 365 (anteriormente Office 365 grupos)
- Sitios de SharePoint

Use la siguiente configuración de etiqueta para ayudar a proteger el contenido de estos contenedores:

- Privacidad (pública o privada) de los sitios de Teams conectados a grupos de Microsoft 365
- Acceso de usuarios externos
- Acceso desde dispositivos no administrados

Para la privacidad de los datos, para evitar el uso compartido externo de contenedores que se usarán para almacenar contenido con datos personales confidenciales, marque los archivos que contienen los datos como privados y requiera dispositivos administrados.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Creación e implementación de etiquetas de confidencialidad para el contenido

Las etiquetas de confidencialidad aplicadas a los archivos permiten cifrar su contenido, marcar la marca de agua del contenido y definir otros controles para el contenido de las aplicaciones de Office, incluidos Outlook y Office en la Web.

Cuando esté listo para empezar a proteger los datos de su organización con etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Para obtener más información sobre el desarrollo de una taxonomía de clasificación, consulte el [artículo sobre taxonomía de la etiqueta de confidencialidad y clasificación de datos](https://aka.ms/dataclassificationwhitepaper).
2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, es posible que desee que el contenido de confidencialidad inferior (como una etiqueta "General") tenga aplicado solo un encabezado o pie de página, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debe tener una marca de agua y tener el cifrado habilitado.
3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable. Se define una vez y, a continuación, se puede incluir en varias directivas de etiqueta asignadas a usuarios diferentes.

Una vez que publique etiquetas de confidencialidad desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, comenzarán a aparecer en [las aplicaciones de Office](../compliance/sensitivity-labels-office-apps.md) para que los usuarios clasifiquen y protejan el contenido a medida que se crea o edita.

![Flujo de implementación de etiquetas de confidencialidad en Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Para la privacidad de los datos, aplica manualmente una etiqueta de confidencialidad con cifrado y otras reglas al correo electrónico o al contenido que contiene información personal confidencial.

> [!NOTE]
> Las etiquetas de confidencialidad con cifrado habilitado aplicado al correo electrónico tienen alguna funcionalidad superpuesta con OME. Consulte [Comparación de escenarios de correo electrónico seguros con OME y etiquetas de confidencialidad](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels).

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Etiquetado automático del lado cliente cuando los usuarios editan documentos o redactan correos electrónicos

Al crear una etiqueta de confidencialidad, puede [asignarla automáticamente](../compliance/apply-sensitivity-label-automatically.md) al contenido, incluido el correo electrónico, cuando coincida con las condiciones que especifique.

La capacidad de aplicar automáticamente etiquetas de confidencialidad al contenido es importante por estos motivos:

- No es necesario enseñar a los usuarios cuándo usar cada una de las clasificaciones.
- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.

El etiquetado automático admite la recomendación de una etiqueta a los usuarios, así como la aplicación automática de una etiqueta. Pero en ambos casos, el usuario decide si acepta o rechaza la etiqueta, para ayudar a garantizar el etiquetado correcto del contenido.

Este etiquetado del lado del cliente tiene un retraso mínimo para los documentos porque la etiqueta se puede aplicar incluso antes de que se guarde el documento. Sin embargo, no todas las aplicaciones cliente son compatibles con el etiquetado automático. Esta funcionalidad es compatible con Azure Information Protection cliente de etiquetado unificado y [algunas versiones de aplicaciones de Office](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Para obtener instrucciones de configuración, consulte [Configuración del etiquetado automático para aplicaciones de Office](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Para la privacidad de los datos, aplica automáticamente etiquetas de confidencialidad para el contenido que contiene información personal confidencial.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Etiquetado automático del lado del servicio cuando el contenido ya está guardado

Este método se conoce como clasificación automática con etiquetas de confidencialidad. También puede escucharlo como etiquetado automático para datos en reposo (para documentos en SharePoint y OneDrive) y datos en tránsito (para correo electrónico enviado o recibido por Exchange). Para Exchange, no incluye correos electrónicos en buzones en reposo.

Dado que este etiquetado lo aplica el propio servicio en lugar de la aplicación de usuario, no es necesario preocuparse por qué aplicaciones tienen los usuarios y qué versión. Por lo tanto, esta funcionalidad está disponible inmediatamente en toda la organización y es adecuada para aplicar las etiquetas a cualquier escala. Las directivas de etiquetado automático no admiten el etiquetado recomendado, ya que el usuario no interactúa con el proceso de etiquetado. En su lugar, el administrador ejecuta las directivas en el modo de simulación para ayudarle a garantizar el etiquetado correcto del contenido antes de aplicar la etiqueta.

Para obtener instrucciones de configuración, consulte [Configuración de directivas de etiquetado automático para SharePoint, OneDrive y Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

Para la privacidad de los datos dentro de los sitios de interés, inserte etiquetas de confidencialidad para el cifrado automático del contenido que contiene información personal confidencial.

## <a name="data-loss-prevention"></a>Prevención de pérdida de datos

Puede usar la [prevención de pérdida de datos (DLP)](../compliance/dlp-learn-about-dlp.md) en Microsoft Purview para detectar, advertir y bloquear el uso compartido de riesgos, involuntarios o inadecuados, como el uso compartido de datos que contienen información personal, tanto interna como externamente.

DLP le permite:

- Identificar y supervisar actividades de uso compartido de riesgo.
- Instruya a los usuarios con instrucciones en contexto para tomar las decisiones adecuadas.
- Aplicar directivas de uso de datos sobre el contenido sin inhibir la productividad.
- Integre con clasificación y etiquetado para detectar y proteger los datos cuando se comparten.

### <a name="supported-workloads-for-dlp"></a>Cargas de trabajo admitidas para DLP

Con una directiva DLP en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, puede identificar, supervisar y proteger automáticamente elementos confidenciales en muchas ubicaciones de Microsoft 365, como Exchange Online, SharePoint, OneDrive y Microsoft Teams.

Por ejemplo, puede identificar cualquier documento que contenga un número de tarjeta de crédito almacenado en cualquier sitio de OneDrive, o puede supervisar solo los sitios de OneDrive de personas específicas.

También puede supervisar y proteger elementos confidenciales en las versiones instaladas localmente de Excel, PowerPoint y Word, que incluyen la capacidad de identificar elementos confidenciales y aplicar directivas DLP. DLP proporciona supervisión continua cuando los usuarios comparten contenido de estas aplicaciones de Office.

> [!div class="mx-imgBorder"]
> ![Cargas de trabajo admitidas para DLP.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

En esta ilustración se muestra un ejemplo de protección de datos personales de DLP.

> [!div class="mx-imgBorder"]
> ![Ejemplo de protección de datos personales mediante DLP.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP se usa para identificar un documento o correo electrónico que contiene un registro de estado y, a continuación, bloquea automáticamente el acceso a ese documento o impide que se envíe el correo electrónico. A continuación, DLP notifica al destinatario una sugerencia de directiva y envía una alerta al usuario final y al administrador.

### <a name="planning-for-dlp"></a>Planeamiento de DLP

Consulte [Planear la prevención de pérdida de datos (DLP)](../compliance/dlp-overview-plan-for-dlp.md) para obtener instrucciones completas sobre cómo planear la implementación de DLP.

<!-- Plan your DLP policies for:

- Your business requirements.

- A risk-based assessment of the organization as described in the [assess data privacy risks and identify sensitive items article](information-protection-deploy-assess.md).

- Other information protection and governance mechanisms in place or in planning for data privacy.

- The sensitive information types that you’ve identified for personal data based on your assessment work as described in the [assess data privacy risks and identify sensitive items article](information-protection-deploy-assess.md). DLP policy conditions can be based on both sensitive information types and retention labels.

- The retention labels you'll need to specify DLP conditions. See the [govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md) article for more information.

- Ongoing DLP policy management, which requires someone in the organization to operate and tune policies for changes in sensitive information types, retention labels, regulations, and compliance policies.

Although sensitivity labels can’t be used in DLP policy conditions, certain protection scenarios to prevent access may be achievable with just sensitivity labels that can be auto-applied based on sensitive information types. If robust sensitivity labeling is in place, consider whether DLP should be used to augment protection because:

  - DLP can prevent sharing of files. Sensitivity labels can just prevent access.

  - DLP has more granular levels of control in terms of rules, conditions, and actions.

  - DLP policies can be applied to Teams chat and channel messages. Sensitivity labels can only be applied to documents and email. -->


### <a name="dlp-policies"></a>Directivas DLP

Las directivas DLP se configuran en el portal de cumplimiento Microsoft Purview y especifican el nivel de protección, la información que busca la directiva y las cargas de trabajo de destino. Cada directiva DLP requiere lo siguiente:

1. Elija lo que quiere supervisar.
1. Elija dónde supervisar.
1. Elija las condiciones que deben coincidir para que una directiva se aplique a un elemento.
1. Elija la acción que se va a realizar cuando se cumplan las condiciones de la directiva.

Para obtener más información sobre las directivas DLP y cómo diseñarlas, consulte:

- [Obtenga más información acerca de la prevención contra la pérdida de datos](../compliance/dlp-learn-about-dlp.md)
- [Diseño de una directiva de prevención de pérdida de datos](../compliance/dlp-policy-design.md)
- [Referencia de directiva de prevención de pérdida de datos](../compliance/dlp-policy-reference.md)


<!--

> [!div class="mx-imgBorder"]
> ![DLP policy configuration in Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Here is an example DLP policy for awareness of GDPR.

![Example DLP policy for awareness of GDPR.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

See [this article](../compliance/create-test-tune-dlp-policy.md) for more information about creating and applying DLP policies.-->

### <a name="protection-levels-for-data-privacy"></a>Niveles de protección para la privacidad de los datos

En la tabla siguiente se enumeran tres configuraciones de aumento de la protección mediante DLP.

![Niveles de protección de la privacidad de los datos con DLP.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

La primera configuración, Awareness, se puede usar como punto de partida y nivel mínimo de protección para satisfacer las necesidades de cumplimiento de las normativas de privacidad de datos.

> [!NOTE]
> A medida que aumentan los niveles de protección, la capacidad de los usuarios para compartir y acceder a la información disminuirá en algunos casos y podría afectar potencialmente a su productividad o capacidad para completar tareas diarias.

Para ayudar a los empleados a seguir siendo productivos en un entorno más seguro al aumentar los niveles de protección, tómese el tiempo necesario para entrenarlos y educarlos en nuevas directivas y procedimientos de seguridad.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Ejemplo de uso de etiquetas de confidencialidad con DLP

Las etiquetas de confidencialidad pueden funcionar junto con DLP para proporcionar privacidad de datos en un entorno altamente regulado. Estos son los pasos clave de la implementación integrada:

1. Se documentan los requisitos normativos y empresariales de la privacidad de los datos.
2. Los orígenes de datos de destino, los tipos y la propiedad se caracterizan por tener en cuenta los problemas de privacidad de los datos.
3. Se establece una estrategia general para abordar los requisitos y proteger y controlar los puntos de acceso a la privacidad de los datos.
4. Se establece un plan de acción por fases para abordar la estrategia de control de privacidad de datos.

Una vez determinados estos elementos, puede usar los tipos de información confidencial, la taxonomía de etiquetado de confidencialidad y las directivas DLP juntas. En esta ilustración se muestra un ejemplo.

> [!div class="mx-imgBorder"]
> ![Ejemplo de etiquetas de confidencialidad que funcionan con DLP.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Estos son algunos escenarios de protección de datos que usan dlp y etiquetas de confidencialidad juntos, como se muestra en la ilustración.

| Escenario | Proceso |
|:-------|:-----|
| A | <ol><li>Las etiquetas de confidencialidad del contenido las publica un administrador a los usuarios y grupos para que la aplicación manual o automática se publique en el contenido y el correo electrónico. </li><li>El usuario A aplica las etiquetas de forma manual o automática al interactuar con el contenido, con cifrado u otra configuración aplicada. </li><li>El usuario A envía un archivo o correo electrónico protegido al usuario B, un usuario invitado. </li></ol> |
| N | La directiva DLP publicada por un administrador en el usuario A impide que el usuario A envíe el correo electrónico o el archivo al usuario B. |
| C |  La etiqueta de confidencialidad con la configuración "propietario no puede invitar invitados" se publica en el usuario A, que aprovisiona un equipo de Teams o un sitio de SharePoint. Otro usuario del sitio intenta compartir selectivamente un archivo con el usuario B, pero DLP lo bloquea. |
| D | La etiqueta de confidencialidad del contenido de aplicación automática al sitio se publica en uno o varios sitios, lo que proporciona otra capa de protección, lo que da lugar a un sitio protegido. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 nuevas funcionalidades de cifrado de mensajes (OME)

Personas a menudo usan el correo electrónico para intercambiar elementos confidenciales, como información de salud del paciente o información de clientes y empleados. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Con [OME](../compliance/ome.md), puede enviar y recibir mensajes cifrados entre personas dentro y fuera de su organización. OME funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. OME ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Para la privacidad de los datos, use OME para proteger los mensajes internos que contienen elementos confidenciales. Office 365 Message Encryption es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS) que forma parte de Azure Information Protection. Esto incluye directivas de cifrado, identidad y autorización para ayudar a proteger el correo electrónico. Puede cifrar los mensajes mediante plantillas de administración de derechos, la opción No reenviar y la opción de solo cifrado.

También puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico, o que contenga palabras clave específicas en la línea de asunto, y también especificar que los destinatarios no puedan copiar ni imprimir el contenido del mensaje.

Además, el [cifrado avanzado de](../compliance/ome-advanced-message-encryption.md) mensajes de OME le ayuda a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a correos electrónicos cifrados. Con el cifrado avanzado de mensajes de OME en Microsoft 365, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que detectan tipos de información confidencial.

Para la privacidad de los datos, si necesita compartir correo electrónico con una entidad externa, puede especificar una fecha de expiración y revocar los mensajes. Solo puede revocar y establecer una fecha de expiración para los mensajes enviados a destinatarios externos.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Comparación de escenarios de correo electrónico seguros con OME y etiquetas de confidencialidad

Las etiquetas de OME y confidencialidad aplicadas al correo electrónico con cifrado tienen cierta superposición, por lo que es importante comprender a qué escenarios se pueden aplicar, como se muestra en esta tabla.

| Escenario | Etiquetas de confidencialidad | Ome |
|:-------|:-----|:-------|
| Interno y asociados <br> Comunicación y colaboración seguras entre usuarios internos y asociados de confianza | Recomendación: etiquetas con clasificación y protección totalmente personalizadas | Sí: cifre solo o no reenvíe la protección sin clasificación |
| Partes externas <br> Comunicarse y colaborar de forma segura con cualquier usuario externo o consumidor | Sí: predefinidos destinatarios en la etiqueta | Recomendación: protección Just-In-Time basada en destinatarios |
| Interno y asociados, con expiración o revocación <br> Control del acceso al correo y al contenido con usuarios internos y asociados de confianza con expiración y revocación | Recomendación: protección totalmente personalizada con duración de acceso, el usuario puede realizar un seguimiento manual y revocar archivos. | No: no hay revocación ni expiración para el correo interno |
| Partes externas con expiración o revocación <br> Control del acceso al correo y al contenido con usuarios externos o consumidores con expiración y revocación | Sí: el usuario puede realizar un seguimiento manual de los archivos | Recomendación (E5): el administrador puede revocar el correo del Centro de cumplimiento de seguridad & |
| Etiquetado automático <br> La organización quiere proteger automáticamente el correo o los datos adjuntos con contenido confidencial específico o destinatarios específicos | Recomendación (E5): etiquetado automático en clientes de Exchange y Outlook, aumenta las reglas de flujo de correo y la directiva DLP | Sí: reglas de flujo de correo y directiva DLP con cifrar solo o no reenviar protección |
||||

También habrá diferencias en las experiencias de usuario final y administrador entre estos dos métodos.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Equipos con protección para datos altamente confidenciales

Para las organizaciones que planean almacenar datos personales sujetos a las regulaciones de privacidad de datos en Teams, consulte [Configuración de un equipo con aislamiento de seguridad](secure-teams-security-isolation.md), que proporciona instrucciones detalladas y pasos de configuración para:

- Acceso de dispositivos e identidades
- Creación de un equipo privado
- Bloqueo de permisos de sitio de equipo subyacentes
- Una etiqueta de confidencialidad basada en grupos con cifrado
