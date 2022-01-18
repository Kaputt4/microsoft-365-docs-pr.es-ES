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
ms.localizationpriority: high
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Información para que los administradores de TI administren las etiquetas de confidencialidad en las aplicaciones de Office para escritorio, móvil y web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d13c587c86874354e05422b2ff105d923e234c61
ms.sourcegitcommit: dbce0b6e74ae2efec42fe2b3b82c8e8cabe0ddbe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "62054889"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Administrar etiquetas de confidencialidad en las aplicaciones de Office

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Cuando haya [publicado](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) etiquetas de confidencialidad desde el Centro de cumplimiento de Microsoft 365 o un centro de etiquetado equivalente, empezarán a aparecer en las apps de Office para que los usuarios clasifiquen y protejan los datos a medida que se creen o editen.

Use la información de este artículo para ayudarle a administrar correctamente las etiquetas de confidencialidad en las aplicaciones de Office. Por ejemplo, identifique las versiones mínimas de las aplicaciones que necesita para ser compatible con el etiquetado integrado y comprenda las interacciones con el cliente de etiquetado unificado de Azure Information Protection y la compatibilidad con otras aplicaciones y servicios.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de etiquetado para aplicaciones de escritorio

Para usar las etiquetas de confidencialidad integradas en las aplicaciones de escritorio de Office para Windows y Mac, debe utilizar una edición de suscripción de Office. Este cliente de etiquetado no es compatible con las ediciones independientes de Office, como Office 2016 u Office 2019.

Para usar las etiquetas de confidencialidad con estas ediciones independientes de Office en equipos Windows, instale el [cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Compatibilidad con las funciones de las etiquetas de confidencialidad en las aplicaciones

Para cada función, las siguientes tablas enumeran la versión mínima de Office que se necesita para que sea compatible con las etiquetas de confidencialidad utilizando el etiquetado integrado. O bien, si la función de la etiqueta está en vista previa pública o en revisión para una versión futura. Use el [plan de desarrollo de Microsoft 365](https://aka.ms/MIPC/Roadmap) para obtener detalles sobre las nuevas funcionalidades que están planeadas para futuras versiones.

Las nuevas versiones de las aplicaciones de Office están disponibles en diferentes momentos para diferentes canales de actualización. Para Windows, las nuevas funciones se obtienen antes cuando se encuentra en el Canal actual o el Canal mensual para empresas, en lugar del Canal semestral para empresas. Los números de versión mínimos también pueden ser diferentes de un canal de actualización al siguiente. Para obtener más información, vea [Introducción a los canales de actualización para las Aplicaciones de Microsoft 365](/deployoffice/overview-update-channels) y [Actualizar historial para las Aplicaciones Microsoft 365](/officeupdates/update-history-microsoft365-apps-by-date).

Las nuevas funciones que están en vista previa privada no se incluyen en la tabla, pero es posible que pueda unirse a estas vistas previas nominando a su organización para el programa de vista previa privada de [Microsoft Information Protection](https://aka.ms/mip-preview).

Office para iOS y Office para Android: Las etiquetas de confidencialidad están integradas en las [aplicación de Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Las funciones adicionales están disponibles cuando se instala el cliente de etiquetado unificado de Azure Information Protection, que se ejecuta sólo en equipos Windows. Para conocer estos detalles, consulte [Comparar los clientes de etiquetado para equipos con Windows](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

> [!TIP]
> Al comparar las versiones mínimas en las tablas con las versiones que tiene, recuerde que es común que las versiones de lanzamiento omitan los ceros iniciales.
> 
> Por ejemplo, tiene la versión 4.2128.0 y la 4.7.1+ es la versión mínima. Para facilitar la comparación, 4.7.1 (sin ceros iniciales) sería 4.**0007**.1 (y no 4.**7000**.1). Su versión de 4.2128.0 es posterior a la 4.0007.1, por lo que es compatible.

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funciones de etiquetas de confidencialidad en Word, Excel y PowerPoint

Los números indicados son las versiones mínimas de la aplicación Office requeridas para cada función. 

> [!NOTE]
> Para Windows y el Canal empresarial semestral, es posible que aún no se hayan publicado los números de versión mínimos admitidos. [Más información](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)
 
|Funcionalidad |Windows |Mac |iOS |Android |Web |
|-----------|-------:|----|----|--------|----|
|[Aplicar, cambiar o eliminar manualmente la etiqueta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do) a nuevos documentos                                         | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do) a documentos existentes | Vista previa: [Canal Beta](https://office.com/insider) | Vista previa: [Canal Beta](https://office.com/insider) | En revisión | En revisión | Implementar: [Sí: participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Requerir una justificación para cambiar una etiqueta.](sensitivity-labels.md#what-label-policies-can-do)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+  <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada.](sensitivity-labels.md#what-label-policies-can-do)                       | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables).                                              | Canal actual: 2010+ <br /><br> Canal mensual para empresas: 2010+ <br /><br> Canal semestral para empresas: 2102+ | 16.42+     | 2.42+ | 16.0.13328+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir a los usuarios asignar permisos: <br /> - Solicitar a los usuarios](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |Canal actual: 2004+ <br /><br> Canal mensual para empresas: 2004+ <br /><br> Canal semestral para empresas: 2008+ | 16.35+   | En revisión   | En revisión         | En revisión                                                        |
|[Auditoría de la actividad de los usuarios relacionada con las etiquetas](data-classification-activity-explorer.md)                      | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ | 2.46+ | 16.0.13628+ | Si <sup>\*</sup>                                                        |
|[Requerir a los usuarios que apliquen una etiqueta a sus correos electrónicos y documentos ](#require-users-to-apply-a-label-to-their-email-and-documents)   | Canal actual: 2101+ <br /><br> Canal mensual para empresas: 2101+ <br /><br> Canal semestral para empresas: 2108+ | 16.45+         | 2.47+ | 16.0.13628+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de tipos de información confidencial                    | Canal actual: 2009+ <br /><br> Canal mensual para empresas: 2009+ <br /><br> Canal semestral para empresas: 2102+ | 16.44+ | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de clasificadores capacitados                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2018+ | En revisión | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Compatibilidad con la coautoría y el autoguardado](sensitivity-labels-coauthoring.md) documentos etiquetados y cifrados | Canal actual: 2107+ <br /><br> Canal mensual para empresas: 2107+ <br /><br> Canal semestral para empresas: 2202+ |  16.51+ | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Notas al pie:**

<sup>\*</sup> Actualmente, no incluye un texto de justificación para eliminar una etiqueta o bajar el nivel de clasificación

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funciones de la etiqueta de confidencialidad en Outlook

Los números indicados son las versiones mínimas de la aplicación Office requeridas para cada función. 

> [!NOTE]
> Para Windows y el Canal empresarial semestral, es posible que aún no se hayan publicado los números de versión mínimos admitidos. [Más información](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)

|Funcionalidad |Outlook para Windows |Outlook para Mac |Outlook en iOS |Outlook en Android |Outlook en la Web |
|-----------|-------------------:|----------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o eliminar manualmente la etiqueta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Requerir una justificación para cambiar una etiqueta.](sensitivity-labels.md#what-label-policies-can-do)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada.](sensitivity-labels.md#what-label-policies-can-do)                       | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables).                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Permitir a los usuarios asignar permisos: <br /> - No reenviar](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Permitir a los usuarios asignar permisos: <br /> - Solo cifrar](encryption-sensitivity-labels.md#let-users-assign-permissions)  | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: 2108+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Sí |
|[Requerir a los usuarios que apliquen una etiqueta a sus correos electrónicos y documentos ](#require-users-to-apply-a-label-to-their-email-and-documents)   | Canal actual: 2101+ <br /><br> Canal mensual para empresas: 2101+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Sí                |
|[Auditoría de la actividad de los usuarios relacionada con las etiquetas](data-classification-activity-explorer.md) | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: en revisión | 16.51+ <sup>\*</sup> | 4.2126+ | 4.2126+ | Sí |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de tipos de información confidencial                    | Canal actual: 2009+ <br /><br> Canal mensual para empresas: 2009+ <br /><br> Canal semestral para empresas: 2102+ | 16.44+ <sup>\*</sup>                    | En revisión           | En revisión               | Sí |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de clasificadores capacitados                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2108+ | En revisión                    | En revisión           | En revisión               | Sí |
|[Diferentes opciones de configuración para etiquetas predeterminadas y etiquetas obligatorias](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Sí |
|

**Notas al pie:**

<sup>\*</sup> Se requiere el [nuevo Outlook para Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de etiquetado integrado en Office y otras soluciones de etiquetado

El cliente de etiquetado integrado de Office descarga las etiquetas de confidencialidad y la configuración de la política de etiquetas de confidencialidad desde el Centro de cumplimiento de Microsoft 365. 

Para usar el cliente de etiquetado integrado de Office, debe tener una o más [directivas de etiquetado publicadas ](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)para los usuarios desde uno de los centros de administración enumerados y una [ versión compatible de Office](#support-for-sensitivity-label-capabilities-in-apps).

Si se cumplen ambas condiciones, pero necesita desactivar las etiquetas integradas en las aplicaciones de Office, use la siguiente configuración de directiva de grupo:

1. Navegar a **Configuración de usuario/Plantillas administrativas/Microsoft Office 2016/Configuración de seguridad**.

2. Establecer **Usar la función de confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad** a **0**. 
 
Implementar esta configuración mediante la directiva de grupo o mediante el [Servicio de directiva de la nube de Office](/DeployOffice/overview-office-cloud-policy-service). La configuración tiene efecto cuando se reinician las aplicaciones de Office.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>El cliente de etiquetado integrado de Office y el cliente de Azure Information Protection

Si los usuarios tienen el [Azure Information Protection cliente](/azure/information-protection/rms-client/aip-clientv2) instalado en sus equipos Windows, de forma predeterminada, las etiquetas integradas se desactivan en [Aparecen aplicaciones de Office que las admiten](#labeling-client-for-desktop-apps). Dado que las etiquetas integradas no usan un complemento de Office, tal y como las usa el cliente de Azure Information Protection, tienen la ventaja de una mayor estabilidad y un mejor rendimiento. También admiten las características más recientes, como clasificadores avanzados.

En lugar de desinstalar el cliente de Azure Information Protection, se recomienda evitar que el complemento de Azure Information Protection se cargue en las aplicaciones de Office. A continuación, obtendrá las ventajas del etiquetado integrado en las aplicaciones de Office y las ventajas de los archivos de etiquetado de cliente de Azure Information Protection fuera de las aplicaciones de Office. Por ejemplo, el cliente de Azure Information Protection puede etiquetar todos los tipos de archivo mediante Explorador de archivos y PowerShell. Para obtener más información sobre las características de etiquetado compatibles fuera de las aplicaciones de Office, vea [Etiquetas de confidencialidad y Azure Information Protection](sensitivity-labels.md#sensitivity-labels-and-azure-information-protection).

Para evitar que el complemento de cliente de Azure Information Protection se cargue en las aplicaciones de Office, use la configuración de directiva de grupo **Lista de complementos administrados** como se documenta en [No hay complementos cargados debido a la configuración de directiva de grupo para los programas de Office 2013 y Office 2016](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

Para las aplicaciones de Office que admiten el etiquetado integrado, use la configuración de Microsoft Word 2016, Excel 2016, PowerPoint 2016 y Outlook 2016, especifique los siguientes identificadores de programación (ProgID) para el cliente de Azure Information Protection y establezca la opción en **0: el complemento siempre está deshabilitado (bloqueado)**

|Aplicación  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

Implementar esta configuración mediante la directiva de grupo o mediante el [Servicio de directiva de la nube de Office](/DeployOffice/overview-office-cloud-policy-service).

> [!IMPORTANT]
> Si usa la configuración de directiva de grupo **Use la característica Confidencialidad de Office para aplicar y ver las etiquetas de confidencialidad** y establecerla en **1**, hay algunas situaciones en las que el cliente de Azure Information Protection puede seguir cargando en las aplicaciones de Office. Bloquear la carga del complemento en cada aplicación impide que esto suceda.

Como alternativa, puede deshabilitar o quitar de forma interactiva el complemento de Office **Microsoft Azure Information Protection** de Word, Excel, PowerPoint y Outlook. Este método es adecuado para un solo ordenador y para pruebas ad hoc. Para obtener instrucciones, consulte [Ver, administrar e instalar complementos en los programas de Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Independientemente del método que elija, los cambios surtirán efecto cuando se reinicien las aplicaciones de Office.

Para obtener información sobre las características son compatibles con los clientes de Azure Information Protection y el cliente de etiquetado integrado de Office, consulte [Elegir la solución de etiquetado de Windows en la documentación](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) de Azure Information Protection.

## <a name="office-file-types-supported"></a>Tipos de archivos compatibles con Office

Las aplicaciones de Office que tienen etiquetado integrado para archivos de Word, Excel y PowerPoint admiten el formato Open XML (como .docx y .xlsx), pero no el formato de Microsoft Office 97-2003 (como .doc y .xls), formato de documento abierto (como .odt y .ods) u otros formatos. Cuando no se admite un tipo de archivo para el etiquetado integrado, el botón de **confidencialidad** no está disponible en la aplicación de Office.

El cliente de etiquetado unificado de Azure Information Protection es compatible tanto con el formato Open XML como con el formato de Microsoft Office 97-2003. Para obtener más información, consulte [Tipos de archivos compatibles con el cliente de etiquetado unificado de Azure Information Protection ](/azure/information-protection/rms-client/clientv2-admin-guide-file-types)en la guía de administración de dicho cliente.

Para otras soluciones de etiquetado, compruebe en su documentación los tipos de archivo compatibles.

## <a name="protection-templates-and-sensitivity-labels"></a>Plantillas de protección y etiquetas de confidencialidad

Las [plantillas de protección](/azure/information-protection/configure-policy-templates) definidas por el administrador, como las que se definen para el Cifrado de mensajes de Office 365, no son visibles en las aplicaciones de Office cuando se utiliza el etiquetado integrado. Esta experiencia simplificada refleja que no es necesario seleccionar una plantilla de protección, ya que los mismos ajustes se incluyen con las etiquetas de confidencialidad que tienen el cifrado activado.

Puede convertir una plantilla existente en una etiqueta de confidencialidad cuando use el cmdlet [New-Label](/powershell/module/exchange/new-label) con el parámetro *EncryptionTemplateId*.

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opciones de administración de derechos de información (IRM) y etiquetas de confidencialidad

Las etiquetas de confidencialidad que se configuran para aplicar el cifrado eliminan la complejidad de que los usuarios especifiquen su propia configuración de cifrado. En muchas aplicaciones de Office, los usuarios pueden seguir configurando manualmente estos ajustes de cifrado individuales mediante las opciones de Information Rights Management (IRM). Por ejemplo, para las aplicaciones de Windows:

- Para un documento:  **Archivo** > **Información** > **Proteger documento** > **Restringir el acceso**
- para un correo electrónico: en la pestaña **Opciones** > **Cifrar** 
  
Cuando los usuarios etiquetan inicialmente un documento o correo electrónico, pueden anular los ajustes de configuración de la etiqueta con sus propios ajustes de cifrado. Por ejemplo:

- Un usuario aplica la etiqueta **Confidencial/todos los empleados** a un documento y esta etiqueta está configurada para aplicar la configuración de cifrado a todos los usuarios de la organización. A continuación, este usuario configura manualmente los ajustes del IRM para restringir el acceso a un usuario ajeno a su organización. El resultado final es un documento etiquetado como **Confidencial/todos los empleados** y encriptado, pero los usuarios de su organización no pueden abrirlo como se esperaba.

- Un usuario aplica la etiqueta **Confidencial/sólo para destinatarios** a un correo electrónico y este correo está configurado para aplicar la configuración de cifrado de **No reenviar**. En la aplicación de Outlook, este usuario selecciona manualmente la configuración de IRM para Solo cifrar. El resultado final es que aunque el correo siga cifrado, puede ser reenviado por los destinatarios, a pesar de tener la etiqueta de **Confidencial/Solo para destinatarios**.
    
    Como excepción, en el caso de Outlook en la Web, las opciones del menú **Cifrar** no están disponibles para que el usuario las seleccione cuando la etiqueta seleccionada actualmente aplica el cifrado.

- Un usuario aplica la etiqueta **General** un documento, y esta etiqueta no está configurada para aplicar el cifrado. A continuación, este usuario configura manualmente los parámetros del IRM para restringir el acceso al documento. El resultado final es un documento etiquetado **General**, pero que también aplica un cifrado para que algunos usuarios no puedan abrirlo como se espera.

Si el documento o el correo electrónico ya está etiquetado, un usuario puede realizar cualquiera de estas acciones si el contenido no está ya encriptado, o tiene el [derecho de uso ](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Exportar o Control total. 

Para una experiencia de etiquetado más uniforme con los informes significativos, proporcione etiquetas y orientación adecuadas para que los usuarios apliquen solo etiquetas para proteger los documentos y correos electrónicos. Por ejemplo:

- Para los casos excepcionales en los que los usuarios deben asignar sus propios permisos, proporcione etiquetas que [permitan a los usuarios asignar sus propios permisos](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- En lugar de que los usuarios eliminen manualmente el cifrado después de seleccionar una etiqueta que aplique cifrado, proporcione una alternativa de subetiqueta cuando los usuarios necesiten una etiqueta con la misma clasificación, pero sin cifrado. Como:
    - **Confidencial/todos los empleados**
    - **Confidencial/cualquiera (sin cifrado)**

- Puede deshabilitar la configuración de IRM para impedir que los usuarios los seleccionen:
    - Outlook para Windows: 
        - Claves del Registro (DWORD:00000001) *DisableDNDE* y *DisableEO* de HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DOMAIN
        - Asegúrese de que la configuración de directiva de grupo **Configuración de cifrado predeterminada para el botón Cifrar** no está configurada
    - Outlook para Mac: 
        - Claves *DisableEncryptOnly* y *DisableDoNotForward* documentadas en [Establecer preferencias para Outlook para Mac](/DeployOffice/mac/preferences-outlook)
    - Outlook en la web: 
        - Parámetros *SimplifiedClientAccessDoNotForwardDisabled* y *SimplifiedClientAccessEncryptOnlyDisabled* documentados para [Set-IRMConfiguración](/powershell/module/exchange/set-irmconfiguration)
    - Outlook para iOS y Android: estas aplicaciones no admiten que los usuarios apliquen cifrado sin etiquetas, por lo que no hay nada que deshabilitar.

> [!NOTE]
> Si los usuarios eliminan manualmente el cifrado de un documento etiquetado que está almacenado en SharePoint o OneDrive y usted ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), el cifrado de la etiqueta se restaurará automáticamente la próxima vez que se acceda al documento o se descargue. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar etiquetas de confidencialidad a los archivos, correos electrónicos y archivos adjuntos

Los usuarios pueden aplicar una sola etiqueta a la vez para cada documento o correo electrónico.

Cuando etiqueta un mensaje de correo electrónico que tiene archivos adjuntos, los archivos adjuntos heredan la etiqueta solo si la etiqueta que aplica al mensaje de correo electrónico aplica cifrado y el archivo adjunto es un documento de Office que aún no está cifrado. Debido a que la etiqueta heredada aplica cifrado, el archivo adjunto se vuelve a cifrar.

Un archivo adjunto no hereda las etiquetas del mensaje de correo electrónico cuando la etiqueta aplicada al mensaje de correo electrónico no aplica el cifrado o el archivo adjunto ya está cifrado.

Ejemplos de herencia de etiquetas, donde la etiqueta **Confidencial** aplica encriptación y la etiqueta **General** no aplica encriptación:

- Un usuario crea un nuevo mensaje de correo electrónico y le aplica la etiqueta **Confidencial**. A continuación, agregan un documento de Word que no está etiquetado ni cifrado. Como resultado de la herencia, el documento recibe la nueva etiqueta de **Confidencial** y ahora se le aplica el cifrado a partir de esa etiqueta.

- Un usuario crea un nuevo mensaje de correo electrónico y le aplica la etiqueta **Confidencial**. A continuación, agregan un documento de Word con la etiqueta **General** y este archivo no está cifrado. Como resultado de la herencia, el documento se etiqueta de nuevo como **Confidencial** y ahora se le aplica el cifrado a partir de esa etiqueta.

## <a name="sensitivity-label-compatibility"></a>Compatibilidad con la etiqueta de confidencialidad

**Con las aplicaciones con RMS**: si abre un documento o correo electrónico etiquetado y cifrado en una [aplicación con RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications)que no es compatible con las etiquetas de confidencialidad, la aplicación sigue aplicando el cifrado y la administración de derechos.

**Con el cliente de Azure Information Protection**: puede ver y cambiar las etiquetas de confidencialidad que aplica a los documentos y correos electrónicos con el cliente de etiquetado integrado de Office utilizando el cliente de Azure Information Protection, y al revés

**Con otras versiones de Office**: cualquier usuario autorizado puede abrir documentos y correos electrónicos etiquetados en otras versiones de Office. Sin embargo, sólo puede ver o cambiar la etiqueta en las versiones de Office compatibles o utilizando el cliente de Azure Information Protection. Las versiones de la aplicación de Office compatibles se enumeran en la [sección anterior ](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Compatibilidad para archivos de SharePoint y OneDrive protegidos por etiquetas de confidencialidad

Para utilizar el cliente de etiquetado integrado de Office con Office en la web para los documentos en SharePoint o OneDrive, asegúrese de haber [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Compatibilidad con usuarios externos y contenidos etiquetados

Cuando se etiqueta un documento o un correo electrónico, la etiqueta se almacena como metadatos que incluyen su inquilino y un GUID de la etiqueta. Cuando un documento o correo electrónico etiquetado es abierto por una aplicación de Office que admite etiquetas de confidencialidad, estos metadatos se leen y sólo si el usuario pertenece al mismo tenant, la etiqueta se muestra en su aplicación. Por ejemplo, en el caso de las etiquetas integradas en Word, PowerPoint y Excel, el nombre de la etiqueta aparece en la barra de estado. 

Esto significa que si comparte documentos con otra organización que utiliza nombres de etiquetas diferentes, cada organización puede aplicar y ver su propia etiqueta aplicada al documento. Sin embargo, los siguientes elementos de una etiqueta aplicada son visibles para los usuarios ajenos a su organización:

- Marcas de contenido. Cuando una etiqueta aplica un encabezado, pie de página o marca de agua, estos se agregan directamente al contenido y permanecen visibles hasta que alguien los modifica o los elimina.

- El nombre y la descripción de la plantilla de protección subyacente de una etiqueta que aplicó el cifrado. Esta información se muestra en una barra de mensajes en la parte superior del documento, para proporcionar información sobre quién está autorizado a abrir el documento, y sus derechos de uso para ese documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartir documentos encriptados con usuarios externos

Además de restringir el acceso a los usuarios de su propia organización, puede ampliar el acceso a cualquier otro usuario que tenga una cuenta en Azure Active Directory. Sin embargo, si su organización utiliza directivas de acceso condicional, consulte la [siguiente sección](#conditional-access-policies) para obtener consideraciones adicionales.

Todas las aplicaciones de Office y [otras aplicaciones con RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) pueden abrir documentos encriptados después de que el usuario se haya autenticado correctamente. 

Si los usuarios externos no tienen una cuenta en Azure Active Directory, pueden autenticarse utilizando cuentas de invitados en su tenant. Estas cuentas de invitados también se pueden utilizar para acceder a los documentos compartidos en SharePoint o OneDrive cuando se han [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- Una opción es crear por usted mismo estas cuentas de invitado. Puede especificar cualquier dirección de correo electrónico que estos usuarios ya utilicen. Por ejemplo, su dirección de Gmail.
    
    La ventaja de esta opción es que puedes restringir el acceso y los derechos a usuarios específicos especificando su dirección de correo electrónico en la configuración de cifrado. El inconveniente es la sobrecarga administrativa para la creación de la cuenta y la coordinación con la configuración de la etiqueta.

- Otra opción es usar la [integración de SharePoint y OneDrive con Azure AD B2B ](/sharepoint/sharepoint-azureb2b-integration) para que las cuentas de invitados se creen automáticamente cuando sus usuarios compartan enlaces.
    
    La ventaja de esta opción es que la carga administrativa es mínima, ya que las cuentas se crean automáticamente, y la configuración de las etiquetas es más sencilla. Para este escenario, debe seleccionar la opción de encriptación [Agregar cualquier usuario autentificado](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) porque no conocerá las direcciones de correo electrónico de antemano. El inconveniente es que esta configuración no permite restringir los derechos de acceso y uso a usuarios específicos.

Los usuarios externos también pueden utilizar una cuenta de Microsoft para abrir documentos encriptados cuando utilizan Windows y las Aplicaciones de Microsoft 365 ([las que antes eran aplicaciones de Office 365](/deployoffice/name-change)) o la edición independiente de Office 2019. Más recientemente, las cuentas de Microsoft también son compatibles con la apertura de documentos cifrados en macOS (Aplicaciones de Microsoft 365, versión 16.42+), Android (versión 16.0.13029+) e iOS (versión 2.42+). Por ejemplo, un usuario de su organización comparte un documento encriptado con un usuario externo a su organización, y la configuración de encriptación especifica una dirección de correo electrónico de Gmail para el usuario externo. Este usuario externo puede crear su propia cuenta de Microsoft que utiliza su dirección de correo electrónico de Gmail. A continuación, tras iniciar sesión con esta cuenta, pueden abrir el documento y editarlo, según las restricciones de uso especificadas para ellos. Para ver un ejemplo de este escenario, consulte [Abrir y editar el documento protegido](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> La dirección de correo electrónico de la cuenta de Microsoft debe coincidir con la dirección de correo electrónico especificada para restringir el acceso a la configuración de cifrado.

Cuando un usuario con una cuenta de Microsoft abre un documento encriptado de esta manera, se crea automáticamente una cuenta de invitado para el inquilino si no existe ya una cuenta de invitado con el mismo nombre. Cuando existe una cuenta de invitado, se puede utilizar para abrir documentos en SharePoint y OneDrive utilizando Office en la web, además de abrir documentos encriptados desde las aplicaciones de escritorio y móviles de Office compatibles.

Sin embargo, la cuenta automática de invitado no se crea inmediatamente en este escenario, debido a la latencia de la replicación. Si especifica direcciones de correo electrónico personales como parte de la configuración del cifrado de etiquetas, le recomendamos que cree las correspondientes cuentas de invitado en Azure Active Directory. A continuación, comunique a estos usuarios que deben utilizar esta cuenta para abrir un documento cifrado de su organización.

> [!TIP]
> Dado que no puede estar seguro de que los usuarios externos vayan a utilizar una aplicación cliente de Office compatible, compartir enlaces desde SharePoint y OneDrive después de crear cuentas de invitado (para usuarios específicos) o cuando use la [integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (para cualquier usuario autenticado) es un método más fiable para admitir la colaboración segura con usuarios externos.

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Si su organización ha implementado [Azure Active Directory con directivas de acceso condicional](/azure/active-directory/conditional-access/overview), compruebe la configuración de esas directivas. Si las directivas incluyen **Microsoft Azure Information Protection** y la directiva se extiende a usuarios externos, esos usuarios externos deben tener una cuenta de invitado en su cuenta empresarial, incluso si tienen una cuenta de Azure AD en su propia cuenta empresarial.

Sin esta cuenta de invitado, no pueden abrir el documento cifrado y ver un mensaje de error. El texto del mensaje podría informarles de que su cuenta debe agregarse como usuario externo en la cuenta empresarial, con la instrucción incorrecta para este escenario de **cerrar sesión e iniciar sesión de nuevo con una cuenta de usuario Azure Active Directory diferente**.

Si no puede crear y configurar cuentas de invitado en su inquilino para usuarios externos que necesiten abrir documentos cifrados por sus etiquetas, debe eliminar Azure Information Protection de las directivas de acceso condicional o excluir a los usuarios externos de las directivas.

Para obtener más información sobre el acceso condicional y Azure Information Protection, el servicio de cifrado utilizado por las etiquetas de confidencialidad, consulte la pregunta frecuente, [Veo que Azure Information Protection aparece como una aplicación en la nube disponible para el acceso condicional, ¿cómo funciona?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Cuando las aplicaciones de Office aplican el marcado y el cifrado de contenidos

Las aplicaciones de Office aplican el marcado de contenidos y el cifrado con etiqueta de confidencialidad de forma diferente, según la aplicación que utilice.

| Aplicación | Marcado de contenido | Cifrado |
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Después de que Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Después de que Exchange Online envíe el correo electrónico | Después de que Exchange Online envíe el correo electrónico |
|

Las soluciones que aplican etiquetas sensibles a archivos fuera de las aplicaciones de Office lo hacen aplicando etiquetas metadatos al archivo. En este caso, el contenido marcado desde la configuración de la etiqueta no se inserta en el archivo, sino que se aplica la codificación. 

Cuando esos archivos se abren en una aplicación de escritorio de Office, el cliente de etiquetado unificado de Azure Information Protection aplica automáticamente las marcas de contenido cuando el archivo se guarda por primera vez. Las marcas de contenido no se aplican automáticamente cuando se utiliza el etiquetado integrado para aplicaciones de escritorio, móviles o web.

Los escenarios que incluyen la aplicación de una etiqueta de confidencialidad fuera de las aplicaciones de Office incluyen:

- El escáner, el Explorador de archivos y PowerShell del cliente de etiquetado unificado de Azure Information Protection 

- Directivas de etiquetado automático para SharePoint y OneDrive

- Exportación de datos etiquetados y encriptados desde Power BI

- Microsoft Defender for Cloud Apps

Para estos escenarios, utilizando sus aplicaciones de Office, un usuario con etiquetado incorporado puede aplicar las marcas de contenido de la etiqueta eliminando o sustituyendo temporalmente la etiqueta actual y volviendo a aplicar la etiqueta original.

### <a name="dynamic-markings-with-variables"></a>Marcas dinámicas con variables

> [!IMPORTANT]
> Actualmente, no todas las aplicaciones de todas las plataformas admiten las marcas de contenido dinámico que puedes especificar para tus encabezados, pies de página y marcas de agua. Las aplicaciones que no admiten esta funcionalidad aplican las marcas como el texto original especificado en la configuración de la etiqueta, en lugar de resolver las variables.
> 
> El cliente de etiquetado unificado Azure Information Protection admite marcas dinámicas. Para el etiquetado integrado en Office, consulte las tablas de la sección [funcionalidades](#support-for-sensitivity-label-capabilities-in-apps) de esta página para ver las versiones mínimas admitidas.

Cuando se configura una etiqueta de confidencialidad para las marcas de contenido, se pueden utilizar las siguientes variables en la cadena de texto para su cabecera, pie de página o marca de agua:

| Variable | Descripción | Ejemplo de cuando las etiquetas son aplicadas |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nombre de visualización de la etiqueta aplicada | **General**|
| `${Item.Name}` | Nombre del archivo o asunto del correo electrónico del contenido etiquetado | **Sales.docx** |
| `${Item.Location}` | Ruta y nombre de archivo del documento que se va a etiquetar, o el asunto del correo electrónico que se va a etiquetar | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nombre del usuario que aplica la etiqueta | **Richard Simone** |
| `${User.PrincipalName}` | Nombre principal del usuario de Azure AD (UPN) del usuario que aplica la etiqueta | **rsimone\@contoso.com** |
| `${Event.DateTime}` | Fecha y hora en que se etiqueta el contenido, en la zona horaria local del usuario que aplica la etiqueta en aplicaciones de Microsoft 365 o UTC (hora universal coordinada) para Office Online y directivas de etiquetado automático | **8/10/2020 1:30 PM** |

> [!NOTE]
> La sintaxis de estas variables distingue entre mayúsculas y minúsculas.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Configuración de diferentes marcas visuales para Word, Excel, PowerPoint y Outlook

Como variable adicional, puede configurar las marcas visuales por tipo de aplicación de Office utilizando una declaración de variable "If.App" en la cadena de texto, e identificar el tipo de aplicación utilizando los valores **Word**, **Excel**, **PowerPoint**, o **Outlook**. También puede abreviar estos valores, lo cual es necesario si desea especificar más de uno en la misma sentencia If.App.

Utilice la siguiente sintaxis:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Igual que el resto de las marcas visuales dinámicas, la sintaxis distingue mayúsculas de minúsculas, lo que incluye las abreviaturas para cada tipo de aplicación (WEPO).

Ejemplos:

- **Establezca el texto de la cabecera sólo para los documentos de Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Sólo en las cabeceras de los documentos de Word, la etiqueta aplica el texto de cabecera "Este documento de Word es confidencial". No se aplica ningún texto de cabecera a otras aplicaciones de Office.

- **Establezca un texto de pie de página para Word, Excel y Outlook, y un texto de pie de página diferente para PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    En Word, Excel y Outlook, la etiqueta aplica el texto a pie de página "Este contenido es confidencial". En PowerPoint, la etiqueta aplica el texto de pie de página "Esta presentación es confidencial".

- **Establezca un texto de marca de agua específico para Word y PowerPoint, y luego un texto de marca de agua para Word, Excel y PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    En Word y PowerPoint, la etiqueta aplica el texto de marca de agua "Este contenido es confidencial". En Excel, la etiqueta aplica el texto de marca de agua "Confidencial". En Outlook, la etiqueta no aplica ningún texto de marca de agua porque las marcas de agua como marcas visuales no son compatibles con Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos

> [!IMPORTANT]
> 
> El [cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)es compatible con el etiquetado obligatorio. Para el etiquetado incorporado a las aplicaciones de Office, consulte las tablas de la sección de [funciones](#support-for-sensitivity-label-capabilities-in-apps) de esta página para ver las versiones mínimas.
>
> Para usar el etiquetado obligatorio para documentos pero no para correos electrónicos, consulte las instrucciones en la siguiente sección que explica cómo configurar las opciones específicas de Outlook.
> 
> Para usar el etiquetado obligatorio para Power BI, consulte [directiva de etiquetas obligatorias para Power BI](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy).

Cuando la configuración de directiva **Requerir que los usuarios apliquen una etiqueta a su correo electrónico y documentos** está seleccionada, los usuarios asignados a la directiva deben seleccionar y aplicar una etiqueta de confidencialidad en los escenarios siguientes:

- Para el cliente de etiquetado unificado de Azure Information Protection:
    - Para documentos (Word, Excel, PowerPoint): cuando se guarda un documento sin etiqueta o los usuarios cierran el documento.
    - Para los correos electrónicos (Outlook): En el momento en que los usuarios envían un mensaje sin etiqueta.

- Para el etiquetado integrado en las aplicaciones de Office:
    - Para los documentos (Word, Excel, PowerPoint): cuando se abre o guarda un documento sin etiqueta.
    - Para los correos electrónicos (Outlook): en el momento en que los usuarios envían un mensaje de correo electrónico sin etiqueta.

Información adicional para el etiquetado incorporado:

- Cuando se pide a los usuarios que añadan una etiqueta de confidencialidad porque abren un documento sin etiqueta, pueden agregar una etiqueta o elegir abrir el documento en modo de sólo lectura.

- Cuando el etiquetado obligatorio está en vigor, los usuarios no pueden eliminar las etiquetas de confidencialidad de los documentos, pero pueden cambiar una etiqueta existente.

Para obtener orientación sobre cuándo utilizar esta configuración, consulte la información sobre la [configuración de directivas](sensitivity-labels.md#what-label-policies-can-do).

> [!NOTE]
> Si usa la configuración de directiva de etiquetado predeterminada para documentos y correos electrónicos, además del etiquetado obligatorio: 
>
> La etiqueta predeterminada siempre tiene prioridad sobre el etiquetado obligatorio. Pero en el caso de los documentos, el cliente de etiquetado unificado de Azure Information Protection aplica la etiqueta predeterminada a todos los documentos sin etiquetar, mientras que las etiquetas integradas aplican la etiqueta predeterminada a los documentos nuevos y no a los documentos existentes sin etiqueta. Esta diferencia en el comportamiento significa que cuando use etiquetado obligatorio con la configuración de etiquetas predeterminadas, probablemente se pedirá a los usuarios que apliquen una etiqueta de confidencialidad más a menudo cuando usan el etiquetado integrado que cuando usan el cliente de etiquetado unificado de Azure Information Protection.
> 
> Implementación en curso: las aplicaciones de Office que usan el etiquetado integrado y admiten una etiqueta predeterminada para documentos existentes. Para obtener más información, consulte la [tabla de funcionalidades](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) de Word, Excel y PowerPoint.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Opciones específicas de Outlook para etiquetas predeterminadas y etiquetas obligatorias

Para el etiquetado integrado, identifique las versiones mínimas de Outlook que admiten estas características mediante la tabla de [ capacidades para Outlook](#sensitivity-label-capabilities-in-outlook) en esta página, y la fila **Configuración diferente para la etiqueta predeterminada y el etiquetado obligatorio**. Todas las versiones de Azure Information Protection del cliente de etiquetado unificado admiten estas opciones específicas de Outlook.

Cuando la aplicación de Outlook sea compatible con una configuración de etiqueta predeterminada diferente a la configuración de etiqueta predeterminada para documentos:

- En el Asistente para directivas de etiqueta de la página **Aplicar una etiqueta predeterminada a los correos electrónicos**, puede especificar la elección de la etiqueta de confidencialidad que se aplicará a todos los correos electrónicos sin etiqueta o ninguna etiqueta predeterminada. Esta configuración es independiente de la configuración **Aplicar esta etiqueta de forma predeterminada a los documentos** en la página anterior **Configuración de directiva para documentos** del Asistente.

Cuando la aplicación de Outlook no admita una configuración de etiqueta predeterminada diferente a la configuración de etiqueta predeterminada para los documentos, Outlook siempre usará el valor que especifique en **Aplicar esta etiqueta de forma predeterminada a los documentos** en la página **Configuración de directiva para documentos** del Asistente para directivas de etiqueta.

Cuando la aplicación de Outlook admita desactivar la etiqueta obligatoria:

- En el Asistente para directivas de etiqueta de la página **Configuración de directiva**, seleccione **Requerir que los usuarios apliquen una etiqueta a su correo electrónico o documentos**. Después, seleccione **Siguiente** > **Siguiente** y desactive la casilla **Requerir que los usuarios apliquen una etiqueta a sus mensajes**. Seleccione la casilla si quiere que la etiqueta obligatoria se aplique a correos electrónicos, así como a documentos.

Cuando la aplicación de Outlook no admita desactivar la etiqueta obligatoria: si selecciona **Requerir que los usuarios apliquen una etiqueta a su correo electrónico o documentos** como configuración de directiva, Outlook siempre pedirá a los usuarios que seleccionen una etiqueta para los correos electrónicos que no la tengan.

> [!NOTE]
> Si ha configurado las opciones avanzadas de PowerShell **OutlookDefaultLabel** y **DisableMandatoryInOutlook** con los cmdlets [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) o [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy):
> 
> Los valores seleccionados para estas opciones de configuración de PowerShell se reflejan en el Asistente para directivas de etiqueta y funcionan automáticamente en las aplicaciones de Outlook compatibles con esta configuración. El resto de las opciones avanzadas de PowerShell siguen siendo compatibles solo con el cliente de etiquetado unificado de Azure Information Protection.

## <a name="end-user-documentation"></a>Documentación para el usuario final

- [Aplicar etiquetas de confidencialidad a sus archivos y correos electrónicos en Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
