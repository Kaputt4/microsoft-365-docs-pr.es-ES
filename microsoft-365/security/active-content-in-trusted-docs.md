---
title: Administrar contenido activo en Office documentos para administradores de TI
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ROBOTS: NOINDEX,NOFOLOW
description: Los administradores pueden aprender a crear directivas para bloquear el contenido activo en Office documentos
ms.openlocfilehash: 1e27e3f4292b1036f05f41c3f5f2b48594d527b1
ms.sourcegitcommit: 5eecb0ccc70bf75779411d80147ed5588132b103
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2021
ms.locfileid: "59461648"
---
# <a name="manage-active-content-in-office-documents"></a>Administrar contenido activo en Office documentos

> [!NOTE]
> Las características que se describen en este artículo están en Versión preliminar, no están disponibles para todos y están sujetas a cambios.

Office documentos se pueden actualizar, actualizar o ejecutar automáticamente cuando contienen _contenido activo_. Ejemplos de contenido activo son macros, ActiveX controles y Office complementos. El contenido activo puede proporcionar una funcionalidad eficaz y útil a los usuarios, pero los atacantes también pueden usar contenido activo para entregar malware.

Los administradores pueden crear directivas de organización (directivas de grupo o directivas en la nube) que limiten el uso de contenido activo a conjuntos específicos de usuarios o deshabilitar el contenido activo por completo. Los usuarios pueden configurar sus propias opciones de seguridad y privacidad en el Centro de confianza de Office en sus aplicaciones Office en **el Centro** de confianza de opciones \>  \> **de archivos.**

Anteriormente, cuando los usuarios identificaban documentos como documentos de confianza, su selección permitía ejecutar contenido activo, incluso si un administrador configuraba directivas para bloquear el contenido activo en Office documentos. Ahora, las directivas establecidas por los administradores tienen prioridad sobre la identificación de usuarios de documentos de confianza. Este cambio en el comportamiento puede provocar problemas para los usuarios.

La lógica actualizada del Centro de confianza se describe en el siguiente diagrama:

![Gráfico de flujo que muestra el comportamiento del Centro de confianza para el contenido activo en Office documentos.](../media/office-trust-center-flow.png)

1. Un usuario abre un Office que contiene contenido activo.

2. Si el documento es de una ubicación de confianza, el documento se abre con el contenido activo habilitado. Si el documento no es de una ubicación de confianza, la evaluación continúa.

3. Aquí es donde el comportamiento actualizado tiene efecto:
   - Anteriormente, la siguiente configuración evaluada habría sido si el usuario hubiera identificado este documento como un documento de confianza. Si lo hicieran, el documento se abriría con el contenido activo habilitado.
   - Ahora, si el usuario identificó el documento como un documento de confianza no se considera aquí (ahora en el paso 8).

     Este es el cambio fundamental en el comportamiento: las directivas en la nube (paso 4), las directivas de grupo (paso 6) y la configuración local (paso 7) se comprueban antes de que se considere la designación de usuario de un documento de confianza.  Si alguno de estos pasos bloquea  el acceso al contenido activo y ninguno de los pasos permite invalidaciones de usuario, la identificación del documento como documento de confianza es básicamente irrelevante.

4. Las directivas en la nube se comprueban para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo no está bloqueado, la evaluación continúa en el paso 6.

   Si la directiva bloquea el contenido activo, la experiencia se describe en el paso 5.

5. La apertura del documento se bloquea con una notificación en la barra de confianza. Lo que sucede a continuación se controla mediante la configuración de invalidación de usuario en la directiva: a. **No se permite la invalidación de** usuario: el usuario no puede abrir el documento y la evaluación se detiene.
   b. **Invalidación de usuario** permitida: el usuario puede hacer clic en el vínculo de la barra de confianza para abrir el documento con el contenido activo habilitado.

6. Las directivas de grupo se comprueban para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo no está bloqueado, la evaluación continúa en el paso 7.

   Si la directiva bloquea el contenido activo, la experiencia se describe en el paso 5.

7. Se comprueba la configuración local para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo está bloqueado, la apertura del documento se bloquea con una notificación en la barra de confianza. Si el contenido activo no está bloqueado, la evaluación continúa.

8. Si el usuario identificó previamente el documento como un documento de confianza, el documento se abre con el contenido activo habilitado. Si no es así, se bloquea la apertura del documento.

## <a name="what-is-a-trusted-document"></a>¿Qué es un documento de confianza?

Los documentos de confianza Office documentos que se abren sin avisos de seguridad para macros, ActiveX controles y otros tipos de contenido activo del documento. Vista protegida o Protección de aplicaciones no se usa para abrir el documento. Cuando los usuarios abren un documento de confianza y todo el contenido activo está habilitado.Incluso si el documento contiene nuevo contenido activo o actualizaciones del contenido activo existente, los usuarios no recibirán avisos de seguridad la próxima vez que abran el documento.

Debido a este comportamiento, los usuarios deben confiar claramente en los documentos solo si confían en el origen del documento.

Si un administrador bloquea el contenido activo mediante una directiva o si los usuarios establecen una configuración del Centro de confianza que bloquea el contenido activo, el contenido activo permanecerá bloqueado.

Para más información, consulte los siguientes artículos:

- [Documentos confiables](https://support.microsoft.com/topic/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53)
- [Agregar, quitar o cambiar una ubicación de confianza](https://support.microsoft.com/topic/add-remove-or-change-a-trusted-location-7ee1cdc2-483e-4cbb-bcb3-4e7c67147fb4)
- [Tipos de contenido activos en los archivos](https://support.microsoft.com/topic/active-content-types-in-your-files-b7ff2e8a-4055-47d4-8c7d-541e19f62bea)

## <a name="configure-trusted-document-settings-in-office-policies"></a>Configurar la configuración de documentos de confianza en Office directivas

Los administradores tienen muchas formas de configurar Office en una organización. Por ejemplo:

- **Office de** directivas en la nube: configure una directiva basada en usuario que se aplique a un usuario en cualquier dispositivo que acceda a archivos de Office aplicaciones con su cuenta de Azure AD. Vea los pasos para [crear una configuración Office directiva de nube en](/DeployOffice/overview-office-cloud-policy-service) el Office Cloud Policy [Service](https://config.office.com/officeSettings/officePolicies).
- Office directivas en **Intune:** use el catálogo de Intune Configuración o las plantillas administrativas para implementar directivas HKCU en equipos Windows 10: en el Centro de administración de [MEM](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/configurationProfiles) en **Perfiles** de configuración de \> **dispositivos**.
  - ***Plantillas administrativas:*** vea las instrucciones para usar Windows 10 plantillas administrativas para configurar [plantillas administrativas](/mem/intune/configuration/administrative-templates-windows).
  - ***Configuración (versión preliminar):*** vea las instrucciones para usar el [Configuración (versión preliminar).](/mem/intune/configuration/settings-catalog)
- **Directiva de grupo:** use Active Directory local para implementar objetos de directiva de grupo (GPO) en usuarios y equipos. Para crear un GPO para esta configuración, descargue los archivos de plantilla administrativa más recientes (ADMX/ADML) y la herramienta de personalización de Office para [Aplicaciones Microsoft 365 para empresas, Office 2019 y Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

## <a name="admin-options-for-restricting-active-content"></a>Opciones de administración para restringir el contenido activo

Hay una gran diferencia en el nivel de confianza en el contenido creado internamente frente al contenido que los usuarios descargan de Internet. Considere la posibilidad de permitir contenido activo en documentos internos y globalmente no permitir contenido activo en documentos de Internet.

Si los usuarios no necesitan tipos específicos de contenido activo, la opción más segura es usar directivas para desactivar el acceso de los usuarios a ese contenido activo y permitir excepciones según sea necesario.

Las siguientes directivas están disponibles:

- **Desactivar Ubicaciones de confianza:** excepciones para grupos disponibles.
- **Desactivar Documentos de confianza:** excepciones para grupos disponibles.
- **Desactivar todo el contenido activo:** excepciones para individuos.

Las tablas de las secciones siguientes describen la configuración que controla el contenido activo. Estas directivas, si se aplican a los usuarios, se aplicarán en documentos de confianza y es posible que la experiencia del usuario final anterior no sea la misma. Las tablas también incluyen la configuración de líneas base de seguridad recomendadas e identifican otras opciones en las que el mensaje del usuario para invalidar está disponible (lo que permite al usuario habilitar el contenido activo).

### <a name="hkey_current_user-settings"></a>HKEY_CURRENT_USER configuración

<p>

****
|Categoría|Aplicación|Nombre de la directiva|Línea base de seguridad<br>configuración (recomendado)|Configuración con solicitud de usuario<br>y reemplazar disponible?|
|---|---|---|---|---|
|ActiveX|Office|ActiveX Inicialización de control|**6**|**Sí** para los siguientes valores: <ul><li>**3**</li><li>**4**</li><li>**5**</li><li>**6**</li></ul>|
|ActiveX|Office|Permitir formularios activos x uno desactivados|**Cargar sólo controles de Outlook**|No|
|ActiveX|Office|Comprobar objetos ActiveX|No es una configuración de línea base de seguridad.|No|
|ActiveX|Office|Deshabilitar todo ActiveX|No es una configuración de línea base de seguridad.|**Sí** para los siguientes valores: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|ActiveX|Office|Cargar controles en Formularios3|**1**|**Sí** para los siguientes valores: <ul><li>**2**</li><li>**3**</li></ul>|
|Extensibilidad de & complementos|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Deshabilitar la notificación de la barra de confianza para complementos de aplicaciones sin firma y bloquearlos|**Enabled**|**Sí** para el valor **Disabled**.|
|Extensibilidad de & complementos|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Requerir que un editor de confianza firme los complementos de aplicaciones|**Enabled**|No|
|Extensibilidad de & complementos|Excel|No mostrar la alerta de advertencia de Autorepublish|**Disabled**|No|
|Extensibilidad de & complementos|Excel|Notificación de función WEBSERVICE Configuración|**Deshabilitar todas con notificación**|**Sí** para los siguientes valores: <ul><li>**Deshabilitar todas con notificación**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Office|Deshabilitar el Office de sondeo del servidor SharePoint para los vínculos publicados|**Disabled**|No|
|Extensibilidad de & complementos|Office|Deshabilitar la UI que procede de documentos y plantillas|No permitir en Word = True <p> No permitir en Project = False <p> No permitir en Excel = True <p> No permitir en Visio= False <p> No permitir en PowerPoint = True <p> No permitir en Access = True <p> No permitir en Outlook = True <p> No permitir en Publisher = True <p> No permitir en InfoPath = True|No|
|Extensibilidad de & complementos|Outlook|Configurar el texto del modelo de objetos de Outlook al obtener acceso a una libreta de direcciones|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Configurar Outlook de modelo de objetos al obtener acceso a la propiedad Formula de un objeto UserProperty|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Configurar el texto del modelo de objetos de Outlook al ejecutar Guardar como|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Configurar el texto del modelo de objetos de Outlook al leer la información de la dirección|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Configurar el texto del modelo de objetos de Outlook al responder a convocatorias de reunión y solicitudes de tarea|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Configurar el texto del modelo de objetos de Outlook al enviar correo|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|Outlook|Establecer Outlook de ejecución de acciones personalizadas del modelo de objetos|**Denegar automáticamente**|**Sí** para los siguientes valores: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Extensibilidad de & complementos|PowerPoint|Ejecutar programas|**disable (no ejecute ningún programa)**|**Sí** para el valor **Enable (preguntar al usuario antes de ejecutarlo)**|
|Extensibilidad de & complementos|Word <p> Excel|Deshabilitar el uso de manifiestos de Smart Document|**Enabled**|No|
|DDE|Excel|No permitir el inicio del servidor de Exchange datos dinámicos (DDE) en Excel|**Enabled**|**Sí** para el valor **No configurado**.|
|DDE|Excel|No permitir la búsqueda de servidores de Exchange datos dinámicos (DDE) en Excel|**Enabled**|**Sí** para los siguientes valores: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|DDE|Word|Datos dinámicos Exchange|**Disabled**|No|
|Jscript & VBScript|Outlook|Permitir scripts en formularios de uso único de Outlook|**Disabled**|No|
|Jscript & VBScript|Outlook|No permitir que Outlook scripts del modelo de objetos se ejecuten para carpetas públicas|**Enabled**|No|
|Jscript & VBScript|Outlook|No permitir que Outlook scripts del modelo de objetos se ejecuten para carpetas compartidas|**Enabled**|No|
|Macros|Access <p> Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Notificación de macros de VBA Configuración|**Deshabilitar todas las macros excepto las firmadas digitalmente** <p> y <p> **Requerir que las macros las firme un editor de confianza**|**Sí** para los siguientes valores: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|Access <p> Excel <p> PowerPoint <p> Visio <p> Word|Impedir que las macros se ejecuten Office archivos de Internet|**Enabled**|**Sí** para los siguientes valores: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|Excel|Examinar macros cifradas en Excel libros de Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|Macros|Office|Permitir que VBA cargue referencias de tipolib por ruta de acceso desde ubicaciones de intranet que no son de confianza|**Disabled**|No|
|Macros|Office|Seguridad de automatización|**Usar nivel de seguridad de macro de aplicación**|No|
|Macros|Office|Deshabilitar comprobaciones de seguridad adicionales en las referencias de biblioteca VBA que pueden hacer referencia a ubicaciones no seguras en el equipo local|**Disabled**|No|
|Macros|Office|Ámbito de examen de tiempo de ejecución de macros|**Habilitar para todos los documentos**|No|
|Macros|Office|Solo confía en macros de VBA que usan firmas V3|No es una configuración de línea base de seguridad.|No|
|Macros|Outlook|Outlook Modo de seguridad|**Usar Outlook de grupo de seguridad**|Necesario para habilitar todas las Outlook GPO. <p> Se menciona como dependencia (esta directiva no bloquea el contenido activo en sí).|
|Macros|Outlook|Configuración de seguridad para macros|**Advertir para firmar, deshabilitar sin firmar**|**Sí** para los siguientes valores: <ul><li>**Advertir siempre**</li><li>**Advertir para firmar, deshabilitar sin firmar**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|PowerPoint|Examinar macros cifradas en PowerPoint presentaciones de Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|Macros|Publisher|Publisher Nivel de seguridad de automatización|**Mediante interfaz de usuario (preguntado)**|No|
|Macros|Word|Examinar macros cifradas en documentos de Word Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|

### <a name="hkey_local_machine-settings"></a>HKEY_LOCAL_MACHINE configuración

<p>

****
|Categoría|Aplicación|Nombre de la directiva|Línea base de seguridad<br>configuración (recomendado)|Configuración con solicitud de usuario<br>y reemplazar disponible?|
|---|---|---|---|---|
|ActiveX|Office|Restringir instalación de ActiveX |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|Extensibilidad de & complementos|Office|Administración de complementos |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|Extensibilidad de & complementos|Office|Bloquear la activación de Flash en Office documentos|Consulta los archivos ADMX/ADML de la Guía de seguridad de Microsoft para obtener una lista de killbits COM para bloquear toda activación para Flash en Microsoft 365 aplicaciones. Los archivos ADMX/ADML para las líneas base de seguridad empresariales están disponibles en el [Toolkit](https://www.microsoft.com/download/details.aspx?id=55319).|No|
|Jscript & VBScript|Office|Restringir la ejecución de JScript heredada para Office|**Habilitado:** <p> Access: 69632 <p> Excel: 69632 <p> OneNote: 69632 <p> Outlook: 69632 <p> PowerPoint: 69632 <p> Project: 69632 <p> Publisher: 69632 <p> Visio: 69632 <p> Word: 69632|No|
|Jscript & VBScript|Office|Restricciones de seguridad de ventanas con scripts |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|
