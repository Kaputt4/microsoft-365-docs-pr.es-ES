---
title: Requisitos clave de infraestructura antes de inscribirse en el servicio Microsoft Defender Experts for Hunting
ms.reviewer: ''
description: En esta sección se describen los requisitos clave de infraestructura que debe cumplir e información importante sobre el acceso y el cumplimiento de los datos.
keywords: servicio de búsqueda de amenazas administrada, búsqueda de amenazas administrada, servicio de detección y respuesta administrada (MDR), MTE, Expertos en amenazas de Microsoft, MTE-TAN, notificación de expertos de defender, notificación de ataque dirigido, expertos de Microsoft Defender para la búsqueda, búsqueda y análisis de amenazas.
search.product: Windows 10
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 51e882c879f9365fbdc5b4a70d2ade106d061d51
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276228"
---
# <a name="before-you-begin-using-defender-experts-for-hunting"></a>Antes de empezar a usar Expertos de Defender para la búsqueda

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En este documento se describen los requisitos clave de infraestructura que debe cumplir e información importante sobre el acceso a datos y el cumplimiento que debe conocer antes de inscribirse en el servicio Expertos de Microsoft Defender para la búsqueda. Microsoft entiende que los clientes que usan nuestros servicios administrados nos confían su recurso más valioso, sus datos.

## <a name="check-if-your-environment-meets-licensing-and-access-prerequisites"></a>Compruebe si el entorno cumple los requisitos previos de licencia y acceso.

Expertos de Microsoft Defender para la búsqueda es un servicio independiente de los productos de Defender existentes. Antes de inscribirse en este servicio, asegúrese de que tiene la licencia y el acceso necesarios. 

### <a name="eligibility-and-licensing"></a>Elegibilidad y licencias

A los clientes de Defender Experts for Hunting se les asignarán dos créditos de Expertos a petición el primero de cada mes, que se pueden usar para enviar preguntas. Los créditos sin usar expiran 90 días a partir de la fecha de asignación o al final del período de suscripción, lo que sea más corto.

Para obtener más información sobre los términos de licencia comercial de Microsoft, visite [esta página](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA).

### <a name="access-requirements"></a>Requisitos de acceso

Cualquier persona de su organización puede completar el formulario de interés del cliente para el servicio Expertos de Microsoft Defender para la búsqueda; sin embargo, debe trabajar con su ejecutivo comercial para realizar transacciones con la SKU. Es posible que necesite determinados roles y permisos para acceder completamente a las funcionalidades del servicio. Consulte [Roles personalizados en el control de acceso basado en rol para obtener Microsoft 365 Defender](custom-roles.md) para obtener más información.

## <a name="understand-the-services-availability-and-data-access-requirements"></a>Descripción de los requisitos de disponibilidad y acceso a datos del servicio

Expertos de Defender para la búsqueda es un servicio de búsqueda de amenazas administrado que busca amenazas de forma proactiva en los puntos de conexión, el correo electrónico, la identidad y las aplicaciones en la nube. Para llevar a cabo la búsqueda en su nombre, los expertos de Microsoft necesitan acceso a sus Microsoft 365 Defender datos de búsqueda avanzados. Inscribirse en este servicio significa que concede permiso a expertos de Microsoft para acceder a dichos datos.

En las secciones siguientes se enumera información adicional sobre el uso, el cumplimiento y la disponibilidad de los datos del servicio. Para obtener más información sobre el compromiso de Microsoft en la valoración y protección de los datos, visite el [Centro de confianza](https://aka.ms/trustcenter-dex4hunting) > desplácese hacia abajo hasta **Productos y servicios** >  adicionales **de Servicios de seguridad** > [**administrados Experto en Microsoft Defender para la búsqueda**](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE51fRH).

### <a name="data-collection-usage-and-retention"></a>Recopilación, uso y retención de datos

Todos los datos usados para la búsqueda de servicios de Defender existentes seguirán residiendo en la ubicación de almacenamiento del servicio Microsoft 365 Defender original del cliente. [Más información](../../enterprise/o365-data-locations.md)

Los expertos de Defender para la búsqueda de datos operativos, como vales de casos y notas de analistas, se generan y almacenan en un centro de datos de Microsoft en la región de EE. UU. durante la duración del servicio, independientemente de la ubicación de almacenamiento del servicio Microsoft 365 Defender. Los datos generados para el panel de informes se almacenan en la ubicación de almacenamiento del servicio Microsoft 365 Defender del cliente. Los datos de informes y los datos operativos se conservarán durante un período de gracia de no menos de 90 días después de que un cliente deje el servicio.

Los expertos de Microsoft buscan [registros de búsqueda avanzados](../../security/defender/advanced-hunting-schema-tables.md) en Microsoft 365 Defender tablas de búsqueda avanzadas. Los datos de estas tablas dependen del conjunto de servicios de Defender para los que está habilitado el cliente (por ejemplo, Pertahanan Microsoft untuk Titik Akhir, Pertahanan Microsoft untuk Office 365, Pertahanan Microsoft untuk Identitas, Microsoft Defender for Cloud Apps y Azure Active Directory). Los expertos también usan un gran conjunto de datos internos de inteligencia sobre amenazas para informar sobre su búsqueda y automatización.

### <a name="security-and-compliance"></a>Seguridad y cumplimiento

Al comprar e incorporarse a Expertos de Defender para la búsqueda, se concede permiso a los expertos de Microsoft para acceder a los datos de búsqueda avanzados.

Este servicio se ha desarrollado en consonancia con los estándares de seguridad y privacidad existentes y está trabajando para varias certificaciones, como ISO 27001 e ISO 27018.

### <a name="availability"></a>Disponibilidad

Este servicio está disponible en todo el mundo para los clientes en nuestras nubes públicas comerciales. Actualmente no está disponible para los clientes en nubes gubernamentales y soberanas.

### <a name="languages"></a>Idiomas

Este servicio solo se ofrece actualmente en inglés.

## <a name="apply-for-microsoft-defender-experts-for-hunting-service"></a>Solicitud para expertos de Microsoft Defender para el servicio de búsqueda

Si aún no lo ha hecho, puede completar el formulario de interés del cliente para expertos de Defender para la búsqueda:

1. Complete el [formulario de interés del cliente](https://aka.ms/DEX4HuntingCustomerInterestForm). Cualquier persona de su empresa puede solicitarlo, pero si se acepta, debe trabajar con su ejecutivo comercial para realizar transacciones con la SKU.
2. Escriba el nombre, el nombre de la empresa y el identificador de correo electrónico de la empresa.
3. Seleccione **Enviar**. Alguien de nuestro equipo de ventas se pondrá en contacto con nosotros en un plazo de cinco días laborables.


### <a name="next-step"></a>Paso siguiente

- [Empezar a usar expertos de Defender para la búsqueda](onboarding-defender-experts-for-hunting.md)
