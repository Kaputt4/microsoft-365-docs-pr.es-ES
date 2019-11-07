---
title: Referencia de configuración configurable para escritorio administrado de Microsoft
description: Establecer categorías para las opciones configurables en el escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a405f96ee7a113197fbc9c237779db3e3e5e5ca
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012265"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referencia de opciones configurables-escritorio administrado por Microsoft

En este tema se enumeran las categorías de configuración que los clientes pueden configurar con el escritorio administrado de Microsoft. Cada categoría de configuración incluye información sobre los requisitos, procedimientos recomendados y cómo personalizar la categoría de configuración. 

## <a name="desktop-background-picture"></a>Imagen de fondo de escritorio
Puede personalizar la imagen de fondo de escritorio de los dispositivos de escritorio administrados por Microsoft en su organización. Puede usar esto para aplicar una marca de empresa o material de marketing. 

### <a name="requirements"></a>Requirements

Estos requisitos se deben cumplir para una imagen de fondo de escritorio:
- Formato de archivo de imagen:. jpg, JPEG o. png
- Ubicación del archivo: host en una ubicación http seguro de confianza (https). 
- No permitido: no se admiten las ubicaciones http y de recursos compartidos de archivos (UNC). 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizar e implementar la imagen de fondo de escritorio

**Para agregar una imagen de fondo de escritorio personalizada**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En área de trabajo **configurable** , seleccione **imagen de fondo de escritorio**. 
4. Escriba la ubicación de la imagen que desea usar. 
5. Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba. 

## <a name="browser-start-pages"></a>Páginas de inicio del explorador
Las páginas de inicio del explorador se abren en pestañas individuales cuando los usuarios inician Microsoft Edge. Si desea que los usuarios puedan abrir fácilmente un conjunto de sitios que usan con frecuencia, agregue una página de inicio de explorador para cada sitio. 

### <a name="requirements"></a>Requirements

Debe proporcionar el nombre de dominio completo (FQDN) para los sitios de intranet o Internet en las páginas de inicio del explorador. Si se configuran los sitios internos, informe a los usuarios de que solo se permite el acceso a estos sitios cuando está conectado a la red interna en la oficina o cuando está conectado con una conexión VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalización e implementación de páginas de inicio del explorador

**Para agregar una página de inicio del explorador**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En área de trabajo **configurable** , seleccione **páginas de inicio del explorador**. 
4. Seleccione **Agregar página de inicio**.
5. En **Agregar página de inicio del explorador**, escriba la dirección URL del sitio que desea usar y, a continuación, seleccione **Agregar página de inicio**. 
6. Repita los pasos 1-5 para páginas de inicio adicionales del explorador. 
7. Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba.

## <a name="enterprise-mode-site-list-location"></a>Ubicación de la lista de sitios del modo de empresa

Si tienes sitios web y aplicaciones específicos en los que conoces problemas de compatibilidad con Microsoft Edge, puedes usar la lista de sitios del modo de empresa para que los sitios web se abran automáticamente con Internet Explorer 11. Además, si sabe que los sitios de la intranet no van a funcionar correctamente con Microsoft Edge, puede configurar todos los sitios de intranet para que se abran automáticamente con Internet Explorer 11. El uso del modo de empresa significa que puede seguir usando Microsoft Edge como explorador predeterminado, a la vez que garantiza que las aplicaciones sigan funcionando en Internet Explorer 11. Para obtener más información sobre las listas de sitios del modo de empresa, vea el modo [de empresa y las listas de sitios del modo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)de empresa. 

Puede especificar una ubicación de https://o la ubicación de un recurso compartido interno donde haya hospedado la lista de sitios del modo de empresa. 

### <a name="requirements"></a>Requirements

Estos requisitos deben cumplirse para el archivo de lista de sitios del modo de empresa:
- Formato de archivo: archivo XML que cumple [los requisitos de archivo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Ubicación del archivo: archivo de host en una ubicación https interna. 
- No permitido: no se permite el hospedaje en un recurso compartido de archivos interno, como *//ShareName*

### <a name="best-practices"></a>Procedimientos recomendados

Se ofrecen estos procedimientos recomendados para ayudar a los clientes a tomar decisiones para modernizar su infraestructura de TI:
- **Elegir un número limitado de sitios** : Microsoft Managed Desktop usa Microsoft Edge como explorador preferido para mejorar la seguridad general de la organización y la facilidad de uso para los usuarios. La mayoría de los sitios de esta lista son para las aplicaciones web heredadas que necesitan una versión anterior de un explorador que no incluirá tantas características de seguridad. 
- **Considere** la posibilidad de usar un sitio alternativo o una aplicación web diferente que no requiera un explorador más antiguo. O bien, considere la posibilidad de actualizar el sitio para que pueda usar los exploradores más recientes. Los exploradores más modernos usan la tecnología más reciente y ayudan a mejorar la seguridad.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalización e implementación de la ubicación de la lista del modo de sitio de empresa

**Para agregar una ubicación de la lista en el modo de sitio de empresa**

1.  Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2.  En **configuración**, seleccione **configurable**.
3.  En área de trabajo **configurable** , seleccione ubicación de la **lista de sitios del modo de empresa**. 
4.  Escriba la ubicación https de la lista de sitios. 
5.  Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba.

## <a name="trusted-sites"></a>Sitios de confianza

Los sitios de confianza permiten personalizar las zonas de seguridad o dónde se puede usar un sitio para sitios diferentes. Las zonas de seguridad incluyen: 
- Zona 1: zona de Intranet local
- Zona 2: zona de sitios de confianza
- Zona 3: zona de Internet
- Zona 4: zona de sitios restringidos

### <a name="requirements"></a>Requirements

Proporcione el nombre de dominio completo (FQDN) para los sitios de intranet o de Internet para cada sitio de confianza. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalización e implementación de sitios de confianza

**Para agregar un sitio de confianza**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En área de trabajo **configurable** , seleccione **sitios de confianza**y, a continuación, seleccione **Agregar sitio de confianza**. 
4. En **Agregar sitio de confianza**, escriba la dirección URL, elija una zona de seguridad y, a continuación, seleccione **Agregar sitio de confianza**. 
5. Repita los pasos 1-4 para cada sitio de confianza que desee agregar. 
6. Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba.

**Para quitar un sitio de confianza**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En área de trabajo **configurable** , seleccione **sitios de confianza**. 
4. Seleccione el sitio que desea eliminar y, a continuación, seleccione **eliminar**. 
5. Repita los pasos 1-4 para cada sitio de confianza que desee eliminar. 
6. Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba.

## <a name="proxy"></a>Proxy
Puede administrar la configuración del proxy de red de su organización. Agregue el servidor proxy y el número de puerto y, a continuación, agregue las excepciones de sitio proxy. Microsoft Managed Desktop incluye un conjunto de excepciones de proxy predeterminadas necesarias para que funcione el servicio. La lista de exclusión predeterminada solo puede ser modificada por el servicio de escritorio administrado de Microsoft.  Para obtener más información, consulte [configuración de red para escritorio administrado de Microsoft](../get-ready/network.md). 

Las excepciones de sitio de proxy que agregue en el portal de escritorio administrado de Microsoft se agregan a las excepciones predeterminadas de proxy incluidas en el servicio de escritorio administrado de Microsoft. 

> [!NOTE]
> La actualización de la lista de excepciones de proxy predeterminada siempre tiene prioridad sobre las implementaciones de clientes. Esto significa que la implementación preconfigurada se pondrá en pausa si hay una implementación para la lista de excepciones de proxy predeterminada.  

### <a name="requirements"></a>Requirements

Estos requisitos se deben cumplir con las excepciones de servidor proxy y de sitio proxy:
- Debe ser una dirección de servidor y un número de Puerto válidos
- Las direcciones URL deben ser un sitio http válido 

### <a name="customize-and-deploy-proxies"></a>Personalización e implementación de servidores proxy

**Para agregar una excepción de sitio de proxy individual**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En área de trabajo **configurable** , seleccione **proxy**. 
4. Escriba la **Dirección** y el **número de Puerto** del servidor proxy y, a continuación, seleccione **Agregar excepción de proxy**. 
5. Escriba la dirección URL de un sitio http válido y, a continuación, seleccione **Agregar excepción de proxy**. 
6. Repita los pasos 1-5 para cada sitio de confianza que desee agregar. 
7. Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el grupo de prueba.

## <a name="additional-resources"></a>Otros recursos
- [Información general de configuración configurable](config-setting-overview.md) 
- [Implementar parámetros configurables](config-setting-deploy.md)
