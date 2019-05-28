---
title: Solicitudes del interesado de Azure DevOps para el RGPD
keywords: Visual Studio Team Services, VSTS, documentación de Azure DevOps, privacidad, RGPD
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 91ab1c1e23b2f4f9aab5c4327c29ac6cea52d080
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431781"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a>Solicitudes del interesado de Azure DevOps Services para el RGPD

El [Reglamento general de protección de datos (RGPD)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas, que se denominan *interesados* en el reglamento, para administrar los datos personales recopilados por un *responsable de los datos*. Un responsable de los datos, o simplemente *responsable* es una empresa u otro tipo de agencia u organización. Los datos personales se definen de forma amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos en sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro poseedor de los datos. Las solicitudes formales realizadas por un interesado a un poseedor de los datos para realizar una acción en sus datos personales se denominan *solicitudes de interesado*.

Para obtener información general sobre el RGPD, consulte la [sección RGPD del Portal de confianza de servicios](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

En esta guía, se describe cómo usar las herramientas de Microsoft para exportar o eliminar datos personales recopilados durante una sesión autenticada (en la que se inició sesión) de Azure DevOps Services (antes conocido como Visual Studio Team Services).

## <a name="additional-privacy-information"></a>Información de privacidad adicional

Los artículos de la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement), los [Términos de servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) y los [Compromisos de RGPD de Microsoft](/legal/gdpr) describen los procedimientos de procesamiento de datos.

## <a name="personal-data-we-collect"></a>Los datos personales que recopilamos

Microsoft recopila datos de los usuarios para operar y mejorar Azure DevOps Services. Azure DevOps Services recopila dos categorías de datos: datos de clientes y registros generados por el sistema. En los datos de clientes, se incluyen datos de transacciones y de interacciones de usuario identificables que Azure DevOps Services necesita para ofrecer el servicio. En los registros generados por el sistema, se incluyen datos de uso del servicio que se agregan a cada área de producto y característica.

## <a name="delete-azure-devops-data"></a>Eliminar datos de Azure DevOps

El primer paso para eliminar los datos de clientes de Azure DevOps Services asociados y anonimizar la información de identificación personal en registros generados por el sistema es cerrar su cuenta de identidad de Azure Active Directory (AAD) o su cuenta Microsoft (MSA). Azure DevOps Services se usa como un sistema de registro con integridad estricta, rastreabilidad y reglas de auditoría. Estas obligaciones existentes afectan a nuestras obligaciones de eliminación y retención de RGPD. Cerrar la cuenta de identidad no modifica, quita ni cambia los artefactos y registros asociados a la identidad individual de la organización de Azure DevOps. Nos aseguramos de que, cuando se elimine una organización de Azure DevOps completa, se borre del sistema toda la información de identificación personal asociada, así como los registros generados por el sistema que se encuentren en esa organización (después del período necesario de eliminación temporal de 30 días de la organización de Azure DevOps).

## <a name="export-azure-devops-data"></a>Exportar datos de Azure DevOps

Los responsables pueden usar dos métodos para exportar los datos de clientes y los registros generados por el sistema recopilados de los interesados, según el proveedor de identidades (MSA o AAD) que se usó para iniciar sesión en el servicio de Azure DevOps.

- Los usuarios que se autentiquen con una cuenta respaldada por un inquilino de Azure (como, por ejemplo, una cuenta de AAD o MSA asociada a una suscripción a Azure) pueden seguir las instrucciones de [Solicitudes de interesados de Azure para el RGPD](../compliance/gdpr-dsr-azure.md).

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