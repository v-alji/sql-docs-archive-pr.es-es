---
title: Ejecutar Windows PowerShell desde SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672145"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="dce94-102">Ejecutar Windows PowerShell desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dce94-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="dce94-103">Puede iniciar sesiones de Windows PowerShell desde el **Explorador de objetos** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dce94-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="dce94-104">inicia Windows PowerShell, carga el `sqlps` módulo y establece el contexto de la ruta de acceso en el nodo asociado en el árbol de **Explorador de objetos** .</span><span class="sxs-lookup"><span data-stu-id="dce94-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="dce94-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="dce94-105">Before You Begin</span></span>  
 <span data-ttu-id="dce94-106">Cuando se especifica la ejecución de PowerShell para un objeto en **Explorador de objetos**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] inicia una sesión de Windows PowerShell en la que los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Complementos de PowerShell se han cargado y registrado.</span><span class="sxs-lookup"><span data-stu-id="dce94-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="dce94-107">La ruta de acceso para la sesión se preestablece en la ubicación del objeto en el que hizo clic con el botón secundario en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="dce94-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="dce94-108">Por ejemplo, si hace clic con el botón derecho en el objeto de base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] en el Explorador de objetos y selecciona **Iniciar PowerShell**, la ruta de acceso de Windows PowerShell se establece en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dce94-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="dce94-109">Para ejecutar PowerShell desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dce94-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="dce94-110">Abra **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="dce94-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="dce94-111">Navegue al nodo del objeto en el que trabajará.</span><span class="sxs-lookup"><span data-stu-id="dce94-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="dce94-112">Haga clic con el botón derecho en el objeto y seleccione **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dce94-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="dce94-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="dce94-113">Permissions</span></span>  
 <span data-ttu-id="dce94-114">Cuando se abre desde [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell no se ejecuta con privilegios de Administrador, lo que puede impedir algunas actividades como llamadas a WMI.</span><span class="sxs-lookup"><span data-stu-id="dce94-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce94-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dce94-115">See Also</span></span>  
 [<span data-ttu-id="dce94-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="dce94-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
