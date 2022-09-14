---
title: Inicio rápido de Office 365 Content Delivery Network (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/13/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
description: Inicio rápido de Office 365 Content Delivery Network (CDN)
ms.openlocfilehash: 8eefd20386431f653ef7c247bc07119113e78ef4
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670595"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Inicio rápido de Office 365 Content Delivery Network (CDN)

Puede usar la **Office 365 content delivery network (CDN)** integrada para hospedar recursos estáticos (imágenes, JavaScript, hojas de estilos, archivos WOFF) para proporcionar un mejor rendimiento para las páginas de SharePoint Online. La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia. Además, el Office 365 CDN usa el protocolo HTTP/2 para mejorar la compresión y la canalización HTTP. La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

Para obtener información más detallada, consulte [Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>La red CDN de Office 365 solo está disponible para los inquilinos de la nube de producción (en todo el mundo). Actualmente, los inquilinos de las nubes del Gobierno de EE. UU., China y Alemania no admiten la red CDN de Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Uso de la herramienta Diagnóstico de página para SharePoint para identificar elementos que no están en la red CDN

Puede usar la extensión del explorador de **herramientas de Diagnóstico de páginas para SharePoint** para enumerar fácilmente los recursos de las páginas de SharePoint Online que se pueden agregar a un origen de red CDN.

La **herramienta Diagnóstico de páginas para SharePoint** es una extensión de explorador para los nuevos exploradores Microsoft Edge (<https://www.microsoft.com/edge>) y Chrome que analizan el portal moderno de SharePoint Online y las páginas del sitio de publicación clásicas. La herramienta le ofrece un informe para cada página analizada en el que se muestra el rendimiento de la página respecto a un conjunto definido de criterios de rendimiento. Para instalar e informarse de la herramienta Diagnóstico de página de SharePoint, visite [Usar la herramienta Diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md).

Al ejecutar la herramienta Diagnóstico de página para SharePoint en una página de SharePoint Online, puede hacer clic en la pestaña **Pruebas de diagnóstico** para ver una lista de los recursos que la red CDN no hospeda. Estos recursos se mostrarán en el encabezado **Content Delivery Network (CDN),** como se muestra en la captura de pantalla siguiente.

![Diagnóstico de página.](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>La herramienta de Diagnóstico de páginas solo funciona para SharePoint Online y no se puede usar en una página del sistema de SharePoint. 

## <a name="cdn-overview"></a>Introducción a la red CDN

La red CDN Office 365 está diseñada para optimizar el rendimiento de los usuarios mediante la distribución de objetos a los que se accede con frecuencia, como imágenes y archivos javascript, a través de una red global de alta velocidad, lo que reduce el tiempo de carga de la página y proporciona acceso a objetos hospedados lo más cerca posible al usuario. El CDN captura los recursos de una ubicación denominada _origen_. Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que puede acceder una dirección URL.

La CDN de Office 365 se divide en dos tipos básicos:

- **La red CDN pública** está diseñada para usarse para JS (JavaScript), CSS (StyleSheets), archivo de fuente web (WOFF, WOFF2) e imágenes no propietarias como logotipos de empresa.
- **La red CDN privada** está diseñada para ser utilizada para imágenes (PNG, JPG, JPEG, etc.).

Puede elegir tener orígenes públicos o privados para su organización. La mayoría de las organizaciones elegirán implementar una combinación de las dos. Tanto las opciones públicas como las privadas proporcionan mejoras de rendimiento similares, pero cada una tiene atributos y ventajas únicos. Para obtener más información sobre los orígenes de red CDN pública y privada, vea [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Habilitación de la red CDN pública y privada con la configuración predeterminada
Antes de realizar cambios en la configuración de la red CDN del inquilino, debe comprobar que cumple las directivas de cumplimiento, seguridad y privacidad de su organización.

Para obtener opciones de configuración más detalladas, o si ya ha habilitado la red CDN y desea agregar ubicaciones adicionales (orígenes), consulte la sección [Configuración y configuración de la red CDN de Office 365 mediante el Shell de administración de SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell).

Conéctese al inquilino mediante el Shell de administración de SharePoint Online:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Para permitir que la organización use orígenes públicos y privados con la configuración predeterminada, escriba el siguiente comando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

La salida de estos cmdlets debe ser similar a la siguiente:

![Salida de Set-SPOTenantCdnEnabled.](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Vea también

[Uso de la herramienta de diagnóstico de páginas para SharePoint Online](./page-diagnostics-for-spo.md)

[Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de entrega de contenido](./content-delivery-networks.md)

[Planeamiento de red y ajuste del rendimiento para Office 365](./network-planning-and-performance.md)

[Serie de rendimiento de SharePoint: serie de vídeo Office 365 CDN](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
