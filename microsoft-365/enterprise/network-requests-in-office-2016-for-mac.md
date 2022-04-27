---
title: Solicitudes de red en Office para Mac
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: En este artículo se describe qué puntos de conexión y direcciones URL Office para Mac aplicaciones intentan alcanzar y los servicios proporcionados.
ms.openlocfilehash: 477225cf99ead3f5609c8082644293d4ac006603
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091135"
---
# <a name="network-requests-in-office-for-mac"></a>Solicitudes de red en Office para Mac

Office para Mac aplicaciones proporcionan una experiencia de aplicación nativa en la plataforma macOS. Cada aplicación está diseñada para funcionar en una variedad de escenarios, incluidos los estados en los que no hay acceso a la red disponible. Cuando una máquina está conectada a una red, las aplicaciones se conectan automáticamente a una serie de servicios basados en web para proporcionar una funcionalidad mejorada. En la información siguiente se describen los puntos de conexión y las direcciones URL a los que intentan llegar las aplicaciones y los servicios proporcionados. Esta información es útil al solucionar problemas de configuración de red y establecer directivas para servidores proxy de red. Los detalles de este artículo están diseñados para complementar el [artículo sobre direcciones URL y intervalos de direcciones Office 365](urls-and-ip-address-ranges.md), que incluye puntos de conexión para equipos que ejecutan Microsoft Windows. A menos que se indique, la información de este artículo también se aplica a Office 2019 para Mac y Office 2016 para Mac, que están disponibles como una compra única en una tienda minorista o a través de un contrato de licencias por volumen. 

  
La mayoría de este artículo son tablas en las que se detallan las direcciones URL de red, el tipo y la descripción del servicio o característica proporcionados por ese punto de conexión. Cada una de las aplicaciones de Office puede diferir en su uso del servicio y del punto de conexión. Las siguientes aplicaciones se definen en las tablas siguientes:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
El tipo de dirección URL se define de la siguiente manera:
  
- ST: estático: la dirección URL se codifica de forma rígida en la aplicación cliente.
    
- SS: Semi-Static: la dirección URL se codifica como parte de una página web o un redireccionamiento.
    
- CS: Servicio de configuración: la dirección URL se devuelve como parte del servicio de configuración de Office.

    
## <a name="office-for-mac-default-configuration"></a>Office para Mac configuración predeterminada

 **Instalación y actualizaciones**
  
Los siguientes puntos de conexión de red se usan para descargar el programa de instalación de Office para Mac de Microsoft Content Delivery Network (CDN).
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 portal de instalación reenvía el servicio de vínculo a los paquetes de instalación más recientes.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Ubicación de los paquetes de instalación en el Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Ubicación de los paquetes de instalación en el Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Punto de conexión de control de administración para Microsoft AutoUpdate  <br/> |
   
 **Primer inicio de aplicación**
  
Los siguientes puntos de conexión de red se contacta en el primer inicio de una Aplicación de Office. Estos puntos de conexión proporcionan una funcionalidad de Office mejorada para los usuarios y se contacta con las direcciones URL independientemente del tipo de licencia (incluidas las instalaciones de licencias por volumen).
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configuración de 'flighting': permite la iluminación y experimentación de características.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Prueba de configuración de red "piloto"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Prueba de configuración de red "piloto"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Configuration Service: lista maestra de puntos de conexión de servicio.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office descarga telemetría de reglas: informa al cliente sobre los datos y eventos que se cargarán en el servicio de telemetría.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Servicio de telemetría  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Los informes de telemetría Upload: "Heartbeart" y los eventos de error que se producen en el cliente se cargan en el servicio de telemetría.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Template Service: proporciona a los usuarios plantillas de documento en línea.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Descargas de plantillas de Office: Storage de imágenes de plantilla PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Almacene la configuración de Office aplicaciones.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office catálogo de Document Integration Services (lista de servicios y puntos de conexión) y detección de dominio principal.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Recursos para la detección de dominio principal v2 (15.40 y versiones posteriores)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifiestos de Microsoft AutoUpdate: comprueba si hay actualizaciones disponibles  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Biblioteca JavaScript de Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Aplicación de Wikipedia para Office configuración y recursos.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing aplicación de asignación para la configuración y los recursos de Office.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Los usuarios Graph aplicación para Office configuración y recursos.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Novedades de OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nuevo contenido para OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Novedades de las imágenes para OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Servicio de soporte técnico desde la aplicación.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Servicio de detección de cuentas de correo electrónico.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook Detección automática  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook punto de conexión para Microsoft 365 servicio.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Iconos de Outlook complementos.  <br/> |
   
> [!NOTE]
> El servicio de configuración de Office actúa como un servicio de detección automática para todos los clientes Microsoft Office, no solo para Mac. Los puntos de conexión devueltos en la respuesta son semiestáticos en ese cambio es muy poco frecuente, pero sigue siendo posible. 
  
 **Inicio de sesión**
  
Se contacta con los siguientes puntos de conexión de red al iniciar sesión en el almacenamiento basado en la nube. Dependiendo del tipo de cuenta, es posible que se ponga en contacto con diferentes servicios. Por ejemplo:
  
- **MSA: Cuenta Microsoft** : se usa normalmente para escenarios de consumidor y minorista 
    
- **OrgID: cuenta de la organización** : normalmente se usa para escenarios comerciales 
    
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |servicio de autorización de Windows  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servicio de inicio de sesión de Microsoft 365 (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servicio de inicio de sesión de cuenta de Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |personalización de marca de inicio de sesión de Microsoft 365 (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Localizador de documentos y lugares Storage  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servicio de documentos usados más recientemente (MRU)  <br/> |
   
> [!NOTE]
> En el caso de las licencias comerciales y basadas en suscripciones, el inicio de sesión activa el producto y permite el acceso a recursos en la nube, como OneDrive. En el caso de las instalaciones de licencias por volumen, se sigue solicitando a los usuarios que inicien sesión (de forma predeterminada), pero eso solo es necesario para el acceso a los recursos en la nube, ya que el producto ya está activado. 
  
 **Activación del producto**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción y licencia comercial de Microsoft 365. En concreto, esto NO se aplica a las instalaciones de licencias por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Servicio de licencias de Office  <br/> |
   
 **Novedades del contenido**
  
Los siguientes puntos de conexión de red solo se aplican a Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Novedades del contenido de la página JSON.  <br/> |
   
 **Investigador**
  
Los siguientes puntos de conexión de red solo se aplican a Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Servicio web del investigador  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Contenido estático del investigador  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Proveedor de contenido del investigador  <br/> |
   
 **Búsqueda inteligente**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción de Microsoft 365 y licencia por volumen o minorista.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |servicio web de Ideas  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Compatibilidad con la biblioteca de JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |proveedor de contenido de Ideas  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |proveedor de contenido de Ideas  <br/> |
   
 **Diseñador de PowerPoint**
  
Los siguientes puntos de conexión de red solo se aplican a Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |servicio web del Diseñador de PowerPoint  <br/> |
   
 **Inicio rápido de PowerPoint**
  
Los siguientes puntos de conexión de red solo se aplican a Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint servicio web QuickStarter  <br/> |
   
 **Enviar una sonrisa o un ceño fruncido**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción de Microsoft 365 y licencia por volumen o minorista.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Enviar un servicio de sonrisa  <br/> |
   
 **Póngase en contacto con el soporte técnico**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción de Microsoft 365 y licencia por volumen o minorista.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Póngase en contacto con el servicio de soporte técnico  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Servicio de soporte técnico desde la aplicación  <br/> |
   
 **Guardar como PDF**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción de Microsoft 365 y licencia por volumen o minorista.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Servicio de conversión de documentos de Word (PDF)  <br/> |
   
 **Office Apps (también conocido como complementos)**
  
Los siguientes puntos de conexión de red se aplican a las activaciones de suscripción Microsoft 365 y licencia por volumen o minorista cuando se confía en Office complementos de aplicación.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |configuración del almacén de Aplicación de Office  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Recursos de aplicaciones de Wikipedia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing recursos de la aplicación De mapa  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Usuarios Graph recursos de la aplicación  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office servicio de redireccionamiento  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office bibliotecas de JavaScript  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetría y Reporting Service para aplicaciones Office  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Biblioteca JavaScript de Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Biblioteca JavaScript de Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office bibliotecas de JavaScript  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca de JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Elaboración de informes de errores  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de fuente  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Servicio de telemetría  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Informes de telemetría  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca de recursos de Microsoft Store  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de página de Wikipedia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos multimedia de Wikipedia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Marco de espacio aislado de Wikipedia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Plantillas de mapa  <br/> |
   
 **Vínculos seguros**
  
El siguiente punto de conexión de red se aplica a todas las aplicaciones de Office solo para Microsoft 365 suscripción.
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft Caja fuerte Link Service  <br/> |
   
 **Informes de bloqueo**
  
El siguiente punto de conexión de red se aplica a todas las aplicaciones de Office para las activaciones de suscripción Microsoft 365 y licencia comercial/por volumen. Cuando un proceso se bloquea inesperadamente, se genera un informe y se envía al servicio Watson.
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Servicio de informes de errores de Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Servicio de Ideas colaborativa  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opciones para reducir las solicitudes de red y el tráfico

La configuración predeterminada de Office para Mac proporciona la mejor experiencia de usuario, tanto en términos de funcionalidad como de mantenimiento de la máquina actualizada. En algunos escenarios, es posible que desee impedir que las aplicaciones se pongan en contacto con puntos de conexión de red. En esta sección se describen las opciones para hacerlo.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Deshabilitación de Sign-In y Office Add-Ins en la nube
  
Los clientes de licencias por volumen pueden tener directivas estrictas sobre cómo guardar documentos en el almacenamiento basado en la nube. La siguiente preferencia por aplicación se puede establecer para deshabilitar el inicio de sesión de MSA/OrgID y el acceso a Office complementos.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Si los usuarios intentan acceder a la función Sign-In, verán un error que indica que una conexión de red no está presente. Dado que esta preferencia también bloquea la activación de productos en línea, solo se debe usar para las instalaciones de licencias por volumen. En concreto, el uso de esta preferencia impedirá que Office aplicaciones accedan a los siguientes puntos de conexión:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Todos los puntos de conexión enumerados en la sección "Inicio de sesión" anterior.
    
- Todos los puntos de conexión enumerados en la sección "Búsqueda inteligente" anterior.
    
- Todos los puntos de conexión enumerados en la sección "Activación del producto" anterior.
    
- Todos los puntos de conexión que aparecen en la sección "aplicaciones de Office (también conocidos como complementos)" anterior.
    
Para volver a establecer la funcionalidad completa del usuario, establezca la preferencia en "2" o quítelo.
  
> [!NOTE]
> Esta preferencia requiere Office para Mac compilación 15.25 [160726] o posterior. 
  
### <a name="telemetry"></a>Telemetría
  
Office para Mac envía información de telemetría a Microsoft a intervalos regulares. Los datos se cargan en el punto de conexión "Nexus". Los datos de telemetría ayudan al equipo de ingeniería a evaluar el estado y los comportamientos inesperados de cada Aplicación de Office. Hay dos categorías de telemetría:
  
- **Heartbeat** contiene información de versión y licencia. Estos datos se envían inmediatamente después del inicio de la aplicación. 
    
- **El uso** contiene información sobre cómo se usan las aplicaciones y errores no irrecuperables. Estos datos se envían cada 60 minutos. 
    
Microsoft se toma muy en serio su privacidad. Puede leer sobre la directiva de recopilación de datos de Microsoft en [https://privacy.microsoft.com](https://privacy.microsoft.com). Para evitar que las aplicaciones envíen telemetría de "Uso", se puede ajustar la preferencia **SendAllTelemetryEnabled** . La preferencia es por aplicación y se puede establecer a través de perfiles de configuración de macOS o manualmente desde terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

La telemetría de latidos siempre se envía y no se puede deshabilitar.
  
### <a name="crash-reporting"></a>Informes de bloqueo
  
Cuando se produce un error irrecuperable de la aplicación, la aplicación finalizará inesperadamente y cargará un informe de bloqueo en el servicio "Watson". El informe de bloqueo consta de una pila de llamadas, que es la lista de pasos que la aplicación estaba procesando antes del bloqueo. Estos pasos ayudan al equipo de ingeniería a identificar la función exacta que produjo un error y por qué.
  
En algunos casos, el contenido de un documento hará que la aplicación se bloquee. Si la aplicación identifica el documento como causa, preguntará al usuario si está bien enviar también el documento junto con la pila de llamadas. Los usuarios pueden tomar una decisión informada a esta pregunta. Los administradores de TI pueden tener requisitos estrictos sobre la transmisión de documentos y tomar la decisión en nombre del usuario de no enviar nunca documentos. Se puede establecer la siguiente preferencia para evitar que se envíen documentos y para suprimir el mensaje al usuario:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Si **SendAllTelemetryEnabled** está establecido en **FALSE**, se deshabilitan todos los informes de bloqueo para ese proceso. Para habilitar los informes de bloqueo sin enviar telemetría de uso, se puede establecer la siguiente preferencia: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Actualizaciones
  
Microsoft publica Office para Mac actualizaciones a intervalos regulares (normalmente una vez al mes). Recomendamos encarecidamente a los usuarios y administradores de TI que mantengan las máquinas actualizadas para asegurarse de que se instalan las correcciones de seguridad más recientes. En los casos en los que los administradores de TI quieran controlar y administrar estrechamente las actualizaciones de la máquina, se puede establecer la siguiente preferencia para evitar que el proceso de AutoUpdate detecte y ofrezca actualizaciones de productos automáticamente:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Bloqueo de solicitudes con un firewall o proxy
  
Si su organización bloquea las solicitudes a direcciones URL a través de un firewall o servidor proxy, asegúrese de configurar las direcciones URL enumeradas en este documento como permitidas o bloquee con una respuesta 40X (por ejemplo, 403 o 404). Una respuesta 40X permitirá que las aplicaciones Office acepten correctamente la incapacidad de acceder al recurso y proporcionarán una experiencia de usuario más rápida que simplemente quitar la conexión, lo que a su vez hará que el cliente vuelva a intentarlo.
  
Si el servidor proxy requiere autenticación, se devolverá una respuesta 407 al cliente. Para obtener la mejor experiencia, asegúrese de que usa Office para Mac compilaciones 15.27 o posteriores, ya que incluyen correcciones específicas para trabajar con servidores NTLM y Kerberos.
  
  
## <a name="see-also"></a>Vea también

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

