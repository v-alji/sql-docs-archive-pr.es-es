---
title: 'Lección 1: Crear objetos de base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747840"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="a9b29-102">Lección 1: Creación de objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="a9b29-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="a9b29-103">En esta lección se muestra cómo crear una base de datos, crear una tabla en la base de datos y, a continuación, tener acceso a los datos de la tabla y cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="a9b29-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="a9b29-104">Puesto que esta lección es una introducción al uso de [!INCLUDE[tsql](../includes/tsql-md.md)], no usa ni describe las múltiples opciones disponibles para estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="a9b29-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="a9b29-105">se pueden escribir y enviar a [!INCLUDE[ssDE](../includes/ssde-md.md)] de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="a9b29-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="a9b29-106">Mediante el uso de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b29-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a9b29-107">En este tutorial se supone que se usa [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], pero también puede usarse [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, disponible como descarga gratuita en el [Centro de descargas de Microsoft](https://www.microsoft.com/download/details.aspx?id=14630).</span><span class="sxs-lookup"><span data-stu-id="a9b29-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="a9b29-108">Mediante el uso de la [utilidad sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a9b29-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="a9b29-109">Mediante la conexión desde una aplicación que cree.</span><span class="sxs-lookup"><span data-stu-id="a9b29-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="a9b29-110">El código se ejecuta en [!INCLUDE[ssDE](../includes/ssde-md.md)] de la misma forma y con los mismos permisos, independientemente de cómo envíe las instrucciones de código.</span><span class="sxs-lookup"><span data-stu-id="a9b29-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="a9b29-111">Para ejecutar instrucciones de [!INCLUDE[tsql](../includes/tsql-md.md)] en [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], abra [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] y conéctese a una instancia de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b29-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a9b29-112">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9b29-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="a9b29-113">Crear una base de datos &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b29-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="a9b29-114">Crear una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b29-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="a9b29-115">Insertar y actualizar datos en una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b29-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="a9b29-116">Leer datos de una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b29-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="a9b29-117">Resumen: Creación de objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="a9b29-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a9b29-118">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="a9b29-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a9b29-119">Crear una base de datos &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b29-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  
