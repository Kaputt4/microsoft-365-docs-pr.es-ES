---
title: Referencia de configuración configurable para Microsoft Managed Desktop
description: Establecer categorías para la configuración configurable en Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 2005ead772399f26c3537ac8bf36f6b0810b07fb
ms.sourcegitcommit: 584b4757f715a3eedf748858461c568f45137438
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63495044"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referencia de configuración configurable: Escritorio administrado de Microsoft

En este artículo se enumeran las categorías de configuración que los clientes pueden configurar con Microsoft Managed Desktop. Cada categoría de configuración incluye información sobre requisitos, procedimientos recomendados y cómo personalizar la categoría de configuración.

> [!NOTE]
> Esta página contiene información sobre la configuración solicitada habitualmente. Se aplica al explorador perimetral heredado.

## <a name="desktop-background-picture"></a>Imagen de fondo de escritorio

Puede personalizar la imagen en segundo plano de escritorio para dispositivos de Escritorio administrado de Microsoft en su organización. Puede usar la imagen en segundo plano de escritorio para aplicar una marca de empresa o material de marketing.

### <a name="requirements"></a>Requisitos

Estos requisitos deben cumplirse para una imagen en segundo plano de escritorio:

- Formato de archivo de imagen: .jpg, jpeg o .png
- Ubicación del archivo: hospedar en una ubicación http segura de confianza (https).
- No permitido: las ubicaciones http y de recurso compartido de archivos (unc) no son compatibles.

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizar e implementar la imagen en segundo plano del escritorio

**Para agregar una imagen de fondo de escritorio personalizada:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el área **Configuración**, seleccione **Imagen de fondo de escritorio**.
4. Escriba la ubicación de la imagen que desea usar.
5. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

## <a name="browser-start-pages"></a>Páginas de inicio del explorador

Las páginas de inicio del explorador se abren en pestañas individuales cuando los usuarios inician Microsoft Edge. Si desea facilitar a los usuarios abrir un conjunto de sitios que usan con frecuencia, agregue una página de inicio del explorador para cada sitio.

### <a name="requirements"></a>Requisitos

Debe proporcionar el nombre de dominio completo (FQDN) para los sitios de Internet o intranet para las páginas de inicio del explorador. Si los sitios internos están configurados, informe a los usuarios de que el acceso solo se permite cuando se conecta a la red interna o cuando se conecta a través de VPN.

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizar e implementar páginas de inicio del explorador

**Para agregar una página de inicio del explorador:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el área **Configuración** de trabajo, seleccione **Páginas de inicio del explorador**.
4. Seleccione **Agregar página de inicio**.
5. En **Agregar página de inicio del explorador**, escriba la dirección URL del sitio que desea usar y, a continuación, seleccione **Agregar página de inicio**.
6. Repita los pasos del 1 al 5 para agregar más páginas de inicio del explorador.
7. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

## <a name="enterprise-mode-site-list-location"></a>Enterprise lista de sitios en modo de acceso

Si tienes sitios web y aplicaciones específicos que tienen problemas de compatibilidad con Microsoft Edge, puedes usar la lista de sitios del modo Enterprise para abrir automáticamente los sitios web en Internet Explorer 11. Además, si sabe que los sitios de intranet no funcionan correctamente con Microsoft Edge, puede establecer que todos los sitios de intranet se abran automáticamente en Internet Explorer 11.

Usar Enterprise significa que puedes seguir usando Microsoft Edge como explorador predeterminado, al tiempo que garantizas que tus aplicaciones sigan funcionando en Internet Explorer 11. Para obtener más información sobre las listas de sitios del modo de empresa, vea [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).

Puede especificar una ubicación `https://` o la ubicación de un recurso compartido interno donde ha hospedado la lista de sitios del modo de empresa.

### <a name="requirements"></a>Requisitos

Estos requisitos deben cumplirse para el archivo de lista de sitios del modo de empresa:

- Formato de archivo: archivo XML que cumple los [requisitos del archivo](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file).
- Ubicación del archivo: archivo host en una ubicación https interna.
- No permitido: el hospedaje en un recurso compartido de archivos interno, como `//sharename`, no está permitido.

### <a name="best-practices"></a>Procedimientos recomendados

Estos procedimientos recomendados se ofrecen para ayudar a los clientes a tomar decisiones para modernizar su infraestructura de TI:

| Práctica | Descripción |
| ------ | ------ |
| Elegir un número limitado de sitios | Microsoft Managed Desktop usa Microsoft Edge como explorador preferido para mejorar la seguridad general de la organización y la facilidad de uso para los usuarios. La mayoría de los sitios de esta lista son para aplicaciones web heredadas que necesitan una versión anterior de un explorador. No incluirá tantas características de seguridad. |
| Considere la posibilidad de una alternativa | Considera otro sitio o aplicación web que no requiera un explorador antiguo. O bien, considere la posibilidad de actualizar el sitio para que pueda usar exploradores más recientes. Los exploradores más recientes usan la tecnología más reciente y ayudan a mejorar la seguridad. |

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizar e implementar una Enterprise de lista de modo de sitio

**Para agregar una ubicación de lista del modo de sitio de empresa:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el área **Configuración** de trabajo, **seleccione Enterprise de lista de sitios de modo automático**.
4. Escriba la ubicación https de la lista de sitios.
5. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

## <a name="trusted-sites"></a>Sitios de confianza

Los sitios de confianza permiten personalizar zonas de seguridad, o donde se puede usar un sitio, para distintos sitios. Las zonas de seguridad incluyen:

- Zona 1: zona intranet local
- Zona 2: zona de sitios de confianza
- Zona 3: zona de Internet
- Zona 4: Zona de sitios restringidos

### <a name="requirements"></a>Requisitos

Proporcione el nombre de dominio completo (FQDN) para los sitios de Intranet o Internet para cada sitio de confianza.

### <a name="customize-and-deploy-trusted-sites"></a>Personalizar e implementar sitios de confianza

**Para agregar un sitio de confianza:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el **área Configuración** de trabajo, seleccione **Sitios de** confianza y, a continuación, **seleccione Agregar sitio de confianza**.
4. En **Agregar sitio de confianza**, escriba la dirección URL, elija una zona de seguridad y, a continuación, **seleccione Agregar sitio de confianza**.
5. Repita los pasos del 1 al 4 para cada sitio de confianza que desee agregar.
6. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

**Para quitar un sitio de confianza:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En **Configuración** área de trabajo, seleccione **Sitios de confianza**.
4. Seleccione el sitio que desea eliminar y, a continuación, **seleccione Eliminar**.
5. Repita los pasos del 1 al 4 para cada sitio de confianza que desee eliminar.
6. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

## <a name="proxy"></a>Proxy

Puede administrar la configuración de proxy de red para su organización. Agregue el servidor proxy y el número de puerto y, a continuación, agregue las excepciones del sitio proxy.

Microsoft Managed Desktop incluye un conjunto de excepciones de proxy predeterminadas necesarias para que el servicio funcione. El servicio de Escritorio administrado de Microsoft solo puede modificar la lista de exclusión predeterminada. Para obtener más información, consulte [Configuración de red para Escritorio administrado de Microsoft](../get-ready/network.md).

Las excepciones de sitio proxy agregadas en el portal de Escritorio administrado de Microsoft se agregan a las excepciones de proxy predeterminadas incluidas con el servicio de Escritorio administrado de Microsoft.

> [!NOTE]
> La actualización de la lista de excepciones de proxy predeterminada siempre se prioriza sobre las implementaciones de clientes. Esto significa que la implementación por fases se pausará si hay una implementación para la lista de excepciones de proxy predeterminada.  

### <a name="requirements"></a>Requisitos

Estos requisitos deben cumplirse para las excepciones de servidor proxy y sitio proxy:

- Debe ser una dirección de servidor y un número de puerto válidos.
- Las direcciones URL deben ser un sitio http válido.

### <a name="customize-and-deploy-proxies"></a>Personalizar e implementar servidores proxy

**Para agregar una excepción de sitio proxy individual:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el **área Configuración** de trabajo, seleccione **Proxy**.
4. Escriba el **número de** dirección **y puerto** del servidor proxy y, a continuación, seleccione **Agregar excepción de proxy**.
5. Escriba la dirección URL de un sitio http válido y, a continuación, **seleccione Agregar excepción de proxy**.
6. Repita los pasos del 1 al 5 para cada sitio de confianza que desee agregar.
7. Seleccione **Implementación de** fase para guardar los cambios e implementarlos en el grupo Prueba.

## <a name="additional-resources"></a>Recursos adicionales

- [Introducción a la configuración configurable](config-setting-overview.md)
- [Implementar parámetros configurables](config-setting-deploy.md)
