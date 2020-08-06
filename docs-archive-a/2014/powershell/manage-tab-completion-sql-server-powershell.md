---
title: Administración de la finalización mediante tabulador (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677732"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="36692-102">Administrar la finalización mediante tabulador (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="36692-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="36692-103">Los complementos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell presentan tres variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` y `$SqlServerIncludeSystemObjects`) para controlar la finalización mediante el tabulador de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36692-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="36692-104">La finalización mediante el tabulador reduce la cantidad de texto que se debe escribir al devolver las tablas de elementos cuyos nombres empiezan por la cadena que está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="36692-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="36692-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="36692-105">Before You Begin</span></span>  
 <span data-ttu-id="36692-106">Con la finalización mediante el tabulador de PowerShell, cuando se ha escrito parte de una ruta de acceso o nombre de cmdlet, se puede presionar la tecla Tab para obtener una lista de los elementos cuyos nombres coincidan con lo que ya se ha escrito.</span><span class="sxs-lookup"><span data-stu-id="36692-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="36692-107">Se puede seleccionar a continuación el elemento que desee en la lista sin tener que escribir el resto del nombre.</span><span class="sxs-lookup"><span data-stu-id="36692-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="36692-108">Si está trabajando en una base de datos que tiene muchos objetos, las listas para finalización mediante tabulador pueden llegar a ser muy grandes.</span><span class="sxs-lookup"><span data-stu-id="36692-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="36692-109">Algunos tipos de objeto de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , como las vistas, también tienen una gran cantidad de objetos de sistema.</span><span class="sxs-lookup"><span data-stu-id="36692-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="36692-110">Los complementos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] presentan tres variables del sistema que se pueden usar para controlar la cantidad de información presentada por la finalización mediante tabulador y **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="36692-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="36692-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="36692-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="36692-112">Especifica el número máximo de objetos que se incluyen en una lista de finalización mediante tabulador.</span><span class="sxs-lookup"><span data-stu-id="36692-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="36692-113">Si selecciona Tab en un nodo de ruta de acceso que tiene más de *n* objetos, la lista de finalización mediante tabulador se trunca en *n*.</span><span class="sxs-lookup"><span data-stu-id="36692-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="36692-114">*n* es un entero.</span><span class="sxs-lookup"><span data-stu-id="36692-114">*n* is an integer.</span></span> <span data-ttu-id="36692-115">El valor predeterminado es 0, es decir, no hay límite para el número de objetos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="36692-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="36692-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="36692-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="36692-117">Especifica el número máximo de objetos mostrados por **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="36692-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="36692-118">Si se ejecuta **Get-ChildItem** en un nodo de ruta de acceso que tiene más de *n* objetos, la lista se trunca en *n*.</span><span class="sxs-lookup"><span data-stu-id="36692-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="36692-119">*n* es un entero.</span><span class="sxs-lookup"><span data-stu-id="36692-119">*n* is an integer.</span></span> <span data-ttu-id="36692-120">El valor predeterminado es 0, es decir, no hay límite para el número de objetos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="36692-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="36692-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="36692-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="36692-122">Si es **$True**, los objetos del sistema se muestran con finalización mediante tabulador y **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="36692-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="36692-123">Si es **$False**, no se muestran objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="36692-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="36692-124">La configuración predeterminada es **$false**.</span><span class="sxs-lookup"><span data-stu-id="36692-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="36692-125">Establecer las variables de finalización mediante tabulador de SQL Server</span><span class="sxs-lookup"><span data-stu-id="36692-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="36692-126">Para cualquiera de las variables a las que desee cambiar el valor predeterminado, establezca la variable en el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="36692-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="36692-127">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="36692-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="36692-128">En el ejemplo siguiente se establecen las tres variables y se enumeran sus valores:</span><span class="sxs-lookup"><span data-stu-id="36692-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="36692-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36692-129">See Also</span></span>  
 [<span data-ttu-id="36692-130">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="36692-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
