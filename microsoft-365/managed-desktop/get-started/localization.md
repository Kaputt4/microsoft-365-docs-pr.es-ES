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

Los usuarios Escritorio administrado de Microsoft dispositivos pueden seleccionar el idioma que prefieran durante el proceso de configuración (la experiencia "fuera de la caja") o después.

## <a name="during-setup-the-out-of-box-experience"></a>Durante la instalación (la experiencia "fuera de la caja")

Durante el proceso de completar la configuración, los usuarios pueden seleccionar el idioma que prefieran. Esta selección afecta a estos atributos:

- Windows 10 de idioma:
    - Idioma para mostrar
    - Idioma del teclado
    - Características relacionadas con el idioma a petición

- Aplicaciones Microsoft 365 para Enterprise de idioma:
    - Idioma para mostrar
    - Herramientas de corrección y creación

> [!NOTE]
> Los usuarios solo pueden obtener características relacionadas con el idioma a petición seleccionando el idioma durante el proceso de configuración.

## <a name="after-completing-setup"></a>Después de completar la configuración

Los usuarios pueden seleccionar el idioma que prefieran para Windows 10 y Aplicaciones Microsoft 365 para Enterprise en cualquier momento después de que se complete el proceso de instalación. En particular:

- Windows 10 de idioma:
    - Idioma para mostrar
    - Idioma del teclado

- Aplicaciones Microsoft 365 para Enterprise de idioma:
    - Idioma para mostrar
    - Herramientas de corrección y creación

Para que los [idiomas admitidos](#supported-languages) para Aplicaciones Microsoft 365 para Enterprise que los usuarios puedan instalar, agregue los usuarios al grupo **Modern Workplace-Office-Language_Packs.** Los idiomas estarán disponibles en el Portal de empresa de Intune.


## <a name="supported-languages"></a>Idiomas admitidos

Para los nuevos dispositivos, el fabricante debe proporcionar imágenes de dispositivo que incluyan los idiomas que necesites. Si la imagen del fabricante incluye idiomas distintos de los proporcionados en la lista de idiomas admitidos, el servicio aún la admite.

Si vas a volver a usar dispositivos existentes, es posible que debas trabajar con el representante de tu cuenta microsoft para obtener las imágenes adecuadas. Para obtener más información, consulta [Imágenes del dispositivo](../service-description/device-images.md).

La [imagen universal](../service-description/device-images.md#universal-image) proporcionada por Escritorio administrado de Microsoft incluye estos idiomas y para Windows 10:

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

Aplicaciones Microsoft 365 para Enterprise puede admitir una lista ligeramente diferente.

Si los usuarios necesitan un idioma distinto de los enumerados aquí, debe presentar una solicitud de soporte [técnico](../working-with-managed-desktop/admin-support.md) mediante el portal [de administración](access-admin-portal.md).

## <a name="languages-for-support-and-operations"></a>Idiomas para soporte técnico y operaciones

### <a name="user-support"></a>Soporte al usuario
Escritorio administrado de Microsoft solo admite en inglés. Si los usuarios eligen otro idioma en la aplicación Obtener ayuda, recibirán soporte técnico de los canales de soporte general de Microsoft, en lugar de admitir directamente desde Escritorio administrado de Microsoft. Para obtener más información, vea [Obtener ayuda para los usuarios](../working-with-managed-desktop/end-user-support.md).

Si los usuarios necesitan soporte técnico en otros idiomas, tendrás que proporcionarlo a través de orígenes de soporte técnico que no son de Microsoft o de tu propia organización.

### <a name="admin-support-and-operations"></a>Soporte técnico y operaciones de administración
Escritorio administrado de Microsoft proporciona soporte técnico para administradores solo en inglés. Esto incluye el portal de administración y todas las comunicaciones con Escritorio administrado de Microsoft operaciones. Debe asumir que todas las interacciones e interfaces relacionadas con el administrador estarán en inglés, a menos que se especifique lo contrario.


