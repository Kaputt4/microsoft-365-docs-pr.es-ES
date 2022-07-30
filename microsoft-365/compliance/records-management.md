---
title: Más información sobre la administración de registros de Microsoft Purview
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
ms.collection:
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- admindeeplinkCOMPLIANCE
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Obtenga información sobre cómo la administración de registros de Microsoft Purview admite elementos de alto valor para requisitos empresariales, legales o de mantenimiento de registros normativos.
ms.openlocfilehash: 326731a80659b58368c41bff7894567e14e2d000
ms.sourcegitcommit: 57c2f5ba74e238543d6fd724ed79527547bd0780
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "67069543"
---
# <a name="learn-about-records-management"></a>Más información sobre la administración de registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!TIP]
> *¿Sabía que puede probar las versiones premium de las nueve soluciones de Microsoft Purview de forma gratuita?* Utilice la prueba de 90 días de las soluciones Purview para explorar cómo las sólidas capacidades de Purview pueden ayudar a su organización a satisfacer sus necesidades de cumplimiento. Los clientes Microsoft 365 E3 y Office 365 E3 pueden empezar ahora en el [Centro de pruebas del portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef). Obtenga información sobre [las personas que pueden registrarse y los términos de la prueba](compliance-easy-trials.md).

Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos. La administración de registros para Microsoft Purview ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no se necesitan retener, no son de gran valor o ya no son necesarios para fines empresariales.

Use las siguientes funcionalidades para admitir la solución de administración de registros para los servicios y aplicaciones de Microsoft 365:

- **Etiquetar contenido como registro**. Cree y configure etiquetas de retención para marcar el contenido como [registro](#records) que los usuarios pueden aplicar o aplicar automáticamente mediante la identificación de información confidencial, palabras clave o tipos de contenido.

- **Migrar y administrar los requisitos de retención con el plan de archivos**. Mediante el uso de un [plan de archivos](file-plan-manager.md), puede incorporar un plan de retención existente a Microsoft 365 o crear uno nuevo para mejorar las capacidades de administración.

- **Configure las opciones de retención y eliminación con etiquetas de retención**. Configure las [etiquetas de retención](retention.md#retention-labels) con los períodos de retención y las acciones en función de varios factores que incluyen la fecha de la última modificación o creación.

- **Inicie diferentes períodos de retención cuando se produzca un evento** con la [retención basada en eventos](event-driven-retention.md).

- **Revisar y validar la eliminación** con [la revisión de eliminación](disposition.md#disposition-reviews) y la prueba de [eliminación de registros](disposition.md#disposition-of-records).

- **Exportar la información sobre todos los elementos que se han eliminado** con la [opción exportar](disposition.md#filter-and-export-the-views).

- **Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Con estas funciones, puede incorporar los requisitos y las programaciones de retención de su organización en una solución de administración de registros para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.

Además de la documentación en línea, puede resultar útil descargar un [conjunto de diapositivas con las preguntas más frecuentes](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) de un seminario web sobre la administración de registros. La grabación del seminario web propiamente dicho ya no está disponible.

## <a name="records"></a>Registros

Cuando el contenido se declara como registro:

- Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Se registran otras actividades sobre el elemento.

- Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.

Usted utiliza las [etiquetas de retención](retention.md#retention-labels) para marcar contenido como un **registro** o un **registro normativo**. La diferencia entre estas dos etiquetas se explica en la siguiente sección. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro o como registro normativo.

Al usar las etiquetas de retención para declarar registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restricciones de acciones permitidas o bloqueadas

Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro o un registro normativo.

Una etiqueta de retención estándar tiene opciones de retención y acciones, pero no marca el contenido como un registro o un registro normativo.

> [!NOTE]
> Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange. La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](record-versioning.md) que no es compatible con los elementos de Exchange. Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.


|Acción| Etiqueta de retención |Registro: bloqueado| Registro: desbloqueado| Registro normativo |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Editar contenidos|Permitido | **Bloqueado** | Permitido | **Bloqueado**|
|Editar propiedades, incluido cambiar nombre|Permitido |Permitido<sup>1</sup> | Permitido | **Bloqueado**|
|Eliminar|Permitido <sup>2</sup> |**Bloqueado** |**Bloqueado**| **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido| Permitido|
|Mover dentro del contenedor <sup>3</sup>|Permitido |Permitido | Permitido| Permitido|
|Moverse a través de contenedores <sup>3</sup>|Permitido |Permitido si nunca se desbloquea | **Bloqueado** | **Bloqueado**|
|Abrir y leer|Permitido |Permitido | Permitido| Permitido|
|Cambiar etiqueta|Permitido |Permitido: solo administradores del contenedor | **Bloqueado**| **Bloqueado**
|Quitar etiqueta|Permitido |Permitido: solo administradores del contenedor | **Bloqueado**| **Bloqueado**

Notas al pie:

<sup>1</sup> De forma predeterminada, está permitida la edición de las propiedades de un registro bloqueado, pero se puede bloquear mediante una opción de configuración de espacio empresarial en el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/) > **Administración de registros** > **Configuración de administración de registros** > **Etiquetas de retención** > **Permitir la edición de propiedades del registro**.

<sup>2</sup> En SharePoint y OneDrive, el borrado de elementos etiquetados se puede bloquear como una opción de configuración de espacio empresarial en el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/) > **Administración de registros** > **Configuración de administración de registros** > **Etiquetas de retención** > **Borrado de elementos**.

Cuando se aplica una etiqueta de retención a un elemento de lista que tiene datos adjuntos de documento, ese documento no hereda la configuración de retención y se puede eliminar del elemento de lista. En cambio, si se declara un registro con una etiqueta de retención, los datos adjuntos del documento heredarán la configuración de retención y no se podrán eliminar.

<sup>3 </sup> Los contenedores incluyen bibliotecas de documentos de SharePoint, cuentas de OneDrive y buzones de Exchange.

> [!IMPORTANT]
> La diferencia más importante que supone un registro normativo es que, una vez que se aplica al contenido, nadie, ni siquiera un administrador global, puede quitar la etiqueta.
>
> Las etiquetas de retención configuradas para los registros normativos también tienen las siguientes restricciones de administrador:
>
> - El período de retención no se puede reducir después de guardar la etiqueta, solo se puede extender.
> - Estas etiquetas no son compatibles con las directivas de etiquetado automático y deben aplicarse mediante [directivas de etiqueta de retención](create-apply-retention-labels.md).
>
> Además, no se puede aplicar una etiqueta normativa a un documento que está desprotegido en SharePoint.
>
> Dado que se trata de acciones irreversibles y restricciones, asegúrese de que realmente necesita usar registros normativos antes de seleccionar esta opción para las etiquetas de retención. Para evitar la configuración accidental, esta opción no está disponible de forma predeterminada, sino que primero se debe habilitar con PowerShell. Las instrucciones se incluyen en [Declarar registros mediante etiquetas de retención](declare-records.md).

## <a name="validating-migrated-records"></a>Validación de registros migrados

Si va a migrar registros a SharePoint o OneDrive, es posible que tenga que validar que estos registros no se han modificado y conservan su estado de inmutabilidad. Por ejemplo, está usando una solución de migración y necesita cumplir los requisitos de cadena de custodia para sus registros. Es posible que las propiedades y los métodos de archivo típicos que se usan para este tipo de validación, como el tamaño de archivo o el hash de archivo, no sean suficientes porque SharePoint actualiza automáticamente los metadatos de un archivo cuando se carga.

En su lugar, para validar los registros migrados, puede usar el valor de la propiedad `vti_writevalidationtoken`, que es un hash XOR codificado en base64 del archivo antes de que SharePoint lo modifique. Siga estos pasos:

1. Genere el hash XOR del archivo original mediante el algoritmo QuickXorHash. Para más información, vea el [fragmento de código del algoritmo QuickXorHash](/onedrive/developer/code-snippets/quickxorhash).

2. Codifique en Base64 el hash XOR. Para más información, consulte la [documentación del método Base64Encode](/windows/win32/seccrypto/utilities-base64encode).

3. Después de migrar el archivo, recupere el valor de la propiedad `vti_writevalidationtoken` del archivo cargado.

4. Compare el valor generado en el paso 2 con el valor recuperado en el paso 3. Estos dos valores deben coincidir. Si lo hacen, ha validado que el registro no ha cambiado.


## <a name="configuration-guidance"></a>Instrucciones de configuración

Consulte [Introducción a la administración de registros](get-started-with-records-management.md). Este artículo contiene información sobre suscripciones, permisos y vínculos a instrucciones de configuración de un extremo a otro para escenarios de administración de registros.
