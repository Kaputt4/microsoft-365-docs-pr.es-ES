---
title: Proteger la información sujeta a la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Implemente características de seguridad y cumplimiento de Microsoft 365 y proteja su información personal.
ms.openlocfilehash: 657b3c9c6416c8a38629a0d26253e1222aa6d242
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928477"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger la información sujeta a la regulación de privacidad de datos

Se pueden usar varios controles de protección de la información en la suscripción para ayudar a solucionar las necesidades y normativas de cumplimiento de privacidad de datos. Entre ellas se incluyen el Reglamento general de protección de datos (RGPD), HIPAA-HITECH (la ley de privacidad del cuidado de la salud de Estados Unidos), la Ley de protección de consumidores de California (CCPA) y la Ley de protección de datos de Brasil (LGPD).

Estos controles se encuentran dentro de las siguientes áreas de solución:

- Etiquetas de confidencialidad
- Prevención de pérdida de datos (DLP)
- Cifrado de mensajes de Office (OME)
- Controles de acceso de teams y sitios

![Servicios clave para proteger la información personal sujeta a la regulación de privacidad de datos](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Esta solución describe las características de seguridad y cumplimiento para proteger la información sujeta a las normativas de privacidad de datos. Para obtener una lista completa de las características de seguridad de Microsoft 365, consulte Documentación de seguridad [de Microsoft 365](../security/index.yml). Para obtener una lista completa de las características de cumplimiento en Microsoft 365, consulte Documentación de cumplimiento de [Microsoft 365](../compliance/index.yml).
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Normativas de privacidad de datos que afectan a los controles de protección de la información

Esta es una lista de ejemplo de las normativas de privacidad de datos que pueden estar relacionadas con los controles de protección de la información:

- Artículo 5(1)(f)del RGPD)
- Artículo del RGPD (32)(1)(a)
- Artículo 46 de LGPD
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Consulte el artículo evaluar los riesgos de privacidad de datos e identificar elementos [confidenciales](information-protection-deploy-assess.md) para obtener más información sobre cada uno de los anteriores.

Las normativas de privacidad de datos para la protección de la información recomiendan:

- Protección contra pérdida o acceso no autorizado, uso y/o transmisión.
- Aplicación basada en riesgos de mecanismos de protección.
- Uso del cifrado cuando corresponda.

Es posible que su organización también quiera proteger el contenido de Microsoft 365 para otros fines, como otras necesidades de cumplimiento o por motivos empresariales. El establecimiento del esquema de protección de la información para la privacidad de datos debe realizarse como parte de la planeación, implementación y administración generales de la protección de la información.

Para ayudarle a empezar con un esquema de protección de la información en Microsoft 365, en la siguiente sección se incluye una breve lista de las capacidades relacionadas y las acciones de mejora para Microsoft 365. La lista incluye funcionalidades y acciones de mejora que se aplican a las normativas de privacidad de datos. Sin embargo, la lista no incluye tecnologías anteriores si hay una funcionalidad más reciente que reemplaza en gran medida a la anterior. Por ejemplo, Information Rights Management (IRM) para SharePoint y OneDrive no se incluye en la lista, pero se incluyen etiquetas de confidencialidad.

## <a name="managing-information-protection-in-microsoft-365"></a>Administración de la protección de la información en Microsoft 365

Las [soluciones de protección de la](../compliance/information-protection.md) información de Microsoft incluyen una serie de funcionalidades integradas en Microsoft 365, Microsoft Azure y Microsoft Windows. En Microsoft 365, las soluciones de protección de la información incluyen:

- [Cifrado de servicio con clave de cliente](../compliance/customer-key-overview.md)
- [Tipos de información confidencial](../compliance/sensitive-information-type-entity-definitions.md) (descrito en el artículo Evaluar riesgos de privacidad de datos [e identificar elementos confidenciales)](information-protection-deploy-assess.md)
- [Etiquetas de confidencialidad](../compliance/sensitivity-labels.md) 
  - Nivel de servicio/contenedor
  - Cliente/nivel de contenido
  - Automatizado para datos en reposo en SharePoint y OneDrive
- Prevención de pérdida de datos (DLP)
- [Prevención de pérdida de datos del punto de conexión de Microsoft 365](../compliance/endpoint-dlp-learn-about.md)
- [Cifrado de mensajes de Office 365 nuevas capacidades (OME)](../compliance/ome.md) y Cifrado de mensajes [avanzado de](../compliance/ome-advanced-message-encryption.md) OME

Además, la protección del nivel de sitio y biblioteca son mecanismos importantes que deben incluirse en cualquier esquema de protección.

Para obtener información sobre otras capacidades de protección de la información fuera de Microsoft 365, vea:

- [Microsoft Cloud Application Security (MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Las etiquetas de confidencialidad del marco de Microsoft Information Protection le permiten clasificar y proteger los datos de su organización sin obstaculizar la productividad de los usuarios y su capacidad de colaboración.

![Etiquetas de confidencialidad en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Requisitos previos para etiquetas de confidencialidad

Complete estas actividades antes de implementar cualquiera de las funciones basadas en etiquetas de confidencialidad que se destacan a continuación:

1. Comprenda lo siguiente:
   - **Requisitos empresariales.** Establecer las razones de negocio para aplicar etiquetas de confidencialidad en su empresa. Por ejemplo, los requisitos de privacidad de datos para la protección de la información.
   - **Capacidades de etiqueta de confidencialidad.** El etiquetado de confidencialidad puede ser complejo, por lo que asegúrate de leer la documentación de etiquetas [de confidencialidad](../compliance/sensitivity-labels.md) antes de empezar.
   - **Cosas clave que debe recordar** Las etiquetas de confidencialidad se administran en el Centro de administración de Cumplimiento de Microsoft, pero las opciones de destino y aplicación varían considerablemente.
      - Hay etiquetas de confidencialidad para sitios, grupos y Teams en el nivel de contenedor (la configuración no se aplica al contenido dentro del contenedor). Se publican para usuarios y grupos que los aplican cuando se aprovisiona un sitio, un grupo o un equipo.
      - Hay etiquetas de confidencialidad para el contenido activo. También se publican en usuarios o grupos, que los aplican manualmente o se aplican automáticamente cuando:
        - El archivo se abre, edita o guarda, ya sea en el escritorio del usuario o en un sitio de SharePoint.
        - Se redacta y se envía un correo electrónico.
      - Hay etiquetas de confidencialidad para la aplicación automática a los archivos en reposo en SharePoint y OneDrive, además de los correos electrónicos en tránsito a través de Exchange. Estos están dirigidos a todos los sitios o específicos y se aplican automáticamente a los archivos en reposo en estos entornos.

2. Racionalizar el etiquetado de confidencialidad actual con métodos anteriores o alternativos

   - Azure Information Protection

      Es posible que el esquema de etiquetado de confidencialidad actual deba conciliarse con cualquier implementación de etiquetado existente de [Azure Information Protection.](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Si está planeando usar el etiquetado de confidencialidad moderno para la protección de correo electrónico y los métodos de cifrado de correo electrónico existentes, como OME, pueden coexistir, pero debe comprender los escenarios en los que se debe aplicar cualquiera de los dos. Consulte [Office 365 Message Encryption new capabilities (OME),](#office-365-message-encryption-ome-new-capabilities)que incluye una tabla que compara la protección de tipo de etiqueta de confidencialidad moderna con la protección basada en OME.

3. Planear la integración en un esquema de protección de la información más amplio. Además de la coexistencia con OME, las etiquetas de confidencialidad actuales se pueden usar junto con funcionalidades como prevención de pérdida de datos (DLP) de Microsoft 365 y Microsoft Cloud App Security. Consulta [Etiquetas de confidencialidad y Microsoft Cloud App Security para](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) lograr tus objetivos de protección de la información relacionados con la privacidad de datos.

4. Desarrollar un esquema de clasificación y control de etiquetas de confidencialidad. Vea [Clasificación de datos y Taxonomía de etiquetas de confidencialidad.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Instrucciones generales

1. **Definición de esquema.** Antes de usar funcionalidades técnicas para aplicar etiquetas y protección, trabaje en toda la organización para definir un esquema de clasificación. Es posible que ya tenga un esquema de clasificación, lo que facilita la adición de datos personales. 
2. **Introducción.** Comience por decidir el número y los nombres de las etiquetas que se implementarán. Realice esta actividad sin preocuparse por qué tecnología usar y cómo se aplicarán las etiquetas. Aplique este esquema de forma universal en toda la organización, incluidos los datos que residen en el entorno local y en otros servicios en la nube.
3. **Recomendaciones adicionales** Al diseñar e implementar directivas, etiquetas y condiciones, considere la posibilidad de seguir estas recomendaciones:

   - **Use el esquema de clasificación existente (si existe).** Muchas organizaciones ya usan la clasificación de datos de alguna forma. Evalúe cuidadosamente el esquema de etiqueta existente y, si es posible, úselo tal como está. El uso de etiquetas conocidas que son reconocibles para los usuarios finales impulsará la adopción.
   - **Inicie pequeño.** Prácticamente no hay ningún límite en el número de etiquetas que puede crear. Sin embargo, un gran número de etiquetas y subetiquetas puede ralentizar la adopción.
   - **Use escenarios y casos de uso.** Identifique casos de uso comunes dentro de su organización y use escenarios derivados de las normativas de privacidad de datos a las que está sujeto. Compruebe si la etiqueta y la configuración de clasificación previstos funcionarán en la práctica.
   - **Pregunta cada solicitud de una nueva etiqueta.** ¿Cada escenario o caso de uso realmente necesita una nueva etiqueta o puede usar lo que ya tiene? Mantener el número de etiquetas al mínimo mejora la adopción.
   - **Use subetiquetas para departamentos clave.** Algunos departamentos tendrán necesidades específicas que requieren etiquetas específicas. Defina estas etiquetas como subetiquetas en una etiqueta existente y considere la posibilidad de usar directivas de ámbito asignadas a grupos de usuarios en lugar de globalmente.
   - **Considere las directivas de ámbito.** Las directivas dirigidas a subconjuntos de usuarios evitarán la sobrecarga de etiquetas. Una directiva de ámbito permite asignar etiquetas o subetiquetas específicas del departamento o roles a solo los empleados que trabajan para ese departamento específico. 
   - **Use nombres de etiqueta significativos.** Intente no usar jerga, estándares o acrónimos como nombres de etiqueta. Intente usar nombres que resonen con el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, MBI y HBI, considera nombres como Non-Business, Public, General, Confidential y Highly Confidential.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Crear e implementar etiquetas de confidencialidad para sitios, grupos y equipos

Al crear [etiquetas de confidencialidad](../compliance/sensitivity-labels-teams-groups-sites.md) en el Centro de cumplimiento de Microsoft 365, ahora puede aplicarlas a estos contenedores:

- Sitios de Microsoft Teams
- Grupos de Microsoft 365 (anteriormente grupos de Office 365)
- Sitios de SharePoint

Use la siguiente configuración de etiqueta para ayudar a proteger el contenido de estos contenedores:

- Privacidad (pública o privada) de los sitios de Microsoft 365 conectados a grupos de Teams
- Acceso de usuarios externos
- Acceso desde dispositivos no administrados

Para la privacidad de datos, para evitar el uso compartido externo de contenedores que se usarán para almacenar contenido con datos personales confidenciales, marque los archivos que contienen los datos como privados y requiera dispositivos administrados.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Crear e implementar etiquetas de confidencialidad para el contenido

Las etiquetas de confidencialidad aplicadas a los archivos permiten cifrar su contenido, marcar de agua el contenido y definir otros controles para el contenido de aplicaciones de Office, incluidos Outlook y Office en la web.

Cuando esté listo para empezar a proteger los datos de su organización con etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Para obtener más información sobre el desarrollo de una taxonomía de clasificación, vea las white [paper Data Classification and Sensitivity Label Taxonomy](https://aka.ms/dataclassificationwhitepaper).
2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, es posible que desee que el contenido de menor confidencialidad (como una etiqueta "General") tenga solo un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debe tener una marca de agua y tener cifrado habilitado.
3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable. Se define una vez y, a continuación, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios.

Una vez que publique etiquetas de confidencialidad desde el Centro de cumplimiento de Microsoft 365, empezarán a aparecer en aplicaciones de [Office](../compliance/sensitivity-labels-office-apps.md) para que los usuarios clasifiquen y protejan el contenido a medida que se crea o edita.

![Flujo de implementación de etiquetas de confidencialidad en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Para la privacidad de datos, se aplica manualmente una etiqueta de confidencialidad con cifrado y otras reglas al correo electrónico o al contenido que contiene información personal confidencial.

>[!Note]
>Las etiquetas de confidencialidad con cifrado habilitado aplicado al correo electrónico tienen cierta funcionalidad superpuesta con OME. Consulte [Secure email scenarios comparison with OME and sensitivity labels](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels).

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Etiquetado automático del lado cliente cuando los usuarios editan documentos o redactan correos electrónicos

Al crear una etiqueta de [](../compliance/apply-sensitivity-label-automatically.md) confidencialidad, puede asignarla automáticamente al contenido, incluido el correo electrónico, cuando coincida con las condiciones especificadas.

La capacidad de aplicar automáticamente etiquetas de confidencialidad al contenido es importante por estos motivos:

- No es necesario enseñar a los usuarios cuándo usar cada una de las clasificaciones.
- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.

El etiquetado automático admite la recomendación de una etiqueta a los usuarios, así como la aplicación automática de una etiqueta. Pero en ambos casos, el usuario decide si acepta o rechaza la etiqueta, para ayudar a garantizar el etiquetado correcto del contenido.

Este etiquetado del lado del cliente tiene un retraso mínimo para los documentos porque la etiqueta se puede aplicar incluso antes de que se guarde el documento. Sin embargo, no todas las aplicaciones cliente son compatibles con el etiquetado automático. Esta funcionalidad es compatible con el cliente de etiquetado unificado de Azure Information Protection y algunas [versiones de aplicaciones de Office.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Para obtener instrucciones de configuración, [vea How to configure auto-labeling for Office apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Para la privacidad de datos, se aplican automáticamente etiquetas de confidencialidad para el contenido que contiene información personal confidencial.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Etiquetado automático del lado del servicio cuando el contenido ya está guardado

Este método se conoce como clasificación automática con etiquetas de confidencialidad. También puede oir que se conoce como etiquetado automático de datos en reposo (para documentos en SharePoint y OneDrive) y datos en tránsito (para correo electrónico enviado o recibido por Exchange). Para Exchange, no incluye correos electrónicos en buzones en reposo.
 
Dado que este etiquetado se aplica por el propio servicio en lugar de por la aplicación de usuario, no es necesario preocuparse por las aplicaciones que tienen los usuarios y qué versión. Por lo tanto, esta funcionalidad está disponible inmediatamente en toda la organización y es adecuada para aplicar las etiquetas a cualquier escala. Las directivas de etiquetado automático no admiten el etiquetado recomendado, ya que el usuario no interactúa con el proceso de etiquetado. En su lugar, el administrador ejecuta las directivas en el modo de simulación para ayudarle a garantizar el etiquetado correcto del contenido antes de aplicar la etiqueta.

Para obtener instrucciones de configuración, [vea How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

Para la privacidad de datos dentro de los sitios de interés, presione etiquetas de confidencialidad para el cifrado automático del contenido que contiene información personal confidencial.

## <a name="data-loss-prevention"></a>Prevención de pérdida de datos 

Puede usar la prevención de pérdida de datos [(DLP)](../compliance/data-loss-prevention-policies.md) en Microsoft 365 para detectar, advertir y bloquear el uso compartido peligroso, involuntario o inadecuado, como el uso compartido de datos que contienen información personal, tanto interna como externamente.

DLP le permite:

- Identificar y supervisar actividades de uso compartido arriesgadas.
- Educar a los usuarios con instrucciones en contexto para tomar las decisiones correctas.
- Aplicar directivas de uso de datos sobre el contenido sin inhibir la productividad.
- Integre con clasificación y etiquetado para detectar y proteger los datos cuando se comparten.

### <a name="supported-workloads-for-dlp"></a>Cargas de trabajo admitidas para DLP

Con una directiva DLP en el Centro de cumplimiento de Microsoft 365, puede identificar, supervisar y proteger automáticamente elementos confidenciales en muchas ubicaciones de Microsoft 365, como Exchange Online, SharePoint, OneDrive y Microsoft Teams.

Por ejemplo, puede identificar cualquier documento que contenga un número de tarjeta de crédito almacenado en cualquier sitio de OneDrive o puede supervisar solo los sitios de OneDrive de personas específicas.

También puede supervisar y proteger elementos confidenciales en las versiones instaladas localmente de Excel, PowerPoint y Word, que incluyen la capacidad de identificar elementos confidenciales y aplicar directivas DLP. DLP proporciona supervisión continua cuando las personas comparten contenido de estas aplicaciones de Office.

![Cargas de trabajo admitidas para DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

En esta figura se muestra un ejemplo de DLP que protege los datos personales.

![Ejemplo de protección de datos personales con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP se usa para identificar un documento o correo electrónico que contiene un registro de mantenimiento y, a continuación, bloquea automáticamente el acceso a ese documento o bloquea el envío del correo electrónico. A continuación, DLP notifica al destinatario con una sugerencia de directiva y envía una alerta al usuario final y al administrador.

### <a name="planning-for-dlp"></a>Planeación de DLP

Planee las directivas dlp para: 

- Requisitos empresariales.

- Una evaluación basada en riesgos de la organización, tal como se describe en el artículo evaluar los riesgos de privacidad de datos [e identificar elementos confidenciales.](information-protection-deploy-assess.md)

- Otros mecanismos de protección de la información y gobierno en su lugar o en la planeación de la privacidad de datos.

- Los tipos de información confidencial que ha identificado para los datos personales en función del trabajo de evaluación que se describe en el artículo evaluar los riesgos de privacidad de datos e [identificar elementos confidenciales](information-protection-deploy-assess.md). Las condiciones de directiva DLP pueden basarse en tipos de información confidencial y etiquetas de retención.

- Las etiquetas de retención que necesitarás para especificar condiciones DLP. Vea el [artículo sobre la información de](information-protection-deploy-govern.md) gobierno sujeta a la regulación de privacidad de datos en su organización para obtener más información.

- Administración continua de directivas DLP, que requiere que alguien de la organización funcione y ajuste las directivas para los cambios en tipos de información confidencial, etiquetas de retención, reglamentos y directivas de cumplimiento.

Aunque las etiquetas de confidencialidad no se pueden usar en condiciones de directiva DLP, ciertos escenarios de protección para impedir el acceso pueden lograrse con solo etiquetas de confidencialidad que se pueden aplicar automáticamente en función de tipos de información confidencial. Si hay un etiquetado de confidencialidad sólido, considere si DLP debe usarse para aumentar la protección porque:

  - DLP puede impedir el uso compartido de archivos. Las etiquetas de confidencialidad solo pueden impedir el acceso.

  - DLP tiene niveles de control más granulares en términos de reglas, condiciones y acciones.

  - Las directivas DLP se pueden aplicar al chat y los mensajes de canal de Teams. Las etiquetas de confidencialidad solo se pueden aplicar a documentos y correo electrónico.


### <a name="dlp-policies"></a>Directivas DLP

Las directivas DLP se configuran en el Centro de administración de Cumplimiento de Microsoft y especifican el nivel de protección, el tipo de información confidencial que está buscando la directiva y las cargas de trabajo de destino. Sus componentes básicos consisten en identificar la protección y los tipos de datos.

![Configuración de directivas DLP en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

A continuación se muestra una directiva DLP de ejemplo para conocer el RGPD.

![Ejemplo de directiva DLP para el reconocimiento del RGPD](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Vea [este artículo para](../compliance/create-test-tune-dlp-policy.md) obtener más información sobre cómo crear y aplicar directivas DLP.

### <a name="protection-levels-for-data-privacy"></a>Niveles de protección para la privacidad de datos

En la tabla siguiente se enumeran tres configuraciones de aumento de la protección mediante DLP.

![Niveles de protección de privacidad de datos con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

La primera configuración, Awareness, se puede usar como punto de partida y nivel mínimo de protección para satisfacer las necesidades de cumplimiento de las normativas de privacidad de datos.

>[!Note]
>A medida que aumenten los niveles de protección, la capacidad de los usuarios para compartir y acceder a la información disminuirá en algunos casos y podría afectar su productividad o capacidad para completar tareas diarias.
>

To help your employees continue to be productive in a more secure environment when increasing protection levels, take the time to train and educate them on new security policies and procedures.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Ejemplo de uso de etiquetas de confidencialidad con DLP

Las etiquetas de confidencialidad pueden funcionar junto con DLP para proporcionar privacidad de datos en un entorno altamente regulado. Estos son los pasos clave de la implementación integrada:

1. Se documentan los requisitos normativos y empresariales para la privacidad de datos.
2. Los orígenes de datos de destino, los tipos y la propiedad se caracterizan por cuestiones de privacidad de datos.
3. Se establece una estrategia general para abordar los requisitos y proteger y regular los puntos de acceso a la privacidad de datos.
4. Se pone en marcha un plan de acción por fases para abordar la estrategia de control de privacidad de datos.

Una vez determinados estos elementos, puede usar los tipos de información confidencial, la taxonomía de etiquetado de confidencialidad y las directivas DLP juntas. En esta figura se muestra un ejemplo.

![Ejemplo de etiquetas de confidencialidad que funcionan con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Estos son algunos escenarios de protección de datos que usan dlp y etiquetas de confidencialidad juntos, como se muestra en la figura.

| Escenario | Proceso |
|:-------|:-----|
| A | <ol><li>Un administrador publica etiquetas de confidencialidad para contenido para usuarios y grupos para aplicaciones manuales o automáticas en el contenido y el correo electrónico. </li><li>El usuario A aplica las etiquetas de forma manual o automática al interactuar con el contenido, con el cifrado u otra configuración aplicada. </li><li>El usuario A envía un correo electrónico o archivo protegido al usuario B, un usuario invitado. </li></ol> |
| B | La directiva DLP publicada por un administrador en el usuario A impide que el usuario A envíe el correo electrónico o el archivo al usuario B. |
| C |  La etiqueta de confidencialidad con la configuración "el propietario no puede invitar invitados" se publica en el usuario A, que aprovisiona un equipo de Teams o un sitio de SharePoint. Otro usuario del sitio intenta compartir selectivamente un archivo con el usuario B, pero DLP lo bloquea. |
| D | La etiqueta de confidencialidad para la aplicación automática al contenido del sitio se publica en uno o varios sitios, lo que proporciona otra capa de protección, lo que da como resultado un sitio protegido. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Nuevas funcionalidades de cifrado de mensajes (OME) de Office 365

Las personas suelen usar el correo electrónico para intercambiar elementos confidenciales, como información de salud del paciente o información de clientes y empleados. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Con [OME,](../compliance/ome.md)puede enviar y recibir mensajes cifrados entre personas dentro y fuera de la organización. OME funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. OME ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Para la privacidad de datos, se usa OME para proteger los mensajes internos que contienen elementos confidenciales. Cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS) que forma parte de Azure Information Protection. Esto incluye directivas de cifrado, identidad y autorización para ayudar a proteger el correo electrónico. Puede cifrar mensajes mediante plantillas de administración de derechos, la opción No reenviar y la opción de solo cifrado.

También puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico, o que contenga palabras clave específicas en la línea de asunto, y también especifique que los destinatarios no pueden copiar ni imprimir el contenido del mensaje.

Además, el cifrado avanzado de mensajes de [OME](../compliance/ome-advanced-message-encryption.md) le ayuda a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a correos electrónicos cifrados. Con el cifrado de mensajes avanzado de OME en Microsoft 365, puede controlar correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que detectan tipos de información confidencial. 

Para la privacidad de datos, si necesita compartir correo electrónico con un tercero externo, puede especificar una fecha de expiración y revocar mensajes. Solo puede revocar y establecer una fecha de expiración para los mensajes enviados a destinatarios externos.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Comparación de escenarios de correo electrónico seguro con etiquetas de confidencialidad y OME

Las etiquetas de confidencialidad y OME aplicadas al correo electrónico con cifrado tienen cierta superposición, por lo que es importante comprender a qué escenarios se pueden aplicar, como se muestra en esta tabla.

| Escenario | Etiquetas de confidencialidad | OME |
|:-------|:-----|:-------|
| Interno + partners <br> Comunicarse y colaborar de forma segura entre usuarios internos y socios de confianza | Recomendamos: etiquetas con clasificación y protección totalmente personalizadas | Sí: cifrar solo o no reenviar la protección sin clasificación |
| Partes externas <br> Comunicarse y colaborar de forma segura con cualquier usuario externo o consumidor | Sí: predefine a los destinatarios en la etiqueta | Recomendado: protección just-in-time basada en destinatarios |
| Interno + partners, con expiración/revocación <br> Controlar el acceso de correo y contenido con usuarios internos y socios de confianza con expiración y revocación | Recomendado: protección totalmente personalizada con duración de acceso, el usuario puede realizar un seguimiento manual y revocar archivos | No: no hay revocación o expiración para el correo interno |
| Partes externas con expiración/revocación <br> Controlar el acceso de correo y contenido con usuarios externos/consumidores con caducidad y revocación | Sí: el usuario puede realizar un seguimiento manual de los archivos | Recomendado (E5): el administrador puede revocar el correo del Centro de seguridad & cumplimiento |
| Etiquetado automático <br> La organización quiere proteger automáticamente el correo o los datos adjuntos con contenido confidencial específico o con destinatarios específicos | Recomendado (E5): etiquetado automático en clientes de Exchange y Outlook, aumenta las reglas de flujo de correo y la directiva DLP | Sí: reglas de flujo de correo y directiva DLP con solo cifrar o no reenviar protección |
||||

También habrá diferencias en las experiencias de usuario final y administrador entre estos dos métodos.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams con protección para datos altamente confidenciales

Para las organizaciones que planean almacenar datos personales sujetos a las regulaciones de privacidad de datos en Teams, vea [Configure a team with security isolation](secure-teams-security-isolation.md), que proporciona instrucciones detalladas y pasos de configuración para:

- Acceso de dispositivos e identidades
- Creación de un equipo privado
- Bloqueo de permisos de sitio de grupo subyacentes
- Una etiqueta de confidencialidad basada en grupos con cifrado