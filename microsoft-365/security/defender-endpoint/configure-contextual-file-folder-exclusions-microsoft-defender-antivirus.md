---
title: Exclusiones contextuales de archivos y carpetas
description: Describe la funcionalidad de exclusiones de archivos y carpetas contextuales para Antivirus de Microsoft Defender en Windows. Esta funcionalidad le permite ser más específico al definir en qué contexto el Antivirus de Microsoft Defender no debe examinar un archivo o carpeta, aplicando restricciones.
keywords: Antivirus de Microsoft Defender, proceso, exclusión, archivos, exámenes
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 0868250b04120a4eed0cf254e4a9d3692eb661fa
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477965"
---
# <a name="contextual-file-and-folder-exclusions"></a>Exclusiones contextuales de archivos y carpetas

En este artículo o sección se describe la funcionalidad de exclusiones de archivos y carpetas contextuales para antivirus de Microsoft Defender en Windows. Esta funcionalidad le permite ser más específico al definir en qué contexto el Antivirus de Microsoft Defender no debe examinar un archivo o carpeta mediante la aplicación de restricciones.

## <a name="overview"></a>Información general

Las exclusiones están pensadas principalmente para mitigar los efectos en el rendimiento. Se ven penalizado por un valor de protección reducido. Estas restricciones permiten limitar esta reducción de protección especificando las circunstancias en las que se debe aplicar la exclusión. Las exclusiones contextuales no son adecuadas para abordar falsos positivos de forma confiable. Si encuentra un falso positivo, puede enviar archivos para su análisis a través del portal [de Microsoft 365 Defender](https://security.microsoft.com/) (se requiere suscripción) o a través del sitio web [de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission). Para un método de supresión temporal, considere la posibilidad de crear un indicador _de permiso_ personalizado en [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/indicator-file).

Hay cuatro restricciones que puede aplicar para limitar la aplicabilidad de una exclusión:

- **Restricción de tipo de ruta de acceso de archivo o carpeta**. Puede restringir las exclusiones para que solo se apliquen si el destino es un archivo o una carpeta haciendo que la intención sea específica. Si el destino es un archivo pero se especifica que la exclusión es una carpeta, no se aplicará. Por el contrario, si el destino es una carpeta, pero se especifica que la exclusión es un archivo, se aplicará la exclusión.
- **Restricción del tipo de examen**. Permite definir el tipo de examen necesario para que se aplique una exclusión. Por ejemplo, solo quiere excluir una carpeta determinada de exámenes completos, pero no de un examen de "recursos" (examen de destino).
- **Restricción del tipo de desencadenador de examen**. Puede usar esta restricción para especificar que la exclusión solo se debe aplicar cuando un evento específico inició el examen:
  - bajo demanda
  - en el acceso
  - o que se origina en la supervisión del comportamiento
- **Restricción del proceso**. Permite definir que una exclusión solo se debe aplicar cuando un proceso específico tiene acceso a un archivo o carpeta.

## <a name="configuring-restrictions"></a>Configuración de restricciones

Normalmente, las restricciones se aplican agregando el tipo de restricción a la ruta de exclusión de archivos o carpetas.  

| Restriction | TypeName | valor |
|:---|:---|:---|
| Archivo o carpeta  | PathType  | file <br> folder |
| Tipo de examen | ScanType | Rápido <br> Completo |
| Desencadenador de examen | ScanTrigger | Ondemand <br> OnAccess <br> Bm |
| Proceso | Proceso | "<image_path>" |

### <a name="requirements"></a>Requisitos

Esta funcionalidad requiere antivirus de Microsoft Defender:

- Plataforma: **4.18.2205.7** o posterior
- Motor: **1.1.19300.2** o posterior

### <a name="syntax"></a>Sintaxis

Como punto de partida, es posible que ya tenga exclusiones en su lugar que desee hacer más específicas. Para formar la cadena de exclusión, defina primero la ruta de acceso al archivo o carpeta que se va a excluir y, a continuación, agregue el nombre de tipo y el valor asociado, como se muestra en el ejemplo siguiente.

`<PATH>\:{TypeName:value,TypeName:value}`

Tenga en cuenta que _todos los_ **tipos** y **valores** distinguen mayúsculas de minúsculas.

> [!NOTE]  
> Las condiciones dentro `{}` de DEBEN ser true para que la restricción coincida. Por ejemplo, si especifica dos desencadenadores de examen, esto no puede ser true y la exclusión no se aplicará. Para especificar dos restricciones del mismo tipo, cree dos exclusiones independientes.


### <a name="examples"></a>Ejemplos

La cadena siguiente excluye "c:\documents\design.doc" solo si se trata de un archivo y solo en los exámenes en el acceso:

`c:\documents\design.doc\:{PathType:file,ScanTrigger:OnAccess}`

La cadena siguiente excluye "c:\documents\design.doc" solo si se examina (a su acceso) debido a que un proceso que tiene el nombre de imagen "winword.exe":

`c:\documents\design.doc\:{Process:"winword.exe"}`

La ruta de acceso de la imagen de proceso puede contener caracteres comodín, como en el ejemplo siguiente:

`c:\documents\design.doc\:{Process:"C:\Program Files*\Microsoft Office\root\Office??\winword.exe"}`

### <a name="filefolder-restriction"></a>Restricción de archivos o carpetas

Puede restringir las exclusiones para que solo se apliquen si el destino es un archivo o una carpeta haciendo que la intención sea específica. Si el destino es un archivo pero se especifica que la exclusión es una carpeta, no se aplicará la exclusión. Por el contrario, si el destino es una carpeta, pero se especifica que la exclusión es un archivo, se aplicará la exclusión.

#### <a name="filefolder-exclusions-default-behavior"></a>Comportamiento predeterminado de exclusiones de archivos o carpetas

Si no especifica ninguna otra opción, el archivo o carpeta se excluye de todos los tipos de exámenes _y_ la exclusión se aplica independientemente de si el destino es un archivo o una carpeta. Para obtener más información sobre cómo personalizar exclusiones para que solo se apliquen a un tipo de examen específico, consulte [Restricción del tipo de examen](#scan-type-restriction).

#### <a name="folders"></a>Folders

Para asegurarse de que una exclusión solo se aplica si el destino es una carpeta, no un archivo, puede usar la restricción **PathType:folder** . Por ejemplo:

`C:\documents\:{PathType:folder}`

#### <a name="files"></a>Archivos

Para asegurarse de que una exclusión solo se aplica si el destino es un archivo, no una carpeta, puede usar la restricción de archivo PathType: .

Ejemplo:

`C:\documents\database.mdb\:{PathType:file}`

### <a name="scan-type-restriction"></a>Restricción del tipo de examen

De forma predeterminada, las exclusiones se aplican a todos los tipos de examen:  

- **recurso**: un único archivo o carpeta se examina de forma dirigida (por ejemplo, hacer clic con el botón derecho, Examinar)
- **quick**: ubicaciones de inicio comunes utilizadas por malware, memoria y ciertas claves del Registro
- **full**: incluye ubicaciones de examen rápido y sistema de archivos completo (todos los archivos y carpetas)

Para mitigar los problemas de rendimiento, puede excluir que un tipo de examen específico examine una carpeta o un conjunto de archivos. También puede definir el tipo de examen necesario para que se aplique una exclusión.  

Para excluir que una carpeta se examine solo durante un examen completo, especifique un tipo de restricción junto con la exclusión de archivos o carpetas, como en el ejemplo siguiente:

`C:\documents\:{ScanType:full}`

Para excluir que una carpeta se examine solo durante un examen rápido, especifique un tipo de restricción junto con la exclusión de archivos o carpetas:

`C:\program.exe\:{ScanType:quick}`

Si desea asegurarse de que esta exclusión solo se aplica a un archivo específico y no a una carpeta (c:\foo.exe podría ser una carpeta), aplique también la restricción PathType:

`C:\program.exe\:{ScanType:quick,PathType:file}`

### <a name="scan-trigger-restriction"></a>Restricción del desencadenador de examen

De forma predeterminada, las exclusiones básicas se aplican a todos los desencadenadores de examen. La restricción ScanTrigger le permite especificar que la exclusión solo se debe aplicar cuando un evento específico inició el examen; a petición (incluidos los exámenes rápidos, completos y dirigidos), el acceso o el origen de la supervisión del comportamiento (incluidos los exámenes de memoria).

- **OnDemand**: un examen se desencadenó mediante una acción de comando o administrador. Recuerde que los exámenes rápidos y completos programados también pertenecen a esta categoría.
- **OnAccess**: se abre, escribe, lee o modifica un archivo o carpeta (normalmente se considera protección en tiempo real)
- **BM**: un desencadenador de comportamiento hace que la supervisión del comportamiento examine un archivo específico.

Para excluir un archivo o carpeta y su contenido de que solo se examinen cuando se examina el archivo después de acceder a él, defina una restricción de desencadenador de examen como el ejemplo siguiente:

`c:\documents\:{ScanTrigger:OnAccess}`

### <a name="process-restriction"></a>Restricción del proceso

Esta restricción le permite definir que una exclusión solo se debe aplicar cuando un proceso específico tiene acceso a un archivo o carpeta. Un escenario común es cuando se quiere evitar excluir el proceso, ya que esa evitación haría que Antivirus de Defender ignorara otras operaciones por ese proceso.

> [!NOTE]  
>
> El uso de una gran cantidad de restricciones de exclusión de procesos en una máquina puede afectar negativamente al rendimiento.  
> Además, dado que ha restringido la exclusión a un proceso o proceso determinado, otros procesos activos (como la indexación, la copia de seguridad y las actualizaciones) todavía pueden desencadenar exámenes de archivos.

Para excluir un archivo o carpeta solo cuando un proceso específico acceda a él, cree un archivo o una exclusión de carpeta normales y agregue el proceso para restringir la exclusión a:  

`c:\documents\design.doc\:{Process:"winword.exe", Process:"msaccess.exe"}`

### <a name="how-to-configure"></a>Cómo establecer la configuración

Después de crear las exclusiones contextuales deseadas, puede usar la herramienta de administración existente para configurar las exclusiones de archivos y carpetas mediante la cadena que ha creado.

Consulte: [Configuración y validación de exclusiones para exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
