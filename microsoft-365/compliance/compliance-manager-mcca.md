---
title: Analizador de configuración de cumplimiento de Microsoft para administrador de cumplimiento
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar El analizador de configuración de cumplimiento de Microsoft para rápida ejecución con El Administrador de cumplimiento de Microsoft.
ms.openlocfilehash: 2b91ac274d7270f5be9530742cf711a3918b287d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570379"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="1f8d7-103">Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="1f8d7-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="1f8d7-104">**En este artículo:** Obtenga información sobre cómo instalar y ejecutar la herramienta Microsoft Compliance Configure Analyzer para empezar rápidamente con el Administrador de cumplimiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="1f8d7-105">Introducción al Analizador de configuración de cumplimiento de Microsoft (MCCA) (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="1f8d7-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="1f8d7-106">El Analizador de configuración de cumplimiento de Microsoft (MCCA) es una herramienta de vista previa que puede ayudarle a empezar a trabajar con [Microsoft Compliance Manager](compliance-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="1f8d7-107">MCCA es una utilidad basada en PowerShell que recuperará las configuraciones actuales de su organización y las validará con los procedimientos recomendados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="1f8d7-108">Estos procedimientos recomendados se basan en un conjunto de controles que incluyen normativas y estándares clave para la protección de datos y el gobierno de datos.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="1f8d7-109">MCCA puede ayudarle a ver rápidamente qué acciones de mejora en el administrador de cumplimiento se aplican al entorno actual de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="1f8d7-110">Cada acción identificada por MCCA le dará recomendaciones para la implementación, con vínculos directos al Administrador de cumplimiento y la solución aplicable para empezar a tomar medidas correctivas.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="1f8d7-111">Un recurso adicional para comprender MCCA es visitar las instrucciones [readme en GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="1f8d7-112">Esta página proporciona información detallada sobre los requisitos previos y proporciona instrucciones de instalación completas.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="1f8d7-113">No necesita una cuenta de GitHub para tener acceso a esta página.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="1f8d7-114">**Disponibilidad:** MCCA está disponible para todas las organizaciones con licencias de Office 365 y Microsoft 365 y clientes moderados, GCC High y del Departamento de Defensa (DoD) de la Comunidad gubernamental de Estados Unidos (GCC).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="1f8d7-115">Instalar MCCA y ejecutar un informe</span><span class="sxs-lookup"><span data-stu-id="1f8d7-115">Install MCCA and run a report</span></span>

<span data-ttu-id="1f8d7-116">Puede instalar la herramienta MCCA mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="1f8d7-117">Una vez que descargue e instale la herramienta, no es necesario repetir esos pasos para ejecutar informes.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="1f8d7-118">Cada vez que abra MCCA, le pedirá sus credenciales de inicio de sesión y generará un informe nuevo y actualizado.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="1f8d7-119">Paso 1: Instalar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f8d7-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="1f8d7-120">Para empezar, necesitará el módulo de PowerShell de Exchange Online (v2.0.3 o posterior) que esté disponible en la galería de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="1f8d7-121">[Obtener instrucciones de instalación](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="1f8d7-122">Paso 2: Instalar MCCA</span><span class="sxs-lookup"><span data-stu-id="1f8d7-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="1f8d7-123">Para instalar MCCA, empiece con PowerShell en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="1f8d7-124">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-124">Follow the steps below:</span></span>

1. <span data-ttu-id="1f8d7-125">Selecciona el botón **Inicio de** Windows.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="1f8d7-126">Escriba **PowerShell**, haga clic con el botón secundario **en Windows PowerShell** y, a continuación, seleccione Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="1f8d7-127">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="1f8d7-128">Paso 3: Ejecutar un informe</span><span class="sxs-lookup"><span data-stu-id="1f8d7-128">Step 3: Run a report</span></span>

<span data-ttu-id="1f8d7-129">Después de instalar MCCA, puede ejecutar MCCA y generar un informe.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="1f8d7-130">Para ejecutar un informe:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-130">To run a report:</span></span>

1. <span data-ttu-id="1f8d7-131">Abrir PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f8d7-131">Open PowerShell</span></span>
2. <span data-ttu-id="1f8d7-132">Ejecute el cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="1f8d7-133">Si es cliente de GCC High, deberá proporcionar un parámetro de entrada adicional para ejecutar el informe:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="1f8d7-134">Una vez que se ejecuta MCCA, realiza una comprobación de versión inicial y pide credenciales.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="1f8d7-135">En el símbolo del sistema Introducir el nombre de usuario, inicie sesión con la dirección de correo electrónico de su cuenta de Microsoft 365 ( vea los[roles aptos para crear informes](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="1f8d7-136">A continuación, escriba la contraseña en el símbolo del sistema de contraseña.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="1f8d7-137">A continuación, el informe tarda aproximadamente entre 2 y 5 minutos en generarse.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="1f8d7-138">Cuando haya terminado, se abrirá una ventana del explorador y se mostrará el informe HTML.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="1f8d7-139">Cada vez que ejecute la herramienta, pedirá sus credenciales y generará un nuevo informe.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="1f8d7-140">Este informe se almacena localmente en el directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="1f8d7-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="1f8d7-142">Puede obtener acceso a los informes generados anteriormente desde este directorio.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="1f8d7-143">Descripción del informe</span><span class="sxs-lookup"><span data-stu-id="1f8d7-143">Understanding your report</span></span>

<span data-ttu-id="1f8d7-144">El informe refleja los datos en función de la fecha y hora en que se generó.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="1f8d7-145">La sección superior proporciona detalles sobre cuándo se generó, el nombre de la organización y el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="1f8d7-146">Informes basados en geolocalización</span><span class="sxs-lookup"><span data-stu-id="1f8d7-146">Geolocation-based reporting</span></span>

<span data-ttu-id="1f8d7-147">La **sección** Nota muestra que el informe se personaliza en función de la ubicación geográfica del inquilino.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="1f8d7-148">Las recomendaciones enumeradas en la herramienta serán específicas de su país o región.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="1f8d7-149">La selección de geolocalización se usa para evaluar los tipos de información confidencial (SIT) que son relevantes para esa geolocalización y generar un informe que se alinee con su país o región.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="1f8d7-150">Elija las geolocalizaciones en función de los datos que tenga en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="1f8d7-151">Para cambiar la información de ubicación del informe, debe proporcionar un parámetro de entrada de geolocalización (-Geo).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="1f8d7-152">Puede elegir una o varias geolocalizaciones aplicables a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="1f8d7-153">Siga estas instrucciones para ejecutar un informe en función de una ubicación específica:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="1f8d7-154">Abrir PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f8d7-154">Open PowerShell</span></span>
2. <span data-ttu-id="1f8d7-155">Para especificar una región determinada, ejecutará un cmdlet con los números de la tabla siguiente que corresponden al país o región.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="1f8d7-156">Escriba varios números separándolos con una coma.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="1f8d7-157">Por ejemplo, el cmdlet siguiente ejecutará un informe personalizado para Asia-Pacific y Japón:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="1f8d7-158">Input</span><span class="sxs-lookup"><span data-stu-id="1f8d7-158">Input</span></span> |  <span data-ttu-id="1f8d7-159">País o región</span><span class="sxs-lookup"><span data-stu-id="1f8d7-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="1f8d7-160">1</span><span class="sxs-lookup"><span data-stu-id="1f8d7-160">1</span></span> | <span data-ttu-id="1f8d7-161">Asia-Pacífico</span><span class="sxs-lookup"><span data-stu-id="1f8d7-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="1f8d7-162">2</span><span class="sxs-lookup"><span data-stu-id="1f8d7-162">2</span></span> | <span data-ttu-id="1f8d7-163">Australia</span><span class="sxs-lookup"><span data-stu-id="1f8d7-163">Australia</span></span> |
  | <span data-ttu-id="1f8d7-164">3</span><span class="sxs-lookup"><span data-stu-id="1f8d7-164">3</span></span> | <span data-ttu-id="1f8d7-165">Canadá</span><span class="sxs-lookup"><span data-stu-id="1f8d7-165">Canada</span></span> |
  | <span data-ttu-id="1f8d7-166">4 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-166">4</span></span> | <span data-ttu-id="1f8d7-167">Europa (excluyendo Francia) / Oriente Medio / África</span><span class="sxs-lookup"><span data-stu-id="1f8d7-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="1f8d7-168">5 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-168">5</span></span> | <span data-ttu-id="1f8d7-169">Francia</span><span class="sxs-lookup"><span data-stu-id="1f8d7-169">France</span></span> |
  | <span data-ttu-id="1f8d7-170">6 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-170">6</span></span> | <span data-ttu-id="1f8d7-171">India</span><span class="sxs-lookup"><span data-stu-id="1f8d7-171">India</span></span> |
  | <span data-ttu-id="1f8d7-172">7 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-172">7</span></span> | <span data-ttu-id="1f8d7-173">Japón</span><span class="sxs-lookup"><span data-stu-id="1f8d7-173">Japan</span></span> |
  | <span data-ttu-id="1f8d7-174">8 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-174">8</span></span> | <span data-ttu-id="1f8d7-175">Corea</span><span class="sxs-lookup"><span data-stu-id="1f8d7-175">Korea</span></span> |
  | <span data-ttu-id="1f8d7-176">9 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-176">9</span></span> | <span data-ttu-id="1f8d7-177">Norteamérica (excepto Canadá)</span><span class="sxs-lookup"><span data-stu-id="1f8d7-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="1f8d7-178">10  </span><span class="sxs-lookup"><span data-stu-id="1f8d7-178">10</span></span> | <span data-ttu-id="1f8d7-179">Sudamérica</span><span class="sxs-lookup"><span data-stu-id="1f8d7-179">South America</span></span> |
  | <span data-ttu-id="1f8d7-180">11</span><span class="sxs-lookup"><span data-stu-id="1f8d7-180">11</span></span> | <span data-ttu-id="1f8d7-181">Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="1f8d7-181">South Africa</span></span> |
  | <span data-ttu-id="1f8d7-182">12 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-182">12</span></span> | <span data-ttu-id="1f8d7-183">Suiza</span><span class="sxs-lookup"><span data-stu-id="1f8d7-183">Switzerland</span></span> |
  | <span data-ttu-id="1f8d7-184">13</span><span class="sxs-lookup"><span data-stu-id="1f8d7-184">13</span></span> | <span data-ttu-id="1f8d7-185">Emiratos Árabes Unidos</span><span class="sxs-lookup"><span data-stu-id="1f8d7-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="1f8d7-186">14 </span><span class="sxs-lookup"><span data-stu-id="1f8d7-186">14</span></span> | <span data-ttu-id="1f8d7-187">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1f8d7-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="1f8d7-188">El informe siempre incluirá tipos de información confidencial internacional compatibles con MCCA, como código SWIFT, número de tarjeta de crédito, etc.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="1f8d7-189">Informes basados en roles</span><span class="sxs-lookup"><span data-stu-id="1f8d7-189">Role-based reporting</span></span>

<span data-ttu-id="1f8d7-190">El informe también se personalizará en función del rol.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="1f8d7-191">En la tabla siguiente se muestran los roles a los que tienen acceso las secciones del informe.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="1f8d7-192">Es posible que otros roles de la organización (no incluidos en la tabla siguiente) no puedan ejecutar la herramienta o que ejecuten la herramienta y tengan acceso limitado a la información del informe final.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="1f8d7-193">![MCCA: roles](../media/compliance-manager-mcca-roles.png "Roles mcca")</span><span class="sxs-lookup"><span data-stu-id="1f8d7-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="1f8d7-194">Excepciones:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-194">Exceptions:</span></span>
1. <span data-ttu-id="1f8d7-195">Los usuarios no podrán generar informes para IP aparte de la sección "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="1f8d7-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="1f8d7-196">Los usuarios podrán generar informes para IP aparte de la sección "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="1f8d7-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="1f8d7-197">Los usuarios podrán generar informes para IP aparte de la sección "Habilitar el cumplimiento de la comunicación en O365".</span><span class="sxs-lookup"><span data-stu-id="1f8d7-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="1f8d7-198">Los usuarios no podrán generar informes para IP aparte de la sección "Habilitar auditoría en Office 365".</span><span class="sxs-lookup"><span data-stu-id="1f8d7-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="1f8d7-199">Los usuarios podrán generar informes para IP aparte de la sección "Habilitar auditoría en Office 365".</span><span class="sxs-lookup"><span data-stu-id="1f8d7-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="1f8d7-200">Sección Resumen de soluciones</span><span class="sxs-lookup"><span data-stu-id="1f8d7-200">Solutions Summary section</span></span>

<span data-ttu-id="1f8d7-201">La **sección Resumen de** soluciones del informe ofrece información general sobre las acciones de mejora que su organización puede llevar a cabo en el Administrador de cumplimiento para ayudar a mejorar su posición de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="1f8d7-202">![MCCA: resumen de soluciones](../media/compliance-manager-mcca-solutions.png "Pantalla Resumen de soluciones mcca")</span><span class="sxs-lookup"><span data-stu-id="1f8d7-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="1f8d7-203">MCCA evalúa las configuraciones actuales con respecto a las acciones de mejora recomendadas en el Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="1f8d7-204">Cualquier acción de mejora identificada por la herramienta MCCA como que necesita atención se enumerará en esta sección.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="1f8d7-205">Junto a cada solución de Microsoft hay cuadros codificados por colores que indican el número de elementos que corresponden a acciones de mejora en el Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="1f8d7-206">Las acciones se desglosan en tres estados de estado:</span><span class="sxs-lookup"><span data-stu-id="1f8d7-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="1f8d7-207">**Aceptar:** las acciones que cumplen las condiciones recomendadas y no necesitan atención en este momento</span><span class="sxs-lookup"><span data-stu-id="1f8d7-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="1f8d7-208">**Mejora:** acciones que necesitan atención</span><span class="sxs-lookup"><span data-stu-id="1f8d7-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="1f8d7-209">**Recomendación:** acciones que no necesitan atención, pero para las que se recomiendan procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="1f8d7-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="1f8d7-210">Seleccione un cuadro para ver las mejoras y recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="1f8d7-211">**Elementos con el estado de mejora**</span><span class="sxs-lookup"><span data-stu-id="1f8d7-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="1f8d7-212">Selecciona el desplegable junto a la **etiqueta Mejora** a la derecha de la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="1f8d7-213">Verás un resumen rápido y detalles sobre la configuración actual y las acciones de mejora recomendadas.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="1f8d7-214">El resumen incluye vínculos directos al Administrador de cumplimiento, la solución aplicable en el Centro de cumplimiento de Microsoft 365 y documentación relevante.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="1f8d7-215">Al hacer clic en el vínculo Administrador de cumplimiento, se muestra una vista filtrada de todas las acciones de mejora de esa solución que aún no se han implementado.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="1f8d7-216">Desde allí, puede ver el número de puntos que puede lograr para aumentar la puntuación de cumplimiento [y](compliance-score-calculation.md)las evaluaciones a las que se aplican, así como las normativas y certificaciones aplicables.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="1f8d7-217">Para DLP, hay un botón **Script** de corrección que le proporciona un script de PowerShell generado previamente en función de lo que se recomienda.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="1f8d7-218">Puede copiarla y pegarla directamente en la consola de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="1f8d7-219">Creará una directiva DLP en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="1f8d7-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="1f8d7-220">**Elementos con estado de recomendación**</span><span class="sxs-lookup"><span data-stu-id="1f8d7-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="1f8d7-221">Selecciona el desplegable junto a la **etiqueta** Recomendación a la derecha de la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="1f8d7-222">Verá un resumen del entorno actual de Microsoft 365 de su organización relacionado con la acción de mejora, junto con los procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="1f8d7-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="1f8d7-223">Recursos</span><span class="sxs-lookup"><span data-stu-id="1f8d7-223">Resources</span></span>

<span data-ttu-id="1f8d7-224">Para obtener información más detallada sobre cómo instalar, configurar y usar MCCA, consulte las instrucciones README en [GitHub](https://github.com/OfficeDev/MCCA#overview) (no se requiere una cuenta de GitHub).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="1f8d7-225">Para obtener más información Windows PowerShell, comience [en Cómo usar la documentación de PowerShell](/powershell/scripting/how-to-use-docs?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="1f8d7-226">Vea también [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1f8d7-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>