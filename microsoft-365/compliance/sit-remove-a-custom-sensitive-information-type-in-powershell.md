---
title: Quitar un tipo de información confidencial personalizada con PowerShell
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
description: Obtenga información sobre cómo quitar un tipo de información confidencial personalizada con PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322955"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="4a3c4-103">Quitar un tipo de información confidencial personalizada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a3c4-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="4a3c4-104">En PowerShell del Centro de cumplimiento, hay dos métodos para quitar los tipos personalizados de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="4a3c4-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="4a3c4-105">**Quitar tipos de información confidencial** personalizados individuales: use el método documentado en Modificar un tipo de información confidencial personalizado con [PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="4a3c4-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="4a3c4-106">Exporte el paquete de reglas personalizado que contiene el tipo de información confidencial personalizada, quite el tipo de información confidencial del archivo XML e importe el archivo XML actualizado de nuevo al paquete de reglas personalizado existente.</span><span class="sxs-lookup"><span data-stu-id="4a3c4-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="4a3c4-107">**Quitar un paquete de reglas personalizado y todos los tipos de información confidencial que contiene**: este método se documenta en esta sección.</span><span class="sxs-lookup"><span data-stu-id="4a3c4-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="4a3c4-108">Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4a3c4-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="4a3c4-109">Conectar con el Centro de seguridad y cumplimiento de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a3c4-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="4a3c4-110">Para quitar un paquete de reglas personalizado, use el cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="4a3c4-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="4a3c4-111">Puede usar el valor de nombre (en cualquier idioma) o el valor (GUID) `RulePack id` para identificar el paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="4a3c4-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="4a3c4-112">En este ejemplo se quita el paquete de reglas denominado "Paquete de reglas personalizado de Id. de empleado".</span><span class="sxs-lookup"><span data-stu-id="4a3c4-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="4a3c4-113">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="4a3c4-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="4a3c4-114">Para comprobar que ha quitado correctamente un nuevo tipo personalizado de información confidencial, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a3c4-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="4a3c4-115">Ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) y compruebe que ya no se muestra el paquete de reglas en la lista:</span><span class="sxs-lookup"><span data-stu-id="4a3c4-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="4a3c4-116">Ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para comprobar que ya no aparecen los tipos de información confidencial en el paquete de reglas que ha quitado:</span><span class="sxs-lookup"><span data-stu-id="4a3c4-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="4a3c4-117">Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.</span><span class="sxs-lookup"><span data-stu-id="4a3c4-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="4a3c4-118">Reemplace \<Name\> con el valor de Nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para comprobar que el tipo de información confidencial ya no aparece:</span><span class="sxs-lookup"><span data-stu-id="4a3c4-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="4a3c4-119">Más información</span><span class="sxs-lookup"><span data-stu-id="4a3c4-119">More information</span></span>

- [<span data-ttu-id="4a3c4-120">Obtenga más información acerca de la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="4a3c4-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="4a3c4-121">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4a3c4-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="4a3c4-122">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="4a3c4-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
