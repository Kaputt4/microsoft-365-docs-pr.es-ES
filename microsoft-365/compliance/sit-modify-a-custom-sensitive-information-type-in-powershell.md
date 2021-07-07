---
title: Modificar un tipo de información confidencial personalizada con PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo modificar una información confidencial personalizada con PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322958"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="755e9-103">Modificar un tipo de información confidencial personalizada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="755e9-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="755e9-104">Crear un tipo personalizado de información confidencial en PowerShell del Centro de cumplimiento requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="755e9-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="755e9-105">Exporte el paquete de reglas existente que contiene el tipo de información confidencial a un archivo XML (o, si lo tiene, use el archivo XML existente).</span><span class="sxs-lookup"><span data-stu-id="755e9-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="755e9-106">Modifique el tipo personalizado de información confidencial en el archivo XML exportado.</span><span class="sxs-lookup"><span data-stu-id="755e9-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="755e9-107">Importe el archivo XML actualizado en el paquete de reglas existentes.</span><span class="sxs-lookup"><span data-stu-id="755e9-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="755e9-108">Para conectarse a PowerShell del Centro de cumplimiento, vea [Conectarse a PowerShell del Centro de cumplimiento](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="755e9-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="755e9-109">Paso 1: exportar el paquete de reglas existentes a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="755e9-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="755e9-110">Si tiene una copia del archivo XML (si, por ejemplo, lo acaba de crear y de importar), puede saltar al paso siguiente para modificar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="755e9-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="755e9-111">Si aún no lo sabe, ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) para buscar el nombre del paquete de reglas personalizado:</span><span class="sxs-lookup"><span data-stu-id="755e9-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="755e9-p101">El paquete de reglas integradas que contiene los tipos de información confidencial integrados se denomina paquete de reglas de Microsoft. El paquete de reglas que contiene los tipos de información confidencial personalizados que creó en la interfaz de usuario del Centro de cumplimiento se llama Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="755e9-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="755e9-114">Use el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) para almacenar el paquete de reglas personalizadas en una variable:</span><span class="sxs-lookup"><span data-stu-id="755e9-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="755e9-115">Por ejemplo, si el paquete de reglas se llama "Paquete de reglas personalizado de Id. de empleado", ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="755e9-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="755e9-116">Use el cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) para exportar el paquete de reglas personalizado a un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="755e9-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="755e9-117">En este ejemplo se exporta el paquete de reglas para el archivo denominado ExportedRulePackage.xml en la carpeta C:\Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="755e9-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="755e9-118">Paso 2: modificar el tipo de información confidencial en el archivo XML exportado</span><span class="sxs-lookup"><span data-stu-id="755e9-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="755e9-119">Anteriormente en este tema se describen los tipos de información confidencial en el archivo XML y otros elementos del archivo.</span><span class="sxs-lookup"><span data-stu-id="755e9-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="755e9-120">Paso 3: importar el archivo XML actualizado en el paquete de reglas existentes</span><span class="sxs-lookup"><span data-stu-id="755e9-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="755e9-121">Para importar el archivo XML actualizado en el paquete de reglas existentes, use el cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="755e9-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="755e9-122">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="755e9-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="755e9-123">Más información</span><span class="sxs-lookup"><span data-stu-id="755e9-123">More information</span></span>

- [<span data-ttu-id="755e9-124">Obtenga más información acerca de la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="755e9-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="755e9-125">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="755e9-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="755e9-126">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="755e9-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
