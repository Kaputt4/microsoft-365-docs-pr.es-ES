---
title: Conceptos básicos sobre DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: El sistema de nombres de dominio asigna los nombres de host del equipo a las direcciones IP, comprender los conceptos básicos de DNS y registrador de dominios puede ayudarle a administrar los dominios.
ms.openlocfilehash: 37d8e885dafaa055ed5cc7eee24456b758ef8b4f
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394293"
---
# <a name="dns-basics"></a>Conceptos básicos sobre DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

Los nombres de dominio, como contoso.com, se administran con un sistema mundial de bases de datos y registradores de dominios. El Sistema de nombres de dominio (DNS) proporciona una asignación entre nombres de hosts de equipos legibles y las direcciones IP que usan los dispositivos de red. Comprender los conceptos básicos de DNS y de registrador de dominios le ayudará a administrar los dominios.

## <a name="watch-domains--dns-an-overview"></a>Ver: Dominios y DNS: Información general
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Los nombres de dominio, como contoso.com, se administran con un sistema mundial de bases de datos y registradores de dominios. El Sistema de nombres de dominio (DNS) proporciona una asignación entre nombres de hosts de equipos legibles y las direcciones IP que usan los dispositivos de red. Comprender los conceptos básicos de DNS y de registrador de dominios le ayudará a administrar los dominios.

## <a name="watch-domains--dns-an-overview"></a>Ver: Dominios y DNS: Información general
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Los nombres de dominio, como contoso.com, se administran con un sistema mundial de bases de datos y registradores de dominios. El Sistema de nombres de dominio (DNS) proporciona una asignación entre nombres de hosts de equipos legibles y las direcciones IP que usan los dispositivos de red. Comprender los conceptos básicos de DNS y de registrador de dominios ayudará a los administradores a administrar los dominios.
  
::: moniker-end

## <a name="what-are-domain-names"></a>¿Qué son los nombres de dominio?

Los nombres de dominio se usan en las direcciones de correo electrónico y URL, y cuentan con distintos niveles. Por ejemplo, correo.contoso.com es un nombre de dominio con los tres niveles siguientes:
  
- **.com** es el dominio de primer nivel. 
    
- **contoso** es el dominio de segundo nivel. 
    
- **correo** es el dominio de tercer nivel. 
    
¿Por qué usar un dominio de tercer nivel? Es posible que le interese tener distintos nombres de dominio para marketing o para un blog. Por ejemplo, blog.contoso.com. Generalmente se agrega un domino de segundo nivel, como contoso.com, para usarlo con Microsoft, pero, si quiere, también puede usar dominios de tercer nivel.
  
Obtenga más información sobre qué puede hacer con los dominios para cada tipo de oferta en la [descripción del servicio de la plataforma de Office 365 y Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/domains).
  
## <a name="understand-dns-record-types"></a>Comprender los tipos de registros DNS

Los registros DNS almacenados en un host DNS de su dominio se usan para dirigir el tráfico del dominio. En la tabla siguiente se describen los registros DNS que se usan con más frecuencia y cómo se usan.
  
|**Registro NS (servidor de nombres)**|**Identifica los servidores de nombres que son los "servidores de nombres autoritativos" de un dominio. Al cambiar los servidores de nombres del dominio, cambia dónde se administran los registros DNS y el lugar en el que el sistema DNS busca información sobre los servidores de correo, etc. Microsoft cuenta con sus propios servidores de nombres, pero también puede optar por usar los servidores de nombres que ya estén configurados en su dominio.**|
|:-----|:-----|
|Registro A (registro de dirección)  <br/> |Asocia un nombre de dominio a una dirección IP.  <br/> |
|Registro CNAME (alias o nombre canónico)  <br/> |Redirecciona un dominio a otro en el sistema DNS. Cuando un servidor de nombres busca un dominio y encuentra que tiene un registro CNAME, el servidor reemplaza el primer nombre de dominio por el CNAME y busca el nombre nuevo.  <br/> |
|Registro MX (intercambiador de correo)  <br/> |Apunta dónde debería enviarse su correo electrónico. También tiene un campo de prioridad para que pueda enviar un correo a diferentes servidores en orden de prioridad.  <br/> |
|Registro SPF (marco de directivas de remitente)  <br/> |Registro TXT que ayuda a evitar la suplantación de identidad (spoofing y phishing) a través del correo electrónico.  <br/> |
|Registro SRV (servicio)  <br/> |Lo utiliza Skype Empresarial Online y Exchange Online para coordinar el flujo de información entre los servicios de Microsoft. Por ejemplo, los registros SRV son necesarios para comprobar la presencia en Outlook Web App y para usar Skype Empresarial Online, Skype u otras herramientas de mensajería instantánea con personas de otras empresas.  <br/> |
|TTL (período de vida)  <br/> |La cantidad de tiempo que un servidor de nombre guarda un registro DNS antes de que el servidor busque una versión actualizada.  <br/> |
   
## <a name="how-does-dns-work"></a>¿Cómo funciona el sistema DNS?

Parte de la configuración del dominio con un servicio de nube como Microsoft 365 incluye cambiar o agregar [registros DNS](dns-basics.md) para el dominio. Estos cambios son necesarios por el modo en que Internet funciona con el Sistema de nombres de dominio (DNS) y los nombres de dominio, para saber dónde debe enviar o buscar algo, como el correo electrónico o los sitios web. 
  
Internet está configurado para utilizar el sistema DNS, o Sistema de nombres de dominio, que nos permite usar nombres conocidos, como contoso.com, para ubicar determinados sitios de Internet que en realidad se denominan con números difíciles de recordar llamados direcciones IP (Protocolo de Internet). Las direcciones IP tienen un aspecto parecido a 70.42.241.42, de modo que es mucho más fácil usar un nombre de dominio para identificar ubicaciones como hosts de correo electrónico y sitios web.
  
En resumen, los registros DNS dicen a Internet dónde enviar el correo electrónico (como joe@contoso.com) o dónde encontrar los sitios web (como www.contoso.com) que usen el nombre de dominio. Cuando introduce la información correcta en los registros DNS adecuados para su dominio, el sistema DNS redirige todo correctamente de modo que, por ejemplo, el correo electrónico llegue a Microsoft 365 en lugar de a otra ubicación.
  
Los registros DNS de un dominio también pueden ser útiles de otras maneras. Por ejemplo, Exchange comprueba un registro DNS que permite a Outlook establecer automáticamente una conexión con el servidor de Exchange adecuado.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>Los registros DNS ayudan a Internet a enviar el correo electrónico a la ubicación adecuada

Como se menciona anteriormente, el sistema DNS básicamente dirige el tráfico por Internet, asignando los nombres de dominio conocidos a aquellas direcciones IP difíciles de recordar. Un registro DNS, denominado registro MX, es específico para enviar el correo electrónico al host correcto.
  
Los registros DNS son como una base de datos de información sobre el dominio. Los registros y sus valores se conservan en lo que se llama un archivo de zona, que incluye una lista de cada registro del dominio y de cuál es su valor. Los registradores de dominios y otras empresas de hospedaje de DNS proporcionan una interfaz de usuario en sus sitios web para que pueda editar los registros en el archivo de zona del dominio. Y aquí es donde puede actualizar el registro MX del dominio, para enviar los mensajes de correo electrónico a Microsoft 365.
  
 *Al cambiar el correo electrónico a Microsoft 365, después de actualizar el registro MX del dominio en el paso siguiente, TODOS los mensajes de correo electrónico que se envíen al dominio empezarán a llegar a Microsoft 365.*  Si otros usuarios usan el dominio para el correo electrónico, tendrá que configurar los buzones de Microsoft 365 de todos esos usuarios. 
  
¿Le parece complicado? Bueno, puede serlo, pero le guiaremos a través de cada paso de la configuración del dominio de Microsoft.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>El sistema DNS también indica a Internet dónde debe buscar sitios web

Cuando escribe la dirección de un sitio web, por ejemplo, www.contoso.com, Internet primero busca en uno de los servidores DNS lo que se denomina un registro de servidor de nombres (NS), en este caso contoso.com. El registro NS indica a Internet dónde debe buscar el archivo de zona que contiene todos los demás valores de registro DNS para aquel dominio. Hay muchos servidores DNS, todos conectados entre sí. Los servidores funcionan de forma conjunta para realizar un seguimiento de todos los nombres de dominio registrados, que tienen que ser únicos, y de dónde se encuentran los archivos de zona del dominio.
  
::: moniker range="o365-worldwide"

Supongamos que el registro NS para contoso.com pone "godaddy.com". Ahora Internet sabe que GoDaddy.com es donde debe buscar el archivo de zona que contiene todos los demás registros DNS para contoso.com. Estos registros DNS incluyen el registro MX que pone dónde deben enviarse los correos electrónicos de contoso.com y otros registros. Si el registro MX tiene un valor que indica (en términos técnicos) "enviar correo electrónico a Microsoft 365", aquí es donde se enviarán todos los mensajes de correo electrónico enviado a una dirección de correo electrónico contoso.com (como joe@contoso.com). Entonces, siempre que haya un buzón llamado "joe" en esa ubicación, el correo electrónico se entregará.

::: moniker-end

::: moniker range="o365-germany"

Supongamos que el registro NS para contoso.com pone "godaddy.com". Ahora Internet sabe que GoDaddy.com es donde debe buscar el archivo de zona que contiene todos los demás registros DNS para contoso.com. Estos registros DNS incluyen el registro MX que pone dónde deben enviarse los correos electrónicos de contoso.com y otros registros. Si el registro MX tiene un valor que indica (en términos técnicos) "enviar correo electrónico a Microsoft 365", aquí es donde se enviarán todos los mensajes de correo electrónico enviado a una dirección de correo electrónico contoso.com (como joe@contoso.com). Entonces, siempre que haya un buzón llamado "joe" en esa ubicación, el correo electrónico se entregará.

::: moniker-end

::: moniker range="o365-21vianet"

Supongamos que el registro NS para contoso.com pone "hichina.com". Ahora Internet sabe que hichina.com es donde debe buscar el archivo de zona que contiene todos los demás registros DNS para contoso.com. Estos registros DNS incluyen el registro MX que pone dónde deben enviarse los correos electrónicos de contoso.com y otros registros. Si el registro MX tiene un valor que indica (en términos técnicos) "enviar correo electrónico a Microsoft 365", aquí es donde se enviarán todos los mensajes de correo electrónico enviado a una dirección de correo electrónico contoso.com (como joe@contoso.com). Entonces, siempre que haya un buzón llamado "joe" en esa ubicación, el correo electrónico se entregará.

::: moniker-end

Los valores reales que debe introducir para que todo esto funcione con Microsoft 365 se muestran en los pasos de configuración del dominio. Si está realizando la configuración de forma manual, deberá copiar y pegar los valores en los registros DNS correctos (registro MX, registros CNAME, etc.) en el host de DNS, que podría ser el registrador de dominios, aunque no tiene por qué serlo.
  
::: moniker range="o365-worldwide"

¿Por qué es posible que el archivo de zona de su dominio esté en otro lugar aparte del registrador de dominios? Bueno, es posible que registre su nombre de dominio en un registrador de dominios como GoDaddy, pero que los registros DNS se administren en otra ubicación, en una empresa de hospedaje DNS independiente o una compañía de hospedaje de sitios web. Los registros NS de su dominio almacenan esta información para que todos los servidores DNS sepan dónde buscar.

::: moniker-end

::: moniker range="o365-germany"

¿Por qué es posible que el archivo de zona de su dominio esté en otro lugar aparte del registrador de dominios? Bueno, es posible que registre su nombre de dominio en un registrador de dominios como GoDaddy, pero que los registros DNS se administren en otra ubicación, en una empresa de hospedaje DNS independiente o una compañía de hospedaje de sitios web. Los registros NS de su dominio almacenan esta información para que todos los servidores DNS sepan dónde buscar.

::: moniker-end

::: moniker range="o365-21vianet"

¿Por qué es posible que el archivo de zona de su dominio esté en otro lugar aparte del registrador de dominios? Bueno, es posible que registre su nombre de dominio en un registrador de dominios como hichina, pero que los registros DNS se administren en otra ubicación, en una empresa de hospedaje DNS independiente o una compañía de hospedaje de sitios web. Los registros NS de su dominio almacenan esta información para que todos los servidores DNS sepan dónde buscar.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>¿Por qué agregar un dominio a Microsoft 365?


Agregar a Microsoft 365 un dominio personalizado, como fourthcoffee.com, le permite usar para el servicio direcciones de correo electrónico e Id. de usuario más breves y familiares. Al registrarse en una cuenta de Microsoft 365, [recibe un dominio](../setup/domains-faq.yml), pero su dirección incluye "onmicrosoft.com". Mucha gente prefiere agregar un dominio propio para su organización y empresa si se va a usar el correo electrónico de Microsoft 365. 
  
> [!NOTE]
> Si solo desea descargar y usar aplicaciones de Microsoft, como Outlook o Word, no deberá agregar un dominio: [Instalar Office en su PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Puede usar su nombre de dominio en Microsoft 365 con su correo electrónico, sitio web público y dirección de mensajería instantánea.
  
- **Correo electrónico:** su nombre de dominio le permite personalizar el correo electrónico, por lo que puede usar una dirección más corta y fácil de recordar que no sea [la dirección de correo electrónico onmicrosoft.com inicial](../setup/domains-faq.yml) que viene con su cuenta. Así, en vez de joe@contoso.onmicrosoft.com, la dirección de correo electrónico (que también es el cuenta profesional que usa para iniciar sesión en Microsoft 365) podría ser joe@contoso.com. 
    
- **Sitio web**: si dispone de una suscripción a Microsoft 365 que incluye un sitio web público de SharePoint Online (ya no está disponible para la compra), la dirección inicial de dicho sitio web es de este tipo: contoso-public.sharepoint.com. Si configura un sitio web para su empresa, puede usar un nombre de dominio personalizado para cambiar el nombre de la dirección del sitio web por algo como, por ejemplo, www.contoso.com. 
    
- **Mensajería instantánea:** la dirección de Skype Empresarial Online también puede personalizarse para usar el nombre del dominio, de modo que las personas de la organización puedan conectarse entre ellas en Skype Empresarial Online usando una dirección más corta y fácil de recordar (por ejemplo, joe@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>¿Por qué agregar un dominio a Microsoft 365?


Agregar a Microsoft 365 un dominio personalizado, como fourthcoffee.com, le permite usar para el servicio direcciones de correo electrónico e Id. de usuario más breves y familiares. Al registrarse en una cuenta de Microsoft 365, [recibe un dominio](../setup/domains-faq.yml), pero su dirección incluye "onmicrosoft.com". Mucha gente prefiere agregar un dominio propio para su organización y empresa si se va a usar el correo electrónico de Microsoft 365. 
  
> [!NOTE]
> Si solo quiere descargar y usar aplicaciones de Microsoft 365, como Outlook o Word, no deberá agregar un dominio: [Instalar Office en su PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Puede usar su nombre de dominio en Microsoft 365 con su correo electrónico, sitio web público y dirección de mensajería instantánea.
  
- **Correo electrónico:** su nombre de dominio le permite personalizar el correo electrónico, por lo que puede usar una dirección más corta y fácil de recordar que no sea [la dirección de correo electrónico onmicrosoft.com inicial](../setup/domains-faq.yml) que viene con su cuenta. Así, en vez de joe@contoso.onmicrosoft.com, la dirección de correo electrónico (que también es el cuenta profesional que usa para iniciar sesión en Microsoft 365) podría ser joe@contoso.com. 
    
- **Sitio web**: si dispone de una suscripción que incluye un sitio web público de SharePoint Online (ya no está disponible para la compra), la dirección inicial de dicho sitio web es de este tipo: contoso-public.sharepoint.com. Si configura un sitio web para su empresa, puede usar un nombre de dominio personalizado para cambiar el nombre de la dirección del sitio web por algo como, por ejemplo, www.contoso.com. 
    
- **Mensajería instantánea:** la dirección de Skype Empresarial Online también puede personalizarse para usar el nombre del dominio, de modo que las personas de la organización puedan conectarse entre ellas en Skype Empresarial Online usando una dirección más corta y fácil de recordar (por ejemplo, joe@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Registros DNS necesarios para Microsoft 365

Se necesitan varios registros DNS para que Microsoft 365 funcione con su dominio. Además de configurar el registro MX del dominio para que el correo electrónico se envíe a Microsoft 365, hay registros para ayudar con tareas como, por ejemplo, asegurarse de que Outlook pueda conectarse automáticamente al servidor de Exchange adecuado, configurar la mensajería instantánea y ayudar a evitar el correo electrónico no deseado.
  
También puede [encontrar una lista de valores](information-for-dns-records.md) para configurar su dominio. Se incluyen directamente en el <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">centro de administración de Microsoft 365</a>. 
  
O, si está planificando una implementación, tal vez quiera revisar una lista de todos los registros DNS necesarios para Microsoft 365, sus funciones y valores de ejemplo. Consulte [Registros externos del sistema de nombres de dominio para Microsoft 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Siguientes pasos

Consulte uno de estos procedimientos: 
  
- ¿No sabe dónde está registrado su dominio? [Obtenga ayuda para encontrar su registrador de dominios](find-your-domain-registrar.md).
- Averigüe [por qué tiene que completar los pasos del asistente](../setup/add-domain.md) para poder usar su dominio con Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)\
[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)\
[Administrar dominios](index.yml) (página de vínculo)