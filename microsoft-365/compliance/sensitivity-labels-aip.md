---
title: Migración del complemento de Azure Information Protection (AIP) a Microsoft Purview Information Protection etiquetado integrado para aplicaciones de Office
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
search.appverid:
- MOE150
- MET150
description: Para Office 365 aplicaciones, comprenda la migración del complemento de Azure Information Protection (AIP) a un etiquetado integrado para proteger la información confidencial.
ms.openlocfilehash: 80cc5a22f3fe604f2579b321bd12546502386988
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644777"
---
# <a name="migrate-the-azure-information-protection-aip-add-in-to-built-in-labeling-for-office-apps"></a>Migración del complemento Azure Information Protection (AIP) al etiquetado integrado para aplicaciones de Office

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Cuando se usan [etiquetas de confidencialidad](sensitivity-labels.md) en Aplicaciones Microsoft 365 en equipos Windows, se recomienda usar el etiquetado integrado en aplicaciones de Office, incluso si tiene instalado el [cliente de etiquetado unificado de Azure Information Protection (AIP](/azure/information-protection/rms-client/aip-clientv2)). En el futuro, el complemento AIP se deshabilitará de forma predeterminada en las versiones más recientes de las aplicaciones de Office.

Para prepararse para este cambio, use este artículo para comprender las ventajas de usar el etiquetado integrado, qué características principales tienen paridad y cómo controlar la migración desde el complemento AIP a la experiencia de etiquetado más reciente.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="built-in-labeling-vs-the-aip-client"></a>Etiquetado integrado frente al cliente de AIP

El etiquetado integrado constituye la piedra angular de una [implementación de Microsoft Purview Information Protection](information-protection-solution.md) porque esta tecnología de etiquetado se extiende entre plataformas (Windows, macOS, iOS, Android y web), así como entre aplicaciones y servicios de Microsoft, etc. El etiquetado integrado también está diseñado para trabajar con otras funcionalidades de Microsoft Purview, como la clasificación de datos y la Prevención de pérdida de datos de Microsoft Purview (DLP).

Dado que las etiquetas integradas no usan un complemento de Office, se benefician de una mayor estabilidad y un mejor rendimiento. También admiten las características más recientes de Microsoft Purview, como los clasificadores avanzados.

Hasta hace poco, el etiquetado integrado estaba desactivado de forma predeterminada en las aplicaciones de Office para Windows cuando se instaló el cliente de AIP. Este valor predeterminado ya no será el caso de las versiones más recientes de Office. Puede controlar el comportamiento predeterminado mediante las instrucciones de la sección siguiente, [Cómo deshabilitar el complemento AIP para usar el etiquetado integrado para aplicaciones de Office](#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps). Por ejemplo, deshabilite el complemento para las pruebas iniciales en un par de equipos y, a continuación, pase a un piloto para algunos usuarios. Cuando esté listo, migre todos los usuarios a la experiencia de etiquetado más reciente.

Al mantener el cliente de AIP instalado pero deshabilitado en las aplicaciones de Office, las demás funcionalidades del cliente de AIP siguen siendo compatibles:

- Opciones de botón derecho en el explorador de archivos para que los usuarios puedan aplicar etiquetas a todos los tipos de archivo.

- Un visor para mostrar archivos cifrados para texto, imágenes o documentos PDF.

- Un módulo de PowerShell para detectar información confidencial en los archivos locales y aplicar o quitar las etiquetas y el cifrado de estos archivos.

- Un escáner para detectar información confidencial almacenada en almacenes de datos locales y, si quiere, etiquetar el contenido

Para obtener más información sobre estas capacidades que amplían el etiquetado más allá de las aplicaciones de Office, consulte la [Guía del administrador de clientes de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide) de la documentación de AIP.

Independientemente del etiquetado, puede seguir usando el módulo [AIPService](/powershell/module/aipservice) PowerShell para la administración a nivel de inquilino del servicio de cifrado. Por ejemplo, configure el acceso de superusuario cuando necesite quitar el cifrado para la recuperación de datos, realizar un seguimiento y revocar documentos abiertos por el cliente de AIP y configurar el período de validez de la licencia de uso para el acceso sin conexión. Para obtener más información, consulte [Administrar la protección de Azure Information Protection mediante PowerShell](/azure/information-protection/administer-powershell).

> [!NOTE]
> Las etiquetas integradas requieren una edición de suscripción de aplicaciones de Office. Si tiene ediciones independientes de Office, a veces denominadas "Office Perpetual", actualice a Aplicaciones Microsoft 365 para Enterprise para beneficiarse de las funcionalidades de etiquetado más recientes.

## <a name="benefits-of-using-built-in-labeling-for-office-apps-vs-the-aip-add-in"></a>Ventajas de usar el etiquetado integrado para aplicaciones de Office frente al complemento de AIP

El cliente de AIP está en [modo de mantenimiento](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-aip-unified-labeling-client-maintenance-mode-and/ba-p/3043613) y no se recomienda usar el complemento AIP para aplicaciones de Office por los siguientes motivos:

- No se admiten nuevas características de etiquetado.
- Los complementos son menos estables porque pueden entrar en conflicto con otros complementos que pueden provocar que las aplicaciones de Office se cuelguen, se bloqueen o deshabiliten automáticamente el complemento.
- Como complemento, se ejecuta [más lentamente](/deployoffice/fieldnotes/performance-recommendations#office-add-ins) y los usuarios pueden deshabilitarlo para omitir los requisitos de etiquetado.
- Cualquier corrección de errores requerirá volver a instalar el cliente de Azure Information Protection.
- The labeling experience for users is slightly different from built-in labels that users have on their other devices (macOS, iOS, Android), and when they use Office for the web. This difference can increase costs for training and support.
- Hay nuevas características de etiquetado de Office publicadas que [solo son compatibles con el etiquetado integrado](#features-supported-only-by-built-in-labeling-for-office-apps) y la lista está creciendo todo el tiempo.

Use el complemento de AIP para las aplicaciones de Windows Office solo si ya lo ha implementado para los usuarios y necesita tiempo para la migración al etiquetado integrado. O bien, si hay una característica clave que los usuarios necesitan que aún no está disponible para su canal de actualización de Office.

## <a name="features-supported-only-by-built-in-labeling-for-office-apps"></a>Características admitidas solo por el etiquetado integrado para aplicaciones de Office

> [!NOTE]
> Muchas características de etiquetado nuevas se encuentran en fase de planificación o desarrollo, por lo que se espera que la lista de esta sección crezca con el paso del tiempo.

Some features are only supported by built-in labeling for Office apps, and won't be supported by the AIP add-in. These include:

- Para el etiquetado automático y recomendado:
    - Acceso a servicios de clasificación inteligentes que incluyen [clasificadores capacitados](classifier-learn-about.md), [coincidencia exacta de datos (EDM)](sit-learn-about-exact-data-match-based-sits.md) y [entidades con nombre](named-entities-learn.md)
    - Detección de información confidencial a medida que los usuarios escriben
    - En Word, los usuarios pueden revisar y quitar el contenido confidencial identificado
- [Barra de confidencialidad](sensitivity-labels-office-apps.md#sensitivity-bar) integrada en flujos de trabajo de usuario existentes
- [Compatibilidad con PDF](sensitivity-labels-office-apps.md#pdf-support)
- En el caso de las etiquetas que permiten a los usuarios asignar permisos, se pueden conceder permisos diferentes (lectura o cambio) a usuarios o grupos
- Solo cifrar para correos electrónicos
- Compatibilidad con el cambio de cuentas
- Los usuarios no pueden deshabilitar el etiquetado

Vea una breve demostración para ver algunas de estas características en acción:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE58yhH]

Para estar a la última con las nuevas funcionalidades de etiquetado disponibles para el etiquetado integrado, consulte las secciones [Novedades en Microsoft Purview](whats-new.md) y **Etiquetas de confidencialidad**.

## <a name="how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps"></a>Cómo deshabilitar el complemento de AIP para usar el etiquetado integrado para las aplicaciones de Office

En el caso de las aplicaciones de Office más recientes, el complemento AIP está deshabilitado de forma predeterminada, por lo que no hay nada que configurar:

- **Compilación 16.0.15716.0+**: Actualmente en [el canal beta](https://office.com/insider)
- **Canal actual** y **canal mensual de empresa**: versión 2211+ (aún no publicada)
- **Canal semianual**: versión 2301+ (aún no publicada)

Si tiene una de estas versiones y necesita usar el complemento AIP en lugar del etiquetado integrado, debe [configurar una nueva configuración para invalidar el valor predeterminado](#how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in).

> [!IMPORTANT]
> Si ha usado anteriormente el complemento AIP como cliente de etiquetado predeterminado en aplicaciones de Office y usa las versiones de Office enumeradas en esta sección, el complemento AIP se deshabilita automáticamente y se reemplaza por el etiquetado integrado.

Para deshabilitar el complemento AIP para versiones anteriores, consulte la sección siguiente.

Recuerde que, cuando el complemento de AIP está deshabilitado, puede seguir usando el cliente de AIP para ampliar el etiquetado más allá de las aplicaciones de Office.

### <a name="how-to-configure-older-versions-of-office-to-disable-the-aip-add-in"></a>Configuración de versiones anteriores de Office para deshabilitar el complemento AIP

En el caso de las aplicaciones de Office anteriores a las versiones enumeradas en la sección anterior, para evitar que el complemento AIP se cargue en aplicaciones de Office, use la configuración de समूह नीति **Lista de complementos administrados**, tal como se documenta en [Sin complementos cargados debido a la configuración de directiva de grupo para los programas de Office 2013 y Office 2016](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

Para las aplicaciones de Windows Office que admiten el etiquetado integrado, use la configuración de Microsoft Word 2016, Excel 2016, PowerPoint 2016 y Outlook 2016, especifique los siguientes identificadores de programación (ProgID) para el cliente de AIP y establezca la opción en **0: el complemento siempre está deshabilitado (bloqueado)**

|Aplicación  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

Implementar esta configuración mediante la directiva de grupo o mediante el [Servicio de directiva de la nube de Office](/DeployOffice/overview-office-cloud-policy-service).

> [!IMPORTANT]
> If you use the Group Policy setting **Use the Sensitivity feature in Office to apply and view sensitivity labels** and set this to **1**, there are some situations where the AIP add-in might still load in Office apps. Blocking the add-in from loading in each app prevents this happening.

Como alternativa, puede deshabilitar o quitar de forma interactiva el complemento de Office **Microsoft Azure Information Protection** de Word, Excel, PowerPoint y Outlook. Este método es adecuado para un solo ordenador y para pruebas ad hoc. Para obtener instrucciones, consulte [Ver, administrar e instalar complementos en los programas de Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d).

Independientemente del método que elija, los cambios surtirán efecto cuando se reinicien las aplicaciones de Office.

Si después de realizar estos cambios, el botón **Confidencialidad** no se muestra en la cinta de Opciones de Office, compruebe si el etiquetado de confidencialidad se ha [desactivado](sensitivity-labels-office-apps.md#if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows) con **la opción Usar la característica Confidencialidad en Office para aplicar y ver etiquetas de confidencialidad** . Aunque esta no es la configuración predeterminada para las aplicaciones de Office, es posible que un administrador haya establecido explícitamente esta configuración mediante समूह नीति o editando directamente el Registro.

### <a name="how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in"></a>Configuración de versiones más recientes de Office para habilitar el complemento AIP

> [!CAUTION]
> Si previamente ha establecido el valor de **Usar la característica de confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad** en **0** (o ha usado la clave del Registro equivalente de **UseOfficeForLabelling**) para deshabilitar el etiquetado integrado porque quería usar el complemento AIP: En adelante, si no configura la nueva configuración que se describe en esta sección, no podrá usar el etiquetado de confidencialidad con el complemento AIP o el etiquetado integrado.

En las [versiones más recientes de Office](#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps), el complemento AIP está deshabilitado de forma predeterminada. Para habilitarlo, debe configurar una nueva configuración de Office en **Configuración de usuario/Plantillas administrativas/Microsoft Office 2016/Configuración de seguridad**:

- **Use el complemento Azure Information Protection para el etiquetado de confidencialidad**. Establezca el valor en **1**.

Esta nueva configuración todavía se está implementando. Si aún no lo ve, espere unos días más e inténtelo de nuevo.

Implementar esta configuración mediante la directiva de grupo o mediante el [Servicio de directiva de la nube de Office](/DeployOffice/overview-office-cloud-policy-service).

Es posible que tenga que configurar opciones adicionales de Office:

1. La configuración de seguridad **Use la característica Confidencialidad de Office para aplicar y ver etiquetas de confidencialidad**, debe ser **0** o no está configurada.

2. Si la lista de complementos administrados bloquea el complemento de AIP, como se describe en la sección anterior, deberá quitar estas entradas para el complemento AIP o establecer su valor **en 1: El complemento siempre está habilitado.** 

## <a name="feature-parity-for-built-in-labeling-and-the-aip-add-in-for-office-apps"></a>Paridad de características para el etiquetado integrado y el complemento de AIP para aplicaciones de Office

Muchas de las características de etiquetado compatibles con el complemento de AIP ahora son compatibles con el etiquetado integrado. Para obtener una lista más detallada de las funcionalidades disponibles, las versiones mínimas que podrían ser necesarias y la información de configuración, consulte [Administración de etiquetas de confidencialidad en aplicaciones de Office](sensitivity-labels-office-apps.md). Para admitir una característica específica, es posible que tenga que cambiar el [canal de actualización de Office](/deployoffice/overview-update-channels).
 
More features are planned and in development. If there's a specific feature that you're interested in, check the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) and consider joining the [Microsoft Information Protection in Office Private Preview](https://aka.ms/MIP/PreviewRing).

Use la siguiente información para ayudarle a identificar si las características que usa con el complemento AIP están disponibles actualmente con el etiquetado integrado. Las características que aún no están disponibles, pero en el planeamiento o la implementación, pueden retrasar la migración final para los usuarios, pero ahora puede empezar a probar las otras características para acelerar una migración posterior.

|Característica o funcionalidad del complemento AIP|Etiquetado integrado |
|:-------------------------------|:----------------:|
|**Categoría: General** ||
|Informes y auditorías centrales|![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels-office-apps.md#auditing-labeling-activities) |
|Nube de administración pública|![Se admite.](../media/yes-icon.png)|
|Administración puede deshabilitar el etiquetado para todas las aplicaciones|  ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels-office-apps.md#if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows)|
|**Categoría: Experiencia del usuario** ||
|Botón Etiquetado de la cinta de opciones|![Se admite.](../media/yes-icon.png)|
|Compatibilidad con varios idiomas para nombres de etiquetas e información sobre herramientas| ![Se admite.](../media/yes-icon.png) <br>[Más información](create-sensitivity-labels.md#example-configuration-to-configure-a-sensitivity-label-for-different-languages) |
|Visibilidad de etiquetas en una barra de herramientas| [En versión preliminar](sensitivity-labels-office-apps.md#sensitivity-bar) |
|Colores de etiqueta| [En versión preliminar](sensitivity-labels-office-apps.md#label-colors) |
|**Categoría: Acciones de etiquetado** ||
|Etiquetado manual |  ![Se admite.](../media/yes-icon.png) <br>[Más información](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) |
|Etiquetado obligatorio | ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels.md#what-label-policies-can-do)|
|Etiquetado predeterminado <br> - Elementos nuevos y existentes <br> - Configuración independiente del correo electrónico|  ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels.md#what-label-policies-can-do) |
|Recomendado o automático |![Se admite.](../media/yes-icon.png) <br>[Más información](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) |
|Justificación de cambiar a una versión anterior |  ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels.md#what-label-policies-can-do)|
| **Categoría: marcas visuales** | |
|Encabezados, pies de página, marca de agua| ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels.md#what-label-policies-can-do)|
|Marcado dinámico| ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)|
|Marcado visual por aplicación| ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels-office-apps.md#setting-different-visual-markings-for-word-excel-powerpoint-and-outlook)|
| **Categoría: cifrado** | |
|Permisos definidos por el administrador | ![Se admite.](../media/yes-icon.png) <br>[Más información](encryption-sensitivity-labels.md#assign-permissions-now) |
|Permisos definidos por el usuario <br> - No reenviar para Outlook <br> - Permisos personalizados de usuario y grupo para Word, Excel y PowerPoint| ![Se admite.](../media/yes-icon.png) <br>[Más información](encryption-sensitivity-labels.md#let-users-assign-permissions)|
|Permisos definidos por el usuario <br> - Permisos personalizados de toda la organización especificando dominios para Word, Excel y PowerPoint | [En versión preliminar](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions) |
|Coautoría y autoguardado | ![Se admite.](../media/yes-icon.png) <br>[Más información](sensitivity-labels-coauthoring.md) |
| | |

No olvide usar la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) para identificar y realizar un seguimiento de las nuevas características en el desarrollo.

### <a name="support-for-powershell-advanced-settings"></a>Compatibilidad con la configuración avanzada de PowerShell

El cliente AIP admite muchas personalizaciones mediante la [configuración avanzada de PowerShell](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#configuring-advanced-settings-for-the-client-via-powershell). Para obtener la configuración avanzada aplicable a las aplicaciones de Office que también son compatibles con el etiquetado integrado, vea la lista en [New-Label](/powershell/module/exchange/new-label) o [Set-Label](/powershell/module/exchange/set-label), y [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy) o [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy).

Sin embargo, es posible que no necesite usar PowerShell para configurar las opciones admitidas porque se incluyen en la configuración estándar del Centro de cumplimiento de Microsoft Purview. Por ejemplo, la configuración de la interfaz de usuario para elegir colores de etiqueta y desactivar el etiquetado obligatorio para Outlook.

Las siguientes configuraciones del complemento AIP que aún no son compatibles con el etiquetado integrado incluyen:

- [Herencia de etiquetas de archivos adjuntos a mensajes de correo electrónico](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#for-email-messages-with-attachments-apply-a-label-that-matches-the-highest-classification-of-those-attachments)
- [S/MIME para Outlook](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#configure-a-label-to-apply-smime-protection-in-outlook)
    - Esta configuración está empezando a [implementarse en versión preliminar para el etiquetado integrado en todas las plataformas](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook)
- [Compartir en exceso los mensajes emergentes para Outlook](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#implement-pop-up-messages-in-outlook-that-warn-justify-or-block-emails-being-sent)
- [Subetiqueta predeterminada para una etiqueta principal](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#specify-a-default-sublabel-for-a-parent-label)
- [Quitar marcas de contenido externo](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#remove-headers-and-footers-from-other-labeling-solution )

## <a name="features-not-planned-to-be-supported-by-built-in-labeling-for-office-apps"></a>Características no planeadas para ser compatibles con el etiquetado integrado para las aplicaciones de Office

Aunque se agregan nuevas funcionalidades para el etiquetado integrado continuamente, el complemento de Office AIP admite las siguientes funcionalidades que no están planificadas para estar disponibles en futuras versiones para el etiquetado integrado:

- Aplicación de etiquetas a formatos de Microsoft Office 97-2003, como archivos .doc
- Registro de uso local en el registro de eventos de Windows
- Equipos desconectados permanentemente
- Ediciones independientes de Office (a veces denominadas "Office Perpetua") en lugar de basadas en suscripciones

## <a name="migration-planning-for-the-aip-add-in-for-office-apps"></a>Planeamiento de la migración para el complemento AIP para aplicaciones de Office

Para realizar la transición sin problemas al uso del etiquetado integrado para aplicaciones de Office, use la información de esta página para preparar un plan de migración que incluya las siguientes tareas:

- Identifique las características que usa actualmente y pruébelas con el etiquetado integrado para asegurarse de que comprende la configuración y la experiencia del usuario.

- Identifique las nuevas características que quiera usar y decida si desea incluirlas en la migración o en una fase posterior.

- Asegúrese de que todas las dependencias están en su lugar, como Aplicaciones Microsoft 365 for Enterprise se implementa con el canal de actualización correcto y el complemento AIP deshabilitado, y que las [licencias correctas se asignan a los usuarios](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-information-protection-sensitivity-labeling).

- Actualice toda la documentación interna y el entrenamiento, y prepare el departamento de soporte técnico y los usuarios para que cambien.

Para ayudarle con su recorrido de migración, se recomienda la [guía de migración y el cuaderno de estrategias de Microsoft Purview Customer Experience Engineering (CxE).](https://microsoft.github.io/ComplianceCxE/playbooks/AIP2MIPPlaybook)
