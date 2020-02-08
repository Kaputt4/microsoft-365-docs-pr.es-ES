---
title: RGPD de uso compartido de archivos local
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en el uso compartido de archivos de Windows Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e5431c4f0953a9d65246f65d783bf6753c5f9bef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596427"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a>RGPD para uso compartido de archivos de Windows Server local.

El método recomendado básico para el uso compartido de archivos es:

-   Use Azure Information Protection para etiquetar los datos confidenciales.

-   Use el escáner de Azure Information Protection para buscar datos.

El enfoque recomendado para el uso compartido de archivos incluye estos pasos:

1.  **Instale y configure el escáner de Azure Information Protection.**

    -   Decida qué tipos de datos confidenciales quiere usar.

    -   Especifique las carpetas locales y los recursos compartidos de red que se van a usar.

2.  **Complete un ciclo de detección.**

    -   Ejecute el escáner en el modo de detección y valide los resultados.

    -   Si es necesario, optimice las condiciones y los tipos de información confidencial.

    -   Evalúe el impacto esperado de aplicar etiquetas automáticamente.

3.  **Ejecute el analizador de Azure Information Protection para aplicar etiquetas a los documentos necesarios**.

4.  **Para obtener protección:**

    -   Configure las reglas de prevención de pérdida de datos de Exchange para proteger los documentos con la etiqueta que desee.

    -   Asegúrese de usar permisos para limitar quién puede obtener acceso a los archivos.

5.  **Para supervisar, integre los registros de Windows Server con una herramienta SIEM.**

    -   Para buscar datos personales para solicitudes de datos personales, utilice el escáner de Azure Information Protection. También puede configurar la búsqueda de SharePoint Server para rastrear el uso compartido de archivos.

Para obtener más información sobre cómo usar el escáner de Azure Information Protection para buscar y etiquetar datos personales, vea el Kit de herramientas de detección de datos de RGPD de Microsoft en [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>).

Para obtener información sobre cómo configurar el escáner para buscar condiciones y usar los tipos de información confidencial prevención de pérdida de datos (DLP) de Office 365, consulte [Configuración de las condiciones para la clasificación automática y recomendada en Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Tenga en cuenta que los nuevos tipos de información confidencial de Office 365 no estarán disponibles inmediatamente para su uso con el escáner y que los tipos de información confidencial personalizados no pueden usarse con este.
