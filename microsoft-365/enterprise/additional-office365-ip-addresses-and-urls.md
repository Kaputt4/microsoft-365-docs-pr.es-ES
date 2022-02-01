---
title: Otros puntos de conexión no incluidos en el servicio Office 365 dirección IP y dirección URL
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/31/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Resumen: el nuevo servicio web de extremo no incluye algunos puntos de conexión para escenarios específicos.'
hideEdit: true
ms.openlocfilehash: 0453efbea7957c3cf859c59da7a2cff7db04b4f0
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295151"
---
# <a name="other-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Otros puntos de conexión no incluidos en el servicio Office 365 dirección IP y dirección URL

Algunos puntos de conexión de red se publicaron anteriormente y no se han incluido en el servicio web Office 365 [dirección IP y dirección URL](microsoft-365-ip-web-service.md). El servicio web publica puntos de conexión de red necesarios para la Office 365 a través de una red perimetral empresarial. Este ámbito actualmente no incluye:

1. Conectividad de red que pueda ser requerida por un centro de datos de Microsoft a una red de cliente (tráfico de red de servidor de entrada híbrido)
2. Conectividad de red desde servidores en una red de cliente en todo el perímetro de la empresa (tráfico de red de servidor saliente).
3. Escenarios poco comunes para requisitos de conectividad de red de un usuario.
4. Requisito de conectividad de resolución DNS (no se muestra a continuación).
5. Sitios de confianza de Internet Explorer o Microsoft Edge.

Aparte de DNS, estas instancias son todas opcionales para la mayoría de los clientes a menos que necesite el escenario específico que se describe.

<br>

****

|Fila|Objetivo|Destino|Tipo|
|---|---|---|---|
|1|**[Import Service](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) for PST and file ingestion**|Consulte el [Servicio de importación para](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) obtener más requisitos.|Escenario de salida poco común|
|2|**[Asistente para soporte y recuperación de Office 365 de Microsoft](https://diagnostics.office.com/#/)**|<https://autodiscover.outlook.com> <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> <https://apibasic.diagnostics.office.com> <br> <https://autodiscover-s.outlook.com> <br> <https://cloudcheckenabler.azurewebsites.net> <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|Tráfico de servidor saliente|
|3|**Azure AD Conectar (opción w/SSO)** <p> WinRM & PowerShell remoto|Entorno de STS de cliente (servidor AD FS y Proxy AD FS) \| Puertos TCP 80 y 443|Tráfico de servidor entrante|
|4|**STS** como los servidores proxy de AD FS (solo para clientes federados)|STS de cliente (como proxy de AD FS) \| Puertos TCP 443 o TCP 49443 con TLS de cliente|Tráfico de servidor entrante|
|5|**[Mensajería unificada de Exchange Online/Integración de SBC](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)**|Bidireccional entre el controlador de borde de sesión local y \*.um.outlook.com|Tráfico de solo servidor saliente|
|6 |**Migración de buzones**<p>Cuando se inicia la migración de buzones de correo [](/exchange/exchange-deployment-assistant) desde el servidor Exchange híbrido local a Office 365, Office 365 se conectará al servidor publicado de Exchange Web Services (EWS)/Mailbox Replication Services (MRS). Si necesita las direcciones IP NAT usadas por los servidores de Exchange Online para restringir las conexiones entrantes de intervalos IP de origen específicos Office 365, se enumeran en los intervalos IP de dirección [URL &](urls-and-ip-address-ranges.md) en el área de servicio "Exchange Online". <p> Debe tenerse cuidado de asegurarse de que el acceso a los puntos de conexión de EWS publicados como OWA no se ven afectados al garantizar que el proxy MRS se resuelve en un FQDN independiente y una dirección IP pública antes de restringir las conexiones TCP 443 de intervalos IP de origen específicos.|Proxy EWS o MRS local de cliente <br> Puerto TCP 443|Tráfico de servidor entrante|
|7 |**[Exchange de](/exchange/exchange-deployment-assistant) coexistencia híbrida**, como el uso compartido de disponibilidad.|Servidor de Exchange local de cliente|Tráfico de servidor entrante|
|8 |**[Exchange autenticación de](/exchange/exchange-deployment-assistant) proxy híbrido**|STS local de cliente|Tráfico de servidor entrante|
|9 |Se usa para configurar [Exchange híbrido](/exchange/exchange-deployment-assistant), mediante el **[Asistente Exchange de configuración híbrida](/exchange/hybrid-configuration-wizard)** <p> Nota: Estos puntos de conexión solo son necesarios para configurar la implementación híbrida de Exchange|domains.live.com en los puertos TCP 80 y 443, solo son necesarios para el Asistente de configuración híbrida de Exchange 2010 SP3 <p> Direcciones IP de DoD y GCC High: 40.118.209.192/32; 168.62.190.41/32 <p> Worldwide Commercial & GCC: \*.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <br> aka.ms/hybridwizard; <br> \*shcwreleaseprod.blob.core.windows.net/shcw/;|Tráfico de solo servidor saliente|
|10|El **servicio Detección** automática se usa en [Exchange escenarios](/exchange/exchange-deployment-assistant) híbridos con autenticación moderna híbrida [con Outlook para iOS y Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <p> `*.acompli.net` <br> `*.outlookmobile.com` <br> `*.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|Servidor de Exchange local de cliente en TCP 443|Tráfico de servidor entrante|
|11|**Exchange de Azure AD híbrida**|*.msappproxy.net|Tráfico de solo servidor saliente TCP|
|12 |Skype Empresarial en Office 2016 incluye el uso compartido de pantalla basado en **vídeo, que** usa puertos UDP. Antes Skype Empresarial clientes en Office 2013 y versiones anteriores usaban RDP a través del puerto TCP 443.|El puerto TCP 443 se abre a 52.112.0.0/14|Versiones de cliente anteriores de Skype Empresarial en Office 2013 y versiones anteriores|
|13|**Skype Empresarial conectividad de servidor local híbrido a** Skype Empresarial Online|13.107.64.0/18, 52.112.0.0/14 <br> Puertos UDP 50,000-59,999 <br> Puertos TCP 50,000-59,999; 5061|Conectividad de salida de servidor local de Skype Empresarial|
|14 |**La RTC en la** nube con conectividad híbrida local requiere conectividad de red abierta a los hosts locales. Para obtener más información acerca Skype Empresarial configuraciones híbridas en línea|Consulte [Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity)|Skype Empresarial híbrido local entrante|
|15 |**FQDN de autenticación e identidad** <p> Para que funcione, el FQDN `secure.aadcdn.microsoftonline-p.com` debe estar en el Internet Explorer (IE) del cliente o en su zona de sitios de confianza de Microsoft Edge.||Sitios de confianza|
|16|**FQDN de Microsoft Teams** <p> Si usa Internet Explorer o Microsoft Edge, debe habilitar las cookies propias y de terceros y agregar los FQDN para Teams a los sitios de confianza. Esto es complementario a los FQDN de todo el conjunto de aplicaciones, los CDN y la telemetría enumerados en la fila 14. Para obtener más información, vea [Problemas conocidos de Microsoft Teams](/microsoftteams/known-issues).||Sitios de confianza|
|17 |**FQDN de SharePoint Online y OneDrive para la Empresa** <p> Todos los FQDN '.sharepoint.com' con "\<tenant\>" en el FQDN deben estar en la zona de sitios de confianza de Internet Explorer o Microsoft Edge del cliente para que funcionen. Además de los FQDN de todo el conjunto de aplicaciones, los CDN y la telemetría enumerados en la fila 14, necesitará agregar también estos puntos de conexión.||Sitios de confianza|
|18 |**Yammer**  <br> Yammer solo está disponible en el explorador y requiere que el usuario autenticado pase por un proxy. Para que funcionen, todos los FQDN de Yammer deben estar en el Internet Explorer del cliente o en su zona de sitios de confianza de Microsoft Edge.
||Sitios de confianza|
|19|Use **[Azure AD Conectar](/azure/active-directory/hybrid/)** para sincronizar cuentas de usuario locales para Azure AD.|Vea [Puertos y protocolos necesarios para la identidad híbrida,](/azure/active-directory/hybrid/reference-connect-ports) [Solución de problemas de conectividad de Azure AD](/azure/active-directory/hybrid/tshoot-connect-connectivity) e [Instalación del Agente de Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints).|Tráfico de solo servidor saliente|
|20|**[Azure AD Conectar](/azure/active-directory/hybrid/)** 21 ViaNet en China para sincronizar cuentas de usuario locales con Azure AD.|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*.partner.microsoftonline.cn:443 <p> Consulte también [Solución de problemas de entrada con problemas de conectividad de Azure AD](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity).|Tráfico de solo servidor saliente|
| 21|**Microsoft Stream** (necesita el Azure AD de usuario). <br> Office 365 mundial (incluido GCC)|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> Puerto TCP 443|Tráfico de servidor entrante|
|22|Use **el servidor MFA** para las solicitudes de autenticación multifactor, tanto las nuevas instalaciones del servidor como la configuración con Servicios de dominio de Active Directory (AD DS).|Consulte [Getting started with the Azure AD multi-factor authentication Server](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).|Tráfico de solo servidor saliente|
|23|**Notificaciones Graph cambios de Microsoft** <p> Los desarrolladores pueden [usar las notificaciones de cambio](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) para suscribirse a eventos en microsoft Graph.|Public Cloud: 52.159.23.209, 52.159.17.84, 52.147.213.251, 52.147.213.181, 13.85.192.59, 13.85.192.123, 13.89.108.233, 13.89.104.147, 20.96.21.67, 20.69.245.215, 137.135.11.161, 137.135.11.116, 52.159.107.50, 52.159.107.4, 52.229.38.131, 52.183.67.212, 52.142.114.29, 52.142.115.31, 51.124.75.43, 51.124.73.177, 20.44.210.83, 20.44.210.146, 40.80.232.177, 40.80.232.118, 20.48.12.75, 20.48.11.201, 104.215.13.23, 104.215.6.169, 52.148.24.136, 52.148.27.39, 40.76.162.99, 40.76.162.42 , 40.74.203.28, 40.74.203.27, 13.86.37.15, 52.154.246.238, 20.96.21.98, 20.96.21.115, 137.135.11.222, 137.135.11.250, 52.159.109.205, 52.159.102.72, 52.151.30.78, 52.191.173.85, 51.104.159.213, 51.104.159.181, 51.138.90.7, 51.138.90.52, 52.148.115.48, 52.148.114.238, 40.80.233.14, 40.80.239.196, 20.48.14.35, 20.48.15.147, 104.215.18.55, 104.215.12.254, 20.199.102.157, 20.199.102.73, 13.87.81.123, 13.87.81.35, 20.111.9.46, 20.111.9.77, 13.87.81.133, 13.87.81.141 <p> Microsoft Cloud for US Government: 52.244.33.45, 52.244.35.174, 52.243.157.104, 52.243.157.105, 52.182.25.254, 52.182.25.110, 52.181.25.67, 52.181.25.66, 52.244.111.156, 52.244.111.170, 52.243.147.249, 52.243.148.1 9, 52.182.32.51, 52.182.32.143, 52.181.24.199, 52.181.24.220 <p> Microsoft Cloud China operado por 21Vianet: 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56, 40.125.138.23, 40.125.136.69, 40.72.155.199, 40.72.155.2169 <br> Puerto TCP 443 <p> Nota: los desarrolladores pueden especificar puertos diferentes al crear las suscripciones.|Tráfico de servidor entrante|
|24|**Indicador de estado de conexión de red**<p>Se usa Windows 10 y 11 para determinar si el equipo está conectado a Internet (no se aplica a clientes que no Windows cliente). Cuando no se pueda alcanzar esta dirección URL, Windows supondrá que no está conectada a Internet y las aplicaciones M365 para Enterprise no intentarán comprobar el estado de activación, lo que provocará errores en las conexiones a Exchange y otros servicios.|www.mstfconnecttest.com <br> 13.107.4.52<p>Vea también [Manage connection endpoints for Windows 11 Enterprise](/windows/privacy/manage-windows-11-endpoints) y [Manage connection endpoints for Windows 10 Enterprise, version 21H2](/windows/privacy/manage-windows-21h2-endpoints).|Tráfico de solo servidor saliente|
|

## <a name="related-topics"></a>Temas relacionados

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)
  
[Supervisar la conectividad de Microsoft 365](./monitor-connectivity.md)
  
[Conectividad de clientes](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Redes de entrega de contenido](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP Ranges and Service Tags: Us Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Intervalos IP de Azure y etiquetas de servicio: Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Intervalos IP de Azure y etiquetas de servicio: China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Espacio IP público de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
