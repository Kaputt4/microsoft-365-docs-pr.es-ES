---
title: Administrar contenido activo en documentos de Office para administradores de TI
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.localizationpriority: medium
ms.service: microsoft-365-security
ms.collection:
- M365-security-compliance
- tier3
search.appverid:
- MET150
ROBOTS: NOINDEX,NOFOLOW
description: Los administradores pueden aprender a crear directivas para bloquear el contenido activo en documentos de Office
ms.openlocfilehash: b9eba7b71c34b38ba40cd63d824026d1ae28a182
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68063428"
---
# <a name="manage-active-content-in-office-documents"></a>Administrar contenido activo en documentos de Office

> [!NOTE]
> Las características que se describen en este artículo están en versión preliminar, no están disponibles para todos y están sujetas a cambios.

Los documentos de Office se pueden actualizar, actualizar o ejecutar automáticamente cuando contienen _contenido activo_. Algunos ejemplos de contenido activo son macros, controles ActiveX y complementos de Office. El contenido activo puede proporcionar una funcionalidad eficaz y útil a los usuarios, pero los atacantes también pueden usar contenido activo para entregar malware.

Los administradores pueden crear directivas de organización (directivas de grupo o directivas en la nube) que limiten el uso de contenido activo a conjuntos específicos de usuarios o para deshabilitar completamente el contenido activo. Los usuarios pueden configurar sus propias opciones de seguridad y privacidad en el Centro de confianza de Office en sus aplicaciones de Office en el **Centro de confianza** **de opciones** \> de **archivo**\>.

Anteriormente, cuando los usuarios identificaban documentos como documentos de confianza, su selección permitía que se ejecutara contenido activo, incluso si un administrador configuraba directivas para bloquear el contenido activo en documentos de Office. Ahora, las directivas establecidas por los administradores tienen prioridad sobre la identificación por parte del usuario de documentos de confianza. Este cambio en el comportamiento puede causar problemas a los usuarios.

La lógica actualizada del Centro de confianza se describe en el diagrama siguiente:

:::image type="content" source="../media/office-trust-center-flow.png" alt-text="Gráfico de flujo que describe la lógica del centro de confianza en el portal de Microsoft 365 Defender" lightbox="../media/office-trust-center-flow.png":::

1. Un usuario abre un documento de Office que contiene contenido activo.

2. Si el documento procede de una ubicación de confianza, el documento se abre con el contenido activo habilitado. Si el documento no procede de una ubicación de confianza, la evaluación continúa.

3. Es aquí donde el comportamiento actualizado surte efecto:
   - Anteriormente, la siguiente configuración evaluada habría sido si el usuario hubiera identificado este documento como un documento de confianza. Si lo hicieran, el documento se abriría con el contenido activo habilitado.
   - Ahora, no se considera aquí si el usuario identificó el documento como un documento de confianza (ahora en el paso 8).

     El cambio fundamental en el comportamiento se describe de la siguiente manera: las directivas en la nube (paso 4), las directivas de grupo (paso 6) y la configuración local (paso 7) se comprueban _antes_ de que se tenga en cuenta la designación del usuario de un documento de confianza. Si alguno de esos pasos bloquea el acceso al contenido activo **y** ninguno de los pasos permite invalidaciones de usuario, la identificación por parte del usuario del documento como documento de confianza es irrelevante.

4. Las directivas en la nube se comprueban para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo no está bloqueado, la evaluación continúa en el paso 6.

   Si la directiva bloquea el contenido activo, la experiencia se describe en el paso 5.

5. La apertura del documento se bloquea con una notificación en la barra de confianza. Lo que sucede a continuación se controla mediante la configuración de invalidación de usuario en la directiva: a. **Invalidación de usuario no permitida**: el usuario no puede abrir el documento y la evaluación se detiene.
   b. **Invalidación de usuario permitida**: el usuario puede hacer clic en el vínculo de la barra de confianza para abrir el documento con el contenido activo habilitado.

6. Las directivas de grupo se comprueban para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo no está bloqueado, la evaluación continúa en el paso 7.

   Si la directiva bloquea el contenido activo, la experiencia se describe en el paso 5.

7. Se comprueba la configuración local para ver si este tipo de contenido activo está permitido o bloqueado. Si el contenido activo está bloqueado, la apertura del documento se bloquea con una notificación en la barra de confianza. Si el contenido activo no está bloqueado, la evaluación continúa.

8. Si el usuario identificó previamente el documento como un documento de confianza, el documento se abre con el contenido activo habilitado. Si no es así, se bloquea la apertura del documento.

## <a name="what-is-a-trusted-document"></a>¿Qué es un documento de confianza?

Los documentos de confianza son documentos de Office que se abren sin avisos de seguridad para macros, controles ActiveX y otros tipos de contenido activo en el documento. Vista protegida o Protección de aplicaciones no se usa para abrir el documento. Cuando los usuarios abren un documento de confianza y todo el contenido activo está habilitado. Incluso si el documento contiene nuevo contenido activo o actualizaciones del contenido activo existente, los usuarios no recibirán mensajes de seguridad la próxima vez que abran el documento.

Debido a este comportamiento, los usuarios deben confiar claramente en los documentos solo si confían en el origen del documento.

Si un administrador bloquea el contenido activo mediante una directiva o si los usuarios establecen una configuración del Centro de confianza que bloquea el contenido activo, el contenido activo permanecerá bloqueado.

Para más información, consulte los siguientes artículos:

- [Documentos confiables](https://support.microsoft.com/topic/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53)
- [Agregar, quitar o cambiar una ubicación de confianza](https://support.microsoft.com/topic/add-remove-or-change-a-trusted-location-7ee1cdc2-483e-4cbb-bcb3-4e7c67147fb4)
- [Tipos de contenido activos en los archivos](https://support.microsoft.com/topic/active-content-types-in-your-files-b7ff2e8a-4055-47d4-8c7d-541e19f62bea)

## <a name="configure-trusted-document-settings-in-office-policies"></a>Configuración de la configuración de documentos de confianza en directivas de Office

Los administradores tienen muchas maneras de configurar Office en una organización. Por ejemplo:

- **Servicio de directivas** en la nube de Office: configure una directiva basada en el usuario que se aplique a un usuario en cualquier dispositivo que acceda a archivos de aplicaciones de Office con su cuenta de Azure AD. Consulte los pasos para [crear una configuración de directiva](/DeployOffice/overview-office-cloud-policy-service) en la nube de Office en el [servicio de directivas en la nube de Office](https://config.office.com/officeSettings/officePolicies).
- **Directivas de Office en Intune**: use el catálogo de configuración de Intune o plantillas administrativas para implementar directivas HKCU en equipos Windows 10: en el [Centro de administración de MEM](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/configurationProfiles), en **Perfiles de configuración** de **dispositivos**\>.
  - ***Plantillas administrativas***: consulte las instrucciones para usar plantillas de Windows 10 para configurar [plantillas administrativas](/mem/intune/configuration/administrative-templates-windows).
  - ***Catálogo de configuración (versión preliminar):*** consulte las instrucciones para usar el [catálogo configuración (versión preliminar).](/mem/intune/configuration/settings-catalog)
- **Directiva de grupo**: use active directory local para implementar objetos de directiva de grupo (GPO) en usuarios y equipos. Para crear un GPO para esta configuración, descargue los [archivos de plantilla administrativa más recientes (ADMX/ADML) y la Herramienta de personalización de Office para Aplicaciones Microsoft 365 para empresas, Office 2019 y Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

## <a name="known-issues"></a>Problemas conocidos

- Cuando las **notificaciones de macro de VBA** de la directiva (Access, PowerPoint, Visio, Word) o **Las notificaciones de macro** (Excel) se establecen en el valor **Deshabilitar todas excepto las macros firmadas digitalmente**, no se muestra la barra de confianza esperada y la **información de seguridad** en el backstage no muestra los detalles de las macros bloqueadas, aunque la configuración funcione según lo esperado. El equipo de Office está trabajando para resolver este problema.

## <a name="admin-options-for-restricting-active-content"></a>Administración opciones para restringir el contenido activo

Hay una gran diferencia en el nivel de confianza en el contenido creado internamente frente al contenido que los usuarios descargan de Internet. Considere la posibilidad de permitir el contenido activo en documentos internos y no permitir globalmente el contenido activo en documentos de Internet.

Si los usuarios no necesitan tipos específicos de contenido activo, la opción más segura es usar directivas para desactivar el acceso de los usuarios a ese contenido activo y permitir excepciones según sea necesario.

Están disponibles las siguientes directivas:

- **Desactivar Ubicaciones de confianza**: excepciones para los grupos disponibles.
- **Desactivar documentos de confianza**: excepciones para los grupos disponibles.
- **Desactivar todo el contenido activo**: excepciones para individuos.

Las tablas de las secciones siguientes describen la configuración que controla el contenido activo. Estas directivas, si se aplican a los usuarios, se aplicarán en documentos de confianza y es posible que la experiencia anterior del usuario final no sea la misma. Las tablas también incluyen la configuración de líneas base de seguridad recomendadas e identifican otras opciones en las que está disponible la solicitud de invalidación del usuario (lo que permite al usuario habilitar el contenido activo).

### <a name="hkey_current_user-settings"></a>configuración de HKEY_CURRENT_USER

<p>

****
|Categoría|Aplicación|Nombre de la directiva|Línea base de seguridad<br>configuración (recomendado)|Configuración con el símbolo del usuario<br>e invalidar disponibles?|
|---|---|---|---|---|
|Activex|Oficina|Inicialización del control ActiveX|**6**|**Sí** para los valores siguientes: <ul><li>**3**</li><li>**4**</li><li>**5**</li><li>**6**</li></ul>|
|Activex|Oficina|Permitir formularios desactivados de X One activo|**Cargar sólo controles de Outlook**|No|
|Activex|Oficina|Comprobar objetos ActiveX|No es una configuración de línea base de seguridad.|No|
|Activex|Oficina|Deshabilitar todo ActiveX|No es una configuración de línea base de seguridad.|**Sí** para los valores siguientes: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Activex|Oficina|Cargar controles en Formularios3|**1**|**Sí** para los valores siguientes: <ul><li>**2**</li><li>**3**</li></ul>|
|Complementos & extensibilidad|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Deshabilitar la notificación de la barra de confianza para complementos de aplicación sin firmar y bloquearlos|**Enabled**|**Sí** para el valor **Deshabilitado**.|
|Complementos & extensibilidad|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Requerir que un editor de confianza firme los complementos de aplicaciones|**Enabled**|No|
|Complementos & extensibilidad|Excel|No mostrar alerta de advertencia de publicación automática|**Disabled**|No|
|Complementos & extensibilidad|Excel|Configuración de notificación de función WEBSERVICE|**Deshabilitar todas con notificación**|**Sí** para los valores siguientes: <ul><li>**Deshabilitar todas con notificación**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Oficina|Deshabilitación del cliente de Office para que no sondee los vínculos publicados en SharePoint Server|**Disabled**|No|
|Complementos & extensibilidad|Oficina|Deshabilitar la UI que procede de documentos y plantillas|No permitir en Word = True <p> No permitir en Project = False <p> No permitir en Excel = True <p> No permitir en Visio= False <p> No permitir en PowerPoint = True <p> No permitir en Access = True <p> No permitir en Outlook = True <p> No permitir en Publisher = True <p> No permitir en InfoPath = True|No|
|Complementos & extensibilidad|Outlook|Configurar el texto del modelo de objetos de Outlook al obtener acceso a una libreta de direcciones|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Configurar el símbolo del modelo de objetos de Outlook al acceder a la propiedad Formula de un objeto UserProperty|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Configurar el texto del modelo de objetos de Outlook al ejecutar Guardar como|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Configurar el texto del modelo de objetos de Outlook al leer la información de la dirección|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Configurar el texto del modelo de objetos de Outlook al responder a convocatorias de reunión y solicitudes de tarea|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Configurar el texto del modelo de objetos de Outlook al enviar correo|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|Outlook|Establecimiento del símbolo del sistema de ejecución de acciones personalizadas del modelo de objetos de Outlook|**Denegar automáticamente**|**Sí** para los valores siguientes: <ul><li>**Preguntar al usuario**</li><li>**Pedir confirmación del usuario en función de la seguridad del equipo**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Complementos & extensibilidad|PowerPoint|Ejecución de programas|**disable (no ejecute ningún programa)**|**Sí** para el valor **Habilitar (preguntar al usuario antes de ejecutarlo)**|
|Complementos & extensibilidad|Word <p> Excel|Deshabilitar el uso de manifiestos por parte de Smart Document|**Enabled**|No|
|Dde|Excel|No permitir el inicio del servidor de Intercambio dinámico de datos (DDE) en Excel|**Enabled**|**Sí** para el valor **No configurado**.|
|Dde|Excel|No permitir la búsqueda de servidores de Intercambio dinámico de datos (DDE) en Excel|**Enabled**|**Sí** para los valores siguientes: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Dde|Word|Intercambio dinámico de datos|**Disabled**|No|
|Jscript & VBScript|Outlook|Permitir scripts en formularios de uso único de Outlook|**Disabled**|No|
|Jscript & VBScript|Outlook|No permitir que los scripts del modelo de objetos de Outlook se ejecuten para carpetas públicas|**Enabled**|No|
|Jscript & VBScript|Outlook|No permitir que los scripts del modelo de objetos de Outlook se ejecuten para carpetas compartidas|**Enabled**|No|
|Macros|Excel|Notificaciones de macro|**Deshabilitar todas las macros excepto las firmadas digitalmente**|**Sí** para los valores siguientes: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|Acceso <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|Configuración de notificación de macros de VBA|**Deshabilitar todas las macros excepto las firmadas digitalmente** <p> y <p> **Requerir que las macros estén firmadas por un publicador de confianza**|**Sí** para los valores siguientes: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|Acceso <p> Excel <p> PowerPoint <p> Visio <p> Word|Impedir que las macros se ejecuten en archivos de Office desde Internet|**Enabled**|**Sí** para los valores siguientes: <ul><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|Excel|Examen de macros cifradas en libros De Excel Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|Macros|Oficina|Permitir que VBA cargue referencias de biblioteca de tipos por ruta de acceso desde ubicaciones de intranet que no son de confianza|**Disabled**|No|
|Macros|Oficina|Seguridad de automation|**Usar nivel de seguridad de macro de aplicación**|No|
|Macros|Oficina|Deshabilitar otras comprobaciones de seguridad en referencias de biblioteca vba que puedan hacer referencia a ubicaciones no seguras en el equipo local|**Disabled**|No|
|Macros|Oficina|Ámbito de examen en tiempo de ejecución de macros|**Habilitar para todos los documentos**|No|
|Macros|Oficina|Solo las macros de VBA de confianza que usan firmas V3|No es una configuración de línea base de seguridad.|No|
|Macros|Outlook|Modo de seguridad de Outlook|**Uso de Outlook Security directiva de grupo**|Necesario para habilitar toda la configuración de GPO de Outlook. <p> Se menciona como una dependencia (esta directiva no bloquea el contenido activo en sí).|
|Macros|Outlook|Configuración de seguridad para macros|**Advertir para firmar, deshabilitar sin firmar**|**Sí** para los valores siguientes: <ul><li>**Advertir siempre**</li><li>**Advertir para firmar, deshabilitar sin firmar**</li><li>**Disabled**</li><li>**Sin configurar**</li></ul>|
|Macros|PowerPoint|Examen de macros cifradas en presentaciones de PowerPoint Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|Macros|Publisher|Nivel de seguridad de Publisher Automation|**Mediante interfaz de usuario (preguntado)**|No|
|Macros|Word|Examen de macros cifradas en documentos De Word Open XML|**Examinar macros cifradas (valor predeterminado)**|No|
|

### <a name="hkey_local_machine-settings"></a>configuración de HKEY_LOCAL_MACHINE

<p>

****
|Categoría|Aplicación|Nombre de la directiva|Línea base de seguridad<br>configuración (recomendado)|Configuración con el símbolo del usuario<br>e invalidar disponibles?|
|---|---|---|---|---|
|Activex|Oficina|Restringir instalación de ActiveX |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|Complementos & extensibilidad|Oficina|Administración de complementos |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|Complementos & extensibilidad|Oficina|Bloquear la activación flash en documentos de Office|Consulte los archivos ADMX/ADML de la Guía de seguridad de Microsoft para obtener una lista de bits de eliminación COM para bloquear toda la activación de Flash en aplicaciones de Microsoft 365. Los archivos ADMX/ADML para líneas base de seguridad empresariales están disponibles en security [compliance toolkit](https://www.microsoft.com/download/details.aspx?id=55319).|No|
|Jscript & VBScript|Oficina|Restricción de la ejecución de JScript heredada para Office|**Habilitado**: <p> Acceso: 69632 <p> Excel: 69632 <p> OneNote: 69632 <p> Outlook: 69632 <p> PowerPoint: 69632 <p> Proyecto: 69632 <p> Publicador: 69632 <p> Visio: 69632 <p> Palabra: 69632|No|
|Jscript & VBScript|Oficina|Restricciones de seguridad de ventanas con scripts |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|No|
|
