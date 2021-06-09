---
title: Solicitudes de red en Office para Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: En este artículo se describen los puntos de conexión y las direcciones URL Office para Mac que las aplicaciones intentan alcanzar y los servicios proporcionados.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693941"
---
# <a name="network-requests-in-office-for-mac"></a>Solicitudes de red en Office para Mac

Office para Mac aplicaciones proporcionan una experiencia de aplicación nativa en la plataforma macOS. Cada aplicación está diseñada para funcionar en una variedad de escenarios, incluidos los estados en los que no hay acceso a la red disponible. Cuando un equipo está conectado a una red, las aplicaciones se conectan automáticamente a una serie de servicios basados en web para proporcionar funcionalidad mejorada. En la siguiente información se describen los puntos de conexión y las direcciones URL a las que las aplicaciones intentan llegar y los servicios proporcionados. Esta información es útil al solucionar problemas de configuración de red y establecer directivas para servidores proxy de red. Los detalles de este artículo están diseñados para complementar el artículo Office 365 url e [intervalos](urls-and-ip-address-ranges.md)de direcciones, que incluye puntos de conexión para equipos que ejecutan Microsoft Windows. A menos que se indique, la información de este artículo también se aplica a Office 2019 para Mac y Office 2016 para Mac, que están disponibles como una compra única en una tienda comercial o a través de un contrato de licencias por volumen. 

  
La mayoría de este artículo contiene tablas que detallan las direcciones URL de red, el tipo y la descripción del servicio o característica proporcionados por ese extremo. Cada una de las Office puede diferir en su uso de servicio y punto de conexión. Las siguientes aplicaciones se definen en las tablas siguientes:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
El tipo de dirección URL se define de la siguiente manera:
  
- ST: estático: la dirección URL está codificada de forma predeterminada en la aplicación cliente.
    
- SS: Semi-Static: la dirección URL se codifica como parte de una página web o redirector.
    
- CS: Servicio de configuración: la dirección URL se devuelve como parte del servicio de configuración Office configuración.

    
## <a name="office-for-mac-default-configuration"></a>Office para Mac configuración predeterminada

 **Instalación y actualizaciones**
  
Los siguientes puntos de conexión de red se usan para descargar el Office para Mac de instalación de Microsoft Content Delivery Network (CDN).
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Servicio de vínculo de reenvío del Portal de instalación a los paquetes de instalación más recientes.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Ubicación de los paquetes de instalación en el Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Ubicación de los paquetes de instalación en el Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Extremo de control de administración para Microsoft AutoUpdate  <br/> |
   
 **Primer inicio de la aplicación**
  
Se contacta con los siguientes puntos de conexión de red en el primer inicio de una Aplicación de Office. Estos puntos de conexión proporcionan una Office mejorada para los usuarios y se contacta con las direcciones URL independientemente del tipo de licencia (incluidas las instalaciones de licencias por volumen).
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configuración de 'flighting': permite la iluminación y la experimentación de características.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Prueba de configuración de red "piloto"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Prueba de configuración de red "piloto"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Servicio de configuración: lista maestra de extremos de servicio.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Descarga de telemetría de reglas: informa al cliente sobre qué datos y eventos se cargarán en el servicio de telemetría.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Servicio de telemetría  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Informes Upload telemetría: los eventos de error y "Heartbeart" que se producen en el cliente se cargan en el servicio de telemetría.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Servicio de plantillas: proporciona a los usuarios plantillas de documento en línea.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office Descargas de plantillas: Storage de imágenes de plantilla PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configuración de la tienda para Office aplicaciones.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services Catalog (lista de servicios y puntos de conexión) y Home Realm Discovery.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Recursos para Home Realm Discovery v2 (15.40 y versiones posteriores)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifiestos de Microsoft AutoUpdate: comprueba si hay actualizaciones disponibles  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Biblioteca javascript de Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Aplicación wikipedia para Office configuración y recursos.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Asignar aplicación para Office configuración y recursos.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Las Graph aplicación para Office configuración y recursos.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |What's New content for OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nuevo contenido para OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |What's New images for OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Servicio de soporte técnico desde la aplicación.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Servicio de detección de cuentas de correo electrónico.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook Detección automática  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook punto de conexión para Microsoft 365 servicio.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Iconos para Outlook complementos.  <br/> |
   
> [!NOTE]
> El Office configuration service actúa como un servicio de detección automática para todos los Microsoft Office clientes, no solo para Mac. Los extremos devueltos en la respuesta son semiestáticos en que el cambio es muy poco frecuente, pero aún es posible. 
  
 **Inicio de sesión**
  
Al iniciar sesión en el almacenamiento basado en la nube, se contacta con los siguientes puntos de conexión de red. Según el tipo de cuenta, es posible que se contacte con diferentes servicios. Por ejemplo:
  
- **MSA: cuenta de Microsoft:** normalmente se usa para escenarios de consumidores y comerciales 
    
- **OrgID: cuenta de la organización:** normalmente se usa para escenarios comerciales 
    
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Servicio de autorización  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Servicio de inicio de sesión (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servicio de inicio de sesión de cuenta de Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Aplicación auxiliar del servicio de inicio de sesión de cuenta de Microsoft (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Personal de marca de inicio de sesión (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Localizador de documentos Storage lugares  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servicio de documentos usado más recientemente (MRU)  <br/> |
   
> [!NOTE]
> Para las licencias comerciales y basadas en suscripción, la sesión activa el producto y permite el acceso a recursos en la nube, como OneDrive. En el caso de las instalaciones de licencias por volumen, se sigue solicitando a los usuarios que inicien sesión (de forma predeterminada), pero solo es necesario para obtener acceso a los recursos en la nube, ya que el producto ya está activado. 
  
 **Activación del producto**
  
Los siguientes puntos de conexión de red se aplican Microsoft 365 activaciones de suscripción y licencia comercial. En concreto, esto NO se aplica a las instalaciones de licencias por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Servicio de licencias de Office  <br/> |
   
 **Novedades del contenido**
  
Los siguientes puntos de conexión de red se aplican solo Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |What's New JSON page content.  <br/> |
   
 **Investigador**
  
Los siguientes puntos de conexión de red se aplican solo Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Servicio web de investigador  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Contenido estático del investigador  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Proveedor de contenido de investigador  <br/> |
   
 **Búsqueda inteligente**
  
Los siguientes puntos de conexión de red se aplican tanto a Microsoft 365 de suscripción como a las activaciones de licencia comercial y por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servicio web insights  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Compatibilidad con la biblioteca de JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Proveedor de contenido de Insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Proveedor de contenido de Insights  <br/> |
   
 **Diseñador de PowerPoint**
  
Los siguientes puntos de conexión de red se aplican solo Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Diseñador de PowerPoint web  <br/> |
   
 **Inicio rápido de PowerPoint**
  
Los siguientes puntos de conexión de red se aplican solo Microsoft 365 suscripción.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Servicio web QuickStarter  <br/> |
   
 **Enviar una sonrisa/ceño**
  
Los siguientes puntos de conexión de red se aplican tanto a Microsoft 365 de suscripción como a las activaciones de licencia comercial y por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Enviar un servicio de sonriente  <br/> |
   
 **Póngase en contacto con el soporte técnico**
  
Los siguientes puntos de conexión de red se aplican tanto a Microsoft 365 de suscripción como a las activaciones de licencia comercial y por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Póngase en contacto con el servicio de soporte técnico  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Servicio de soporte técnico desde la aplicación  <br/> |
   
 **Guardar como PDF**
  
Los siguientes puntos de conexión de red se aplican tanto a Microsoft 365 de suscripción como a las activaciones de licencia comercial y por volumen.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Servicio de conversión de documentos de Word (PDF)  <br/> |
   
 **Office Aplicaciones (también conocido como complementos)**
  
Los siguientes puntos de conexión de red se aplican Microsoft 365 activaciones de suscripción y de licencia comercial/por volumen cuando Office complementos de la aplicación son de confianza.
  
|**URL**|**Aplicaciones**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Aplicación de Office de almacenamiento  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Recursos de la aplicación Wikipedia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Asignar recursos de la aplicación  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Los Graph recursos de la aplicación  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Servicio de redirección  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office Bibliotecas de JavaScript  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Servicio de telemetría e informes para Office aplicaciones  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Biblioteca javascript de Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Biblioteca javascript de Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office Bibliotecas de JavaScript  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de soporte técnico  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca de JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Elaboración de informes de errores  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de fuente  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Servicio de telemetría  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Informes de telemetría  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Biblioteca de activos  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de página de Wikipedia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos multimedia de Wikipedia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Marco de espacio aislado de Wikipedia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Plantillas de mapa  <br/> |
   
 **Vínculos seguros**
  
El siguiente punto de conexión de red se aplica a todas las Office para Microsoft 365 suscripción.
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Servicio de vínculos Caja fuerte Microsoft  <br/> |
   
 **Informes de bloqueo**
  
El siguiente punto de conexión de red se aplica a todas las Office para las Microsoft 365 suscripción y las activaciones de licencia comercial/por volumen. Cuando un proceso se bloquea inesperadamente, se genera un informe y se envía al servicio Watson.
  
|**URL**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Servicio de informes de errores de Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Servicio de información de colaboración  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opciones para reducir el tráfico y las solicitudes de red

La configuración predeterminada de Office para Mac proporciona la mejor experiencia del usuario, tanto en términos de funcionalidad como de mantener la máquina actualizada. En algunos escenarios, es posible que desee impedir que las aplicaciones se contacte con puntos de conexión de red. En esta sección se analizan las opciones para hacerlo.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Deshabilitar cloud Sign-In y Office Add-Ins
  
Los clientes de licencias por volumen pueden tener directivas estrictas sobre cómo guardar documentos en el almacenamiento basado en la nube. La siguiente preferencia por aplicación se puede establecer para deshabilitar el inicio de sesión de MSA/OrgID y el acceso a Office complementos.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Si los usuarios intentan acceder a la Sign-In, verán un error de que una conexión de red no está presente. Dado que esta preferencia también bloquea la activación de productos en línea, solo debe usarse para instalaciones de licencias por volumen. En concreto, el uso de esta preferencia impedirá que Office aplicaciones tengan acceso a los siguientes puntos de conexión:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Todos los puntos de conexión enumerados en la sección "Iniciar sesión" anteriores.
    
- Todos los puntos de conexión enumerados en la sección "Búsqueda inteligente" anteriores.
    
- Todos los puntos de conexión enumerados en la sección "Activación del producto" anteriores.
    
- Todos los puntos de conexión enumerados en la sección "Office aplicaciones (también conocido como complementos)" anteriores.
    
Para restablecer la funcionalidad completa del usuario, establezca la preferencia en "2" o quítela.
  
> [!NOTE]
> Esta preferencia requiere Office para Mac compilación 15.25 [160726] o posterior. 
  
### <a name="telemetry"></a>Telemetría
  
Office para Mac envía información de telemetría a Microsoft a intervalos regulares. Los datos se cargan en el punto de conexión "Nexus". Los datos de telemetría ayudan al equipo de ingeniería a evaluar el estado y los comportamientos inesperados de cada Aplicación de Office. Hay dos categorías de telemetría:
  
- **Heartbeat** contiene información de versión y licencia. Estos datos se envían inmediatamente después del inicio de la aplicación. 
    
- **El** uso contiene información sobre cómo se usan las aplicaciones y los errores no fatales. Estos datos se envían cada 60 minutos. 
    
Microsoft se toma muy en serio su privacidad. Puede leer acerca de la directiva de recopilación de datos de Microsoft en [https://privacy.microsoft.com](https://privacy.microsoft.com) . Para evitar que las aplicaciones envíen telemetría de "Uso", se puede ajustar la preferencia **SendAllTelemetryEnabled.** La preferencia es por aplicación y se puede establecer a través de perfiles de configuración de macOS o manualmente desde terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

La telemetría de latido siempre se envía y no se puede deshabilitar.
  
### <a name="crash-reporting"></a>Informes de bloqueo
  
Cuando se produce un error de aplicación fatal, la aplicación finalizará inesperadamente y cargará un informe de bloqueo en el servicio "Watson". El informe de bloqueo consta de una pila de llamadas, que es la lista de pasos que la aplicación estaba procesando antes del bloqueo. Estos pasos ayudan al equipo de ingeniería a identificar la función exacta que falló y por qué.
  
En algunos casos, el contenido de un documento hará que la aplicación se bloquea. Si la aplicación identifica el documento como causa, preguntará al usuario si está bien enviar el documento junto con la pila de llamadas. Los usuarios pueden tomar una decisión informada a esta pregunta. Los administradores de TI pueden tener requisitos estrictos sobre la transmisión de documentos y tomar la decisión en nombre del usuario de no enviar documentos nunca. Se puede establecer la siguiente preferencia para evitar que se envíen documentos y para suprimir el mensaje al usuario:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Si **SendAllTelemetryEnabled** está establecido en **FALSE**, se deshabilitan todos los informes de bloqueo para ese proceso. Para habilitar los informes de bloqueo sin enviar telemetría de uso, se puede establecer la siguiente preferencia: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Actualizaciones
  
Microsoft publica Office para Mac actualizaciones a intervalos regulares (normalmente una vez al mes). Recomendamos encarecidamente a los usuarios y administradores de TI que mantengan las máquinas actualizadas para garantizar que se instalen las últimas correcciones de seguridad. En los casos en los que los administradores de TI desean controlar y administrar estrechamente las actualizaciones de la máquina, se puede establecer la siguiente preferencia para evitar que el proceso de Actualización automática detecte y ofrezca actualizaciones de productos automáticamente:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Bloquear solicitudes con un firewall/proxy
  
Si su organización bloquea las solicitudes a las direcciones URL a través de un firewall o un servidor proxy, asegúrese de configurar las direcciones URL enumeradas en este documento como permitidas o bloques enumerados con una respuesta 40X (por ejemplo, 403 o 404). Una respuesta 40X permitirá a las aplicaciones de Office aceptar correctamente la incapacidad para acceder al recurso y proporcionará una experiencia de usuario más rápida, que simplemente colocar la conexión, lo que a su vez hará que el cliente vuelva a intentar.
  
Si el servidor proxy requiere autenticación, se devolverá una respuesta 407 al cliente. Para obtener la mejor experiencia, asegúrese de que está usando Office para Mac compilaciones 15.27 o posterior, ya que incluyen correcciones específicas para trabajar con servidores NTLM y Kerberos.
  
  
## <a name="see-also"></a>Consulte también

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

