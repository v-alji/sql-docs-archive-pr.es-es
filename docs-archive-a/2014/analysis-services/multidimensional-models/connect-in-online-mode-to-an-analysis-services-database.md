---
title: Conectar en modo en línea a una base de datos de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 363beb7132eae92907198979fe2d9892c5d07b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748364"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a><span data-ttu-id="f2dc5-102">Conectar con una base de datos de Analysis Services en modo en línea</span><span class="sxs-lookup"><span data-stu-id="f2dc5-102">Connect in Online Mode to an Analysis Services Database</span></span>
  <span data-ttu-id="f2dc5-103">Puede conectarse directamente a una base de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] datos existente y modificar directamente los objetos de esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-103">You can connect directly to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and directly modify objects within that database.</span></span> <span data-ttu-id="f2dc5-104">Si se conecta directamente con una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , los cambios realizados en los objetos tienen lugar inmediatamente y no se crea un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dc5-104">When you connect directly to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, changes to objects occur immediately and no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is created within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a><span data-ttu-id="f2dc5-105">Para conectarse directamente a una base de datos de Analysis Services mediante las Herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2dc5-105">To Connect Directly to an Analysis Services Database by using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="f2dc5-106">Abra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dc5-106">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f2dc5-107">En el menú **Archivo** , seleccione **Abrir** y haga clic en **Base de datos de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-107">On the **File** menu, point to **Open** and then click **Analysis Services Database**.</span></span>  
  
3.  <span data-ttu-id="f2dc5-108">Seleccione **Conectar con base de datos existente**.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-108">Select **Connect to existing database**.</span></span>  
  
4.  <span data-ttu-id="f2dc5-109">Especifique el nombre del servidor y el de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-109">Specify the server name and the database name.</span></span>  
  
     <span data-ttu-id="f2dc5-110">Puede escribir el nombre de la base de datos o hacer una consulta en el servidor para ver las bases de datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-110">You can either type the database name or query the server to view the existing databases on the server.</span></span>  
  
5.  <span data-ttu-id="f2dc5-111">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2dc5-111">Click **OK**.</span></span>  
  
     <span data-ttu-id="f2dc5-112">En ese momento, puede editar directamente los objetos de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dc5-112">You can now directly edit any objects within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dc5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2dc5-113">See Also</span></span>  
 <span data-ttu-id="f2dc5-114">[Trabajar con Analysis Services proyectos y bases de datos durante la fase de desarrollo](work-with-analysis-services-projects-and-databases-in-development.md) </span><span class="sxs-lookup"><span data-stu-id="f2dc5-114">[Working with Analysis Services Projects and Databases During the Development Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span></span>  
 [<span data-ttu-id="f2dc5-115">Crear modelos multidimensionales utilizando las herramientas de datos de SQL Server &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="f2dc5-115">Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;</span></span>](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  
