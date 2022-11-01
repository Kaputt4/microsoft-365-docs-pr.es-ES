---
title: Información general y definiciones
description: Más información sobre Data Residency información general y definiciones de características
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
ms.openlocfilehash: c73910350027ff90fa54208e4e11c53b04538969
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806319"
---
# <a name="overview-and-definitions"></a>Información general y definiciones

## <a name="definitions"></a>Definiciones

Para proporcionar claridad a las descripciones siguientes sobre la funcionalidad y el comportamiento de residencia de datos, es necesario tener términos y definiciones claros para comprender mejor las funcionalidades que Proporciona Microsoft en esta área.

**Tabla 1: Definiciones y términos**

| **Término** | **Definición** |
|:-----|:-----|
|Geografía de la región de macro  <br/> |Macro Region Geography 1 – EMEA, Macro Region Geography – Asia Pacific, Macro Region Geography - Americas  <br/> |
|Geografía de la región de macro 1 - EMEA  <br/> |Centros de datos en Austria, Finlandia, Francia, Irlanda, Países Bajos, Suecia  <br/> |
|Macro Region Geography 2 - Asia Pacífico  <br/> |Centros de datos en Hong Kong, Japón, Malasia, Singapur, Corea del Sur  <br/> |
|Macro Region Geography 3 - Americas  <br/> |Centros de datos en Brasil, Chile, Estados Unidos  <br/> |
|Geografía de la región local  <br/> |Australia, Brasil, Canadá, Francia, Alemania, India, Japón, Qatar, Corea del Sur, Noruega, Sudáfrica, Suecia, Suiza, Emiratos Árabes Unidos, Reino Unido  <br/> |
|Geografía de la región local expandida  <br/> |Polonia, Italia, Indonesia, Israel, España, México, Malasia, Austria, Chile, Nueva Zelanda, Dinamarca, Grecia, Taiwán  <br/> |
|Geografía  <br/> |_Geografía de la región local, geografía de la región local expandida_ o _geografía de la región de macro_  <br/> |
|Geografía satélite  <br/> |Si un cliente se suscribe al servicio Multi Geo, puede hacer que los datos de clientes de usuario definidos se almacenen en otras zonas geográficas fuera de la _geografía aprovisionada principal_ del _inquilino_.  <br/> |
|Aad  <br/> |Azure Active Directory  <br/> |
|Tenant  <br/> |Un _inquilino_ representa una organización en Azure Active Directory. Es una instancia reservada del servicio de Azure AD que una organización recibe y posee cuando se registra en un servicio en la nube de Microsoft, como Azure o Microsoft 365. Cada _inquilino de_ Azure AD es distinto e independiente de otros _inquilinos de_ Azure AD.  <br/> |
|Geografía predeterminada  <br/> |Cuando se crea un _inquilino de AAD_ , el cliente proporciona un país durante el proceso de registro.  Este país determinará la geografía predeterminada para todos los servicios de Microsoft 365.  En algunos casos, no todos los servicios pueden aprovisionarse en esta única _geografía predeterminada_. Consulte Asignación de _aprovisionamiento de servicios de Microsoft 365_ a continuación para obtener una descripción.  <br/> |
|Asignación de aprovisionamiento de servicios de Microsoft 365  <br/> |Todos los servicios de Microsoft 365 usarán la _geografía predeterminada_ para determinar dónde se aprovisionarán y almacenarán los datos especificados _de un inquilino_ determinado.  <br/> |
|Asignación de país de aprovisionamiento de servicios de Microsoft 365  <br/> |Consulte mapas de [datos](https://aka.ms/datamaps) para obtener información sobre dónde un servicio determinado aprovisionará los datos de cliente especificados, en función de la _geografía predeterminada del inquilino._  <br/> |
|Geografía aprovisionada principal  <br/> |Un servicio de Microsoft 365 determinado usará la _geografía predeterminada del inquilino_ combinada con la _asignación de país de aprovisionamiento de servicios de Microsoft 365_ para determinar en qué _geografía_ aprovisionar los datos del cliente.   <br/> |
|Ubicación de datos del centro de Administración de Microsoft 365  <br/> |Para ver la _geografía aprovisionada principal_ para Exchange Online, SharePoint Online y Microsoft Teams hacen referencia al Centro de Office 365 Admin en Configuración; Configuración de la organización; Perfil de la organización; Tarjeta de ubicación de datos.  <br/> |
|Funcionalidades multigeográficas de Microsoft 365  <br/> |Las funcionalidades multigeográficas de Microsoft 365 permiten a un único _inquilino_ almacenar datos de clientes en reposo en varias zonas geográficas, en lugar de limitarse a la geografía _aprovisionada principal_ única. Consulte la descripción multigeográfica para obtener más detalles.  <br/> |
|Ubicación de datos preferida (PDL)  <br/> |Se usa para _inquilinos_ con una suscripción multigeográfica.  Propiedad establecida por el administrador que indica dónde se deben almacenar los datos del usuario o recurso compartido en reposo.  Consulte la descripción multigeográfica para obtener más detalles.  <br/> |
|Data Residency avanzada (ADR)  <br/> |Un nuevo servicio complementario de Microsoft 365 que garantiza la residencia de datos del cliente para un conjunto definido de servicios. Consulte la sección 3.  <br/> |
|Términos del producto de privacidad y seguridad  <br/> |Los términos de privacidad y seguridad de los servicios de Microsoft 365 proporcionan algunos compromisos relacionados con la ubicación de datos del cliente.  El documento se puede encontrar <a href="https://www.microsoft.com/licensing/terms/en-US/product/PrivacyandSecurityTerms/EAEAS" target="_blank">aquí</a>. El extracto de la sección pertinente (el 1 de noviembre de 2022) es:<br>**Office 365 Services.** Si el cliente aprovisiona su _inquilino_ en Australia, Brasil, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Noruega, Qatar, Sudáfrica, Corea del Sur, Suecia, Suiza, el Reino Unido, los Emiratos Árabes Unidos o el Estados Unidos, Microsoft almacenará los siguientes datos de cliente en reposo solo dentro de esa geoárea: (1) Exchange Online  contenido de buzón (cuerpo del correo electrónico, entradas de calendario y contenido de datos adjuntos de correo electrónico), (2) contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio, (3) archivos cargados en OneDrive para la Empresa y (4) mensajes de chat de Microsoft Teams (incluidos mensajes privados, mensajes de canal, mensajes de reunión e imágenes usados en chats) y para clientes que usan Microsoft Stream  (en SharePoint), grabaciones de reuniones.
|Cargas de trabajo  <br/> |A menudo se usa para hacer referencia a un servicio de Microsoft 365 como, entre otros, Exchange Online, SharePoint Online, Microsoft Teams, etc.|

## <a name="overview-of-data-residency"></a>Introducción a Data Residency

Los servicios en la nube de Microsoft 365 se ejecutan en nuestros centros de datos de todo el mundo y proporcionan servicios a clientes de todo el mundo.  Los datos del cliente se pueden almacenar en varios centros de datos.  La residencia de datos hace referencia a la ubicación geográfica donde se almacenan los datos del cliente en reposo. La residencia de datos es importante para el gobierno, el sector público, la educación y las entidades comerciales reguladas para ayudar a garantizar la protección de la información personal o confidencial.  En muchos países, se espera que los clientes cumplan con las leyes, regulaciones o estándares del sector que rigen explícitamente la ubicación del almacenamiento de datos.

Microsoft toma decisiones sobre dónde almacenar de forma persistente los datos de los clientes en función de dos factores:

1. Geografía _predeterminada_ del _inquilino_
1. _Zonas geográficas_ disponibles para un servicio determinado

### <a name="_default-geography_-of-the-aad-_tenant_"></a>_Geografía predeterminada_ del _inquilino_ de AAD

Cuando un cliente crea un nuevo _inquilino_ de AAD, el cliente entrará en un país durante el proceso de creación.  Este país es lo que define la _geografía predeterminada_ para el _inquilino_.  Hay varias rutas de acceso para crear _inquilinos_.  Se pueden crear a través de formularios de AAD, se pueden crear al probar nuevos servicios de Microsoft 365 (pruebas), etc.  Una vez creado un _inquilino_ , no se puede cambiar la _geografía predeterminada_ .

### <a name="available-geographies-for-a-given-service"></a>Zonas geográficas disponibles para un servicio determinado

Los servicios de Microsoft 365 no se implementan en todos los centros de datos de Microsoft globalmente.  Los servicios más grandes, como Exchange Online, SharePoint Online y Microsoft Teams se implementan universalmente en todas las _zonas geográficas_.   Otros servicios toman decisiones sobre dónde implementar sus servicios en función del número de clientes, afiliaciones regionales y arquitecturas de software.  Cuando un cliente usa por primera vez un servicio en esta categoría, la lógica de aprovisionamiento usará la _geografía predeterminada_ y _las zonas geográficas admitidas_ para determinar dónde aprovisionar un cliente determinado.

Con el tiempo, un servicio determinado puede implementar su software en _zonas geográficas_ adicionales, por lo que las ubicaciones de aprovisionamiento de nuevos clientes pueden cambiar con el tiempo, lo que no hace necesariamente que los datos de los clientes se muevan a una nueva _geografía_.

Para comprender dónde se almacenan los datos de un servicio determinado, la herramienta principal para comprender esto se encuentra en el Centro de Administración de _inquilinos_.  Como administrador de _inquilinos_, puede encontrar la ubicación de datos real; para ello, vaya a configuración de Administración->-configuración de la organización >->ubicación de datos del perfil de la organización >.  Actualmente, la ubicación de datos está disponible para Exchange Online, SharePoint Online y Microsoft Teams.  Además de este recurso, consulte la [página Mapas de datos](o365-data-locations.md).

Por ejemplo:

**Ejemplo 1:** Para un _inquilino_ con el país de registro como "Francia" que tiene una nueva suscripción que incluye Exchange Online, SharePoint Online y Microsoft Teams, los datos del cliente de esos servicios se aprovisionarán en la geografía de la _región local_ francesa. ¿Por qué?  Dado que esos servicios se implementan en los centros de datos franceses y el _inquilino_ tiene un país de registro en Francia.

**Ejemplo 2:**  Para un _inquilino_ con el país de registro como "Bélgica" que tiene una nueva suscripción que incluye Exchange Online, SharePoint Online y Microsoft Teams, los datos del cliente de esos servicios se aprovisionarán en la _región de macro Geography 1 – EMEA_.  ¿Por qué?  Dado que no hay centros de datos de Microsoft 365 en Bélgica y la geografía más cercana es _Macro Region Geography 1 - EMEA_.

**Ejemplo 3:** En el _caso_ de un inquilino con el país de registro como "Japón" que tiene una nueva suscripción que incluye Microsoft Forms, los datos del cliente de Forms se aprovisionarán en la _región macro Geography 3 - Americas_.  ¿Por qué?  Dado que Los formularios solo se implementan en _la región macro Geography 3 - Americas_ y _Macro Region Geography 1 – EMEA_ (solo _inquilinos de_ la UE).

**Ejemplo 4a:** En el _caso_ de un inquilino con el país de registro como "Suecia" que tiene una nueva suscripción que incluye Microsoft Yammer, los datos del cliente de Yammer se aprovisionarán en la _macro región Geography 1 - EMEA_.  ¿Por qué?  Dado que Yammer se implementa en _la región de macro Geography 1, emea_ y los _inquilinos suecos_ se sirven mejor fuera de esa _geografía_.

**Ejemplo 4b:** Para un _inquilino_ con el país de registro como "Suecia" que tiene una suscripción que incluye Microsoft Yammer desde antes de que Yammer se implementara en _Macro Regional Geography 1 - EMEA_, los datos del cliente de Yammer se ubicarán en _Macro Region Geography 3 - Americas_.  ¿Por qué?  Porque, en ese momento, Yammer solo tenía una implementación única para todos los clientes en ese momento en _macro region geography 3 - Americas_.

### <a name="migrationsmoves"></a>Migraciones o movimientos

Una vez que un servicio de Microsoft 365 aprovisiona un _inquilino_ en una _geografía_ determinada, hay cinco maneras de mover estos datos a otra _geografía_:

1. El servicio Microsoft 365 decide mover los datos a una nueva _geografía_ por motivos de operaciones de servicio, si no hay ninguna otra directiva en vigor para evitar el traslado.
1. En el caso _de las zonas geográficas locales_ que tienen centros de datos de Microsoft y para _los inquilinos_ que tienen el mismo país, hay opciones para migrar datos de las _zonas geográficas regionales_ a las _zonas geográficas locales_.  Esta opción normalmente solo está disponible durante 6 meses después de que se haya establecido una _geografía de región local_ .
1. Si un _inquilino_ se suscribe al servicio _Multi-Geo_, los datos de usuario de _inquilinos_ para Exchange Online, SharePoint Online y Microsoft Teams se pueden asignar a _zonas geográficas satélite_.
1. Si un _inquilino_ tiene un país de registro como geografía de _región local_ o _geografía de región local expandida_ y tiene una suscripción al complemento de servicio _advanced Data Residency_, los datos del _inquilino_ de los servicios incluidos se migrarán de la _geografía regional_ a la _geografía de la región local_ pertinente.
1. En ocasiones, Microsoft vuelve a abrir la opción migración desde _la geografía regional_ a las _zonas geográficas locales pertinentes_ o a _las zonas geográficas locales expandidas_.

### <a name="durable-commitments-on-data-location"></a>Compromisos duraderos en la ubicación de datos

Hay tres métodos para asegurarse de que la ubicación de datos del _inquilino_ de un servicio determinado no cambia.

1. Términos del producto: Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams aprovisionados en cualquier _región geográfica de la región local_, o la Unión Europea o la Estados Unidos tienen un compromiso de residencia de datos del cliente expresado en los [Términos del producto](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all).  Para obtener más información, consulte la [página Data Residency términos del producto](m365-dr-product-terms-dr.md).
1. _Suscripción multigeográfica_: permite a los clientes asignar la ubicación de datos para Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams a cualquier _ubicación geográfica_ compatible.  Para obtener más información, consulte [Data Residency multigeográfica](microsoft-365-multi-geo.md).
1. _La suscripción Data Residency avanzada_ garantiza la residencia de datos para un conjunto expandido de servicios de Microsoft 365 en cualquier geografía de _región local_ o _geografía de región local expandida_.  Para obtener más información, consulte la [página Advanced Data Residency (Avanzadas Data Residency).](advanced-data-residency.md)

**Tabla 2: Disponible Data Residency por carga de trabajo**

|**Nombre del servicio**|**Términos del producto**|**Multi-Geo**|**Adr**|
|:-----|:-----|:-----|:-----|
|Exchange Online <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>3</sup>  <br/> |
| SharePoint Online/OneDrive para la Empresa <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>2</sup>  <br/> |
| Microsoft Teams <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>2</sup>  <br/> |
| Microsoft Defender para Office P1 <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Office para la Web <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Viva Connections <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Temas Viva <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Microsoft Purview <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |

1. Solo disponible para los países _de geografía de la región local_, la Unión Europea y el Estados Unidos.
1. Disponible en _Geografía de región local_, _Geografía de región local expandida_ y _Países o regiones de geografía regional_
1. Solo está disponible para los países _de geografía de la región local_ y geografía _de la región local expandida_ .

>[!NOTE]
>Consulte la [sección Workload Data Residency Capabilities (Funcionalidades de Data Residency](m365-dr-workload-exo.md) de carga de trabajo) para obtener más información sobre estos temas.

**Tabla 3: Disponible Data Residency por país**

| País    | Exchange Online  | SharePoint Online  | Teams  | MDO P1  | Office para la web  | Viva Connections  | Temas Viva  |  Ámbito  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Australia  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Brasil  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Canada  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Unión Europea  | P-M  | P-M  | P-M  | -  | -  | -  | -  | -  |
| Francia  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Alemania  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| India  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Japón  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Qatar  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Corea del Sur  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Noruega  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Sudáfrica  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Suecia  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Suiza  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Emiratos Árabes Unidos  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Reino Unido  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Estados Unidos  | P-M  | P-M  | P-M  | -  | -  | -  | -  | -  |

P: Términos del producto Data Residency<br>
M: Data Residency multigeográfica<br>
R: Data Residency avanzadas

### <a name="countryregion-specific-data-center-city-locations"></a>Ubicaciones de ciudades de centros de datos específicos por país o región

Las siguientes zonas geográficas regionales pueden almacenar datos en reposo.

**Tabla 4: Zonas geográficas regionales**

|**Zonas geográficas regionales** |**Ubicaciones en las que se almacenan los datos de los clientes**  |
|---------|---------|
|Macro Region Geography 1 - EMEA (Europa, Oriente Medio y África) |  Austria, Finlandia, Francia, Irlanda, Países Bajos, Suecia  |
|Macro Region Geography 2 - Asia Pacífico |  RAE de Hong Kong, Japón, Malasia, Singapur, Corea del Sur  |
|Macro Region Geography 3 - Americas | Brasil, Chile, Estados Unidos  |

**Tabla 5: Zonas geográficas locales actuales y ubicaciones de centros de datos específicos de la región**

|País |Ubicación del centro de datos  |
|---------|---------|
|Australia   |Sídney, Melbourne   |
|Brasil   |Rio, Campinas   |
|Canadá      |Quebec City, Toronto    |
|Unión Europea      |Austria (Viena), Finlandia (Helsinki), Francia (París, Marsella), Irlanda (Dublín), Países Bajos (Ámsterdam), Suecia (Gvleä, Sandviken, Staffanstorp)     |
|Francia      |Paris, Marsella     |
|Alemania     |Frankfurt, Berlín       |
|India   |Chennai, Mumbai, Pune        |
|Japón     |Osaka, Tokio      |
|Corea del Sur   |Busan, Seúl        |
|Noruega     |Oslo, Stavanger       |
|Qatar     |Doha          |
|Sudáfrica       |Ciudad del Cabo, Johannesburgo        |
|Suecia     |Gävle, Sandviken, Staffanstorp      |
|Suiza           |Ginebra, Zúrich     |
|Emiratos Árabes Unidos    |Dubái, Abu Dabi        |
|Reino Unido       |Durham, Londres, Cardiff      |
|Estados Unidos    |Boydton, Cheyenne, Chicago, Des Moines, Quincy, San Antonio, Santa Clara, San Jose       |

### <a name="faq"></a>Preguntas más frecuentes

#### <a name="how-does-microsoft-define-data"></a>¿Cómo define Microsoft los datos?
<details><summary>Haga clic para expandir</summary>

Revise nuestras [definiciones de los distintos tipos de datos de clientes](https://go.microsoft.com/fwlink/p/?linkid=864390) en el Centro de confianza de Microsoft. En los [Términos de seguridad de privacidad &](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all), Microsoft realiza compromisos contractuales con respecto a los datos del cliente o los datos del _inquilino_ y del usuario. Nos referimos a los datos del cliente como los datos del cliente que se confirman para almacenarse en reposo solo dentro de la región _de un inquilino_ de acuerdo con los [Términos de privacidad & seguridad](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all).

</details>

#### <a name="where-are-the-exact-addresses-of-the-data-centers"></a>¿Dónde están las direcciones exactas de los centros de datos?

<details><summary>Haga clic para expandir</summary>

Microsoft no revela las direcciones exactas de los centros de datos. Establecimos esta directiva para proteger nuestros centros de datos. Sin embargo, enumeramos las ubicaciones de las ciudades. Consulte la tabla 5 en Ubicaciones de ciudad del [centro de datos específicas del país o región](m365-dr-overview.md#countryregion-specific-data-center-city-locations) en la página Información general y definiciones para obtener más información.

</details>

#### <a name="does-the-location-of-your-customer-data-have-a-direct-impact-on-your-end-users-experience"></a>¿Afecta la ubicación de los datos de los clientes a la experiencia de los usuarios finales?
<details><summary>Haga clic para expandir</summary>

El rendimiento de Microsoft 365 no es simplemente proporcional a la distancia de un usuario de _inquilino_ a las ubicaciones del centro de datos. Las inversiones continuas de Microsoft en su red en la nube global, infraestructura de su nube global, y la arquitectura de los servicios de Microsoft 365 proporcionan a los usuarios una experiencia consistente y única, donde sea que estén almacenados los datos en reposo de los clientes. Si los usuarios están experimentando problemas de rendimiento, debe analizarlos en profundidad. Microsoft ha publicado instrucciones dirigidas hacia los clientes de Microsoft 365 para planear y optimizar el rendimiento de los usuarios finales en el [sitio web de soporte técnico de Office](network-planning-and-performance.md).

</details>

#### <a name="how-does-microsoft-help-me-comply-with-my-national-regional-and-industry-specific-regulations"></a>¿Cómo me ayuda Microsoft a cumplir los reglamentos nacionales, regionales y específicos del sector?
<details><summary>Haga clic para expandir</summary>

Para ayudar a un _inquilino_ a cumplir con los requisitos nacionales, regionales y específicos del sector que rigen la recopilación y el uso de los datos de los usuarios, Microsoft 365 ofrece el conjunto más completo de ofertas de cumplimiento de cualquier proveedor global de productividad en la nube. Revise [nuestras ofertas de cumplimiento](/compliance/regulatory/offering-home) y más detalles en la sección [Microsoft Purview](https://go.microsoft.com/fwlink/p/?linkid=862317) del Centro de confianza de Microsoft. Además, algunos planes de Microsoft 365 ofrecen soluciones de cumplimiento adicionales para ayudar a un _inquilino_ a administrar sus datos, cumplir con los requisitos legales y normativos y supervisar las acciones realizadas en sus datos.

</details>

#### <a name="who-can-access-your-data-and-according-to-what-rules"></a>¿Quién puede obtener acceso a los datos y en función de qué reglas?
<details><summary>Haga clic para expandir</summary>

 Microsoft implementa medidas sólidas para ayudar a proteger los datos de los clientes _de un inquilino_ frente al acceso inadecuado o el uso por parte de personas no autorizadas. Esto incluye la restricción del acceso del personal de Microsoft y de los subcontratistas, y la definición cuidadosa de los requisitos para responder a las solicitudes de administración pública para datos de clientes. Sin embargo, puede acceder a los datos _del cliente del inquilino_ en cualquier momento y por cualquier motivo. Puede obtener más información en el [centro de confianza de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=864392).

</details>

#### <a name="does-microsoft-access-your-data"></a>¿Microsoft accede a sus datos?
<details><summary>Haga clic para expandir</summary>

Microsoft automatiza la mayoría de las operaciones de Microsoft 365 y, a la par, limita de forma intencionada su propio acceso a los datos de los clientes. Esto nos ayuda a administrar Microsoft 365 a gran escala y a abordar los riesgos de las amenazas internas a los datos de los clientes. De manera predeterminada, los ingenieros de Microsoft no cuentan con privilegios administrativos permanentes ni acceso permanente a los datos de los clientes en Microsoft 365. Un ingeniero de Microsoft puede tener un acceso limitado y registrado a los datos de los clientes durante un período de tiempo limitado, pero solo cuando sea necesario para las operaciones de servicio normal y solo cuando lo apruebe un miembro de la administración ejecutiva de Microsoft (y, en el caso de los clientes que tengan una licencia para la característica de Caja de seguridad del cliente, el cliente).

</details>

#### <a name="how-does-microsoft-secure-your-data"></a>¿Cómo protege Microsoft los datos?
<details><summary>Haga clic para expandir</summary>

Microsoft tiene directivas, controles y sistemas sólidos integrados en Microsoft 365 para ayudarle a proteger su información. Para obtener más información, consulte la [sección Seguridad de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=864393) en el centro de confianza de Microsoft.

</details>

#### <a name="does-microsoft-365-encrypt-your-data"></a>¿Microsoft 365 cifra los datos?
<details><summary>Haga clic para expandir</summary>

Microsoft 365 usa tecnologías del lado del servidor que cifran los datos en reposo y en tránsito de los clientes. En el caso de los datos en reposo de los clientes, Microsoft 365 usa el cifrado de disco y el cifrado por archivo. En el caso de los datos en tránsito de los clientes, Microsoft 365 usa varias tecnologías de cifrado para las comunicaciones entre centros de datos, y entre clientes y servidores, como la Seguridad de la capa de transporte (TLS) y el protocolo de seguridad de Internet (IPsec). Microsoft 365 también incluye características de cifrado administradas por el cliente.

</details>

#### <a name="where-can-i-find-data-residency-information-for-microsoft-azure"></a>¿Dónde puedo encontrar información de residencia de datos para Microsoft Azure?
<details><summary>Haga clic para expandir</summary>

Consulte la página [productos disponibles por región](https://go.microsoft.com/fwlink/p/?linkid=2093451) para buscar información sobre la residencia de datos de Microsoft Azure.

</details>

#### <a name="why-do-i-see-my-microsoft-365-service-requests-for-my-data-at-rest-connecting-to-servers-in-countries-outside-of-my-region"></a>¿Por qué veo que mis solicitudes de servicio de Microsoft 365 para mis datos en reposo se conectan a servidores de países fuera de mi región?
<details><summary>Haga clic para expandir</summary>

En ocasiones, los servidores de una región diferente a la ubicación donde se almacenan los datos _de cliente de un inquilino_ pueden controlar una solicitud de cliente en reposo. Esto puede ocurrir cuando las decisiones de enrutamiento de red eligen un servidor diferente para el procesamiento de solicitudes, pero en estos casos, los datos _del cliente del inquilino_ no se mueven a una nueva ubicación en reposo.

</details>
