---
title: Importar directivas (cuadro de diálogo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663447"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="648eb-102">Importar directivas (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="648eb-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="648eb-103">Utilice este cuadro de diálogo para importar una o varias directivas (y su condición a la que se hace referencia) que se guardaron como archivos XML, en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="648eb-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="648eb-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="648eb-104">Options</span></span>  
 <span data-ttu-id="648eb-105">**Archivos para importar**</span><span class="sxs-lookup"><span data-stu-id="648eb-105">**Files to import**</span></span>  
 <span data-ttu-id="648eb-106">Para importar una directiva desde un archivo XML, escriba la ruta de acceso y el nombre del archivo, o use el botón Examinar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="648eb-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="648eb-107">**Reemplazar duplicados con elementos importados**</span><span class="sxs-lookup"><span data-stu-id="648eb-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="648eb-108">Seleccione esta opción para sobrescribir cualquier directiva o condición existente del mismo nombre si ya existe en esta instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="648eb-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="648eb-109">Una condición con una directiva dependiente no se puede sobrescribir a menos que la directiva dependiente se esté sobrescribiendo también.</span><span class="sxs-lookup"><span data-stu-id="648eb-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="648eb-110">Si no se selecciona esta opción, una condición existente que está utilizando la misma expresión de condición no producirá un error.</span><span class="sxs-lookup"><span data-stu-id="648eb-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="648eb-111">**Estado de directiva**</span><span class="sxs-lookup"><span data-stu-id="648eb-111">**Policy state**</span></span>  
 <span data-ttu-id="648eb-112">Seleccione el estado que desea para la directiva importada:</span><span class="sxs-lookup"><span data-stu-id="648eb-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="648eb-113">**Conservar el estado de las directivas al importar**</span><span class="sxs-lookup"><span data-stu-id="648eb-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="648eb-114">**Habilitar todas las directivas al importar**</span><span class="sxs-lookup"><span data-stu-id="648eb-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="648eb-115">**Deshabilitar todas las directivas al importar**</span><span class="sxs-lookup"><span data-stu-id="648eb-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648eb-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="648eb-116">See Also</span></span>  
 <span data-ttu-id="648eb-117">[Administrar servidores mediante administración basada en directivas](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="648eb-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="648eb-118">[Importar una directiva de administración basada en directivas](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="648eb-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="648eb-119">Exportar una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="648eb-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
