---
title: Administración de datos para Microsoft Whiteboard en entornos de GCC
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo habilitar, deshabilitar y administrar el acceso a Whiteboard.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 508557253df5172c3aa89baf7b30c58886ffd73e
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497470"
---
# <a name="manage-data-for-microsoft-whiteboard-in-gcc-environments"></a>Administración de datos para Microsoft Whiteboard en entornos de GCC

>[!NOTE]
> Esta guía se aplica a los entornos de la nube comunitaria (GCC) de la administración pública de EE. UU.

Los datos se almacenan como archivos .whiteboard en OneDrive para la Empresa. Una pizarra promedio podría tener un tamaño de entre 50 KB y 1 MB y estar ubicada donde resida el contenido OneDrive para la Empresa. Para comprobar dónde se crean los nuevos datos, consulte [Dónde se almacenan los datos del cliente de Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Examine la ubicación de OneDrive para la Empresa. Todas las propiedades que se aplican a los archivos generales de OneDrive para la Empresa también se aplican a Whiteboard, excepto para el uso compartido externo.

Puede administrar datos de Pizarra mediante controles de OneDrive para la Empresa existentes. Para obtener más información, vea [Guía de OneDrive para empresas](/onedrive/plan-onedrive-enterprise).

Puede usar las herramientas de OneDrive para la Empresa existentes para satisfacer las solicitudes del interesado (DSR) para el Reglamento general de protección de datos (RGPD). Los archivos de pizarra se pueden mover de la misma manera que otros contenidos de OneDrive para la Empresa. Sin embargo, es posible que no se muevan los vínculos y permisos de uso compartido.

Para administrar los datos, primero debe asegurarse de que Whiteboard está habilitado para su organización. Para obtener más información, consulte [Administración del acceso a Whiteboard en entornos de GCC](manage-whiteboard-access-gcc.md).

## <a name="data-controls-supported"></a>Controles de datos admitidos

Actualmente se admiten los siguientes controles de datos en Whiteboard:

- Directivas de retención
- Quota
- Suspensión legal
- Prevención de pérdida de datos (DLP)
- Exhibición de documentos electrónicos básica: las pizarras se almacenan como archivos .whiteboard en la OneDrive para la Empresa del creador. Se indexan para la búsqueda de palabras clave y tipos de archivo, pero no están disponibles para la vista previa o la revisión. Tras la exportación, un administrador debe volver a cargar el archivo en OneDrive para la Empresa para ver el contenido. Se planea más soporte técnico para el futuro.

## <a name="data-controls-planned"></a>Controles de datos planeados

Los siguientes controles de datos están planeados para futuras versiones de Whiteboard:

- Etiquetas de confidencialidad
- Análisis
- Más compatibilidad con eDiscovery
- Almacenamiento de pizarras en sitios de SharePoint

## <a name="see-also"></a>Vea también

[Administración del acceso a Whiteboard: GCC](manage-whiteboard-access-gcc.md)

[Administración del uso compartido para Pizarra: GCC](manage-sharing-gcc.md)

[Administración de clientes para Whiteboard: GCC](manage-clients-gcc.md)
