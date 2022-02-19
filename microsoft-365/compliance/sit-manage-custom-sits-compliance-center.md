---
title: Administrar tipos de información confidencial personalizados en el Centro de cumplimiento
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo modificar y quitar tipos de información confidencial personalizados en el Centro de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0efbb93096fc3c0b61a57319aa2d23a079f684d1
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902629"
---
# <a name="manage-custom-sensitive-information-types-in-the-compliance-center"></a>Administrar tipos de información confidencial personalizados en el Centro de cumplimiento

En este artículo se le guían los pasos para modificar y quitar un tipo de información confidencial personalizada existente en el Centro de cumplimiento.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Modificar tipos personalizados de información confidencial en el Centro de cumplimiento

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista que desee modificar y seleccione **Editar**.

2. Puede agregar otros patrones, con elementos únicos principales y compatibles, niveles de confianza, proximidad de caracteres y [**comprobaciones adicionales**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks), o editar o quitar los existentes.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Quitar tipos personalizados de información confidencial en el Centro de cumplimiento 

> [!NOTE]
> Solo se pueden quitar los tipos personalizados de información confidencial; no se pueden quitar los tipos de información confidencial integrados.

> [!IMPORTANT]
> Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista que desee quitar.

2. En el menú desplegable que se abre, elija **Eliminar**.
