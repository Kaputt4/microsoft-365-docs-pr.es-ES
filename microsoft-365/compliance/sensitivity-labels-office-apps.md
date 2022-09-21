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
ms.openlocfilehash: 2062f1d03d23c3a2de029c862a332a089f2dabcc
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851620"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Administrar etiquetas de confidencialidad en las aplicaciones de Office

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Cuando haya [publicado](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) etiquetas de confidencialidad desde el portal de cumplimiento de Microsoft Purview, empezarán a aparecer en las aplicaciones de Office para que los usuarios clasifiquen y protejan los datos a medida que se creen o editen.

Use la información de este artículo como ayuda para administrar correctamente las etiquetas de confidencialidad en las aplicaciones de Office. Por ejemplo, identifique las versiones mínimas de las aplicaciones que necesitará para características específicas de etiquetado integrado, cualquier información de configuración adicional para estas características y, además, comprenda las interacciones con el cliente de etiquetado unificado de Azure Information Protection y otras aplicaciones y servicios.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de etiquetado para aplicaciones de escritorio

Para usar las etiquetas de confidencialidad integradas en las aplicaciones de escritorio de Office para Windows y Mac, debe utilizar una edición de suscripción de Office. Este cliente de etiquetado no es compatible con las ediciones independientes de Office, a veces denominadas "Office Perpetua".

Si no puede actualizar a Aplicaciones de Microsoft 365 para empresas para las versiones de suscripción de Office en equipos Windows, puede usar el [Cliente de etiquetado unificado de Azure Information Protection (AIP)](/azure/information-protection/rms-client/aip-clientv2). Sin embargo, este cliente está ahora en [modo de mantenimiento](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-aip-unified-labeling-client-maintenance-mode-and/ba-p/3043613) y no se recomienda usar el complemento AIP para aplicaciones de Office a menos que deba hacerlo. Para obtener más información, consulte [Por qué elegir el etiquetado integrado en lugar del complemento de AIP para las aplicaciones de Office](sensitivity-labels-aip.md).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Compatibilidad con las funciones de las etiquetas de confidencialidad en las aplicaciones

En las tablas siguientes se muestra la versión mínima de Office que introdujo funcionalidades específicas para las etiquetas de confidencialidad integradas en las aplicaciones de Office. O bien, si la función de la etiqueta está en vista previa pública o en revisión para una versión futura. Use el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) para obtener detalles sobre las nuevas funcionalidades que están planeadas para futuras versiones.

Las nuevas versiones de las aplicaciones de Office están disponibles en diferentes momentos para diferentes canales de actualización. Para Windows, las nuevas funciones se obtienen antes cuando se encuentra en el Canal actual o el Canal mensual para empresas, en lugar del Canal semestral para empresas. Los números de versión mínimos también pueden ser diferentes de un canal de actualización al siguiente. Para obtener más información, vea [Introducción a los canales de actualización para las Aplicaciones de Microsoft 365](/deployoffice/overview-update-channels) y [Actualizar historial para las Aplicaciones Microsoft 365](/officeupdates/update-history-microsoft365-apps-by-date).

Las nuevas funciones que están en vista previa privada no se incluyen en la tabla, pero es posible que pueda unirse a estas vistas previas nominando a su organización para el programa de vista previa privada de [Microsoft Information Protection](https://aka.ms/mip-preview).

Office para iOS y Office para Android: Las etiquetas de confidencialidad están integradas en las [aplicación de Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

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
|[Compatibilidad con varios idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | En revisión |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do) a nuevos documentos                                         | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do) a documentos existentes | Canal actual: 2208+ <br /><br> Canal mensual de empresa: 2207+  <br /><br> Canal semestral para empresas: en revisión | 16.63+ | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Requerir una justificación para cambiar una etiqueta.](sensitivity-labels.md#what-label-policies-can-do)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+  <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada.](sensitivity-labels.md#what-label-policies-can-do)                       | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables).                                              | Canal actual: 2010+ <br /><br> Canal mensual para empresas: 2010+ <br /><br> Canal semestral para empresas: 2102+ | 16.42+     | 2.42+ | 16.0.13328+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que los usuarios asignen permisos: <br /> - Solicitar permisos personalizados a los usuarios (usuarios y grupos)](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |Canal actual: 2004+ <br /><br> Canal mensual para empresas: 2004+ <br /><br> Canal semestral para empresas: 2008+ | 16.35+   | En revisión   | En revisión         | En revisión                                                        |
|[Permitir que los usuarios asignen permisos: <br /> - Solicitar permisos personalizados a los usuarios (usuarios, grupos y organizaciones)](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |Versión preliminar: implementando en [Canal Beta](https://office.com/insider)  | En revisión   | En revisión   | En revisión         | En revisión                                                        |
|[Auditoría de la actividad de los usuarios relacionada con las etiquetas](#auditing-labeling-activities)                      | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ | 2.46+ | 16.0.13628+ | Sí |
|[Requerir a los usuarios que apliquen una etiqueta a sus correos electrónicos y documentos ](#require-users-to-apply-a-label-to-their-email-and-documents)   | Canal actual: 2101+ <br /><br> Canal mensual para empresas: 2101+ <br /><br> Canal semestral para empresas: 2108+ | 16.45+         | 2.47+ | 16.0.13628+ | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de tipos de información confidencial                    | Canal actual: 2009+ <br /><br> Canal mensual para empresas: 2009+ <br /><br> Canal semestral para empresas: 2102+ | 16.44+ | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de clasificadores capacitados                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2108+ | 16.49+ | En revisión | En revisión | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Compatibilidad con la coautoría y el autoguardado](sensitivity-labels-coauthoring.md) documentos etiquetados y cifrados | Canal actual: 2107+ <br /><br> Canal mensual para empresas: 2107+ <br /><br> Canal semestral para empresas: 2202+ |  16.51+ | 2.58+ | 16.0.14931+  | [Sí - participar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Compatibilidad con PDF](#pdf-support)| Canal actual: 2208+ <br /><br> Canal mensual de empresa: 2208+ <br /><br> Canal semestral para empresas: en revisión|  En revisión | En revisión | En revisión | En revisión |
|[Barra de confidencialidad](#sensitivity-bar) y [color de la etiqueta de presentación](#label-colors) | Versión preliminar: implementando en [Canal Beta](https://office.com/insider) | En revisión | En revisión | En revisión | En revisión |

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funciones de la etiqueta de confidencialidad en Outlook

Los números indicados son las versiones mínimas de la aplicación Office requeridas para cada función. 

> [!NOTE]
> Para Windows y el Canal empresarial semestral, es posible que aún no se hayan publicado los números de versión mínimos admitidos. [Más información](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)

|Funcionalidad |Outlook para Windows |Outlook para Mac |Outlook en iOS |Outlook en Android |Outlook en la Web |
|-----------|-------------------:|----------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o eliminar manualmente la etiqueta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Compatibilidad con varios idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+ | 4.7.1+ | 4.0.39+ | Sí |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Requerir una justificación para cambiar una etiqueta.](sensitivity-labels.md#what-label-policies-can-do)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada.](sensitivity-labels.md#what-label-policies-can-do)                       | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Marcados dinámicos con variables](#dynamic-markings-with-variables).                                              | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Permitir a los usuarios asignar permisos: <br /> - No reenviar](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Canal actual: 1910+ <br /><br> Canal mensual para empresas: 1910+ <br /><br> Canal semestral para empresas: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Sí               |
|[Permitir a los usuarios asignar permisos: <br /> - Solo cifrar](encryption-sensitivity-labels.md#let-users-assign-permissions)  | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: 2108+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Sí |
|[Requerir a los usuarios que apliquen una etiqueta a sus correos electrónicos y documentos ](#require-users-to-apply-a-label-to-their-email-and-documents)   | Canal actual: 2101+ <br /><br> Canal mensual para empresas: 2101+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Sí                |
|[Auditoría de la actividad de los usuarios relacionada con las etiquetas](#auditing-labeling-activities) | Canal actual: 2011+ <br /><br> Canal mensual para empresas: 2011+ <br /><br> Canal semestral para empresas: 2108+ | 16.51+ <sup>\*</sup> | 4.2126+ | 4.2126+ | Sí |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de tipos de información confidencial                    | Canal actual: 2009+ <br /><br> Canal mensual para empresas: 2009+ <br /><br> Canal semestral para empresas: 2102+ | 16.44+ <sup>\*</sup>                    | En revisión           | En revisión               | Sí |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md) <br /> - Uso de clasificadores capacitados                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2108+ | 16.49+ | En revisión           | En revisión               | Sí |
|[Diferentes opciones de configuración para etiquetas predeterminadas y etiquetas obligatorias](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | Canal actual: 2105+ <br /><br> Canal mensual para empresas: 2105+ <br /><br> Canal semestral para empresas: 2108+ | 16.43+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Sí |
|[Compatibilidad con PDF](#pdf-support) | Versión preliminar: implementando en [Canal Beta](https://office.com/insider)|  En revisión | En revisión | En revisión | En revisión |
|[Aplicar protección S/MIME](#configure-a-label-to-apply-smime-protection-in-outlook) | Versión preliminar: implementando en [Canal Beta](https://office.com/insider) | Implementando: 16.61+ <sup>\*</sup>                   | Implementación: 4.2226+ | Implementación: 4.2203+ | En revisión |
|[Barra de confidencialidad](#sensitivity-bar) y [color de la etiqueta de presentación](#label-colors) | En revisión |  En revisión | En revisión | En revisión | En revisión |

**Notas al pie:**

<sup>\*</sup> Se requiere el [nuevo Outlook para Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>El cliente de etiquetado integrado de Office y el cliente de Azure Information Protection

Si los usuarios tienen el [cliente de Azure Information Protection (AIP)](/azure/information-protection/rms-client/aip-clientv2) instalado en sus equipos Windows, de forma predeterminada, las etiquetas integradas se desactivan en [Aplicaciones de Windows Office que las admiten](#labeling-client-for-desktop-apps). Dado que las etiquetas integradas no usan un complemento de Office, tal y como las usa el cliente de AIP, tienen la ventaja de una mayor estabilidad y un mejor rendimiento. También admiten las características más recientes, como clasificadores avanzados. 

> [!NOTE]
> Si no ve las características de etiquetado que se espera en equipos Windows, a pesar de confirmar las versiones mínimas admitidas para el canal de actualización de Office, puede deberse a que necesita [deshabilitar el complemento de AIP](sensitivity-labels-aip.md#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps).

Para obtener más información sobre la compatibilidad de etiquetado con el cliente de AIP, y cómo deshabilitar este cliente justamente en las aplicaciones de Office, consulte [Por qué elegir el etiquetado integrado en lugar del complemento de AIP para las aplicaciones de Office](sensitivity-labels-aip.md).

## <a name="if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows"></a>Si necesita desactivar el etiquetado integrado en las aplicaciones de Office en Windows

El cliente de etiquetado integrado de Office descarga las etiquetas de confidencialidad y la configuración de directiva de etiquetas de confidencialidad desde el portal de cumplimiento de Microsoft Purview.

Para usar el cliente de etiquetado integrado de Office, debe tener una o más [directivas de etiquetas publicadas ](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)para los usuarios desde uno de los centros de administración enumerados y una [ versión compatible de Office](#support-for-sensitivity-label-capabilities-in-apps).

Si se cumplen ambas condiciones, pero necesita desactivar las etiquetas integradas en las aplicaciones de Windows Office, use la siguiente configuración de directiva de grupo:

1. Navegar a **Configuración de usuario/Plantillas administrativas/Microsoft Office 2016/Configuración de seguridad**.

2. Establecer **Usar la función de confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad** a **0**.

Si más adelante necesita revertir esta configuración, cambie el valor a **1**. También es posible que tenga que cambiar el valor a 1 si el botón **Confidencialidad** no se muestra en la cinta de opciones según lo esperado. Por ejemplo, un administrador anterior ha desactivado esta configuración de etiquetado.
 
Implementar esta configuración mediante la directiva de grupo o mediante el [Servicio de directiva de la nube de Office](/DeployOffice/overview-office-cloud-policy-service). La configuración tiene efecto cuando se reinician estas aplicaciones de Office. 

Dado que esta configuración es específica de las aplicaciones de Windows Office, no tiene ningún impacto en otras aplicaciones de Windows que admiten etiquetas de confidencialidad (como Power BI) u otras plataformas (como macOS, dispositivos móviles y Office para la Web). Si no quiere que algunos o que todos los usuarios vean y usen etiquetas de confidencialidad en todas las aplicaciones y plataformas, no asigne una directiva de etiquetas de confidencialidad a esos usuarios.

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
        - Claves del Registro `DWORD:00000001` *DisableDNF* y *DisableEO* de `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM`
        - Asegúrese de que la configuración de directiva de grupo **Configuración de cifrado predeterminada para el botón Cifrar** no está configurada
    - Outlook para Mac: 
        - Claves *DisableEncryptOnly* y *DisableDoNotForward* documentadas en [Establecer preferencias para Outlook para Mac](/DeployOffice/mac/preferences-outlook)
    - Outlook en la web: 
        - Parámetros *SimplifiedClientAccessDoNotForwardDisabled* y *SimplifiedClientAccessEncryptOnlyDisabled* documentados para [Set-IRMConfiguración](/powershell/module/exchange/set-irmconfiguration)
    - Outlook para iOS y Android: estas aplicaciones no admiten que los usuarios apliquen cifrado sin etiquetas, por lo que no hay nada que deshabilitar.

> [!NOTE]
> Si los usuarios eliminan manualmente el cifrado de un documento etiquetado que está almacenado en SharePoint o OneDrive y usted ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), el cifrado de la etiqueta se restaurará automáticamente la próxima vez que se acceda al documento o se descargue. 

## <a name="encryption-based-label-matching-for-documents"></a>Coincidencia de etiquetas basadas en cifrado para documentos

Cuando se ha cifrado un documento con permisos definidos por el administrador, la directiva de cifrado se inserta en el documento. Esto sucede independientemente del etiquetado. Por ejemplo, cuando un archivo adjunto de Office hereda el cifrado de un mensaje de correo electrónico o un usuario ha aplicado una plantilla de protección mediante Information Rights Management (IRM) en su aplicación de Office. Si una etiqueta de confidencialidad del inquilino coincide con esa misma directiva de cifrado, las aplicaciones de Office asignarán automáticamente esa etiqueta coincidente al documento.

En este escenario, la etiqueta de confidencialidad coincidente puede etiquetar un documento sin etiquetar y reemplazar una etiqueta existente que no aplique el cifrado. Por ejemplo, la etiqueta **General** se reemplaza por **Confidencial/Todos los empleados**. Las marcas de contenido de la etiqueta coincidente no se aplican automáticamente, a menos que el documento no se haya etiquetado previamente y use el complemento AIP.

Este escenario ayuda a mover las soluciones de cifrado anteriores de las plantillas de protección a las etiquetas de confidencialidad que aplican el cifrado.

Sin embargo, también verá este comportamiento con un escenario de etiquetado para los datos adjuntos de correo electrónico cuando el destinatario los abra. Por ejemplo:

1. Un usuario crea un correo electrónico y adjunta un documento de Office sin cifrar y, a continuación, aplica una etiqueta al correo electrónico.
    
    La etiqueta aplica el cifrado con permisos establecidos por el administrador, en lugar de las opciones No reenviar o Encrypt-Only. Por ejemplo, para la configuración de la etiqueta, el administrador selecciona **Asignar permisos ahora** y especifica que todos los empleados tienen acceso de lectura.

2. Cuando se envía el correo electrónico, los [datos adjuntos heredan automáticamente el cifrado, pero no la etiqueta](encryption-sensitivity-labels.md#email-attachments-for-encrypted-email-messages).

3. Cuando un destinatario del mismo inquilino abre el documento cifrado, se muestra automáticamente una etiqueta coincidente para los permisos definidos por el administrador para el documento y se conserva si se guarda el documento.
    
    Como evento de auditoría que se muestra en el Explorador de actividades, este usuario aplicó la etiqueta, no el remitente del correo electrónico.

La coincidencia de etiquetas basada en cifrado solo funciona dentro del inquilino, para los permisos definidos por el administrador, y la etiqueta de confidencialidad coincidente debe publicarse para el usuario que abre el documento. La etiqueta coincidente se conserva si se guarda el documento.

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

Aunque puede restringir el acceso a los usuarios de su propia organización, también puede ampliar el acceso a cualquier otro usuario que tenga una cuenta en Azure Active Directory (Azure AD). De forma predeterminada, estos usuarios externos se autenticarán sin ninguna configuración adicional. Sin embargo, es posible que se requiera una configuración adicional para [la configuración de acceso entre inquilinos de Identidades externas](/azure/active-directory/external-identities/cross-tenant-access-overview) de Azure AD y el [acceso condicional](/azure/active-directory/conditional-access/overview). 

Si los usuarios externos no tienen una cuenta en Azure AD, pueden autenticarse mediante cuentas de invitado en el inquilino. Estas cuentas de invitado también se pueden usar para acceder a documentos compartidos en SharePoint o OneDrive cuando se han [habilitado etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

Para obtener más información sobre las características opcionales de Azure AD y el uso de cuentas de invitado para los requisitos de autenticación, consulte [Configuración de Azure AD para el contenido de cifrado](encryption-azure-ad-configuration.md).

Todas las aplicaciones de Office y [otras aplicaciones con RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) pueden abrir documentos encriptados después de que el usuario se haya autenticado correctamente. 

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
> Si sus aplicaciones de Office no admiten esta capacidad, aplican las marcas como el texto original especificado en la configuración de la etiqueta, en lugar de resolver las variables.
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

- Cuando el etiquetado obligatorio está en vigor, la opción Imprimir en PDF no estará disponible cuando un documento esté etiquetado o cifrado. Para más información, consulte la sección [Compatibilidad con PDF](#pdf-support) de esta página.

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

- En la configuración de la directiva de etiquetas del portal de cumplimiento de Microsoft Purview, en la página **Aplicar una etiqueta predeterminada a los correos electrónicos**, puede especificar la etiqueta de confidencialidad que se aplicará a todos los correos electrónicos sin etiquetar o no especificar ninguna etiqueta predeterminada. Esta configuración es independiente de la configuración **Aplicar esta etiqueta de forma predeterminada a los documentos** establecida en la página de la configuración anterior **Configuración de directivas para documentos**.

Cuando la aplicación Outlook no admite una configuración de etiqueta predeterminada que sea diferente de la configuración de etiqueta predeterminada para los documentos: Outlook siempre usará el valor que especifique para **Aplicar esta etiqueta de forma predeterminada a los documentos** en la página de configuración de directivas de etiquetas **Configuración de directivas para documentos**.

Cuando la aplicación de Outlook admita desactivar la etiqueta obligatoria:

- En la configuración de directiva de etiquetas del portal de cumplimiento de Microsoft Purview, en la página de **Configuración de directivas**, seleccione **Requerir a los usuarios que apliquen una etiqueta a su correo electrónico o a los documentos**. Después, seleccione **Siguiente** > **Siguiente** y desactive la casilla **Requerir que los usuarios apliquen una etiqueta a sus mensajes**. Seleccione la casilla si quiere que la etiqueta obligatoria se aplique a correos electrónicos, así como a documentos.

Cuando la aplicación de Outlook no admita desactivar la etiqueta obligatoria: si selecciona **Requerir que los usuarios apliquen una etiqueta a su correo electrónico o documentos** como configuración de directiva, Outlook siempre pedirá a los usuarios que seleccionen una etiqueta para los correos electrónicos que no la tengan.

> [!NOTE]
> Si ha configurado las opciones avanzadas de PowerShell **OutlookDefaultLabel** y **DisableMandatoryInOutlook** con los cmdlets [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) o [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy):
> 
> Los valores elegidos para esta configuración de PowerShell se reflejan en la configuración de directivas de etiquetas en el portal de cumplimiento de Microsoft Purview y funcionan automáticamente para las aplicaciones de Outlook que admiten esta configuración. El resto de las opciones avanzadas de PowerShell siguen siendo compatibles solo con el cliente de etiquetado unificado de Azure Information Protection.

## <a name="configure-a-label-to-apply-smime-protection-in-outlook"></a>Configurar una etiqueta para aplicar la protección S/MIME en Outlook

> [!NOTE]
> Esta funcionalidad se está implementando actualmente para el etiquetado integrado. Identifique las versiones mínimas de Outlook que admiten esta característica mediante la [tabla de capacidades de Outlook](#sensitivity-label-capabilities-in-outlook) en esta página y la fila **Aplicar protección S/MIME**.
> 
> Si configura una etiqueta para aplicar la protección S/MIME, pero la aplicación de Outlook aún no la admite, la etiqueta se sigue mostrando en Outlook y se puede aplicar, pero se omite la configuración de S/MIME. No podrá seleccionar esta etiqueta para las directivas de etiquetado automático de Exchange.

Esta configuración no está disponible en el portal de cumplimiento Microsoft Purview. Debe usar la configuración avanzada de PowerShell con el cmd [Set-Label](/powershell/module/exchange/set-label) o [New-Label](/powershell/module/exchange/new-label) después de [conectarse a Office 365 Centro de seguridad y cumplimiento PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

Use esta configuración solo cuando tenga una [implementación S/MIME](/microsoft-365/security/office-365-security/s-mime-for-message-signing-and-encryption) en funcionamiento y quiera que una etiqueta aplique automáticamente este método de protección para los correos electrónicos en lugar de la [protección predeterminada que usa el cifrado de la administración de derechos de Azure Information Protection](encryption-sensitivity-labels.md). La protección resultante será la misma que cuando un usuario selecciona manualmente las opciones S/MIME de Outlook.

|Configuración  |Clave o valor de configuración avanzada |
|---------|---------|
|**Firma digital S/MIME** | SMimeSign="True" |
|**Cifrado S/MIME** | SMimeEncrypt="True"|

La etiqueta que configure para estas opciones no tiene que configurarse para el cifrado en el portal de cumplimiento. Pero si es así, la protección S/MIME reemplaza el cifrado de Rights Management solo en Outlook. Para otras aplicaciones, la etiqueta aplica la configuración de cifrado especificada en el portal de cumplimiento de Microsoft Purview.

Comandos de PowerShell de ejemplo, donde el GUID de la etiqueta de confidencialidad es **8faca7b8-8d20-48a3-8ea2-0f96310a848e**:

```PowerShell
Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeSign="True"}

Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeEncrypt="True"}
```

Para obtener más ayuda sobre cómo especificar la configuración avanzada de PowerShell, consulte [Sugerencias de PowerShell para especificar la configuración avanzada](create-sensitivity-labels.md#powershell-tips-for-specifying-the-advanced-settings).

## <a name="pdf-support"></a>Compatibilidad con PDF

Para el etiquetado integrado, use las tablas de la sección [funcionalidades](#support-for-sensitivity-label-capabilities-in-apps) de esta página para identificar las versiones mínimas admitidas. El cliente de etiquetado unificado de Azure Information Protection no admite PDF en aplicaciones de Office.

Word, Excel y PowerPoint admiten los métodos siguientes para convertir un documento de Office en un documento PDF:

- Archivo > Guardar como > PDF 
- Archivo > Exportar > PDF
- Compartir > Enviar una copia > PDF

Esta acción se registra con el evento de auditoría del **Archivo cuyo nombre se ha cambiado** desde el grupo de auditoría [Actividades de archivos y páginas](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities). En los resultados de la búsqueda de auditoría en el portal de cumplimiento, verá que los detalles de este evento de auditoría muestran **SensitivityLabeledFileRenamed** para el campo **Actividad**.

Cuando se crea el PDF, hereda la etiqueta con cualquier marca de contenido y cifrado. Los archivos PDF cifrados se pueden abrir con Microsoft Edge en Windows o Mac. Para obtener más información y para lectores alternativos, vea [¿Cuáles son los lectores de PDF compatibles para archivos PDF protegidos?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)

Outlook no admite actualmente datos adjuntos PDF que conserven el cifrado de un mensaje etiquetado. Sin embargo, Outlook ahora sí permite ofrecer una advertencia o impedir a los usuarios que impriman en PDF, como se describe a continuación.

Escenarios de PDF no admitidos:

- Imprimir en PDF
    
    Si los usuarios seleccionan esta opción, se les advertirá de que el documento perderá la protección de la etiqueta y el cifrado (si se aplica), y deberán confirmar para continuar. Si la directiva de etiqueta de confidencialidad requiere justificación para quitar una etiqueta o reducir su clasificación, verá este mensaje.
    
    Dado que esta opción quita la etiqueta de confidencialidad, esta opción no estará disponible para los usuarios si usa el etiquetado obligatorio. Esta configuración hace referencia a la configuración de directiva de etiqueta de confidencialidad que requiere que los usuarios apliquen una etiqueta a sus correos electrónicos y documentos.

- Formato y cifrado PDF/A
    
     Este formato PDF diseñado para el archivado a largo plazo no se admite cuando la etiqueta aplica cifrado y evitará que los usuarios conviertan documentos de Office en PDF. Para obtener información de configuración, consulte la documentación de directiva de grupo para [exigir el cumplimiento de PDF con ISO 19005-1 (PDF/A).](https://admx.help/?Category=Office2016&Policy=office16.Office.Microsoft.Policies.Windows::L_EnforcePDFcompliancewithISO190051PDFA)
    
- Protección con contraseña y cifrado
    
    La opción **Archivo** > **Información** > **Proteger documento** > **Cifrar con contraseña** no se admite cuando la etiqueta del documento aplica cifrado. En este escenario, la opción Cifrar con contraseña deja de estar disponible para los usuarios.

Para más información sobre esta funcionalidad, vea el anuncio [Aplicar etiquetas de confidencialidad a archivos PDF creados con aplicaciones de Office](https://insider.office.com/blog/apply-sensitivity-labels-to-pdfs-created-with-office-apps).

Para obtener documentación del usuario final, consulte [Creación de archivos PDF protegidos a partir de archivos de Office](https://support.microsoft.com/topic/aba7e367-e482-49e7-b746-a385e48d01e4).

## <a name="sensitivity-bar"></a>Barra de confidencialidad

Recién compatible con la versión preliminar para etiquetas integradas en Word, Excel y PowerPoint, pero aún no para Outlook o Office para la Web, vea las tablas de la sección [funcionalidades](#support-for-sensitivity-label-capabilities-in-apps) de esta página para identificar las versiones mínimas.

En el caso de las aplicaciones admitidas, las etiquetas de confidencialidad ahora se muestran en una barra de confidencialidad, junto al nombre de archivo de la barra de ventana superior. Por ejemplo:

![Etiquetas de confidencialidad en la barra de título de la ventana.](../media/sensitivity-bar-example.png)

La información sobre las etiquetas y la capacidad de seleccionar o cambiar una etiqueta también se integran en flujos de trabajo de usuario que incluyen guardar y cambiar el nombre, exportar, compartir, imprimir y [convertir a PDF](#pdf-support). Para obtener más información y capturas de pantalla de ejemplo, vea el anuncio de la entrada de blog [, Nueva barra de confidencialidad en Office para Windows](https://insider.office.com/blog/sensitivity-bar-in-office-for-windows).

Como parte de esta alta visibilidad, estas etiquetas también admiten colores. Para más información, vea la sección siguiente.

### <a name="label-colors"></a>Colores de etiqueta

> [!IMPORTANT]
> Si las aplicaciones de etiquetado no admiten esta funcionalidad, no muestran los colores de etiqueta configurados.
> 
> El cliente de etiquetado unificado de Azure Information Protection admite colores de etiqueta. Para el etiquetado integrado en Office, los colores de etiquetas se admiten actualmente en versión preliminar para Word, Excel y PowerPoint en Windows y macOS, pero no Outlook ni Office para la Web. Para obtener más información, consulte las tablas de la sección [funcionalidades](#support-for-sensitivity-label-capabilities-in-apps) de esta página.

Las etiquetas recién creadas no tienen un color de forma predeterminada. Si las etiquetas se [migraron desde Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels) o configuró los colores de etiqueta para azure Information Protection cliente de etiquetado unificado, estos colores de etiqueta ahora se muestran en las aplicaciones que las admiten.

Use el portal de cumplimiento Microsoft Purview para seleccionar uno de los 10 colores estándar para las etiquetas de confidencialidad. Esta configuración se encuentra en la primera página de la configuración de la etiqueta después del nombre y la descripción de la etiqueta.

No puede seleccionar los colores de las subetiquetas porque heredan automáticamente el color de la etiqueta de su etiqueta primaria.

Si la etiqueta está configurada para un color diferente de uno de los 10 colores, verá una opción **Color personalizado** seleccionada y las opciones de color estándar no están disponibles:

![Configuración de color de etiqueta de confidencialidad cuando la etiqueta tiene un color personalizado.](../media/label-custom-color-configuration.png)

Puede cambiar el color personalizado a uno de los colores estándar quitando primero la selección de color personalizada y, a continuación, seleccionando uno de los colores estándar. Pero no puede usar el portal de cumplimiento para configurar un color personalizado diferente. En su lugar, use PowerShell, como se describe en la sección siguiente.

#### <a name="configuring-custom-colors-by-using-powershell"></a>Configuración de colores personalizados mediante PowerShell 

Puede usar el **color** de configuración avanzada [de PowerShell del Centro](/powershell/exchange/scc-powershell) de cumplimiento de Seguridad & para establecer un color para una etiqueta de confidencialidad. Esta configuración admite colores que no se pueden configurar en el portal de cumplimiento Microsoft Purview.

Para especificar la elección de color, use un código hexadecimal de triplete para los componentes rojo, verde y azul (RGB) del color. Por ejemplo, #40e0d0 es el valor hexadecimal RGB para el turquesa.

Para obtener más información sobre estos códigos, consulte la [\<color>](https://developer.mozilla.org/docs/Web/CSS/color_value) página de los documentos web de MSDN y también puede que [RapidTables](https://www.rapidtables.com/web/color/RGB_Color.html) le resulte útil. Puede identificar estos códigos en muchas aplicaciones que le permiten editar imágenes. Por ejemplo, Microsoft Paint le permite elegir un color personalizado de una paleta y los valores de RGB se muestran de forma automática, los que puede copiar luego.

Comando de PowerShell de ejemplo, donde el GUID de la etiqueta de confidencialidad es **8faca7b8-8d20-48a3-8ea2-0f96310a848e**

```PowerShell
Set-Label -Identity 8faca7b8-8d20-48a3-8ea2-0f96310a848e -AdvancedSettings @{color="#40e0d0"}
```

Para obtener más información que le ayude a especificar la configuración avanzada de PowerShell para etiquetas de confidencialidad, consulte [Sugerencias de PowerShell para especificar la configuración avanzada](create-sensitivity-labels.md#powershell-tips-for-specifying-the-advanced-settings).

## <a name="auditing-labeling-activities"></a>Actividades de etiquetado de auditoría

Para obtener información sobre los eventos de auditoría generados por las actividades de etiquetas de confidencialidad, vea la sección [Actividades de etiquetas de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) de [Buscar en el registro de auditoría en el portal de cumplimiento de Microsoft Purview](search-the-audit-log-in-security-and-compliance.md).

Esta información de auditoría se representa visualmente en el [explorador de contenido](data-classification-content-explorer.md) y en el [explorador de actividades](data-classification-activity-explorer.md) para ayudarle a comprender cómo se usan las etiquetas de confidencialidad y dónde se encuentra el contenido etiquetado. 

También puede crear informes personalizados con su elección de administración de eventos e información de seguridad (SIEM) al [exportar y configurar los registros de auditoría](export-view-audit-log-records.md). Para obtener soluciones de creación de informes a gran escala, consulte la [referencia de la API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

> [!TIP]
> Para ayudar a crear informes personalizados, consulte las siguientes entradas de blog:
> - [Actividades de registro de auditoría de Microsoft Purview a través de la API de Administración de O365: parte 1](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957171)
> - [Actividades de registro de auditoría de Microsoft Purview a través de la API de Administración de O365: parte 2](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957297) 

## <a name="end-user-documentation"></a>Documentación para el usuario final

- [Aplicar etiquetas de confidencialidad a sus archivos y correos electrónicos en Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Creación de archivos PDF protegidos a partir de archivos de Office](https://support.microsoft.com/topic/aba7e367-e482-49e7-b746-a385e48d01e4)
