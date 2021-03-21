---
title: Regulación de la información sujeta a la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use directivas y etiquetas de retención de Microsoft 365 para administrar datos personales en su entorno de Microsoft 365.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928441"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="ff0fd-103">Regulación de la información sujeta a la regulación de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="ff0fd-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="ff0fd-104">Los controles de gobierno de la información se pueden usar en su entorno para ayudar a satisfacer las necesidades de cumplimiento de privacidad de datos, incluido un número específico del Reglamento general de protección de datos (RGPD), HIPAA-HITECH (la ley de privacidad del cuidado de la salud de los Estados Unidos), la Ley de protección de consumidores de California (CCPA) y la Ley de protección de datos de Brasil (LGPD).</span><span class="sxs-lookup"><span data-stu-id="ff0fd-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="ff0fd-105">Estos controles están principalmente en las siguientes áreas de solución:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="ff0fd-106">Directivas de retención</span><span class="sxs-lookup"><span data-stu-id="ff0fd-106">Retention policies</span></span>
- <span data-ttu-id="ff0fd-107">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="ff0fd-107">Retention labels</span></span>
- <span data-ttu-id="ff0fd-108">Administración de registros</span><span class="sxs-lookup"><span data-stu-id="ff0fd-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="ff0fd-109">Normativas de privacidad de datos que afectan a los controles de gobierno de la información</span><span class="sxs-lookup"><span data-stu-id="ff0fd-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="ff0fd-110">Esta es una lista de ejemplo de las normativas de privacidad de datos que pueden estar relacionadas con los controles de gobierno de la información:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="ff0fd-111">Artículo del RGPD (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="ff0fd-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="ff0fd-112">Artículo del RGPD (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="ff0fd-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="ff0fd-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="ff0fd-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="ff0fd-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="ff0fd-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="ff0fd-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="ff0fd-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="ff0fd-116">Artículo 46 de LGPD</span><span class="sxs-lookup"><span data-stu-id="ff0fd-116">LGPD Article 46</span></span>

<span data-ttu-id="ff0fd-117">Para obtener más información sobre estas [normativas,](information-protection-deploy-assess.md)vea el artículo evaluar los riesgos de privacidad de datos e identificar información confidencial.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="ff0fd-118">Para el gobierno de la información, las normativas de privacidad de datos suelen llamar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="ff0fd-119">Debe emplear un esquema técnico para la retención y eliminación de datos personales almacenados en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="ff0fd-120">Si va a almacenar datos personales, informe al interesado de cuánto tiempo se almacenarán los datos, que es una práctica estándar ahora en sistemas front-end web.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="ff0fd-121">Los datos personales deben protegerse contra el procesamiento accidental, la pérdida o la alteración mediante métodos verificables.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="ff0fd-122">Cualquier acción ejecutada con datos personales debe documentarse y esa documentación debe conservarse durante un período especificado.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="ff0fd-123">Dado que las normativas de privacidad de datos no son muy específicas en lo que respecta a la retención y eliminación de datos, es necesario tener en cuenta otros factores que pueden dictar directrices de gobierno de la información para la información personal almacenada en su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="ff0fd-124">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-124">Here are a few examples:</span></span>

- <span data-ttu-id="ff0fd-125">El envejecimiento de las cuentas de consumidor después de 5 años de inactividad y requiere la eliminación o anonimización de los datos de la cuenta después de ese punto, lo que requiere una orquestación entre el sistema que almacena los datos y los flujos de trabajo relacionados con las notificaciones y otras automatizacións.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="ff0fd-126">Configurar reglas para mantener las directivas y procedimientos relacionados con el RGPD durante tres años después de su sustitución, lo que se alinea con la programación de retención de la organización para las directivas y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="ff0fd-127">Mantener una suscripción independiente para comunicarse con los consumidores a través de su organización de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="ff0fd-128">Todas las comunicaciones de correo electrónico se conservaron y eliminaron después de dos semanas para reducir cualquier acumulación de la deuda de privacidad en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="ff0fd-129">Una pregunta clave para responder es:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-129">A key question to answer is:</span></span> 

- <span data-ttu-id="ff0fd-130">¿Durante cuánto tiempo es necesario mantener la información que contiene datos personales por motivos empresariales válidos para evitar prácticas de "mantenerla para siempre"?</span><span class="sxs-lookup"><span data-stu-id="ff0fd-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="ff0fd-131">Esto debe equilibrarse con las necesidades de retención para la continuidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="ff0fd-132">Independientemente de los motivos legales y empresariales para mantener o eliminar la información personal, Microsoft proporciona una serie de capacidades para implementar el esquema de gobierno de datos en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="ff0fd-133">Administración del gobierno de la información en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff0fd-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="ff0fd-134">Para empezar, vea [Manage information governance](../compliance/manage-information-governance.md) and Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="ff0fd-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="ff0fd-135">Desarrollar programaciones de retención de datos para contenedores, correo electrónico y contenido</span><span class="sxs-lookup"><span data-stu-id="ff0fd-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="ff0fd-136">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff0fd-136">Keep the following in mind:</span></span>

- <span data-ttu-id="ff0fd-137">Establecer una programación de retención de datos para tipos de información definidos debe considerarse un requisito previo para implementar cualquier esquema de retención o eliminación.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="ff0fd-138">Dado el número de tipos de información que la mayoría de las organizaciones consideran importantes y las programaciones de retención de registros grandes correspondientes que van con ellos, la implementación de una estrategia de administración de registros y retención de datos requiere planeación.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="ff0fd-139">La clave para establecer una estrategia de gobierno de datos eficaz de este tipo es centrarse en las funciones empresariales de mayor prioridad y los tipos de información que requieren una administración más formal.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="ff0fd-140">Algunos ejemplos son contratos legales, estados financieros y documentación de cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="ff0fd-141">Intente evitar tener una programación de retención independiente para cada tipo de información.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="ff0fd-142">Intente usar las categorías generales tanto como sea posible, por ejemplo, con programaciones de retención de 7 años para contenido empresarial general.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="ff0fd-143">Una vez que se conozcan mejor los tipos de información personal de su entorno, establezca programaciones de retención y eliminación para este tipo de contenido y ajuste la arquitectura de la información para facilitar el gobierno de este tipo de información.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="ff0fd-144">Por ejemplo, aísla información personal en sitios, bibliotecas o carpetas independientes con acceso controlado.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="ff0fd-145">Directivas de retención y etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="ff0fd-145">Retention policies and retention labels</span></span>

<span data-ttu-id="ff0fd-146">Use [directivas de retención y etiquetas de](../compliance/retention.md) retención para retener o eliminar contenido en Microsoft 365 que contenga o se espera que contenga datos personales.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="ff0fd-147">Administración de registros</span><span class="sxs-lookup"><span data-stu-id="ff0fd-147">Records management</span></span>

<span data-ttu-id="ff0fd-148">Use etiquetas de retención que [](../compliance/records-management.md) declaren el contenido un registro para implementar una solución de administración de registros para datos en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="ff0fd-149">Para la privacidad de los datos, las solicitudes de interesados (DSR) recibidas por el departamento legal se declaran un registro y se pueden almacenar indefinidamente o eliminarse con pruebas, para cumplir con las especificaciones de retención de actividades reglamentarias.</span><span class="sxs-lookup"><span data-stu-id="ff0fd-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>