---
title: Ampliar la cobertura de búsqueda avanzada con la configuración correcta
description: Comprueba la configuración de auditoría en dispositivos Windows y otras configuraciones para asegurarte de obtener los datos más completos en la búsqueda avanzada
keywords: búsqueda avanzada, incidente, pivot, entidad, configuración de auditoría, administración de cuentas de usuario, administración de grupos de seguridad, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, mdatp, ATP de Microsoft Defender, Microsoft Defender para endpoint, Windows Defender, ATP de Windows Defender, protección contra amenazas avanzada de Windows Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500615"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="cf07a-104">Ampliar la cobertura de búsqueda avanzada con la configuración correcta</span><span class="sxs-lookup"><span data-stu-id="cf07a-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf07a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cf07a-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf07a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cf07a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="cf07a-107">[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="cf07a-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="cf07a-108">Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="cf07a-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="cf07a-109">Auditoría de seguridad avanzada en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="cf07a-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="cf07a-110">Activa esta configuración de auditoría avanzada para asegurarte de obtener datos sobre actividades en tus dispositivos, incluida la administración de cuentas locales, la administración de grupos de seguridad local y la creación de servicios.</span><span class="sxs-lookup"><span data-stu-id="cf07a-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="cf07a-111">Datos</span><span class="sxs-lookup"><span data-stu-id="cf07a-111">Data</span></span> | <span data-ttu-id="cf07a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf07a-112">Description</span></span> | <span data-ttu-id="cf07a-113">Tabla de esquema</span><span class="sxs-lookup"><span data-stu-id="cf07a-113">Schema table</span></span> | <span data-ttu-id="cf07a-114">Cómo establecer la configuración</span><span class="sxs-lookup"><span data-stu-id="cf07a-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="cf07a-115">Administración de cuentas</span><span class="sxs-lookup"><span data-stu-id="cf07a-115">Account management</span></span> | <span data-ttu-id="cf07a-116">Eventos capturados como varios valores que indican la creación, eliminación y `ActionType` otras actividades relacionadas con la cuenta local</span><span class="sxs-lookup"><span data-stu-id="cf07a-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="cf07a-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cf07a-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cf07a-118">- Implementar una directiva de auditoría de seguridad avanzada: [Auditar administración de cuentas de usuario](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="cf07a-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="cf07a-119">- [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cf07a-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="cf07a-120">Administración de grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="cf07a-120">Security group management</span></span> | <span data-ttu-id="cf07a-121">Eventos capturados como varios valores que indican la creación de grupos `ActionType` de seguridad locales y otras actividades de administración de grupos locales</span><span class="sxs-lookup"><span data-stu-id="cf07a-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="cf07a-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cf07a-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cf07a-123">- Implementar una directiva de auditoría de seguridad avanzada: [Auditar la administración de grupos de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="cf07a-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="cf07a-124">- [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cf07a-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="cf07a-125">Instalación del servicio</span><span class="sxs-lookup"><span data-stu-id="cf07a-125">Service installation</span></span> | <span data-ttu-id="cf07a-126">Eventos capturados con el valor , que indican que se ha creado `ActionType` `ServiceInstalled` un servicio</span><span class="sxs-lookup"><span data-stu-id="cf07a-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="cf07a-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cf07a-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cf07a-128">- Implementar una directiva de auditoría de seguridad avanzada: [Extensión del sistema de seguridad de auditoría](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="cf07a-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="cf07a-129">- [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cf07a-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf07a-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cf07a-130">Related topics</span></span>

- [<span data-ttu-id="cf07a-131">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="cf07a-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf07a-132">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="cf07a-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cf07a-133">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="cf07a-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="cf07a-134">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="cf07a-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="cf07a-135">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="cf07a-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cf07a-136">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="cf07a-136">Custom detections overview</span></span>](overview-custom-detections.md)
