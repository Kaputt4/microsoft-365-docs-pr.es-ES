---
title: Data Residency para otros servicios de Microsoft 365
description: Más información sobre Data Residency para otros servicios de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 0c8cb3f31d2b4a553c190cd384978d30d7802ec4
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806311"
---
# <a name="data-residency-for-other-microsoft-365-services"></a>Data Residency para otros servicios de Microsoft 365

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

Use las instrucciones siguientes para determinar dónde se encuentran los datos. Haga referencia a la _geografía predeterminada_ del _inquilino_.

### <a name="azure-active-directory-aad"></a>Azure Active Directory (AAD)

Consulte Ubicaciones de [datos de Azure Active Directory](https://aka.ms/aaddatamap).

### <a name="forms"></a>Forms
Los inquilinos de los países miembros de la UE mantienen datos en _la región macro geografía 1 – EMEA_. Todos los demás inquilinos tienen datos de cliente almacenados en el Estados Unidos.

### <a name="intune"></a>Intune
Consulte endpoint.microsoft.com, Administración de inquilinos | Estado del inquilino para los inquilinos existentes. Si no tiene un inquilino existente, cree un inquilino de prueba y aprovisione Intune.

- Microsoft no almacenará los datos del cliente de Intune en reposo fuera de la zona geográfica indicada. Excepto si:
- Es necesario que Microsoft proporcione asistencia al cliente, solucione problemas del servicio o cumpla los requisitos legales.
- El cliente configura una cuenta para permitir dicho almacenamiento de datos de clientes, incluido el uso de los siguientes:
- Características diseñadas para funcionar de forma global, como Content Delivery Network (CDN), que proporciona un servicio de almacenamiento en caché global y almacena datos de clientes en ubicaciones periféricas en todo el mundo.
- Para Azure Active Directory: consulte Ubicaciones de [datos de Azure Active Directory](https://aka.ms/aaddatamap).
- Versión preliminar, beta u otros servicios preliminares, que, por lo general, almacenan datos de clientes en Estados Unidos, pero pueden almacenarlos de forma global. En cualquier caso, Microsoft no controla ni limita la geoárea desde la cual los clientes o usuarios finales pueden tener acceso a los datos de los clientes. Del mismo modo, cuando los datos del cliente de otros servicios se integren posteriormente en Intune, los datos del cliente de origen seguirán almacenados según los compromisos geográficos del otro servicio (si los hubiera); solo la copia de los datos del cliente integrada en Intune se almacenará en la configuración geográfica de Intune indicada.

### <a name="office-for-mobile"></a>Office para dispositivos móviles
Los datos del cliente de este servicio proceden de otros servicios, como Exchange Online y SharePoint Online. No hay datos de clientes almacenados fuera de esos servicios con la excepción del dispositivo móvil.

### <a name="onenote-services"></a>Servicios de OneNote
OneNote almacena los datos de los clientes en OneDrive para la Empresa. Sin embargo, tiene una API que puede hacer que las cachés persistentes se realicen fuera de la geografía donde OneDrive para la Empresa almacena los datos del cliente.

### <a name="planner"></a>Planner
Consulte la [sección Static data location information for select workloads (Información de ubicación de datos estáticos para cargas de trabajo selectas](#static-data-location-information-for-select-workloads) ).

### <a name="power-apps-for-microsoft-365"></a>Power Apps para Microsoft 365
Consulte Ubicaciones de [datos y disponibilidad de Dynamics 365 | Microsoft Learn](/dynamics365/get-started/availability).

### <a name="stream"></a>Stream
Puede encontrar esta información en la opción "?" en la interfaz de usuario de Stream, si la tiene en ejecución y, a continuación, haga clic en "Acerca de Microsoft Stream" y vea dónde se almacenan los datos. Si es necesario, cree un inquilino de prueba.

### <a name="viva-insights--advanced-mgr-leader"></a>Viva Insights: Avanzado, Manager, Líder
Consulte la [sección Static data location information for select workloads (Información de ubicación de datos estáticos para cargas de trabajo selectas](#static-data-location-information-for-select-workloads) ).  La región de datos para Manager/Leader y Advanced viene determinada por la _geografía predeterminada_ del _inquilino_, no por usuarios individuales.

### <a name="viva-insights--personal"></a>Viva Insights: personal
Los datos del cliente se procesan y almacenan en el buzón Exchange Online del empleado. La residencia de datos para Información personal en Viva Insights se basa en la ubicación del buzón del empleado. Para obtener más información, consulte [Información personal en Viva Insights guía de privacidad para administradores](/viva/insights/personal/overview/privacy-guide-admins?branch=main#summary-of-key-points).

### <a name="viva-learning"></a>Viva Learning
Consulte la [sección Static data location information for select workloads (Información de ubicación de datos estáticos para cargas de trabajo selectas](#static-data-location-information-for-select-workloads) ).

### <a name="whiteboard"></a>Whiteboard
Consulte Administración de [datos de Microsoft Whiteboard | Microsoft Learn](/whiteboard/manage-data-organizations).

### <a name="yammer"></a>Yammer
Consulte [Data Residency - Yammer | Microsoft Learn](/yammer/manage-security-and-compliance/data-residency).

## <a name="static-data-location-information-for-select-workloads"></a>Información de ubicación de datos estáticos para cargas de trabajo selectas

1. Macro Region Geography 1 – EMEA/Unión Europea
1. Macro Region Geography 2 - Asia Pacífico
1. Macro Region Geography 3 – Americas
1. Australia
1. Canada
1. Japón

| Country Code | Nombre del país | Viva Insights Avanzadas | Viva Learning | Planner |
| --- | --- | --- | --- | --- |
| Af | Afganistán | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ax | Islas Aland | APC<sup>2</sup>| AMER<sup>3</sup>| <sup>1</sup> EUR|
| AL | Albania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dz | Argelia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| AS | Samoa Americana | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Anuncio | Andorra | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ao | Angola | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ai | Anguila | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Aq | Antártida | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ag | Antigua y Barbuda | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ar | Argentina | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Soy | Armenia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Aw | Aruba | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Au | Australia | APC<sup>2</sup>| AUS<sup>4</sup>| AUS<sup>4</sup>|
| AT | Austria | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Az | Azerbaiyán | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bs | Bahamas | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bh | Baréin | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bd | Bangladesh | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Bb | Barbados | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Por | Belarús | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ser | Bélgica | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bz | Belice | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bj | Benín | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bm | Bermudas | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bt | Bután | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Bo | Bolivia | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bq | Bonaire | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ba | Bosnia y Herzegovina | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bw | Botsuana | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bv | Isla Bouvet | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Br | Brasil | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| E/S | Territorio Británico del Océano Índico | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Vg | Islas Vírgenes Británicas | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bn | Brunei Darussalam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| BG | Bulgaria | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bf | Burkina Faso | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bi | Burundi | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kh | Camboya | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cm | Camerún | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| CA | Canada | AMER<sup>3</sup>| AMER<sup>3</sup>| CAN<sup>5</sup>|
| VC | Cabo Verde | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ky | Islas Caimán | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Cf | República Centroafricana | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Td | Chad | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cl | Chile | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Cn | China | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cx | Isla de Navidad | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| CC | Islas Cocos | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Co | Colombia | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Km | Comoras | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cg | Congo (Brazzaville) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cd | Congo (Kinshasa) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ck | Islas Cook | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cr | Costa Rica | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| CI | Côte d'Ivoire | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| HR | Croacia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| CW | Curaçao | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Cy | Chipre | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cz | Chequia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| DK | Dinamarca | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dj | Yibuti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dm | Dominica | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Hacer | República Dominicana | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ce | Ecuador | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Eg | Egipto | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SV | El Salvador | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gq | Guinea Ecuatorial | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| EMERGENCIA | Eritrea | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| EE | Estonia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Et | Etiopía | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Fk | Islas Malvinas (Malvinas) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Fo | Islas Feroe | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Fm | Estados federados de Micronesia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Fj | Fiyi | APC<sup>2</sup>| APC<sup>2</sup>| AUS<sup>4</sup>|
| FI | Finlandia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| FR | Francia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gf | Guayana Francesa | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pf | Polinesia Francesa | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Tf | Territorios Australes Franceses | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| GA | Gabón | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gm | Gambia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ge | Georgia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| DE | Alemania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gh | Ghana | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gi | Gibraltar | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| GR | Grecia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gl | Groenlandia | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gd | Granada | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gp | Guadalupe | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gu | Guam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Gt | Guatemala | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gg | Guernsey | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gn | Guinea | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gw | Guinea-Bisáu | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gy | Guyana | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ht | Haití | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Hm | Islas Heard y McDonald | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| VA | Santa Sede (Estado de la Ciudad del Vaticano) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Hn | Honduras | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Hk | Hong Kong, SAR China | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Hu | Hungría | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Es | Islandia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| EN | India | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Id. | Indonesia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| IQ | Irak | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| IE | Irlanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mensajería instantánea | Isla de Man | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Il | Israel | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| TI | Italia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Jm | Jamaica | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Jp | Japón | APC<sup>2</sup>| APC<sup>2</sup>| JPN<sup>6</sup>|
| Je | Jersey | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Jo | Jordania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kz | Kazajistán | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ke | Kenia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ki | Kiribati | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Kp | Corea del Norte | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Kr | Corea del Sur | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Xk | Kosovo | <sup>1</sup> EUR| AMER<sup>3</sup>| <sup>1</sup> EUR|
| Kw | Kuwait | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kg | Kirguistán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| LA | Lao PDR | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Lv | Letonia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lb | Líbano | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| LS | Lesoto | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lr | Liberia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ly | Libia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Li | Liechtenstein | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lt | Lituania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lu | Luxemburgo | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mo | Macao, SAR China | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mg | Madagascar | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mw | Malaui | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mi | Malasia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mv | Maldivas | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ml | Mali | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mt | Malta | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mh | Islas Marshall | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mq | Martinica | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Sr | Mauritania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mu | Mauricio | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Yt | Mayotte | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| MX | México | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Mc | Mónaco | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Md | Moldova | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mn | Mongolia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| YO | Montenegro | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sra | Montserrat | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ma | Marruecos | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mz | Mozambique | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| MM | Myanmar | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| ND | Namibia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Nr | Nauru | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Np | Nepal | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| NL | Países Bajos | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Un | Antillas Neerlandesas | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Nc | Nueva Caledonia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Nz | Nueva Zelanda | APC<sup>2</sup>| APC<sup>2</sup>| AUS<sup>4</sup>|
| NI | Nicaragua | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| NE | Níger | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ng | Nigeria | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Nu | Niue | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Nf | Isla Norfolk | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mp | Islas Marianas del Norte | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| NO | Noruega | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Om | Omán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Pk | Pakistán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| PW | Palaos | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ps | Autoridad Nacional Palestina | APC<sup>2</sup>| <sup>1</sup> EUR| APC<sup>2</sup>|
| Pa | Panamá | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pg | Papúa-Nueva Guinea | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Py | Paraguay | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pe | Perú | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| PH | Filipinas | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Pn | Islas Pitcairn | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| PL | Polonia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Pt | Portugal | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Pr | Puerto Rico | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Qa | Qator | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mk | República de Macedonia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| RE | Reunión | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ro | Rumanía | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ru | Federación Rusa | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Rw | Ruanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sh | Santa Elena | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kn | San Cristóbal y Nieves | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Lc | Santa Lucía | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| PM | San Pedro y Miquelón | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Vc | San Vicente y Las Granadinas | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bl | San Bartolomé | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Mf | Saint-Martin (parte francesa) | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ws | Samoa | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Sm | San Marino | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| St | Santo Tomé y Príncipe | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SA | Arabia Saudí | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sn | Senegal | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| RS | Serbia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sc | Seychelles | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SL | Sierra Leona | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sg | Singapur | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Sx | Sint Maarten | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Sk | Eslovaquia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SI | Eslovenia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sb | Islas Salomón | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Así que | Somalia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Za | Sudáfrica | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gs | Islas Georgia del Sur y Sandwich del Sur | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ss | Sudán del Sur | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| ES | España | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lk | Sri Lanka | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| SR | Surinam | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Sj | Islas Svalbard y Jan Mayen | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sz | Suazilandia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SE | Suecia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ch | Suiza | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tw | Taiwán, República de China | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Tj | Tayikistán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| TH | Tailandia | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Tl | Timor-Leste | APC<sup>2</sup>| <sup>1</sup> EUR| APC<sup>2</sup>|
| Tg | Togo | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| TK | Tokelau | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Para | Tonga | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| TT | Trinidad y Tobago | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| TN | Túnez | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tr | Turquía | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tm | Turkmenistán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Tc | Islas Turcas y Caicos | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Tv | Tuvalu | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ug | Uganda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ua | Ucrania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ae | Emiratos Árabes Unidos | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gb | Reino Unido | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tz | República Unida de Tanzania | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| EE. UU. | Estados Unidos de América | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Uy | Uruguay | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Mensajería unificada | Islas Ultramarinas Menores de los Estados Unidos | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Uz | Uzbekistán | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Vu | Vanuatu | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| VE | Venezuela (República Bolivariana) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Vn | Vietnam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| VI | Islas Vírgenes (Estados Unidos) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Wf | Wallis y Futuna | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| EH | Sáhara Occidental | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Vosotros | Yemen | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Zm | Zambia | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Zw | Zimbabue | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
