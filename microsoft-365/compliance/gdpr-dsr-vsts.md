---
title: Solicitudes del interesado de Azure DevOps para el RGPD y CCPA
keywords: Visual Studio Team Services, VSTS, documentación de Azure DevOps, privacidad, RGPD, CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a803dfd8d917ff0c2753b5ee87d9d619bc2f6222
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596477"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes del interesado de Azure DevOps Services para el RGPD y CCPA

El [Reglamento general de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas, que se denominan *interesados* en el reglamento, para administrar los datos personales recopilados por un *responsable de los datos*. Un responsable de los datos, o simplemente *responsable* es una empresa u otro tipo de agencia u organización. Los datos personales se definen de forma amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos en sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro poseedor de los datos. Las solicitudes formales realizadas por un interesado a un poseedor de los datos para realizar una acción en sus datos personales se denominan *solicitudes de interesado*.

De forma similar, la Ley de Privacidad de Consumidores de California (CCPA) establece derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los sancionados por el RGDP, como el derecho a eliminar, obtener acceso y recibir (portabilidad) sus datos personales.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Para obtener información general sobre el RGPD, consulte la [sección RGPD del Portal de confianza de servicios](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

En esta guía, se describe cómo usar las herramientas de Microsoft para exportar o eliminar datos personales recopilados durante una sesión autenticada (en la que se inició sesión) de Azure DevOps Services (antes conocido como Visual Studio Team Services).

## <a name="additional-privacy-information"></a>Información de privacidad adicional

Los artículos de la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement), los [Términos de servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) y los [Compromisos de RGPD de Microsoft](/legal/gdpr) describen los procedimientos de procesamiento de datos.

## <a name="personal-data-we-collect"></a>Los datos personales que recopilamos

Microsoft recopila datos para que los usuarios puedan operar y ayudar a mejorar los servicios de Azure DevOps. Azure DevOps Services recopila dos categorías de datos: los datos de clientes y los registros generados por el sistema. Los datos de los clientes incluyen datos de transacciones e interacciones que pueden identificar al usuario y que Azure DevOps necesita para su funcionamiento. Los registros generados por el sistema incluyen datos de uso del servicio que se agregan para cada área de producto y característica.

## <a name="delete-azure-devops-data"></a>Eliminar datos de Azure DevOps

El primer paso para eliminar los datos de cliente de Azure DevOps Services y hacer anónimos los datos personales que puedan identificarle en los registros generados por el sistema es cerrar su cuenta de identidad de Azure Active Directory (AAD) o su cuenta de Microsoft (MSA). Azure DevOps Services se basa en un sistema de registro con estrictos requisitos de integridad, trazabilidad y auditoría. Las obligaciones existentes afectan a nuestras obligaciones de eliminación y conservación relativas al RGPD. El cierre de la cuenta de identidad no altera, quita ni cambia los artefactos y registros asociados a la identidad individual en la organización de Azure DevOps. Le garantizamos que cuando se elimina toda una organización de Azure DevOps, todos los datos asociados que puedan identificar a una persona y los registros generados por el sistema que se encuentren en la organización se eliminan de nuestro sistema (después del período de 30 días obligatorio de eliminación temporal de Azure DevOps).

## <a name="export-azure-devops-data"></a>Exportar datos de Azure DevOps

Los responsables pueden usar dos métodos para exportar los datos de clientes y los registros generados por el sistema recopilados de los interesados, según el proveedor de identidades (MSA o AAD) que se usó para iniciar sesión en el servicio de Azure DevOps.

- Los usuarios que se autentiquen con una cuenta respaldada por un inquilino de Azure (como, por ejemplo, una cuenta de AAD o MSA asociada a una suscripción a Azure) pueden seguir las instrucciones de [Solicitudes de interesados de Azure para el RGPD](gdpr-dsr-azure.md).

- Los usuarios que se autentiquen con una identidad de MSA pueden usar este [sitio de Privacy Request](https://www.microsoft.com/concern/privacyrequest-msa) para ver los datos de actividad vinculados a su identidad de MSA en varios servicios de Microsoft. En este escenario, el usuario es un responsable de sus datos personales.

## <a name="export-or-delete-issues"></a>Exportar o eliminar problemas

Para identidades de AAD, si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción** > **Otras solicitudes de seguridad y cumplimiento** > **Solicitudes de RGPD y la hoja de privacidad**.

Para las identidades de MSA, si tiene problemas al exportar datos desde el sitio de Solicitud de privacidad, inicie sesión en el [sitio de Privacy Request](https://www.microsoft.com/concern/privacyrequest-msa) y envíe una solicitud para obtener ayuda del equipo de Microsoft Privacy mediante el formulario de solicitud web.

## <a name="learn-more"></a>Más información

Microsoft se compromete a garantizar que sus datos de Azure DevOps Services sigan siendo seguros y privados, sin ninguna excepción. Visite las notas del producto [Información general sobre la protección de datos de Azure DevOps Services](/vsts/articles/team-services-security-whitepaper?view=vsts) para obtener más información sobre cómo protegemos sus datos de Azure DevOps Services.

## <a name="see-also"></a>Vea también

- [Compromisos de Microsoft en virtud del RGPD con los clientes de nuestros productos de software empresarial generalmente disponibles](https://docs.microsoft.com/legal/gdpr)
- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Portal de confianza del servicio](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy)
- [Centro de respuesta de privacidad de Microsoft](https://aka.ms/userprivacysite)
- [Solicitudes de interesados de Azure para el RGPD](gdpr-dsr-azure.md)