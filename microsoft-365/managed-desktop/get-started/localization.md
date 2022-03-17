---
title: Localizar la experiencia del usuario
description: Cómo localización de dispositivos para usuarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c429a072d6ceb2d5d1472533649e30d1fc1a0078
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525007"
---
# <a name="localize-the-user-experience"></a>Localizar la experiencia del usuario

Los usuarios de dispositivos de Escritorio administrado de Microsoft pueden seleccionar el idioma que prefieran durante el proceso de configuración (la "experiencia inicial") o después.

## <a name="during-setup-the-out-of-box-experience"></a>Durante la instalación (la experiencia "fuera de la caja")

Durante la configuración, los usuarios pueden seleccionar el idioma que prefieran. Esta selección afecta a estos atributos:

| Atributo | Description |
| ------ | ------ |
| Windows 10 de idioma | <ul><li>Idioma para mostrar</li><li>Idioma del teclado</li><li>Características relacionadas con el idioma a petición</li><ul> |
| Aplicaciones Microsoft 365 para Enterprise de idioma | <ul><li>Idioma para mostrar</li><li>Herramientas de corrección y creación</li></ul> |

> [!NOTE]
> Los usuarios solo pueden obtener características relacionadas con el idioma a petición seleccionando el idioma durante el proceso de configuración.

## <a name="after-completing-setup"></a>Después de completar la configuración

Los usuarios pueden seleccionar el idioma que prefieran para Windows 10 y Aplicaciones Microsoft 365 para Enterprise en cualquier momento después de que se complete el proceso de instalación. En concreto:

| Característica | Descripción |
| ------ | ------ |
| Windows 10 de idioma | <ul><li>Idioma para mostrar</li><li>Idioma del teclado</li><ul> |
| Aplicaciones Microsoft 365 para Enterprise de idioma | <ul><li>Idioma para mostrar</li><li>Herramientas de corrección y creación</li></ul> |

## <a name="install-more-languages"></a>Instalar más idiomas

> [!NOTE]
> A partir del 16 de marzo de 2022, estamos eliminando gradualmente el grupo Modern Workplace-Office-Language_Packs que permite a los tuyos agregar idiomas a Microsoft Office. La transición al nuevo método (vea más adelante) se completará en abril de 2022. Si tiene algún problema durante este período de transición, póngase en contacto con el [soporte técnico](../working-with-managed-desktop/admin-support.md).

De forma predeterminada, Microsoft Office requiere que los usuarios sean administradores. Microsoft Managed Desktop implementa una directiva de Office para permitir a los usuarios estándar instalar paquetes de accesorios de idioma directamente desde sus Office aplicaciones. Para obtener más información, [consulta Permitir que los usuarios que no son administradores instalen idiomas adicionales](/deployoffice/overview-deploying-languages-microsoft-365-apps#allow-users-who-arent-admins-to-install-additional-languages).

## <a name="supported-languages"></a>Idiomas admitidos

Para los nuevos dispositivos, el fabricante debe proporcionar imágenes de dispositivo que incluyan los idiomas que necesites. Si la imagen del fabricante incluye idiomas que no están incluidos en la lista de idiomas admitidos, el servicio aún admite el dispositivo.

Si estás reusando dispositivos existentes, es posible que debas trabajar con el representante de tu cuenta microsoft para obtener imágenes adecuadas. Para obtener más información, consulta [Imágenes de dispositivo](../service-description/device-images.md).

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

> [!NOTE]
> Aplicaciones Microsoft 365 para Enterprise puede admitir una lista ligeramente diferente.

Si los usuarios necesitan un idioma distinto de los enumerados aquí, debe presentar una solicitud de [soporte técnico mediante](../working-with-managed-desktop/admin-support.md) el [portal de administración](access-admin-portal.md).

## <a name="languages-for-support-and-operations"></a>Idiomas para soporte técnico y operaciones

### <a name="admin-support-and-operations"></a>Soporte técnico y operaciones de administración

Microsoft Managed Desktop proporciona soporte técnico para administradores solo en inglés. Esta compatibilidad incluye el portal de administración y todas las comunicaciones con operaciones de escritorio administrado de Microsoft. Debe asumir que todas las interacciones e interfaces relacionadas con el administrador estarán en inglés, a menos que se especifique lo contrario.
