---
title: Obtenga más información sobre el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: El explorador local de prevención de pérdida de datos de Microsoft 365 amplía la supervisión de actividades de archivo y acciones de protección de esos archivos a recursos compartidos de archivos locales y carpetas y bibliotecas de documentos de SharePoint. El examinador de Azure Information Protection (AIP) examina y protege los archivos.
ms.openlocfilehash: fa1c14520c8ad0afa4856fdd8a1c59a0f71f400d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917816"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Obtenga más información sobre el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)

La prevención de pérdida de datos del examinador local es parte de la serie de características de prevención de pérdida de datos (DLP) de Microsoft 365 que se pueden usar para detectar y proteger elementos confidenciales en los servicios de Microsoft 365. Para obtener más información sobre las ofertas de DLP de Microsoft, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).

El **examinador de DLP local** rastrea datos en reposo a nivel local en recursos compartidos de archivos y en bibliotecas y carpetas de documentos de SharePoint para elementos confidenciales que, de filtrarse, constituirían un riesgo para su organización o podrían infringir la directiva de cumplimiento. Esto le proporciona la visibilidad y el control que necesita para asegurarse de que los elementos confidenciales se usan y protegen correctamente, así como para ayudar a evitar algún comportamiento peligroso que podría comprometerlos. El examinador DLP local detecta información confidencial con tipos [integrados](sensitive-information-type-entity-definitions.md) o de [información confidencial personalizada](create-a-custom-sensitive-information-type.md), [etiquetas de confidencialidad](sensitivity-labels.md) o propiedades de archivo. La información sobre qué hacen los usuarios con elementos confidenciales se hace visible en el [explorador de actividades](data-classification-activity-explorer.md). Usted puede aplicar acciones de protección a estos elementos con [directivas DLP](create-test-tune-dlp-policy.md).

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>El examinador DLP local se basa en el examinador de Azure Information Protection

El examinador DLP local se basa en una implementación completa del examinador de Azure Information Protection (AIP) para supervisar, etiquetar y proteger elementos confidenciales. Si no conoce bien el examinador de AIP, le recomendamos que se familiarice con él. Vea estos artículos para obtener más información:

- [¿Qué es Azure Information Protection?](/azure/information-protection/what-is-information-protection)
- [Qué es el examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner)
- [Requisitos para instalar e implementar el examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-prereqs)
- [Tutorial de instalación del examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/tutorial-install-scanner)
- [Configuración e instalación del examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Cliente de etiquetas unificado de Azure Information Protection: historial de versiones y directiva de soporte técnico](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>Acciones de examinador DLP local

El examinador local DLP detecta archivos con uno de estos cuatro métodos:

- tipos de información confidencial
- etiquetas de confidencialidad
- extensión de archivo
- propiedades del documento personalizadas solo en archivos de Office 

Cuando un archivo detectado constituya, de ser filtrado, un riesgo en potencia o una infracción de directiva de cumplimiento, el examinador local DLP puede tomar una de estas cuatro acciones.

|Acción |Descripción  |
|---------|---------|
|**Impedir a estas personas que accedan al archivo almacenado en el examinador local: Todos los usuarios** | Cuando se aplica, esta acción bloquea el acceso a todas las cuentas excepto al propietario del contenido, la última cuenta que modificó el elemento y el administrador. Para ello, quita todas las cuentas de los permisos NTFS/SharePoint a nivel de archivo excepto para el propietario del archivo, el propietario del repositorio (establecido en la configuración [Establecer el propietario del repositorio](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) en el trabajo de análisis de contenido), el último modificador (se puede identificar solo en SharePoint) y el administrador. A la cuenta del examinador también se le conceden derechos FC sobre el archivo.|
|**Impedir que estas personas accedan al archivo almacenado en el examinador local: bloquear el acceso a toda la organización (público)**    |Cuando se aplica, esta acción quita los SID **_Todo el mundo_*_, _*_NT AUTHORITY\authenticated users_*_ y _*_Usuarios de dominio_** de la lista de control de acceso a archivos (ACL). Solo los usuarios y grupos a los que se hayan concedido derechos explícitamente para la carpeta principal o el archivo podrán tener acceso al archivo.|
|**Establecer permisos en el archivo**|Cuando se aplica, esta acción obliga al archivo a heredar los permisos de su carpeta principal. De forma predeterminada, esta acción solo se aplicará si los permisos de la carpeta principal son más restrictivos que los permisos que ya están en el archivo. Por ejemplo, si la ACL del archivo se establece para permitir solo **_usuarios específicos_*_ y la carpeta principal está configurada para permitir el grupo _*_Usuarios del dominio_*_, el archivo no heredará los permisos de la carpeta principal. Puede invalidar este comportamiento seleccionando la opción _* Heredar aunque los permisos de elemento primario sean menos restrictivos**.|
|**Quitar el archivo de una ubicación incorrecta**|Cuando se aplica, esta acción reemplaza el archivo original con un archivo auxiliar con la extensión .txt y coloca una copia del archivo original en una carpeta en cuarentena. 

## <a name="whats-different-in-the-on-premises-scanner"></a>¿Qué tiene de diferente el examinador local?

Debe tener en cuenta algunos conceptos adicionales antes de profundizar en el examinador local.

### <a name="aip-repositories-and-content-scan-jobs"></a>Trabajos de examen de contenido y repositorios de AIP

Necesita crear trabajos de examen de contenido de AIP e identificar los repositorios que hospedan los archivos que quiere que evalúe el motor DLP. Asegúrese de habilitar las reglas DLP en el trabajo de examen de contenido de AIP creado.

### <a name="policy-tips"></a>Sugerencias de directiva

[Las Sugerencias de directiva](use-notifications-and-policy-tips.md) no están disponibles en el examinador local.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Ver eventos del examinador DLP local

Puede ver datos del examinador DLP local en el [Explorador de actividades](data-classification-activity-explorer.md) del Centro de cumplimiento de M365. 

## <a name="next-steps"></a>Pasos siguientes

Ahora que se ha informado sobre el examinador local de DLP, estos los siguientes pasos:

1. [Introducción al examinador local DLP](dlp-on-premises-scanner-get-started.md)
2. [Usar el examinador local DLP](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Vea también

- [Introducción al examinador de prevención de pérdida de datos locales de Microsoft](dlp-on-premises-scanner-get-started.md)
- [Usar el examinador de prevención de pérdida de datos locales de Microsoft](dlp-on-premises-scanner-use.md)
- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)