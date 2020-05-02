---
title: Información sobre las etiquetas de confidencialidad
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Use las etiquetas de confidencial del marco de Microsoft Information Protection para clasificar y proteger los datos de la organización, a la vez que se asegura de que la productividad de los usuarios y su capacidad de colaboración no se vean obstaculizadas. Estas etiquetas pueden aplicar la configuración de protección, que incluye marcadores visuales de cifrado como pies de página y marcas de agua.
ms.openlocfilehash: d31faa5dde212060f5e7b3c075cf4bc6fb3bef5f
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957310"
---
# <a name="learn-about-sensitivity-labels"></a>Información sobre las etiquetas de confidencialidad

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para realizar su trabajo, las personas de su organización colaboran con otras tanto dentro como fuera de la organización. Esto significa que el contenido ya no se queda detrás de un firewall, sino que puede desplazarse a todas partes, a través de dispositivos, aplicaciones y servicios. Y cuando se desplaza, usted quiere que lo haga de una forma segura y protegida que cumpla con las directivas empresariales y de cumplimiento de normas de su organización.

Las etiquetas de confidencial del marco de Microsoft Information Protection le permiten clasificar y proteger los datos de la organización, a la vez que se asegura de que no se obstaculice la productividad de los usuarios y su capacidad de colaboración.

Ejemplo que muestra las etiquetas de confidencialidad disponibles en Excel, en la pestaña **Inicio** de la cinta de opciones. En este ejemplo, la etiqueta aplicada se muestra en la barra de estado:

![Etiqueta de sensibilidad en la barra de herramientas de Excel y en la barra de estado](../media/Sensitivity-label-in-Excel.png)

Las etiquetas de confidencialidad sólo se admiten para los espacios empresariales en la nube global (pública). Actualmente, las etiquetas de compatibilidad no son compatibles con los espacios empresariales de otras nubes, como las[nubes nacionales](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud).

> [!NOTE]
> Las etiquetas de confidencialidad todavía no están disponibles en la Government Community (GCC) de EE. UU.

Para aplicar etiquetas de confidencialidad, los usuarios tienen que haber iniciado sesión en Office con su cuenta profesional o educativa.

Puede usar etiquetas de confidencialidad para:
  
- **Aplicar opciones de protección como encriptación o marcas de agua en el contenido etiquetado.** Por ejemplo, los usuarios pueden aplicar una etiqueta Confidencial a un documento o correo electrónico, y esa etiqueta puede encriptar el contenido y aplicar una marca de agua Confidencial.

- **Proteger el contenido de las aplicaciones de Office en distintos dispositivos y plataformas.** Para obtener una lista de aplicaciones compatibles, vea [Uso de etiquetas de confidencialidad en aplicaciones de Office](sensitivity-labels-office-apps.md).

- ** Proteger el contenido en los servicios y aplicaciones de terceros ** con Microsoft Cloud App Security Con Cloud App Security, puede detectar, clasificar, etiquetar y proteger el contenido en los servicios y aplicaciones de terceros, como SalesForce, Box o Dropbox, incluso si la aplicación o servicio de terceros no puede leer o no tiene compatibilidad con etiquetas de confidencialidad.

- **Extienda las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.** Con el SDK de la protección de la información de Microsoft, las aplicaciones de terceros pueden leer etiquetas de confidencialidad y aplicar configuraciones de protección.

- **Clasificar contenido sin usar una configuración de protección.** También puede asignar una clasificación al contenido (como un adhesivo) que se adhiera y traslade con el contenido cuando se use y comparta. Puede usar esta clasificación para crear informes de uso y ver los datos de actividad de contenido confidencial. También puede usar esta información para aplicar la configuración de protección más adelante.

En todos estos casos, las etiquetas de confidencialidad de Microsoft 365 pueden ayudarle a realizar las acciones correctas en el contenido adecuado. Con las etiquetas de confidencialidad, puede clasificar los datos en toda la organización, y aplicar la configuración de protección en función de dicha clasificación.

## <a name="what-a-sensitivity-label-is"></a>Qué es una etiqueta de confidencialidad

Cuando asigna una etiqueta de confidencialidad a un documento o correo electrónico, es como un sello que se aplica al contenido que:

- **Es personalizable. ** Puede crear categorías para distintos niveles de contenido confidencial en su organización, como Personal, Público, General, Confidencial y Extremadamente confidencial.

- **Texto no cifrado.** Debido a que la etiqueta se almacena en texto no cifrado en los metadatos del contenido, las aplicaciones y servicios de terceros pueden leerla y luego aplicar sus propias acciones de protección, si es necesario.

- **Persistente.** Después de aplicar una etiqueta de confidencialidad al contenido, la etiqueta se almacena en los metadatos de ese correo electrónico o documento. Esto significa que la etiqueta se desplaza con el contenido, incluyendo la configuración de protección, y estos datos se convierten en la base para aplicar y hacer cumplir las políticas.

En las aplicaciones de Office, una etiqueta de confidencialidad se muestra como una etiqueta para los usuarios en un correo electrónico o documento.

Cada elemento de contenido puede tener una única etiqueta de confidencialidad aplicada. Un elemento puede tener a la vez una única etiqueta de confidencialidad y una única [etiqueta de retención](labels.md) aplicadas.

> [!div class="mx-imgBorder"]
> ![Etiqueta de confidencialidad aplicada a un correo electrónico](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>Qué pueden hacer las etiquetas de confidencialidad

> [!NOTE]
> Además de aplicar etiquetas de confidencialidad a los mensajes de correo electrónico y documentos, actualmente en versión preliminar, también puede [usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md).

Después de aplicar una etiqueta de confidencialidad a un documento o correo electrónico, cualquier configuración de protección de la etiqueta se aplica en el contenido. Con una etiqueta de confidencialidad, puede:

- **Cifre** solo el correo electrónico o el correo electrónico y los documentos. Puede elegir qué usuarios o grupos tienen permisos para realizar las acciones y durante cuánto tiempo. Por ejemplo, puede elegir permitir que los usuarios de un grupo específico en otra organización tengan permisos para revisar el contenido solo 7 días después de que se haya marcado el contenido. Como alternativa, en lugar de permisos definidos por el administrador, puede permitir a los usuarios asignar permisos al contenido al aplicar la etiqueta. 
    
    Para obtener más información sobre la configuración de **Cifrado** cuando cree o edite una etiqueta de confidencialidad, vea [Restringir el acceso a contenido con el cifrado en etiquetas de confidencialidad](encryption-sensitivity-labels.md).

- **Marcar el contenido** cuando utilice las aplicaciones de Office, agregando marcas de agua, encabezados o pies de página a correos electrónicos o documentos que tengan aplicada la etiqueta. Las marcas de agua se pueden aplicar en documentos, pero no en mensajes de correo electrónico. Encabezado y marca de agua de ejemplo:
    
    ![Marca de agua y encabezado aplicados a un documento](../media/Sensitivity-label-watermark-header.png)
    
    ¿Necesita comprobar cuándo se aplican marcas de contenido? Consulte el artículo sobre [cuando Microsoft 365 aplica el marcado y el cifrado de contenido ](sensitivity-labels-office-apps.md#when-office-365-applies-content-marking-and-encryption).
    
    Longitudes de cadena: las marcas de agua están limitadas a 255 caracteres. Los encabezados y pies de página tienen un límite de 1024 caracteres, excepto en Excel. Excel tiene un límite total de 255 caracteres para encabezados y pies de página, pero este límite incluye caracteres que no son visibles, como códigos de formato. Si se alcanza ese límite, la cadena que escriba no se mostrará en Excel.


- **Proteja el contenido de los contenedores como sitios y grupos** cuando opta por la versión preliminar para [usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint (versión preliminar pública)](sensitivity-labels-teams-groups-sites.md).
    
    Las opciones de configuración para **configuración de sitio y de grupo** no se mostrarán hasta que opte por la versión preliminar. Tenga en cuenta que esta configuración de etiqueta no da como resultado que los documentos se etiqueten automáticamente, sino que la configuración de la etiqueta protege el contenido al controlar el acceso al contenedor donde se almacenan los documentos. Esta configuración incluye el nivel de privacidad, si un propietario de un grupo de Microsoft 365 puede agregar invitados al grupo y el nivel de acceso concedido a un dispositivo no administrado.

- **Aplicar la etiqueta automáticamente en aplicaciones de Office o recomendar una etiqueta.** Puede elegir qué tipos de información confidencial quiere etiquetar y la etiqueta se puede aplicar automáticamente, o bien puede solicitar a los usuarios que apliquen la etiqueta que recomiende usar. Si recomienda una etiqueta, el mensaje mostrará el texto que elija. Por ejemplo:
    
    ![Aviso para asignar una etiqueta necesaria](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    Para obtener más información sobre la configuración **Aplicación automática de etiquetas para aplicaciones de Office** al crear o editar una etiqueta de confidencialidad, vea [Aplicar automáticamente una etiqueta de confidencialidad al contenido](apply-sensitivity-label-automatically.md).

### <a name="label-priority-order-matters"></a>Prioridad de etiqueta (el orden importa)

Al crear las etiquetas de confidencialidad en el centro de administración, éstas aparecen en una lista en la pestaña **Confidencialidad** en la página de **Etiquetas**. En esta lista, el orden de las etiquetas es importante, ya que refleja su prioridad. Quiere que la etiqueta de confidencialidad más restrictiva, como la Extremadamente confidencial, aparezca en la **parte inferior** de la lista y la etiqueta de confidencialidad menos restrictiva, como la Pública, aparezca en la **parte superior**.

Puede aplicar una sola etiqueta de confidencialidad a un documento o correo electrónico. Si configura una opción que exige a los usuarios proporcionar una justificación para cambiar una etiqueta a una clasificación inferior, el orden de esta lista identifica las clasificaciones más bajas. Sin embargo, esta opción no se aplica a las subetiquetas.

Aunque, el orden de las subetiquetas se usa en el [ etiquetado automático](apply-sensitivity-label-automatically.md). Cuando configure etiquetas para aplicarlas automáticamente o como recomendación, pueden producirse varias coincidencias para más de una etiqueta. Para determinar la etiqueta que se va a aplicar o recomendar, se usa el orden de las etiquetas: se selecciona la última etiqueta de confidencialidad y, a continuación, si procede, la última subetiqueta.

![Opción para crear una subetiqueta](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Subetiquetas (agrupación de etiquetas)

Con las subetiquetas, puede agrupar una o varias etiquetas bajo una etiqueta principal que el usuario ve en la aplicación de Office. Por ejemplo, en Confidencial, su organización puede usar varias etiquetas distintas para determinados tipos dentro de esa clasificación. En este ejemplo, la etiqueta principal Confidencial es simplemente una etiqueta de texto sin ninguna configuración de protección y, como contiene subetiquetas, no se puede aplicar al contenido. En su lugar, los usuarios deben elegir Confidencial para ver las subetiquetas y, a continuación, pueden elegir una subetiqueta para que se aplique al contenido.

Las subetiquetas son simplemente una forma de presentar etiquetas a los usuarios en grupos lógicos. Las subetiquetas no heredan ninguna configuración de su etiqueta principal. Cuando publique una subetiqueta para un usuario, éste podrá aplicar dicha subetiqueta al contenido, pero no podrá aplicar solo la etiqueta principal.

No elija una etiqueta principal como predeterminada o configure una etiqueta principal para que se aplique automáticamente (o se recomiende). Si lo hace, la etiqueta principal no se aplicará al contenido.

Ejemplo de cómo se muestran las subetiquetas para los usuarios:

![Subetiquetas agrupadas en la cinta de opciones](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Modificar o eliminar una etiqueta de confidencialidad

Si elimina una etiqueta de confidencialidad del centro administración, la etiqueta no se quitará automáticamente del contenido, y cualquier configuración de protección se seguirá aplicando al contenido que tenía esa etiqueta aplicada.

Si edita una etiqueta de confidencialidad, la versión de la etiqueta que se aplicó al contenido es la que se aplica a ese contenido.

## <a name="what-label-policies-can-do"></a>Qué pueden hacer las directivas de etiqueta

Después de crear las etiquetas de confidencialidad, debe publicarlas para que estén disponibles para las personas y los servicios de su organización. Las etiquetas de confidencialidad se pueden aplicar a documentos y correos electrónicos. A diferencia de las etiquetas de retención, que se publican en ubicaciones como todos los buzones de Exchange, las etiquetas de confidencialidad se publican para los usuarios o los grupos. Las etiquetas de confidencialidad aparecerán en las aplicaciones de Office para esos usuarios y grupos.

Con una directiva de etiqueta, puede:

- **Elija qué usuarios y grupos ven las etiquetas.** Las etiquetas pueden publicarse para cualquier usuario específico o un grupo de seguridad activado por correo electrónico, un grupo de distribución o un grupo de Microsoft 365, que puede tener [suscripción dinámica](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) en Azure AD.

- **Aplicar una etiqueta predeterminada** a todos los nuevos documentos y correos electrónicos creados por los usuarios y grupos incluidos en la directiva de etiqueta. Esta opción también se aplica a los contenedores, si [habilita las etiquetas de confidencialidad para Microsoft Teams, los grupos de Microsoft 365 y los sitios de SharePoint](sensitivity-labels-teams-groups-sites.md). Los usuarios siempre pueden cambiar la etiqueta predeterminada si no es la etiqueta adecuada para su documento o correo electrónico. Considere utilizar una etiqueta predeterminada para establecer un nivel base de configuración de protección que desee aplicar a todo su contenido. Sin embargo, sin el aprendizaje del usuario y otros controles, esta configuración también puede dar como resultado una etiqueta incorrecta. 

- **Requerir una justificación para cambiar una etiqueta.** Si un usuario intenta quitar una etiqueta o reemplazarla por una etiqueta con un número de pedido inferior, puede solicitar que el usuario proporcione una justificación para realizar esa acción. Por ejemplo, un usuario abre un documento con la etiqueta Confidencial (número de pedido 3) y reemplaza dicha etiqueta por una llamada Público (número de pedido 1). Actualmente, el motivo de justificación no es enviado a [la etiqueta Analítica](label-analytics.md) para que el administrador pueda revisarla. No obstante, la [cliente de etiquetas unificada de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) envía esta información a [Azure Information Protection Analytics](https://docs.microsoft.com/azure/information-protection/reports-aip).

    ![Aviso en el que los usuarios especifican una justificación](../media/Sensitivity-label-justification-required.png)

- **Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos.** También conocido como etiqueta obligatoria, puede solicitar que se aplique una etiqueta para que los usuarios puedan guardar documentos y enviar correos electrónicos. Use esta opción para mejorar la cobertura de la etiqueta. El usuario puede asignar manualmente la etiqueta, automáticamente como resultado de una condición configurada, o bien puede asignarse de forma predeterminada (la opción de etiqueta predeterminada se ha indicado anteriormente). El aviso que se muestra en Outlook cuando se requiere que un usuario asigne una etiqueta:

    ![Aviso en Outlook donde se pide a un usuario que aplique una etiqueta necesaria](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > Las etiquetas obligatorias requieren una suscripción en Azure Information Protection. Para usar esta característica, debe instalar el [Cliente de etiquetado unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app). Este cliente solo se ejecuta en Windows, por lo que esta característica aún no se admite en Mac, iOS y Android.

- **Proporcione un vínculo de ayuda a una página de ayuda personalizada.** Si los usuarios no están seguros de lo que significan las etiquetas de confidencialidad o cómo deben usarse, puede proporcionar una URL con más información que aparecerá en la parte inferior del menú **Etiqueta de confidencialidad** en las aplicaciones de Office:

    ![Vínculo para obtener más información en la cinta o botón de confidencialidad](../media/Sensitivity-label-learn-more.png)

Después de crear una directiva de etiqueta que asigne etiquetas de confidencialidad a usuarios y grupos, espere hasta 24 horas para que estos usuarios puedan ver las etiquetas en las aplicaciones de Office.

No hay límite en el número de etiquetas de sensibilidad que puede crear y publicar, con una excepción: si la etiqueta aplica un cifrado, hay un máximo de 500 etiquetas. Sin embargo, como mejor práctica para reducir los gastos generales de administración y reducir la complejidad para sus usuarios, trate de mantener el número de etiquetas al mínimo. Las implementaciones de palabras reales han demostrado que la eficacia se reduce notablemente cuando los usuarios tienen más de cinco etiquetas principales o más de cinco subetiquetas por etiqueta principal.

### <a name="label-policy-priority-order-matters"></a>Prioridad de etiquetas de directivas (el orden importa)

Para que los usuarios dispongan de sus etiquetas de confidencialidad, puede publicarlas en una directiva de etiqueta de confidencialidad, que se muestra en una lista en la pestaña de **Directivas de confidencialidad** en la página **Directivas de etiqueta**. Al igual que las etiquetas de confidencialidad (consulte [la sección anterior](#label-priority-order-matters) (el orden importa)), el orden de las directivas de etiqueta de confidencialidad es importante, puesto que refleja su prioridad. La directiva de etiqueta de menor prioridad se muestra en la parte **superior**, mientras que la directiva de mayor prioridad se muestra en la parte **inferior**.

Una directiva de etiqueta consiste en lo siguiente:

- Un conjunto de etiquetas.
- El alcance de la directiva de etiqueta, es decir, los usuarios y grupos incluidos en la directiva.
- La configuración de la directiva de etiqueta arriba descrita (etiqueta predeterminada, justificación, etiqueta obligatoria y vínculo de ayuda).

Puede incluir un usuario en varias políticas de etiquetas, y el usuario verá todas las etiquetas de confidencialidad de esas políticas. Sin embargo, el usuario conseguirá las configuraciones de directiva solo de la directiva de etiqueta de mayor prioridad.

Si no ve la configuración de la etiqueta o la configuración de la misma que esperaba para un usuario o un grupo, y ha esperado 24 horas, compruebe el orden de las directivas de etiqueta de sensibilidad. Para cambiar el orden de las directivas de etiqueta, seleccione una directiva de etiqueta de carácter > seleccione los puntos suspensivos a la derecha > **Mover abajo** o **Mover arriba**.

![Opción Mover en la página de directivas de etiquetas de confidencialidad](../media/sensitivity-label-policy-priority.png)

Si usa las etiquetas de retención además de las etiquetas de confidencialidad, es importante que recuerde que la prioridad importa para las directivas de etiquetas de confidencialidad, pero no para las [directivas de etiqueta de retención](labels.md#the-principles-of-retention-or-what-takes-precedence).

## <a name="sensitivity-labels-and-azure-information-protection"></a>Etiquetas de confidencialidad y Azure Information Protection

Si ha implementado etiquetas con Azure Information Protection, utilice las secciones siguientes para obtener información sobre cómo empezar a usar las etiquetas de confidencialidad.

### <a name="azure-information-protection-labels"></a>Etiquetas de Azure Information Protection

> [!NOTE]
> La gestión de etiquetas para las etiquetas de Azure Information Protection en Microsoft Azure Portal quedará en desuso el **31 de marzo de 2021**. Más información en la página oficial [notificación de desuso](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

Si utiliza etiquetas de protección de información azul porque su inquilino aún no está en la[ plataforma de etiquetado unificado](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform), le recomendamos que evite crear etiquetas de confidencialidad hasta que active el etiquetado unificado. En este escenario, las etiquetas que se muestran en el Azure Portal son etiquetas de Azure Information Protection en lugar de etiquetas de confidencialidad. El cliente de Azure Information Protection (clásico) puede usar estas etiquetas en los equipos con Windows, pero no los dispositivos que ejecuten macOS, iOS o Android. Para resolver este problema, [migre estas etiquetas](/azure/information-protection/configure-policy-migrate-labels) a etiquetas de confidencialidad. 

Los metadatos aplicados por los dos conjuntos de etiquetas son compatibles, por lo que no es necesario volver a etiquetar documentos y correos electrónicos cuando se haya completado la migración.

### <a name="azure-information-protection-clients"></a>Clientes de Azure Information Protection

Cuando se usan etiquetas de confidencialidad en Aplicaciones de Microsoft 365 para empresas en equipos con Windows, tiene la opción de usar un cliente de Azure Information Protection o usar etiquetas integradas en Office.

De forma predeterminada, la etiqueta integrada está desactivada en estas aplicaciones cuando el cliente de Azure Information Protection está instalado. Para obtener más información, incluido cómo cambiar este comportamiento predeterminado, consulte [cliente de etiquetas integrado de Office y cliente de Azure Information Protection](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client).

Incluso si usa etiquetas integradas en las aplicaciones de Office, también puede usar el cliente de etiquetas Unificado de Azure Information Protection con etiquetas de confidencialidad para lo siguiente:

- Un escáner para detectar información confidencial almacenada localmente y, si quiere, etiquete el contenido

- Opciones de botón derecho en el explorador de archivos para que los usuarios puedan aplicar etiquetas a todos los tipos de archivo

- Un visor para mostrar archivos cifrados para texto, imágenes o documentos PDF

- Un módulo de PowerShell para detectar información confidencial en los archivos locales y aplicar o quitar las etiquetas y el cifrado de estos archivos.

Si no está familiarizado con Azure Information Protection, o si es un cliente de Azure Information Protection que acaba de migrar sus etiquetas, consulte [Elegir el cliente de etiquetas que se usará para los equipos Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) en la documentación de Azure Information Protection.

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a>Etiquetas de confidencialidad y Microsoft Cloud App Security

Cuando hace uso de Cloud App Security (CAS), puede detectar, clasificar, etiquetar y proteger el contenido en los servicios y aplicaciones de terceros, como por ejemplo SalesForce, Box o Dropbox. 

Cloud App Security funciona con las etiquetas mismas y las de confidencialidad de Azure Information Protection:

- Si los centros de administración de etiquetas tienen una o más etiquetas de confidencialidad [publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para al menos un usuario: se usan las etiquetas de confidencialidad.

- Si los centros de administración de etiquetas no tienen etiquetas de confidencialidad publicadas: se usan las etiquetas de Azure Information Protection.

Para obtener instrucciones sobre cómo usar Cloud App Security con estas etiquetas, consulte [Integración de Azure Information Protection](https://docs.microsoft.com/cloud-app-security/azip-integration).

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>Etiquetas de confidencialidad y el SDK de protección de la información de Microsoft

Como las etiquetas de sensibilidad se almacenan como texto sin formato en los metadatos de un documento, las aplicaciones y los servicios de terceros pueden leer y escribir en los metadatos de etiqueta para complementar la implementación de la etiqueta. Además, los desarrolladores de software pueden usar el [SDK de Microsoft Information Protection](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk) para admitir por completo las características de etiquetado y cifrado en varias plataformas. Para obtener más información, consulte el [anuncio de disponibilidad general en el blog de la comunidad tecnológica](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). 

También puede obtener más información sobre [las soluciones de asociados que se integran con la protección de la información de Microsoft](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="deployment-guidance"></a>Instrucciones de implementación

Consulte [Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md).

