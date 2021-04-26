---
title: Localizar la experiencia del usuario
description: Cómo localización de dispositivos para usuarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023266"
---
# <a name="localize-the-user-experience"></a>Localizar la experiencia del usuario

Los usuarios de dispositivos de Escritorio administrado de Microsoft pueden seleccionar el idioma que prefieran durante el proceso de configuración (la "experiencia de salida") o después.

## <a name="during-setup-the-out-of-box-experience"></a>Durante la instalación (la experiencia "fuera de la caja")

Durante el proceso de completar la configuración, los usuarios pueden seleccionar el idioma que prefieran. Esta selección afecta a estos atributos:

- Características del idioma de Windows 10:
    - Idioma para mostrar
    - Idioma del teclado
    - Características relacionadas con el idioma a petición

- Características del idioma de Aplicaciones de Microsoft 365 para empresas:
    - Idioma para mostrar
    - Herramientas de corrección y creación

> [!NOTE]
> Los usuarios solo pueden obtener características relacionadas con el idioma a petición seleccionando el idioma durante el proceso de configuración.

## <a name="after-completing-setup"></a>Después de completar la configuración

Los usuarios pueden seleccionar el idioma que prefieran para Windows 10 y Aplicaciones de Microsoft 365 para Empresas en cualquier momento una vez completado el proceso de configuración. En particular:

- Características del idioma de Windows 10:
    - Idioma para mostrar
    - Idioma del teclado

- Características del idioma de Aplicaciones de Microsoft 365 para empresas:
    - Idioma para mostrar
    - Herramientas de corrección y creación

Para que los [idiomas admitidos](#supported-languages) para Aplicaciones de Microsoft 365 para empresas estén disponibles para que los usuarios puedan instalarlos, agregue los usuarios al grupo De trabajo **moderno-Office-Language_Packs** empresa. Los idiomas estarán disponibles en el Portal de empresa de Intune.


## <a name="supported-languages"></a>Idiomas admitidos

Para los nuevos dispositivos, el fabricante debe proporcionar imágenes de dispositivo que incluyan los idiomas que necesites. Si la imagen del fabricante incluye idiomas distintos de los proporcionados en la lista de idiomas admitidos, el servicio aún la admite.

Si vas a volver a usar dispositivos existentes, es posible que debas trabajar con el representante de tu cuenta microsoft para obtener las imágenes adecuadas. Para obtener más información, consulta [Imágenes del dispositivo](../service-description/device-images.md).

La [imagen universal proporcionada](../service-description/device-images.md#universal-image) por Microsoft Managed Desktop incluye estos idiomas y para Windows 10:

- Árabe
- Búlgaro
- Chino simplificado
- Chino tradicional
- Croata
- Checo
- Danés  
- Neerlandés  
- Inglés (US, GB, AU, CA, IN)
- Estonio
- Finés 
- Francés (Francia, Canadá)
- Alemán
- Griego
- Hebreo
- Húngaro
- Indonesio
- Italiano
- Japonés
- Coreano
- Letón
- Lituano
- Noruego (bokmal)
- Polaco
- Portugués (Brasil)
- Portugués (Portugal)
- Rumano
- Ruso 
- Serbio (alfabeto latino)
- Eslovaco
- Esloveno
- Español (España, México)
- Sueco
- Tailandés
- Turco
- Ucraniano
- Vietnamita

Aplicaciones de Microsoft 365 para empresas puede admitir una lista ligeramente diferente.

Si los usuarios necesitan un idioma distinto de los enumerados aquí, debe presentar una solicitud de soporte [técnico](../working-with-managed-desktop/admin-support.md) mediante el portal [de administración](access-admin-portal.md).

## <a name="languages-for-support-and-operations"></a>Idiomas para soporte técnico y operaciones

### <a name="user-support"></a>Soporte al usuario
Microsoft Managed Desktop proporciona soporte técnico solo en inglés. Si los usuarios eligen otro idioma en la aplicación Obtener ayuda, recibirán soporte técnico de los canales generales de soporte técnico de Microsoft, en lugar de admitir directamente desde Microsoft Managed Desktop. Para obtener más información, vea [Obtener ayuda para los usuarios](../working-with-managed-desktop/end-user-support.md).

Si los usuarios necesitan soporte técnico en otros idiomas, tendrás que proporcionarlo a través de orígenes de soporte técnico que no son de Microsoft o de tu propia organización.

### <a name="admin-support-and-operations"></a>Soporte técnico y operaciones de administración
Microsoft Managed Desktop proporciona soporte técnico para administradores solo en inglés. Esto incluye el portal de administración y todas las comunicaciones con operaciones de escritorio administrado de Microsoft. Debe asumir que todas las interacciones e interfaces relacionadas con el administrador estarán en inglés, a menos que se especifique lo contrario.


