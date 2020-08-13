---
title: Usar etiquetas de confidencialidad en las aplicaciones de Office
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
description: Obtenga información sobre cómo trabajan los usuarios con las etiquetas de confidencialidad en las aplicaciones de Office para equipos de escritorio, móviles y Web, así como las aplicaciones compatibles con las etiquetas de confidencialidad.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c47b97c573822cb44f895296613b70af7f85c93
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656785"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usar etiquetas de confidencialidad en las aplicaciones de Office

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Una vez [publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) las etiquetas de confidencialidad del centro de cumplimiento de Microsoft 365 o del centro de etiquetas equivalente, comienzan a aparecer en las aplicaciones de Office para que los usuarios clasifiquen y protejan los datos cuando se crean o editan.

Use la información de este artículo como ayuda para administrar correctamente las etiquetas de confidencialidad en las aplicaciones de Office. Por ejemplo, identifique las versiones mínimas de las aplicaciones que necesita para admitir etiquetas integradas y comprenda las interacciones con el cliente de etiquetado Unificado de Azure Information Protection y la compatibilidad con otras aplicaciones y servicios.

## <a name="labeling-client-for-desktop-apps"></a>Etiquetar el cliente para aplicaciones de escritorio

Para usar las etiquetas de confidencialidad integradas en las aplicaciones de escritorio de Office para Windows y Mac, debe usar una edición de suscripción de Office. Este cliente de etiquetado no admite ediciones independientes de Office, como Office 2016 u Office 2019.

Para usar las etiquetas de confidencialidad con estas ediciones independientes de Office en equipos con Windows, instale el [cliente de etiquetado Unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Compatibilidad con funcionalidades de etiqueta de confidencialidad en las aplicaciones

Para cada funcionalidad, en las tablas siguientes se muestra la versión mínima que necesita para que la aplicación admita etiquetas de confidencialidad mediante el uso de etiquetas integradas. O bien, si la capacidad de la etiqueta está en versión preliminar pública o en revisión para una versión futura.

Las nuevas versiones de las aplicaciones están disponibles en diferentes momentos para diferentes canales de actualización. Para obtener más información, incluido cómo configurar el canal de actualización para que pueda probar una nueva capacidad de etiquetado que le interese, vea [Overview of Update Channels for Microsoft 365 apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Las nuevas funciones que se encuentran en la versión preliminar privada no se incluyen en la tabla, pero es posible que pueda unirse a estas vistas previas nombrando a su organización para el [programa de vista previa de la información privada de Microsoft Information Protection](https://aka.ms/mip-preview).

> [!NOTE]
> Los nombres de los canales de actualización para las aplicaciones de Office han cambiado recientemente. Por ejemplo, el canal mensual es ahora el canal actual y Office Insider es ahora el canal beta. Para obtener más información, consulte [cambios en los canales de actualización de las aplicaciones de Microsoft 365](https://docs.microsoft.com/deployoffice/update-channels-changes).

Hay disponibles capacidades adicionales al instalar el cliente de etiquetado Unificado de Azure Information Protection, que se ejecuta solo en equipos con Windows. Para obtener información detallada, consulte [Compare The Labeling clients for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Capacidades de la etiqueta de confidencialidad en Word, Excel y PowerPoint

Para iOS y Android: cuando se muestran las versiones mínimas, también se admite la capacidad de la etiqueta de confidencialción con la [aplicación de Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

|Funcionalidad                                                                                                        |Escritorio de Windows |Escritorio de Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Vínculo proporcionar ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | [Canal actual](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) (2003 +) | 16.35 +   | En revisión   | En revisión         | En revisión                                                        |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | En revisión            | En revisión        | En revisión   | En revisión         | En revisión                                                        |
|[Pedir a los usuarios que apliquen una etiqueta a su correo electrónico y documentos](sensitivity-labels.md#what-label-policies-can-do)   | En revisión            | En revisión        | En revisión   | En revisión         | En revisión                                                        |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | Implementación en el [canal actual](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) (2006 +)                                  | En revisión | En revisión | En revisión | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|Compatibilidad con [autoguardado](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) y [coautoría](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) en documentos con y sin etiquetas | En revisión | En revisión | En revisión | En revisión | [Sí-participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Capacidades de la etiqueta de confidencialidad en Outlook

|Funcionalidad                                                                                                        |Outlook en el escritorio de Windows |Escritorio de Outlook en Mac  |Outlook en iOS |Outlook en Android |Outlook en la Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Vínculo proporcionar ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | En revisión                       | En revisión                    | En revisión           | En revisión               | En revisión               |
|[Pedir a los usuarios que apliquen una etiqueta a su correo electrónico y documentos](sensitivity-labels.md#what-label-policies-can-do)   | En revisión                       | En revisión                    | En revisión           | En revisión               | En revisión               |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | Vista previa: canal de la [versión beta](https://office.com/insider) e implementación en el [canal actual (versión preliminar)](https://office.com/insider)                      | En revisión                    | En revisión           | En revisión               | Sí |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de etiquetado de Office integrado y otras soluciones de etiquetado

La configuración de directiva de la etiqueta de confidencialidad de descargas de clientes de la etiqueta integrada de Office de los siguientes centros de administración:

- Centro de cumplimiento de Microsoft 365
- Centro de seguridad de Microsoft 365
- Centro de seguridad y cumplimiento de Office 365

Para usar el cliente de etiquetado integrado de Office, debe tener una o más directivas de [etiquetas publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para los usuarios desde uno de los centros de administración que aparecen en la lista y una [versión compatible de Office](#support-for-sensitivity-label-capabilities-in-apps).

Si se cumplen estas dos condiciones, pero necesita desactivar el cliente de etiquetado integrado de Office, use la siguiente configuración de directiva de Grupo:

1. Vaya a **configuración del usuario/Plantillas administrativas/Microsoft Office 2016/configuración de seguridad**

2. Set **use la característica de confidencialidad de Office para aplicar y ver las etiquetas de confidencialidad** a **0**. 
 
Implemente esta configuración mediante la Directiva de grupo o con el [servicio de directivas de nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). La configuración surte efecto cuando se reinician las aplicaciones de Office.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de etiquetado de Office integrado y el cliente de Azure Information Protection

Si los usuarios tienen instalado uno de los clientes de Azure Information Protection ([cliente de etiquetado unificado](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) o [cliente clásico](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), el cliente de etiquetado integrado está desactivado en las aplicaciones de Office de forma predeterminada. 

Para usar etiquetas integradas en lugar del cliente de Azure Information Protection para las aplicaciones de Office, siga las instrucciones de la sección anterior pero establezca la configuración de directiva de grupo **use la característica de confidencialidad de Office para aplicar y ver las etiquetas de confidencialidad** a **1**. 

Como alternativa, deshabilite o quite el complemento de Office, **Azure Information Protection**. Este método es apto para un solo equipo y para pruebas ad-hoc. Para obtener instrucciones, consulte [View, Manage e install Add-Ins in Office Programs](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Al deshabilitar o quitar este complemento de Office, el cliente de Azure Information Protection permanece instalado para que pueda seguir etiquetando los archivos fuera de las aplicaciones de Office. Por ejemplo, con el explorador de archivos o PowerShell.

Para obtener información sobre las características admitidas por los clientes de Azure Information Protection y el cliente de etiquetado integrado de Office, vea [Choose The Labeling client to use for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="office-file-types-supported"></a>Tipos de archivo de Office admitidos

Las aplicaciones de Office con etiquetas integradas para archivos de Word, Excel y PowerPoint admiten el formato Open XML (como. docx y. xlsx), pero no el formato de Microsoft Office 97-2003 (como. doc y. xls). Cuando un tipo de archivo no es compatible con las etiquetas integradas, el botón **confidencial** no está disponible en la aplicación de Office.

El cliente de etiquetación Unificado de Azure Information Protection admite tanto el formato Open XML como el formato 97-2003 de Microsoft Office. Para obtener más información, consulte [tipos de archivo compatibles con el cliente de etiquetación unificada de Azure Information Protection desde la](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) guía de administración de ese cliente.

Para otras soluciones de etiquetado, consulte en su documentación los tipos de archivo admitidos.

## <a name="protection-templates-and-sensitivity-labels"></a>Plantillas de protección y etiquetas de confidencialidad

[Las plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidas por el administrador, como las que se definen para el cifrado de mensajes de Office 365, no son visibles en las aplicaciones de Office cuando se usan etiquetas integradas. Esta experiencia simplificada refleja que no es necesario seleccionar una plantilla de protección, ya que se incluye la misma configuración con las etiquetas de confidencialidad que tienen habilitado el cifrado.

Si necesita convertir plantillas de protección existentes en etiquetas, use Azure portal y las siguientes instrucciones: [para convertir plantillas en etiquetas](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opciones de Information Rights Management (IRM) y etiquetas de confidencialidad

Las etiquetas de confidencialidad que configure para aplicar el cifrado eliminan la complejidad de los usuarios para especificar su propia configuración de cifrado. En muchas aplicaciones de Office, los usuarios pueden seguir configurando manualmente estas configuraciones de cifrado individuales mediante las opciones de Information Rights Management (IRM). Por ejemplo, para aplicaciones de Windows:

- Para un documento: información sobre el **archivo**  >  **Info**  >  **proteger documento**  >  **restringir acceso**
- para un correo electrónico: en la pestaña **opciones** > **cifrar** 
  
Cuando los usuarios etiquetan inicialmente un documento o correo electrónico, siempre pueden invalidar las opciones de configuración de la etiqueta con su propia configuración de cifrado. Por ejemplo:

- Un usuario aplica la etiqueta **confidencial \ todos los empleados** a un documento y esta etiqueta se configura para aplicar la configuración de cifrado para todos los usuarios de la organización. A continuación, este usuario configura manualmente la configuración de IRM para restringir el acceso a un usuario fuera de la organización. El resultado final es un documento que se denomina **confidencial \ todos los empleados** y cifrados, pero los usuarios de su organización no pueden abrirlo de la manera esperada.

- Un usuario aplica la etiqueta **confidencial \ destinatarios solamente** a un correo electrónico y este correo está configurado para aplicar la configuración de cifrado de no **reenviar**. A continuación, este usuario configura manualmente la configuración de IRM para que el correo no esté restringido. El resultado final es que los destinatarios pueden reenviar el correo electrónico, a pesar de tener la etiqueta de **confidencialidad solo de destinatarios** .

- Un usuario aplica la etiqueta **General** a un documento y esta etiqueta no está configurada para aplicar el cifrado. A continuación, este usuario configura manualmente las opciones de IRM para restringir el acceso al documento. El resultado final es un documento con la etiqueta **General** , pero que también aplica el cifrado para que algunos usuarios no puedan abrirlo de la manera esperada.

Si el documento o correo electrónico ya tiene la etiqueta, un usuario puede realizar cualquiera de estas acciones si el contenido no está cifrado o si tiene el [derecho de uso](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) exportar o control total. 

Para obtener una experiencia de etiqueta más coherente con informes significativos, proporcione las etiquetas apropiadas y las instrucciones para que los usuarios apliquen sólo las etiquetas para proteger los documentos. Por ejemplo:

- Para los casos de excepción en los que los usuarios deben asignar sus propios permisos, proporcione etiquetas que [permitan a los usuarios asignar sus propios permisos](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- En lugar de que los usuarios quiten manualmente el cifrado después de seleccionar una etiqueta que aplique cifrado, proporcione una subetiqueta alternativa cuando los usuarios necesiten una etiqueta con la misma clasificación, pero sin cifrado. Como:
    - **Confidencial \ todos los empleados**
    - **Confidencial \ cualquiera (sin cifrado)**

> [!NOTE]
> Si los usuarios quitan manualmente el cifrado de un documento con etiquetas que se almacena en SharePoint o OneDrive y se [habilitan las etiquetas de confidencialidad para los archivos de Office en SharePoint y onedrive](sensitivity-labels-sharepoint-onedrive-files.md), el cifrado de etiqueta se restaurará automáticamente la próxima vez que se acceda al documento o se descargue. 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar etiquetas de confidencialidad a archivos, mensajes de correo electrónico y datos adjuntos

Los usuarios pueden aplicar una sola etiqueta a la vez para cada documento o correo electrónico.

Al etiquetar un mensaje de correo electrónico que tiene datos adjuntos, los datos adjuntos no heredan la etiqueta con una excepción:

- Los datos adjuntos son un documento de Office con una etiqueta que no aplica el cifrado y la etiqueta que se aplica al mensaje de correo electrónico aplica el cifrado. En este caso, el documento de Office por correo electrónico hereda la etiqueta del correo electrónico con su configuración de cifrado.

En caso contrario: 

- Si los datos adjuntos tienen una etiqueta, mantienen su etiqueta originalmente aplicada.
- Si los datos adjuntos se cifran sin etiqueta, el cifrado permanece pero no se etiquetan.
- Si los datos adjuntos no tienen etiqueta, permanecen sin etiqueta.

## <a name="sensitivity-label-compatibility"></a>Compatibilidad de las etiquetas de confidencialidad

**Con aplicaciones habilitadas para RMS**: Si abre un documento o un correo electrónico con la etiqueta y cifrada en una [aplicación habilitada para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que no admite etiquetas de confidencialidad, la aplicación sigue forzando el cifrado y la administración de derechos.

**Con el cliente de Azure Information Protection**: puede ver y cambiar las etiquetas de confidencialidad que se aplican a los documentos y correos electrónicos con el cliente de etiquetación integrado de Office mediante el cliente de Azure Information Protection y la otra forma.

**Con otras versiones de Office**: cualquier usuario autorizado puede abrir documentos con etiquetas y correos electrónicos en otras versiones de Office. Sin embargo, solo puede ver o cambiar la etiqueta en versiones de Office compatibles o mediante el cliente de Azure Information Protection. Las versiones de aplicaciones de Office admitidas se muestran en la [sección anterior](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Compatibilidad con archivos de OneDrive y SharePoint protegidos por etiquetas de confidencialidad

Para usar el cliente de etiquetado integrado de Office con Office en la web para documentos en SharePoint o OneDrive, asegúrese de que ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Compatibilidad con usuarios externos y con etiqueta de contenido

Al etiquetar un documento o correo electrónico, la etiqueta se almacena como metadatos que incluyen el espacio empresarial y un GUID de etiqueta. Cuando un documento etiquetado o un correo electrónico se abre con una aplicación de Office que admite etiquetas de confidencialidad, estos metadatos se leen y solo si el usuario pertenece al mismo espacio empresarial, la etiqueta se muestra en la aplicación. Por ejemplo, para las etiquetas integradas de Word, PowerPoint y Excel, el nombre de la etiqueta se muestra en la barra de estado. 

Esto significa que si comparte documentos con otra organización que usa distintos nombres de etiquetas, cada organización puede aplicar y ver su propia etiqueta aplicada al documento. Sin embargo, los usuarios externos a la organización pueden ver los siguientes elementos de una etiqueta aplicada:

- Marcados de contenido. Cuando una etiqueta aplica un encabezado, un pie de página o una marca de agua, estos se agregan directamente al contenido y permanecen visibles hasta que alguien los modifica o Los elimina.

- El nombre y la descripción de la plantilla de protección subyacente de una etiqueta que aplicó el cifrado. Esta información se muestra en una barra de mensajes en la parte superior del documento para proporcionar información sobre quién está autorizado para abrir el documento y sus derechos de uso para ese documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Uso compartido de documentos cifrados con usuarios externos

Además de restringir el acceso a los usuarios de su propia organización, puede ampliar el acceso a cualquier otro usuario que tenga una cuenta en Azure Active Directory. Todas las aplicaciones de Office y otras [aplicaciones habilitadas para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) pueden abrir documentos cifrados después de que el usuario se haya autenticado correctamente.

Si los usuarios externos no tienen una cuenta en Azure Active Directory, puede crear una cuenta de invitado para ellos en su espacio empresarial. Para su dirección de correo electrónico, puede especificar cualquier dirección de correo electrónico que ya use. Por ejemplo, su dirección de gmail. Esta cuenta de invitado también se puede usar para obtener acceso a un documento compartido en SharePoint o OneDrive cuando haya [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

Los usuarios externos también pueden usar y crear una cuenta de Microsoft para documentos cifrados cuando usan aplicaciones de Microsoft 365 ([anteriormente aplicaciones de Office 365](https://docs.microsoft.com/deployoffice/name-change)) en Windows. Esta funcionalidad aún no es compatible con macOS, Android o iOS. Por ejemplo, alguien comparte un documento cifrado con ellos y la configuración de cifrado especifica la dirección de correo electrónico de gmail. Este usuario puede crear su propia cuenta de Microsoft que usa su dirección de correo de gmail. A continuación, después de iniciar sesión con esta cuenta, pueden abrir el documento y editarlo, de acuerdo con las restricciones de uso especificadas para ese usuario. Para obtener un ejemplo de un tutorial de este escenario, consulte [abrir y editar el documento protegido](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> La dirección de correo electrónico de la cuenta Microsoft debe coincidir con la dirección de correo electrónico especificada para restringir el acceso a la configuración de cifrado.

Cuando un usuario con una cuenta de Microsoft abre un documento cifrado de esta manera, crea automáticamente una cuenta de invitado para el inquilino si todavía no existe una cuenta de invitado con el mismo nombre. Cuando existe la cuenta de invitado, puede usarse para abrir documentos en SharePoint y OneDrive con un explorador (Office en la web), además de abrir documentos cifrados desde la aplicación de escritorio de Windows. 

Sin embargo, la cuenta de invitado automática no se crea inmediatamente debido a la latencia de replicación. Si especifica direcciones de correo electrónico personales como parte de la configuración de cifrado de la etiqueta, le recomendamos que cree las cuentas de invitado correspondientes en Azure Active Directory. A continuación, informe a estos usuarios de que deben usar esta cuenta para abrir un documento cifrado de la organización.

> [!TIP]
> Como no puede estar seguro de que los usuarios externos usen una aplicación de cliente de Office admitida, compartir vínculos de SharePoint y OneDrive después de crear cuentas de invitado es un método más confiable para admitir la colaboración segura con usuarios externos.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Cuando las aplicaciones de Office aplican marcado y cifrado de contenido

Las aplicaciones de Office aplican marcado y cifrado de contenido con una etiqueta de confidencialidad de forma diferente, según la aplicación que use.

| Aplicación | Marcado de contenido | Cifrado |
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Después de que Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Después de que Exchange Online envíe el correo electrónico | Después de que Exchange Online envíe el correo electrónico |
|

Las soluciones que aplican las etiquetas de confidencialidad a los archivos fuera de las aplicaciones de Office lo hacen aplicando metadatos de etiquetado al archivo. En este escenario, la marcación de contenido de la configuración de la etiqueta no se inserta en el archivo, pero se aplica el cifrado. 

Cuando estos archivos se abren en una aplicación de escritorio de Office, el cliente de etiquetación Unificado de Azure Information Protection aplica automáticamente los marcadores de contenido. Las marcas de contenido no se aplican automáticamente cuando se usan etiquetas integradas para aplicaciones Web, móviles o de escritorio.

Entre los escenarios que incluyen la aplicación de una etiqueta de confidencialidad fuera de las aplicaciones de Office se incluyen:

- El analizador, el explorador de archivos y PowerShell desde el cliente de etiquetado Unificado de Azure Information Protection 

- Directivas de etiquetado automático para SharePoint y OneDrive

- Datos exportados y con etiquetas de Power BI

- Microsoft Cloud App Security

Para estos escenarios, usando sus aplicaciones de Office, un usuario con etiquetas integradas puede aplicar los marcados de contenido de la etiqueta quitando o reemplazando temporalmente la etiqueta actual y, a continuación, volviendo a aplicar la etiqueta original.

## <a name="end-user-documentation"></a>Documentación para el usuario final

- [Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conocidos al aplicar etiquetas de confidencialidad en sus archivos de Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)