---
title: Proteger la información sujeta a la normativa de privacidad de datos
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
description: Implemente las características de seguridad y cumplimiento de Microsoft 365 y proteja su información personal.
ms.openlocfilehash: 97c34ca236ea4be98b9412518788630732259d5a
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377156"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger la información sujeta a la normativa de privacidad de datos

Se pueden usar varios controles de protección de la información en su suscripción para ayudar a satisfacer las necesidades y regulaciones de cumplimiento normativo de privacidad de datos. Entre estos se incluyen el Reglamento General de protección de datos (RGPD), HIPAA-up (la ley de privacidad de atención médica de Estados Unidos), la ley de protección del consumidor de California (CCPA) y la ley de protección de datos de Brasil (LGPD).

Estos controles se encuentran en las siguientes áreas de solución:

- Etiquetas de confidencialidad
- Prevención de pérdida de datos (DLP)
- Cifrado de mensajes de Office (OME)
- Controles de acceso de Microsoft Teams y sitios

![Servicios clave para proteger la información personal sujeta a la normativa de privacidad de datos](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Esta solución describe las características de seguridad y cumplimiento para proteger la información sujeta a las regulaciones de privacidad de datos. Para obtener una lista completa de las características de seguridad de Microsoft 365, consulte la [documentación de seguridad 365 de Microsoft](https://docs.microsoft.com/microsoft-365/security/). Para obtener una lista completa de las características de cumplimiento de Microsoft 365, consulte la [documentación de cumplimiento de 365 de Microsoft](https://docs.microsoft.com/microsoft-365/compliance/).
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Regulaciones de privacidad de datos que afectan a los controles de protección de la información

A continuación se muestra una lista de ejemplo de normas de privacidad de datos que pueden estar relacionadas con los controles de protección de la información:

- RGPD apartado 1 del artículo 5 (f))
- Artículo de RGPD (32) (1) (a)
- Artículo 46 de LGPD
- HIPAA-tecnología (45 CFR 164.312 (e) (1))
- HIPAA-TECNOLOGÍA (45 C.F.R. 164.312 (e) (2) (II))

Para obtener más información sobre cada uno de los elementos anteriores, consulte el [artículo evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md) .

Las normas de privacidad de datos para la protección de información recomiendan:

- Protección contra la pérdida o el acceso no autorizado, el uso o la transmisión.
- Aplicación basada en riesgos de mecanismos de protección.
- Uso de cifrado cuando proceda.

Es posible que su organización también desee proteger el contenido de Microsoft 365 para otros fines, como otras necesidades de cumplimiento o motivos empresariales. El establecimiento de un esquema de protección de la información para la privacidad de los datos debe realizarse como parte de la planeación, implementación y administración de la protección de la información general.

Para ayudarle a empezar con un esquema de protección de la información en Microsoft 365, en la siguiente sección se incluye una breve lista de las capacidades relacionadas y las acciones de mejora para Microsoft 365. La lista incluye las capacidades y acciones de mejora que se aplican a las regulaciones de privacidad de datos. Sin embargo, la lista no incluye tecnologías más antiguas si hay una funcionalidad más nueva que reemplaza en gran medida al anterior. Por ejemplo, Information Rights Management (IRM) para SharePoint y OneDrive no se incluyen en la lista, pero se incluyen las etiquetas de confidencialidad.

## <a name="managing-information-protection-in-microsoft-365"></a>Administración de la protección de la información en Microsoft 365

Las [soluciones de protección](../compliance/protect-information.md) de la información de Microsoft incluyen varias capacidades integradas en Microsoft 365, Microsoft Azure y Microsoft Windows. En Microsoft 365, las soluciones de protección de la información incluyen:

- [Cifrado de servicio con clave de cliente](../compliance/customer-key-overview.md)
- [Tipos de información confidencial](../compliance/what-the-sensitive-information-types-look-for.md) (descritos en el [artículo evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md))
- [Etiquetas de confidencialidad](../compliance/sensitivity-labels.md) 
  - Nivel de servicio/contenedor
  - Cliente/nivel de contenido
  - Automatizada para datos en reposo en SharePoint y OneDrive
- Prevención de pérdida de datos (DLP)
- [Prevención de pérdida de datos de Microsoft 365 Endpoint (versión preliminar)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Cifrado de mensajes de Office 365 nuevas funciones (OME)](../compliance/ome.md) y OME [cifrado de mensajes avanzado](../compliance/ome-advanced-message-encryption.md)

Además, la protección a nivel de sitio y biblioteca son mecanismos importantes para incluir en cualquier esquema de protección.

Para obtener información sobre otras capacidades de protección de la información fuera de Microsoft 365, consulte:

- [Seguridad de aplicaciones en la nube de Microsoft (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Las etiquetas de confidencialidad de Microsoft Information Protection Framework le permiten clasificar y proteger los datos de su organización sin obstaculizar la productividad de los usuarios y su capacidad de colaborar.

![Etiquetas de confidencialidad en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Requisitos previos para las etiquetas de confidencialidad

Complete estas actividades antes de implementar cualquiera de las capacidades basadas en etiquetas de sensibilidad resaltadas a continuación:

1. Comprenda lo siguiente:
   - **Requisitos empresariales.** Establezca los motivos empresariales para aplicar las etiquetas de confidencialidad en su empresa. Por ejemplo, sus requisitos de privacidad de datos para la protección de la información.
   - **Capacidades de la etiqueta de confidencialidad.** La etiqueta de confidencialidad puede llegar a ser compleja, por lo que debe asegurarse de leer la documentación de las [etiquetas de confidencialidad](../compliance/sensitivity-labels.md) antes de empezar.
   - **Puntos clave que se deben recordar** Las etiquetas de confidencialidad se administran en el centro de administración de cumplimiento de Microsoft, pero las opciones de aplicación y de destino varían significativamente.
      - Hay etiquetas de confidencialidad para sitios, grupos y equipos en el nivel de contenedor (la configuración no se aplica al contenido dentro del contenedor). Se publican para los usuarios y grupos que los aplican cuando se aprovisiona un sitio, grupo o equipo.
      - Hay etiquetas de sensibilidad para el contenido activo. También se publican en usuarios o grupos, que los aplican manualmente, o se aplican automáticamente cuando:
        - El archivo se abre/modifica o guarda, ya sea en el escritorio del usuario o en un sitio de SharePoint.
        - Se ha enviado un correo electrónico y está redactado.
      - Hay etiquetas de confidencialidad para la aplicación automática en archivos en reposo en SharePoint y OneDrive, además de los mensajes de correo electrónico en tránsito a través de Exchange. Estos se dirigen a todos los sitios o a unos específicos y se aplican automáticamente a los archivos en reposo en estos entornos.

2. Racionalizar la etiqueta de confidencialidad actual con métodos anteriores o alternativos

   - Azure Information Protection

      Es posible que el esquema de etiquetado de sensibilidad actual deba reconciliarse con cualquier implementación existente de etiquetas de [Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) .
   - OME

      Si está pensando en usar la etiqueta de confidencialidad moderna para la protección de correo electrónico y los métodos de cifrado de correo electrónico existentes como OME están en su ubicación, pueden coexistir, pero debe comprender los escenarios en los que se deben aplicar ambos. Consulte [Office 365 Message Encryption New Capabilities (OME)](#office-365-message-encryption-ome-new-capabilities), que incluye una tabla que compara la protección moderna de tipo de etiqueta de confidencialidad con la protección basada en OME.

3. Planee la integración en un esquema más amplio de protección de la información. Sobre la coexistencia con OME, se pueden usar las etiquetas de confidencialidad actuales como funciones de Microsoft 365 Data Loss Prevention (DLP) y Microsoft Cloud App Security. Consulte las [etiquetas de confidencialidad y Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) para lograr los objetivos de protección de la información relacionada con la privacidad de los datos.

4. Desarrollar un esquema de clasificación y control de la etiqueta de confidencialidad. Consulte [clasificación de datos y taxonomía de etiqueta de confidencialidad](https://aka.ms/dataclassificationwhitepaper).

### <a name="general-guidance"></a>Instrucciones generales

1. **Definición de esquema.** Antes de usar las capacidades técnicas para aplicar etiquetas y protección, trabaje en toda la organización para definir un esquema de clasificación. Es posible que ya tenga un esquema de clasificación, lo que hace que sea más fácil agregar datos personales. 
2. **Introducción.** Para empezar, decida el número y los nombres de las etiquetas que se van a implementar. Realice esta actividad sin preocuparse sobre qué tecnología usar y cómo se aplicarán las etiquetas. Aplique este esquema de forma universal en toda la organización, incluidos los datos que residen de forma local y en otros servicios en la nube.
3. **Recomendaciones adicionales** Al diseñar e implementar directivas, etiquetas y condiciones, tenga en cuenta las siguientes recomendaciones:

   - **Use el esquema de clasificación existente (si hay alguno).** Muchas organizaciones ya usan la clasificación de datos de alguna forma. Evalúe cuidadosamente el esquema de etiqueta existente y, si es posible, úselo tal cual. El uso de etiquetas familiares que reconozcan los usuarios finales impulsarán la adopción.
   - **Empiece con un poco.** No hay prácticamente ningún límite en el número de etiquetas que puede crear. Sin embargo, un gran número de etiquetas y subetiquetas puede ser una operación lenta.
   - **Usar escenarios y casos de uso.** Identifique los casos de uso comunes dentro de su organización y use escenarios derivados de la normativa de privacidad de datos a la que está sujeto. Compruebe si la configuración de etiquetas y clasificaciones previstas funcionará en la práctica.
   - **Pregunta cada solicitud de una nueva etiqueta.** ¿Cada escenario o caso de uso necesita realmente una nueva etiqueta o puede usar lo que ya tiene? Mantener el número de etiquetas en un mínimo mejora la adopción.
   - **Use subetiquetas para departamentos clave.** Algunos departamentos tendrán necesidades específicas que requieran etiquetas específicas. Defina estas etiquetas como subetiquetas de una etiqueta existente y considere la posibilidad de usar directivas de ámbito asignadas a grupos de usuarios en lugar de globalmente.
   - **Considere las directivas con ámbito.** Las directivas destinadas a subconjuntos de usuarios impedirán la sobrecarga de etiquetas. Una directiva con ámbito permite asignar etiquetas o subetiquetas específicas de roles o departamentos a solo los empleados que trabajan para ese departamento específico. 
   - **Use nombres de etiqueta significativos.** Intente no usar jerga, estándares o acrónimos como nombres de etiqueta. Intente usar nombres que se retengan con el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, AC, y HBI, considere nombres como no empresarial, público, general, confidencial y extremadamente confidencial.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Crear e implementar etiquetas de confidencialidad para sitios, grupos y equipos

Al crear [etiquetas de confidencialidad](../compliance/sensitivity-labels-teams-groups-sites.md) en el centro de cumplimiento de Microsoft 365, ahora puede aplicarlas a estos contenedores:

- Sitios de Microsoft Teams
- Microsoft 365 grupos (anteriormente grupos de Office 365)
- Sitios de SharePoint

Use la siguiente configuración de etiqueta para ayudar a proteger el contenido de estos contenedores:

- Privacidad (pública o privada) de los sitios de Microsoft Teams conectados a grupos de 365
- Acceso de usuarios externos
- Acceso desde dispositivos no administrados

Para la privacidad de los datos, para impedir el uso compartido externo de contenedores que se usarán para almacenar contenido con datos personales confidenciales, marque los archivos que contienen datos como privados y requiera dispositivos administrados.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Crear e implementar etiquetas de confidencialidad para el contenido

Las etiquetas de confidencialidad aplicadas a los archivos le permiten cifrar su contenido, aplicar marcas de agua al contenido y definir otros controles para el contenido de las aplicaciones de Office, incluidos Outlook y Office en la Web.

Cuando esté listo para empezar a proteger los datos de la organización con las etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Para obtener más información sobre el desarrollo de una taxonomía de clasificación, vea las notas del producto sobre la taxonomía de la [etiqueta de confidencialidad y la clasificación de datos](https://aka.ms/dataclassificationwhitepaper).
2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, es posible que desee que el contenido de sensibilidad menor (como una etiqueta "general") tenga solo un encabezado o pie de página aplicado, mientras que el contenido de sensibilidad más alto (como una etiqueta "confidencial") debe tener una marca de agua y tener habilitado el cifrado.
3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Se puede reutilizar una sola etiqueta. Se define una vez y, a continuación, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios.

Una vez que publique las etiquetas de confidencialidad del centro de cumplimiento de Microsoft 365, empezarán a aparecer en las [aplicaciones de Office](../compliance/sensitivity-labels-office-apps.md) para que los usuarios clasifiquen y protejan el contenido a medida que se crea o edita.

![Flujo de implementación de la etiqueta de confidencialidad en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Para la privacidad de los datos, se aplica manualmente una etiqueta de confidencialidad con cifrado y otras reglas a correo electrónico o contenido que contiene información personal confidencial.

>[!Note]
>Las etiquetas de confidencialidad con cifrado habilitado aplicado al correo electrónico tienen alguna funcionalidad superpuesta con OME. Vea [comparación de escenarios de correo electrónico seguro con OME y las etiquetas de confidencialidad](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels).

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Etiquetado automático del lado cliente cuando los usuarios editan documentos o redactan mensajes de correo electrónico

Al crear una etiqueta de confidencialidad, puede [asignarla automáticamente](../compliance/apply-sensitivity-label-automatically.md) al contenido, incluido el correo electrónico, cuando coincida con las condiciones especificadas.

La capacidad de aplicar automáticamente etiquetas de confidencialidad al contenido es importante por estos motivos:

- No es necesario enseñar a los usuarios cuándo usar cada una de las clasificaciones.
- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.

La etiqueta automática admite la recomendación de una etiqueta a los usuarios, así como la aplicación automática de una etiqueta. Pero en ambos casos, el usuario decide si acepta o rechaza la etiqueta, para ayudar a garantizar el etiquetado correcto del contenido.

Este etiquetado del lado del cliente tiene un retraso mínimo para los documentos porque la etiqueta se puede aplicar incluso antes de que se guarde el documento. Sin embargo, no todas las aplicaciones cliente son compatibles con el etiquetado automático. Esta funcionalidad es compatible con el cliente de etiquetación unificada de Azure Information Protection y [algunas versiones de aplicaciones de Office](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Para obtener instrucciones de configuración, consulte [How to Configure auto-Labeling for Office apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Para la privacidad de los datos, se aplican automáticamente etiquetas de sensibilidad para contenido que contiene información personal confidencial.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Etiquetado automático del servicio cuando ya se ha guardado el contenido

Este método se conoce como clasificación automática con etiquetas de confidencialidad. También es posible que escuche como etiquetado automático para datos en reposo (para documentos en SharePoint y OneDrive) y datos en tránsito (para el correo electrónico que se envía o recibe por Exchange). Para Exchange, no incluye los correos electrónicos en los buzones de correo en reposo.
 
Dado que esta etiqueta es aplicada por el propio servicio en lugar de por la aplicación de usuario, no tiene que preocuparse de qué aplicaciones tienen los usuarios y de la versión. Por lo tanto, esta funcionalidad está disponible inmediatamente en toda la organización y es adecuada para aplicar las etiquetas a cualquier escala. Las directivas de etiquetado automático no admiten el etiquetado recomendado, ya que el usuario no interactúa con el proceso de etiquetado. En su lugar, el administrador ejecuta las directivas en el modo de simulación para ayudarle a garantizar el etiquetado correcto del contenido antes de aplicar la etiqueta.

Para obtener instrucciones de configuración, consulte [How to Configure auto-Labeling Policies for SharePoint, OneDrive y Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

Para la privacidad de los datos en sitios de preocupación, las etiquetas de confidencialidad de inserción para el cifrado automático del contenido que contiene información personal confidencial.

## <a name="data-loss-prevention"></a>Prevención de pérdida de datos 

Puede usar [prevención de pérdida de datos (DLP)](../compliance/data-loss-prevention-policies.md) en Microsoft 365 para detectar, avisar y bloquear el uso compartido peligroso, inesperado o inadecuado, como el uso compartido de datos que contienen información personal, tanto de forma interna como externa.

DLP le permite:

- Identificar y supervisar las actividades de uso compartido de riesgos.
- Instruya a los usuarios con instrucciones en contexto para tomar las decisiones correctas.
- Aplicar directivas de uso de datos al contenido sin inhibir la productividad.
- Integre con la clasificación y etiquetado para detectar y proteger los datos cuando se compartan.

### <a name="supported-workloads-for-dlp"></a>Cargas de trabajo compatibles con DLP

Con una directiva DLP en el centro de cumplimiento de Microsoft 365, puede identificar, supervisar y proteger automáticamente los elementos confidenciales en varias ubicaciones de Microsoft 365, como Exchange Online, SharePoint, OneDrive y Microsoft Teams.

Por ejemplo, puede identificar cualquier documento que contenga un número de tarjeta de crédito que esté almacenado en cualquier sitio de OneDrive o puede supervisar solo los sitios de OneDrive de personas específicas.

También puede supervisar y proteger elementos confidenciales en las versiones instaladas localmente de Excel, PowerPoint y Word, que incluyen la capacidad de identificar elementos confidenciales y aplicar directivas de DLP. DLP proporciona supervisión continua cuando los usuarios comparten contenido de estas aplicaciones de Office.

![Cargas de trabajo compatibles con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

En esta figura se muestra un ejemplo de DLP que protege datos personales.

![Ejemplo de protección de datos personales con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP se usa para identificar un documento o correo electrónico que contiene un registro de mantenimiento y, a continuación, bloquea automáticamente el acceso a ese documento o bloquea el envío del correo electrónico. Después, DLP notifica al destinatario con una sugerencia de directiva y envía una alerta al usuario final y al administrador.

### <a name="planning-for-dlp"></a>Planeación de DLP

Planee las directivas de DLP para: 

- Los requisitos empresariales.

- Una evaluación basada en riesgos de la organización, tal y como se describe en el [artículo evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md).

- Otros mecanismos de control y protección de la información en su ubicación o planeación de la privacidad de los datos.

- Los tipos de información confidencial que ha identificado para los datos personales en función de su trabajo de evaluación, tal como se describe en el [artículo evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md). Las condiciones de la Directiva DLP se pueden basar en los tipos de información confidencial y las etiquetas de retención.

- Las etiquetas de retención que necesitará para especificar las condiciones de DLP. Para obtener más información, consulte la [información de control del tema sobre la privacidad de los datos en el artículo de la organización](information-protection-deploy-govern.md) .

- Administración de directivas DLP en curso, que requiere que alguien de la organización opere y ajuste las directivas para los cambios en los tipos de información confidencial, las etiquetas de retención, las regulaciones y las directivas de cumplimiento.

Aunque las etiquetas de confidencialidad no se pueden usar en las condiciones de la Directiva de DLP, es posible que se puedan obtener acceso a determinados escenarios de protección para evitar el acceso con las etiquetas de confidencialidad que se aplican automáticamente en función de los tipos de información confidencial. Si la etiqueta de confidencialidad es sólida, tenga en cuenta si debe usarse DLP para aumentar la protección porque:

  - DLP puede impedir el uso compartido de archivos. Las etiquetas de confidencialidad solo pueden impedir el acceso.

  - DLP tiene niveles de control más granulares en términos de reglas, condiciones y acciones.

  - Las directivas DLP se pueden aplicar a los mensajes de chat y de canal de Microsoft Teams. Las etiquetas de confidencialidad solo se pueden aplicar a documentos y correo electrónico.


### <a name="dlp-policies"></a>Directivas DLP

Las directivas DLP se configuran en el centro de administración de cumplimiento de Microsoft y especifican el nivel de protección, el tipo de información confidencial que busca la Directiva y las cargas de trabajo de destino. Los componentes básicos consisten en identificar la protección y los tipos de datos.

![Configuración de la Directiva DLP en Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

A continuación, se muestra un ejemplo de una directiva de DLP para conocer los RGPD.

![Ejemplo de directiva de DLP para conocer la RGPD](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Consulte [este artículo](../compliance/create-test-tune-dlp-policy.md) para obtener más información sobre cómo crear y aplicar directivas de DLP.

### <a name="protection-levels-for-data-privacy"></a>Niveles de protección para la privacidad de datos

En la tabla siguiente se enumeran tres configuraciones para aumentar la protección con DLP.

![Niveles de protección de la privacidad de datos con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

La primera configuración, reconocimiento, puede usarse como punto de partida y nivel mínimo de protección para satisfacer las necesidades de cumplimiento de las regulaciones de privacidad de datos.

>[!Note]
>A medida que aumenta el nivel de protección, la capacidad de los usuarios para compartir y obtener acceso a la información disminuirá en algunos casos y podría afectar potencialmente a su productividad o a la capacidad para completar las tareas diarias.
>

Para ayudar a sus empleados a seguir siendo productivos en un entorno más seguro al aumentar los niveles de protección, dedique tiempo a entrenarlos y a darles a conocer los nuevos procedimientos y directivas de seguridad.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Ejemplo de uso de las etiquetas de confidencialidad con DLP

Las etiquetas de confidencialidad pueden funcionar junto con DLP para proporcionar privacidad de datos en un entorno altamente regulado. Estos son los pasos clave de la implementación integrada:

1. Se documentan los requisitos normativos y de negocio para la privacidad de los datos.
2. Los orígenes de datos, tipos y propiedad de destino se caracterizan con respecto a las preocupaciones sobre privacidad de los datos.
3. Se establece una estrategia general para abordar los requisitos y proteger y controlar las zonas Wi-Fi de privacidad de datos.
4. Se ha puesto en marcha un plan de acción escalonada para tratar la estrategia de control de privacidad de datos.

Una vez que se determinan estos elementos, puede usar los tipos de información confidencial, la taxonomía de etiquetado de confidencialidad y las directivas de DLP en conjunto. En esta figura se muestra un ejemplo.

![Ejemplo de etiquetas de sensibilidad que funcionan con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

A continuación, se muestran algunos escenarios de protección de datos que usan las DLP y las etiquetas de confidencialidad, como se muestra en la figura.

| Escenario | Proceso |
|:-------|:-----|
| A | <ol><li>Las etiquetas de confidencialidad de contenido las publica un administrador a los usuarios y grupos para la aplicación manual o automática a contenido y correo electrónico. </li><li>El usuario A aplica las etiquetas de forma manual o automática al interactuar con el contenido, aplicando cifrado u otras opciones de configuración. </li><li>El usuario A envía un correo electrónico protegido o un archivo al usuario B, un usuario Guest. </li></ol> |
| B | La Directiva DLP publicada por un administrador al usuario a impide que el usuario a envíe el correo electrónico o el archivo al usuario B. |
| C |  La etiqueta de confidencialidad con la configuración "el propietario no puede invitar a los invitados" se publica en el usuario A, que aprovisiona un equipo de Teams o un sitio de SharePoint. Otro usuario del sitio intenta de forma selectiva compartir un archivo con el usuario B, pero DLP lo bloquea. |
| D | La etiqueta de confidencialidad para la aplicación automática en el contenido del sitio se publica en uno o varios sitios, lo que proporciona otro nivel de protección, lo que resulta en un sitio protegido. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 de cifrado de mensajes (OME) nuevas capacidades

Los usuarios suelen usar el correo electrónico para intercambiar elementos confidenciales, como información de salud del paciente o información de clientes y empleados. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes.

Con [OME](../compliance/ome.md), puede enviar y recibir mensajes cifrados entre usuarios de dentro y fuera de la organización. OME funciona con Outlook.com, Yahoo!, gmail y otros servicios de correo electrónico. OME ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes.

Para la privacidad de los datos, use OME para proteger los mensajes internos que contengan elementos confidenciales. El cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS), que forma parte de Azure Information Protection. Esto incluye directivas de cifrado, identidades y autorización para ayudar a proteger el correo electrónico. Puede cifrar mensajes mediante el uso de plantillas de Rights Management, la opción no reenviar y la opción de solo cifrado.

También puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico, o que contenga palabras clave específicas en la línea de asunto, y también especificar que los destinatarios no pueden copiar ni imprimir el contenido del mensaje.

Además, el [cifrado de mensajes avanzado](../compliance/ome-advanced-message-encryption.md) de OME le ayuda a cumplir con las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a los correos electrónicos cifrados. Con OME cifrado de mensajes avanzado en Microsoft 365, puede controlar los mensajes de correo electrónico confidenciales que se compartan fuera de la organización con directivas automáticas que detecten tipos de información confidencial. 

Para la privacidad de los datos, si necesita compartir el correo electrónico con una entidad externa, puede especificar una fecha de expiración y revocar los mensajes. Solo puede revocar y establecer una fecha de caducidad para los mensajes enviados a destinatarios externos.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Escenarios de correo electrónico seguro comparación con OME y las etiquetas de confidencialidad

Los OME y las etiquetas de confidencialidad que se aplican al correo electrónico con cifrado se superponen, por lo que es importante comprender los escenarios a los que se puede aplicar, como se muestra en esta tabla.

| Escenario | Etiquetas de confidencialidad | OME |
|:-------|:-----|:-------|
| Partners internos + <br> Comunicarse y colaborar de forma segura entre usuarios internos y asociados de confianza | Recomendación: etiquetas con clasificación completamente personalizada y protección | Sí: cifrar solo o no reenviar la protección sin clasificación |
| Entidades externas <br> Comunicarse de forma segura y colaborar con cualquier usuario externo o de consumidor | Sí: los destinatarios predefinidos en la etiqueta | Recomendación: protección Just-in-Time basada en destinatarios |
| Asociados + internos, con expiración/revocación <br> Controlar el acceso al correo electrónico y el contenido con usuarios internos y asociados de confianza con expiración y revocación | Recomiende-protección completamente personalizada con duración de acceso, el usuario puede realizar un seguimiento y revocar archivos manualmente | No: no hay revocación ni expiración para el correo interno |
| Entidades externas con caducidad/revocación <br> Controlar el acceso al correo electrónico y el contenido con usuarios externos o de consumo con caducidad y revocación | Sí, el usuario puede realizar un seguimiento de los archivos manualmente | Recomendar (e5): el administrador puede revocar el correo del centro de seguridad & cumplimiento |
| Etiquetado automático <br> La organización desea proteger automáticamente el correo y los datos adjuntos con contenido confidencial específico o destinatarios específicos | Recomendación (e5): etiquetado automático en los clientes de Exchange y Outlook, aumenta las reglas de flujo de correo y la Directiva DLP | Reglas de flujo de correo de sí y Directiva de DLP con protección sólo cifrada o no reenvío |
||||

También habrá diferencias en las experiencias de usuario final y de administrador entre estos dos métodos.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams con protección para datos muy confidenciales

Para las organizaciones que planean almacenar datos personales sujetos a las leyes de privacidad de datos en Teams, vea [Configure a Team with Security Isolation](secure-teams-security-isolation.md), que proporciona instrucciones detalladas y pasos de configuración para:

- Acceso de dispositivos e identidades
- Creación de un equipo privado
- Bloqueo de permisos de sitio de grupo subyacentes
- Una etiqueta de confidencialidad basada en grupos con cifrado
