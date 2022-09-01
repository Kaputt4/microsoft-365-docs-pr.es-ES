---
title: Asignación de identidad entre inquilinos (versión preliminar)
description: Cómo asignar identidades entre organizaciones de Microsoft 365 al prepararse para migraciones entre inquilinos.
author: briandaymsft
ms.author: brianday
manager: rolowe
ms.topic: overview
ms.date: 07/18/2022
ms.service: office-365
ms.custom: template-overview
ms.openlocfilehash: 21738fd4131bcaa7ea8c1022608003eea6f1562e
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497407"
---
# <a name="cross-tenant-identity-mapping-preview"></a>Asignación de identidad entre inquilinos (versión preliminar)

La asignación de identidades entre inquilinos es una característica que se puede usar durante las migraciones de una organización de Microsoft 365 a otra (normalmente denominada migración entre inquilinos). Proporciona un método seguro para establecer relaciones de objetos uno a uno a través de los límites de la organización y prepara automáticamente los objetos de destino para una migración correcta.

>[!NOTE]
>La asignación de identidades entre inquilinos se encuentra en una fase de desarrollo en versión preliminar privada. Como proyecto inacabado, cualquier información o disponibilidad está sujeta a cambios en cualquier momento. La compatibilidad con los clientes de versión preliminar privada se controlará por correo electrónico. La asignación de identidades entre inquilinos está cubierta por los **términos de vista previa** de los [Términos de licencia universal de Microsoft para servicios en línea](https://www.microsoft.com/licensing/terms/product/ForOnlineServices/all).

## <a name="benefits-of-using-cross-tenant-identity-mapping"></a>Ventajas del uso de la asignación de identidades entre inquilinos

La asignación de identidades entre inquilinos elimina la necesidad de exportar grandes conjuntos de datos de una organización de origen con el único fin de configurar objetos De usuario habilitado para correo en la organización de destino.

Con la asignación de identidad entre inquilinos, los datos permanecen dentro del límite de seguridad de Microsoft y se copian de forma segura directamente desde la organización de origen a la organización de destino mediante **relaciones de organización especialmente configuradas** que sirven como confianza unidireccional.

El uso de la asignación de identidad entre inquilinos reducirá la posibilidad de errores al configurar lo que podría ser miles de objetos de destino para una migración mediante la configuración automática de valores como _ExchangeGuid_, _ArchiveGuid_ y todas _las direcciones proxy X500 necesarias_.

Algunas ventajas adicionales del uso de la asignación de identidades entre inquilinos:

- Reduce el número de procesos manuales en los que un error puede dar lugar a migraciones con errores
- Automatiza la identificación de objetos dentro del ámbito para migrar desde la organización de origen a la organización de destino.
- Establece un mapa 1:1 de un objeto Usuario de buzón de correo en la organización de origen a un objeto usuario habilitado para correo existente en la organización de destino.
- Automatiza el rellenado de atributos necesarios de la organización de origen Usuario de buzón de correo a la organización de destino Usuario habilitado para correo
- Proporciona una lista de objetos preparados y listos para la [migración de buzones entre inquilinos](cross-tenant-mailbox-migration.md) en función del valor primarySMTPAddress de los usuarios de la organización de origen.

## <a name="faq-about-cross-tenant-identity-mapping"></a>Preguntas más frecuentes sobre la asignación de identidades entre inquilinos

Nos gustaría proporcionar información que se suele solicitar para que pueda evaluar si desea participar en la versión preliminar privada.

- La característica solo está pensada para usarse con [la migración de buzones entre inquilinos (versión preliminar)](cross-tenant-mailbox-migration.md) y no con soluciones de migración de terceros que no sean de Microsoft.
- El procesamiento de datos (almacenamiento, proceso, transferencia, etc.) está actualmente dentro de la Estados Unidos de Estados Unidos y dentro de la Exchange Online región principal de las organizaciones que participan en la migración.
  - En el caso de las organizaciones habilitadas para varias zonas geográficas, se usará la ubicación geográfica principal de la organización para Exchange Online.
- Esta característica solo se puede habilitar actualmente en la oferta mundial de Microsoft 365. No funciona en GCC, GCC High, DoD, Office 365 por 21 Vianet, etc.
- Actualmente se requiere cierta familiaridad con PowerShell, ya que la característica está basada en PowerShell.
- La característica se comunica a través de una conexión cifrada a un punto de conexión REST.
- La característica requiere actualmente el rol De administrador global para la configuración inicial. Este comportamiento puede cambiar en una actualización futura.
- Las relaciones organizativas se usan como un enfoque de protocolo de enlace doble para asegurarse de que ambas organizaciones han autorizado este tipo de transacción para que tenga lugar.
- Funciona con organizaciones híbridas o solo en la nube.
- Las organizaciones de destino en una configuración híbrida necesitarán un servidor exchange local para modificar los objetos De usuario habilitado para correo sincronizados desde el directorio local. No hemos probado la compatibilidad con la nueva característica herramienta de administración de Exchange publicada en Exchange Server 2019 CU12.

## <a name="what-does-participating-in-the-private-preview-entail"></a>¿Qué implica participar en la versión preliminar privada?

Estamos buscando clientes dispuestos a probar la asignación de identidades entre inquilinos y a proporcionar comentarios en función de su experiencia. ¿Ha facilitado la migración en comparación con las migraciones anteriores que ha realizado? ¿Faltan características? Todos los comentarios constructivos son bienvenidos.

## <a name="how-to-participate"></a>Cómo participar

Si desea participar o tiene más preguntas, envíe un correo electrónico [a CTIMPreview@service.microsoft.com](mailto:CTIMPreview@service.microsoft.com) y proporcione información básica sobre la migración con la que desea usar la asignación de identidades entre inquilinos.

## <a name="next-steps"></a>Pasos siguientes

Se recomienda revisar los pasos actuales de migración de buzones entre inquilinos relacionados con la preparación de objetos de usuario de destino para la migración, ya que esta preparación es lo que automatizará la asignación de identidad entre inquilinos.

- [Revisión de la migración de buzones entre inquilinos (versión preliminar)](cross-tenant-mailbox-migration.md#prepare-target-user-objects-for-migration)
