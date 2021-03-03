---
title: Administrar etiquetas de confidencialidad en las aplicaciones de Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Información para que los administradores de TI administren etiquetas de confidencialidad en aplicaciones de Office para escritorio, móvil y web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1834e1071c56e03ef20ae0e87b63fc4c03a6921b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407310"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Administrar etiquetas de confidencialidad en las aplicaciones de Office

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Cuando ha [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) publicado etiquetas de confidencialidad desde el centro de cumplimiento de Microsoft 365 o el centro de etiquetado equivalente, comienzan a aparecer en aplicaciones de Office para que los usuarios clasifiquen y protejan los datos a medida que se crean o editan.

Use la información de este artículo para ayudarle a administrar correctamente las etiquetas de confidencialidad en las aplicaciones de Office. Por ejemplo, identifique las versiones mínimas de aplicaciones que necesita para admitir el etiquetado integrado y comprenda las interacciones con el cliente de etiquetado unificado de Azure Information Protection y la compatibilidad con otras aplicaciones y servicios.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de etiquetado para aplicaciones de escritorio

Para usar etiquetas de confidencialidad integradas en aplicaciones de escritorio de Office para Windows y Mac, debe usar una edición de suscripción de Office. Este cliente de etiquetado no admite ediciones independientes de Office, como Office 2016 u Office 2019.

Para usar etiquetas de confidencialidad con estas ediciones independientes de Office en equipos Windows, instale el cliente de etiquetado unificado [de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Compatibilidad con funcionalidades de etiquetas de confidencialidad en aplicaciones

Para cada funcionalidad, las tablas siguientes muestran la versión mínima de Office que necesita para admitir etiquetas de confidencialidad mediante el etiquetado integrado. O bien, si la funcionalidad de etiqueta está en versión preliminar pública o en revisión para una versión futura. Use la [guía básica de Microsoft 365](https://aka.ms/MIPC/Roadmap) para obtener más información sobre futuras versiones.

Las nuevas versiones de las aplicaciones de Office están disponibles en diferentes momentos para diferentes canales de actualización. Para obtener más información, incluido cómo configurar el canal de actualización para que pueda probar una nueva funcionalidad de etiquetado que le interesa, vea [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Las nuevas funcionalidades que están en versión preliminar privada no se incluyen en la tabla, pero es posible que pueda unirse a estas vistas previas nominando a su organización para el programa de vista previa privada [de Microsoft Information Protection](https://aka.ms/mip-preview).

> [!NOTE]
> Los nombres de los canales de actualización de las aplicaciones de Office han cambiado recientemente. Por ejemplo, El canal mensual ahora es Canal actual y Office Insider ahora es Canal beta. Para obtener más información, vea [Changes to update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/update-channels-changes).

Office para iOS y Office para Android: las etiquetas de confidencialidad están integradas en la [aplicación de Office.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Las funcionalidades adicionales están disponibles al instalar el cliente de etiquetado unificado de Azure Information Protection, que solo se ejecuta en equipos Windows. Para obtener más información, [consulta Comparar los clientes de etiquetado para equipos Windows.](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Capacidades de etiquetas de confidencialidad en Word, Excel y PowerPoint

Los números enumerados son la versión mínima de la aplicación de Office necesaria para cada funcionalidad.

|Funcionalidad                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, cambiar o quitar etiqueta manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Proporcionar vínculo de ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | En revisión |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | En revisión   | En revisión         | En revisión                                                        |
|[Introducción a la clasificación de datos](data-classification-overview.md) y envío de datos para administradores                      | 2011+ | 16.43+ | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider) | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider) | Sí <sup>\*</sup>                                                        |
|[Requerir que los usuarios apliquen una etiqueta a su correo electrónico y documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider)             | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider)         | En revisión   | Implementar: 16.0.13628+ | En revisión                                            
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Implementar: 16.44+ | En revisión | En revisión | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Compatibilidad con la co-autoría y autoguardado](sensitivity-labels-coauthoring.md) para documentos etiquetados y cifrados | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider) | Vista previa: [Canal beta](https://office.com/insider) | En revisión | En revisión | [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Nota al pie:**

<sup>\*</sup> Actualmente, no incluye texto de justificación para quitar una etiqueta o bajar el nivel de clasificación

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funcionalidades de etiquetas de confidencialidad en Outlook

Los números enumerados son la versión mínima de la aplicación de Office necesaria para cada funcionalidad.

|Funcionalidad                                                                                                        |Outlook para Windows |Outlook para Mac |Outlook en iOS |Outlook en Android |Outlook en la Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o quitar etiqueta manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Proporcionar vínculo de ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables)                                              | En revisión                     | En revisión                 | En revisión         | En revisión           | En revisión               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Requerir que los usuarios apliquen una etiqueta a su correo electrónico y documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Vista previa: [Canal actual (versión preliminar)](https://office.com/insider)                        | 16.43+ <sup>\*</sup>                    | En revisión            | En revisión                | Sí                |
|[Introducción a la clasificación de datos](data-classification-overview.md) y envío de datos para administradores                      | 2011+ | En revisión | En revisión           | En revisión               | En revisión |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | En revisión           | En revisión               | Sí |
|

**Nota al pie:**

<sup>\*</sup> Requiere el [nuevo Outlook para Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de etiquetado integrado de Office y otras soluciones de etiquetado

El cliente de etiquetado integrado de Office descarga etiquetas de confidencialidad y la configuración de directiva de etiquetas de confidencialidad de los siguientes centros de administración:

- Centro de cumplimiento de Microsoft 365
- Centro de seguridad de Microsoft 365
- Centro de seguridad y cumplimiento de Office 365

Para usar el cliente de etiquetado integrado de Office, debe tener una o más directivas de etiquetas publicadas para los usuarios de uno de los centros de administración enumerados y una versión compatible [de Office](#support-for-sensitivity-label-capabilities-in-apps). [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)

Si se cumplen ambas condiciones pero necesita desactivar el cliente de etiquetado integrado de Office, use la siguiente configuración de directiva de grupo:

1. Vaya a **Configuración de usuario/Plantillas administrativas/Microsoft Office 2016/Configuración de seguridad**.

2. Establecer **Usar la característica de confidencialidad en Office para aplicar y ver etiquetas de confidencialidad** en **0**. 
 
Implemente esta configuración mediante la directiva de grupo o mediante el servicio de directivas en la [nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). La configuración tiene efecto cuando se reinician las aplicaciones de Office.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de etiquetado integrado de Office y cliente de Azure Information Protection

Si los usuarios tienen uno de los clientes de Azure Information Protection[instalados](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) (cliente de etiquetado unificado o cliente [clásico),](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)de forma predeterminada, el cliente de etiquetado integrado se desactivará en sus aplicaciones de Office. 

Para usar el etiquetado integrado en lugar del cliente de Azure Information Protection para aplicaciones de Office, use las instrucciones de la sección anterior, pero establezca la configuración de directiva de grupo Use la característica de confidencialidad en **Office** para aplicar y ver etiquetas de confidencialidad en **1**. 

Como alternativa, deshabilite o quite el complemento de Office, **Azure Information Protection**. Este método es adecuado para un solo equipo y pruebas ad hoc. Para obtener instrucciones, [vea Ver, administrar e instalar complementos](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)en programas de Office. 

Al deshabilitar o quitar este complemento de Office, el cliente de Azure Information Protection permanece instalado para que pueda seguir etiquetando archivos fuera de las aplicaciones de Office. Por ejemplo, mediante el Explorador de archivos o PowerShell.

Para obtener información sobre qué características son compatibles con los clientes de Azure Information Protection y el cliente de etiquetado integrado de Office, vea Elegir qué cliente de etiquetado se usará para equipos [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) en la documentación de Azure Information Protection.

## <a name="office-file-types-supported"></a>Tipos de archivo de Office admitidos

Las aplicaciones de Office que tienen etiquetado integrado para archivos de Word, Excel y PowerPoint admiten el formato Open XML (como .docx y .xlsx), pero no el formato de Microsoft Office 97-2003 (como .doc y .xls), Formato de documento abierto (como .odt y .ods) u otros formatos. Cuando un tipo de archivo no es compatible  con el etiquetado integrado, el botón Confidencialidad no está disponible en la aplicación de Office.

El cliente de etiquetado unificado de Azure Information Protection admite tanto el formato Open XML como el Microsoft Office 97-2003. Para obtener más información, vea Tipos de [archivo admitidos](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) por el cliente de etiquetado unificado de Azure Information Protection desde la guía de administración de ese cliente.

Para otras soluciones de etiquetado, compruebe la documentación de los tipos de archivo admitidos.

## <a name="protection-templates-and-sensitivity-labels"></a>Plantillas de protección y etiquetas de confidencialidad

Las plantillas de protección definidas por el [administrador,](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)como las que define para cifrado de mensajes de Office 365, no son visibles en las aplicaciones de Office cuando se usa el etiquetado integrado. Esta experiencia simplificada refleja que no es necesario seleccionar una plantilla de protección, ya que la misma configuración se incluye con etiquetas de confidencialidad que tienen el cifrado habilitado.

Si necesita convertir plantillas de protección existentes en etiquetas, use Azure Portal y las siguientes instrucciones: Para convertir [plantillas en etiquetas](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opciones de Information Rights Management (IRM) y etiquetas de confidencialidad

Las etiquetas de confidencialidad que configure para aplicar cifrado eliminan la complejidad de los usuarios para especificar su propia configuración de cifrado. En muchas aplicaciones de Office, los usuarios aún pueden configurar manualmente esta configuración de cifrado individual mediante las opciones de Information Rights Management (IRM). Por ejemplo, para aplicaciones de Windows:

- Para un documento: **Información de archivo** Proteger documento  >    >  **Restringir**  >  **acceso**
- para un correo electrónico: en la **pestaña Opciones** > **Cifrar** 
  
Cuando los usuarios etiquetan inicialmente un documento o correo electrónico, siempre pueden invalidar las opciones de configuración de la etiqueta con sus propias opciones de cifrado. Por ejemplo:

- Un usuario aplica la etiqueta **Confidencial \ Todos** los empleados a un documento y esta etiqueta está configurada para aplicar la configuración de cifrado para todos los usuarios de la organización. A continuación, este usuario configura manualmente las opciones de IRM para restringir el acceso a un usuario fuera de la organización. El resultado final es un documento con la etiqueta **Confidencial \ Todos** los empleados y cifrado, pero los usuarios de la organización no pueden abrirlo como se esperaba.

- Un usuario aplica la etiqueta **Confidencial \ Solo** destinatarios a un correo electrónico y este correo electrónico está configurado para aplicar la configuración de cifrado de No **reenviar**. A continuación, este usuario configura manualmente la configuración de IRM para que el correo electrónico no esté restringido. El resultado final es que los destinatarios pueden reenviar el correo electrónico, a pesar de tener la etiqueta **Confidencial \ Solo destinatarios.**

- Un usuario aplica la etiqueta **General** a un documento y esta etiqueta no está configurada para aplicar cifrado. A continuación, este usuario configura manualmente las opciones de IRM para restringir el acceso al documento. El resultado final es un documento con la etiqueta **General,** pero que también aplica cifrado para que algunos usuarios no puedan abrirlo como se esperaba.

Si el documento o el correo electrónico ya están etiquetados, un usuario puede realizar cualquiera de estas acciones si el contenido aún no está cifrado o si tiene el derecho de uso [Exportar](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) o Control total. 

Para una experiencia de etiqueta más coherente con informes significativos, proporcione etiquetas y instrucciones adecuadas para que los usuarios apliquen solo etiquetas para proteger documentos. Por ejemplo:

- Para los casos de excepción en los que los usuarios deben asignar sus propios permisos, proporcione etiquetas que permiten a los usuarios [asignar sus propios permisos](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- En lugar de que los usuarios quiten el cifrado manualmente después de seleccionar una etiqueta que aplique cifrado, proporcione una alternativa de subetiqueta cuando los usuarios necesiten una etiqueta con la misma clasificación, pero sin cifrado. Por ejemplo:
    - **Confidencial \ Todos los empleados**
    - **Confidencial \ Cualquiera (sin cifrado)**

> [!NOTE]
> Si los usuarios quitan manualmente el cifrado de un documento etiquetado que está almacenado en SharePoint o OneDrive y ha habilitado etiquetas de confidencialidad para archivos de Office en SharePoint y [OneDrive,](sensitivity-labels-sharepoint-onedrive-files.md)el cifrado de etiquetas se restaurará automáticamente la próxima vez que se acceda o descargue el documento. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar etiquetas de confidencialidad a archivos, correos electrónicos y datos adjuntos

Los usuarios pueden aplicar una sola etiqueta a la vez para cada documento o correo electrónico.

Cuando etiqueta un mensaje de correo electrónico que tiene datos adjuntos, los datos adjuntos heredan la etiqueta solo si la etiqueta que aplica al mensaje de correo electrónico aplica cifrado y los datos adjuntos son documentos de Office que no están cifrados. Dado que la etiqueta heredada aplica cifrado, los datos adjuntos se cifran recientemente.

Los datos adjuntos no heredan las etiquetas del mensaje de correo electrónico cuando la etiqueta aplicada al mensaje de correo electrónico no aplica cifrado o los datos adjuntos ya están cifrados.

Ejemplos de herencia de etiquetas, donde la etiqueta **Confidencial** aplica cifrado y la etiqueta **General** no aplica cifrado:

- Un usuario crea un nuevo mensaje de correo electrónico y aplica la **etiqueta Confidencial** a este mensaje. A continuación, agregan un documento de Word que no está etiquetado ni cifrado. Como resultado de la herencia, el documento se acaba de etiquetar **Confidencial** y ahora se aplica cifrado desde esa etiqueta.

- Un usuario crea un nuevo mensaje de correo electrónico y aplica la **etiqueta Confidencial** a este mensaje. A continuación, agregan un documento de Word con la etiqueta **General** y este archivo no está cifrado. Como resultado de la herencia, el documento se vuelve a etiquetar como **Confidencial** y ahora se aplica cifrado desde esa etiqueta.

## <a name="sensitivity-label-compatibility"></a>Compatibilidad de etiquetas de confidencialidad

Con aplicaciones con **rms** iluminados: si abres un documento o correo electrónico con etiquetas y cifrados en una aplicación con [rms](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que no admite etiquetas de confidencialidad, la aplicación seguirá obligando a la administración de derechos y cifrado.

Con el cliente de **Azure Information Protection:** puede ver y cambiar las etiquetas de confidencialidad que se aplican a documentos y correos electrónicos con el cliente de etiquetado integrado de Office mediante el cliente de Azure Information Protection y al revés.

**Con otras versiones de Office:** cualquier usuario autorizado puede abrir documentos y correos electrónicos etiquetados en otras versiones de Office. Sin embargo, solo puede ver o cambiar la etiqueta en versiones compatibles de Office o mediante el cliente de Azure Information Protection. Las versiones compatibles de la aplicación de Office se enumeran en [la sección anterior.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Compatibilidad con archivos de SharePoint y OneDrive protegidos por etiquetas de confidencialidad

Para usar el cliente de etiquetado integrado de Office con Office en la web para documentos en SharePoint o OneDrive, asegúrese de que ha habilitado etiquetas de confidencialidad para archivos de Office en SharePoint y [OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Compatibilidad con usuarios externos y contenido etiquetado

Al etiquetar un documento o correo electrónico, la etiqueta se almacena como metadatos que incluyen el inquilino y un GUID de etiqueta. Cuando una aplicación de Office abre un documento o correo electrónico etiquetado que admite etiquetas de confidencialidad, estos metadatos se leen y solo si el usuario pertenece al mismo inquilino, la etiqueta se muestra en su aplicación. Por ejemplo, para el etiquetado integrado para Word, PowerPoint y Excel, el nombre de la etiqueta se muestra en la barra de estado. 

Esto significa que si comparte documentos con otra organización que usa nombres de etiqueta diferentes, cada organización puede aplicar y ver su propia etiqueta aplicada al documento. Sin embargo, los siguientes elementos de una etiqueta aplicada son visibles para los usuarios de fuera de la organización:

- Marcas de contenido. Cuando una etiqueta aplica un encabezado, pie de página o marca de agua, se agregan directamente al contenido y permanecen visibles hasta que alguien los modifica o elimina.

- Nombre y descripción de la plantilla de protección subyacente de una etiqueta que aplicó cifrado. Esta información se muestra en una barra de mensajes en la parte superior del documento, para proporcionar información sobre quién está autorizado a abrir el documento y sus derechos de uso para ese documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartir documentos cifrados con usuarios externos

Además de restringir el acceso a los usuarios de su propia organización, puede ampliar el acceso a cualquier otro usuario que tenga una cuenta en Azure Active Directory. Sin embargo, si su organización usa directivas de acceso condicional, consulte la [siguiente sección para](#conditional-access-policies) más consideraciones.

Todas las aplicaciones de Office y [otras aplicaciones](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) con rms iluminados pueden abrir documentos cifrados después de que el usuario se haya autenticado correctamente. 

Si los usuarios externos no tienen una cuenta en Azure Active Directory, pueden autenticarse con cuentas invitadas en el espacio empresarial. Estas cuentas invitadas también se pueden usar para obtener acceso a documentos compartidos en SharePoint o OneDrive cuando se han habilitado etiquetas de confidencialidad para archivos de Office en [SharePoint y OneDrive:](sensitivity-labels-sharepoint-onedrive-files.md)

- Una opción es crear estas cuentas de invitado usted mismo. Puede especificar cualquier dirección de correo electrónico que estos usuarios ya usen. Por ejemplo, su dirección de Gmail.
    
    La ventaja de esta opción es que puede restringir el acceso y los derechos a usuarios específicos especificando su dirección de correo electrónico en la configuración de cifrado. La desventaja es la sobrecarga de administración para la creación de cuentas y la coordinación con la configuración de etiquetas.

- Otra opción es usar la integración de SharePoint y OneDrive con [Azure AD B2B (versión preliminar)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para que las cuentas invitadas se crean automáticamente cuando los usuarios comparten vínculos.
    
    La ventaja de esta opción es una sobrecarga administrativa mínima porque las cuentas se crean automáticamente y la configuración de etiquetas es más sencilla. Para este escenario, debe seleccionar la opción de cifrado [Agregar cualquier](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) usuario autenticado porque no conocerá las direcciones de correo electrónico por adelantado. La desventaja es que esta configuración no le permite restringir los derechos de acceso y uso a usuarios específicos.

Los usuarios externos también pueden usar una cuenta de Microsoft para abrir documentos cifrados cuando usan Aplicaciones de Windows y Microsoft 365 (anteriormente aplicaciones de[Office 365)](https://docs.microsoft.com/deployoffice/name-change)o la edición independiente de Office 2019. Más recientemente compatible con otras plataformas, las cuentas de Microsoft también son compatibles con la apertura de documentos cifrados en macOS (Aplicaciones de Microsoft 365, versión 16.42+), Android (versión 16.0.13029+) e iOS (versión 2.42+). Por ejemplo, un usuario de la organización comparte un documento cifrado con un usuario externo a la organización y la configuración de cifrado especifica una dirección de correo electrónico de Gmail para el usuario externo. Este usuario externo puede crear su propia cuenta de Microsoft que use su dirección de correo electrónico de Gmail. Después, después de iniciar sesión con esta cuenta, pueden abrir el documento y editarlo, según las restricciones de uso especificadas para ellos. Para ver un ejemplo de tutorial de este escenario, vea [Opening and editing the protected document](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> La dirección de correo electrónico de la cuenta Microsoft debe coincidir con la dirección de correo electrónico especificada para restringir el acceso a la configuración de cifrado.

Cuando un usuario con una cuenta microsoft abre un documento cifrado de esta manera, crea automáticamente una cuenta de invitado para el inquilino si aún no existe una cuenta de invitado con el mismo nombre. Cuando la cuenta de invitado existe, se puede usar para abrir documentos en SharePoint y OneDrive mediante Office en la web, además de abrir documentos cifrados desde las aplicaciones de Office móviles y de escritorio compatibles.

Sin embargo, la cuenta de invitado automática no se crea inmediatamente en este escenario, debido a la latencia de replicación. Si especifica direcciones de correo electrónico personales como parte de la configuración de cifrado de etiquetas, se recomienda crear las cuentas de invitado correspondientes en Azure Active Directory. A continuación, haga saber a estos usuarios que deben usar esta cuenta para abrir un documento cifrado de su organización.

> [!TIP]
> Como no puede estar seguro de que los usuarios externos usarán una aplicación cliente de Office compatible, compartir vínculos de SharePoint y OneDrive después de crear cuentas de invitado (para usuarios específicos) o cuando use la integración de SharePoint y OneDrive con [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (para cualquier usuario autenticado) es un método más confiable para admitir la colaboración segura con usuarios externos.

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Si su organización ha implementado directivas de acceso condicional de [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)compruebe la configuración de dichas directivas. Si las directivas incluyen Azure Information Protection y la directiva se extiende a usuarios externos, esos usuarios externos deben tener una cuenta de invitado en el inquilino incluso si tienen una cuenta de Azure AD en su propio inquilino.

Sin esta cuenta de invitado, no pueden abrir el documento cifrado y ver un mensaje de error. El texto del mensaje puede informarles de que su cuenta debe agregarse como usuario externo en el inquilino, con la instrucción incorrecta para este escenario de cerrar sesión e iniciar sesión de nuevo con una cuenta de usuario de **Azure Active Directory** diferente.

Si no puede crear y configurar cuentas de invitado en el inquilino para usuarios externos que necesiten abrir documentos cifrados por las etiquetas, debe quitar Azure Information Protection de las directivas de acceso condicional o excluir usuarios externos de las directivas.

Para obtener más información acerca del acceso condicional y Azure Information Protection, el servicio de cifrado que usan las etiquetas de confidencialidad, vea la pregunta más frecuente, veo que Azure Information Protection aparece como una aplicación en la nube disponible para el acceso condicional, ¿cómo funciona [esto?](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Cuando las aplicaciones de Office aplican el marcado y cifrado de contenido

Las aplicaciones de Office aplican el marcado de contenido y el cifrado con una etiqueta de confidencialidad de forma diferente, según la aplicación que use.

| Aplicación | Marcado de contenido | Cifrado |
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Después de que Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Después de que Exchange Online envíe el correo electrónico | Después de que Exchange Online envíe el correo electrónico |
|

Las soluciones que aplican etiquetas de confidencialidad a archivos fuera de aplicaciones de Office lo hacen aplicando metadatos de etiquetado al archivo. En este escenario, el marcado de contenido de la configuración de la etiqueta no se inserta en el archivo, pero se aplica el cifrado. 

Cuando esos archivos se abren en una aplicación de escritorio de Office, el cliente de etiquetado unificado de Azure Information Protection aplica automáticamente las marcas de contenido. Las marcas de contenido no se aplican automáticamente cuando se usa el etiquetado integrado para aplicaciones de escritorio, móviles o web.

Entre los escenarios que incluyen la aplicación de una etiqueta de confidencialidad fuera de las aplicaciones de Office se incluyen:

- El escáner, el Explorador de archivos y PowerShell del cliente de etiquetado unificado de Azure Information Protection 

- Directivas de etiquetado automático para SharePoint y OneDrive

- Datos etiquetados y cifrados exportados desde Power BI

- Microsoft Cloud App Security

Para estos escenarios, con sus aplicaciones de Office, un usuario con etiquetado integrado puede aplicar las marcas de contenido de la etiqueta quitando o reemplazando temporalmente la etiqueta actual y, a continuación, volver a aplicar la etiqueta original.

### <a name="dynamic-markings-with-variables"></a>Marcados dinámicos con variables

> [!IMPORTANT]
> Actualmente, no todas las aplicaciones de todas las plataformas admiten marcas de contenido dinámicas que puedes especificar para tus encabezados, pies de página y marcas de agua. Para las aplicaciones que no admiten esta funcionalidad, aplican las marcas como texto original especificado en la configuración de etiquetas, en lugar de resolver las variables.
> 
> El cliente de etiquetado unificado de Azure Information Protection admite marcas dinámicas. Para etiquetar integrado en Office, vea las tablas de la sección [de](#support-for-sensitivity-label-capabilities-in-apps) funcionalidades de esta página.

Al configurar una etiqueta de confidencialidad para marcas de contenido, puede usar las siguientes variables en la cadena de texto para el encabezado, pie de página o marca de agua:

| Variable | Descripción | Ejemplo cuando se aplica la etiqueta |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nombre para mostrar de etiqueta de la etiqueta aplicada| **General**|
| `${Item.Name}` | Nombre de archivo o asunto de correo electrónico del contenido que se va a etiquetar | **Sales.docx** |
| `${Item.Location}` | Ruta de acceso y nombre de archivo del documento que se va a etiquetar, o el asunto de correo electrónico de un correo electrónico que se va a etiquetar | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nombre para mostrar del usuario que aplica la etiqueta| **Richard Simone** |
| `${User.PrincipalName}` | Nombre principal de usuario de Azure AD (UPN) del usuario que aplica la etiqueta | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Fecha y hora en que se etiqueta el contenido, en la zona horaria local del usuario que aplica la etiqueta | **10/08/2020 1:30 p.m.** |

> [!NOTE]
> La sintaxis de estas variables distingue mayúsculas de minúsculas.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Establecer diferentes marcas visuales para Word, Excel, PowerPoint y Outlook

Como variable adicional, puede configurar marcas visuales por tipo de aplicación de Office mediante una instrucción de variable "If.App" en la cadena de texto e identificar el tipo de aplicación mediante los valores **Word,** **Excel,** **PowerPoint** o **Outlook**. También puede abreviar estos valores, que es necesario si desea especificar más de uno en la misma instrucción If.App.

> [!NOTE]
> Para mayor integridad, se incluyen instrucciones para Outlook, aunque actualmente solo son compatibles con el cliente de etiquetado unificado de Azure Information Protection.

Utilice la sintaxis siguiente:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Al igual que con las otras marcas visuales dinámicas, la sintaxis distingue mayúsculas de minúsculas.

Ejemplos:

- **Establecer solo texto de encabezado para documentos de Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Solo en encabezados de documento de Word, la etiqueta aplica el texto de encabezado "Este documento de Word es confidencial". No se aplica texto de encabezado a otras aplicaciones de Office.

- **Establecer texto de pie de página para Word, Excel y Outlook, y texto de pie de página diferente para PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    En Word, Excel y Outlook, la etiqueta aplica el texto de pie de página "Este contenido es confidencial". En PowerPoint, la etiqueta aplica el texto del pie de página "Esta presentación es confidencial".

- **Establezca texto de marca de agua específico para Word y PowerPoint y, a continuación, texto de marca de agua para Word, Excel y PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    En Word y PowerPoint, la etiqueta aplica el texto de marca de agua "Este contenido es confidencial". En Excel, la etiqueta aplica el texto de marca de agua "Confidencial". En Outlook, la etiqueta no aplica ningún texto de marca de agua porque las marcas de agua como marcas de agua visuales no son compatibles con Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Requerir que los usuarios apliquen una etiqueta a su correo electrónico y documentos

> [!IMPORTANT]
> También conocido como etiquetado obligatorio, no todas las aplicaciones de todas las plataformas admiten actualmente la configuración de directiva de Requerir que los usuarios apliquen una etiqueta a su correo electrónico **y documentos.**
> 
> El cliente de etiquetado unificado de [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) admite el etiquetado obligatorio y [](#support-for-sensitivity-label-capabilities-in-apps) para el etiquetado integrado en aplicaciones de Office, consulte las tablas de la sección de funcionalidades de esta página.

Cuando se selecciona esta configuración de directiva, los usuarios asignados a la directiva deben seleccionar y aplicar una etiqueta de confidencialidad en los siguientes escenarios:

- Para el cliente de etiquetado unificado de Azure Information Protection:
    - Para documentos (Word, Excel, PowerPoint): cuando se guarda un documento sin etiquetar o los usuarios cierran el documento.
    - Para correos electrónicos (Outlook): en el momento en que los usuarios envían un mensaje sin etiquetar.

- Para el etiquetado integrado en aplicaciones de Office:
    - Para documentos ((Word, Excel, PowerPoint): cuando se abre o guarda un documento sin etiquetar.
    - Para correos electrónicos (Outlook): en el momento en que los usuarios envían un mensaje de correo electrónico sin etiquetar.

Información adicional para el etiquetado integrado:

- Cuando se pide a los usuarios que agreguen una etiqueta de confidencialidad porque abren un documento sin etiquetar, pueden agregar una etiqueta o elegir abrir el documento en modo de solo lectura.

- Cuando el etiquetado obligatorio está en vigor, los usuarios no pueden quitar etiquetas de confidencialidad de los documentos, pero pueden cambiar una etiqueta existente.

Para obtener instrucciones sobre cuándo usar esta configuración, consulte la información sobre la [configuración de directiva](sensitivity-labels.md#what-label-policies-can-do).

## <a name="end-user-documentation"></a>Documentación del usuario final

- [Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conocidos al aplicar etiquetas de confidencialidad en sus archivos de Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
