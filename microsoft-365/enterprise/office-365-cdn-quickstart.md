---
title: Office 365 Content Delivery Network inicio rápido (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network inicio rápido (CDN)
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921599"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network inicio rápido (CDN)

Puede usar el Office 365 Content Delivery Network **integrado (CDN)** para hospedar activos estáticos (imágenes, JavaScript, hojas de estilos, archivos WOFF) para proporcionar un mejor rendimiento para las páginas de SharePoint Online. La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia. Además, el Office 365 CDN usa el protocolo HTTP/2 para mejorar la compresión y la canalización HTTP. La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

Para obtener instrucciones más detalladas, vea [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>El Office 365 CDN solo está disponible para los inquilinos en la nube de producción (en todo el mundo). Actualmente, los inquilinos de las nubes de Estados Unidos, China y Alemania no admiten el Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Use la herramienta Diagnóstico de página para SharePoint para identificar elementos que no están en CDN

Puede usar  el diagnóstico de página para la extensión del explorador de herramientas SharePoint para enumerar fácilmente los activos de las páginas de SharePoint Online que se pueden agregar a un CDN origen.

La **herramienta Diagnóstico de** página para SharePoint es una extensión de explorador para el nuevo Microsoft Edge ( y los exploradores Chrome que analizan tanto SharePoint Portal moderno en línea como páginas de sitio de publicación https://www.microsoft.com/edge) clásicas. La herramienta le ofrece un informe para cada página analizada en el que se muestra el rendimiento de la página respecto a un conjunto definido de criterios de rendimiento. Para instalar e informarse de la herramienta Diagnóstico de página de SharePoint, visite [Usar la herramienta Diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md).

Al ejecutar la herramienta Diagnósticos de página para SharePoint en una página de  SharePoint Online, puede hacer clic en la pestaña Pruebas de diagnóstico para ver una lista de activos que el CDN. Estos activos se mostrarán bajo el encabezado **Content Delivery Network (CDN) como** se muestra en la captura de pantalla siguiente.

![Diagnósticos de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>La herramienta de Diagnóstico de páginas solo funciona para SharePoint Online y no se puede usar en una página del sistema de SharePoint. 

## <a name="cdn-overview"></a>CDN Información general

El Office 365 CDN está diseñado para optimizar el rendimiento de los usuarios mediante la distribución de objetos a los que se accede con frecuencia como imágenes y archivos javascript a través de una red global de alta velocidad, lo que reduce el tiempo de carga de la página y proporciona acceso a objetos hospedados lo más cerca posible para el usuario. El CDN recupera los activos de una ubicación denominada _origen_. Un origen puede ser un sitio SharePoint, biblioteca de documentos o carpeta a la que una dirección URL puede tener acceso.

El Office 365 CDN está separado en dos tipos básicos:

- **El CDN** público está diseñado para usarse para JS (JavaScript), CSS (StyleSheets), archivo de fuente web (WOFF, WOFF2) e imágenes no propietarias como logotipos de empresa.
- **El CDN** privado está diseñado para usarse para imágenes (PNG, JPG, JPEG, etc.).

Puede elegir tener orígenes públicos o privados para su organización. La mayoría de las organizaciones elegirán implementar una combinación de las dos. Las opciones públicas y privadas proporcionan ganancias de rendimiento similares, pero cada una tiene atributos y ventajas únicos. Para obtener más información acerca de los orígenes CDN públicos y privados, vea [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Cómo habilitar los servicios públicos y CDN con la configuración predeterminada
Antes de realizar cambios en la configuración de CDN inquilino, debe comprobar que cumple las directivas de cumplimiento, seguridad y privacidad de su organización.

Para obtener opciones de configuración más detalladas, o si ya ha habilitado CDN y desea agregar ubicaciones adicionales (orígenes), consulte la sección Configurar y configurar el Office 365 CDN mediante el Shell de administración en línea de [SharePoint](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Conectar a su inquilino mediante el Shell SharePoint administración en línea:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Para permitir que la organización use orígenes públicos y privados con la configuración predeterminada, escriba el siguiente comando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

El resultado de estos cmdlets debe tener el siguiente aspecto:

![Salida de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Consulte también

[Usar la herramienta Diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md)

[Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de entrega de contenido](./content-delivery-networks.md)

[Planeamiento de red y ajuste del rendimiento para Office 365](./network-planning-and-performance.md)

[SharePoint Serie de rendimiento: Office 365 CDN de vídeo](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)